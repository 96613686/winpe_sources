# __DllMainCRTStartup

- ea: `0x1800012c4`
- end: `0x1800014d0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001280`

## callees

- `0x180001050`
- `0x1800012c4`
- `0x180001546`
- `0x180001718`
- `0x180002e00`

## pseudocode

```c
__int64 __fastcall _DllMainCRTStartup(HINSTANCE hinstDLL, __int64 fdwReason, void *a3)
{
  DWORD v3; // edi
  unsigned int v5; // ebx

  v3 = fdwReason;
  v5 = 1;
  if ( (unsigned int)fdwReason <= 1 )
    _native_dllmain_reason = fdwReason;
  if ( (_DWORD)fdwReason || dword_1800070E0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_1800070E4 = 1;
      v5 = pRawDllMain(hinstDLL, fdwReason, a3);
    }
    if ( v5 )
    {
      v5 = CRT_INIT(hinstDLL, v3, a3);
      if ( v5 )
      {
LABEL_13:
        v5 = DllMain(hinstDLL, v3, a3);
        if ( v3 == 1 && !v5 )
        {
          DllMain(hinstDLL, 0, 0);
          CRT_INIT(hinstDLL, 0, 0);
          if ( pRawDllMain )
            pRawDllMain(hinstDLL, 0, 0);
        }
        if ( !v3 || v3 == 3 )
        {
          v5 = CRT_INIT(hinstDLL, v3, a3);
          if ( pRawDllMain )
          {
            if ( dword_1800070E4 )
              v5 = pRawDllMain(hinstDLL, v3, a3);
          }
        }
      }
    }
  }
  else
  {
    v5 = 0;
  }
  if ( v3 <= 1 )
    _native_dllmain_reason = -1;
  return v5;
}

```

## disassembly

```asm
0x1800012c4  mov     [rsp+lpvReserved], r8
0x1800012c9  mov     [rsp+arg_8], edx
0x1800012cd  mov     [rsp+arg_0], rcx
0x1800012d2  push    rbx
0x1800012d3  push    rsi
0x1800012d4  push    rdi
0x1800012d5  sub     rsp, 0F0h
0x1800012dc  mov     edi, edx
0x1800012de  mov     rsi, rcx
0x1800012e1  mov     ebx, 1
0x1800012e6  cmp     edx, ebx
0x1800012e8  ja      short loc_1800012F0
0x1800012ea  mov     cs:__native_dllmain_reason, edx
0x1800012f0  test    edx, edx
0x1800012f2  jnz     short loc_180001307
0x1800012f4  cmp     cs:dword_1800070E0, edx
0x1800012fa  jnz     short loc_180001307
0x1800012fc  xor     ebx, ebx
0x1800012fe  mov     [rsp+108h+var_E8], ebx
0x180001302  jmp     loc_1800014B4
0x180001307  lea     eax, [rdx-1]
0x18000130a  cmp     eax, 1
0x18000130d  ja      loc_180001394
0x180001313  mov     rax, cs:_pRawDllMain
0x18000131a  test    rax, rax
0x18000131d  jz      short loc_180001355
0x18000131f  cmp     edx, 1
0x180001322  jnz     short loc_18000132A
0x180001324  mov     cs:dword_1800070E4, edx
0x18000132a  mov     r8, [rsp+108h+lpvReserved]
0x180001332  call    cs:__guard_dispatch_icall_fptr
0x180001338  mov     ebx, eax
0x18000133a  mov     [rsp+108h+var_E8], eax
0x18000133e  jmp     short loc_180001355
0x180001340  xor     ebx, ebx
0x180001342  mov     [rsp+108h+var_E8], ebx
0x180001346  mov     edi, [rsp+108h+arg_8]
0x18000134d  mov     rsi, [rsp+108h+arg_0]
0x180001355  test    ebx, ebx
0x180001357  jz      loc_1800014B4
0x18000135d  mov     r8, [rsp+108h+lpvReserved]
0x180001365  mov     edx, edi
0x180001367  mov     rcx, rsi
0x18000136a  call    _CRT_INIT
0x18000136f  mov     ebx, eax
0x180001371  mov     [rsp+108h+var_E8], eax
0x180001375  jmp     short loc_18000138C
0x180001377  xor     ebx, ebx
0x180001379  mov     [rsp+108h+var_E8], ebx
0x18000137d  mov     edi, [rsp+108h+arg_8]
0x180001384  mov     rsi, [rsp+108h+arg_0]
0x18000138c  test    ebx, ebx
0x18000138e  jz      loc_1800014B4
0x180001394  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000139c  mov     edx, edi; fdwReason
0x18000139e  mov     rcx, rsi; hinstDLL
0x1800013a1  call    DllMain
0x1800013a6  mov     ebx, eax
0x1800013a8  mov     [rsp+108h+var_E8], eax
0x1800013ac  jmp     short loc_1800013C3
0x1800013ae  xor     ebx, ebx
0x1800013b0  mov     [rsp+108h+var_E8], ebx
0x1800013b4  mov     edi, [rsp+108h+arg_8]
0x1800013bb  mov     rsi, [rsp+108h+arg_0]
0x1800013c3  cmp     edi, 1
0x1800013c6  jnz     short loc_18000143F
0x1800013c8  test    ebx, ebx
0x1800013ca  jnz     short loc_18000143F
0x1800013cc  xor     r8d, r8d; lpvReserved
0x1800013cf  xor     edx, edx; fdwReason
0x1800013d1  mov     rcx, rsi; hinstDLL
0x1800013d4  call    DllMain
0x1800013d9  jmp     short loc_1800013EE
0x1800013db  mov     edi, [rsp+108h+arg_8]
0x1800013e2  mov     rsi, [rsp+108h+arg_0]
0x1800013ea  mov     ebx, [rsp+108h+var_E8]
0x1800013ee  xor     r8d, r8d
0x1800013f1  xor     edx, edx
0x1800013f3  mov     rcx, rsi
0x1800013f6  call    _CRT_INIT
0x1800013fb  jmp     short loc_180001410
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  mov     ebx, [rsp+108h+var_E8]
0x180001410  mov     rax, cs:_pRawDllMain
0x180001417  test    rax, rax
0x18000141a  jz      short loc_18000143F
0x18000141c  xor     r8d, r8d
0x18000141f  xor     edx, edx
0x180001421  mov     rcx, rsi
0x180001424  call    cs:__guard_dispatch_icall_fptr
0x18000142a  jmp     short loc_18000143F
0x18000142c  mov     edi, [rsp+108h+arg_8]
0x180001433  mov     rsi, [rsp+108h+arg_0]
0x18000143b  mov     ebx, [rsp+108h+var_E8]
0x18000143f  test    edi, edi
0x180001441  jz      short loc_180001448
0x180001443  cmp     edi, 3
0x180001446  jnz     short loc_1800014B4
0x180001448  mov     r8, [rsp+108h+lpvReserved]
0x180001450  mov     edx, edi
0x180001452  mov     rcx, rsi
0x180001455  call    _CRT_INIT
0x18000145a  mov     ebx, eax
0x18000145c  mov     [rsp+108h+var_E8], eax
0x180001460  jmp     short loc_180001477
0x180001462  xor     ebx, ebx
0x180001464  mov     [rsp+108h+var_E8], ebx
0x180001468  mov     edi, [rsp+108h+arg_8]
0x18000146f  mov     rsi, [rsp+108h+arg_0]
0x180001477  mov     rax, cs:_pRawDllMain
0x18000147e  test    rax, rax
0x180001481  jz      short loc_1800014B4
0x180001483  cmp     cs:dword_1800070E4, 0
0x18000148a  jz      short loc_1800014B4
0x18000148c  mov     r8, [rsp+108h+lpvReserved]
0x180001494  mov     edx, edi
0x180001496  mov     rcx, rsi
0x180001499  call    cs:__guard_dispatch_icall_fptr
0x18000149f  mov     ebx, eax
0x1800014a1  mov     [rsp+108h+var_E8], eax
0x1800014a5  jmp     short loc_1800014B4
0x1800014a7  xor     ebx, ebx
0x1800014a9  mov     [rsp+108h+var_E8], ebx
0x1800014ad  mov     edi, [rsp+108h+arg_8]
0x1800014b4  cmp     edi, 1
0x1800014b7  ja      short loc_1800014C3
0x1800014b9  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x1800014c3  mov     eax, ebx
0x1800014c5  add     rsp, 0F0h
0x1800014cc  pop     rdi
0x1800014cd  pop     rsi
0x1800014ce  pop     rbx
0x1800014cf  retn
0x180002e70  push    rbp
0x180002e72  sub     rsp, 20h
0x180002e76  mov     rbp, rdx
0x180002e79  mov     rax, [rcx]
0x180002e7c  mov     edx, [rax]
0x180002e7e  mov     [rbp+0A8h], rcx
0x180002e85  mov     [rbp+28h], edx
0x180002e88  mov     eax, [rbp+28h]
0x180002e8b  cmp     eax, 0E06D7363h
0x180002e90  jnz     short loc_180002EA6
0x180002e92  mov     rdx, [rbp+0A8h]
0x180002e99  mov     ecx, [rbp+28h]
0x180002e9c  call    _XcptFilter_0
0x180002ea1  mov     [rbp+30h], eax
0x180002ea4  jmp     short loc_180002EAD
0x180002ea6  mov     dword ptr [rbp+30h], 0
0x180002ead  mov     eax, [rbp+30h]
0x180002eb0  add     rsp, 20h
0x180002eb4  pop     rbp
0x180002eb5  retn
0x180002eb7  push    rbp
0x180002eb9  sub     rsp, 20h
0x180002ebd  mov     rbp, rdx
0x180002ec0  mov     rax, [rcx]
0x180002ec3  mov     edx, [rax]
0x180002ec5  mov     [rbp+0B0h], rcx
0x180002ecc  mov     [rbp+38h], edx
0x180002ecf  mov     eax, [rbp+38h]
0x180002ed2  cmp     eax, 0E06D7363h
0x180002ed7  jnz     short loc_180002EED
0x180002ed9  mov     rdx, [rbp+0B0h]
0x180002ee0  mov     ecx, [rbp+38h]
0x180002ee3  call    _XcptFilter_0
0x180002ee8  mov     [rbp+40h], eax
0x180002eeb  jmp     short loc_180002EF4
0x180002eed  mov     dword ptr [rbp+40h], 0
0x180002ef4  mov     eax, [rbp+40h]
0x180002ef7  add     rsp, 20h
0x180002efb  pop     rbp
0x180002efc  retn
0x180002efe  push    rbp
0x180002f00  sub     rsp, 20h
0x180002f04  mov     rbp, rdx
0x180002f07  mov     rax, [rcx]
0x180002f0a  mov     edx, [rax]
0x180002f0c  mov     [rbp+0B8h], rcx
0x180002f13  mov     [rbp+48h], edx
0x180002f16  mov     eax, [rbp+48h]
0x180002f19  cmp     eax, 0E06D7363h
0x180002f1e  jnz     short loc_180002F34
0x180002f20  mov     rdx, [rbp+0B8h]
0x180002f27  mov     ecx, [rbp+48h]
0x180002f2a  call    _XcptFilter_0
0x180002f2f  mov     [rbp+50h], eax
0x180002f32  jmp     short loc_180002F3B
0x180002f34  mov     dword ptr [rbp+50h], 0
0x180002f3b  mov     eax, [rbp+50h]
0x180002f3e  add     rsp, 20h
0x180002f42  pop     rbp
0x180002f43  retn
0x180002f45  push    rbp
0x180002f47  sub     rsp, 20h
0x180002f4b  mov     rbp, rdx
0x180002f4e  mov     rax, [rcx]
0x180002f51  mov     edx, [rax]
0x180002f53  mov     [rbp+0C0h], rcx
0x180002f5a  mov     [rbp+58h], edx
0x180002f5d  mov     eax, [rbp+58h]
0x180002f60  cmp     eax, 0E06D7363h
0x180002f65  jnz     short loc_180002F7B
0x180002f67  mov     rdx, [rbp+0C0h]
0x180002f6e  mov     ecx, [rbp+58h]
0x180002f71  call    _XcptFilter_0
0x180002f76  mov     [rbp+60h], eax
0x180002f79  jmp     short loc_180002F82
0x180002f7b  mov     dword ptr [rbp+60h], 0
0x180002f82  mov     eax, [rbp+60h]
0x180002f85  add     rsp, 20h
0x180002f89  pop     rbp
0x180002f8a  retn
0x180002f8c  push    rbp
0x180002f8e  sub     rsp, 20h
0x180002f92  mov     rbp, rdx
0x180002f95  mov     rax, [rcx]
0x180002f98  mov     edx, [rax]
0x180002f9a  mov     [rbp+0C8h], rcx
0x180002fa1  mov     [rbp+68h], edx
0x180002fa4  mov     eax, [rbp+68h]
0x180002fa7  cmp     eax, 0E06D7363h
0x180002fac  jnz     short loc_180002FC2
0x180002fae  mov     rdx, [rbp+0C8h]
0x180002fb5  mov     ecx, [rbp+68h]
0x180002fb8  call    _XcptFilter_0
0x180002fbd  mov     [rbp+70h], eax
0x180002fc0  jmp     short loc_180002FC9
0x180002fc2  mov     dword ptr [rbp+70h], 0
0x180002fc9  mov     eax, [rbp+70h]
0x180002fcc  add     rsp, 20h
0x180002fd0  pop     rbp
0x180002fd1  retn
0x180002fd3  push    rbp
0x180002fd5  sub     rsp, 20h
0x180002fd9  mov     rbp, rdx
0x180002fdc  mov     rax, [rcx]
0x180002fdf  mov     edx, [rax]
0x180002fe1  mov     [rbp+0D0h], rcx
0x180002fe8  mov     [rbp+78h], edx
0x180002feb  mov     eax, [rbp+78h]
0x180002fee  cmp     eax, 0E06D7363h
0x180002ff3  jnz     short loc_18000300C
0x180002ff5  mov     rdx, [rbp+0D0h]
0x180002ffc  mov     ecx, [rbp+78h]
0x180002fff  call    _XcptFilter_0
0x180003004  mov     [rbp+80h], eax
0x18000300a  jmp     short loc_180003016
0x18000300c  mov     dword ptr [rbp+80h], 0
0x180003016  mov     eax, [rbp+80h]
0x18000301c  add     rsp, 20h
0x180003020  pop     rbp
0x180003021  retn
0x180003023  push    rbp
0x180003025  sub     rsp, 20h
0x180003029  mov     rbp, rdx
0x18000302c  mov     rax, [rcx]
0x18000302f  mov     edx, [rax]
0x180003031  mov     [rbp+0D8h], rcx
0x180003038  mov     [rbp+88h], edx
0x18000303e  mov     eax, [rbp+88h]
0x180003044  cmp     eax, 0E06D7363h
0x180003049  jnz     short loc_180003065
0x18000304b  mov     rdx, [rbp+0D8h]
0x180003052  mov     ecx, [rbp+88h]
0x180003058  call    _XcptFilter_0
0x18000305d  mov     [rbp+90h], eax
0x180003063  jmp     short loc_18000306F
0x180003065  mov     dword ptr [rbp+90h], 0
0x18000306f  mov     eax, [rbp+90h]
0x180003075  add     rsp, 20h
0x180003079  pop     rbp
0x18000307a  retn
0x18000307c  push    rbp
0x18000307e  sub     rsp, 20h
0x180003082  mov     rbp, rdx
0x180003085  mov     rax, [rcx]
0x180003088  mov     edx, [rax]
0x18000308a  mov     [rbp+0E0h], rcx
0x180003091  mov     [rbp+98h], edx
0x180003097  mov     eax, [rbp+98h]
0x18000309d  cmp     eax, 0E06D7363h
0x1800030a2  jnz     short loc_1800030BE
0x1800030a4  mov     rdx, [rbp+0E0h]
0x1800030ab  mov     ecx, [rbp+98h]
0x1800030b1  call    _XcptFilter_0
0x1800030b6  mov     [rbp+0A0h], eax
0x1800030bc  jmp     short loc_1800030C8
0x1800030be  mov     dword ptr [rbp+0A0h], 0
0x1800030c8  mov     eax, [rbp+0A0h]
0x1800030ce  add     rsp, 20h
0x1800030d2  pop     rbp
0x1800030d3  retn
0x1800030d5  push    rbp
0x1800030d7  sub     rsp, 20h
0x1800030db  mov     rbp, rdx
0x1800030de  cmp     dword ptr [rbp+118h], 1
0x1800030e5  ja      short loc_1800030F1
0x1800030e7  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
