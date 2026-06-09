# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18000805c`
- end: `0x180008110`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004640`
- `0x18000d168`
- `0x18000d678`

## callees

- `0x18000805c`
- `0x180037010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800080ff`
- `KERNEL32!GetLastError` at `0x1800080ff`
- `KERNEL32!GetProcAddress` at `0x180008096`
- `KERNEL32!GetProcAddress` at `0x1800080c3`
- `KERNEL32!GetProcAddress` at `0x180008096`
- `KERNEL32!GetProcAddress` at `0x1800080c3`
- `KERNEL32!LoadLibraryExW` at `0x1800080ae`
- `KERNEL32!LoadLibraryExW` at `0x1800080ae`
- `KERNEL32!GetModuleHandleW` at `0x180008081`
- `KERNEL32!GetModuleHandleW` at `0x180008081`

## string_xrefs

- `0x18000807a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000808c`: `RegDeleteKeyExW`
- `0x1800080a5`: `advapi32.dll`
- `0x1800080b9`: `RegDeleteKeyW`

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
0x18000805c  mov     [rsp+arg_0], rbx
0x180008061  push    rdi
0x180008062  sub     rsp, 30h
0x180008066  cmp     qword ptr [rcx+8], 0
0x18000806b  mov     rdi, rdx
0x18000806e  mov     rbx, rcx
0x180008071  jnz     short loc_1800080CD
0x180008073  cmp     qword ptr [rcx+10h], 0
0x180008078  jnz     short loc_1800080CD
0x18000807a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180008081  call    cs:__imp_GetModuleHandleW
0x180008087  test    rax, rax
0x18000808a  jz      short loc_1800080A2
0x18000808c  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180008093  mov     rcx, rax; hModule
0x180008096  call    cs:__imp_GetProcAddress
0x18000809c  mov     [rbx+8], rax
0x1800080a0  jmp     short loc_1800080CD
0x1800080a2  xor     r8d, r8d; dwFlags
0x1800080a5  lea     rcx, LibFileName; "advapi32.dll"
0x1800080ac  xor     edx, edx; hFile
0x1800080ae  call    cs:__imp_LoadLibraryExW
0x1800080b4  test    rax, rax
0x1800080b7  jz      short loc_1800080CD
0x1800080b9  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800080c0  mov     rcx, rax; hModule
0x1800080c3  call    cs:__imp_GetProcAddress
0x1800080c9  mov     [rbx+10h], rax
0x1800080cd  mov     rax, [rbx+8]
0x1800080d1  test    rax, rax
0x1800080d4  jz      short loc_1800080E9
0x1800080d6  mov     rcx, [rbx]
0x1800080d9  xor     r9d, r9d
0x1800080dc  xor     r8d, r8d
0x1800080df  mov     rdx, rdi
0x1800080e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e7  jmp     short loc_180008105
0x1800080e9  mov     rax, [rbx+10h]
0x1800080ed  test    rax, rax
0x1800080f0  jz      short loc_1800080FF
0x1800080f2  mov     rcx, [rbx]
0x1800080f5  mov     rdx, rdi
0x1800080f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080fd  jmp     short loc_180008105
0x1800080ff  call    cs:__imp_GetLastError
0x180008105  mov     rbx, [rsp+38h+arg_0]
0x18000810a  add     rsp, 30h
0x18000810e  pop     rdi
0x18000810f  retn
```
