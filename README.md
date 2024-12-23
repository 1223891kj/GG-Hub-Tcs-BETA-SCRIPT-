# GG-Hub-Tcs-BETA-SCRIPT-
local Players = game:GetService("Players")
local CoreGui = game:GetService("CoreGui")
local UserInputService = game:GetService("UserInputService")

-- Função para criar a interface do usuário
local function createUI()
    local ScreenGui = Instance.new("ScreenGui")
    ScreenGui.Parent = CoreGui

    local Frame = Instance.new("Frame")
    Frame.Size = UDim2.new(0, 200, 0, 150)
    Frame.Position = UDim2.new(0.5, -100, 0.5, -75)
    Frame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
    Frame.Parent = ScreenGui

    local Title = Instance.new("TextLabel")
    Title.Size = UDim2.new(1, 0, 0, 50)
    Title.BackgroundTransparency = 1
    Title.Text = "GG hub [BETA]"
    Title.TextColor3 = Color3.fromRGB(255, 255, 255)
    Title.Font = Enum.Font.SourceSansBold
    Title.TextSize = 24
    Title.Parent = Frame

    local HandsButton = Instance.new("TextButton")
    HandsButton.Size = UDim2.new(0.8, 0, 0, 30)
    HandsButton.Position = UDim2.new(0.1, 0, 0.4, 0)
    HandsButton.Text = "Hands Reach"
    HandsButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    HandsButton.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
    HandsButton.Parent = Frame

    local FeetButton = Instance.new("TextButton")
    FeetButton.Size = UDim2.new(0.8, 0, 0, 30)
    FeetButton.Position = UDim2.new(0.1, 0, 0.7, 0)
    FeetButton.Text = "Foot Reach"
    FeetButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    FeetButton.BackgroundColor3 = Color3.fromRGB(100, 100, 100)
    FeetButton.Parent = Frame

    return HandsButton, FeetButton
end

-- Função para aumentar o alcance das mãos
local function extendHands(player)
    local character = player.Character
    if character then
        local leftHand = character:FindFirstChild("LeftHand")
        local rightHand = character:FindFirstChild("RightHand")
        if leftHand and rightHand then
            leftHand.Size = Vector3.new(5, 5, 5)
            rightHand.Size = Vector3.new(5, 5, 5)
        end
    end
end

-- Função para aumentar o alcance dos pés
local function extendFeet(player)
    local character = player.Character
    if character then
        local leftFoot = character:FindFirstChild("LeftFoot")
        local rightFoot = character:FindFirstChild("RightFoot")
        if leftFoot and rightFoot then
            leftFoot.Size = Vector3.new(5, 5, 5)
            rightFoot.Size = Vector3.new(5, 5, 5)
        end
    end
end

-- Criar a interface do usuário e conectar os botões
local HandsButton, FeetButton = createUI()

HandsButton.MouseButton1Click:Connect(function()
    local player = Players.LocalPlayer
    extendHands(player)
end)

FeetButton.MouseButton1Click:Connect(function()
    local player = Players.LocalPlayer
    extendFeet(player)
end)

