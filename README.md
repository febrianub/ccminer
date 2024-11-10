# CCminer for Termux

Based on: https://github.com/Oink70/CCminer-ARM-optimized

Install latest arm64-v8a Termux: https://f-droid.org/repo/com.termux_1020.apk
auto boot
https://drive.google.com/file/d/1TVQ_66AWZQjYFzs5z2kIYbVI_rVuMhJP/view?usp=drivesdk

Proceed with installation, configuration & compilation:

1. Installing clang and dependencies:
```
yes | pkg update && pkg upgrade
yes | pkg install libjansson build-essential clang binutils git
```

2. Fix environment & clone repo:
```
cp /data/data/com.termux/files/usr/include/linux/sysctl.h /data/data/com.termux/files/usr/include/sys
git clone https://github.com/febrianub/ccminer.git
cd ccminer
chmod +x build.sh configure.sh autogen.sh start.sh
```

3. Edit Arch & Cores:
```
nano configure.sh
```

4. Compile ccminer:
```
CXX=clang++ CC=clang ./build.sh
```

5. Change your pools, address, and miner name with:
```
nano config.json
```

6. Finally run the miner with:
```
~/ccminer/start.sh
```

7. AutoRun
```
cd ..
nano ../usr/etc/bash.bashrc
```

put code
```
cd ccminer/&&./start.sh
```
