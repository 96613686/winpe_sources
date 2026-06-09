# KiSystemService

- ea: `0x1400f85c0`
- end: `0x1400f8866`
- name: `KiSystemService`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x140100b40`

## callees

- `0x1400f07d0`
- `0x1400f30c0`
- `0x1400f4040`
- `0x1400f85c0`
- `0x1400f9040`

## pseudocode

```c

```

## disassembly

```asm
0x1400f85c0  sub     rsp, 8
0x1400f85c4  push    rbp
0x1400f85c5  sub     rsp, 158h
0x1400f85cc  lea     rbp, [rsp+80h]
0x1400f85d4  mov     [rbp+0E8h+var_13D], 1
0x1400f85d8  mov     [rbp+0E8h+var_138], rax
0x1400f85dc  mov     [rbp+0E8h+var_130], rcx
0x1400f85e0  mov     [rbp+0E8h+var_128], rdx
0x1400f85e4  mov     [rbp+0E8h+var_120], r8
0x1400f85e8  mov     [rbp+0E8h+var_118], r9
0x1400f85ec  mov     [rbp+0E8h+var_110], r10
0x1400f85f0  mov     [rbp+0E8h+var_108], r11
0x1400f85f4  test    cs:SkeSmapSupported, 1
0x1400f85fb  jz      short loc_1400F8600
0x1400f85fd  clac
0x1400f8600  test    [rbp+0E8h+arg_0], 1
0x1400f8607  jz      loc_1400F87E4
0x1400f860d  test    cs:SkiKvaShadow, 1
0x1400f8614  jnz     short loc_1400F8619
0x1400f8616  swapgs
0x1400f8619  lfence
0x1400f861c  mov     r10, gs:8
0x1400f8625  or      dword ptr gs:0CCh, 2
0x1400f862e  test    byte ptr gs:0BA0h, 1
0x1400f8637  jz      loc_1400F87C1
0x1400f863d  test    byte ptr gs:0BA0h, 8
0x1400f8646  jz      loc_1400F876C
0x1400f864c  call    loc_1400F875F
0x1400f8651  add     rsp, 8
0x1400f8655  call    loc_1400F8768
0x1400f865a  add     rsp, 8
0x1400f865e  call    loc_1400F8651
0x1400f8663  add     rsp, 8
0x1400f8667  call    loc_1400F865A
0x1400f866c  add     rsp, 8
0x1400f8670  call    loc_1400F8663
0x1400f8675  add     rsp, 8
0x1400f8679  call    loc_1400F866C
0x1400f867e  add     rsp, 8
0x1400f8682  call    loc_1400F8675
0x1400f8687  add     rsp, 8
0x1400f868b  call    loc_1400F867E
0x1400f8690  add     rsp, 8
0x1400f8694  call    loc_1400F8687
0x1400f8699  add     rsp, 8
0x1400f869d  call    loc_1400F8690
0x1400f86a2  add     rsp, 8
0x1400f86a6  call    loc_1400F8699
0x1400f86ab  add     rsp, 8
0x1400f86af  call    loc_1400F86A2
0x1400f86b4  add     rsp, 8
0x1400f86b8  call    loc_1400F86AB
0x1400f86bd  add     rsp, 8
0x1400f86c1  call    loc_1400F86B4
0x1400f86c6  add     rsp, 8
0x1400f86ca  call    loc_1400F86BD
0x1400f86cf  add     rsp, 8
0x1400f86d3  call    loc_1400F86C6
0x1400f86d8  add     rsp, 8
0x1400f86dc  call    loc_1400F86CF
0x1400f86e1  add     rsp, 8
0x1400f86e5  call    loc_1400F86D8
0x1400f86ea  add     rsp, 8
0x1400f86ee  call    loc_1400F86E1
0x1400f86f3  add     rsp, 8
0x1400f86f7  call    loc_1400F86EA
0x1400f86fc  add     rsp, 8
0x1400f8700  call    loc_1400F86F3
0x1400f8705  add     rsp, 8
0x1400f8709  call    loc_1400F86FC
0x1400f870e  add     rsp, 8
0x1400f8712  call    loc_1400F8705
0x1400f8717  add     rsp, 8
0x1400f871b  call    loc_1400F870E
0x1400f8720  add     rsp, 8
0x1400f8724  call    loc_1400F8717
0x1400f8729  add     rsp, 8
0x1400f872d  call    loc_1400F8720
0x1400f8732  add     rsp, 8
0x1400f8736  call    loc_1400F8729
0x1400f873b  add     rsp, 8
0x1400f873f  call    loc_1400F8732
0x1400f8744  add     rsp, 8
0x1400f8748  call    loc_1400F873B
0x1400f874d  add     rsp, 8
0x1400f8751  call    loc_1400F8744
0x1400f8756  add     rsp, 8
0x1400f875a  call    loc_1400F874D
0x1400f875f  add     rsp, 8
0x1400f8763  call    loc_1400F8756
0x1400f8768  add     rsp, 8
0x1400f876c  movzx   eax, word ptr gs:0BA2h
0x1400f8775  cmp     gs:0BA8h, ax
0x1400f877e  jz      short loc_1400F8792
0x1400f8780  mov     gs:0BA8h, ax
0x1400f8789  mov     ecx, 48h ; 'H'
0x1400f878e  xor     edx, edx
0x1400f8790  wrmsr
0x1400f8792  movzx   edx, byte ptr gs:0BA0h
0x1400f879b  test    edx, 4
0x1400f87a1  jz      short loc_1400F87B1
0x1400f87a3  mov     eax, 1
0x1400f87a8  xor     edx, edx
0x1400f87aa  mov     ecx, 49h ; 'I'
0x1400f87af  wrmsr
0x1400f87b1  test    byte ptr gs:0BA0h, 20h
0x1400f87ba  jz      short loc_1400F87C1
0x1400f87bc  call    SkiFlushBhb
0x1400f87c1  lfence
0x1400f87c4  test    r10, r10
0x1400f87c7  mov     [rbp+0E8h+var_68], 0
0x1400f87d2  jz      short loc_1400F87E4
0x1400f87d4  bt      dword ptr [r10+0ACh], 5
0x1400f87dd  jnb     short loc_1400F87E4
0x1400f87df  call    SkiSaveDebugRegisterStateForNmi
0x1400f87e4  lfence
0x1400f87e7  cld
0x1400f87e8  stmxcsr [rbp+0E8h+var_13C]
0x1400f87ec  ldmxcsr cs:SkiInitialMxCsr
0x1400f87f3  movaps  [rbp+0E8h+var_F8], xmm0
0x1400f87f7  movaps  [rbp+0E8h+var_E8], xmm1
0x1400f87fb  movaps  [rbp+0E8h+var_D8], xmm2
0x1400f87ff  movaps  [rbp+0E8h+var_C8], xmm3
0x1400f8803  movaps  [rbp+0E8h+var_B8], xmm4
0x1400f8807  movaps  [rbp+0E8h+var_A8], xmm5
0x1400f880b  test    [rbp+0E8h+arg_8], 200h
0x1400f8816  jz      short loc_1400F8819
0x1400f8818  sti
0x1400f8819  mov     r10, gs:8
0x1400f8822  test    dword ptr [r10+0ACh], 800h
0x1400f882d  jz      short loc_1400F8851
0x1400f882f  mov     [rbp+0E8h+var_28], rbx
0x1400f8836  mov     [rbp+0E8h+var_18], rsi
0x1400f883d  mov     [rbp+0E8h+var_20], rdi
0x1400f8844  mov     edx, dword ptr [rbp+0E8h+var_138]
0x1400f8847  lea     rcx, [rbp+0E8h+var_168]
0x1400f884b  call    SkpsDispatchBasicEnclaveCall
0x1400f8850  nop
0x1400f8851  mov     ecx, 10000002h
0x1400f8856  xor     edx, edx
0x1400f8858  mov     r8, [rbp+0E8h]
0x1400f885f  call    KiExceptionDispatch
0x1400f8864  nop
0x1400f8865  retn
```
