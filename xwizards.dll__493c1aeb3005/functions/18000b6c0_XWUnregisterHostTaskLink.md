# XWUnregisterHostTaskLink

- ea: `0x18000b6c0`
- end: `0x18000b7ba`
- name: `XWUnregisterHostTaskLink`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b6c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b719`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b719`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b6d6`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b6d6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b778`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b778`

## pseudocode

```c
__int64 __fastcall XWUnregisterHostTaskLink(__int64 a1, __int64 a2)
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
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 80LL))(ppv, a1, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b6c0  push    rbx
0x18000b6c2  push    rbp
0x18000b6c3  push    rsi
0x18000b6c4  push    rdi
0x18000b6c5  sub     rsp, 38h
0x18000b6c9  mov     rsi, rdx
0x18000b6cc  mov     rbp, rcx
0x18000b6cf  mov     edx, 6; dwCoInit
0x18000b6d4  xor     ecx, ecx; pvReserved
0x18000b6d6  call    cs:__imp_CoInitializeEx
0x18000b6dc  xor     ebx, ebx
0x18000b6de  mov     edi, eax
0x18000b6e0  cmp     eax, 80010106h
0x18000b6e5  cmovnz  ebx, eax
0x18000b6e8  test    ebx, ebx
0x18000b6ea  js      loc_18000B77E
0x18000b6f0  lea     rax, [rsp+58h+arg_10]
0x18000b6f5  mov     [rsp+58h+arg_10], 0
0x18000b6fe  lea     r9, IID_IXWizard; riid
0x18000b705  mov     [rsp+58h+ppv], rax; ppv
0x18000b70a  xor     edx, edx; pUnkOuter
0x18000b70c  lea     rcx, CLSID_CXWizard; rclsid
0x18000b713  mov     r8d, 401h; dwClsContext
0x18000b719  call    cs:__imp_CoCreateInstance
0x18000b71f  mov     ebx, eax
0x18000b721  test    eax, eax
0x18000b723  js      short loc_18000B770
0x18000b725  mov     rcx, [rsp+58h+arg_10]
0x18000b72a  xor     r8d, r8d
0x18000b72d  mov     rax, [rcx]
0x18000b730  lea     edx, [r8+1]
0x18000b734  mov     rax, [rax+0D8h]
0x18000b73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b740  mov     ebx, eax
0x18000b742  test    eax, eax
0x18000b744  js      short loc_18000B75F
0x18000b746  mov     rcx, [rsp+58h+arg_10]
0x18000b74b  mov     r8, rsi
0x18000b74e  mov     rdx, rbp
0x18000b751  mov     rax, [rcx]
0x18000b754  mov     rax, [rax+50h]
0x18000b758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b75d  mov     ebx, eax
0x18000b75f  mov     rcx, [rsp+58h+arg_10]
0x18000b764  mov     rax, [rcx]
0x18000b767  mov     rax, [rax+10h]
0x18000b76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b770  cmp     edi, 80010106h
0x18000b776  jz      short loc_18000B77E
0x18000b778  call    cs:__imp_CoUninitialize
0x18000b77e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b785  lea     rax, WPP_GLOBAL_Control
0x18000b78c  cmp     rcx, rax
0x18000b78f  jz      short loc_18000B7AF
0x18000b791  test    byte ptr [rcx+1Ch], 10h
0x18000b795  jz      short loc_18000B7AF
0x18000b797  mov     rcx, [rcx+10h]
0x18000b79b  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b7a2  mov     edx, 19h
0x18000b7a7  mov     r9d, ebx
0x18000b7aa  call    WPP_SF_d
0x18000b7af  mov     eax, ebx
0x18000b7b1  add     rsp, 38h
0x18000b7b5  pop     rdi
0x18000b7b6  pop     rsi
0x18000b7b7  pop     rbp
0x18000b7b8  pop     rbx
0x18000b7b9  retn
```
