## lab0_test_for_env


这个用来测试你的环境是否正常。
如果你是在一个python虚拟环境下安装的opencv,记得激活它:

```bash
conda activate <your_env_name>
```

如果你是python选手，进入scripts目录并启动test.py:
```bash
# linux环境
cd scripts
python test.py
```

如果你是c++选手，创建build目录，完成构建后启动可执行码:
```bash
# linux环境
mkdir build
cd build
cmake ..
make
./lab0
```

如果你成功地配置了环境，程序会弹出一张欧阳老师的帅照。

