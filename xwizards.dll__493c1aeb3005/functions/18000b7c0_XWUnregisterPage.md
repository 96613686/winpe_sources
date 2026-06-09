# XWUnregisterPage

- ea: `0x18000b7c0`
- end: `0x18000b8b9`
- name: `XWUnregisterPage`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b7c0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b818`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b818`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b7d5`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b7d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b877`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b877`

## pseudocode

```c
__int64 __fastcall XWUnregisterPage(__int64 a1, unsigned int a2)
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
        v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, a1, a2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v6 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b7c0  push    rbx
0x18000b7c2  push    rbp
0x18000b7c3  push    rsi
0x18000b7c4  push    rdi
0x18000b7c5  sub     rsp, 38h
0x18000b7c9  mov     esi, edx
0x18000b7cb  mov     rbp, rcx
0x18000b7ce  mov     edx, 6; dwCoInit
0x18000b7d3  xor     ecx, ecx; pvReserved
0x18000b7d5  call    cs:__imp_CoInitializeEx
0x18000b7db  xor     ebx, ebx
0x18000b7dd  mov     edi, eax
0x18000b7df  cmp     eax, 80010106h
0x18000b7e4  cmovnz  ebx, eax
0x18000b7e7  test    ebx, ebx
0x18000b7e9  js      loc_18000B87D
0x18000b7ef  lea     rax, [rsp+58h+arg_10]
0x18000b7f4  mov     [rsp+58h+arg_10], 0
0x18000b7fd  lea     r9, IID_IXWizard; riid
0x18000b804  mov     [rsp+58h+ppv], rax; ppv
0x18000b809  xor     edx, edx; pUnkOuter
0x18000b80b  lea     rcx, CLSID_CXWizard; rclsid
0x18000b812  mov     r8d, 401h; dwClsContext
0x18000b818  call    cs:__imp_CoCreateInstance
0x18000b81e  mov     ebx, eax
0x18000b820  test    eax, eax
0x18000b822  js      short loc_18000B86F
0x18000b824  mov     rcx, [rsp+58h+arg_10]
0x18000b829  xor     r8d, r8d
0x18000b82c  mov     rax, [rcx]
0x18000b82f  lea     edx, [r8+1]
0x18000b833  mov     rax, [rax+0D8h]
0x18000b83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b83f  mov     ebx, eax
0x18000b841  test    eax, eax
0x18000b843  js      short loc_18000B85E
0x18000b845  mov     rcx, [rsp+58h+arg_10]
0x18000b84a  mov     r8d, esi
0x18000b84d  mov     rdx, rbp
0x18000b850  mov     rax, [rcx]
0x18000b853  mov     rax, [rax+48h]
0x18000b857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b85c  mov     ebx, eax
0x18000b85e  mov     rcx, [rsp+58h+arg_10]
0x18000b863  mov     rax, [rcx]
0x18000b866  mov     rax, [rax+10h]
0x18000b86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b86f  cmp     edi, 80010106h
0x18000b875  jz      short loc_18000B87D
0x18000b877  call    cs:__imp_CoUninitialize
0x18000b87d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b884  lea     rax, WPP_GLOBAL_Control
0x18000b88b  cmp     rcx, rax
0x18000b88e  jz      short loc_18000B8AE
0x18000b890  test    byte ptr [rcx+1Ch], 10h
0x18000b894  jz      short loc_18000B8AE
0x18000b896  mov     rcx, [rcx+10h]
0x18000b89a  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b8a1  mov     edx, 18h
0x18000b8a6  mov     r9d, ebx
0x18000b8a9  call    WPP_SF_d
0x18000b8ae  mov     eax, ebx
0x18000b8b0  add     rsp, 38h
0x18000b8b4  pop     rdi
0x18000b8b5  pop     rsi
0x18000b8b6  pop     rbp
0x18000b8b7  pop     rbx
0x18000b8b8  retn
```
