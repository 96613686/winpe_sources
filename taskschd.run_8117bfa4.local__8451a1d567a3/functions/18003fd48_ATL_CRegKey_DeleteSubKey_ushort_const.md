# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18003fd48`
- end: `0x18003fe1c`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `212`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18003f76c`

## callees

- `0x18003fd48`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003fd6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003fd6d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fd88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fdc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fd88`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003fdc1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003fda6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003fda6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe03`

## string_xrefs

- `0x18003fd66`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18003fd7e`: `RegDeleteKeyExW`
- `0x18003fd9f`: `advapi32.dll`
- `0x18003fdb7`: `RegDeleteKeyW`

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
0x18003fd48  mov     [rsp+arg_0], rbx
0x18003fd4d  push    rdi
0x18003fd4e  sub     rsp, 30h
0x18003fd52  mov     rdi, rdx
0x18003fd55  mov     rbx, rcx
0x18003fd58  cmp     qword ptr [rcx+8], 0
0x18003fd5d  jnz     short loc_18003FDD1
0x18003fd5f  cmp     qword ptr [rcx+10h], 0
0x18003fd64  jnz     short loc_18003FDD1
0x18003fd66  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18003fd6d  call    cs:__imp_GetModuleHandleW
0x18003fd74  nop     dword ptr [rax+rax+00h]
0x18003fd79  test    rax, rax
0x18003fd7c  jz      short loc_18003FD9A
0x18003fd7e  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18003fd85  mov     rcx, rax; hModule
0x18003fd88  call    cs:__imp_GetProcAddress
0x18003fd8f  nop     dword ptr [rax+rax+00h]
0x18003fd94  mov     [rbx+8], rax
0x18003fd98  jmp     short loc_18003FDD1
0x18003fd9a  xor     r8d, r8d; dwFlags
0x18003fd9d  xor     edx, edx; hFile
0x18003fd9f  lea     rcx, LibFileName; "advapi32.dll"
0x18003fda6  call    cs:__imp_LoadLibraryExW
0x18003fdad  nop     dword ptr [rax+rax+00h]
0x18003fdb2  test    rax, rax
0x18003fdb5  jz      short loc_18003FDD1
0x18003fdb7  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18003fdbe  mov     rcx, rax; hModule
0x18003fdc1  call    cs:__imp_GetProcAddress
0x18003fdc8  nop     dword ptr [rax+rax+00h]
0x18003fdcd  mov     [rbx+10h], rax
0x18003fdd1  mov     rax, [rbx+8]
0x18003fdd5  test    rax, rax
0x18003fdd8  jz      short loc_18003FDED
0x18003fdda  xor     r9d, r9d
0x18003fddd  xor     r8d, r8d
0x18003fde0  mov     rdx, rdi
0x18003fde3  mov     rcx, [rbx]
0x18003fde6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fdeb  jmp     short loc_18003FE10
0x18003fded  mov     rax, [rbx+10h]
0x18003fdf1  test    rax, rax
0x18003fdf4  jz      short loc_18003FE03
0x18003fdf6  mov     rdx, rdi
0x18003fdf9  mov     rcx, [rbx]
0x18003fdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe01  jmp     short loc_18003FE10
0x18003fe03  call    cs:__imp_GetLastError
0x18003fe0a  nop     dword ptr [rax+rax+00h]
0x18003fe0f  nop
0x18003fe10  mov     rbx, [rsp+38h+arg_0]
0x18003fe15  add     rsp, 30h
0x18003fe19  pop     rdi
0x18003fe1a  retn
```
