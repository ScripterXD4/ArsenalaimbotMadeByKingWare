-- Aimbot Script
 
-- Variables
local Players = game:GetService("Players")
local Mouse = Players.LocalPlayer:GetMouse()
 
-- Functions
local function GetNearestPlayer()
	local NearestPlayer = nil
	local NearestDistance = math.huge
 
	for _, Player in pairs(Players:GetPlayers()) do
		if Player ~= Players.LocalPlayer then
			local Distance = (Player.Character.Head.Position - Players.LocalPlayer.Character.Head.Position).magnitude
			if Distance < NearestDistance then
				NearestDistance = Distance
				NearestPlayer = Player
			end
		end
	end
 
	return NearestPlayer
end
 
-- Main Loop
while wait(0.1) do
	local NearestPlayer = GetNearestPlayer()
	if NearestPlayer then
		Mouse.Target = NearestPlayer.Character.Head
	end
end
