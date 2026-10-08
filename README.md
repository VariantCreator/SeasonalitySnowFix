# Seasonality Snow Fix

A patch for trees, rocks and buildings that stay snowy when using Seasonality on a larger world. It also corrects the map coordinate checks used for Deep North ocean weather.

Seasonality still controls the seasons. Mountains and the Deep North keep their snow, and normal winter cold remains. The patch runs as objects load, in both explored and new areas. Existing worlds do not need to be regenerated.

## Install

Install with your mod manager, or copy `SeasonalitySnowFix.dll` into `BepInEx/plugins` in your game or profile folder.

Install on each player's client. The server does not need this patch.

Close the game completely before updating and replace the older DLL. Returning to the main menu does not reload plugins.

If you have the first test build, remove `SeasonalityExpandedWorldSnowFix.dll` before installing this one.

## Required mods

- BepInEx
- Seasonality 3.8.3 (or later)
- Expand World Size 1.43.0 or 1.44.0 (or later)

Expand World Data is optional. This build is for Valheim 1.0.17.

## Settings

The patch runs automatically on larger worlds. Its settings are in `BepInEx/config/Variant.SeasonalityExpandedWorldSnowFix.cfg`.

- `Enabled`: turn the patch on or off.
- `Fix Ocean Weather`: correct the Deep North map coordinate checks.

The patch reads the active world size from Expand World Size, including settings loaded from the world file in 1.44.

## Updates

If a required game or world-size API changes, the patch stays off and logs a message. Changed Seasonality update hooks fall back to regular background checks. The ocean weather correction is skipped when the game already uses the correct coordinates.

## Notes

This corrects the snow overlay and coastal weather checks. Custom weather can still make an area cold or freezing. The patch does not grant cold immunity.

In Seasonality 3.8.3, use `Warm_Twilight_SnowStorm` in winter weather entries. Some configs use the unregistered name `Warm_Twilight_Snow`. Update Seasonality's server config too when playing on a server.

On affected objects, the patch also removes snow caused by high altitude in normally snow-free biomes. Custom biomes and other shaders are left alone.

To uninstall, close the game and remove `SeasonalitySnowFix.dll`.
