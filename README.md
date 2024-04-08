local Players = game:GetService("Players")
local Player = Players.LocalPlayer
local Character = Player.Character
local Humanoid = Character:WaitForChild("Humanoid")

-- Create a new GUI
local GUI = Instance.new("ScreenGui")
GUI.Parent = Player.PlayerGui
GUI.Name = "SpeedGUI"

-- Create a new Frame
local Frame = Instance.new("Frame")
Frame.Parent = GUI
Frame.BackgroundColor3 = Color3.new(0, 0, 0)
Frame.Size = UDim2.new(0.4, 0, 0.4, 0)
Frame.Position = UDim2.new(0.5, -200, 0.5, -200)

-- Create a new TextLabel for the title
local TitleLabel = Instance.new("TextLabel")
TitleLabel.Parent = Frame
TitleLabel.BackgroundTransparency = 1
TitleLabel.Size = UDim2.new(1, 0, 0.1, 0)
TitleLabel.Position = UDim2.new(0, 0, 0, 0)
TitleLabel.Text = "EXP script"
TitleLabel.Font = Enum.Font.SourceSansBold
TitleLabel.TextSize = 20
TitleLabel.TextColor3 = Color3.new(1, 1, 1)

-- Create a new TextLabel for the speed input
local SpeedLabel = Instance.new("TextLabel")
SpeedLabel.Parent = Frame
SpeedLabel.BackgroundTransparency = 1
SpeedLabel.Size = UDim2.new(1, 0, 0.1, 0)
SpeedLabel.Position = UDim2.new(0, 0, 0.1, 0)
SpeedLabel.Text = "Enter a new speed:"
SpeedLabel.Font = Enum.Font.SourceSansBold
SpeedLabel.TextSize = 15
SpeedLabel.TextColor3 = Color3.new(1, 1, 1)

-- Create a new TextBox for speed input
local SpeedTextBox = Instance.new("TextBox")
SpeedTextBox.Parent = Frame
SpeedTextBox.BackgroundColor3 = Color3.new(0.5, 0.5, 0.5)
SpeedTextBox.Size = UDim2.new(0.5, 0, 0.1, 0)
SpeedTextBox.Position = UDim2.new(0.1, 0, 0.2, 0)

-- Create a new Button for confirming the speed
local ConfirmButton = Instance.new("TextButton")
ConfirmButton.Parent = Frame
ConfirmButton.BackgroundColor3 = Color3.new(0.5, 0.5, 0.5)
ConfirmButton.Size = UDim2.new(0.2, 0, 0.1, 0)
ConfirmButton.Position = UDim2.new(0.7, 0, 0.2, 0)
ConfirmButton.Text = "Confirm"
ConfirmButton.MouseButton1Click:Connect(function()
-- Convert the input to a number
local Speed = tonumber(SpeedTextBox.Text)
if Speed then
-- Change the humanoid's walk speed
Humanoid.WalkSpeed = Speed
-- Destroy the GUI
GUI:Destroy()
end
end)

-- Create a new Button for exiting the GUI
local ExitButton = Instance.new("TextButton")
ExitButton.Parent = Frame
ExitButton.BackgroundColor3 = Color3.new(0.5, 0.5, 0.5)
ExitButton.Size = UDim2.new(0.1, 0, 0.05, 0)
ExitButton.Position = UDim2.new(0.9, 0, 0.95, 0)
ExitButton.Text = "X"
ExitButton.MouseButton1Click:Connect(function()
-- Destroy the GUI
GUI:Destroy()
end)
