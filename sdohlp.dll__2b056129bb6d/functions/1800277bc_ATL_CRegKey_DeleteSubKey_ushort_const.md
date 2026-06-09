# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800277bc`
- end: `0x180027871`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18002637c`
- `0x18002a148`
- `0x18002a62c`

## callees

- `0x1800277bc`
- `0x180058010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800277e1`
- `KERNEL32!GetModuleHandleW` at `0x1800277e1`
- `KERNEL32!LoadLibraryExW` at `0x18002780e`
- `KERNEL32!LoadLibraryExW` at `0x18002780e`
- `KERNEL32!GetProcAddress` at `0x1800277f6`
- `KERNEL32!GetProcAddress` at `0x180027823`
- `KERNEL32!GetProcAddress` at `0x1800277f6`
- `KERNEL32!GetProcAddress` at `0x180027823`
- `KERNEL32!GetLastError` at `0x18002785f`
- `KERNEL32!GetLastError` at `0x18002785f`

## string_xrefs

- `0x1800277da`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800277ec`: `RegDeleteKeyExW`
- `0x180027807`: `advapi32.dll`
- `0x180027819`: `RegDeleteKeyW`

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
0x1800277bc  mov     [rsp+arg_0], rbx
0x1800277c1  push    rdi
0x1800277c2  sub     rsp, 30h
0x1800277c6  mov     rdi, rdx
0x1800277c9  mov     rbx, rcx
0x1800277cc  cmp     qword ptr [rcx+8], 0
0x1800277d1  jnz     short loc_18002782D
0x1800277d3  cmp     qword ptr [rcx+10h], 0
0x1800277d8  jnz     short loc_18002782D
0x1800277da  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800277e1  call    cs:__imp_GetModuleHandleW
0x1800277e7  test    rax, rax
0x1800277ea  jz      short loc_180027802
0x1800277ec  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800277f3  mov     rcx, rax; hModule
0x1800277f6  call    cs:__imp_GetProcAddress
0x1800277fc  mov     [rbx+8], rax
0x180027800  jmp     short loc_18002782D
0x180027802  xor     r8d, r8d; dwFlags
0x180027805  xor     edx, edx; hFile
0x180027807  lea     rcx, LibFileName; "advapi32.dll"
0x18002780e  call    cs:__imp_LoadLibraryExW
0x180027814  test    rax, rax
0x180027817  jz      short loc_18002782D
0x180027819  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180027820  mov     rcx, rax; hModule
0x180027823  call    cs:__imp_GetProcAddress
0x180027829  mov     [rbx+10h], rax
0x18002782d  mov     rax, [rbx+8]
0x180027831  test    rax, rax
0x180027834  jz      short loc_180027849
0x180027836  xor     r9d, r9d
0x180027839  xor     r8d, r8d
0x18002783c  mov     rdx, rdi
0x18002783f  mov     rcx, [rbx]
0x180027842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027847  jmp     short loc_180027866
0x180027849  mov     rax, [rbx+10h]
0x18002784d  test    rax, rax
0x180027850  jz      short loc_18002785F
0x180027852  mov     rdx, rdi
0x180027855  mov     rcx, [rbx]
0x180027858  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002785d  jmp     short loc_180027866
0x18002785f  call    cs:__imp_GetLastError
0x180027865  nop
0x180027866  mov     rbx, [rsp+38h+arg_0]
0x18002786b  add     rsp, 30h
0x18002786f  pop     rdi
0x180027870  retn
```
