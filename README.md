local RevulAntiLagger = Instance.new("ScreenGui")
RevulAntiLagger.Name = "RevulAntiLagger"
RevulAntiLagger.ResetOnSpawn = false
RevulAntiLagger.Parent = game:GetService("Players").LocalPlayer:WaitForChild("PlayerGui")

local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")
local RunService = game:GetService("RunService")
local Lighting = game:GetService("Lighting")
local Workspace = game:GetService("Workspace")

local Frame = Instance.new("Frame")
Frame.Name = "Frame"
Frame.Active = true
Frame.Position = UDim2.new(0.5,-115,0.5,-65)
Frame.Size = UDim2.new(0,230,0,130)
Frame.BackgroundColor3 = Color3.fromRGB(8,8,12)
Frame.BorderSizePixel = 0
Frame.ClipsDescendants = true
Frame.Parent = RevulAntiLagger

    local UICorner = Instance.new("UICorner")
    UICorner.CornerRadius = UDim.new(0,12)
    UICorner.Parent = Frame

    local UIStroke = Instance.new("UIStroke")
    UIStroke.Color = Color3.fromRGB(255,255,255)
    UIStroke.Thickness = 1.5
    UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
    UIStroke.Parent = Frame

        local UIGradient = Instance.new("UIGradient")
        UIGradient.Color = ColorSequence.new({
            ColorSequenceKeypoint.new(0,   Color3.fromRGB(70,0,100)),
            ColorSequenceKeypoint.new(0.2, Color3.fromRGB(90,20,130)),
            ColorSequenceKeypoint.new(0.4, Color3.fromRGB(110,40,160)),
            ColorSequenceKeypoint.new(0.6, Color3.fromRGB(130,60,190)),
            ColorSequenceKeypoint.new(0.8, Color3.fromRGB(100,30,150)),
            ColorSequenceKeypoint.new(1,   Color3.fromRGB(70,0,100)),
        })
        UIGradient.Rotation = 278.4
        UIGradient.Parent = UIStroke

    local rot = 278.4
    RunService.Heartbeat:Connect(function(dt)
        rot = (rot + dt * 60) % 360
        UIGradient.Rotation = rot
    end)

    local TextButton = Instance.new("TextButton")
    TextButton.Position = UDim2.new(1,-35,0,5)
    TextButton.Size = UDim2.new(0,25,0,25)
    TextButton.BackgroundColor3 = Color3.fromRGB(30,30,40)
    TextButton.BorderSizePixel = 0
    TextButton.Text = "-"
    TextButton.TextColor3 = Color3.fromRGB(255,255,255)
    TextButton.TextSize = 18
    TextButton.Font = Enum.Font.GothamBold
    TextButton.Parent = Frame

        local UICorner2 = Instance.new("UICorner")
        UICorner2.CornerRadius = UDim.new(0,6)
        UICorner2.Parent = TextButton

        local UIStroke2 = Instance.new("UIStroke")
        UIStroke2.Color = Color3.fromRGB(255,255,255)
        UIStroke2.Thickness = 1.5
        UIStroke2.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
        UIStroke2.Parent = TextButton

            local UIGradient2 = Instance.new("UIGradient")
            UIGradient2.Color = UIGradient.Color
            UIGradient2.Rotation = 278.4
            UIGradient2.Parent = UIStroke2

    local TextButton2 = Instance.new("TextButton")
    TextButton2.Visible = false
    TextButton2.Position = UDim2.new(1,-35,0,5)
    TextButton2.Size = UDim2.new(0,25,0,25)
    TextButton2.BackgroundColor3 = Color3.fromRGB(30,30,40)
    TextButton2.BorderSizePixel = 0
    TextButton2.Text = "+"
    TextButton2.TextColor3 = Color3.fromRGB(255,255,255)
    TextButton2.TextSize = 18
    TextButton2.Font = Enum.Font.GothamBold
    TextButton2.Parent = Frame

        local UICorner3 = Instance.new("UICorner")
        UICorner3.CornerRadius = UDim.new(0,6)
        UICorner3.Parent = TextButton2

        local UIStroke3 = Instance.new("UIStroke")
        UIStroke3.Color = Color3.fromRGB(255,255,255)
        UIStroke3.Thickness = 1.5
        UIStroke3.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
        UIStroke3.Parent = TextButton2

            local UIGradient3 = Instance.new("UIGradient")
            UIGradient3.Color = UIGradient.Color
            UIGradient3.Rotation = 278.4
            UIGradient3.Parent = UIStroke3

    local TextLabel = Instance.new("TextLabel")
    TextLabel.Position = UDim2.new(0,0,0,8)
    TextLabel.Size = UDim2.new(1,0,0,30)
    TextLabel.BackgroundTransparency = 1
    TextLabel.Text = "REVUL ANTI LAGGER"
    TextLabel.TextColor3 = Color3.fromRGB(218,218,218)
    TextLabel.TextSize = 14
    TextLabel.Font = Enum.Font.GothamBlack
    TextLabel.Parent = Frame

        local TextGradient = Instance.new("UIGradient")
        TextGradient.Rotation = 0
        TextGradient.Parent = TextLabel

        local shimmerOffset = 0
        RunService.Heartbeat:Connect(function(dt)
            shimmerOffset = shimmerOffset + dt * 0.6
            local x = shimmerOffset % 1
            local p0 = math.clamp(x - 0.01, 0, 1)
            local p1 = math.clamp(x + 0.01, 0, 1)
            if p0 >= p1 then p1 = math.min(p0 + 0.02, 1) end
            TextGradient.Color = ColorSequence.new({
                ColorSequenceKeypoint.new(0, Color3.fromRGB(150,150,160)),
                ColorSequenceKeypoint.new(math.max(p0 - 0.15, 0), Color3.fromRGB(160,160,170)),
                ColorSequenceKeypoint.new(p0, Color3.fromRGB(200,200,210)),
                ColorSequenceKeypoint.new(math.clamp((p0+p1)/2, p0+0.001, 0.999), Color3.fromRGB(255,255,255)),
                ColorSequenceKeypoint.new(p1, Color3.fromRGB(200,200,210)),
                ColorSequenceKeypoint.new(math.min(p1 + 0.15, 1), Color3.fromRGB(160,160,170)),
                ColorSequenceKeypoint.new(1, Color3.fromRGB(150,150,160)),
            })
        end)

    local TextLabel2 = Instance.new("TextLabel")
    TextLabel2.Position = UDim2.new(0,0,0,36)
    TextLabel2.Size = UDim2.new(1,0,0,16)
    TextLabel2.BackgroundTransparency = 1
    TextLabel2.Text = "discord.gg/revulhub"
    TextLabel2.TextColor3 = Color3.fromRGB(100,100,120)
    TextLabel2.Font = Enum.Font.Gotham
    TextLabel2.Parent = Frame

    local TextButton3 = Instance.new("TextButton")
    TextButton3.Position = UDim2.new(0.5,-100,0,60)
    TextButton3.Size = UDim2.new(0,200,0,40)
    TextButton3.BackgroundColor3 = Color3.fromRGB(30,30,40)
    TextButton3.BorderSizePixel = 0
    TextButton3.Text = "ANTI LAGGER âœ“"
    TextButton3.TextColor3 = Color3.fromRGB(218,218,218)
    TextButton3.TextSize = 13
    TextButton3.Font = Enum.Font.GothamBold
    TextButton3.Parent = Frame

        local UICorner4 = Instance.new("UICorner")
        UICorner4.Parent = TextButton3

        local UIStroke4 = Instance.new("UIStroke")
        UIStroke4.Color = Color3.fromRGB(255,255,255)
        UIStroke4.Thickness = 1.5
        UIStroke4.ApplyStrokeMode = Enum.ApplyStrokeMode.Border
        UIStroke4.Parent = TextButton3

            local UIGradient4 = Instance.new("UIGradient")
            UIGradient4.Color = UIGradient.Color
            UIGradient4.Rotation = 278.4
            UIGradient4.Parent = UIStroke4

local TextLabel3 = Instance.new("TextLabel")
TextLabel3.Position = UDim2.new(0.5,-200,0.5,-25)
TextLabel3.Size = UDim2.new(0,400,0,50)
TextLabel3.BackgroundTransparency = 1
TextLabel3.Text = "discord.gg/revulhub"
TextLabel3.TextColor3 = Color3.fromRGB(125,211,252)
TextLabel3.TextScaled = true
TextLabel3.Font = Enum.Font.GothamBlack
TextLabel3.TextWrapped = true
TextLabel3.TextStrokeColor3 = Color3.fromRGB(0,255,255)
TextLabel3.TextStrokeTransparency = 0.5
TextLabel3.Parent = RevulAntiLagger

-- ============================================================
-- OPEN ANIMATION
-- ============================================================
Frame.Size = UDim2.new(0,0,0,0)
Frame.Position = UDim2.new(0.5,0,0.5,0)
TweenService:Create(Frame, TweenInfo.new(0.4, Enum.EasingStyle.Back, Enum.EasingDirection.Out), {
    Size = UDim2.new(0,230,0,130),
    Position = UDim2.new(0.5,-115,0.5,-65),
}):Play()

-- ============================================================
-- MINIMIZE / EXPAND
-- ============================================================
local minimized = false
local FULL_SIZE = UDim2.new(0,230,0,130)
local MINI_SIZE = UDim2.new(0,230,0,35)
local tweenInfo = TweenInfo.new(0.35, Enum.EasingStyle.Quart, Enum.EasingDirection.Out)

TextButton.MouseButton1Click:Connect(function()
    if minimized then return end
    minimized = true
    TextButton.Visible = false
    TextButton2.Visible = true
    TweenService:Create(Frame, tweenInfo, { Size = MINI_SIZE }):Play()
end)

TextButton2.MouseButton1Click:Connect(function()
    if not minimized then return end
    minimized = false
    TextButton2.Visible = false
    TextButton.Visible = true
    TweenService:Create(Frame, tweenInfo, { Size = FULL_SIZE }):Play()
end)

-- ============================================================
-- BUTTON HOVER EFFECTS
-- ============================================================
local function addHover(btn, normalColor, hoverColor)
    btn.MouseEnter:Connect(function()
        TweenService:Create(btn, TweenInfo.new(0.15), { BackgroundColor3 = hoverColor }):Play()
    end)
    btn.MouseLeave:Connect(function()
        TweenService:Create(btn, TweenInfo.new(0.15), { BackgroundColor3 = normalColor }):Play()
    end)
end

addHover(TextButton,  Color3.fromRGB(30,30,40), Color3.fromRGB(60,20,80))
addHover(TextButton2, Color3.fromRGB(30,30,40), Color3.fromRGB(60,20,80))
addHover(TextButton3, Color3.fromRGB(30,30,40), Color3.fromRGB(50,15,70))

-- ============================================================
-- SNAPSHOT ORIGINAL STATE BEFORE ANY CHANGES
-- ============================================================

-- Save original Lighting values
local originalLighting = {
    GlobalShadows            = Lighting.GlobalShadows,
    FogEnd                   = Lighting.FogEnd,
    Brightness               = Lighting.Brightness,
    EnvironmentDiffuseScale  = Lighting.EnvironmentDiffuseScale,
    EnvironmentSpecularScale = Lighting.EnvironmentSpecularScale,
}

-- Save original PostEffect states
local originalPostEffects = {}
for _, effect in ipairs(Lighting:GetChildren()) do
    if effect:IsA("PostEffect") then
        originalPostEffects[effect] = effect.Enabled
    end
end

-- Save original workspace descendant states
local originalParts = {}
local function SnapshotDescendant(obj)
    if obj:IsA("ParticleEmitter") or obj:IsA("Smoke") or obj:IsA("Fire") or obj:IsA("Sparkles") then
        originalParts[obj] = { Enabled = obj.Enabled }
    elseif obj:IsA("Decal") or obj:IsA("Texture") then
        originalParts[obj] = { Transparency = obj.Transparency }
    elseif obj:IsA("BasePart") then
        originalParts[obj] = {
            Material    = obj.Material,
            Reflectance = obj.Reflectance,
            CastShadow  = obj.CastShadow,
        }
    end
end

for _, obj in ipairs(Workspace:GetDescendants()) do
    SnapshotDescendant(obj)
end

-- ============================================================
-- ANTI-LAG FUNCTIONS
-- ============================================================

local descendantAddedConn = nil

local function ApplyLightingFixes()
    Lighting.GlobalShadows            = false
    Lighting.FogEnd                   = 8999999488
    Lighting.Brightness               = 1
    Lighting.EnvironmentDiffuseScale  = 0
    Lighting.EnvironmentSpecularScale = 0
    for _, effect in ipairs(Lighting:GetChildren()) do
        if effect:IsA("PostEffect") then
            effect.Enabled = false
        end
    end
end

local function RestoreLighting()
    Lighting.GlobalShadows            = originalLighting.GlobalShadows
    Lighting.FogEnd                   = originalLighting.FogEnd
    Lighting.Brightness               = originalLighting.Brightness
    Lighting.EnvironmentDiffuseScale  = originalLighting.EnvironmentDiffuseScale
    Lighting.EnvironmentSpecularScale = originalLighting.EnvironmentSpecularScale
    for effect, wasEnabled in pairs(originalPostEffects) do
        if effect and effect.Parent then
            effect.Enabled = wasEnabled
        end
    end
end

local function OptimiseDescendant(obj)
    -- Snapshot new objects that weren't captured before
    if not originalParts[obj] then
        SnapshotDescendant(obj)
    end
    if obj:IsA("ParticleEmitter") or obj:IsA("Smoke") or obj:IsA("Fire") or obj:IsA("Sparkles") then
        obj.Enabled = false
    elseif obj:IsA("Decal") or obj:IsA("Texture") then
        obj.Transparency = 1
    elseif obj:IsA("BasePart") then
        obj.Material    = Enum.Material.Plastic
        obj.Reflectance = 0
        obj.CastShadow  = false
    end
end

local function RestoreDescendants()
    for obj, saved in pairs(originalParts) do
        if obj and obj.Parent then
            if saved.Enabled ~= nil then
                obj.Enabled = saved.Enabled
            end
            if saved.Transparency ~= nil then
                obj.Transparency = saved.Transparency
            end
            if saved.Material ~= nil then
                obj.Material    = saved.Material
                obj.Reflectance = saved.Reflectance
                obj.CastShadow  = saved.CastShadow
            end
        end
    end
end

local function ApplyWorkspaceFixes()
    for _, obj in ipairs(Workspace:GetDescendants()) do
        OptimiseDescendant(obj)
    end
    -- Hook future streamed-in parts
    descendantAddedConn = Workspace.DescendantAdded:Connect(function(obj)
        OptimiseDescendant(obj)
    end)
end

local function CancelAntiLag()
    -- Disconnect the hook so new parts are no longer touched
    if descendantAddedConn then
        descendantAddedConn:Disconnect()
        descendantAddedConn = nil
    end
    RestoreLighting()
    RestoreDescendants()
end

-- ============================================================
-- ANTI LAGGER BUTTON
-- ============================================================
local antiLaggerActive = false

TextButton3.MouseButton1Click:Connect(function()
    antiLaggerActive = not antiLaggerActive

    -- Bounce press effect
    TweenService:Create(TextButton3, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {
        Size = UDim2.new(0,190,0,36),
        Position = UDim2.new(0.5,-95,0,62),
    }):Play()
    task.wait(0.1)
    TweenService:Create(TextButton3, TweenInfo.new(0.15, Enum.EasingStyle.Back, Enum.EasingDirection.Out), {
        Size = UDim2.new(0,200,0,40),
        Position = UDim2.new(0.5,-100,0,60),
    }):Play()

    if antiLaggerActive then
        TextButton3.Text = "ANTI LAGGER âœ“"
        TextButton3.TextColor3 = Color3.fromRGB(218,218,218)
        ApplyLightingFixes()
        ApplyWorkspaceFixes()
    else
        TextButton3.Text = "ANTI LAGGER âœ—"
        TextButton3.TextColor3 = Color3.fromRGB(180,80,80)
        CancelAntiLag()
    end
end)

-- ============================================================
-- DRAG LOGIC
-- ============================================================
local dragging = false
local dragInput, dragStart, startPos

Frame.InputBegan:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
        dragging = true
        dragStart = input.Position
        startPos = Frame.Position
        input.Changed:Connect(function()
            if input.UserInputState == Enum.UserInputState.End then
                dragging = false
            end
        end)
    end
end)

Frame.InputChanged:Connect(function(input)
    if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
        dragInput = input
    end
end)

UserInputService.InputChanged:Connect(function(input)
    if input == dragInput and dragging then
        local delta = input.Position - dragStart
        Frame.Position = UDim2.new(
            startPos.X.Scale, startPos.X.Offset + delta.X,
            startPos.Y.Scale, startPos.Y.Offset + delta.Y
        )
    end
end)
