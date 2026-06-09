# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800195c4`
- end: `0x180019679`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180016f84`
- `0x18001a988`
- `0x18001ae58`

## callees

- `0x1800195c4`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019616`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019616`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800195e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800195e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001962b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800195fe`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001962b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019667`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019667`

## string_xrefs

- `0x18001960f`: `advapi32.dll`
- `0x1800195e2`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800195f4`: `RegDeleteKeyExW`
- `0x180019621`: `RegDeleteKeyW`

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
0x1800195c4  mov     [rsp+arg_0], rbx
0x1800195c9  push    rdi
0x1800195ca  sub     rsp, 30h
0x1800195ce  mov     rdi, rdx
0x1800195d1  mov     rbx, rcx
0x1800195d4  cmp     qword ptr [rcx+8], 0
0x1800195d9  jnz     short loc_180019635
0x1800195db  cmp     qword ptr [rcx+10h], 0
0x1800195e0  jnz     short loc_180019635
0x1800195e2  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800195e9  call    cs:__imp_GetModuleHandleW
0x1800195ef  test    rax, rax
0x1800195f2  jz      short loc_18001960A
0x1800195f4  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800195fb  mov     rcx, rax; hModule
0x1800195fe  call    cs:__imp_GetProcAddress
0x180019604  mov     [rbx+8], rax
0x180019608  jmp     short loc_180019635
0x18001960a  xor     r8d, r8d; dwFlags
0x18001960d  xor     edx, edx; hFile
0x18001960f  lea     rcx, LibFileName; "advapi32.dll"
0x180019616  call    cs:__imp_LoadLibraryExW
0x18001961c  test    rax, rax
0x18001961f  jz      short loc_180019635
0x180019621  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180019628  mov     rcx, rax; hModule
0x18001962b  call    cs:__imp_GetProcAddress
0x180019631  mov     [rbx+10h], rax
0x180019635  mov     rax, [rbx+8]
0x180019639  test    rax, rax
0x18001963c  jz      short loc_180019651
0x18001963e  xor     r9d, r9d
0x180019641  xor     r8d, r8d
0x180019644  mov     rdx, rdi
0x180019647  mov     rcx, [rbx]
0x18001964a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001964f  jmp     short loc_18001966E
0x180019651  mov     rax, [rbx+10h]
0x180019655  test    rax, rax
0x180019658  jz      short loc_180019667
0x18001965a  mov     rdx, rdi
0x18001965d  mov     rcx, [rbx]
0x180019660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019665  jmp     short loc_18001966E
0x180019667  call    cs:__imp_GetLastError
0x18001966d  nop
0x18001966e  mov     rbx, [rsp+38h+arg_0]
0x180019673  add     rsp, 30h
0x180019677  pop     rdi
0x180019678  retn
```
