# __DllMainCRTStartup

- ea: `0x180001344`
- end: `0x180001550`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001300`

## callees

- `0x1800010d0`
- `0x180001344`
- `0x180001825`
- `0x180001ac0`
- `0x180006890`

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
  if ( (_DWORD)fdwReason || dword_18000B0A0 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_18000B0A4 = 1;
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
            if ( dword_18000B0A4 )
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
0x180001344  mov     [rsp+lpvReserved], r8
0x180001349  mov     [rsp+arg_8], edx
0x18000134d  mov     [rsp+arg_0], rcx
0x180001352  push    rbx
0x180001353  push    rsi
0x180001354  push    rdi
0x180001355  sub     rsp, 0F0h
0x18000135c  mov     edi, edx
0x18000135e  mov     rsi, rcx
0x180001361  mov     ebx, 1
0x180001366  cmp     edx, ebx
0x180001368  ja      short loc_180001370
0x18000136a  mov     cs:__native_dllmain_reason, edx
0x180001370  test    edx, edx
0x180001372  jnz     short loc_180001387
0x180001374  cmp     cs:dword_18000B0A0, edx
0x18000137a  jnz     short loc_180001387
0x18000137c  xor     ebx, ebx
0x18000137e  mov     [rsp+108h+var_E8], ebx
0x180001382  jmp     loc_180001534
0x180001387  lea     eax, [rdx-1]
0x18000138a  cmp     eax, 1
0x18000138d  ja      loc_180001414
0x180001393  mov     rax, cs:_pRawDllMain
0x18000139a  test    rax, rax
0x18000139d  jz      short loc_1800013D5
0x18000139f  cmp     edx, 1
0x1800013a2  jnz     short loc_1800013AA
0x1800013a4  mov     cs:dword_18000B0A4, edx
0x1800013aa  mov     r8, [rsp+108h+lpvReserved]
0x1800013b2  call    cs:__guard_dispatch_icall_fptr
0x1800013b8  mov     ebx, eax
0x1800013ba  mov     [rsp+108h+var_E8], eax
0x1800013be  jmp     short loc_1800013D5
0x1800013c0  xor     ebx, ebx
0x1800013c2  mov     [rsp+108h+var_E8], ebx
0x1800013c6  mov     edi, [rsp+108h+arg_8]
0x1800013cd  mov     rsi, [rsp+108h+arg_0]
0x1800013d5  test    ebx, ebx
0x1800013d7  jz      loc_180001534
0x1800013dd  mov     r8, [rsp+108h+lpvReserved]
0x1800013e5  mov     edx, edi
0x1800013e7  mov     rcx, rsi
0x1800013ea  call    _CRT_INIT
0x1800013ef  mov     ebx, eax
0x1800013f1  mov     [rsp+108h+var_E8], eax
0x1800013f5  jmp     short loc_18000140C
0x1800013f7  xor     ebx, ebx
0x1800013f9  mov     [rsp+108h+var_E8], ebx
0x1800013fd  mov     edi, [rsp+108h+arg_8]
0x180001404  mov     rsi, [rsp+108h+arg_0]
0x18000140c  test    ebx, ebx
0x18000140e  jz      loc_180001534
0x180001414  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18000141c  mov     edx, edi; fdwReason
0x18000141e  mov     rcx, rsi; hinstDLL
0x180001421  call    DllMain
0x180001426  mov     ebx, eax
0x180001428  mov     [rsp+108h+var_E8], eax
0x18000142c  jmp     short loc_180001443
0x18000142e  xor     ebx, ebx
0x180001430  mov     [rsp+108h+var_E8], ebx
0x180001434  mov     edi, [rsp+108h+arg_8]
0x18000143b  mov     rsi, [rsp+108h+arg_0]
0x180001443  cmp     edi, 1
0x180001446  jnz     short loc_1800014BF
0x180001448  test    ebx, ebx
0x18000144a  jnz     short loc_1800014BF
0x18000144c  xor     r8d, r8d; lpvReserved
0x18000144f  xor     edx, edx; fdwReason
0x180001451  mov     rcx, rsi; hinstDLL
0x180001454  call    DllMain
0x180001459  jmp     short loc_18000146E
0x18000145b  mov     edi, [rsp+108h+arg_8]
0x180001462  mov     rsi, [rsp+108h+arg_0]
0x18000146a  mov     ebx, [rsp+108h+var_E8]
0x18000146e  xor     r8d, r8d
0x180001471  xor     edx, edx
0x180001473  mov     rcx, rsi
0x180001476  call    _CRT_INIT
0x18000147b  jmp     short loc_180001490
0x18000147d  mov     edi, [rsp+108h+arg_8]
0x180001484  mov     rsi, [rsp+108h+arg_0]
0x18000148c  mov     ebx, [rsp+108h+var_E8]
0x180001490  mov     rax, cs:_pRawDllMain
0x180001497  test    rax, rax
0x18000149a  jz      short loc_1800014BF
0x18000149c  xor     r8d, r8d
0x18000149f  xor     edx, edx
0x1800014a1  mov     rcx, rsi
0x1800014a4  call    cs:__guard_dispatch_icall_fptr
0x1800014aa  jmp     short loc_1800014BF
0x1800014ac  mov     edi, [rsp+108h+arg_8]
0x1800014b3  mov     rsi, [rsp+108h+arg_0]
0x1800014bb  mov     ebx, [rsp+108h+var_E8]
0x1800014bf  test    edi, edi
0x1800014c1  jz      short loc_1800014C8
0x1800014c3  cmp     edi, 3
0x1800014c6  jnz     short loc_180001534
0x1800014c8  mov     r8, [rsp+108h+lpvReserved]
0x1800014d0  mov     edx, edi
0x1800014d2  mov     rcx, rsi
0x1800014d5  call    _CRT_INIT
0x1800014da  mov     ebx, eax
0x1800014dc  mov     [rsp+108h+var_E8], eax
0x1800014e0  jmp     short loc_1800014F7
0x1800014e2  xor     ebx, ebx
0x1800014e4  mov     [rsp+108h+var_E8], ebx
0x1800014e8  mov     edi, [rsp+108h+arg_8]
0x1800014ef  mov     rsi, [rsp+108h+arg_0]
0x1800014f7  mov     rax, cs:_pRawDllMain
0x1800014fe  test    rax, rax
0x180001501  jz      short loc_180001534
0x180001503  cmp     cs:dword_18000B0A4, 0
0x18000150a  jz      short loc_180001534
0x18000150c  mov     r8, [rsp+108h+lpvReserved]
0x180001514  mov     edx, edi
0x180001516  mov     rcx, rsi
0x180001519  call    cs:__guard_dispatch_icall_fptr
0x18000151f  mov     ebx, eax
0x180001521  mov     [rsp+108h+var_E8], eax
0x180001525  jmp     short loc_180001534
0x180001527  xor     ebx, ebx
0x180001529  mov     [rsp+108h+var_E8], ebx
0x18000152d  mov     edi, [rsp+108h+arg_8]
0x180001534  cmp     edi, 1
0x180001537  ja      short loc_180001543
0x180001539  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x180001543  mov     eax, ebx
0x180001545  add     rsp, 0F0h
0x18000154c  pop     rdi
0x18000154d  pop     rsi
0x18000154e  pop     rbx
0x18000154f  retn
0x180006900  push    rbp
0x180006902  sub     rsp, 20h
0x180006906  mov     rbp, rdx
0x180006909  mov     rax, [rcx]
0x18000690c  mov     edx, [rax]
0x18000690e  mov     [rbp+0A8h], rcx
0x180006915  mov     [rbp+28h], edx
0x180006918  mov     eax, [rbp+28h]
0x18000691b  cmp     eax, 0E06D7363h
0x180006920  jnz     short loc_180006936
0x180006922  mov     rdx, [rbp+0A8h]
0x180006929  mov     ecx, [rbp+28h]
0x18000692c  call    _XcptFilter_0
0x180006931  mov     [rbp+30h], eax
0x180006934  jmp     short loc_18000693D
0x180006936  mov     dword ptr [rbp+30h], 0
0x18000693d  mov     eax, [rbp+30h]
0x180006940  add     rsp, 20h
0x180006944  pop     rbp
0x180006945  retn
0x180006947  push    rbp
0x180006949  sub     rsp, 20h
0x18000694d  mov     rbp, rdx
0x180006950  mov     rax, [rcx]
0x180006953  mov     edx, [rax]
0x180006955  mov     [rbp+0B0h], rcx
0x18000695c  mov     [rbp+38h], edx
0x18000695f  mov     eax, [rbp+38h]
0x180006962  cmp     eax, 0E06D7363h
0x180006967  jnz     short loc_18000697D
0x180006969  mov     rdx, [rbp+0B0h]
0x180006970  mov     ecx, [rbp+38h]
0x180006973  call    _XcptFilter_0
0x180006978  mov     [rbp+40h], eax
0x18000697b  jmp     short loc_180006984
0x18000697d  mov     dword ptr [rbp+40h], 0
0x180006984  mov     eax, [rbp+40h]
0x180006987  add     rsp, 20h
0x18000698b  pop     rbp
0x18000698c  retn
0x18000698e  push    rbp
0x180006990  sub     rsp, 20h
0x180006994  mov     rbp, rdx
0x180006997  mov     rax, [rcx]
0x18000699a  mov     edx, [rax]
0x18000699c  mov     [rbp+0B8h], rcx
0x1800069a3  mov     [rbp+48h], edx
0x1800069a6  mov     eax, [rbp+48h]
0x1800069a9  cmp     eax, 0E06D7363h
0x1800069ae  jnz     short loc_1800069C4
0x1800069b0  mov     rdx, [rbp+0B8h]
0x1800069b7  mov     ecx, [rbp+48h]
0x1800069ba  call    _XcptFilter_0
0x1800069bf  mov     [rbp+50h], eax
0x1800069c2  jmp     short loc_1800069CB
0x1800069c4  mov     dword ptr [rbp+50h], 0
0x1800069cb  mov     eax, [rbp+50h]
0x1800069ce  add     rsp, 20h
0x1800069d2  pop     rbp
0x1800069d3  retn
0x1800069d5  push    rbp
0x1800069d7  sub     rsp, 20h
0x1800069db  mov     rbp, rdx
0x1800069de  mov     rax, [rcx]
0x1800069e1  mov     edx, [rax]
0x1800069e3  mov     [rbp+0C0h], rcx
0x1800069ea  mov     [rbp+58h], edx
0x1800069ed  mov     eax, [rbp+58h]
0x1800069f0  cmp     eax, 0E06D7363h
0x1800069f5  jnz     short loc_180006A0B
0x1800069f7  mov     rdx, [rbp+0C0h]
0x1800069fe  mov     ecx, [rbp+58h]
0x180006a01  call    _XcptFilter_0
0x180006a06  mov     [rbp+60h], eax
0x180006a09  jmp     short loc_180006A12
0x180006a0b  mov     dword ptr [rbp+60h], 0
0x180006a12  mov     eax, [rbp+60h]
0x180006a15  add     rsp, 20h
0x180006a19  pop     rbp
0x180006a1a  retn
0x180006a1c  push    rbp
0x180006a1e  sub     rsp, 20h
0x180006a22  mov     rbp, rdx
0x180006a25  mov     rax, [rcx]
0x180006a28  mov     edx, [rax]
0x180006a2a  mov     [rbp+0C8h], rcx
0x180006a31  mov     [rbp+68h], edx
0x180006a34  mov     eax, [rbp+68h]
0x180006a37  cmp     eax, 0E06D7363h
0x180006a3c  jnz     short loc_180006A52
0x180006a3e  mov     rdx, [rbp+0C8h]
0x180006a45  mov     ecx, [rbp+68h]
0x180006a48  call    _XcptFilter_0
0x180006a4d  mov     [rbp+70h], eax
0x180006a50  jmp     short loc_180006A59
0x180006a52  mov     dword ptr [rbp+70h], 0
0x180006a59  mov     eax, [rbp+70h]
0x180006a5c  add     rsp, 20h
0x180006a60  pop     rbp
0x180006a61  retn
0x180006a63  push    rbp
0x180006a65  sub     rsp, 20h
0x180006a69  mov     rbp, rdx
0x180006a6c  mov     rax, [rcx]
0x180006a6f  mov     edx, [rax]
0x180006a71  mov     [rbp+0D0h], rcx
0x180006a78  mov     [rbp+78h], edx
0x180006a7b  mov     eax, [rbp+78h]
0x180006a7e  cmp     eax, 0E06D7363h
0x180006a83  jnz     short loc_180006A9C
0x180006a85  mov     rdx, [rbp+0D0h]
0x180006a8c  mov     ecx, [rbp+78h]
0x180006a8f  call    _XcptFilter_0
0x180006a94  mov     [rbp+80h], eax
0x180006a9a  jmp     short loc_180006AA6
0x180006a9c  mov     dword ptr [rbp+80h], 0
0x180006aa6  mov     eax, [rbp+80h]
0x180006aac  add     rsp, 20h
0x180006ab0  pop     rbp
0x180006ab1  retn
0x180006ab3  push    rbp
0x180006ab5  sub     rsp, 20h
0x180006ab9  mov     rbp, rdx
0x180006abc  mov     rax, [rcx]
0x180006abf  mov     edx, [rax]
0x180006ac1  mov     [rbp+0D8h], rcx
0x180006ac8  mov     [rbp+88h], edx
0x180006ace  mov     eax, [rbp+88h]
0x180006ad4  cmp     eax, 0E06D7363h
0x180006ad9  jnz     short loc_180006AF5
0x180006adb  mov     rdx, [rbp+0D8h]
0x180006ae2  mov     ecx, [rbp+88h]
0x180006ae8  call    _XcptFilter_0
0x180006aed  mov     [rbp+90h], eax
0x180006af3  jmp     short loc_180006AFF
0x180006af5  mov     dword ptr [rbp+90h], 0
0x180006aff  mov     eax, [rbp+90h]
0x180006b05  add     rsp, 20h
0x180006b09  pop     rbp
0x180006b0a  retn
0x180006b0c  push    rbp
0x180006b0e  sub     rsp, 20h
0x180006b12  mov     rbp, rdx
0x180006b15  mov     rax, [rcx]
0x180006b18  mov     edx, [rax]
0x180006b1a  mov     [rbp+0E0h], rcx
0x180006b21  mov     [rbp+98h], edx
0x180006b27  mov     eax, [rbp+98h]
0x180006b2d  cmp     eax, 0E06D7363h
0x180006b32  jnz     short loc_180006B4E
0x180006b34  mov     rdx, [rbp+0E0h]
0x180006b3b  mov     ecx, [rbp+98h]
0x180006b41  call    _XcptFilter_0
0x180006b46  mov     [rbp+0A0h], eax
0x180006b4c  jmp     short loc_180006B58
0x180006b4e  mov     dword ptr [rbp+0A0h], 0
0x180006b58  mov     eax, [rbp+0A0h]
0x180006b5e  add     rsp, 20h
0x180006b62  pop     rbp
0x180006b63  retn
0x180006b65  push    rbp
0x180006b67  sub     rsp, 20h
0x180006b6b  mov     rbp, rdx
0x180006b6e  cmp     dword ptr [rbp+118h], 1
0x180006b75  ja      short loc_180006B81
0x180006b77  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
