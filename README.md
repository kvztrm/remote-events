# remote-events
remote event collection


-- slot collection remote events

```
local args = {
	{
		workspace:WaitForChild("Bases"):WaitForChild("6"):WaitForChild("PlotSlots"):WaitForChild("Slot1"):WaitForChild("ClaimButton"):WaitForChild("Button"),
		"\023"
	}
}
game:GetService("ReplicatedStorage"):WaitForChild("ncxyzero_bridgenet2-fork@1.1.5"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))
```

# Slot 1 can be changed from 1 to 17

-- placing down stuff into slot 2

```
local args = {
	{
		{
			"\001",
			"\143T\1402F\245A[\178\198\163\245n\199\132]",
			{
				"2"
			}
		},
		"\031"
	}
}
game:GetService("ReplicatedStorage"):WaitForChild("ncxyzero_bridgenet2-fork@1.1.5"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))
```
# Can be changed to any slot by changing the number on line 6

-- locking base

```
local args = {
	{
		workspace:WaitForChild("Bases"):WaitForChild("2"):WaitForChild("LockgateButton"):WaitForChild("Button"),
		"\022"
	}
}
game:GetService("ReplicatedStorage"):WaitForChild("ncxyzero_bridgenet2-fork@1.1.5"):WaitForChild("dataRemoteEvent"):FireServer(unpack(args))

```

-- looping all functions except placement

```
while wait() do
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local remote = ReplicatedStorage:WaitForChild("ncxyzero_bridgenet2-fork@1.1.5"):WaitForChild("dataRemoteEvent")

local baseNumber = "2"

for i = 1, 12 do
	local success, err = pcall(function()
		local button = workspace
			:WaitForChild("Bases")
			:WaitForChild(baseNumber)
			:WaitForChild("PlotSlots")
			:WaitForChild("Slot" .. i)
			:WaitForChild("ClaimButton")
			:WaitForChild("Button")

		remote:FireServer({ button, "\023" })
	end)

	if not success then
		warn("Slot" .. i .. " failed: " .. err)
	end

	wait(0.1)
end

-- Fire LockgateButton
local success, err = pcall(function()
	local lockButton = workspace
		:WaitForChild("Bases")
		:WaitForChild(baseNumber)
		:WaitForChild("LockgateButton")
		:WaitForChild("Button")

	remote:FireServer({ lockButton, "\022" })
end)

if not success then
	warn("LockgateButton failed: " .. err)
end
end
```

# Change local base num. to your base num.

-- destroying the teleport / a.c.

```
local removed = 0
for _, obj in ipairs(workspace:GetDescendants()) do
	if obj.Name == "PlotTeritory" or obj.Name == "PlotTeritory2" then
		obj:Destroy()
		removed = removed + 1
	end
end
```
