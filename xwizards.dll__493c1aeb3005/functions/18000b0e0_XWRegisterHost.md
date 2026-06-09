# XWRegisterHost

- ea: `0x18000b0e0`
- end: `0x18000b1ef`
- name: `XWRegisterHost`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000ae04`
- `0x18000b0e0`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b143`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b143`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b100`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b100`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b1a9`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b1a9`

## pseudocode

```c
__int64 __fastcall XWRegisterHost(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  HRESULT v8; // eax
  HRESULT v9; // ebx
  HRESULT v10; // edi
  LPVOID ppv; // [rsp+30h] [rbp-48h] BYREF

  v8 = CoInitializeEx(0, 6u);
  v9 = 0;
  v10 = v8;
  if ( v8 != -2147417850 )
    v9 = v8;
  if ( v9 >= 0 )
  {
    ppv = 0;
    v9 = CoCreateInstance(&CLSID_CXWizard, 0, 0x401u, &IID_IXWizard, &ppv);
    if ( v9 >= 0 )
    {
      v9 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 216LL))(ppv, 1);
      if ( v9 >= 0 )
        v9 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64, __int64, int))(*(_QWORD *)ppv + 24LL))(
               ppv,
               a1,
               a2,
               a3,
               a4);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v10 != -2147417850 )
      CoUninitialize();
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids, (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000b0e0  push    rbx
0x18000b0e2  push    rbp
0x18000b0e3  push    rsi
0x18000b0e4  push    rdi
0x18000b0e5  push    r14
0x18000b0e7  push    r15
0x18000b0e9  sub     rsp, 48h
0x18000b0ed  mov     r14, rdx
0x18000b0f0  mov     r15, rcx
0x18000b0f3  mov     edx, 6; dwCoInit
0x18000b0f8  xor     ecx, ecx; pvReserved
0x18000b0fa  mov     esi, r9d
0x18000b0fd  mov     rbp, r8
0x18000b100  call    cs:__imp_CoInitializeEx
0x18000b106  xor     ebx, ebx
0x18000b108  mov     edi, eax
0x18000b10a  cmp     eax, 80010106h
0x18000b10f  cmovnz  ebx, eax
0x18000b112  test    ebx, ebx
0x18000b114  js      loc_18000B1AF
0x18000b11a  lea     rax, [rsp+78h+var_48]
0x18000b11f  mov     [rsp+78h+var_48], 0
0x18000b128  lea     r9, IID_IXWizard; riid
0x18000b12f  mov     [rsp+78h+ppv], rax; ppv
0x18000b134  xor     edx, edx; pUnkOuter
0x18000b136  lea     rcx, CLSID_CXWizard; rclsid
0x18000b13d  mov     r8d, 401h; dwClsContext
0x18000b143  call    cs:__imp_CoCreateInstance
0x18000b149  mov     ebx, eax
0x18000b14b  test    eax, eax
0x18000b14d  js      short loc_18000B1A1
0x18000b14f  mov     rcx, [rsp+78h+var_48]
0x18000b154  xor     r8d, r8d
0x18000b157  mov     rax, [rcx]
0x18000b15a  lea     edx, [r8+1]
0x18000b15e  mov     rax, [rax+0D8h]
0x18000b165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16a  mov     ebx, eax
0x18000b16c  test    eax, eax
0x18000b16e  js      short loc_18000B190
0x18000b170  mov     rcx, [rsp+78h+var_48]
0x18000b175  mov     r9, rbp
0x18000b178  mov     r8, r14
0x18000b17b  mov     dword ptr [rsp+78h+ppv], esi
0x18000b17f  mov     rdx, r15
0x18000b182  mov     rax, [rcx]
0x18000b185  mov     rax, [rax+18h]
0x18000b189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18e  mov     ebx, eax
0x18000b190  mov     rcx, [rsp+78h+var_48]
0x18000b195  mov     rax, [rcx]
0x18000b198  mov     rax, [rax+10h]
0x18000b19c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1a1  cmp     edi, 80010106h
0x18000b1a7  jz      short loc_18000B1AF
0x18000b1a9  call    cs:__imp_CoUninitialize
0x18000b1af  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b1b6  lea     rax, WPP_GLOBAL_Control
0x18000b1bd  cmp     rcx, rax
0x18000b1c0  jz      short loc_18000B1E0
0x18000b1c2  test    byte ptr [rcx+1Ch], 10h
0x18000b1c6  jz      short loc_18000B1E0
0x18000b1c8  mov     rcx, [rcx+10h]
0x18000b1cc  lea     r8, WPP_68058977b0c233f043f68faaec20b8c5_Traceguids
0x18000b1d3  mov     edx, 12h
0x18000b1d8  mov     r9d, ebx
0x18000b1db  call    WPP_SF_d
0x18000b1e0  mov     eax, ebx
0x18000b1e2  add     rsp, 48h
0x18000b1e6  pop     r15
0x18000b1e8  pop     r14
0x18000b1ea  pop     rdi
0x18000b1eb  pop     rsi
0x18000b1ec  pop     rbp
0x18000b1ed  pop     rbx
0x18000b1ee  retn
```
