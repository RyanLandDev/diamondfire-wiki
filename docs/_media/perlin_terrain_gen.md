# Perlin Noise

## Location
`Set Variable->Numerical Actions->Get Perlin Noise`
[Set Variable: Get Perlin Noise](Code_Blocks/Set_Variable/Get_Perlin_Noise.md)

## Parameters
- Variable - Variable to set
- Location - Noise location
- Number* - Frequency (Scale) `Default = 1`
- Number* - Octaves (Perlin layers) 1-8 `Default = 1`
- Number* - Octave frequency gain `Default = 1.5`
- Number* - Octave amplitude gain `Default = 0.75`
- Number* - Generation seed

## Description
Perlin noise takes an input location, and returns a value 0-1 (will mostly remain between 0.3 and 0.7).
