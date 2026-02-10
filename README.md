# 1. 创建新环境

```bash
conda create -n alicia_py312 python=3.12
conda activate alicia_py312
```

# 2. 安装依赖

```bash
pip install -r requirements.txt
pip install -e .
```

# 3. 修复synriard
```bash
# 复制URDF文件
conda run -n alicia_py312 bash -c "cp -r fix_env/urdf/Alicia_D_v5_6 /root/miniconda3/envs/alicia_py312/lib/python3.12/site-packages/synriard/urdf/"

conda run -n alicia_py312 bash -c "cp -r fix_env/urdf/Alicia_D_v5_5 /root/miniconda3/envs/alicia_py312/lib/python3.12/site-packages/synriard/urdf/"

conda run -n alicia_py312 bash -c "cp -r fix_env/urdf/Alicia_M_v1_0 /root/miniconda3/envs/alicia_py312/lib/python3.12/site-packages/synriard/urdf/"

conda run -n alicia_py312 bash -c "cp -r fix_env/urdf/Bessica_M_v1_0 /root/miniconda3/envs/alicia_py312/lib/python3.12/site-packages/synriard/urdf/"

# 复制MJCF文件
conda run -n alicia_py312 bash -c "cp -r fix_env/mjcf/Alicia_D_v5_5 /root/miniconda3/envs/alicia_py312/lib/python3.12/site-packages/synriard/mjcf/"

conda run -n alicia_py312 bash -c "cp -r fix_env/mjcf/Bessica_M_v1_0 /root/miniconda3/envs/alicia_py312/lib/python3.12/site-packages/synriard/mjcf/"
```

# 4. 验证修复

```bash
# 检查可用的URDF模型
python -c "from synriard import urdf; print('Available URDFs:', [x for x in dir(urdf) if not x.startswith('_')])"

# 运行示例脚本（根据实际机器人硬件选择参数）
# 如果是Alicia_D_v5_6机器人（默认）：
python examples/03_demo_read_state.py --robot_version v5_6 --gripper_type 50mm

# 如果是Alicia_D_v5_5机器人：
python examples/03_demo_read_state.py --robot_version v5_5 --gripper_type 100mm
```

## 注意事项

- **robot_version**: 根据实际机器人硬件选择，可选值：v5_5, v5_6, v5_4等
- **gripper_type**: 根据夹爪类型选择，可选值：50mm, 100mm
- Alicia_D_v5_5只支持100mm夹爪
- Alicia_D_v5_6支持50mm和100mm夹爪
- 默认使用v5_6 + 50mm夹爪