# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000465c`
- end: `0x180004711`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180005168`
- `0x1800055a0`

## callees

- `0x18000465c`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004696`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046c3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004696`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800046c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800046ae`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800046ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004681`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004681`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046ff`

## string_xrefs

- `0x18000467a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000468c`: `RegDeleteKeyExW`
- `0x1800046a7`: `advapi32.dll`
- `0x1800046b9`: `RegDeleteKeyW`

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
0x18000465c  mov     [rsp+arg_0], rbx
0x180004661  push    rdi
0x180004662  sub     rsp, 30h
0x180004666  mov     rdi, rdx
0x180004669  mov     rbx, rcx
0x18000466c  cmp     qword ptr [rcx+8], 0
0x180004671  jnz     short loc_1800046CD
0x180004673  cmp     qword ptr [rcx+10h], 0
0x180004678  jnz     short loc_1800046CD
0x18000467a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004681  call    cs:__imp_GetModuleHandleW
0x180004687  test    rax, rax
0x18000468a  jz      short loc_1800046A2
0x18000468c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004693  mov     rcx, rax; hModule
0x180004696  call    cs:__imp_GetProcAddress
0x18000469c  mov     [rbx+8], rax
0x1800046a0  jmp     short loc_1800046CD
0x1800046a2  xor     r8d, r8d; dwFlags
0x1800046a5  xor     edx, edx; hFile
0x1800046a7  lea     rcx, LibFileName; "advapi32.dll"
0x1800046ae  call    cs:__imp_LoadLibraryExW
0x1800046b4  test    rax, rax
0x1800046b7  jz      short loc_1800046CD
0x1800046b9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800046c0  mov     rcx, rax; hModule
0x1800046c3  call    cs:__imp_GetProcAddress
0x1800046c9  mov     [rbx+10h], rax
0x1800046cd  mov     rax, [rbx+8]
0x1800046d1  test    rax, rax
0x1800046d4  jz      short loc_1800046E9
0x1800046d6  xor     r9d, r9d
0x1800046d9  xor     r8d, r8d
0x1800046dc  mov     rdx, rdi
0x1800046df  mov     rcx, [rbx]
0x1800046e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046e7  jmp     short loc_180004706
0x1800046e9  mov     rax, [rbx+10h]
0x1800046ed  test    rax, rax
0x1800046f0  jz      short loc_1800046FF
0x1800046f2  mov     rdx, rdi
0x1800046f5  mov     rcx, [rbx]
0x1800046f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fd  jmp     short loc_180004706
0x1800046ff  call    cs:__imp_GetLastError
0x180004705  nop
0x180004706  mov     rbx, [rsp+38h+arg_0]
0x18000470b  add     rsp, 30h
0x18000470f  pop     rdi
0x180004710  retn
```
