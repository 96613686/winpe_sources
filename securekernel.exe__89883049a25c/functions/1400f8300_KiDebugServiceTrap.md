# KiDebugServiceTrap

- ea: `0x1400f8300`
- end: `0x1400f8586`
- name: `KiDebugServiceTrap`
- size: `646`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140100ac0`

## callees

- `0x1400f07d0`
- `0x1400f4040`
- `0x1400f8300`
- `0x1400f9040`

## pseudocode

```c

```

## disassembly

```asm
0x1400f8300  inc     qword ptr [rsp+0]
0x1400f8304  cmp     [rsp+arg_0], 23h ; '#'
0x1400f830a  jnz     short loc_1400F8311
0x1400f830c  and     dword ptr [rsp+4], 0
0x1400f8311  sub     rsp, 8
0x1400f8315  push    rbp
0x1400f8316  sub     rsp, 158h
0x1400f831d  lea     rbp, [rsp+168h+var_E8]
0x1400f8325  mov     byte ptr [rbp-55h], 1
0x1400f8329  mov     [rbp-50h], rax
0x1400f832d  mov     [rbp-48h], rcx
0x1400f8331  mov     [rbp-40h], rdx
0x1400f8335  mov     [rbp-38h], r8
0x1400f8339  mov     [rbp-30h], r9
0x1400f833d  mov     [rbp-28h], r10
0x1400f8341  mov     [rbp-20h], r11
0x1400f8345  test    cs:SkeSmapSupported, 1
0x1400f834c  jz      short loc_1400F8351
0x1400f834e  clac
0x1400f8351  test    byte ptr [rbp+0F0h], 1
0x1400f8358  jz      loc_1400F8535
0x1400f835e  test    cs:SkiKvaShadow, 1
0x1400f8365  jnz     short loc_1400F836A
0x1400f8367  swapgs
0x1400f836a  lfence
0x1400f836d  mov     r10, gs:8
0x1400f8376  or      dword ptr gs:0CCh, 2
0x1400f837f  test    byte ptr gs:0BA0h, 1
0x1400f8388  jz      loc_1400F8512
0x1400f838e  test    byte ptr gs:0BA0h, 8
0x1400f8397  jz      loc_1400F84BD
0x1400f839d  call    loc_1400F84B0
0x1400f83a2  add     rsp, 8
0x1400f83a6  call    loc_1400F84B9
0x1400f83ab  add     rsp, 8
0x1400f83af  call    loc_1400F83A2
0x1400f83b4  add     rsp, 8
0x1400f83b8  call    loc_1400F83AB
0x1400f83bd  add     rsp, 8
0x1400f83c1  call    loc_1400F83B4
0x1400f83c6  add     rsp, 8
0x1400f83ca  call    loc_1400F83BD
0x1400f83cf  add     rsp, 8
0x1400f83d3  call    loc_1400F83C6
0x1400f83d8  add     rsp, 8
0x1400f83dc  call    loc_1400F83CF
0x1400f83e1  add     rsp, 8
0x1400f83e5  call    loc_1400F83D8
0x1400f83ea  add     rsp, 8
0x1400f83ee  call    loc_1400F83E1
0x1400f83f3  add     rsp, 8
0x1400f83f7  call    loc_1400F83EA
0x1400f83fc  add     rsp, 8
0x1400f8400  call    loc_1400F83F3
0x1400f8405  add     rsp, 8
0x1400f8409  call    loc_1400F83FC
0x1400f840e  add     rsp, 8
0x1400f8412  call    loc_1400F8405
0x1400f8417  add     rsp, 8
0x1400f841b  call    loc_1400F840E
0x1400f8420  add     rsp, 8
0x1400f8424  call    loc_1400F8417
0x1400f8429  add     rsp, 8
0x1400f842d  call    loc_1400F8420
0x1400f8432  add     rsp, 8
0x1400f8436  call    loc_1400F8429
0x1400f843b  add     rsp, 8
0x1400f843f  call    loc_1400F8432
0x1400f8444  add     rsp, 8
0x1400f8448  call    loc_1400F843B
0x1400f844d  add     rsp, 8
0x1400f8451  call    loc_1400F8444
0x1400f8456  add     rsp, 8
0x1400f845a  call    loc_1400F844D
0x1400f845f  add     rsp, 8
0x1400f8463  call    loc_1400F8456
0x1400f8468  add     rsp, 8
0x1400f846c  call    loc_1400F845F
0x1400f8471  add     rsp, 8
0x1400f8475  call    loc_1400F8468
0x1400f847a  add     rsp, 8
0x1400f847e  call    loc_1400F8471
0x1400f8483  add     rsp, 8
0x1400f8487  call    loc_1400F847A
0x1400f848c  add     rsp, 8
0x1400f8490  call    loc_1400F8483
0x1400f8495  add     rsp, 8
0x1400f8499  call    loc_1400F848C
0x1400f849e  add     rsp, 8
0x1400f84a2  call    loc_1400F8495
0x1400f84a7  add     rsp, 8
0x1400f84ab  call    loc_1400F849E
0x1400f84b0  add     rsp, 8
0x1400f84b4  call    loc_1400F84A7
0x1400f84b9  add     rsp, 8
0x1400f84bd  movzx   eax, word ptr gs:0BA2h
0x1400f84c6  cmp     gs:0BA8h, ax
0x1400f84cf  jz      short loc_1400F84E3
0x1400f84d1  mov     gs:0BA8h, ax
0x1400f84da  mov     ecx, 48h ; 'H'
0x1400f84df  xor     edx, edx
0x1400f84e1  wrmsr
0x1400f84e3  movzx   edx, byte ptr gs:0BA0h
0x1400f84ec  test    edx, 4
0x1400f84f2  jz      short loc_1400F8502
0x1400f84f4  mov     eax, 1
0x1400f84f9  xor     edx, edx
0x1400f84fb  mov     ecx, 49h ; 'I'
0x1400f8500  wrmsr
0x1400f8502  test    byte ptr gs:0BA0h, 20h
0x1400f850b  jz      short loc_1400F8512
0x1400f850d  call    SkiFlushBhb
0x1400f8512  lfence
0x1400f8515  test    r10, r10
0x1400f8518  mov     qword ptr [rbp+80h], 0
0x1400f8523  jz      short loc_1400F8535
0x1400f8525  bt      dword ptr [r10+0ACh], 5
0x1400f852e  jnb     short loc_1400F8535
0x1400f8530  call    SkiSaveDebugRegisterStateForNmi
0x1400f8535  lfence
0x1400f8538  cld
0x1400f8539  stmxcsr dword ptr [rbp-54h]
0x1400f853d  ldmxcsr cs:SkiInitialMxCsr
0x1400f8544  movaps  xmmword ptr [rbp-10h], xmm0
0x1400f8548  movaps  xmmword ptr [rbp+0], xmm1
0x1400f854c  movaps  xmmword ptr [rbp+10h], xmm2
0x1400f8550  movaps  xmmword ptr [rbp+20h], xmm3
0x1400f8554  movaps  xmmword ptr [rbp+30h], xmm4
0x1400f8558  movaps  xmmword ptr [rbp+40h], xmm5
0x1400f855c  test    qword ptr [rbp+0F8h], 200h
0x1400f8567  jz      short loc_1400F856A
0x1400f8569  sti
0x1400f856a  mov     ecx, 80000003h
0x1400f856f  mov     edx, 1
0x1400f8574  mov     r9, [rbp-50h]
0x1400f8578  mov     r8, [rbp+0E8h]
0x1400f857f  call    KiExceptionDispatch
0x1400f8584  nop
0x1400f8585  retn
```
