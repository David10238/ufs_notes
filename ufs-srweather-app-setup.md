
Full setup instructions are located at the [UFS Short-Range Weather App Users Guide](https://ufs-srweather-app.readthedocs.io/en/develop/Quickstart.html#install-the-hpc-stack).

Make sure once you clone the app, edit the following line inside `ufs-srweather-app/modulefiles/build_linux_gnu.lua`
```lua
-- This path should point to your HPCstack installation directory
local HPCstack="/home/david10238/Desktop/hpc-stack/install"
```

This is the step I was stuck on at the end with the following error whenever I tried to load the modules.

![final error](img/final_error.png)

This looks to be saying that `load_any` is nil, so the likely culprit was the Lmod setup.