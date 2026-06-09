# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800041e0`
- end: `0x1800042b4`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800039fc`
- `0x180004a08`
- `0x180004f1c`

## callees

- `0x1800041e0`
- `0x180020010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000429b`
- `KERNEL32!GetLastError` at `0x18000429b`
- `KERNEL32!GetProcAddress` at `0x180004220`
- `KERNEL32!GetProcAddress` at `0x180004259`
- `KERNEL32!GetProcAddress` at `0x180004220`
- `KERNEL32!GetProcAddress` at `0x180004259`
- `KERNEL32!LoadLibraryExW` at `0x18000423e`
- `KERNEL32!LoadLibraryExW` at `0x18000423e`
- `KERNEL32!GetModuleHandleW` at `0x180004205`
- `KERNEL32!GetModuleHandleW` at `0x180004205`

## string_xrefs

- `0x1800041fe`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180004216`: `RegDeleteKeyExW`
- `0x180004237`: `advapi32.dll`
- `0x18000424f`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = LoadLibraryExW(L"advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800041e0  mov     [rsp+arg_0], rbx
0x1800041e5  push    rdi
0x1800041e6  sub     rsp, 30h
0x1800041ea  mov     rdi, rdx
0x1800041ed  mov     rbx, rcx
0x1800041f0  cmp     qword ptr [rcx+8], 0
0x1800041f5  jnz     short loc_180004269
0x1800041f7  cmp     qword ptr [rcx+10h], 0
0x1800041fc  jnz     short loc_180004269
0x1800041fe  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004205  call    cs:__imp_GetModuleHandleW
0x18000420c  nop     dword ptr [rax+rax+00h]
0x180004211  test    rax, rax
0x180004214  jz      short loc_180004232
0x180004216  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000421d  mov     rcx, rax; hModule
0x180004220  call    cs:__imp_GetProcAddress
0x180004227  nop     dword ptr [rax+rax+00h]
0x18000422c  mov     [rbx+8], rax
0x180004230  jmp     short loc_180004269
0x180004232  xor     r8d, r8d; dwFlags
0x180004235  xor     edx, edx; hFile
0x180004237  lea     rcx, LibFileName; "advapi32.dll"
0x18000423e  call    cs:__imp_LoadLibraryExW
0x180004245  nop     dword ptr [rax+rax+00h]
0x18000424a  test    rax, rax
0x18000424d  jz      short loc_180004269
0x18000424f  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180004256  mov     rcx, rax; hModule
0x180004259  call    cs:__imp_GetProcAddress
0x180004260  nop     dword ptr [rax+rax+00h]
0x180004265  mov     [rbx+10h], rax
0x180004269  mov     rax, [rbx+8]
0x18000426d  test    rax, rax
0x180004270  jz      short loc_180004285
0x180004272  xor     r9d, r9d
0x180004275  xor     r8d, r8d
0x180004278  mov     rdx, rdi
0x18000427b  mov     rcx, [rbx]
0x18000427e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004283  jmp     short loc_1800042A8
0x180004285  mov     rax, [rbx+10h]
0x180004289  test    rax, rax
0x18000428c  jz      short loc_18000429B
0x18000428e  mov     rdx, rdi
0x180004291  mov     rcx, [rbx]
0x180004294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004299  jmp     short loc_1800042A8
0x18000429b  call    cs:__imp_GetLastError
0x1800042a2  nop     dword ptr [rax+rax+00h]
0x1800042a7  nop
0x1800042a8  mov     rbx, [rsp+38h+arg_0]
0x1800042ad  add     rsp, 30h
0x1800042b1  pop     rdi
0x1800042b2  retn
```
