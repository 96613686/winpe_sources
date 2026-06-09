# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18002ff08`
- end: `0x18002ffbd`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180030698`
- `0x180030acc`

## callees

- `0x18002ff08`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ff5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002ff5a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ff2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002ff2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ff42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ff6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ff42`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002ff6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ffab`

## string_xrefs

- `0x18002ff26`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18002ff38`: `RegDeleteKeyExW`
- `0x18002ff53`: `advapi32.dll`
- `0x18002ff65`: `RegDeleteKeyW`

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
0x18002ff08  mov     [rsp+arg_0], rbx
0x18002ff0d  push    rdi
0x18002ff0e  sub     rsp, 30h
0x18002ff12  mov     rdi, rdx
0x18002ff15  mov     rbx, rcx
0x18002ff18  cmp     qword ptr [rcx+8], 0
0x18002ff1d  jnz     short loc_18002FF79
0x18002ff1f  cmp     qword ptr [rcx+10h], 0
0x18002ff24  jnz     short loc_18002FF79
0x18002ff26  lea     rcx, aApiMsWinCoreLo_0; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18002ff2d  call    cs:__imp_GetModuleHandleW
0x18002ff33  test    rax, rax
0x18002ff36  jz      short loc_18002FF4E
0x18002ff38  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18002ff3f  mov     rcx, rax; hModule
0x18002ff42  call    cs:__imp_GetProcAddress
0x18002ff48  mov     [rbx+8], rax
0x18002ff4c  jmp     short loc_18002FF79
0x18002ff4e  xor     r8d, r8d; dwFlags
0x18002ff51  xor     edx, edx; hFile
0x18002ff53  lea     rcx, LibFileName; "advapi32.dll"
0x18002ff5a  call    cs:__imp_LoadLibraryExW
0x18002ff60  test    rax, rax
0x18002ff63  jz      short loc_18002FF79
0x18002ff65  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18002ff6c  mov     rcx, rax; hModule
0x18002ff6f  call    cs:__imp_GetProcAddress
0x18002ff75  mov     [rbx+10h], rax
0x18002ff79  mov     rax, [rbx+8]
0x18002ff7d  test    rax, rax
0x18002ff80  jz      short loc_18002FF95
0x18002ff82  xor     r9d, r9d
0x18002ff85  xor     r8d, r8d
0x18002ff88  mov     rdx, rdi
0x18002ff8b  mov     rcx, [rbx]
0x18002ff8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff93  jmp     short loc_18002FFB2
0x18002ff95  mov     rax, [rbx+10h]
0x18002ff99  test    rax, rax
0x18002ff9c  jz      short loc_18002FFAB
0x18002ff9e  mov     rdx, rdi
0x18002ffa1  mov     rcx, [rbx]
0x18002ffa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa9  jmp     short loc_18002FFB2
0x18002ffab  call    cs:__imp_GetLastError
0x18002ffb1  nop
0x18002ffb2  mov     rbx, [rsp+38h+arg_0]
0x18002ffb7  add     rsp, 30h
0x18002ffbb  pop     rdi
0x18002ffbc  retn
```
