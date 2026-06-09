# XWRegisterPageWithPage

- ea: `0x18000b200`
- end: `0x18000b333`
- name: `XWRegisterPageWithPage`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b200`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b263`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b263`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b220`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b220`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b2ed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b2ed`

## pseudocode

```c
__int64 __fastcall XWRegisterPageWithPage(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, __int64 a7)
{
  HRESULT v11; // eax
  HRESULT v12; // ebx
  HRESULT v13; // edi
  LPVOID ppv; // [rsp+50h] [rbp-48h] BYREF

  v11 = CoInitializeEx(0, 6u);
  v12 = 0;
  v13 = v11;
  if ( v11 != -2147417850 )
    v12 = v11;
  if ( v12 >= 0 )
  {
    ppv = 0;
    v12 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 216LL))(ppv, 1);
      if ( v12 >= 0 )
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, __int64, int, int, __int64))(*(_QWORD *)ppv + 48LL))(
                ppv,
                a1,
                a2,
                a3,
                a4,
                a5,
                a6,
                a7);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v13 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      21,
      WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
      (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b200  push    rbx
0x18000b202  push    rbp
0x18000b203  push    rsi
0x18000b204  push    rdi
0x18000b205  push    r14
0x18000b207  push    r15
0x18000b209  sub     rsp, 68h
0x18000b20d  mov     r14, rdx
0x18000b210  mov     r15, rcx
0x18000b213  mov     edx, 6; dwCoInit
0x18000b218  xor     ecx, ecx; pvReserved
0x18000b21a  mov     rsi, r9
0x18000b21d  mov     rbp, r8
0x18000b220  call    cs:__imp_CoInitializeEx
0x18000b226  xor     ebx, ebx
0x18000b228  mov     edi, eax
0x18000b22a  cmp     eax, 80010106h
0x18000b22f  cmovnz  ebx, eax
0x18000b232  test    ebx, ebx
0x18000b234  js      loc_18000B2F3
0x18000b23a  lea     rax, [rsp+98h+var_48]
0x18000b23f  mov     [rsp+98h+var_48], 0
0x18000b248  lea     r9, IID_IXWizard; riid
0x18000b24f  mov     [rsp+98h+ppv], rax; ppv
0x18000b254  xor     edx, edx; pUnkOuter
0x18000b256  lea     rcx, CLSID_CXWizard; rclsid
0x18000b25d  mov     r8d, 401h; dwClsContext
0x18000b263  call    cs:__imp_CoCreateInstance
0x18000b269  mov     ebx, eax
0x18000b26b  test    eax, eax
0x18000b26d  js      short loc_18000B2E5
0x18000b26f  mov     rcx, [rsp+98h+var_48]
0x18000b274  xor     r8d, r8d
0x18000b277  mov     rax, [rcx]
0x18000b27a  lea     edx, [r8+1]
0x18000b27e  mov     rax, [rax+0D8h]
0x18000b285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b28a  mov     ebx, eax
0x18000b28c  test    eax, eax
0x18000b28e  js      short loc_18000B2D4
0x18000b290  mov     rdx, [rsp+98h+arg_30]
0x18000b298  mov     r9, rbp
0x18000b29b  mov     rcx, [rsp+98h+var_48]
0x18000b2a0  mov     r8, r14
0x18000b2a3  mov     [rsp+98h+var_60], rdx
0x18000b2a8  mov     edx, [rsp+98h+arg_28]
0x18000b2af  mov     [rsp+98h+var_68], edx
0x18000b2b3  mov     rax, [rcx]
0x18000b2b6  mov     edx, [rsp+98h+arg_20]
0x18000b2bd  mov     [rsp+98h+var_70], edx
0x18000b2c1  mov     rdx, r15
0x18000b2c4  mov     [rsp+98h+ppv], rsi
0x18000b2c9  mov     rax, [rax+30h]
0x18000b2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d2  mov     ebx, eax
0x18000b2d4  mov     rcx, [rsp+98h+var_48]
0x18000b2d9  mov     rax, [rcx]
0x18000b2dc  mov     rax, [rax+10h]
0x18000b2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e5  cmp     edi, 80010106h
0x18000b2eb  jz      short loc_18000B2F3
0x18000b2ed  call    cs:__imp_CoUninitialize
0x18000b2f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b2fa  lea     rax, WPP_GLOBAL_Control
0x18000b301  cmp     rcx, rax
0x18000b304  jz      short loc_18000B324
0x18000b306  test    byte ptr [rcx+1Ch], 10h
0x18000b30a  jz      short loc_18000B324
0x18000b30c  mov     rcx, [rcx+10h]
0x18000b310  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b317  mov     edx, 15h
0x18000b31c  mov     r9d, ebx
0x18000b31f  call    WPP_SF_d
0x18000b324  mov     eax, ebx
0x18000b326  add     rsp, 68h
0x18000b32a  pop     r15
0x18000b32c  pop     r14
0x18000b32e  pop     rdi
0x18000b32f  pop     rsi
0x18000b330  pop     rbp
0x18000b331  pop     rbx
0x18000b332  retn
```
