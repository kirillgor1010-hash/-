

```lua
local humanoid = script.Parent:WaitForChild("Humanoid")

local walkSpeed = 16 -- скорость походки
local isWalking = false

local function walk()
    isWalking = true
    humanoid.WalkSpeed = walkSpeed
end

local function stopWalking()
    isWalking = false
    humanoid.WalkSpeed = 0
end

humanoid.Died:Connect(function()
    stopWalking()
end)

game:GetService("RunService").Stepped:Connect(function()
    if isWalking then
        local moveDirection = Vector3.new(1, 0, 0) -- направление движения
        humanoid:Move(moveDirection * walkSpeed)
    end
end)

walk() -- начать походку при запуске скрипта
```

Добавьте этот скрипт к объекту персонажа в Roblox Studio, и ваш персонаж будет двигаться вперед со скоростью 16 в единицу времени. Вы можете настроить параметры скрипта, чтобы изменить скорость или направление движения.

Надеюсь, этот пример поможет вам создать интересную походку для вашего персонажа в Roblox Studio!
