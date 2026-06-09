# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18001e32c`
- end: `0x18001e3e1`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001eb18`
- `0x18001ef4c`
- `0x180039a10`

## callees

- `0x18001e32c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e37e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e37e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e351`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001e351`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e366`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e393`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e366`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e393`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e3cf`

## string_xrefs

- `0x18001e34a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001e35c`: `RegDeleteKeyExW`
- `0x18001e377`: `advapi32.dll`
- `0x18001e389`: `RegDeleteKeyW`

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
0x18001e32c  mov     [rsp+arg_0], rbx
0x18001e331  push    rdi
0x18001e332  sub     rsp, 30h
0x18001e336  mov     rdi, rdx
0x18001e339  mov     rbx, rcx
0x18001e33c  cmp     qword ptr [rcx+8], 0
0x18001e341  jnz     short loc_18001E39D
0x18001e343  cmp     qword ptr [rcx+10h], 0
0x18001e348  jnz     short loc_18001E39D
0x18001e34a  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18001e351  call    cs:__imp_GetModuleHandleW
0x18001e357  test    rax, rax
0x18001e35a  jz      short loc_18001E372
0x18001e35c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18001e363  mov     rcx, rax; hModule
0x18001e366  call    cs:__imp_GetProcAddress
0x18001e36c  mov     [rbx+8], rax
0x18001e370  jmp     short loc_18001E39D
0x18001e372  xor     r8d, r8d; dwFlags
0x18001e375  xor     edx, edx; hFile
0x18001e377  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18001e37e  call    cs:__imp_LoadLibraryExW
0x18001e384  test    rax, rax
0x18001e387  jz      short loc_18001E39D
0x18001e389  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001e390  mov     rcx, rax; hModule
0x18001e393  call    cs:__imp_GetProcAddress
0x18001e399  mov     [rbx+10h], rax
0x18001e39d  mov     rax, [rbx+8]
0x18001e3a1  test    rax, rax
0x18001e3a4  jz      short loc_18001E3B9
0x18001e3a6  xor     r9d, r9d
0x18001e3a9  xor     r8d, r8d
0x18001e3ac  mov     rdx, rdi
0x18001e3af  mov     rcx, [rbx]
0x18001e3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3b7  jmp     short loc_18001E3D6
0x18001e3b9  mov     rax, [rbx+10h]
0x18001e3bd  test    rax, rax
0x18001e3c0  jz      short loc_18001E3CF
0x18001e3c2  mov     rdx, rdi
0x18001e3c5  mov     rcx, [rbx]
0x18001e3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3cd  jmp     short loc_18001E3D6
0x18001e3cf  call    cs:__imp_GetLastError
0x18001e3d5  nop
0x18001e3d6  mov     rbx, [rsp+38h+arg_0]
0x18001e3db  add     rsp, 30h
0x18001e3df  pop     rdi
0x18001e3e0  retn
```
