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
local HeadSize = 20
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




local Tab = Window:NewTab("credits")

local Section = Tab:NewSection("Loopy5418 code helped")

local Section = Tab:NewSection("catcat main dev")

local Section = Tab:NewSection("toxic sigma friend")
