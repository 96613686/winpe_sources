# KiRaiseSecurityCheckFailure

- ea: `0x1400f7d80`
- end: `0x1400f8007`
- name: `KiRaiseSecurityCheckFailure`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140100ec0`

## callees

- `0x1400f07d0`
- `0x1400f4040`
- `0x1400f7d80`
- `0x1400f9340`

## pseudocode

```c

```

## disassembly

```asm
0x1400f7d80  sub     qword ptr [rsp+0], 2
0x1400f7d85  cmp     [rsp+arg_0], 23h ; '#'
0x1400f7d8b  jnz     short loc_1400F7D92
0x1400f7d8d  and     dword ptr [rsp+4], 0
0x1400f7d92  sub     rsp, 8
0x1400f7d96  push    rbp
0x1400f7d97  sub     rsp, 158h
0x1400f7d9e  lea     rbp, [rsp+168h+var_E8]
0x1400f7da6  mov     byte ptr [rbp-55h], 1
0x1400f7daa  mov     [rbp-50h], rax
0x1400f7dae  mov     [rbp-48h], rcx
0x1400f7db2  mov     [rbp-40h], rdx
0x1400f7db6  mov     [rbp-38h], r8
0x1400f7dba  mov     [rbp-30h], r9
0x1400f7dbe  mov     [rbp-28h], r10
0x1400f7dc2  mov     [rbp-20h], r11
0x1400f7dc6  test    cs:SkeSmapSupported, 1
0x1400f7dcd  jz      short loc_1400F7DD2
0x1400f7dcf  clac
0x1400f7dd2  test    byte ptr [rbp+0F0h], 1
0x1400f7dd9  jz      loc_1400F7FB6
0x1400f7ddf  test    cs:SkiKvaShadow, 1
0x1400f7de6  jnz     short loc_1400F7DEB
0x1400f7de8  swapgs
0x1400f7deb  lfence
0x1400f7dee  mov     r10, gs:8
0x1400f7df7  or      dword ptr gs:0CCh, 2
0x1400f7e00  test    byte ptr gs:0BA0h, 1
0x1400f7e09  jz      loc_1400F7F93
0x1400f7e0f  test    byte ptr gs:0BA0h, 8
0x1400f7e18  jz      loc_1400F7F3E
0x1400f7e1e  call    loc_1400F7F31
0x1400f7e23  add     rsp, 8
0x1400f7e27  call    loc_1400F7F3A
0x1400f7e2c  add     rsp, 8
0x1400f7e30  call    loc_1400F7E23
0x1400f7e35  add     rsp, 8
0x1400f7e39  call    loc_1400F7E2C
0x1400f7e3e  add     rsp, 8
0x1400f7e42  call    loc_1400F7E35
0x1400f7e47  add     rsp, 8
0x1400f7e4b  call    loc_1400F7E3E
0x1400f7e50  add     rsp, 8
0x1400f7e54  call    loc_1400F7E47
0x1400f7e59  add     rsp, 8
0x1400f7e5d  call    loc_1400F7E50
0x1400f7e62  add     rsp, 8
0x1400f7e66  call    loc_1400F7E59
0x1400f7e6b  add     rsp, 8
0x1400f7e6f  call    loc_1400F7E62
0x1400f7e74  add     rsp, 8
0x1400f7e78  call    loc_1400F7E6B
0x1400f7e7d  add     rsp, 8
0x1400f7e81  call    loc_1400F7E74
0x1400f7e86  add     rsp, 8
0x1400f7e8a  call    loc_1400F7E7D
0x1400f7e8f  add     rsp, 8
0x1400f7e93  call    loc_1400F7E86
0x1400f7e98  add     rsp, 8
0x1400f7e9c  call    loc_1400F7E8F
0x1400f7ea1  add     rsp, 8
0x1400f7ea5  call    loc_1400F7E98
0x1400f7eaa  add     rsp, 8
0x1400f7eae  call    loc_1400F7EA1
0x1400f7eb3  add     rsp, 8
0x1400f7eb7  call    loc_1400F7EAA
0x1400f7ebc  add     rsp, 8
0x1400f7ec0  call    loc_1400F7EB3
0x1400f7ec5  add     rsp, 8
0x1400f7ec9  call    loc_1400F7EBC
0x1400f7ece  add     rsp, 8
0x1400f7ed2  call    loc_1400F7EC5
0x1400f7ed7  add     rsp, 8
0x1400f7edb  call    loc_1400F7ECE
0x1400f7ee0  add     rsp, 8
0x1400f7ee4  call    loc_1400F7ED7
0x1400f7ee9  add     rsp, 8
0x1400f7eed  call    loc_1400F7EE0
0x1400f7ef2  add     rsp, 8
0x1400f7ef6  call    loc_1400F7EE9
0x1400f7efb  add     rsp, 8
0x1400f7eff  call    loc_1400F7EF2
0x1400f7f04  add     rsp, 8
0x1400f7f08  call    loc_1400F7EFB
0x1400f7f0d  add     rsp, 8
0x1400f7f11  call    loc_1400F7F04
0x1400f7f16  add     rsp, 8
0x1400f7f1a  call    loc_1400F7F0D
0x1400f7f1f  add     rsp, 8
0x1400f7f23  call    loc_1400F7F16
0x1400f7f28  add     rsp, 8
0x1400f7f2c  call    loc_1400F7F1F
0x1400f7f31  add     rsp, 8
0x1400f7f35  call    loc_1400F7F28
0x1400f7f3a  add     rsp, 8
0x1400f7f3e  movzx   eax, word ptr gs:0BA2h
0x1400f7f47  cmp     gs:0BA8h, ax
0x1400f7f50  jz      short loc_1400F7F64
0x1400f7f52  mov     gs:0BA8h, ax
0x1400f7f5b  mov     ecx, 48h ; 'H'
0x1400f7f60  xor     edx, edx
0x1400f7f62  wrmsr
0x1400f7f64  movzx   edx, byte ptr gs:0BA0h
0x1400f7f6d  test    edx, 4
0x1400f7f73  jz      short loc_1400F7F83
0x1400f7f75  mov     eax, 1
0x1400f7f7a  xor     edx, edx
0x1400f7f7c  mov     ecx, 49h ; 'I'
0x1400f7f81  wrmsr
0x1400f7f83  test    byte ptr gs:0BA0h, 20h
0x1400f7f8c  jz      short loc_1400F7F93
0x1400f7f8e  call    SkiFlushBhb
0x1400f7f93  lfence
0x1400f7f96  test    r10, r10
0x1400f7f99  mov     qword ptr [rbp+80h], 0
0x1400f7fa4  jz      short loc_1400F7FB6
0x1400f7fa6  bt      dword ptr [r10+0ACh], 5
0x1400f7faf  jnb     short loc_1400F7FB6
0x1400f7fb1  call    SkiSaveDebugRegisterStateForNmi
0x1400f7fb6  lfence
0x1400f7fb9  cld
0x1400f7fba  stmxcsr dword ptr [rbp-54h]
0x1400f7fbe  ldmxcsr cs:SkiInitialMxCsr
0x1400f7fc5  movaps  xmmword ptr [rbp-10h], xmm0
0x1400f7fc9  movaps  xmmword ptr [rbp+0], xmm1
0x1400f7fcd  movaps  xmmword ptr [rbp+10h], xmm2
0x1400f7fd1  movaps  xmmword ptr [rbp+20h], xmm3
0x1400f7fd5  movaps  xmmword ptr [rbp+30h], xmm4
0x1400f7fd9  movaps  xmmword ptr [rbp+40h], xmm5
0x1400f7fdd  test    qword ptr [rbp+0F8h], 200h
0x1400f7fe8  jz      short loc_1400F7FEB
0x1400f7fea  sti
0x1400f7feb  mov     r9, [rbp-48h]
0x1400f7fef  mov     ecx, 0C0000409h
0x1400f7ff4  mov     edx, 1
0x1400f7ff9  mov     r8, [rbp+0E8h]
0x1400f8000  call    KiFastFailDispatch
0x1400f8005  nop
0x1400f8006  retn
```
