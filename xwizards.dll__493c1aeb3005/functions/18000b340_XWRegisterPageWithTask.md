# XWRegisterPageWithTask

- ea: `0x18000b340`
- end: `0x18000b473`
- name: `XWRegisterPageWithTask`
- size: `307`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b340`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b3a3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b3a3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b360`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b360`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b42d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b42d`

## pseudocode

```c
__int64 __fastcall XWRegisterPageWithTask(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, __int64 a7)
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
        v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, __int64, int, int, __int64))(*(_QWORD *)ppv + 40LL))(
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
      20,
      WPP_68058977b0c233f043f68faaec20b8c5_Traceguids,
      (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b340  push    rbx
0x18000b342  push    rbp
0x18000b343  push    rsi
0x18000b344  push    rdi
0x18000b345  push    r14
0x18000b347  push    r15
0x18000b349  sub     rsp, 68h
0x18000b34d  mov     r14, rdx
0x18000b350  mov     r15, rcx
0x18000b353  mov     edx, 6; dwCoInit
0x18000b358  xor     ecx, ecx; pvReserved
0x18000b35a  mov     rsi, r9
0x18000b35d  mov     rbp, r8
0x18000b360  call    cs:__imp_CoInitializeEx
0x18000b366  xor     ebx, ebx
0x18000b368  mov     edi, eax
0x18000b36a  cmp     eax, 80010106h
0x18000b36f  cmovnz  ebx, eax
0x18000b372  test    ebx, ebx
0x18000b374  js      loc_18000B433
0x18000b37a  lea     rax, [rsp+98h+var_48]
0x18000b37f  mov     [rsp+98h+var_48], 0
0x18000b388  lea     r9, IID_IXWizard; riid
0x18000b38f  mov     [rsp+98h+ppv], rax; ppv
0x18000b394  xor     edx, edx; pUnkOuter
0x18000b396  lea     rcx, CLSID_CXWizard; rclsid
0x18000b39d  mov     r8d, 401h; dwClsContext
0x18000b3a3  call    cs:__imp_CoCreateInstance
0x18000b3a9  mov     ebx, eax
0x18000b3ab  test    eax, eax
0x18000b3ad  js      short loc_18000B425
0x18000b3af  mov     rcx, [rsp+98h+var_48]
0x18000b3b4  xor     r8d, r8d
0x18000b3b7  mov     rax, [rcx]
0x18000b3ba  lea     edx, [r8+1]
0x18000b3be  mov     rax, [rax+0D8h]
0x18000b3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ca  mov     ebx, eax
0x18000b3cc  test    eax, eax
0x18000b3ce  js      short loc_18000B414
0x18000b3d0  mov     rdx, [rsp+98h+arg_30]
0x18000b3d8  mov     r9, rbp
0x18000b3db  mov     rcx, [rsp+98h+var_48]
0x18000b3e0  mov     r8, r14
0x18000b3e3  mov     [rsp+98h+var_60], rdx
0x18000b3e8  mov     edx, [rsp+98h+arg_28]
0x18000b3ef  mov     [rsp+98h+var_68], edx
0x18000b3f3  mov     rax, [rcx]
0x18000b3f6  mov     edx, [rsp+98h+arg_20]
0x18000b3fd  mov     [rsp+98h+var_70], edx
0x18000b401  mov     rdx, r15
0x18000b404  mov     [rsp+98h+ppv], rsi
0x18000b409  mov     rax, [rax+28h]
0x18000b40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b412  mov     ebx, eax
0x18000b414  mov     rcx, [rsp+98h+var_48]
0x18000b419  mov     rax, [rcx]
0x18000b41c  mov     rax, [rax+10h]
0x18000b420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b425  cmp     edi, 80010106h
0x18000b42b  jz      short loc_18000B433
0x18000b42d  call    cs:__imp_CoUninitialize
0x18000b433  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b43a  lea     rax, WPP_GLOBAL_Control
0x18000b441  cmp     rcx, rax
0x18000b444  jz      short loc_18000B464
0x18000b446  test    byte ptr [rcx+1Ch], 10h
0x18000b44a  jz      short loc_18000B464
0x18000b44c  mov     rcx, [rcx+10h]
0x18000b450  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b457  mov     edx, 14h
0x18000b45c  mov     r9d, ebx
0x18000b45f  call    WPP_SF_d
0x18000b464  mov     eax, ebx
0x18000b466  add     rsp, 68h
0x18000b46a  pop     r15
0x18000b46c  pop     r14
0x18000b46e  pop     rdi
0x18000b46f  pop     rsi
0x18000b470  pop     rbp
0x18000b471  pop     rbx
0x18000b472  retn
```
