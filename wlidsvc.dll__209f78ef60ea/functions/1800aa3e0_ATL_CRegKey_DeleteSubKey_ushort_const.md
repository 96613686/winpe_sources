# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800aa3e0`
- end: `0x1800aa495`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18005bae0`
- `0x1800aa4a0`
- `0x1800aa5b0`

## callees

- `0x1800aa3e0`
- `0x180128010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa483`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aa41a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aa447`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aa41a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800aa447`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800aa432`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800aa432`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800aa405`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800aa405`

## string_xrefs

- `0x1800aa3fe`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1800aa410`: `RegDeleteKeyExW`
- `0x1800aa42b`: `advapi32.dll`
- `0x1800aa43d`: `RegDeleteKeyW`

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
0x1800aa3e0  mov     [rsp+arg_0], rbx
0x1800aa3e5  push    rdi
0x1800aa3e6  sub     rsp, 30h
0x1800aa3ea  mov     rdi, rdx
0x1800aa3ed  mov     rbx, rcx
0x1800aa3f0  cmp     qword ptr [rcx+8], 0
0x1800aa3f5  jnz     short loc_1800AA451
0x1800aa3f7  cmp     qword ptr [rcx+10h], 0
0x1800aa3fc  jnz     short loc_1800AA451
0x1800aa3fe  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1800aa405  call    cs:__imp_GetModuleHandleW
0x1800aa40b  test    rax, rax
0x1800aa40e  jz      short loc_1800AA426
0x1800aa410  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x1800aa417  mov     rcx, rax; hModule
0x1800aa41a  call    cs:__imp_GetProcAddress
0x1800aa420  mov     [rbx+8], rax
0x1800aa424  jmp     short loc_1800AA451
0x1800aa426  xor     r8d, r8d; dwFlags
0x1800aa429  xor     edx, edx; hFile
0x1800aa42b  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x1800aa432  call    cs:__imp_LoadLibraryExW
0x1800aa438  test    rax, rax
0x1800aa43b  jz      short loc_1800AA451
0x1800aa43d  lea     rdx, aRegdeletekeyw_0; "RegDeleteKeyW"
0x1800aa444  mov     rcx, rax; hModule
0x1800aa447  call    cs:__imp_GetProcAddress
0x1800aa44d  mov     [rbx+10h], rax
0x1800aa451  mov     rax, [rbx+8]
0x1800aa455  test    rax, rax
0x1800aa458  jz      short loc_1800AA46D
0x1800aa45a  xor     r9d, r9d
0x1800aa45d  xor     r8d, r8d
0x1800aa460  mov     rdx, rdi
0x1800aa463  mov     rcx, [rbx]
0x1800aa466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa46b  jmp     short loc_1800AA48A
0x1800aa46d  mov     rax, [rbx+10h]
0x1800aa471  test    rax, rax
0x1800aa474  jz      short loc_1800AA483
0x1800aa476  mov     rdx, rdi
0x1800aa479  mov     rcx, [rbx]
0x1800aa47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa481  jmp     short loc_1800AA48A
0x1800aa483  call    cs:__imp_GetLastError
0x1800aa489  nop
0x1800aa48a  mov     rbx, [rsp+38h+arg_0]
0x1800aa48f  add     rsp, 30h
0x1800aa493  pop     rdi
0x1800aa494  retn
```
