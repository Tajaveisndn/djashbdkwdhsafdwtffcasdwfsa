print("Solara Menu 1.0")
local TweenService = game:GetService("TweenService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
local Quests = {
ChocQuest1 = {
    Position = CFrame.new(-16541.0215, 54.770813, 1051.46118, 0.0410757065, -0, -0.999156058, 0, 1, -0, 0.999156058, 0, 0.0410757065),
    Location = "Tiki Island",
    Quests = {
        {
            Level = 2500,
            Number = 1,
            MobName = "Sun-kissed Warrior [Lv. 2500]",
            QuestName = "TikiQuest2",
            LevelRequire = 2500,
            Mon = "Sun-kissed Warrior",
            MonQ = 8
        },
        {
            Level = 2525,
            Number = 2,
            MobName = "Isle Champion [Lv. 2525]",
            QuestName = "TikiQuest2",
            LevelRequire = 2525,
            Mon = "Isle Champion",
            MonQ = 8
        }
    }
}
}

-- Adiciona verificação de personagem quando ele for recarregado
player.CharacterAdded:Connect(function(char)
    character = char
    humanoidRootPart = char:WaitForChild("HumanoidRootPart")
end)

function GetCurrentQuest()
    local CurrQuest = nil
    local HighestLevel = -1
    local playerLevel = player.Data.Level.Value
    
    pcall(function() -- Adiciona pcall para evitar erros
        for npcmain, configs in pairs(Quests) do
            for index, quest in ipairs(configs.Quests) do
                if playerLevel >= quest.LevelRequire and quest.LevelRequire > HighestLevel then
                    HighestLevel = quest.LevelRequire
                    CurrQuest = {
                        QuestName = quest.QuestName,
                        Position = configs.Position,
                        Number = index,
                        Level = quest.LevelRequire,
                        MobName = quest.MobName,
                        MonQ = quest.MonQ,
                        Location = configs.Location,
                        Mon = quest.Mon
                    }
                end
            end
        end
    end)
    
    return CurrQuest
end

local function TweenToQuest(questData)
    if not questData or not questData.Position then return end
    if not character or not humanoidRootPart then return end
    
    local GettingQuest = true
    
    -- Adiciona verificação de distância máxima para evitar tweens muito longos
    local distance = math.min((humanoidRootPart.Position - questData.Position.Position).Magnitude, 10000)
    local speed = distance > 350 and 300 or 11000
    local tweenInfo = TweenInfo.new(distance / speed, Enum.EasingStyle.Linear)
    
    -- Desativa colisões
    pcall(function()
        for _, part in pairs(character:GetDescendants()) do
            if part:IsA("BasePart") or part:IsA("MeshPart") then
                part.CanCollide = false
            end
        end
    end)
    
    local bodyVelocity = Instance.new("BodyVelocity")
    bodyVelocity.Name = "QuestTweenVelocity"
    bodyVelocity.Parent = humanoidRootPart
    bodyVelocity.MaxForce = Vector3.new(math.huge, math.huge, math.huge)
    bodyVelocity.Velocity = Vector3.new(0, 0, 0)
    
    local tween = TweenService:Create(humanoidRootPart, tweenInfo, {CFrame = questData.Position})
    
    tween.Completed:Connect(function()
        -- Reativa colisões
        pcall(function()
            for _, part in pairs(character:GetDescendants()) do
                if part:IsA("BasePart") or part:IsA("MeshPart") then
                    part.CanCollide = true
                end
            end
        end)
        
        if bodyVelocity and bodyVelocity.Parent then
            bodyVelocity:Destroy()
        end
        
        GettingQuest = false
        
        -- Tenta pegar a quest
        pcall(function()
            ReplicatedStorage.Remotes.CommF_:InvokeServer("StartQuest", questData.QuestName, questData.Number)
        end)
        
        -- Verifica se ainda tem quest atual antes de chamar bringMobs
        local currentQuest = GetCurrentQuest()
        if currentQuest and currentQuest.Mon then
            bringMobs(humanoidRootPart, currentQuest.Mon)
        end
    end)
    
    tween:Play()
end

local function StartQuestHunt()
    local questData = GetCurrentQuest()
    if questData then
        TweenToQuest(questData)
    end
end

-- Conexão com mudança de nível
local function onLevelChanged()
    pcall(function()
        PlayerLevel = player.Data.Level.Value
        StartQuestHunt()
    end)
end

player.Data.Level.Changed:Connect(onLevelChanged)

-- Inicia o auto farm
StartQuestHunt()
