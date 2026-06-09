# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1400031b0`
- end: `0x140003265`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x140003ccc`
- `0x140004190`

## callees

- `0x1400031b0`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140003253`
- `KERNEL32!GetLastError` at `0x140003253`
- `KERNEL32!GetProcAddress` at `0x1400031ea`
- `KERNEL32!GetProcAddress` at `0x140003217`
- `KERNEL32!GetProcAddress` at `0x1400031ea`
- `KERNEL32!GetProcAddress` at `0x140003217`
- `KERNEL32!LoadLibraryExW` at `0x140003202`
- `KERNEL32!LoadLibraryExW` at `0x140003202`
- `KERNEL32!GetModuleHandleW` at `0x1400031d5`
- `KERNEL32!GetModuleHandleW` at `0x1400031d5`

## string_xrefs

- `0x1400031ce`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x1400031e0`: `RegDeleteKeyExW`
- `0x1400031fb`: `advapi32.dll`
- `0x14000320d`: `RegDeleteKeyW`

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
0x1400031b0  mov     [rsp+arg_0], rbx
0x1400031b5  push    rdi
0x1400031b6  sub     rsp, 30h
0x1400031ba  mov     rdi, rdx
0x1400031bd  mov     rbx, rcx
0x1400031c0  cmp     qword ptr [rcx+8], 0
0x1400031c5  jnz     short loc_140003221
0x1400031c7  cmp     qword ptr [rcx+10h], 0
0x1400031cc  jnz     short loc_140003221
0x1400031ce  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x1400031d5  call    cs:__imp_GetModuleHandleW
0x1400031db  test    rax, rax
0x1400031de  jz      short loc_1400031F6
0x1400031e0  lea     rdx, ProcName; "RegDeleteKeyExW"
0x1400031e7  mov     rcx, rax; hModule
0x1400031ea  call    cs:__imp_GetProcAddress
0x1400031f0  mov     [rbx+8], rax
0x1400031f4  jmp     short loc_140003221
0x1400031f6  xor     r8d, r8d; dwFlags
0x1400031f9  xor     edx, edx; hFile
0x1400031fb  lea     rcx, LibFileName; "advapi32.dll"
0x140003202  call    cs:__imp_LoadLibraryExW
0x140003208  test    rax, rax
0x14000320b  jz      short loc_140003221
0x14000320d  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x140003214  mov     rcx, rax; hModule
0x140003217  call    cs:__imp_GetProcAddress
0x14000321d  mov     [rbx+10h], rax
0x140003221  mov     rax, [rbx+8]
0x140003225  test    rax, rax
0x140003228  jz      short loc_14000323D
0x14000322a  xor     r9d, r9d
0x14000322d  xor     r8d, r8d
0x140003230  mov     rdx, rdi
0x140003233  mov     rcx, [rbx]
0x140003236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000323b  jmp     short loc_14000325A
0x14000323d  mov     rax, [rbx+10h]
0x140003241  test    rax, rax
0x140003244  jz      short loc_140003253
0x140003246  mov     rdx, rdi
0x140003249  mov     rcx, [rbx]
0x14000324c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003251  jmp     short loc_14000325A
0x140003253  call    cs:__imp_GetLastError
0x140003259  nop
0x14000325a  mov     rbx, [rsp+38h+arg_0]
0x14000325f  add     rsp, 30h
0x140003263  pop     rdi
0x140003264  retn
```
