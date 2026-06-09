# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180007534`
- end: `0x1800075e6`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `178`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004fc8`
- `0x18000a8e8`
- `0x18000af10`

## callees

- `0x180007534`
- `0x18000c62c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007559`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007559`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000756e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007598`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000756e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075d4`

## string_xrefs

- `0x180007552`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180007564`: `RegDeleteKeyExW`
- `0x18000757d`: `advapi32.dll`
- `0x18000758e`: `RegDeleteKeyW`

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
0x180007534  mov     [rsp+arg_0], rbx
0x180007539  push    rdi
0x18000753a  sub     rsp, 30h
0x18000753e  mov     rdi, rdx
0x180007541  mov     rbx, rcx
0x180007544  cmp     qword ptr [rcx+8], 0
0x180007549  jnz     short loc_1800075A2
0x18000754b  cmp     qword ptr [rcx+10h], 0
0x180007550  jnz     short loc_1800075A2
0x180007552  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180007559  call    cs:__imp_GetModuleHandleW
0x18000755f  test    rax, rax
0x180007562  jz      short loc_18000757A
0x180007564  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000756b  mov     rcx, rax; hModule
0x18000756e  call    cs:__imp_GetProcAddress
0x180007574  mov     [rbx+8], rax
0x180007578  jmp     short loc_1800075A2
0x18000757a  xor     r8d, r8d
0x18000757d  lea     rcx, aAdvapi32Dll; "advapi32.dll"
0x180007584  call    IsolationAwareLoadLibraryExW
0x180007589  test    rax, rax
0x18000758c  jz      short loc_1800075A2
0x18000758e  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180007595  mov     rcx, rax; hModule
0x180007598  call    cs:__imp_GetProcAddress
0x18000759e  mov     [rbx+10h], rax
0x1800075a2  mov     rax, [rbx+8]
0x1800075a6  test    rax, rax
0x1800075a9  jz      short loc_1800075BE
0x1800075ab  xor     r9d, r9d
0x1800075ae  xor     r8d, r8d
0x1800075b1  mov     rdx, rdi
0x1800075b4  mov     rcx, [rbx]
0x1800075b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075bc  jmp     short loc_1800075DB
0x1800075be  mov     rax, [rbx+10h]
0x1800075c2  test    rax, rax
0x1800075c5  jz      short loc_1800075D4
0x1800075c7  mov     rdx, rdi
0x1800075ca  mov     rcx, [rbx]
0x1800075cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075d2  jmp     short loc_1800075DB
0x1800075d4  call    cs:__imp_GetLastError
0x1800075da  nop
0x1800075db  mov     rbx, [rsp+38h+arg_0]
0x1800075e0  add     rsp, 30h
0x1800075e4  pop     rdi
0x1800075e5  retn
```
