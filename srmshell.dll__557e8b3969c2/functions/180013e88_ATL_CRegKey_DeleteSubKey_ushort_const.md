# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180013e88`
- end: `0x180013f3a`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `178`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013004`
- `0x180014668`
- `0x180014b28`

## callees

- `0x180011714`
- `0x180013e88`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013ead`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180013ead`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ec2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013eec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013ec2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180013eec`

## string_xrefs

- `0x180013ea6`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180013eb8`: `RegDeleteKeyExW`
- `0x180013ed1`: `advapi32.dll`
- `0x180013ee2`: `RegDeleteKeyW`

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
      Library = (HMODULE)IsolationAwareLoadLibraryExW(L"advapi32.dll");
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
0x180013e88  mov     [rsp+arg_0], rbx
0x180013e8d  push    rdi
0x180013e8e  sub     rsp, 30h
0x180013e92  mov     rdi, rdx
0x180013e95  mov     rbx, rcx
0x180013e98  cmp     qword ptr [rcx+8], 0
0x180013e9d  jnz     short loc_180013EF6
0x180013e9f  cmp     qword ptr [rcx+10h], 0
0x180013ea4  jnz     short loc_180013EF6
0x180013ea6  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180013ead  call    cs:__imp_GetModuleHandleW
0x180013eb3  test    rax, rax
0x180013eb6  jz      short loc_180013ECE
0x180013eb8  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180013ebf  mov     rcx, rax; hModule
0x180013ec2  call    cs:__imp_GetProcAddress
0x180013ec8  mov     [rbx+8], rax
0x180013ecc  jmp     short loc_180013EF6
0x180013ece  xor     r8d, r8d
0x180013ed1  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180013ed8  call    IsolationAwareLoadLibraryExW
0x180013edd  test    rax, rax
0x180013ee0  jz      short loc_180013EF6
0x180013ee2  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180013ee9  mov     rcx, rax; hModule
0x180013eec  call    cs:__imp_GetProcAddress
0x180013ef2  mov     [rbx+10h], rax
0x180013ef6  mov     rax, [rbx+8]
0x180013efa  test    rax, rax
0x180013efd  jz      short loc_180013F12
0x180013eff  xor     r9d, r9d
0x180013f02  xor     r8d, r8d
0x180013f05  mov     rdx, rdi
0x180013f08  mov     rcx, [rbx]
0x180013f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f10  jmp     short loc_180013F2F
0x180013f12  mov     rax, [rbx+10h]
0x180013f16  test    rax, rax
0x180013f19  jz      short loc_180013F28
0x180013f1b  mov     rdx, rdi
0x180013f1e  mov     rcx, [rbx]
0x180013f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f26  jmp     short loc_180013F2F
0x180013f28  call    cs:__imp_GetLastError
0x180013f2e  nop
0x180013f2f  mov     rbx, [rsp+38h+arg_0]
0x180013f34  add     rsp, 30h
0x180013f38  pop     rdi
0x180013f39  retn
```
