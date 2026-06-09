# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18001c77c`
- end: `0x18001c831`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18001df08`
- `0x18001e340`

## callees

- `0x18001c77c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c7ce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001c7ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c7a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001c7a1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c7b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c7e3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c7b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001c7e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c81f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c81f`

## string_xrefs

- `0x18001c79a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001c7ac`: `RegDeleteKeyExW`
- `0x18001c7c7`: `advapi32.dll`
- `0x18001c7d9`: `RegDeleteKeyW`

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
0x18001c77c  mov     [rsp+arg_0], rbx
0x18001c781  push    rdi
0x18001c782  sub     rsp, 30h
0x18001c786  mov     rdi, rdx
0x18001c789  mov     rbx, rcx
0x18001c78c  cmp     qword ptr [rcx+8], 0
0x18001c791  jnz     short loc_18001C7ED
0x18001c793  cmp     qword ptr [rcx+10h], 0
0x18001c798  jnz     short loc_18001C7ED
0x18001c79a  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18001c7a1  call    cs:__imp_GetModuleHandleW
0x18001c7a7  test    rax, rax
0x18001c7aa  jz      short loc_18001C7C2
0x18001c7ac  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18001c7b3  mov     rcx, rax; hModule
0x18001c7b6  call    cs:__imp_GetProcAddress
0x18001c7bc  mov     [rbx+8], rax
0x18001c7c0  jmp     short loc_18001C7ED
0x18001c7c2  xor     r8d, r8d; dwFlags
0x18001c7c5  xor     edx, edx; hFile
0x18001c7c7  lea     rcx, LibFileName; "advapi32.dll"
0x18001c7ce  call    cs:__imp_LoadLibraryExW
0x18001c7d4  test    rax, rax
0x18001c7d7  jz      short loc_18001C7ED
0x18001c7d9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001c7e0  mov     rcx, rax; hModule
0x18001c7e3  call    cs:__imp_GetProcAddress
0x18001c7e9  mov     [rbx+10h], rax
0x18001c7ed  mov     rax, [rbx+8]
0x18001c7f1  test    rax, rax
0x18001c7f4  jz      short loc_18001C809
0x18001c7f6  xor     r9d, r9d
0x18001c7f9  xor     r8d, r8d
0x18001c7fc  mov     rdx, rdi
0x18001c7ff  mov     rcx, [rbx]
0x18001c802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c807  jmp     short loc_18001C826
0x18001c809  mov     rax, [rbx+10h]
0x18001c80d  test    rax, rax
0x18001c810  jz      short loc_18001C81F
0x18001c812  mov     rdx, rdi
0x18001c815  mov     rcx, [rbx]
0x18001c818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c81d  jmp     short loc_18001C826
0x18001c81f  call    cs:__imp_GetLastError
0x18001c825  nop
0x18001c826  mov     rbx, [rsp+38h+arg_0]
0x18001c82b  add     rsp, 30h
0x18001c82f  pop     rdi
0x18001c830  retn
```
