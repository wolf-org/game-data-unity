<p align="left">
  <a>
    <img alt="Made With Unity" src="https://img.shields.io/badge/made%20with-Unity-57b9d3.svg?logo=Unity">
  </a>
  <a>
    <img alt="License" src="https://img.shields.io/github/license/wolf-package/game-data-unity?logo=github">
  </a>
  <a>
    <img alt="Last Commit" src="https://img.shields.io/github/last-commit/wolf-package/game-data-unity?logo=Mapbox&color=orange">
  </a>
  <a>
    <img alt="Repo Size" src="https://img.shields.io/github/repo-size/wolf-package/game-data-unity?logo=VirtualBox">
  </a>
  <a>
    <img alt="Last Release" src="https://img.shields.io/github/v/release/wolf-package/game-data-unity?include_prereleases&logo=Dropbox&color=yellow">
  </a>
</p>

## What
- System data for game unity (Unity 2022.3)
- Using [Unity.Serialization](https://docs.unity3d.com/Packages/com.unity.serialization@3.1/manual/index.html) to serialize binary data
- Data allows you to store data in byte[] form in blocks called profiles. Each profile is a Dictionary with the key as a string and the value
## How To Install
### Add the line below to `Packages/manifest.json`

for version `1.0.2`
```csharp
"com.wolf-org.game-data":"https://github.com/wolf-org/game-data-unity.git#1.0.2",
```
## Use

- Initialize data when loading the game: `GameData.Init()` Data will be init (Load Data) automatically when game starts
- Change Profile: `GameData.ChangeProfile(int profile)`
- Load Data: `GameData.Load()` Load all data from file for game
- Get Data: `GameData.Get("KEY", valueDefault);` Use similar to PlayerPrefs
- Set Data: `GameData.Set("KEY", value);` Use similar to PlayerPrefs
- Save Data: `GameData.Save()` Save data to file (You should save when pausing or quitting the game)
```csharp
    private void OnApplicationPause(bool pauseStatus)
    {
        if(pauseStatus) GameData.Save();
    }
```
- Has Key: `GameData.HasKey(string key)` To check if the profile has a key,
- DeleteKey: `GameData.DeleteKey(string key)` To delete the key from the profile
- DeleteAll: `GameData.DeleteAll()` To delete the entire key
- Backup: `GameData.Backup()` Get raw byte[] of all data of profile
- Restore: `GameData.Restore(byte[] bytes)` Load from byte[]
