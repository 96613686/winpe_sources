# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800186d0`
- end: `0x18001878f`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `191`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016d08`
- `0x180019be8`
- `0x18001a0e0`

## callees

- `0x1800186d0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018714`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018741`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018714`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180018741`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001872c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001872c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800186ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800186ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001877d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001877d`

## string_xrefs

- `0x1800186f8`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001870a`: `RegDeleteKeyExW`
- `0x180018725`: `advapi32.dll`
- `0x180018737`: `RegDeleteKeyW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x1800186d0  push    rdi
0x1800186d2  sub     rsp, 40h
0x1800186d6  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800186df  mov     [rsp+48h+arg_0], rbx
0x1800186e4  mov     rdi, rdx
0x1800186e7  mov     rbx, rcx
0x1800186ea  cmp     qword ptr [rcx+8], 0
0x1800186ef  jnz     short loc_18001874B
0x1800186f1  cmp     qword ptr [rcx+10h], 0
0x1800186f6  jnz     short loc_18001874B
0x1800186f8  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800186ff  call    cs:__imp_GetModuleHandleW
0x180018705  test    rax, rax
0x180018708  jz      short loc_180018720
0x18001870a  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180018711  mov     rcx, rax; hModule
0x180018714  call    cs:__imp_GetProcAddress
0x18001871a  mov     [rbx+8], rax
0x18001871e  jmp     short loc_18001874B
0x180018720  xor     r8d, r8d; dwFlags
0x180018723  xor     edx, edx; hFile
0x180018725  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18001872c  call    cs:__imp_LoadLibraryExW
0x180018732  test    rax, rax
0x180018735  jz      short loc_18001874B
0x180018737  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001873e  mov     rcx, rax; hModule
0x180018741  call    cs:__imp_GetProcAddress
0x180018747  mov     [rbx+10h], rax
0x18001874b  mov     rax, [rbx+8]
0x18001874f  test    rax, rax
0x180018752  jz      short loc_180018767
0x180018754  xor     r9d, r9d
0x180018757  xor     r8d, r8d
0x18001875a  mov     rdx, rdi
0x18001875d  mov     rcx, [rbx]
0x180018760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018765  jmp     short loc_180018784
0x180018767  mov     rax, [rbx+10h]
0x18001876b  test    rax, rax
0x18001876e  jz      short loc_18001877D
0x180018770  mov     rdx, rdi
0x180018773  mov     rcx, [rbx]
0x180018776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001877b  jmp     short loc_180018784
0x18001877d  call    cs:__imp_GetLastError
0x180018783  nop
0x180018784  mov     rbx, [rsp+48h+arg_0]
0x180018789  add     rsp, 40h
0x18001878d  pop     rdi
0x18001878e  retn
```
