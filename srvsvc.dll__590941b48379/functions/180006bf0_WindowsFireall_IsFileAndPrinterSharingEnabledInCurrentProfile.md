# WindowsFireall_IsFileAndPrinterSharingEnabledInCurrentProfile

- ea: `0x180006bf0`
- end: `0x180006cfb`
- name: `WindowsFireall_IsFileAndPrinterSharingEnabledInCurrentProfile`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006b90`

## callees

- `0x180006bf0`
- `0x18003d14c`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006c52`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006c52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006c7c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006cbe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006cbe`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c06`
- `OLEAUT32!__imp_SysAllocString` at `0x180006c06`
- `OLEAUT32!__imp_SysFreeString` at `0x180006cdd`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ce6`
- `OLEAUT32!__imp_SysFreeString` at `0x180006cdd`
- `OLEAUT32!__imp_SysFreeString` at `0x180006ce6`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006c1d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x180006c1d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180006c28`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180006c28`

## string_xrefs

- `0x180006bff`: `@FirewallAPI.dll,-28502`

## pseudocode

```c
__int64 __fastcall WindowsFireall_IsFileAndPrinterSharingEnabledInCurrentProfile(_DWORD *a1)
{
  OLECHAR *v2; // rax
  int v3; // ecx
  CHAR *v4; // rbx
  UINT v5; // eax
  int v6; // ecx
  OLECHAR *v7; // rbp
  HRESULT v8; // edi
  __int16 v10; // [rsp+58h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+18h] BYREF

  v2 = SysAllocString(L"@FirewallAPI.dll,-28502");
  v4 = (CHAR *)v2;
  if ( !v2 )
    ATL::AtlThrowImpl(v3);
  v5 = SysStringByteLen(v2);
  v7 = SysAllocStringByteLen(v4, v5);
  if ( !v7 )
    ATL::AtlThrowImpl(v6);
  ppv = 0;
  v10 = 0;
  *a1 = 0;
  v8 = CoInitializeEx(0, 0);
  if ( v8 >= 0 )
  {
    v8 = CoCreateInstance(
           &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
           0,
           1u,
           &GUID_98325047_c671_4174_8d81_defcd3f03186,
           &ppv);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 216LL))(ppv, v7, &v10);
      if ( v8 >= 0 && v10 == -1 && !v8 )
        *a1 = 1;
    }
    CoUninitialize();
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  SysFreeString(v7);
  SysFreeString((BSTR)v4);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006bf0  mov     [rsp+arg_0], rbx
0x180006bf5  push    rbp
0x180006bf6  push    rsi
0x180006bf7  push    rdi
0x180006bf8  sub     rsp, 30h
0x180006bfc  mov     rsi, rcx
0x180006bff  lea     rcx, psz; "@FirewallAPI.dll,-28502"
0x180006c06  call    cs:__imp_SysAllocString
0x180006c0c  mov     rbx, rax
0x180006c0f  test    rax, rax
0x180006c12  jnz     short loc_180006C1A
0x180006c14  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006c1a  mov     rcx, rbx; bstr
0x180006c1d  call    cs:__imp_SysStringByteLen
0x180006c23  mov     edx, eax; len
0x180006c25  mov     rcx, rbx; psz
0x180006c28  call    cs:__imp_SysAllocStringByteLen
0x180006c2e  mov     rbp, rax
0x180006c31  test    rax, rax
0x180006c34  jnz     short loc_180006C3C
0x180006c36  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180006c3c  xor     eax, eax
0x180006c3e  mov     [rsp+48h+arg_10], 0
0x180006c47  xor     edx, edx; dwCoInit
0x180006c49  mov     [rsp+48h+arg_8], ax
0x180006c4e  xor     ecx, ecx; pvReserved
0x180006c50  mov     [rsi], eax
0x180006c52  call    cs:__imp_CoInitializeEx
0x180006c58  mov     edi, eax
0x180006c5a  test    eax, eax
0x180006c5c  js      short loc_180006CC4
0x180006c5e  xor     edx, edx; pUnkOuter
0x180006c60  lea     rax, [rsp+48h+arg_10]
0x180006c65  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180006c6c  mov     [rsp+48h+ppv], rax; ppv
0x180006c71  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180006c78  lea     r8d, [rdx+1]; dwClsContext
0x180006c7c  call    cs:__imp_CoCreateInstance
0x180006c82  mov     edi, eax
0x180006c84  test    eax, eax
0x180006c86  js      short loc_180006CBE
0x180006c88  mov     rcx, [rsp+48h+arg_10]
0x180006c8d  lea     r8, [rsp+48h+arg_8]
0x180006c92  mov     rdx, rbp
0x180006c95  mov     rax, [rcx]
0x180006c98  mov     rax, [rax+0D8h]
0x180006c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca4  mov     edi, eax
0x180006ca6  test    eax, eax
0x180006ca8  js      short loc_180006CBE
0x180006caa  or      eax, 0FFFFFFFFh
0x180006cad  cmp     ax, [rsp+48h+arg_8]
0x180006cb2  jnz     short loc_180006CBE
0x180006cb4  test    edi, edi
0x180006cb6  jnz     short loc_180006CBE
0x180006cb8  mov     dword ptr [rsi], 1
0x180006cbe  call    cs:__imp_CoUninitialize
0x180006cc4  mov     rcx, [rsp+48h+arg_10]
0x180006cc9  test    rcx, rcx
0x180006ccc  jz      short loc_180006CDA
0x180006cce  mov     rax, [rcx]
0x180006cd1  mov     rax, [rax+10h]
0x180006cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cda  mov     rcx, rbp; bstrString
0x180006cdd  call    cs:__imp_SysFreeString
0x180006ce3  mov     rcx, rbx; bstrString
0x180006ce6  call    cs:__imp_SysFreeString
0x180006cec  mov     rbx, [rsp+48h+arg_0]
0x180006cf1  mov     eax, edi
0x180006cf3  add     rsp, 30h
0x180006cf7  pop     rdi
0x180006cf8  pop     rsi
0x180006cf9  pop     rbp
0x180006cfa  retn
```
