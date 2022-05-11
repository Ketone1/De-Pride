local ESP = loadstring(game:HttpGet("https://kiriot22.com/releases/ESP.lua"))()
ESP:Toggle(true);
ESP.Players = false;
ESP.Tracers = false;
ESP.Boxes = false;
ESP.Names = false;
ESP.Thickness = 2;
ESP.Color = Color3.fromRGB(255, 255, 255)

local OrionLib = loadstring(game:HttpGet(('https://raw.githubusercontent.com/shlexware/Orion/main/source')))()
 
local Valuess = 1

function updateStaffESP()
for _,v in pairs(game.Players:GetChildren()) do
    if v.Rank.Value >= 50 then
        ESP:Add(game.Workspace[v.Name].HumanoidRootPart, {
            Name = v.Name,
            IsEnabled = "TestESP",
            Color = Color3.fromRGB(135, 137, 255),
        })
    end
end    
end

function updateSpiderESP()
for _,v in pairs(game.Players:GetChildren()) do
    if v.Transformed.TransformationLevel.Value == 3 then
        ESP:Add(game.Workspace[v.Name].HumanoidRootPart, {
            Name = v.Name,
            IsEnabled = "TestESP2",
            Color = Color3.fromRGB(80,0,0),
        })
    end
end    
end

function player()
    local monke = {}
for _, Player in next, game.Players:GetChildren() do
if Player.Rank.Value >=50 then 
    table.insert(monke, Player.Name)
    else
       table.insert(monke, Player.Name) 
end
end
return monke
end

function staff()
    local staffs = {}
for _, Player in next, game.Players:GetChildren() do
if Player.Rank.Value <=50 then 
    table.insert(staffs, Player.Name)
    else
       table.insert(staffs, Player.Name) 
end
end
return staffs
end
 
local Window = OrionLib:MakeWindow({Name = "~De Pride Isle Sanatorium~"})
 
OrionLib:MakeNotification({
    Name = "Ketone",
    Content = "Thanks for using my script make sure to vouch!",
    Image = "rbxassetid://6833114846",
    Time = 5
})
 
local Tab = Window:MakeTab({
    Name = "LocalPlayer",
    Icon = "rbxassetid://80985",
    PremiumOnly = false
})
 
Tab:AddButton({
    Name = "Anonymous",
    Callback = function()
        
        for i,f in pairs(game.Workspace[game.Players.LocalPlayer.Name].Head.Rank:GetChildren()) do
    if f:IsA("TextLabel") then
        f:Destroy()
        
        for i,v in next, game:GetService('Players').LocalPlayer.Character:GetChildren() do
   if v:IsA('Accessory') then
       v:Destroy()
   end
end
local pchar = game:GetService("Players").LocalPlayer.Character
if pchar:FindFirstChild("Shirt") then
   pchar.Shirt:Remove()
end
 
wait()
local pchar = game:GetService("Players").LocalPlayer.Character
if pchar:FindFirstChild("Pants") then
   pchar.Pants:Remove()
end
 
wait()
local pchar = game:GetService("Players").LocalPlayer.Character
if pchar:FindFirstChild("Shirt") then
   pchar.Shirt:Remove()
end
 
wait()
local pchar = game:GetService("Players").LocalPlayer.Character
if pchar:FindFirstChild("ShirtGraphic") then
   pchar.Pants:Remove()
   end
    end
end
end
})
 
Tab:AddButton({
    Name = "No Blur",
    Callback = function()
for i,v in next, game.Lighting:GetDescendants() do
   if v:IsA('Folder') or v:IsA('ColorCorrectionEffect') or v:IsA('BlurEffect') then
       v.Parent = game.Players.LocalPlayer.PlayerGui
       wait()
       v:Destroy()
   end
 
end
    end    
})
 
Tab:AddButton({
    Name = "No Ragdoll",
    Callback = function()
                OrionLib:MakeNotification({
    Name = "Ragdoll",
    Content = "Note, this will NOT work against the holy stick due to it being a SS remote on the staffs side not ours.",
    Image = "rbxassetid://6833114846",
    Time = 10
})
for i,v in next, game.Workspace[game.Players.LocalPlayer.Name]:GetDescendants() do
   if v:IsA('Folder') and v.Name == "Ragdoll" then
       v.Parent = game.Players.LocalPlayer.PlayerGui
       wait()
       v:Destroy()
   end
end

        local mt = getrawmetatable(game)
setreadonly(mt,false)
 
local old = mt.__namecall
 
mt.__namecall = function(...)
    local method= getnamecallmethod() or get_namecall_method()
    local args = {...}
    if method == "FireServer" and args[2] == "Ragdoll" then
          return nil
    end
    return old(...)
end
end
})
 
Tab:AddButton({
    Name = "No Fall Damage",
    Callback = function()
        local mt = getrawmetatable(game)
setreadonly(mt,false)
 
local old = mt.__namecall
 
mt.__namecall = function(...)
    local method= getnamecallmethod() or get_namecall_method()
    local args = {...}
    if method == "FireServer" and args[2] == "FallDamage1" then
          return nil
    end
    return old(...)
end
    end    
})
 
Tab:AddButton({
    Name = "Reset",
    Callback = function()
        local player = game:getService("Players").LocalPlayer
local lastPosition = player.Character.PrimaryPart.Position
player.Character:BreakJoints()
Player.CharacterAdded:connect(function(char)
if (lastPosition ~= nil) then
char:moveTo(lastPosition)
lastPosition = nil
end
end)
    end    
})
 
local Tab = Window:MakeTab({
    Name = "Movement",
    Icon = "rbxassetid://4799",
    PremiumOnly = false
})
 
Tab:AddButton({
    Name = "Fly",
    Callback = function()
                OrionLib:MakeNotification({
    Name = "Fly",
    Content = "(E) to toggle flight \nAlso Works as Noclip",
    Image = "rbxassetid://6833114846",
    Time = 5
})
        loadstring(game:HttpGet("https://raw.githubusercontent.com/LegitH3x0R/Roblox-Scripts/main/AEBypassing/CFrameFly.lua"))()
    end    
})
 
Tab:AddButton({
    Name = "No Stamina",
    Callback = function()
        local mt = getrawmetatable(game)
setreadonly(mt,false)
 
local old = mt.__namecall
 
mt.__namecall = function(...)
    local method= getnamecallmethod() or get_namecall_method()
    local args = {...}
    if method == "FireServer" and args[2] == "Vagour1" then
          return nil
    end
    return old(...)
end
 
    end    
})
 
Tab:AddButton({
    Name = "Inf Jump",
    Callback = function()
        while wait() do
        local Player = game:GetService'Players'.LocalPlayer;
local UIS = game:GetService'UserInputService';
 
_G.JumpHeight = game.Players.LocalPlayer.Character.Humanoid.JumpPower;
 
function Action(Object, Function) if Object ~= nil then Function(Object); end end
 
UIS.InputBegan:connect(function(UserInput)
    if UserInput.UserInputType == Enum.UserInputType.Keyboard and UserInput.KeyCode == Enum.KeyCode.Space then
        Action(Player.Character.Humanoid, function(self)
            if self:GetState() == Enum.HumanoidStateType.Jumping or self:GetState() == Enum.HumanoidStateType.Freefall then
                Action(self.Parent.HumanoidRootPart, function(self)
                    self.Velocity = Vector3.new(0, _G.JumpHeight, 0);
                end)
            end
        end)
    end
end)
        end    
  end
})
 
Tab:AddButton({
    Name = "Sprint Multiplier {+  -}",
    Callback = function()
        
        local Players = game:service("Players")
local Player = Players.LocalPlayer
local userInput = game:service("UserInputService")
local runService = game:service("RunService")
repeat wait() until Player.Character
local Character = Player.Character
local pHum = Character:WaitForChild("Humanoid")
local humRoot = Character:WaitForChild("HumanoidRootPart")
local Multiplier = 0.1 --adjust this for more or less speed

userInput.InputBegan:connect(function(Key)
if Key.KeyCode == Enum.KeyCode.LeftBracket then
Multiplier = Multiplier + 0.1
wait(0.2)
while userInput:IsKeyDown(Enum.KeyCode.LeftBracket) do
wait()
Multiplier = Multiplier + 0.1
end
end

if Key.KeyCode == Enum.KeyCode.RightBracket then
Multiplier = Multiplier - 0.1
wait(0.2)
while userInput:IsKeyDown(Enum.KeyCode.RightBracket) do
wait()
Multiplier = Multiplier - 0.1
end
end
end)

runService.Stepped:connect(function()
if userInput:IsKeyDown(Enum.KeyCode.LeftShift) then
humRoot.CFrame = humRoot.CFrame + pHum.MoveDirection * Multiplier
end
end)

        end   
})

Tab:AddSlider({
    Name = "Walkspeed",
    Min = 16,
    Max = 200,
    Default = 16,
    Increment = 5,
    ValueName = "bananas",
    Callback = function(Value)
        if not getgenv().MTAPIMutex then
           if getgenv().MTAPIMutex ~= nil then
               return
           end
           local function a()
               if is_protosmasher_caller ~= nil then
                   return 0
               end
               if elysianexecute ~= nil then
                   return 1
               end
               if fullaccess ~= nil then
                   return 2
               end
               if Synapse ~= nil then
                   return 3
               end
               return 4
           end
           local function b()
               local c = a()
               if c == 0 then
                   return is_protosmasher_caller
               end
               if c == 1 or c == 3 then
                   return checkcaller
               end
               if c == 2 then
                   return IsLevel7
               end
               return nil
           end
           if a() == 2 then
               error("mt-api: Exploit not supported")
           end
           local d = {}
           local e = {}
           local f = {}
           local g = {}
           local h = {}
           local i = {}
           local j = {}
           local k = {}
           local function l()
               local m = a()
               local n = b()
               local o = getrawmetatable(game)
               if m == 0 then
                   make_writeable(o)
               elseif m == 2 then
                   fullaccess(o)
               else
                   setreadonly(o, false)
               end
               local p = o.__index
               local q = o.__newindex
               local r = o.__namecall
               o.__index =
                   newcclosure(
                   function(s, t)
                       if n() then
                           return p(s, t)
                       end
                       if d[s] and d[s][t] then
                           local u = d[s][t]
                           if u["IsCallback"] == true then
                               return u["Value"](s)
                           else
                               return u["Value"]
                           end
                       end
                       if g[t] then
                           local v = g[t]
                           if v["IsCallback"] == true then
                               return v["Value"](s)
                           else
                               return v["Value"]
                           end
                       end
                       if j[s] and j[s][t] then
                           return k[s][t]
                       end
                       return p(s, t)
                   end
               )
               o.__newindex =
                   newcclosure(
                   function(w, x, y)
                       if n() then
                           return q(w, x, y)
                       end
                       if e[w] and e[w][x] then
                           local z = e[w][x]
                           if z["Callback"] == nil then
                               return
                           else
                               z["Callback"](w, y)
                               return
                           end
                       end
                       if h[x] then
                           local A = h[x]
                           if A["Callback"] == nil then
                               return
                           else
                               A["Callback"](w, y)
                               return
                           end
                       end
                       if j[w] and j[w][x] then
                           local B = j[w][x]
                           if type(y) ~= B["Type"] then
                               error(
                                   "bad argument #3 to '" ..
                                       x .. "' (" .. B["Type"] .. " expected, got " .. type(x) .. ")"
                               )
                           end
                           k[w][x] = y
                           return
                       end
                       return q(w, x, y)
                   end
               )
               local C = isluau and isluau() or false
               o.__namecall =
                   newcclosure(
                   function(D, ...)
                       local E = {...}
                       local F = C and getnamecallmethod() or table.remove(E)
                       if n() then
                           if F == "AddGetHook" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local G = E[1]
                               local H = E[2]
                               local I = E[3]
                               if type(G) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if not d[D] then
                                   d[D] = {}
                               end
                               if I == true and type(H) ~= "function" then
                                   error("mt-api: Invalid callback function")
                               end
                               d[D][G] = {Value = H, IsCallback = I}
                               local J = function()
                                   d[D][G] = nil
                               end
                               return {remove = J, Remove = J}
                           end
                           if F == "AddGlobalGetHook" then
                               local K = E[1]
                               local L = E[2]
                               local M = E[3]
                               if type(K) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if M == true and type(L) ~= "function" then
                                   error("mt-api: Invalid callback function")
                               end
                               g[K] = {Value = L, IsCallback = M}
                               local N = function()
                                   g[K] = nil
                               end
                               return {remove = N, Remove = N}
                           end
                           if F == "AddSetHook" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local O = E[1]
                               local P = E[2]
                               if type(O) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if not e[D] then
                                   e[D] = {}
                               end
                               if type(P) == "function" then
                                   e[D][O] = {Callback = P}
                               else
                                   e[D][O] = {Callback = nil}
                               end
                               local Q = function()
                                   e[D][O] = nil
                               end
                               return {remove = Q, Remove = Q}
                           end
                           if F == "AddGlobalSetHook" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local R = E[1]
                               local S = E[2]
                               if type(R) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if type(S) == "function" then
                                   h[R] = {Callback = S}
                               else
                                   h[R] = {Callback = nil}
                               end
                               local T = function()
                                   h[R] = nil
                               end
                               return {remove = T, Remove = T}
                           end
                           if F == "AddCallHook" then
                               if #E < 2 then
                                   error("mt-api: Invalid argument count")
                               end
                               local U = E[1]
                               local V = E[2]
                               if type(U) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if type(V) ~= "function" then
                                   error("mt-api: Invalid argument #2 (not function)")
                               end
                               if not f[D] then
                                   f[D] = {}
                               end
                               f[D][U] = {Callback = V}
                               local W = function()
                                   f[D][U] = nil
                               end
                               return {remove = W, Remove = W}
                           end
                           if F == "AddGlobalCallHook" then
                               if #E < 2 then
                                   error("mt-api: Invalid argument count")
                               end
                               local X = E[1]
                               local Y = E[2]
                               if type(X) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if type(Y) ~= "function" then
                                   error("mt-api: Invalid argument #2 (not function)")
                               end
                               i[X] = {Callback = Y}
                               local Z = function()
                                   i[X] = nil
                               end
                               return {remove = Z, Remove = Z}
                           end
                           if F == "AddPropertyEmulator" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local _ = E[1]
                               if type(_) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               local a0 = p(D, _)
                               local a1 = type(a0)
                               if not j[D] then
                                   j[D] = {}
                               end
                               if not k[D] then
                                   k[D] = {}
                               end
                               j[D][_] = {Type = a1}
                               k[D][_] = p(D, _)
                               local a2 = function()
                                   j[D][_] = nil
                                   k[D][_] = nil
                               end
                               return {remove = a2, Remove = a2}
                           end
                           return r(D, ...)
                       end
                       if f[D] and f[D][F] then
                           local a3 = f[D][F]
                           return a3["Callback"](p(D, F), unpack(E))
                       end
                       if i[F] then
                           local a4 = i[F]
                           return a4["Callback"](D, p(D, F), unpack(E))
                       end
                       return r(D, ...)
                   end
               )
               if m == 0 then
                   make_readonly(o)
               elseif m == 2 then
               else
                   setreadonly(o, true)
               end
           end
           l()
           getgenv().MTAPIMutex = true -- Network Spoofer for it, ez
           game.Players.LocalPlayer.Character.Humanoid:AddPropertyEmulator("WalkSpeed")
       end
       game:GetService("Players").LocalPlayer.Character.Humanoid.WalkSpeed = (Value)
    end    
})
 
Tab:AddSlider({
    Name = "JumpPower",
    Min = 35,
    Max = 95,
    Default = 35,
    Increment = 5,
    ValueName = "spinach",
    Callback = function(Value)
   
        if not getgenv().MTAPIMutex then
           if getgenv().MTAPIMutex ~= nil then
               return
           end
           local function a()
               if is_protosmasher_caller ~= nil then
                   return 0
               end
               if elysianexecute ~= nil then
                   return 1
               end
               if fullaccess ~= nil then
                   return 2
               end
               if Synapse ~= nil then
                   return 3
               end
               return 4
           end
           local function b()
               local c = a()
               if c == 0 then
                   return is_protosmasher_caller
               end
               if c == 1 or c == 3 then
                   return checkcaller
               end
               if c == 2 then
                   return IsLevel7
               end
               return nil
           end
           if a() == 2 then
               error("mt-api: Exploit not supported")
           end
           local d = {}
           local e = {}
           local f = {}
           local g = {}
           local h = {}
           local i = {}
           local j = {}
           local k = {}
           local function l()
               local m = a()
               local n = b()
               local o = getrawmetatable(game)
               if m == 0 then
                   make_writeable(o)
               elseif m == 2 then
                   fullaccess(o)
               else
                   setreadonly(o, false)
               end
               local p = o.__index
               local q = o.__newindex
               local r = o.__namecall
               o.__index =
                   newcclosure(
                   function(s, t)
                       if n() then
                           return p(s, t)
                       end
                       if d[s] and d[s][t] then
                           local u = d[s][t]
                           if u["IsCallback"] == true then
                               return u["Value"](s)
                           else
                               return u["Value"]
                           end
                       end
                       if g[t] then
                           local v = g[t]
                           if v["IsCallback"] == true then
                               return v["Value"](s)
                           else
                               return v["Value"]
                           end
                       end
                       if j[s] and j[s][t] then
                           return k[s][t]
                       end
                       return p(s, t)
                   end
               )
               o.__newindex =
                   newcclosure(
                   function(w, x, y)
                       if n() then
                           return q(w, x, y)
                       end
                       if e[w] and e[w][x] then
                           local z = e[w][x]
                           if z["Callback"] == nil then
                               return
                           else
                               z["Callback"](w, y)
                               return
                           end
                       end
                       if h[x] then
                           local A = h[x]
                           if A["Callback"] == nil then
                               return
                           else
                               A["Callback"](w, y)
                               return
                           end
                       end
                       if j[w] and j[w][x] then
                           local B = j[w][x]
                           if type(y) ~= B["Type"] then
                               error(
                                   "bad argument #3 to '" ..
                                       x .. "' (" .. B["Type"] .. " expected, got " .. type(x) .. ")"
                               )
                           end
                           k[w][x] = y
                           return
                       end
                       return q(w, x, y)
                   end
               )
               local C = isluau and isluau() or false
               o.__namecall =
                   newcclosure(
                   function(D, ...)
                       local E = {...}
                       local F = C and getnamecallmethod() or table.remove(E)
                       if n() then
                           if F == "AddGetHook" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local G = E[1]
                               local H = E[2]
                               local I = E[3]
                               if type(G) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if not d[D] then
                                   d[D] = {}
                               end
                               if I == true and type(H) ~= "function" then
                                   error("mt-api: Invalid callback function")
                               end
                               d[D][G] = {Value = H, IsCallback = I}
                               local J = function()
                                   d[D][G] = nil
                               end
                               return {remove = J, Remove = J}
                           end
                           if F == "AddGlobalGetHook" then
                               local K = E[1]
                               local L = E[2]
                               local M = E[3]
                               if type(K) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if M == true and type(L) ~= "function" then
                                   error("mt-api: Invalid callback function")
                               end
                               g[K] = {Value = L, IsCallback = M}
                               local N = function()
                                   g[K] = nil
                               end
                               return {remove = N, Remove = N}
                           end
                           if F == "AddSetHook" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local O = E[1]
                               local P = E[2]
                               if type(O) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if not e[D] then
                                   e[D] = {}
                               end
                               if type(P) == "function" then
                                   e[D][O] = {Callback = P}
                               else
                                   e[D][O] = {Callback = nil}
                               end
                               local Q = function()
                                   e[D][O] = nil
                               end
                               return {remove = Q, Remove = Q}
                           end
                           if F == "AddGlobalSetHook" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local R = E[1]
                               local S = E[2]
                               if type(R) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if type(S) == "function" then
                                   h[R] = {Callback = S}
                               else
                                   h[R] = {Callback = nil}
                               end
                               local T = function()
                                   h[R] = nil
                               end
                               return {remove = T, Remove = T}
                           end
                           if F == "AddCallHook" then
                               if #E < 2 then
                                   error("mt-api: Invalid argument count")
                               end
                               local U = E[1]
                               local V = E[2]
                               if type(U) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if type(V) ~= "function" then
                                   error("mt-api: Invalid argument #2 (not function)")
                               end
                               if not f[D] then
                                   f[D] = {}
                               end
                               f[D][U] = {Callback = V}
                               local W = function()
                                   f[D][U] = nil
                               end
                               return {remove = W, Remove = W}
                           end
                           if F == "AddGlobalCallHook" then
                               if #E < 2 then
                                   error("mt-api: Invalid argument count")
                               end
                               local X = E[1]
                               local Y = E[2]
                               if type(X) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               if type(Y) ~= "function" then
                                   error("mt-api: Invalid argument #2 (not function)")
                               end
                               i[X] = {Callback = Y}
                               local Z = function()
                                   i[X] = nil
                               end
                               return {remove = Z, Remove = Z}
                           end
                           if F == "AddPropertyEmulator" then
                               if #E < 1 then
                                   error("mt-api: Invalid argument count")
                               end
                               local _ = E[1]
                               if type(_) ~= "string" then
                                   error("mt-api: Invalid hook type")
                               end
                               local a0 = p(D, _)
                               local a1 = type(a0)
                               if not j[D] then
                                   j[D] = {}
                               end
                               if not k[D] then
                                   k[D] = {}
                               end
                               j[D][_] = {Type = a1}
                               k[D][_] = p(D, _)
                               local a2 = function()
                                   j[D][_] = nil
                                   k[D][_] = nil
                               end
                               return {remove = a2, Remove = a2}
                           end
                           return r(D, ...)
                       end
                       if f[D] and f[D][F] then
                           local a3 = f[D][F]
                           return a3["Callback"](p(D, F), unpack(E))
                       end
                       if i[F] then
                           local a4 = i[F]
                           return a4["Callback"](D, p(D, F), unpack(E))
                       end
                       return r(D, ...)
                   end
               )
               if m == 0 then
                   make_readonly(o)
               elseif m == 2 then
               else
                   setreadonly(o, true)
               end
           end
           l()
           getgenv().MTAPIMutex = true -- Network Spoofer for it, ez
           game.Players.LocalPlayer.Character.Humanoid:AddPropertyEmulator("JumpPower")
       end
       game:GetService("Players").LocalPlayer.Character.Humanoid.JumpPower = (Value)
    end    
})
 
local Tab = Window:MakeTab({
    Name = "Players",
    Icon = "rbxassetid://7268",
    PremiumOnly = false
})
 
local dropdown = Tab:AddDropdown({
    Name = "Players",
    Default = "1",
    Options = {"1", "2"},
    Callback = function(Values)
        Valuess = Values
    end    
})
dropdown:Refresh(player{}, true)
 
Tab:AddButton({
    Name = "Go to Player",
    Callback = function()
          game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = game.Players[Valuess].Character.HumanoidRootPart.CFrame
      end    
})

Tab:AddButton({
    Name = "Give Cockroach",
    Callback = function()
        
    OrionLib:MakeNotification({
    Name = "Cockroach",
    Content = "If it doesnt work then the player already has a Cockroach!",
    Image = "rbxassetid://6833114846",
    Time = 10
})
        
          for i,v in pairs(game.Workspace.Givers:GetDescendants()) do
if v:IsA("ClickDetector") then
fireclickdetector(v)
end
end

for i=1, 10 do

game.Players[Valuess].Character.HumanoidRootPart.CFrame = game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame

local args = {
    [1] = "GiveTool",
    [2] = game:GetService("Players")[Valuess],
    [3] = game:GetService("Players").LocalPlayer.Character.Cockroach
}

game:GetService("ReplicatedStorage").Events.Game:FireServer(unpack(args))
     
     end
end
})
 
local Tab = Window:MakeTab({
    Name = "Misc",
    Icon = "rbxassetid://44898",
    PremiumOnly = false
})
 
Tab:AddButton({
    Name = "No Barriers",
    Callback = function()
for i,v in next, game:GetService("Workspace").RankBarriers:GetDescendants() do
   if v:IsA('Part') then
       v.CFrame = game:GetService("Workspace").Shops["Holy Shop"]["Wood Crate"].Center.CFrame
   end
end
      end    
})
 
Tab:AddButton({
    Name = "Full Bright",
    Callback = function()
loadstring(game:HttpGet("https://pastebin.com/raw/06iG6YkU", true))()
      end    
})
 
Tab:AddButton({
    Name = "No Hunger",
    Callback = function()
local Anticheat = game:GetService("Players").LocalPlayer.Voracity
local GameMt = getrawmetatable(game)
local OldIndex = GameMt.__index
 
setreadonly(GameMt, false)
 
GameMt.__index = newcclosure(function(Self, Key)
   if not checkcaller() and Self == Anticheat and Key == "Value" then
       return math.huge
   end
 
   return OldIndex(Self, Key)
end)
 
setreadonly(GameMt, true)
         local mt = getrawmetatable(game)
setreadonly(mt,false)
 
local old = mt.__namecall
 
mt.__namecall = function(...)
    local method= getnamecallmethod() or get_namecall_method()
    local args = {...}
    if method == "FireServer" and args[2] == "Voracity1" then
          return nil
    end
    return old(...)
end

        local mt = getrawmetatable(game)
setreadonly(mt,false)
 
local old = mt.__namecall
 
mt.__namecall = function(...)
    local method= getnamecallmethod() or get_namecall_method()
    local args = {...}
    if method == "FireServer" and args[2] == "Voracity" then
          return nil
    end
    return old(...)
end

end  
})
 
Tab:AddButton({
    Name = "ChatLogs",
    Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/Y8yW6Nas", true))()
    end    
})
 
Tab:AddParagraph("More Soon...","Wanna Help with the Process? Vouch or doante a staff account \nOtherwise, Have Fun!")
 
local Tab = Window:MakeTab({
	Name = "ESP",
	Icon = "rbxassetid://44898",
	PremiumOnly = false
})


Tab:AddToggle({
	Name = "ESP Toggle",
	Default = false,
	Callback = function(Value)
		ESP:Toggle(Value)
	end    
})

Tab:AddToggle({
	Name = "Staff ESP (Light Purple)",
	Default = false,
	Callback = function(Value)
		ESP.TestESP = Value
		wait()
		updateStaffESP()
	end    
})

Tab:AddToggle({
	Name = "Spider ESP (Dark Red)",
	Default = false,
	Callback = function(Value)
		ESP.TestESP2 = Value
		wait()
		updateSpiderESP()
	end    
})

Tab:AddToggle({
	Name = "Players ESP (White)",
	Default = false,
	Callback = function(Value)
		ESP.Players = Value
	end    
})

Tab:AddToggle({
	Name = "Boxes",
	Default = false,
	Callback = function(Value)
		ESP.Boxes = Value
	end    
})

Tab:AddToggle({
	Name = "Tracers",
	Default = false,
	Callback = function(Value)
		ESP.Tracers = Value
	end    
})

Tab:AddToggle({
	Name = "Nametags",
	Default = false,
	Callback = function(Value)
		ESP.Names = Value
	end    
}) 

local Tab = Window:MakeTab({
    Name = "Credits",
    Icon = "rbxassetid://44898",
    PremiumOnly = false
})
 
Tab:AddLabel("Developer: Ketone")
Tab:AddLabel("Developer: NotOreoz")


OrionLib:Init()
