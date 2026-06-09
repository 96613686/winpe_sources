# ATL::CRegKey::DeleteSubKey(wchar_t const *)

- ea: `0x18007d06c`
- end: `0x18007d176`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z`
- size: `266`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18007b140`
- `0x18007cf08`
- `0x18007d33c`

## callees

- `0x18007d06c`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d0af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d12a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d0af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d12a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d09a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d115`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d09a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d115`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007d0e7`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007d0e7`

## string_xrefs

- `0x18007d0a5`: `RegDeleteKeyTransactedW`
- `0x18007d093`: `Advapi32.dll`
- `0x18007d10e`: `Advapi32.dll`
- `0x18007d120`: `RegDeleteKeyExW`

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
0x18007d06c  mov     [rsp+arg_0], rbx
0x18007d071  mov     [rsp+arg_8], rsi
0x18007d076  push    rdi
0x18007d077  sub     rsp, 40h
0x18007d07b  mov     rsi, rdx
0x18007d07e  mov     rbx, rcx
0x18007d081  mov     rdi, [rcx+10h]
0x18007d085  test    rdi, rdi
0x18007d088  jz      short loc_18007D105
0x18007d08a  mov     rbx, [rcx]
0x18007d08d  cmp     qword ptr [rdi], 0
0x18007d091  jz      short loc_18007D0DE
0x18007d093  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x18007d09a  call    cs:__imp_GetModuleHandleW
0x18007d0a0  test    rax, rax
0x18007d0a3  jz      short loc_18007D0FE
0x18007d0a5  lea     rdx, aRegdeletekeytr; "RegDeleteKeyTransactedW"
0x18007d0ac  mov     rcx, rax; hModule
0x18007d0af  call    cs:__imp_GetProcAddress
0x18007d0b5  test    rax, rax
0x18007d0b8  jz      short loc_18007D0FE
0x18007d0ba  mov     [rsp+48h+var_20], 0
0x18007d0c3  mov     rdx, [rdi]
0x18007d0c6  mov     [rsp+48h+var_28], rdx
0x18007d0cb  xor     r9d, r9d
0x18007d0ce  xor     r8d, r8d
0x18007d0d1  mov     rdx, rsi
0x18007d0d4  mov     rcx, rbx
0x18007d0d7  call    _guard_dispatch_icall
0x18007d0dc  jmp     short loc_18007D0EE
0x18007d0de  cmp     dword ptr [rdi+8], 0
0x18007d0e2  jz      short loc_18007D0FE
0x18007d0e4  mov     rcx, rbx; hKey
0x18007d0e7  call    cs:__imp_RegDeleteKeyW
0x18007d0ed  nop
0x18007d0ee  mov     rbx, [rsp+48h+arg_0]
0x18007d0f3  mov     rsi, [rsp+48h+arg_8]
0x18007d0f8  add     rsp, 40h
0x18007d0fc  pop     rdi
0x18007d0fd  retn
0x18007d0fe  mov     eax, 1
0x18007d103  jmp     short loc_18007D0EE
0x18007d105  cmp     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4_NA, 0; bool `ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::bInitialized
0x18007d10c  jnz     short loc_18007D150
0x18007d10e  lea     rcx, aAdvapi32Dll; "Advapi32.dll"
0x18007d115  call    cs:__imp_GetModuleHandleW
0x18007d11b  test    rax, rax
0x18007d11e  jz      short loc_18007D13C
0x18007d120  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18007d127  mov     rcx, rax; hModule
0x18007d12a  call    cs:__imp_GetProcAddress
0x18007d130  mov     r10, rax
0x18007d133  mov     cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA, rax; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x18007d13a  jmp     short loc_18007D143
0x18007d13c  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x18007d143  mov     eax, 1
0x18007d148  mov     cs:?bInitialized@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4_NA, al; bool `ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::bInitialized
0x18007d14e  jmp     short loc_18007D157
0x18007d150  mov     r10, cs:?pfnRegDeleteKeyEx@?1??DeleteSubKey@CRegKey@ATL@@QEAAJPEB_W@Z@4P6AJPEAUHKEY__@@0KK@ZEA; long (*`ATL::CRegKey::DeleteSubKey(wchar_t const *)'::`2'::pfnRegDeleteKeyEx)(HKEY__ *,wchar_t const *,ulong,ulong)
0x18007d157  mov     rdx, rsi
0x18007d15a  mov     rcx, [rbx]
0x18007d15d  test    r10, r10
0x18007d160  jz      short loc_18007D0E7
0x18007d162  xor     r9d, r9d
0x18007d165  mov     r8d, [rbx+8]
0x18007d169  mov     rax, r10
0x18007d16c  call    _guard_dispatch_icall
0x18007d171  jmp     loc_18007D0EE
```
