# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x180007c10`
- end: `0x180007d1a`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `266`
- prototype: `LSTATUS __fastcall(ATL::CRegKey *this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005770`
- `0x180007aac`
- `0x180007ee0`

## callees

- `0x180007c10`
- `0x180036a10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007cb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c3e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007cb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c53`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007cce`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180007c8b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180007c8b`

## string_xrefs

- `0x180007c49`: `RegDeleteKeyTransactedW`
- `0x180007c37`: `Advapi32.dll`
- `0x180007cb2`: `Advapi32.dll`
- `0x180007cc4`: `RegDeleteKeyExW`

## pseudocode

```c
LSTATUS __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const wchar_t *a2)
{
  const wchar_t *v2; // rsi
  __int64 v4; // rdi
  __int64 v5; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  HKEY v9; // rcx
  HMODULE v10; // rax
  FARPROC v11; // r10

  v2 = a2;
  v4 = *((_QWORD *)this + 2);
  if ( v4 )
  {
    v5 = *(_QWORD *)this;
    if ( *(_QWORD *)v4 )
    {
      ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
      if ( ModuleHandleW )
      {
        ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyTransactedW");
        if ( ProcAddress )
          return ((__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD, _QWORD, _QWORD, _QWORD))ProcAddress)(
                   v5,
                   v2,
                   0,
                   0,
                   *(_QWORD *)v4,
                   0);
      }
      return 1;
    }
    if ( !*(_DWORD *)(v4 + 8) )
      return 1;
    v9 = *(HKEY *)this;
    return RegDeleteKeyW(v9, a2);
  }
  if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
  {
    v11 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
  }
  else
  {
    v10 = GetModuleHandleW(L"Advapi32.dll");
    if ( v10 )
    {
      v11 = GetProcAddress(v10, "RegDeleteKeyExW");
      `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)v11;
    }
    else
    {
      v11 = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
    }
    `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
  }
  a2 = v2;
  v9 = *(HKEY *)this;
  if ( !v11 )
    return RegDeleteKeyW(v9, a2);
  return ((__int64 (__fastcall *)(HKEY, const wchar_t *, _QWORD, _QWORD))v11)(v9, v2, *((unsigned int *)this + 2), 0);
}

```

## disassembly

```asm
0x180007c10  mov     [rsp+arg_0], rbx
0x180007c15  mov     [rsp+arg_8], rsi
0x180007c1a  push    rdi
0x180007c1b  sub     rsp, 40h
0x180007c1f  mov     rsi, rdx
0x180007c22  mov     rbx, rcx
0x180007c25  mov     rdi, [rcx+10h]
0x180007c29  test    rdi, rdi
0x180007c2c  jz      short loc_180007CA9
0x180007c2e  mov     rbx, [rcx]
0x180007c31  cmp     qword ptr [rdi], 0
0x180007c35  jz      short loc_180007C82
0x180007c37  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x180007c3e  call    cs:__imp_GetModuleHandleW
0x180007c44  test    rax, rax
0x180007c47  jz      short loc_180007CA2
0x180007c49  lea     rdx, aRegdeletekeytr; "RegDeleteKeyTransactedW"
0x180007c50  mov     rcx, rax; hModule
0x180007c53  call    cs:__imp_GetProcAddress
0x180007c59  test    rax, rax
0x180007c5c  jz      short loc_180007CA2
0x180007c5e  mov     [rsp+48h+var_20], 0
0x180007c67  mov     rdx, [rdi]
0x180007c6a  mov     [rsp+48h+var_28], rdx
0x180007c6f  xor     r9d, r9d
0x180007c72  xor     r8d, r8d
0x180007c75  mov     rdx, rsi
0x180007c78  mov     rcx, rbx
0x180007c7b  call    _guard_dispatch_icall
0x180007c80  jmp     short loc_180007C92
0x180007c82  cmp     dword ptr [rdi+8], 0
0x180007c86  jz      short loc_180007CA2
0x180007c88  mov     rcx, rbx; hKey
0x180007c8b  call    cs:__imp_RegDeleteKeyW
0x180007c91  nop
0x180007c92  mov     rbx, [rsp+48h+arg_0]
0x180007c97  mov     rsi, [rsp+48h+arg_8]
0x180007c9c  add     rsp, 40h
0x180007ca0  pop     rdi
0x180007ca1  retn
0x180007ca2  mov     eax, 1
0x180007ca7  jmp     short loc_180007C92
0x180007ca9  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4_NA, 0; bool `ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::bInitialized
0x180007cb0  jnz     short loc_180007CF4
0x180007cb2  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x180007cb9  call    cs:__imp_GetModuleHandleW
0x180007cbf  test    rax, rax
0x180007cc2  jz      short loc_180007CE0
0x180007cc4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180007ccb  mov     rcx, rax; hModule
0x180007cce  call    cs:__imp_GetProcAddress
0x180007cd4  mov     r10, rax
0x180007cd7  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x180007cde  jmp     short loc_180007CE7
0x180007ce0  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x180007ce7  mov     eax, 1
0x180007cec  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4_NA, al; bool `ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::bInitialized
0x180007cf2  jmp     short loc_180007CFB
0x180007cf4  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x180007cfb  mov     rdx, rsi
0x180007cfe  mov     rcx, [rbx]
0x180007d01  test    r10, r10
0x180007d04  jz      short loc_180007C8B
0x180007d06  xor     r9d, r9d
0x180007d09  mov     r8d, [rbx+8]
0x180007d0d  mov     rax, r10
0x180007d10  call    _guard_dispatch_icall
0x180007d15  jmp     loc_180007C92
```
