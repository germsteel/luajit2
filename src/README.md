# LuaJIT 源代码目录 (src)

本目录包含LuaJIT的核心源代码文件。以下是各类文件的简要说明：

## 主要头文件
- **lua.h** - Lua API的主要头文件，定义了基础API函数和常量
- **luaconf.h** - Lua配置头文件，包含平台特定的配置和宏定义
- **lualib.h** - Lua标准库的头文件
- **luajit.h** - LuaJIT特定的API头文件
- **luajit_rolling.h** - LuaJIT版本相关的头文件

## 核心源文件
- **luajit.c** - LuaJIT的主程序入口，实现命令行解释器
- **lj_obj.h/c** - 定义Lua对象的内部结构和类型
- **lj_gc.h/c** - 垃圾收集器的实现
- **lj_err.h/c** - 错误处理机制
- **lj_state.h/c** - Lua状态管理
- **lj_meta.h/c** - 元表和元方法的处理
- **lj_func.h/c** - 函数对象的实现
- **lj_str.h/c** - 字符串对象的实现和操作
- **lj_tab.h/c** - 表(table)对象的实现和操作
- **lj_lib.h/c** - 库注册和管理

## 词法和语法分析
- **lj_lex.h/c** - 词法分析器
- **lj_parse.h/c** - 语法分析器
- **lj_load.c** - 加载和编译Lua代码

## JIT编译器
- **lj_jit.h** - JIT编译器的主要头文件
- **lj_ir.h/c** - 中间表示(IR)的定义和操作
- **lj_ircall.h** - IR调用相关的定义
- **lj_iropt.h** - IR优化相关的头文件
- **lj_trace.h/c** - 跟踪记录和管理
- **lj_record.h/c** - 记录Lua代码执行为IR
- **lj_snap.h/c** - 快照(栈状态)管理
- **lj_mcode.h/c** - 机器码生成管理
- **lj_gdbjit.h/c** - GDB JIT接口，用于调试

## 优化器
- **lj_opt_*.c** - 各种IR优化器的实现:
  - **lj_opt_dce.c** - 死代码消除
  - **lj_opt_fold.c** - 常量折叠
  - **lj_opt_loop.c** - 循环优化
  - **lj_opt_mem.c** - 内存访问优化
  - **lj_opt_narrow.c** - 类型窄化优化
  - **lj_opt_sink.c** - 代码下沉优化
  - **lj_opt_split.c** - 快照分割优化

## 虚拟机
- **lj_vm.h** - 虚拟机头文件
- **lj_vmevent.h/c** - 虚拟机事件处理
- **lj_vmmath.c** - 虚拟机数学运算
- **vm_*.dasc** - 不同架构的DynASM模板文件:
  - **vm_x86.dasc** - x86架构
  - **vm_x64.dasc** - x64架构
  - **vm_arm.dasc** - ARM架构
  - **vm_arm64.dasc** - ARM64架构
  - **vm_ppc.dasc** - PowerPC架构
  - **vm_mips.dasc** - MIPS架构
  - **vm_mips64.dasc** - MIPS64架构
  - **vm_s390x.dasc** - IBM z/Architecture(s390x)

## 特定架构的目标代码
- **lj_target.h** - 目标架构的通用定义
- **lj_target_*.h** - 特定架构的定义:
  - **lj_target_x86.h** - x86架构
  - **lj_target_arm.h** - ARM架构
  - **lj_target_arm64.h** - ARM64架构
  - **lj_target_ppc.h** - PowerPC架构
  - **lj_target_mips.h** - MIPS架构
  - **lj_target_s390x.h** - IBM z/Architecture(s390x)

## 其他功能
- **lj_udata.h/c** - 用户数据对象的实现
- **lj_prng.h/c** - 伪随机数生成器
- **lj_profile.h/c** - 性能分析工具
- **lj_serialize.h/c** - 对象序列化功能
- **lj_strfmt.h/c** - 字符串格式化功能
- **lj_strfmt_num.c** - 数字格式化功能
- **lj_strscan.h/c** - 字符串扫描和转换

## FFI库
- **lj_ffrecord.h/c** - FFI调用的记录
- **lj_ff.h** - 快速函数的定义

## 构建脚本
- **msvcbuild.bat** - MSVC(Windows)构建脚本
- **xedkbuild.bat** - Xbox EDK构建脚本
- **xb1build.bat** - Xbox One构建脚本
- **ps4build.bat** - PlayStation 4构建脚本
- **ps5build.bat** - PlayStation 5构建脚本
- **psvitabuild.bat** - PlayStation Vita构建脚本
- **nxbuild.bat** - Nintendo Switch构建脚本

## 其他
- **ljamalg.c** - 源代码合并文件，用于单文件构建
- **lua.hpp** - C++的Lua头文件 