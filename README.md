print("Solara Menu 1.0")
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
            }
        }
    },

    IceCreamIslandQuest = {
        Position = CFrame.new(-819.376709, 64.9259796, -10967.2832, -0.766061664, 0, 0.642767608, 0, 1, 0, -0.642767608, 0, -0.766061664),
        Location = "Ice Cream Island",
        Quests = {
            {
                Level = 2125,
                Number = 1,
                MobName = "Ice Cream Chef [Lv. 2125]",
                QuestName = "IceCreamIslandQuest",
                LevelRequire = 2125,
                Mon = "Ice Cream Chef",
                MonQ = 8
            },
            {
                Level = 2150,
                Number = 2,
                MobName = "Ice Cream Commander [Lv. 2150]",
                QuestName = "IceCreamIslandQuest", 
                LevelRequire = 2150,
                Mon = "Ice Cream Commander",
                MonQ = 8
            }
        }
    },

CakeQuest1 = {
    Position = CFrame.new(-2022.29858, 36.9275894, -12030.9766, -0.961273909, 0, -0.275594592, 0, 1, 0, 0.275594592, 0, -0.961273909),
    Location = "Cake Island",
    Quests = {
        {
            Level = 2200,
            Number = 1,
            MobName = "Cookie Crafter [Lv. 2200]",
            QuestName = "CakeQuest1",
            LevelRequire = 2200,
            Mon = "Cookie Crafter",
            MonQ = 8
        },
        {
            Level = 2225,
            Number = 2,
            MobName = "Cake Guard [Lv. 2225]",
            QuestName = "CakeQuest1",
            LevelRequire = 2225,
            Mon = "Cake Guard",
            MonQ = 8
        }
    }
},

CakeQuest2 = {
    Position = CFrame.new(-1928.31763, 37.7296638, -12840.626, 0.951068401, -0, -0.308980465, 0, 1, -0, 0.308980465, 0, 0.951068401),
    Location = "Cake Island",
    Quests = {
        {
            Level = 2250,
            Number = 1,
            MobName = "Baking Staff [Lv. 2250]",
            QuestName = "CakeQuest2",
            LevelRequire = 2250,
            Mon = "Baking Staff",
            MonQ = 8
        },
        {
            Level = 2275,
            Number = 2,
            MobName = "Head Baker [Lv. 2275]",
            QuestName = "CakeQuest2",
            LevelRequire = 2275,
            Mon = "Head Baker",
            MonQ = 8
        }
    }
},

ChocQuest1 = {
    Position = CFrame.new(231.75, 23.9003029, -12200.292, -1, 0, 0, 0, 1, 0, 0, 0, -1),
    Location = "Chocolate Island",
    Quests = {
        {
            Level = 2300,
            Number = 1,
            MobName = "Cocoa Warrior [Lv. 2300]",
            QuestName = "ChocQuest1",
            LevelRequire = 2300,
            Mon = "Cocoa Warrior",
            MonQ = 8
        },
        {
            Level = 2325,
            Number = 2,
            MobName = "Chocolate Bar Battler [Lv. 2325]",
            QuestName = "ChocQuest1",
            LevelRequire = 2325,
            Mon = "Chocolate Bar Battler",
            MonQ = 8
        }
    }
},

ChocQuest2 = {
    Position = CFrame.new(151.198242, 23.8907146, -12774.6172, 0.422592998, 0, 0.906319618, 0, 1, 0, -0.906319618, 0, 0.422592998),
    Location = "Chocolate Island",
    Quests = {
        {
            Level = 2350,
            Number = 1,
            MobName = "Sweet Thief [Lv. 2350]",
            QuestName = "ChocQuest2",
            LevelRequire = 2350,
            Mon = "Sweet Thief",
            MonQ = 8
        },
        {
            Level = 2375,
            Number = 2,
            MobName = "Candy Rebel [Lv. 2375]",
            QuestName = "ChocQuest2",
            LevelRequire = 2375,
    Mon = "Candy Rebel",
            MonQ = 8
        }
    }
},

CandyQuest1 = {
    Position = CFrame.new(-1149.328, 13.5759039, -14445.6143, -0.156446099, 0, -0.987686574, 0, 1, 0, 0.987686574, 0, -0.156446099),
    Location = "Candy Island",
    Quests = {
        {
            Level = 2400,
            Number = 1,
            MobName = "Candy Pirate [Lv. 2400]",
            QuestName = "CandyQuest1",
            LevelRequire = 2400,
            Mon = "Candy Pirate",
            MonQ = 8
        },
        {
            Level = 2425,
            Number = 2,
            MobName = "Snow Demon [Lv. 2425]",
            QuestName = "CandyQuest1",
            LevelRequire = 2425,
    Mon = "Snow Demon",
            MonQ = 8
        }
    }
},

TikiQuest1 = {
    Position = CFrame.new(-16548.8164, 55.6059914, -172.8125, 0.213092566, -0, -0.977032006, 0, 1, -0, 0.977032006, 0, 0.213092566),
    Location = "Tiki Island",
    Quests = {
        {
            Level = 2450,
            Number = 1,
            MobName = "Isle Outlaw [Lv. 2450]",
            QuestName = "TikiQuest1",
            LevelRequire = 2450,
            Mon = "Isle Outlaw",
            MonQ = 8
        },
        {
            Level = 2475,
            Number = 2,
            MobName = "Island Boy [Lv. 2475]",
            QuestName = "TikiQuest1",
            LevelRequire = 2475,
            Mon = "Island Boy",
            MonQ = 8
        }
    }
},

TikiQuest2 = {
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
