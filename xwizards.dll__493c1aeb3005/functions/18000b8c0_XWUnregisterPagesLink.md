# XWUnregisterPagesLink

- ea: `0x18000b8c0`
- end: `0x18000b9ba`
- name: `XWUnregisterPagesLink`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b8c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b919`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b919`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b8d6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b8d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b978`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b978`

## pseudocode

```c
__int64 __fastcall XWUnregisterPagesLink(__int64 a1, __int64 a2)
{
  HRESULT v4; // eax
  HRESULT v5; // ebx
  HRESULT v6; // edi
  LPVOID ppv; // [rsp+70h] [rbp+18h] BYREF

  v4 = CoInitializeEx(0, 6u);
  v5 = 0;
  v6 = v4;
  if ( v4 != -2147417850 )
    v5 = v4;
  if ( v5 >= 0 )
  {
    ppv = 0;
    v5 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
    if ( v5 >= 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 216LL))(ppv, 1);
      if ( v5 >= 0 )
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 96LL))(ppv, a1, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b8c0  push    rbx
0x18000b8c2  push    rbp
0x18000b8c3  push    rsi
0x18000b8c4  push    rdi
0x18000b8c5  sub     rsp, 38h
0x18000b8c9  mov     rsi, rdx
0x18000b8cc  mov     rbp, rcx
0x18000b8cf  mov     edx, 6; dwCoInit
0x18000b8d4  xor     ecx, ecx; pvReserved
0x18000b8d6  call    cs:__imp_CoInitializeEx
0x18000b8dc  xor     ebx, ebx
0x18000b8de  mov     edi, eax
0x18000b8e0  cmp     eax, 80010106h
0x18000b8e5  cmovnz  ebx, eax
0x18000b8e8  test    ebx, ebx
0x18000b8ea  js      loc_18000B97E
0x18000b8f0  lea     rax, [rsp+58h+arg_10]
0x18000b8f5  mov     [rsp+58h+arg_10], 0
0x18000b8fe  lea     r9, IID_IXWizard; riid
0x18000b905  mov     [rsp+58h+ppv], rax; ppv
0x18000b90a  xor     edx, edx; pUnkOuter
0x18000b90c  lea     rcx, CLSID_CXWizard; rclsid
0x18000b913  mov     r8d, 401h; dwClsContext
0x18000b919  call    cs:__imp_CoCreateInstance
0x18000b91f  mov     ebx, eax
0x18000b921  test    eax, eax
0x18000b923  js      short loc_18000B970
0x18000b925  mov     rcx, [rsp+58h+arg_10]
0x18000b92a  xor     r8d, r8d
0x18000b92d  mov     rax, [rcx]
0x18000b930  lea     edx, [r8+1]
0x18000b934  mov     rax, [rax+0D8h]
0x18000b93b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b940  mov     ebx, eax
0x18000b942  test    eax, eax
0x18000b944  js      short loc_18000B95F
0x18000b946  mov     rcx, [rsp+58h+arg_10]
0x18000b94b  mov     r8, rsi
0x18000b94e  mov     rdx, rbp
0x18000b951  mov     rax, [rcx]
0x18000b954  mov     rax, [rax+60h]
0x18000b958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b95d  mov     ebx, eax
0x18000b95f  mov     rcx, [rsp+58h+arg_10]
0x18000b964  mov     rax, [rcx]
0x18000b967  mov     rax, [rax+10h]
0x18000b96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b970  cmp     edi, 80010106h
0x18000b976  jz      short loc_18000B97E
0x18000b978  call    cs:__imp_CoUninitialize
0x18000b97e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b985  lea     rax, WPP_GLOBAL_Control
0x18000b98c  cmp     rcx, rax
0x18000b98f  jz      short loc_18000B9AF
0x18000b991  test    byte ptr [rcx+1Ch], 10h
0x18000b995  jz      short loc_18000B9AF
0x18000b997  mov     rcx, [rcx+10h]
0x18000b99b  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b9a2  mov     edx, 1Bh
0x18000b9a7  mov     r9d, ebx
0x18000b9aa  call    WPP_SF_d
0x18000b9af  mov     eax, ebx
0x18000b9b1  add     rsp, 38h
0x18000b9b5  pop     rdi
0x18000b9b6  pop     rsi
0x18000b9b7  pop     rbp
0x18000b9b8  pop     rbx
0x18000b9b9  retn
```
