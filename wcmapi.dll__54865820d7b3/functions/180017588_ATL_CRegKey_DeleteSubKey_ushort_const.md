# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180017588`
- end: `0x18001765c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180017b50`

## callees

- `0x180017588`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800175e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800175e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800175ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800175ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800175c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017601`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800175c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180017601`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017643`

## string_xrefs

- `0x1800175a6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800175be`: `RegDeleteKeyExW`
- `0x1800175df`: `advapi32.dll`
- `0x1800175f7`: `RegDeleteKeyW`

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
0x180017588  mov     [rsp+arg_0], rbx
0x18001758d  push    rdi
0x18001758e  sub     rsp, 30h
0x180017592  mov     rdi, rdx
0x180017595  mov     rbx, rcx
0x180017598  cmp     qword ptr [rcx+8], 0
0x18001759d  jnz     short loc_180017611
0x18001759f  cmp     qword ptr [rcx+10h], 0
0x1800175a4  jnz     short loc_180017611
0x1800175a6  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800175ad  call    cs:__imp_GetModuleHandleW
0x1800175b4  nop     dword ptr [rax+rax+00h]
0x1800175b9  test    rax, rax
0x1800175bc  jz      short loc_1800175DA
0x1800175be  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1800175c5  mov     rcx, rax; hModule
0x1800175c8  call    cs:__imp_GetProcAddress
0x1800175cf  nop     dword ptr [rax+rax+00h]
0x1800175d4  mov     [rbx+8], rax
0x1800175d8  jmp     short loc_180017611
0x1800175da  xor     r8d, r8d; dwFlags
0x1800175dd  xor     edx, edx; hFile
0x1800175df  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800175e6  call    cs:__imp_LoadLibraryExW
0x1800175ed  nop     dword ptr [rax+rax+00h]
0x1800175f2  test    rax, rax
0x1800175f5  jz      short loc_180017611
0x1800175f7  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800175fe  mov     rcx, rax; hModule
0x180017601  call    cs:__imp_GetProcAddress
0x180017608  nop     dword ptr [rax+rax+00h]
0x18001760d  mov     [rbx+10h], rax
0x180017611  mov     rax, [rbx+8]
0x180017615  test    rax, rax
0x180017618  jz      short loc_18001762D
0x18001761a  xor     r9d, r9d
0x18001761d  xor     r8d, r8d
0x180017620  mov     rdx, rdi
0x180017623  mov     rcx, [rbx]
0x180017626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001762b  jmp     short loc_180017650
0x18001762d  mov     rax, [rbx+10h]
0x180017631  test    rax, rax
0x180017634  jz      short loc_180017643
0x180017636  mov     rdx, rdi
0x180017639  mov     rcx, [rbx]
0x18001763c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017641  jmp     short loc_180017650
0x180017643  call    cs:__imp_GetLastError
0x18001764a  nop     dword ptr [rax+rax+00h]
0x18001764f  nop
0x180017650  mov     rbx, [rsp+38h+arg_0]
0x180017655  add     rsp, 30h
0x180017659  pop     rdi
0x18001765a  retn
```
