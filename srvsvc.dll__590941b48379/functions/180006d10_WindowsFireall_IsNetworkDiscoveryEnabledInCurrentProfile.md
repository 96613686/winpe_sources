# WindowsFireall_IsNetworkDiscoveryEnabledInCurrentProfile

- ea: `0x180006d10`
- end: `0x180006dfc`
- name: `WindowsFireall_IsNetworkDiscoveryEnabledInCurrentProfile`
- size: `236`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006b90`

## callees

- `0x180006d10`
- `0x18003d14c`
- `0x180044010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006d4d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180006d4d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006d79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006d79`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006da7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180006da7`
- `OLEAUT32!__imp_SysAllocString` at `0x180006d30`
- `OLEAUT32!__imp_SysAllocString` at `0x180006d30`
- `OLEAUT32!__imp_SysFreeString` at `0x180006db0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006db0`

## string_xrefs

- `0x180006d24`: `@FirewallAPI.dll,-32752`

## pseudocode

```c
__int64 __fastcall WindowsFireall_IsNetworkDiscoveryEnabledInCurrentProfile(_DWORD *a1)
{
  int v2; // ecx
  OLECHAR *v3; // rbx
  HRESULT v4; // edi
  __int16 v6; // [rsp+48h] [rbp+10h] BYREF
  LPVOID ppv; // [rsp+50h] [rbp+18h] BYREF

  ppv = 0;
  v3 = SysAllocString(L"@FirewallAPI.dll,-32752");
  if ( !v3 )
    ATL::AtlThrowImpl(v2);
  v6 = 0;
  *a1 = 0;
  v4 = CoInitializeEx(0, 0);
  if ( v4 >= 0 )
  {
    v4 = CoCreateInstance(
           &GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd,
           0,
           1u,
           &GUID_98325047_c671_4174_8d81_defcd3f03186,
           &ppv);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, __int16 *))(*(_QWORD *)ppv + 216LL))(ppv, v3, &v6);
      if ( v4 >= 0 && v6 == -1 && !v4 )
        *a1 = 1;
    }
    CoUninitialize();
  }
  SysFreeString(v3);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180006d10  mov     [rsp+arg_0], rbx
0x180006d15  mov     [rsp+arg_18], rsi
0x180006d1a  push    rdi
0x180006d1b  sub     rsp, 30h
0x180006d1f  mov     rsi, rcx
0x180006d22  xor     edi, edi
0x180006d24  lea     rcx, aFirewallapiDll_1; "@FirewallAPI.dll,-32752"
0x180006d2b  mov     [rsp+38h+arg_10], rdi
0x180006d30  call    cs:__imp_SysAllocString
0x180006d36  mov     rbx, rax
0x180006d39  test    rax, rax
0x180006d3c  jz      loc_180006DF6
0x180006d42  xor     edx, edx; dwCoInit
0x180006d44  mov     [rsp+38h+arg_8], di
0x180006d49  xor     ecx, ecx; pvReserved
0x180006d4b  mov     [rsi], edi
0x180006d4d  call    cs:__imp_CoInitializeEx
0x180006d53  mov     edi, eax
0x180006d55  test    eax, eax
0x180006d57  js      short loc_180006DAD
0x180006d59  lea     rax, [rsp+38h+arg_10]
0x180006d5e  xor     edx, edx; pUnkOuter
0x180006d60  lea     r9, _GUID_98325047_c671_4174_8d81_defcd3f03186; riid
0x180006d67  mov     [rsp+38h+ppv], rax; ppv
0x180006d6c  mov     r8d, 1; dwClsContext
0x180006d72  lea     rcx, _GUID_e2b3c97f_6ae1_41ac_817a_f6f92166d7dd; rclsid
0x180006d79  call    cs:__imp_CoCreateInstance
0x180006d7f  mov     edi, eax
0x180006d81  test    eax, eax
0x180006d83  js      short loc_180006DA7
0x180006d85  mov     rcx, [rsp+38h+arg_10]
0x180006d8a  lea     r8, [rsp+38h+arg_8]
0x180006d8f  mov     rdx, rbx
0x180006d92  mov     rax, [rcx]
0x180006d95  mov     rax, [rax+0D8h]
0x180006d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da1  mov     edi, eax
0x180006da3  test    eax, eax
0x180006da5  jns     short loc_180006DDE
0x180006da7  call    cs:__imp_CoUninitialize
0x180006dad  mov     rcx, rbx; bstrString
0x180006db0  call    cs:__imp_SysFreeString
0x180006db6  mov     rcx, [rsp+38h+arg_10]
0x180006dbb  test    rcx, rcx
0x180006dbe  jz      short loc_180006DCC
0x180006dc0  mov     rax, [rcx]
0x180006dc3  mov     rax, [rax+10h]
0x180006dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dcc  mov     rbx, [rsp+38h+arg_0]
0x180006dd1  mov     eax, edi
0x180006dd3  mov     rsi, [rsp+38h+arg_18]
0x180006dd8  add     rsp, 30h
0x180006ddc  pop     rdi
0x180006ddd  retn
0x180006dde  mov     eax, 0FFFFFFFFh
0x180006de3  cmp     ax, [rsp+38h+arg_8]
0x180006de8  jnz     short loc_180006DA7
0x180006dea  test    edi, edi
0x180006dec  jnz     short loc_180006DA7
0x180006dee  mov     dword ptr [rsi], 1
0x180006df4  jmp     short loc_180006DA7
0x180006df6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
