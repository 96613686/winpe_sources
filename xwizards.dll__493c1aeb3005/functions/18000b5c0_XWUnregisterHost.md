# XWUnregisterHost

- ea: `0x18000b5c0`
- end: `0x18000b6b9`
- name: `XWUnregisterHost`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b5c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b618`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b618`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b5d5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b5d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b677`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b677`

## pseudocode

```c
__int64 __fastcall XWUnregisterHost(__int64 a1, unsigned int a2)
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
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 56LL))(ppv, a1, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b5c0  push    rbx
0x18000b5c2  push    rbp
0x18000b5c3  push    rsi
0x18000b5c4  push    rdi
0x18000b5c5  sub     rsp, 38h
0x18000b5c9  mov     esi, edx
0x18000b5cb  mov     rbp, rcx
0x18000b5ce  mov     edx, 6; dwCoInit
0x18000b5d3  xor     ecx, ecx; pvReserved
0x18000b5d5  call    cs:__imp_CoInitializeEx
0x18000b5db  xor     ebx, ebx
0x18000b5dd  mov     edi, eax
0x18000b5df  cmp     eax, 80010106h
0x18000b5e4  cmovnz  ebx, eax
0x18000b5e7  test    ebx, ebx
0x18000b5e9  js      loc_18000B67D
0x18000b5ef  lea     rax, [rsp+58h+arg_10]
0x18000b5f4  mov     [rsp+58h+arg_10], 0
0x18000b5fd  lea     r9, IID_IXWizard; riid
0x18000b604  mov     [rsp+58h+ppv], rax; ppv
0x18000b609  xor     edx, edx; pUnkOuter
0x18000b60b  lea     rcx, CLSID_CXWizard; rclsid
0x18000b612  mov     r8d, 401h; dwClsContext
0x18000b618  call    cs:__imp_CoCreateInstance
0x18000b61e  mov     ebx, eax
0x18000b620  test    eax, eax
0x18000b622  js      short loc_18000B66F
0x18000b624  mov     rcx, [rsp+58h+arg_10]
0x18000b629  xor     r8d, r8d
0x18000b62c  mov     rax, [rcx]
0x18000b62f  lea     edx, [r8+1]
0x18000b633  mov     rax, [rax+0D8h]
0x18000b63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63f  mov     ebx, eax
0x18000b641  test    eax, eax
0x18000b643  js      short loc_18000B65E
0x18000b645  mov     rcx, [rsp+58h+arg_10]
0x18000b64a  mov     r8d, esi
0x18000b64d  mov     rdx, rbp
0x18000b650  mov     rax, [rcx]
0x18000b653  mov     rax, [rax+38h]
0x18000b657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b65c  mov     ebx, eax
0x18000b65e  mov     rcx, [rsp+58h+arg_10]
0x18000b663  mov     rax, [rcx]
0x18000b666  mov     rax, [rax+10h]
0x18000b66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b66f  cmp     edi, 80010106h
0x18000b675  jz      short loc_18000B67D
0x18000b677  call    cs:__imp_CoUninitialize
0x18000b67d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b684  lea     rax, WPP_GLOBAL_Control
0x18000b68b  cmp     rcx, rax
0x18000b68e  jz      short loc_18000B6AE
0x18000b690  test    byte ptr [rcx+1Ch], 10h
0x18000b694  jz      short loc_18000B6AE
0x18000b696  mov     rcx, [rcx+10h]
0x18000b69a  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b6a1  mov     edx, 16h
0x18000b6a6  mov     r9d, ebx
0x18000b6a9  call    WPP_SF_d
0x18000b6ae  mov     eax, ebx
0x18000b6b0  add     rsp, 38h
0x18000b6b4  pop     rdi
0x18000b6b5  pop     rsi
0x18000b6b6  pop     rbp
0x18000b6b7  pop     rbx
0x18000b6b8  retn
```
