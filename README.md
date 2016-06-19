# lab4
A. 0000000000600e50 d DYNAMIC 0000000000600fe8 d _GLOBAL_OFFSET_TABLE 0000000000400608 R _IO_stdin_used w _Jv_RegisterClasses

00000000004004b4 T _Z7averagePdRd 00000000004004e2 T _Z7averageif //主要看這兩個，因為nm 這個指令即是print 出object的symbol ，而那個程式裡面有兩個相同名稱的function都叫average， 所以g++在編譯時會自動把它用後面輸出的type定名作編號來區分兩個，這叫function overloading，例如:第一個average是吃 (double*,double&)，所以命名就叫averagePdRd，後面的Pd就是pointer double和Rd就是referance double；第二個則是average是吃(int,float)， 所以命名就叫averageif，後面的i就是int、f就是float。

0000000000600e30 d CTOR_END 0000000000600e28 d CTOR_LIST 0000000000600e40 D DTOR_END 0000000000600e38 d DTOR_LIST 0000000000400738 r FRAME_END 0000000000600e48 d JCR_END 0000000000600e48 d JCR_LIST 0000000000601018 A bss_start 0000000000601008 D __data_start 00000000004005c0 t __do_global_ctors_aux 0000000000400420 t __do_global_dtors_aux 0000000000601010 D __dso_handle w __gmon_start 0000000000600e24 d __init_array_end 0000000000600e24 d __init_array_start 00000000004005b0 T __libc_csu_fini 0000000000400520 T __libc_csu_init U __libc_start_main@@GLIBC_2.2.5 0000000000601018 A _edata 0000000000601028 A _end 00000000004005f8 T _fini 0000000000400390 T _init 00000000004003d0 T _start 00000000004003fc t call_gmon_start 0000000000601018 b completed.6531 0000000000601008 W data_start 0000000000601020 b dtor_idx.6533 0000000000400490 t frame_dummy 000000000040050a T main

B. 這是印出的內容 1 8 4 8 4 8 8 8

第一行第一個是變數a 的大小，因為a是char所以有1個byte，第二個是pa(用來存a位置的變數)的大小，因為是在64位元的電腦所以指標有8個byte 第二行第一個是變數b 的大小，因為b是int所以有4個byte，第二個是pb(用來存b位置的變數)的大小，因為是在64位元的電腦所以指標有8個byte 第三行第一個是變數c 的大小，因為c是float所以有4個byte，第二個是pc(用來存c位置的變數)的大小，因為是在64位元的電腦所以指標有8個byte 第四行第一個是變數d 的大小，因為d是double所以有8個byte，第二個是pd(用來存d位置的變數)的大小，因為是在64位元的電腦所以指標有8個byte 不然一般而言，在32位元電腦上通常指標是4 個byte
