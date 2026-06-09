# ATL::CRegKey::DeleteSubKey(char const *)

- ea: `0x180010e78`
- end: `0x180010f2c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBD@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180010440`
- `0x180011538`
- `0x180011b0c`

## callees

- `0x180010e78`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetModuleHandleA` at `0x180010e9d`
- `KERNEL32!GetModuleHandleA` at `0x180010e9d`
- `KERNEL32!LoadLibraryExA` at `0x180010eca`
- `KERNEL32!LoadLibraryExA` at `0x180010eca`
- `KERNEL32!GetProcAddress` at `0x180010eb2`
- `KERNEL32!GetProcAddress` at `0x180010edf`
- `KERNEL32!GetProcAddress` at `0x180010eb2`
- `KERNEL32!GetProcAddress` at `0x180010edf`
- `KERNEL32!GetLastError` at `0x180010f1b`
- `KERNEL32!GetLastError` at `0x180010f1b`

## string_xrefs

- `0x180010e96`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180010ea8`: `RegDeleteKeyExA`
- `0x180010ec1`: `advapi32.dll`
- `0x180010ed5`: `RegDeleteKeyA`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const char *a2)
{
  HMODULE ModuleHandleA; // rax
  HMODULE Library; // rax
  __int64 (__fastcall *v6)(_QWORD, const char *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v8)(_QWORD, const char *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleA = GetModuleHandleA("API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleA )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleA, "RegDeleteKeyExA");
    }
    else
    {
      Library = LoadLibraryExA("advapi32.dll", 0, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyA");
    }
  }
  v6 = (__int64 (__fastcall *)(_QWORD, const char *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v6 )
    return v6(*(_QWORD *)this, a2, 0, 0);
  v8 = (__int64 (__fastcall *)(_QWORD, const char *))*((_QWORD *)this + 2);
  if ( v8 )
    return v8(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x180010e78  mov     [rsp+arg_0], rbx
0x180010e7d  push    rdi
0x180010e7e  sub     rsp, 30h
0x180010e82  cmp     qword ptr [rcx+8], 0
0x180010e87  mov     rdi, rdx
0x180010e8a  mov     rbx, rcx
0x180010e8d  jnz     short loc_180010EE9
0x180010e8f  cmp     qword ptr [rcx+10h], 0
0x180010e94  jnz     short loc_180010EE9
0x180010e96  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180010e9d  call    cs:__imp_GetModuleHandleA
0x180010ea3  test    rax, rax
0x180010ea6  jz      short loc_180010EBE
0x180010ea8  lea     rdx, ProcName; "RegDeleteKeyExA"
0x180010eaf  mov     rcx, rax; hModule
0x180010eb2  call    cs:__imp_GetProcAddress
0x180010eb8  mov     [rbx+8], rax
0x180010ebc  jmp     short loc_180010EE9
0x180010ebe  xor     r8d, r8d; dwFlags
0x180010ec1  lea     rcx, LibFileName; "advapi32.dll"
0x180010ec8  xor     edx, edx; hFile
0x180010eca  call    cs:__imp_LoadLibraryExA
0x180010ed0  test    rax, rax
0x180010ed3  jz      short loc_180010EE9
0x180010ed5  lea     rdx, aRegdeletekeya; "RegDeleteKeyA"
0x180010edc  mov     rcx, rax; hModule
0x180010edf  call    cs:__imp_GetProcAddress
0x180010ee5  mov     [rbx+10h], rax
0x180010ee9  mov     rax, [rbx+8]
0x180010eed  test    rax, rax
0x180010ef0  jz      short loc_180010F05
0x180010ef2  mov     rcx, [rbx]
0x180010ef5  xor     r9d, r9d
0x180010ef8  xor     r8d, r8d
0x180010efb  mov     rdx, rdi
0x180010efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f03  jmp     short loc_180010F21
0x180010f05  mov     rax, [rbx+10h]
0x180010f09  test    rax, rax
0x180010f0c  jz      short loc_180010F1B
0x180010f0e  mov     rcx, [rbx]
0x180010f11  mov     rdx, rdi
0x180010f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f19  jmp     short loc_180010F21
0x180010f1b  call    cs:__imp_GetLastError
0x180010f21  mov     rbx, [rsp+38h+arg_0]
0x180010f26  add     rsp, 30h
0x180010f2a  pop     rdi
0x180010f2b  retn
```
