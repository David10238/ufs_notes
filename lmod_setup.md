HPC-Stack relies on using Lmod as module management system. Module files are Lua files that are loaded using the Lmod and Luarocks libraries.

I would recommend using the instructions located at the [Lmod documentation](https://lmod.readthedocs.io/en/latest/030_installing.html) to install Lua, Luarocks and Lmod.

Here's the commands that I used for installation.

```bash
#prerequisite for configuring Lmod install
sudo apt install tcl-dev



# installing lua
wget https://sourceforge.net/projects/lmod/files/lua-5.1.4.9.tar.bz2
tar xf lua-5.1.4.9.tar.bz2
cd lua-5.1.4.9
./configure --prefix=/opt/apps/lua/5.1.4.9
make; 
sudo make install
sudo cd /opt/apps/lua
sudo ln -s 5.1.4.9 lua
sudo mkdir /usr/local/bin
sudo ln -s /opt/apps/lua/lua/bin/lua /usr/local/bin


# installing luarocks
sudo apt install luarocks
sudo luarocks install luaposix


#LUAROCKS_PREFIX may need changed
LUAROCKS_PREFIX=/usr/local
export LUA_PATH="$LUAROCKS_PREFIX/share/lua/5.1/?.lua;$LUAROCKS_PREFIX/share/lua/5.1/?/init.lua;;"
export LUA_CPATH="$LUAROCKS_PREFIX/lib/lua/5.1/?.so;;"




# INSTALLING Lmod
wget https://sourceforge.net/projects/lmod/files/Lmod-8.7.tar.bz2
tar xf Lmod-8.7.tar.bz2
cd Lmod-8.7

./configure --prefix=/opt/apps
sudo make install



## following must be put in my login profiles

# add to login shell. is important this runs before the z00_lmod.* files
export BASH_ENV=$HOME/apps/lmod/lmod/init/profile
source $BASH_ENV

## paste in new profile files to load paths
# in new file: /etc/profile.d/z00_lmod.sh
ln -s /opt/apps/lmod/lmod/init/profile
# in new file: /etc/profile.d/z00_lmod.csh
ln -s /opt/apps/lmod/lmod/init/cshrc
```