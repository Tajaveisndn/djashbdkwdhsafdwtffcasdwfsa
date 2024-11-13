local TweenService = game:GetService("TweenService")
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
local Quests = {
    BanditQuest1 = {
        Position = CFrame.new(1059.37195, 15.4495068, 1550.4231, 0.939700544, -0, -0.341998369, 0, 1, -0, 0.341998369, 0, 0.939700544),
        Location = "Starter Island",
        Quests = {
            {
                Level = 0,
                Number = 1,
                MobName = "Bandit [Lv. 0]",
                QuestName = "BanditQuest1",
                LevelRequire = 0,
                Mon = "Bandit",
                MonQ = 5
            }
        }
    },

    JungleQuest = {
        Position = CFrame.new(-1598.08911, 35.5501175, 153.377838, 0, 0, 1, 0, 1, -0, -1, 0, 0),
        Location = "Jungle Area",
        Quests = {
            {
                Level = 10,
                MobName = "Monkey [Lv. 10]",
                Number = 1,
                QuestName = "JungleQuest",
                LevelRequire = 10,
                Mon = "Monkey",
                MonQ = 6
            },
            {
                Level = 15,
                MobName = "Gorilla [Lv. 15]",
                QuestName = "JungleQuest",
                Number = 2,
                LevelRequire = 15,
                Mon = "Gorilla",
                MonQ = 8
            },
            {
                Level = 20,
                MobName = "The Gorilla King [Lv. 20]",
                QuestName = "JungleQuest",
                Number = 3,
                LevelRequire = 20,
                Mon = "The Gorilla King",
                MonQ = 1
            }
        }
    },

    BuggyQuest1 = {
        Position = CFrame.new(-1141.07483, 4.10001802, 3831.5498, 0.965929627, -0, -0.258804798, 0, 1, -0, 0.258804798, 0, 0.965929627),
        Location = "Buggy Area",
        Quests = {
            {
                Level = 30,
                MobName = "Pirate [Lv. 30]",
                Numer = 1,
                QuestName = "BuggyQuest1",
                LevelRequire = 30,
                Mon = "Pirate",
                MonQ = 8
            },
            {
                Level = 40,
                MobName = "Brute [Lv. 40]",
                Number = 2,
                QuestName = "BuggyQuest1",
                LevelRequire = 40,
                Mon = "Brute",
                MonQ = 8
            },
            {
                Level = 55,
                MobName = "Bobby [Lv. 55]",
                QuestName = "BuggyQuest1",
                Number = 3,
                LevelRequire = 55,
                Mon = "Bobby",
                MonQ = 1
            }
        }
    },

    DesertQuest = {
        Position = CFrame.new(894.488647, 5.14000702, 4392.43359, 0.819155693, -0, -0.573571265, 0, 1, -0, 0.573571265, 0, 0.819155693),
        Location = "Desert Zone",
        Quests = {
            {
                Level = 60,
                MobName = "Desert Bandit [Lv. 60]",
                Number = 1,
                QuestName = "DesertQuest",
                LevelRequire = 60,
                Mon = "Desert Bandit",
                MonQ = 8
            },
            {
                Level = 75,
                MobName = "Desert Officer [Lv. 75]",
                Number = 2,
                QuestName = "DesertQuest",
                LevelRequire = 75,
                Mon = "Desert Officer",
                MonQ = 6
            }
        }
    },

    SnowQuest = {
        Position = CFrame.new(1389.74451, 86.6520844, -1298.90796, -0.342042685, 0, 0.939684391, 0, 1, 0, -0.939684391, 0, -0.342042685),
        Location = "Snowy Mountains",
        Quests = {
            {
                Level = 90,
                MobName = "Snow Bandit [Lv. 90]",
                Number = 1,
                QuestName = "SnowQuest",
                LevelRequire = 90,
                Mon = "Snow Bandit",
                MonQ = 7
            },
            {
                Level = 100,
                MobName = "Snowman [Lv. 100]",
                Number = 2,
                QuestName = "SnowQuest",
                LevelRequire = 100,
                Mon = "Snowman",
                MonQ = 8
            },
            {
                Level = 105,
                MobName = "Yeti [Lv. 105]",
                Number = 3,
                QuestName = "SnowQuest",
                LevelRequire = 105,
                Mon = "Yeti",
                MonQ = 1
            }
        }
    },

    MarineQuest2 = {
        Position = CFrame.new(-5039.58643, 27.3500385, 4324.68018, 0, 0, -1, 0, 1, 0, 1, 0, 0),
        Location = "Marine Base",
        Quests = {
            {
                Level = 120,
                MobName = "Chief Petty Officer [Lv. 120]",
                Number = 1,
                QuestName = "MarineQuest2",
                LevelRequire = 120,
                Mon = "Chief Petty Officer",
                MonQ = 8
            },
            {
                Level = 130,
                MobName = "Vice Admiral [Lv. 130]",
                Number = 2,
                QuestName = "MarineQuest2",
                LevelRequire = 130,
                Mon = "Vice Admiral",
                MonQ = 1
            }
        }
    },

    SkyQuest = {
        Position = CFrame.new(-4839.53027, 716.368591, -2619.44165, 0.866007268, 0, 0.500031412, 0, 1, 0, -0.500031412, 0, 0.866007268),
        Location = "Sky Highlands",
        Quests = {
            {
                Level = 150,
                MobName = "Sky Bandit [Lv. 150]",
                Number = 1,
                QuestName = "SkyQuest",
                LevelRequire = 150,
                Mon = "Sky Bandit",
                MonQ = 7
            },
            {
                Level = 175,
                MobName = "Dark Master [Lv. 175]",
                Number = 2,
                QuestName = "SkyQuest",
                LevelRequire = 175,
                Mon = "Dark Master",
                MonQ = 8
            }
        }
    },

    PrisonerQuest = {
        Position = CFrame.new(5310.60547, 0.350014925, 474.946594, 0.0175017118, 0, 0.999846935, 0, 1, 0, -0.999846935, 0, 0.0175017118),
        Location = "Prison Facility",
        Quests = {
            {
                Level = 190,
                MobName = "Prisoner [Lv. 190]",
                Number = 1,
                QuestName = "PrisonerQuest",
                LevelRequire = 190,
                Mon = "Prisoner",
                MonQ = 8
            },
            {
                Level = 210,
                MobName = "Dangerous Prisoner [Lv. 210]",
                Number = 2,
                QuestName = "PrisonerQuest",
                LevelRequire = 210,
                Mon = "Dangerous Prisoner",
                MonQ = 8
            }
        }
    },

    ImpelQuest = {
        Position = CFrame.new(5191.86133, 2.84020686, 686.438721, -0.731384635, 0, 0.681965172, 0, 1, 0, -0.681965172, 0, -0.731384635),
        Location = "Impel Tower",
        Quests = {
            {
                Level = 220,
                MobName = "Warden [Lv. 220]",
                Number = 1,
                QuestName = "ImpelQuest",
                LevelRequire = 220,
                Mon = "Warden",
                MonQ = 1
            },
            {
                Level = 230,
                MobName = "Chief Warden [Lv. 230]",
                Number = 2,
                QuestName = "ImpelQuest",
                LevelRequire = 230,
                Mon = "Chief Warden",
                MonQ = 1
            },
            {
                Level = 240,
                MobName = "Swan [Lv. 240]",
                Number = 3,
                QuestName = "ImpelQuest",
                LevelRequire = 240,
                Mon = "Swan",
                MonQ = 1
            }
        }
    },

    ColosseumQuest = {
        Position = CFrame.new(-1580.04663, 6.35000277, -2986.47534, -0.515037298, 0, -0.857167721, 0, 1, 0, 0.857167721, 0, -0.515037298),
        Location = "Colosseum Arena",
        Quests = {
            {
                Level = 250,
                MobName = "Toga Warrior [Lv. 250]",
                Number = 1,
                QuestName = "ColosseumQuest",
                LevelRequire = 250,
                Mon = "Toga Warrior",
                MonQ = 7
            },
            {
                Level = 275,
                MobName = "Gladiator [Lv. 275]",
                Number = 2,
                QuestName = "ColosseumQuest",
                LevelRequire = 275,
                Mon = "Gladiator",
                MonQ = 8
            }
        }
    },

    MagmaQuest = {
        Position = CFrame.new(-5313.37012, 10.9500084, 8515.29395, -0.499959469, 0, 0.866048813, 0, 1, 0, -0.866048813, 0, -0.499959469),
        Location = "Magma Fortress",
        Quests = {
            {
                Level = 300,
                MobName = "Military Soldier [Lv. 300]",
                Number = 1,
                QuestName = "MagmaQuest",
                LevelRequire = 300,
                Mon = "Military Soldier",
                MonQ = 7
            },
            {
                Level = 325,
                MobName = "Military Spy [Lv. 325]",
                Number = 2,
                QuestName = "MagmaQuest",
                LevelRequire = 325,
                Mon = "Military Spy",
                MonQ = 8
            },
            {
                Level = 350,
                MobName = "Magma Admiral [Lv. 350]",
                Number = 3,
                QuestName = "MagmaQuest",
                LevelRequire = 350,
                Mon = "Magma Admiral",
                MonQ = 1
            }
        }
    },

    FishmanQuest = {
        Position = CFrame.new(61121.1094, 17.953125, 1564.52637, -0.913477898, 0, -0.406888306, 0, 1, 0, 0.406888306, 0, -0.913477898),
        Location = "Fishman Island",
        Quests = {
            {
                Level = 375,
                MobName = "Fishman Warrior [Lv. 375]",
                Number = 1,
                QuestName = "FishmanQuest",
                LevelRequire = 375,
                Mon = "Fishman Warrior",
                MonQ = 8
            },
            {
                Level = 400,
                MobName = "Fishman Commando [Lv. 400]",
                Number = 2,
                QuestName = "FishmanQuest",
                LevelRequire = 400,
                Mon = "Fishman Commando",
                MonQ = 7
            },
            {
                Level = 425,
                MobName = "Fishman Lord [Lv. 425]",
                Number = 3,
                QuestName = "FishmanQuest",
                LevelRequire = 425,
                Mon = "Fishman Lord",
                MonQ = 1
            }
        }
    },

    SkyExp1Quest = {
        Position = CFrame.new(-7859.09814, 5544.19043, -381.476196, -0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, -0.422592998),
        Location = "Sky Expedition 1",
        Quests = {
            {
                Level = 450,
                MobName = "God's Guard [Lv. 450]",
                Number = 1,
                QuestName = "SkyExp1Quest",
                LevelRequire = 450,
                Mon = "God's Guard",
                MonQ = 7
            },
            {
                Level = 475,
                MobName = "Shanda [Lv. 475]",
                Number = 2,
                QuestName = "SkyExp1Quest",
                LevelRequire = 475,
                Mon = "Shanda",
                MonQ = 9
            },
            {
                Level = 500,
                MobName = "Wysper [Lv. 500]",
                Number = 3,
                QuestName = "SkyExp1Quest",
                LevelRequire = 500,
                Mon = "Wysper",
                MonQ = 1
            }
        }
    },

    SkyExp2Quest = {
        Position = CFrame.new(-7904.68457, 5634.66113, -1409.96729, 0, 0, -1, 0, 1, 0, 1, 0, 0),
        Location = "Sky Expedition 2",
        Quests = {
            {
                Level = 525,
                MobName = "Royal Squad [Lv. 525]",
                Number = 1,
                QuestName = "SkyExp2Quest",
                LevelRequire = 525,
                Mon = "Royal Squad",
                MonQ = 8
            },
            {
                Level = 550,
                MobName = "Royal Soldier [Lv. 550]",
                Number = 2,
                QuestName = "SkyExp2Quest",
                LevelRequire = 550,
                Mon = "Royal Soldier",
                MonQ = 8
            },
            {
                Level = 575,
                MobName = "Thunder God [Lv. 575]",
                Number = 3,
                QuestName = "SkyExp2Quest",
                LevelRequire = 575,
                Mon = "Thunder God",
                MonQ = 1
            }
        }
    },

    FountainQuest = {
        Position = CFrame.new(5259.81982, 37.3500175, 4050.0293, 0.087131381, 0, 0.996196866, 0, 1, 0, -0.996196866, 0, 0.087131381),
        Location = "Fountain Plaza",
        Quests = {
            {
                Level = 625,
                MobName = "Galley Pirate [Lv. 625]",
                Number = 1,
                QuestName = "FountainQuest",
                LevelRequire = 625,
                Mon = "Galley Pirate",
                MonQ = 8
            },
            {
                Level = 650,
                MobName = "Galley Captain [Lv. 650]",
                Number = 2,
                QuestName = "FountainQuest",
                LevelRequire = 650,
                Mon = "Galley Captain",
                MonQ = 9
            },
            {
                Level = 675,
                MobName = "Cyborg [Lv. 675]",
                Number = 3,
                QuestName = "FountainQuest",
                LevelRequire = 675,
                Mon = "Cyborg",
                MonQ = 1
            }
        }
    },






    --queststsdhsbfewfedsf------------------------------------------------------------------------------------------------------------------------------------------------------------

    Area1Quest = {
        Position = CFrame.new(-429.543518, 71.7699966, 1836.18188, -0.22495985, 0, -0.974368095, 0, 1, 0, 0.974368095, 0, -0.22495985),
        Location = "Area 1",
        Quests = {
            {
                Level = 700,
                MobName = "Raider [Lv. 700]",
                Number = 1,
                QuestName = "Area1Quest", 
                LevelRequire = 700,
                Mon = "Raider",
                MonQ = 8
            },
        }
    }
}

local PlayerLevel = player.Data.Level.Value

function GetCurrentQuest()
    local CurrQuest = nil
    local HighestLevel = -1
    local playerLevel = player.Data.Level.Value
    
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
    
    return CurrQuest
end

local function TweenToQuest(questData)
    if not questData or not questData.Position then return end
    
    local GettingQuest = true
    local distance = (humanoidRootPart.Position - questData.Position.Position).Magnitude
    local speed = distance > 350 and 300 or 11000
    local tweenInfo = TweenInfo.new(distance / speed, Enum.EasingStyle.Linear)
    
    for _, part in pairs(character:GetDescendants()) do
        if part:IsA("BasePart") or part:IsA("MeshPart") then
            part.CanCollide = false
        end
    end
    
    local tween = TweenService:Create(humanoidRootPart, tweenInfo, {CFrame = questData.Position})
    
    tween.Completed:Connect(function()
        for _, part in pairs(character:GetDescendants()) do
            if part:IsA("BasePart") or part:IsA("MeshPart") then
                part.CanCollide = true
            end
        end

        GettingQuest = false
        
        ReplicatedStorage.Remotes.CommF_:InvokeServer("StartQuest", questData.QuestName, questData.Number)

        if GetCurrentQuest() then
            bringMobs(humanoidRootPart, GetCurrentQuest().Mon)
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

player.Data.Level.Changed:Connect(function()
    PlayerLevel = player.Data.Level.Value
    StartQuestHunt()
end)

StartQuestHunt()
