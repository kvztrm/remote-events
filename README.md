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

""Slot 1 can be changed from 1 to 17""
