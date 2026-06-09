# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180003054`
- end: `0x180003109`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180003698`
- `0x180003b5c`

## callees

- `0x180003054`
- `0x180006010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800030a6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800030a6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000308e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800030bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000308e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800030bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003079`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180003079`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800030f7`

## string_xrefs

- `0x180003072`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003084`: `RegDeleteKeyExW`
- `0x18000309f`: `advapi32.dll`
- `0x1800030b1`: `RegDeleteKeyW`

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
0x180003054  mov     [rsp+arg_0], rbx
0x180003059  push    rdi
0x18000305a  sub     rsp, 30h
0x18000305e  mov     rdi, rdx
0x180003061  mov     rbx, rcx
0x180003064  cmp     qword ptr [rcx+8], 0
0x180003069  jnz     short loc_1800030C5
0x18000306b  cmp     qword ptr [rcx+10h], 0
0x180003070  jnz     short loc_1800030C5
0x180003072  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003079  call    cs:__imp_GetModuleHandleW
0x18000307f  test    rax, rax
0x180003082  jz      short loc_18000309A
0x180003084  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000308b  mov     rcx, rax; hModule
0x18000308e  call    cs:__imp_GetProcAddress
0x180003094  mov     [rbx+8], rax
0x180003098  jmp     short loc_1800030C5
0x18000309a  xor     r8d, r8d; dwFlags
0x18000309d  xor     edx, edx; hFile
0x18000309f  lea     rcx, LibFileName; "advapi32.dll"
0x1800030a6  call    cs:__imp_LoadLibraryExW
0x1800030ac  test    rax, rax
0x1800030af  jz      short loc_1800030C5
0x1800030b1  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800030b8  mov     rcx, rax; hModule
0x1800030bb  call    cs:__imp_GetProcAddress
0x1800030c1  mov     [rbx+10h], rax
0x1800030c5  mov     rax, [rbx+8]
0x1800030c9  test    rax, rax
0x1800030cc  jz      short loc_1800030E1
0x1800030ce  xor     r9d, r9d
0x1800030d1  xor     r8d, r8d
0x1800030d4  mov     rdx, rdi
0x1800030d7  mov     rcx, [rbx]
0x1800030da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030df  jmp     short loc_1800030FE
0x1800030e1  mov     rax, [rbx+10h]
0x1800030e5  test    rax, rax
0x1800030e8  jz      short loc_1800030F7
0x1800030ea  mov     rdx, rdi
0x1800030ed  mov     rcx, [rbx]
0x1800030f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f5  jmp     short loc_1800030FE
0x1800030f7  call    cs:__imp_GetLastError
0x1800030fd  nop
0x1800030fe  mov     rbx, [rsp+38h+arg_0]
0x180003103  add     rsp, 30h
0x180003107  pop     rdi
0x180003108  retn
```
