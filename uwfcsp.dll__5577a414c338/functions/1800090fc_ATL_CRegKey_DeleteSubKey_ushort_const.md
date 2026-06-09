# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800090fc`
- end: `0x1800091b0`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a068`
- `0x18000a50c`

## callees

- `0x1800090fc`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009163`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009136`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009163`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000914e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000914e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009121`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000919f`

## string_xrefs

- `0x18000911a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000912c`: `RegDeleteKeyExW`
- `0x180009145`: `advapi32.dll`
- `0x180009159`: `RegDeleteKeyW`

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
0x1800090fc  mov     [rsp+arg_0], rbx
0x180009101  push    rdi
0x180009102  sub     rsp, 30h
0x180009106  cmp     qword ptr [rcx+8], 0
0x18000910b  mov     rdi, rdx
0x18000910e  mov     rbx, rcx
0x180009111  jnz     short loc_18000916D
0x180009113  cmp     qword ptr [rcx+10h], 0
0x180009118  jnz     short loc_18000916D
0x18000911a  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180009121  call    cs:__imp_GetModuleHandleW
0x180009127  test    rax, rax
0x18000912a  jz      short loc_180009142
0x18000912c  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x180009133  mov     rcx, rax; hModule
0x180009136  call    cs:__imp_GetProcAddress
0x18000913c  mov     [rbx+8], rax
0x180009140  jmp     short loc_18000916D
0x180009142  xor     r8d, r8d; dwFlags
0x180009145  lea     rcx, LibFileName; "advapi32.dll"
0x18000914c  xor     edx, edx; hFile
0x18000914e  call    cs:__imp_LoadLibraryExW
0x180009154  test    rax, rax
0x180009157  jz      short loc_18000916D
0x180009159  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180009160  mov     rcx, rax; hModule
0x180009163  call    cs:__imp_GetProcAddress
0x180009169  mov     [rbx+10h], rax
0x18000916d  mov     rax, [rbx+8]
0x180009171  test    rax, rax
0x180009174  jz      short loc_180009189
0x180009176  mov     rcx, [rbx]
0x180009179  xor     r9d, r9d
0x18000917c  xor     r8d, r8d
0x18000917f  mov     rdx, rdi
0x180009182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009187  jmp     short loc_1800091A5
0x180009189  mov     rax, [rbx+10h]
0x18000918d  test    rax, rax
0x180009190  jz      short loc_18000919F
0x180009192  mov     rcx, [rbx]
0x180009195  mov     rdx, rdi
0x180009198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919d  jmp     short loc_1800091A5
0x18000919f  call    cs:__imp_GetLastError
0x1800091a5  mov     rbx, [rsp+38h+arg_0]
0x1800091aa  add     rsp, 30h
0x1800091ae  pop     rdi
0x1800091af  retn
```
