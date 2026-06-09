# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800191ec`
- end: `0x18001929d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180019b88`
- `0x180019fa0`

## callees

- `0x1800191ec`
- `0x18001b2a8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019226`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019250`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019226`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019250`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019211`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001928c`

## string_xrefs

- `0x18001920a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18001921c`: `RegDeleteKeyExW`
- `0x180019235`: `advapi32.dll`
- `0x180019246`: `RegDeleteKeyW`

## pseudocode

```c
DWORD __fastcall ATL::CRegKey::DeleteSubKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  HMODULE ModuleHandleW; // rax
  __int64 v5; // rdx
  HMODULE Library; // rax
  __int64 (__fastcall *v7)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD); // rax
  __int64 (__fastcall *v9)(_QWORD, const unsigned __int16 *); // rax

  if ( *(_OWORD *)((char *)this + 8) == 0 )
  {
    ModuleHandleW = GetModuleHandleW(L"API-MS-Win-Core-LocalRegistry-L1-1-0.dll");
    if ( ModuleHandleW )
    {
      *((_QWORD *)this + 1) = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
    }
    else
    {
      Library = IsolationAwareLoadLibraryExW(L"advapi32.dll", v5, 0);
      if ( Library )
        *((_QWORD *)this + 2) = GetProcAddress(Library, "RegDeleteKeyW");
    }
  }
  v7 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD))*((_QWORD *)this + 1);
  if ( v7 )
    return v7(*(_QWORD *)this, a2, 0, 0);
  v9 = (__int64 (__fastcall *)(_QWORD, const unsigned __int16 *))*((_QWORD *)this + 2);
  if ( v9 )
    return v9(*(_QWORD *)this, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800191ec  mov     [rsp+arg_0], rbx
0x1800191f1  push    rdi
0x1800191f2  sub     rsp, 30h
0x1800191f6  cmp     qword ptr [rcx+8], 0
0x1800191fb  mov     rdi, rdx
0x1800191fe  mov     rbx, rcx
0x180019201  jnz     short loc_18001925A
0x180019203  cmp     qword ptr [rcx+10h], 0
0x180019208  jnz     short loc_18001925A
0x18001920a  lea     rcx, aApiMsWinCoreLo_1; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180019211  call    cs:__imp_GetModuleHandleW
0x180019217  test    rax, rax
0x18001921a  jz      short loc_180019232
0x18001921c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180019223  mov     rcx, rax; hModule
0x180019226  call    cs:__imp_GetProcAddress
0x18001922c  mov     [rbx+8], rax
0x180019230  jmp     short loc_18001925A
0x180019232  xor     r8d, r8d
0x180019235  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x18001923c  call    IsolationAwareLoadLibraryExW
0x180019241  test    rax, rax
0x180019244  jz      short loc_18001925A
0x180019246  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18001924d  mov     rcx, rax; hModule
0x180019250  call    cs:__imp_GetProcAddress
0x180019256  mov     [rbx+10h], rax
0x18001925a  mov     rax, [rbx+8]
0x18001925e  test    rax, rax
0x180019261  jz      short loc_180019276
0x180019263  mov     rcx, [rbx]
0x180019266  xor     r9d, r9d
0x180019269  xor     r8d, r8d
0x18001926c  mov     rdx, rdi
0x18001926f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019274  jmp     short loc_180019292
0x180019276  mov     rax, [rbx+10h]
0x18001927a  test    rax, rax
0x18001927d  jz      short loc_18001928C
0x18001927f  mov     rcx, [rbx]
0x180019282  mov     rdx, rdi
0x180019285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001928a  jmp     short loc_180019292
0x18001928c  call    cs:__imp_GetLastError
0x180019292  mov     rbx, [rsp+38h+arg_0]
0x180019297  add     rsp, 30h
0x18001929b  pop     rdi
0x18001929c  retn
```
