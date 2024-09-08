local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()

local Window = Library.CreateLib("STOCK hub", "BloodTheme")

local Tab = Window:NewTab("auto farms")

local Section = Tab:NewSection("auto farms")

Section:NewButton("ore auto farm", "get ores", function()
    local cpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame

local stuff = workspace:getDescendants()
for i=1,#stuff do
if stuff[i].Name == "Block" and stuff[i].Parent.Name == "Ores" then
repeat
wait()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = stuff[i].CFrame
game.Players.LocalPlayer.Character.Axe.RemoteEvent:FireServer(stuff[i])
until stuff[i].Name ~= "Block" or not game.Players.LocalPlayer.Character:findFirstChild("Axe")
end
end

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cpos
end)

Section:NewButton("break all blocks", "break", function()
    local cpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame

local stuff = workspace:getDescendants()
for i=1,#stuff do
if stuff[i].Name == "Block" and stuff[i].Parent.Name == "Map" then
repeat
wait()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = stuff[i].CFrame
game.Players.LocalPlayer.Character.Axe.RemoteEvent:FireServer(stuff[i])
until stuff[i].Name ~= "Block" or not game.Players.LocalPlayer.Character:findFirstChild("Axe")
end
end

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cpos
end)

Section:NewButton("break all player built blocks", "break", function()
    local cpos = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame

local stuff = workspace:getDescendants()
for i=1,#stuff do
if stuff[i].Name == "Block" and stuff[i].Parent.Name == "Blocks" then
repeat
wait()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = stuff[i].CFrame
game.Players.LocalPlayer.Character.Axe.RemoteEvent:FireServer(stuff[i])
until stuff[i].Name ~= "Block" or not game.Players.LocalPlayer.Character:findFirstChild("Axe")
end
end

game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = cpos
end)

Section:NewButton("kill all borders of first", "not that good", function()
local condition = true 
while condition == true do
 function tpToRandom()
    local AllPlayers = {} --make the variable table that will contain all the player names
    for i, v in next, game.Players:GetPlayers() do --get players
        table.insert(AllPlayers, v.Name) --insert the players names into the "p" table
    end
    local choiceIndex = AllPlayers[math.random(1,#AllPlayers)] --pick the player itself, by generating a random number and picking the player with that position number
    if AllPlayers == game.Players.LocalPlayer.Character.Name then --check if the selected player's name is the same name as localplayer
        choiceIndex = AllPlayers[math.random(1,#AllPlayers)] --if true, then pick a new player from "p" table
    else --if not, then set the localplayers cframe to the selected players cframe
        game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Workspace[choiceIndex].HumanoidRootPart.CFrame --teleport the player to the selected player
    end
end tpToRandom()
 wait(1)
end
end)

local Tab = Window:NewTab("player")

local Section = Tab:NewSection("player")

Section:NewToggle("noclip", "gliched when off", function(state)
    if state then
        --I do not own this script
local noclip = true
char = game.Players.LocalPlayer.Character
while true do
if noclip == true then
for _,v in pairs(char:children()) do
pcall(function()
if v.className == "Part" then
v.CanCollide = false
end
end)
end
end
game:service("RunService").Stepped:wait()
end
    else
        --I do not own this script
local noclip = true
char = game.Players.LocalPlayer.Character
while true do
if noclip == true then
for _,v in pairs(char:children()) do
pcall(function()
if v.className == "Part" then
v.CanCollide = true
end
end)
end
end
game:service("RunService").Stepped:wait()
end
    end
end)

Section:NewSlider("jump power", "more then 60 you die", 60, 0, function(s) -- 500 (MaxValue) | 0 (MinValue)
game.Players.LocalPlayer.Character.Humanoid.JumpPower = s
end)

Section:NewButton("xray", "cant turn off", function()
local function makeAllPartsTransparent()
  
    for _, object in pairs(workspace:GetDescendants()) do
      
        if object:IsA("Part") then
            
            object.Transparency = 0.5
        end
    end
end

makeAllPartsTransparent()
end)

Section:NewButton("hit boxes", "cant turn off", function()
game:GetService('RunService').RenderStepped:Connect(function()
local HeadSize = 19
local IsDisabled = true 

if IsDisabled then
        local localPlayer = game:GetService('Players').LocalPlayer
        if not localPlayer then return end
        
        local localPlayerTeam = localPlayer.Team
        
        for _, player in ipairs(game:GetService('Players'):GetPlayers()) do
            if player ~= localPlayer and (not IsTeamCheckEnabled or player.Team ~= localPlayerTeam) then
                local humanoidRootPart = player.Character and player.Character:FindFirstChild("HumanoidRootPart")
                if humanoidRootPart then
                    humanoidRootPart.Size = Vector3.new(HeadSize, HeadSize, HeadSize)
                    humanoidRootPart.Transparency = 0.7
                    humanoidRootPart.BrickColor = BrickColor.new("Really blue")
                    humanoidRootPart.Material = Enum.Material.Neon
                    humanoidRootPart.CanCollide = false
                end
            end
        end
    end
end)
end)

Section:NewToggle("anti void", "makes a part you can walk on", function(state)
    if state then
       local part = Instance.new("Part")
part.BrickColor = BrickColor.new("Medium Stone Grey")

part.CFrame = CFrame.new(0, 75, 0)

part.Parent = game.workspace

part.Anchored = true

part.Size = Vector3.new(1000, 1, 1000)
    else
        local plr = game:GetService('Players').LocalPlayer.Character
local ScreenGui = Instance.new("ScreenGui")
local OpenFrame = Instance.new("Frame")
local Open = Instance.new("TextButton")
local Frame = Instance.new("Frame")
local BeautyA = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local BeautyA_2 = Instance.new("Frame")
local TextLabel_2 = Instance.new("TextLabel")
local AIM = Instance.new("TextButton")
local CTP = Instance.new("TextButton")
local Close = Instance.new("TextButton")
local MI = Instance.new("TextButton")
local MVIP = Instance.new("TextButton")
local Plate = Instance.new("TextButton")
local Shop = Instance.new("TextButton")
local VIP = Instance.new("TextButton")
local Walls = Instance.new("TextButton")

game.workspace.Part:remove()
    end
end)

Section:NewButton("esp", "sigma esp by loopy", function()
local hgh = Instance.new("Highlight")
for i, v in game.Players:GetPlayers() do
    for ii, vv in v.Character:GetChildren() do
        if vv:IsA("BasePart") then
            local clon = hgh:Clone()
            clon.Parent = vv
        end
    end
end
end)

local Tab = Window:NewTab("extra")

local Section = Tab:NewSection("extra")

Section:NewButton("ctrl + click to tp", "get ores", function()
-- CTRL+CLICK TP
local Plr = game:GetService("Players").LocalPlayer

local Mouse = Plr:GetMouse()

 

Mouse.Button1Down:connect(function()

if not game:GetService("UserInputService"):IsKeyDown(Enum.KeyCode.LeftControl) then return end

if not Mouse.Target then return end

Plr.Character:MoveTo(Mouse.Hit.p)

end)
end)

Section:NewButton("e to fly", "shart", function()
	repeat wait() 
	until game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:findFirstChild("Torso") and game.Players.LocalPlayer.Character:findFirstChild("Humanoid") 
local mouse = game.Players.LocalPlayer:GetMouse() 
repeat wait() until mouse
local plr = game.Players.LocalPlayer 
local torso = plr.Character.Torso 
local flying = false
local deb = true 
local ctrl = {f = 0, b = 0, l = 0, r = 0} 
local lastctrl = {f = 0, b = 0, l = 0, r = 0} 
local maxspeed = 50 
local speed = 0 

function Fly() 
local bg = Instance.new("BodyGyro", torso) 
bg.P = 9e4 
bg.maxTorque = Vector3.new(9e9, 9e9, 9e9) 
bg.cframe = torso.CFrame 
local bv = Instance.new("BodyVelocity", torso) 
bv.velocity = Vector3.new(0,0.1,0) 
bv.maxForce = Vector3.new(9e9, 9e9, 9e9) 
repeat wait() 
plr.Character.Humanoid.PlatformStand = true 
if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then 
speed = speed+.5+(speed/maxspeed) 
if speed > maxspeed then 
speed = maxspeed 
end 
elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then 
speed = speed-1 
if speed < 0 then 
speed = 0 
end 
end 
if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then 
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r} 
elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then 
bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
else 
bv.velocity = Vector3.new(0,0.1,0) 
end 
bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0) 
until not flying 
ctrl = {f = 0, b = 0, l = 0, r = 0} 
lastctrl = {f = 0, b = 0, l = 0, r = 0} 
speed = 0 
bg:Destroy() 
bv:Destroy() 
plr.Character.Humanoid.PlatformStand = false 
end 
mouse.KeyDown:connect(function(key) 
if key:lower() == "e" then 
if flying then flying = false 
else 
flying = true 
Fly() 
end 
elseif key:lower() == "w" then 
ctrl.f = 1 
elseif key:lower() == "s" then 
ctrl.b = -1 
elseif key:lower() == "a" then 
ctrl.l = -1 
elseif key:lower() == "d" then 
ctrl.r = 1 
end 
end) 
mouse.KeyUp:connect(function(key) 
if key:lower() == "w" then 
ctrl.f = 0 
elseif key:lower() == "s" then 
ctrl.b = 0 
elseif key:lower() == "a" then 
ctrl.l = 0 
elseif key:lower() == "d" then 
ctrl.r = 0 
end 
end)
Fly()
end)

Section:NewButton("remove all invis borders", "remove", function()
local plr = game:GetService('Players').LocalPlayer.Character
local ScreenGui = Instance.new("ScreenGui")
local OpenFrame = Instance.new("Frame")
local Open = Instance.new("TextButton")
local Frame = Instance.new("Frame")
local BeautyA = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local BeautyA_2 = Instance.new("Frame")
local TextLabel_2 = Instance.new("TextLabel")
local AIM = Instance.new("TextButton")
local CTP = Instance.new("TextButton")
local Close = Instance.new("TextButton")
local MI = Instance.new("TextButton")
local MVIP = Instance.new("TextButton")
local Plate = Instance.new("TextButton")
local Shop = Instance.new("TextButton")
local VIP = Instance.new("TextButton")
local Walls = Instance.new("TextButton")

game.workspace.Borders.InvisibleBorder:remove()
end)

Section:NewButton("remove all kill borders", "remove", function()
local plr = game:GetService('Players').LocalPlayer.Character
local ScreenGui = Instance.new("ScreenGui")
local OpenFrame = Instance.new("Frame")
local Open = Instance.new("TextButton")
local Frame = Instance.new("Frame")
local BeautyA = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local BeautyA_2 = Instance.new("Frame")
local TextLabel_2 = Instance.new("TextLabel")
local AIM = Instance.new("TextButton")
local CTP = Instance.new("TextButton")
local Close = Instance.new("TextButton")
local MI = Instance.new("TextButton")
local MVIP = Instance.new("TextButton")
local Plate = Instance.new("TextButton")
local Shop = Instance.new("TextButton")
local VIP = Instance.new("TextButton")
local Walls = Instance.new("TextButton")

game.workspace.Lobby.KillPlates:remove()
end)

Section:NewKeybind("toggle UI", "sigma sigma", Enum.KeyCode.F, function()
	Library:ToggleUI()
end)

-- Section:NewButton("remove all anti cheat", "remove", function()
--game.Players.LocalPlayer.PlayerGui.Extra.AntiSploitClient2:Destroy()
--	wait(1)
--	game.Players.LocalPlayer.PlayerGui.Extra.AntiSploitClient:Destroy()
-- end)

local Tab = Window:NewTab("tps")

local Section = Tab:NewSection("TPs")

Section:NewButton("middle", "tp to mid", function()
local plr = game:GetService('Players').LocalPlayer.Character
plr.HumanoidRootPart.CFrame = CFrame.new(-8, 164, 12)
end)

Section:NewButton("mega vip", "tp to mega vip", function()
local plr = game:GetService('Players').LocalPlayer.Character
plr.HumanoidRootPart.CFrame = CFrame.new(12, 264, 79)
end)

Section:NewButton("shop", "tp to shop", function()
local plr = game:GetService('Players').LocalPlayer.Character
plr.HumanoidRootPart.CFrame = CFrame.new(60, 260.5, 0)
end)

Section:NewButton("set cords", "set", function()
here = game.Players.LocalPlayer.Character.HumanoidRootPart.Position
end)

Section:NewButton("go to cords", "go", function()
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(here)
end)

local Tab = Window:NewTab("kill aura")

local Section = Tab:NewSection("kill aura")

Section:NewButton("kill aura", "stick ppl to your sword", function()


local active = true
local trueActive = true
local reachType = "Sphere"
local dmgEnabled = true
local visualizerEnabled = false

local visualizer = Instance.new("Part")
visualizer.BrickColor = BrickColor.Blue()
visualizer.Transparency = 0.6
visualizer.Anchored = true
visualizer.CanCollide = false
visualizer.Size = Vector3.new(0.5,0.5,0.5)
visualizer.BottomSurface = Enum.SurfaceType.Smooth
visualizer.TopSurface = Enum.SurfaceType.Smooth

local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local TextLabel = Instance.new("TextLabel")
local TextBox = Instance.new("TextBox")
local TextLabel_2 = Instance.new("TextLabel")
local TextLabel_3 = Instance.new("TextLabel")
local TextLabel_4 = Instance.new("TextLabel")
local TextButton = Instance.new("TextButton")
local Frame_2 = Instance.new("Frame")
local Frame_3 = Instance.new("Frame")
local Frame_4 = Instance.new("Frame")
local Frame_5 = Instance.new("Frame")
local TextButton_2 = Instance.new("TextButton")

--Properties:

ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
ScreenGui.DisplayOrder = 999999999
ScreenGui.ResetOnSpawn = false

Frame.Parent = sigma
Frame.AnchorPoint = Vector2.new(0, 0.5)
Frame.BackgroundColor3 = Color3.fromRGB(45, 45, 45)
Frame.BackgroundTransparency = 0.300
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 4
Frame.Position = UDim2.new(0, 0, 0.600000024, 0)
Frame.Size = UDim2.new(0.150000006, 0, 0.300000012, 0)


TextLabel.Parent = Frame
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.Size = UDim2.new(0.600000024, 0, 0.200000003, 0)
TextLabel.Font = Enum.Font.SourceSans
TextLabel.Text = "Reach:"
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextWrapped = true

TextBox.Parent = Frame
TextBox.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextBox.BackgroundTransparency = 1.000
TextBox.Position = UDim2.new(0.600000024, 0, 0, 0)
TextBox.Size = UDim2.new(0.400000006, 0, 0.200000003, 0)
TextBox.Font = Enum.Font.SourceSans
TextBox.Text = "15"
TextBox.TextColor3 = Color3.fromRGB(255, 76, 76)
TextBox.TextScaled = true
TextBox.TextSize = 14.000
TextBox.TextWrapped = true

TextLabel_2.Parent = Frame
TextLabel_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.BackgroundTransparency = 1.000
TextLabel_2.Position = UDim2.new(0, 0, 0.200000003, 0)
TextLabel_2.Size = UDim2.new(0.600000024, 0, 0.200000003, 0)
TextLabel_2.Font = Enum.Font.SourceSans
TextLabel_2.Text = "Shape:"
TextLabel_2.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_2.TextScaled = true
TextLabel_2.TextSize = 14.000
TextLabel_2.TextWrapped = true

TextLabel_3.Parent = Frame
TextLabel_3.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_3.BackgroundTransparency = 1.000
TextLabel_3.Position = UDim2.new(0, 0, 0.400000006, 0)
TextLabel_3.Size = UDim2.new(0.600000024, 0, 0.200000003, 0)
TextLabel_3.Font = Enum.Font.SourceSans
TextLabel_3.Text = "Damage:"
TextLabel_3.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_3.TextScaled = true
TextLabel_3.TextSize = 14.000
TextLabel_3.TextWrapped = true

TextLabel_4.Parent = Frame
TextLabel_4.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_4.BackgroundTransparency = 1.000
TextLabel_4.Position = UDim2.new(0, 0, 0.600000024, 0)
TextLabel_4.Size = UDim2.new(0.600000024, 0, 0.200000003, 0)
TextLabel_4.Font = Enum.Font.SourceSans
TextLabel_4.Text = "Visualizer:"
TextLabel_4.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel_4.TextScaled = true
TextLabel_4.TextSize = 14.000
TextLabel_4.TextWrapped = true

TextButton.Parent = Frame
TextButton.AnchorPoint = Vector2.new(0, 1)
TextButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextButton.BackgroundTransparency = 1.000
TextButton.Position = UDim2.new(0, 0, 1, 0)
TextButton.Size = UDim2.new(1, 0, 0.150000006, 0)
TextButton.Font = Enum.Font.SourceSansBold
TextButton.Text = "Kill Script"
TextButton.TextColor3 = Color3.fromRGB(222, 0, 0)
TextButton.TextScaled = true
TextButton.TextSize = 14.000
TextButton.TextWrapped = true

Frame_2.Parent = Frame
Frame_2.Active = false
Frame_2.AnchorPoint = Vector2.new(0, 0.5)
Frame_2.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
Frame_2.BorderSizePixel = 0
Frame_2.Position = UDim2.new(0.725000024, 0, 0.699999988, 0)
Frame_2.Size = UDim2.new(0, 25, 0, 25)
Frame_2.ZIndex = 5

Frame_3.Parent = Frame_2
Frame_3.AnchorPoint = Vector2.new(0.5, 0.5)
Frame_3.BackgroundColor3 = Color3.fromRGB(255, 76, 76)
Frame_3.BorderSizePixel = 0
Frame_3.LayoutOrder = 1
Frame_3.Position = UDim2.new(0.5, 0, 0.5, 0)

Frame_4.Parent = Frame
Frame_4.Active = false
Frame_4.AnchorPoint = Vector2.new(0, 0.5)
Frame_4.BackgroundColor3 = Color3.fromRGB(31, 31, 31)
Frame_4.BorderSizePixel = 0
Frame_4.Position = UDim2.new(0.725000024, 0, 0.5, 0)
Frame_4.Size = UDim2.new(0, 25, 0, 25)
Frame_4.ZIndex = 5

Frame_5.Parent = Frame_4
Frame_5.AnchorPoint = Vector2.new(0.5, 0.5)
Frame_5.BackgroundColor3 = Color3.fromRGB(255, 76, 76)
Frame_5.BorderSizePixel = 0
Frame_5.LayoutOrder = 1
Frame_5.Position = UDim2.new(0.5, 0, 0.5, 0)
Frame_5.Size = UDim2.new(1, 0, 1, 0)

TextButton_2.Parent = Frame
TextButton_2.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextButton_2.BackgroundTransparency = 1.000
TextButton_2.Position = UDim2.new(0.600000024, 0, 0.200000003, 0)
TextButton_2.Size = UDim2.new(0.400000006, 0, 0.200000003, 0)
TextButton_2.Font = Enum.Font.SourceSans
TextButton_2.Text = "Sphere"
TextButton_2.TextColor3 = Color3.fromRGB(255, 76, 76)
TextButton_2.TextScaled = true
TextButton_2.TextSize = 14.000
TextButton_2.TextWrapped = true

repeat wait() until game.Players.LocalPlayer
ScreenGui.Parent = game:GetService("CoreGui")



Frame_4.InputBegan:connect(function(inp)
	if inp.UserInputType == Enum.UserInputType.MouseButton1 then
		dmgEnabled = not dmgEnabled
		local goal = {Size = UDim2.new(0,0,0,0)}
		if dmgEnabled then
			goal = {Size = UDim2.new(1,0,1,0)}
		end
		game:GetService("TweenService"):Create(Frame_5,TweenInfo.new(0.12,Enum.EasingStyle.Quad),goal):Play()
	end
end)
Frame_2.InputBegan:connect(function(inp)
	if inp.UserInputType == Enum.UserInputType.MouseButton1 then
		visualizerEnabled = not visualizerEnabled
		local goal = {Size = UDim2.new(0,0,0,0)}
		if visualizerEnabled then
			goal = {Size = UDim2.new(1,0,1,0)}
		end
		game:GetService("TweenService"):Create(Frame_3,TweenInfo.new(0.12,Enum.EasingStyle.Linear),goal):Play()
	end
end)
TextButton_2.MouseButton1Click:connect(function()
	if reachType == "Sphere" then
		reachType = "Line"
	else
		reachType = "Sphere"
	end
	TextButton_2.Text = reachType
end)
TextButton.MouseButton1Click:connect(function()
	trueActive = false
	ScreenGui:Destroy()
end)
game:GetService("UserInputService").InputBegan:connect(function(inp,gpe)
	if gpe then return end
	if inp.KeyCode == Enum.KeyCode.H then
		ScreenGui.Enabled = not ScreenGui.Enabled
	end
end)

local plr = game.Players.LocalPlayer

local function onHit(hit,handle)
    local victim = hit.Parent:FindFirstChildOfClass("Humanoid")
	    if victim and victim.Parent.Name ~= game.Players.LocalPlayer.Name then
		if dmgEnabled then
	        for _,v in pairs(hit.Parent:GetChildren()) do
	            if v:IsA("Part") then
	                firetouchinterest(v,handle,0)
	                firetouchinterest(v,handle,1)
	            end
			end
		else
			firetouchinterest(hit,handle,0)
			firetouchinterest(hit,handle,1)
		end
    end
end

local function getWhiteList()
    local wl = {}
    for _,v in pairs(game.Players:GetPlayers()) do
        if v ~= plr then
            local char = v.Character
            if char then
                for _,q in pairs(char:GetChildren()) do
                    if q:IsA("Part") then
                        table.insert(wl,q)
                    end
                end
            end
        end
    end
    return wl
end

game:GetService("RunService").RenderStepped:connect(function()
    if not active or not trueActive then return end
	local s = plr.Character and plr.Character:FindFirstChildOfClass("Tool")
	if not s then visualizer.Parent = nil end
    if s then
        local handle = s:FindFirstChild("Handle") or s:FindFirstChildOfClass("Part")
		if handle then
			if visualizerEnabled then
				visualizer.Parent = workspace
			else
				visualizer.Parent = nil
			end
			local reach = tonumber(TextBox.Text)
			if reach then
				if reachType == "Sphere" then
					visualizer.Shape = Enum.PartType.Ball
					visualizer.Size = Vector3.new(reach,reach,reach)
					visualizer.CFrame = handle.CFrame
		            for _,v in pairs(game.Players:GetPlayers()) do
		                local hrp = v.Character and v.Character:FindFirstChild("HumanoidRootPart")
		                if hrp and handle then
		                    local mag = (hrp.Position-handle.Position).magnitude
		                    if mag <= reach then
		                        onHit(hrp,handle)
		                    end
		                end
					end
				elseif reachType == "Line" then
					local origin = (handle.CFrame*CFrame.new(0,0,-2)).p
		    		local ray = Ray.new(origin,handle.CFrame.lookVector*-reach)
					local p,pos = workspace:FindPartOnRayWithWhitelist(ray,getWhiteList())
					visualizer.Shape = Enum.PartType.Block
					visualizer.Size = Vector3.new(1,0.8,reach)
					visualizer.CFrame = handle.CFrame*CFrame.new(0,0,(reach/2)+2)
		    		if p then
		    		    onHit(p,handle)
		    		else
		    		    for _,v in pairs(handle:GetTouchingParts()) do
		    		        onHit(v,handle)
		    		    end
		    		end
				end
			end
        end
    end
end)
end)

local Tab = Window:NewTab("credits")

local Section = Tab:NewSection("Loopy5418 code helped")

local Section = Tab:NewSection("catcat main dev")

local Section = Tab:NewSection("toxic sigma friend")
