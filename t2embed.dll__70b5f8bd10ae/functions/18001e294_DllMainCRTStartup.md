# __DllMainCRTStartup

- ea: `0x18001e294`
- end: `0x18001e4a0`
- name: `__DllMainCRTStartup`
- size: `524`
- prototype: `__int64 __fastcall(HINSTANCE hinstDLL, DWORD fdwReason)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18001e250`

## callees

- `0x18001e020`
- `0x18001e294`
- `0x18001e8ac`
- `0x18001ec20`
- `0x18002a5d0`

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
  if ( (_DWORD)fdwReason || dword_180031580 )
  {
    if ( (unsigned int)(fdwReason - 1) > 1 )
      goto LABEL_13;
    if ( pRawDllMain )
    {
      if ( (_DWORD)fdwReason == 1 )
        dword_180031584 = 1;
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
            if ( dword_180031584 )
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
0x18001e294  mov     [rsp+lpvReserved], r8
0x18001e299  mov     [rsp+arg_8], edx
0x18001e29d  mov     [rsp+arg_0], rcx
0x18001e2a2  push    rbx
0x18001e2a3  push    rsi
0x18001e2a4  push    rdi
0x18001e2a5  sub     rsp, 0F0h
0x18001e2ac  mov     edi, edx
0x18001e2ae  mov     rsi, rcx
0x18001e2b1  mov     ebx, 1
0x18001e2b6  cmp     edx, ebx
0x18001e2b8  ja      short loc_18001E2C0
0x18001e2ba  mov     cs:__native_dllmain_reason, edx
0x18001e2c0  test    edx, edx
0x18001e2c2  jnz     short loc_18001E2D7
0x18001e2c4  cmp     cs:dword_180031580, edx
0x18001e2ca  jnz     short loc_18001E2D7
0x18001e2cc  xor     ebx, ebx
0x18001e2ce  mov     [rsp+108h+var_E8], ebx
0x18001e2d2  jmp     loc_18001E484
0x18001e2d7  lea     eax, [rdx-1]
0x18001e2da  cmp     eax, 1
0x18001e2dd  ja      loc_18001E364
0x18001e2e3  mov     rax, cs:_pRawDllMain
0x18001e2ea  test    rax, rax
0x18001e2ed  jz      short loc_18001E325
0x18001e2ef  cmp     edx, 1
0x18001e2f2  jnz     short loc_18001E2FA
0x18001e2f4  mov     cs:dword_180031584, edx
0x18001e2fa  mov     r8, [rsp+108h+lpvReserved]
0x18001e302  call    cs:__guard_dispatch_icall_fptr
0x18001e308  mov     ebx, eax
0x18001e30a  mov     [rsp+108h+var_E8], eax
0x18001e30e  jmp     short loc_18001E325
0x18001e310  xor     ebx, ebx
0x18001e312  mov     [rsp+108h+var_E8], ebx
0x18001e316  mov     edi, [rsp+108h+arg_8]
0x18001e31d  mov     rsi, [rsp+108h+arg_0]
0x18001e325  test    ebx, ebx
0x18001e327  jz      loc_18001E484
0x18001e32d  mov     r8, [rsp+108h+lpvReserved]
0x18001e335  mov     edx, edi
0x18001e337  mov     rcx, rsi
0x18001e33a  call    _CRT_INIT
0x18001e33f  mov     ebx, eax
0x18001e341  mov     [rsp+108h+var_E8], eax
0x18001e345  jmp     short loc_18001E35C
0x18001e347  xor     ebx, ebx
0x18001e349  mov     [rsp+108h+var_E8], ebx
0x18001e34d  mov     edi, [rsp+108h+arg_8]
0x18001e354  mov     rsi, [rsp+108h+arg_0]
0x18001e35c  test    ebx, ebx
0x18001e35e  jz      loc_18001E484
0x18001e364  mov     r8, [rsp+108h+lpvReserved]; lpvReserved
0x18001e36c  mov     edx, edi; fdwReason
0x18001e36e  mov     rcx, rsi; hinstDLL
0x18001e371  call    DllMain
0x18001e376  mov     ebx, eax
0x18001e378  mov     [rsp+108h+var_E8], eax
0x18001e37c  jmp     short loc_18001E393
0x18001e37e  xor     ebx, ebx
0x18001e380  mov     [rsp+108h+var_E8], ebx
0x18001e384  mov     edi, [rsp+108h+arg_8]
0x18001e38b  mov     rsi, [rsp+108h+arg_0]
0x18001e393  cmp     edi, 1
0x18001e396  jnz     short loc_18001E40F
0x18001e398  test    ebx, ebx
0x18001e39a  jnz     short loc_18001E40F
0x18001e39c  xor     r8d, r8d; lpvReserved
0x18001e39f  xor     edx, edx; fdwReason
0x18001e3a1  mov     rcx, rsi; hinstDLL
0x18001e3a4  call    DllMain
0x18001e3a9  jmp     short loc_18001E3BE
0x18001e3ab  mov     edi, [rsp+108h+arg_8]
0x18001e3b2  mov     rsi, [rsp+108h+arg_0]
0x18001e3ba  mov     ebx, [rsp+108h+var_E8]
0x18001e3be  xor     r8d, r8d
0x18001e3c1  xor     edx, edx
0x18001e3c3  mov     rcx, rsi
0x18001e3c6  call    _CRT_INIT
0x18001e3cb  jmp     short loc_18001E3E0
0x18001e3cd  mov     edi, [rsp+108h+arg_8]
0x18001e3d4  mov     rsi, [rsp+108h+arg_0]
0x18001e3dc  mov     ebx, [rsp+108h+var_E8]
0x18001e3e0  mov     rax, cs:_pRawDllMain
0x18001e3e7  test    rax, rax
0x18001e3ea  jz      short loc_18001E40F
0x18001e3ec  xor     r8d, r8d
0x18001e3ef  xor     edx, edx
0x18001e3f1  mov     rcx, rsi
0x18001e3f4  call    cs:__guard_dispatch_icall_fptr
0x18001e3fa  jmp     short loc_18001E40F
0x18001e3fc  mov     edi, [rsp+108h+arg_8]
0x18001e403  mov     rsi, [rsp+108h+arg_0]
0x18001e40b  mov     ebx, [rsp+108h+var_E8]
0x18001e40f  test    edi, edi
0x18001e411  jz      short loc_18001E418
0x18001e413  cmp     edi, 3
0x18001e416  jnz     short loc_18001E484
0x18001e418  mov     r8, [rsp+108h+lpvReserved]
0x18001e420  mov     edx, edi
0x18001e422  mov     rcx, rsi
0x18001e425  call    _CRT_INIT
0x18001e42a  mov     ebx, eax
0x18001e42c  mov     [rsp+108h+var_E8], eax
0x18001e430  jmp     short loc_18001E447
0x18001e432  xor     ebx, ebx
0x18001e434  mov     [rsp+108h+var_E8], ebx
0x18001e438  mov     edi, [rsp+108h+arg_8]
0x18001e43f  mov     rsi, [rsp+108h+arg_0]
0x18001e447  mov     rax, cs:_pRawDllMain
0x18001e44e  test    rax, rax
0x18001e451  jz      short loc_18001E484
0x18001e453  cmp     cs:dword_180031584, 0
0x18001e45a  jz      short loc_18001E484
0x18001e45c  mov     r8, [rsp+108h+lpvReserved]
0x18001e464  mov     edx, edi
0x18001e466  mov     rcx, rsi
0x18001e469  call    cs:__guard_dispatch_icall_fptr
0x18001e46f  mov     ebx, eax
0x18001e471  mov     [rsp+108h+var_E8], eax
0x18001e475  jmp     short loc_18001E484
0x18001e477  xor     ebx, ebx
0x18001e479  mov     [rsp+108h+var_E8], ebx
0x18001e47d  mov     edi, [rsp+108h+arg_8]
0x18001e484  cmp     edi, 1
0x18001e487  ja      short loc_18001E493
0x18001e489  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
0x18001e493  mov     eax, ebx
0x18001e495  add     rsp, 0F0h
0x18001e49c  pop     rdi
0x18001e49d  pop     rsi
0x18001e49e  pop     rbx
0x18001e49f  retn
0x18002a6a0  push    rbp
0x18002a6a2  sub     rsp, 20h
0x18002a6a6  mov     rbp, rdx
0x18002a6a9  mov     rax, [rcx]
0x18002a6ac  mov     edx, [rax]
0x18002a6ae  mov     [rbp+0A8h], rcx
0x18002a6b5  mov     [rbp+28h], edx
0x18002a6b8  mov     eax, [rbp+28h]
0x18002a6bb  cmp     eax, 0E06D7363h
0x18002a6c0  jnz     short loc_18002A6D6
0x18002a6c2  mov     rdx, [rbp+0A8h]
0x18002a6c9  mov     ecx, [rbp+28h]
0x18002a6cc  call    _XcptFilter_0
0x18002a6d1  mov     [rbp+30h], eax
0x18002a6d4  jmp     short loc_18002A6DD
0x18002a6d6  mov     dword ptr [rbp+30h], 0
0x18002a6dd  mov     eax, [rbp+30h]
0x18002a6e0  add     rsp, 20h
0x18002a6e4  pop     rbp
0x18002a6e5  retn
0x18002a6e7  push    rbp
0x18002a6e9  sub     rsp, 20h
0x18002a6ed  mov     rbp, rdx
0x18002a6f0  mov     rax, [rcx]
0x18002a6f3  mov     edx, [rax]
0x18002a6f5  mov     [rbp+0B0h], rcx
0x18002a6fc  mov     [rbp+38h], edx
0x18002a6ff  mov     eax, [rbp+38h]
0x18002a702  cmp     eax, 0E06D7363h
0x18002a707  jnz     short loc_18002A71D
0x18002a709  mov     rdx, [rbp+0B0h]
0x18002a710  mov     ecx, [rbp+38h]
0x18002a713  call    _XcptFilter_0
0x18002a718  mov     [rbp+40h], eax
0x18002a71b  jmp     short loc_18002A724
0x18002a71d  mov     dword ptr [rbp+40h], 0
0x18002a724  mov     eax, [rbp+40h]
0x18002a727  add     rsp, 20h
0x18002a72b  pop     rbp
0x18002a72c  retn
0x18002a72e  push    rbp
0x18002a730  sub     rsp, 20h
0x18002a734  mov     rbp, rdx
0x18002a737  mov     rax, [rcx]
0x18002a73a  mov     edx, [rax]
0x18002a73c  mov     [rbp+0B8h], rcx
0x18002a743  mov     [rbp+48h], edx
0x18002a746  mov     eax, [rbp+48h]
0x18002a749  cmp     eax, 0E06D7363h
0x18002a74e  jnz     short loc_18002A764
0x18002a750  mov     rdx, [rbp+0B8h]
0x18002a757  mov     ecx, [rbp+48h]
0x18002a75a  call    _XcptFilter_0
0x18002a75f  mov     [rbp+50h], eax
0x18002a762  jmp     short loc_18002A76B
0x18002a764  mov     dword ptr [rbp+50h], 0
0x18002a76b  mov     eax, [rbp+50h]
0x18002a76e  add     rsp, 20h
0x18002a772  pop     rbp
0x18002a773  retn
0x18002a775  push    rbp
0x18002a777  sub     rsp, 20h
0x18002a77b  mov     rbp, rdx
0x18002a77e  mov     rax, [rcx]
0x18002a781  mov     edx, [rax]
0x18002a783  mov     [rbp+0C0h], rcx
0x18002a78a  mov     [rbp+58h], edx
0x18002a78d  mov     eax, [rbp+58h]
0x18002a790  cmp     eax, 0E06D7363h
0x18002a795  jnz     short loc_18002A7AB
0x18002a797  mov     rdx, [rbp+0C0h]
0x18002a79e  mov     ecx, [rbp+58h]
0x18002a7a1  call    _XcptFilter_0
0x18002a7a6  mov     [rbp+60h], eax
0x18002a7a9  jmp     short loc_18002A7B2
0x18002a7ab  mov     dword ptr [rbp+60h], 0
0x18002a7b2  mov     eax, [rbp+60h]
0x18002a7b5  add     rsp, 20h
0x18002a7b9  pop     rbp
0x18002a7ba  retn
0x18002a7bc  push    rbp
0x18002a7be  sub     rsp, 20h
0x18002a7c2  mov     rbp, rdx
0x18002a7c5  mov     rax, [rcx]
0x18002a7c8  mov     edx, [rax]
0x18002a7ca  mov     [rbp+0C8h], rcx
0x18002a7d1  mov     [rbp+68h], edx
0x18002a7d4  mov     eax, [rbp+68h]
0x18002a7d7  cmp     eax, 0E06D7363h
0x18002a7dc  jnz     short loc_18002A7F2
0x18002a7de  mov     rdx, [rbp+0C8h]
0x18002a7e5  mov     ecx, [rbp+68h]
0x18002a7e8  call    _XcptFilter_0
0x18002a7ed  mov     [rbp+70h], eax
0x18002a7f0  jmp     short loc_18002A7F9
0x18002a7f2  mov     dword ptr [rbp+70h], 0
0x18002a7f9  mov     eax, [rbp+70h]
0x18002a7fc  add     rsp, 20h
0x18002a800  pop     rbp
0x18002a801  retn
0x18002a803  push    rbp
0x18002a805  sub     rsp, 20h
0x18002a809  mov     rbp, rdx
0x18002a80c  mov     rax, [rcx]
0x18002a80f  mov     edx, [rax]
0x18002a811  mov     [rbp+0D0h], rcx
0x18002a818  mov     [rbp+78h], edx
0x18002a81b  mov     eax, [rbp+78h]
0x18002a81e  cmp     eax, 0E06D7363h
0x18002a823  jnz     short loc_18002A83C
0x18002a825  mov     rdx, [rbp+0D0h]
0x18002a82c  mov     ecx, [rbp+78h]
0x18002a82f  call    _XcptFilter_0
0x18002a834  mov     [rbp+80h], eax
0x18002a83a  jmp     short loc_18002A846
0x18002a83c  mov     dword ptr [rbp+80h], 0
0x18002a846  mov     eax, [rbp+80h]
0x18002a84c  add     rsp, 20h
0x18002a850  pop     rbp
0x18002a851  retn
0x18002a853  push    rbp
0x18002a855  sub     rsp, 20h
0x18002a859  mov     rbp, rdx
0x18002a85c  mov     rax, [rcx]
0x18002a85f  mov     edx, [rax]
0x18002a861  mov     [rbp+0D8h], rcx
0x18002a868  mov     [rbp+88h], edx
0x18002a86e  mov     eax, [rbp+88h]
0x18002a874  cmp     eax, 0E06D7363h
0x18002a879  jnz     short loc_18002A895
0x18002a87b  mov     rdx, [rbp+0D8h]
0x18002a882  mov     ecx, [rbp+88h]
0x18002a888  call    _XcptFilter_0
0x18002a88d  mov     [rbp+90h], eax
0x18002a893  jmp     short loc_18002A89F
0x18002a895  mov     dword ptr [rbp+90h], 0
0x18002a89f  mov     eax, [rbp+90h]
0x18002a8a5  add     rsp, 20h
0x18002a8a9  pop     rbp
0x18002a8aa  retn
0x18002a8ac  push    rbp
0x18002a8ae  sub     rsp, 20h
0x18002a8b2  mov     rbp, rdx
0x18002a8b5  mov     rax, [rcx]
0x18002a8b8  mov     edx, [rax]
0x18002a8ba  mov     [rbp+0E0h], rcx
0x18002a8c1  mov     [rbp+98h], edx
0x18002a8c7  mov     eax, [rbp+98h]
0x18002a8cd  cmp     eax, 0E06D7363h
0x18002a8d2  jnz     short loc_18002A8EE
0x18002a8d4  mov     rdx, [rbp+0E0h]
0x18002a8db  mov     ecx, [rbp+98h]
0x18002a8e1  call    _XcptFilter_0
0x18002a8e6  mov     [rbp+0A0h], eax
0x18002a8ec  jmp     short loc_18002A8F8
0x18002a8ee  mov     dword ptr [rbp+0A0h], 0
0x18002a8f8  mov     eax, [rbp+0A0h]
0x18002a8fe  add     rsp, 20h
0x18002a902  pop     rbp
0x18002a903  retn
0x18002a905  push    rbp
0x18002a907  sub     rsp, 20h
0x18002a90b  mov     rbp, rdx
0x18002a90e  cmp     dword ptr [rbp+118h], 1
0x18002a915  ja      short loc_18002A921
0x18002a917  mov     cs:__native_dllmain_reason, 0FFFFFFFFh
  ... truncated ...
```
