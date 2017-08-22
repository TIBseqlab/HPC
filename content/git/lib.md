#### 基本原则
原则上，用户尽量把库文件安装在自己的home文件夹下，这样可以保证在各个计算节点上软件的正常使用。实在有必要，请联系管理员安装部分库文件。
#### 通用库安装
###### 编辑器

|软件名称|	软件信息||
|--|--|--|
|GNU编译器|	软件版本|	4.4.7|
|	|安装路径|	/usr|
|	|环境变量配置文件|	-|
|	|调用方式|	C：gcc C++：g++ F77：gfortran F90: gfortran| 
|Intel编译器|	软件版本|	15.0.2|
|	|安装路径|/public/software/Compiler/intel/composer_xe_2015.2.164/|
|	|环境变量配置文件	| /etc/profile.d/iccvars_intel64.sh /etc/profile.d/ifortvars_intel64.sh|
|	|调用方式|	C：icc C++：icpc F77：ifort F90: ifort|

###### 数学库
|软件名称|	软件信息||
|--|--|--|
|GotoBLAS2（Intel编译器调用）|	说明|	BLAS+LAPACK数学库（LAPACK用ifort编译）|
|	|软件版本	|GotoBLAS2-1.13|
|	|安装路径	|/public/software/mathlib/goto2/libgoto2-ifort.a /public/software/mathlib/goto2/libgoto2-ifort.so|
|	|调用方式	|ifort/icc ... -L/public/software/mathlib/goto2 -lgoto2-ifort ifort/icc ... /public/software/mathlib/goto2/libgoto2-ifort.a|
|FFTW2-float|	说明|	单精度版FFTW2数学库|
|	|软件版本|	fftw-2.1.5|
|	|安装路径|	/public/software/mathlib/fftw215-float|
|	|调用方式|	<编译器> -I/public/software/mathlib/fftw215-float/include ... -L/public/software/mathlib/fftw215-float/lib -lsrfftw -lsfftw |
|FFTW2-double|	说明|	双精度版FFTW2数学库|
|	|软件版本|	fftw-2.1.5|
|	|安装路径|	/public/software/mathlib/fftw215-double|
|	|调用方式|	<编译器> -I/public/software/mathlib/fftw215-double/include ... -L/public/software/mathlib/fftw215-double/lib -lrfftw -lfftw|
|FFTW3-float|	说明|	单精度版FFTW3数学库|
|	|软件版本|	fftw-3.3.2|
|	|安装路径|	/public/software/mathlib/fftw332-float|
|	|调用方式|	<编译器> -I/public/software/mathlib/fftw332-float/include ... -L/public/software/mathlib/fftw332-float/lib -lfftw3f|
|FFTW3-double|	说明|	双精度版FFTW3数学库|
||	软件版本	|fftw-3.3.2|
||	安装路径|	/public/software/mathlib/fftw332-double|
||	调用方式|	<编译器> -I/public/software/mathlib/fftw332-double/include ... -L/public/software/mathlib/fftw332-double/lib -lfftw3|
|Intel MKL|	说明	|Intel MKL，包含BLAS、LAPACK、FFT、ScaLAPACK、BLACS等|
||	软件版本	|Intel Compiler 自带版本|
||	安装路径|	/public/software/intel/Compiler/intel/composer_xe_2015.2.164/mkl| 
||	环境变量配置文件|	/etc/profile.d/mklvarsem64t.sh|
||	调用方式|	ifort/icc ... -L/public/software/intel/Compiler/11.1/59/mkl/lib/em64t -lmkl_intel_lp64 -lmkl_sequential -lmkl_core|

###### MPI 并行库
|软件名称|	软件信息||
|--|--|--|
|OpenMPI（与Intel编译器关联）|	说明|	OpenMPI，与Intel编译器关联，支持以太网和InfiniBand。系统默认的MPI环境|
||	软件版本|	openmpi-1.6.5|
||	安装路径|	/public/software/mpi/openmpi/1.6.5/|
||	调用方式|	C：mpicc C++：mpicxx F77：mpif77 F90: mpif90 mpirun -np <N> -machinefile <machinefile> ...|


