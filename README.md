local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/NiceBBMBThai12/NBTScript/main/UI-Library-Robloxx"))()
local window = library:Win()
local tap1 = window:addtap("Main")
local page1 = tap1:addpage()
local page2 = tap1:addpage()
local page3 = tap1:addpage()
local page4 = tap1:addpage()
function CheckQuest()
    local Level = game:GetService("Players").LocalPlayer.PlayerStats.Level.Value
    if Level == 1 or Level <= 14 then
        Mon = "Bandit [Lv:5]"
        Quest = "Bandit"
    elseif Level == 15 or Level <= 29 then
        Mon = "Pirates [Lv:15]"
        Quest = "Pirates"
    elseif Level == 30 or Level <= 59 then
        Mon = "BagyPirates [Lv:30]"
        Quest = "BagyPirates"
    elseif Level == 60 or Level <= 149 then
        Mon = "Clown Pirate [Lv:60]"
        Quest = "Clown Pirate"
    elseif Level == 150 or Level <= 199 then
        Mon = "Revolutionary Troop [Lv:150]"
        Quest = "Revolutionary Troop"
    elseif Level == 200 or Level <= 399 then
        Mon = "Marines [Lv:200]"
        Quest = "Marines"
    elseif Level == 400 or Level <= 599 then
        Mon = "Skilled Chef [Lv:400]"
        Quest = "Skilled Chef"
    elseif Level == 600 or Level <= 699 then
        Mon = "Fishman [Lv:600]"--"Bandit [Lv:5]"
        Quest = "Fishman"--"Bandit"
    elseif Level == 700 or Level <= 849 then
        Mon = "WinterBandit [Lv:700]"
        Quest = "WinterBandit"
    elseif Level == 850 or Level <= 1099 then
        Mon = "Hollow Knight [Lv:850]"
        Quest = "Hollow Knight"
    elseif Level >= 1100 then
        Mon = "Zombie Pirate [Lv:1150]"
        Quest = "Zombie Pirate"
    end
end
_G.SelectWeapon = ""
  function EquipWeapon(ToolSe)
     if game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe) then
        local tool = game.Players.LocalPlayer.Backpack:FindFirstChild(ToolSe)
        wait(.4)
        game.Players.LocalPlayer.Character.Humanoid:EquipTool(tool)
     end
  end
Wapon = {}
	for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
		if v:IsA("Tool") then
			table.insert(Wapon ,v.Name)
		end
	end
	for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
		if v:IsA("Tool") then
			table.insert(Wapon, v.Name)
		end
	end
local VirtualUser = game:GetService('VirtualUser')
page1:Toggle("Auto Farm Level",false, function(value)
    _G.AutoFarm = value
end)
local SelectWeapona = page1:DropDown("Select Wapon","Weapon",Wapon,function(a)
    _G.SelectWeapon = a
end)
page1:Button("Refresh Weapon",function(dsa)
   SelectWeapona:Clear()
		for i,v in pairs(game.Players.LocalPlayer.Backpack:GetChildren()) do  
			if v:IsA("Tool") then
				SelectWeapona:Add(v.Name)
			end
		end
		for i,v in pairs(game.Players.LocalPlayer.Character:GetChildren()) do  
			if v:IsA("Tool") then
				SelectWeapona:Add(v.Name)
			end
		end
end)
page2:Ti("Stats")
page2:Toggle("Melee", false, function(value)
    _G.Melee = value
end)

page2:Toggle("Sword", false, function(value)
    _G.Sword = value
end)

page2:Toggle("Defense", false, function(value)
    _G.Defense = value
end)

page2:Toggle("Devil Fruit", false, function(value)
    _G.Fruit = value
end)
_G.POINT = 1
page2:Slder("Point", 1,100,1, function(value)
    _G.POINT = value
end)
spawn(function()
    while wait() do
        if _G.Melee then
            local args = {
                [1] = _G.POINT,
                [2] = "1"
            }

            game:GetService("ReplicatedStorage").okStats:FireServer(unpack(args))
			if _G.Sword then
				local args = {
					[1] = _G.POINT,
					[2] = "2"
				}
				
				game:GetService("ReplicatedStorage").okStats:FireServer(unpack(args))
			end
			if _G.Defense then
				local args = {
					[1] = _G.POINT,
					[2] = "3"
				}
				
				game:GetService("ReplicatedStorage").okStats:FireServer(unpack(args))
			end
			if _G.Fruit then
				local args = {
					[1] = _G.POINT,
					[2] = "4"
				}
				
				game:GetService("ReplicatedStorage").okStats:FireServer(unpack(args))
			end
        end
    end
end)
page3:Ti("Teleport")
page3:Button("Starter Island", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(368.03778076172, 40.559078216553, -1882.8992919922)
end)

page3:Button("Snow Island", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(2763.31543, 17.3299236, 4538.91895, 0.820167661, -0.0140461493, 0.571950793, 0.0353551134, 0.999032259, -0.0261640809, -0.571029782, 0.0416803174, 0.819870591)
end)

page3:Button("Rock Island", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(-2255.47412, 56.6599236, -2542.8916, -0.152854323, 0, -0.988248765, 0, 1, 0, 0.988248765, 0, -0.152854323)
end)

page3:Button("Justical Island", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(-2576.5056152344, 14.312427520752, 989.39874267578)
end)
page3:Button("Bera", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(820.623596, 1.55829597, -5246.31299, 0, 0, -1, 0, 1, 0, 1, 0, 0)
end)
page3:Button("Fishman Island", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(4702.13867, 1.65887189, 1916.98767, -1, 0, 0, 0, 1, 0, 0, 0, -1)
end)
page3:Button("Factory",function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(-127.271118, 40.0972633, -9444.07812, -1, 0, 0, 0, 1, 0, 0, 0, -1)
end)

page3:Button("Carnival Island", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(1656.45752, 27.4287205, 260.840271, 0, 0, -1, 0, 1, 0, 1, 0, 0)
end)

page3:Button("????", function()
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame =  CFrame.new(3897.60718, 36.5815392, -3052.66064, -0.716245294, 0, -0.697848558, 0, 1, 0, 0.697848558, 0, -0.716245294)
end)
spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        if _G.AutoFarm then
            setfflag("HumanoidParallelRemoveNoPhysics", "False")
            setfflag("HumanoidParallelRemoveNoPhysicsNoSimulate2", "False")
            game:GetService("Players").LocalPlayer.Character.Humanoid:ChangeState(11)
        end
    end)
end)
spawn(function()
    while wait() do
        if _G.AutoFarm then
            pcall(function()
                CheckQuest()
                if game:GetService("Players").LocalPlayer.PlayerGui.QuestGui.Enabled == false then
                    local args = {
                        [1] = Quest
                    }
                    
                    game:GetService("ReplicatedStorage").FuncQuest:InvokeServer(unpack(args))
                elseif game:GetService("Players").LocalPlayer.PlayerGui.QuestGui.Enabled == true then
                    for i,v in pairs(game:GetService("Workspace").Lives:GetChildren()) do
                        for l,x in pairs(game:GetService("Workspace").Lives:GetChildren()) do
                        if x.Name == Mon and x:FindFirstChild("HumanoidRootPart") and x:FindFirstChild("Humanoid") and x.Humanoid.Health > 0 then
                        if v.Name == Mon and v:FindFirstChild("HumanoidRootPart") and v:FindFirstChild("Humanoid") and v.Humanoid.Health > 0 then
                            repeat wait()
                                EquipWeapon(_G.SelectWeapon)
                                VirtualUser:CaptureController()
                                VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
                                game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.HumanoidRootPart.CFrame * CFrame.Angles(math.rad(-90), 0, 0) - Vector3.new(0,-7,0)
                            until _G.AutoFarm == false or v.Humanoid.Health <= 0 or not v.Parent
                        else
							-- Nothing
                        end
                        end
                        end
                    end
                else 
                    local args = {
                        [1] = Quest
                    }
                    
                    game:GetService("ReplicatedStorage").FuncQuest:InvokeServer(unpack(args))
                end
            end)
        end
    end
end)
