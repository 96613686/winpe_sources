# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x140003698`
- end: `0x14000374c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140002bfc`
- `0x140004258`
- `0x140004954`

## callees

- `0x140003698`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400036d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400036ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400036d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400036ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400036bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400036bd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400036ea`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400036ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000373b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000373b`

## string_xrefs

- `0x1400036b6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1400036c8`: `RegDeleteKeyExW`
- `0x1400036e1`: `advapi32.dll`
- `0x1400036f5`: `RegDeleteKeyW`

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
0x140003698  mov     [rsp+arg_0], rbx
0x14000369d  push    rdi
0x14000369e  sub     rsp, 30h
0x1400036a2  cmp     qword ptr [rcx+8], 0
0x1400036a7  mov     rdi, rdx
0x1400036aa  mov     rbx, rcx
0x1400036ad  jnz     short loc_140003709
0x1400036af  cmp     qword ptr [rcx+10h], 0
0x1400036b4  jnz     short loc_140003709
0x1400036b6  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1400036bd  call    cs:__imp_GetModuleHandleW
0x1400036c3  test    rax, rax
0x1400036c6  jz      short loc_1400036DE
0x1400036c8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1400036cf  mov     rcx, rax; hModule
0x1400036d2  call    cs:__imp_GetProcAddress
0x1400036d8  mov     [rbx+8], rax
0x1400036dc  jmp     short loc_140003709
0x1400036de  xor     r8d, r8d; dwFlags
0x1400036e1  lea     rcx, LibFileName; "advapi32.dll"
0x1400036e8  xor     edx, edx; hFile
0x1400036ea  call    cs:__imp_LoadLibraryExW
0x1400036f0  test    rax, rax
0x1400036f3  jz      short loc_140003709
0x1400036f5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1400036fc  mov     rcx, rax; hModule
0x1400036ff  call    cs:__imp_GetProcAddress
0x140003705  mov     [rbx+10h], rax
0x140003709  mov     rax, [rbx+8]
0x14000370d  test    rax, rax
0x140003710  jz      short loc_140003725
0x140003712  mov     rcx, [rbx]
0x140003715  xor     r9d, r9d
0x140003718  xor     r8d, r8d
0x14000371b  mov     rdx, rdi
0x14000371e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003723  jmp     short loc_140003741
0x140003725  mov     rax, [rbx+10h]
0x140003729  test    rax, rax
0x14000372c  jz      short loc_14000373B
0x14000372e  mov     rcx, [rbx]
0x140003731  mov     rdx, rdi
0x140003734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003739  jmp     short loc_140003741
0x14000373b  call    cs:__imp_GetLastError
0x140003741  mov     rbx, [rsp+38h+arg_0]
0x140003746  add     rsp, 30h
0x14000374a  pop     rdi
0x14000374b  retn
```
