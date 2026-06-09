# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180008308`
- end: `0x1800083bc`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `DWORD __fastcall(ATL::CRegKey *this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180007c30`
- `0x180008b98`
- `0x18000902c`

## callees

- `0x180008308`
- `0x180016010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800083ab`
- `KERNEL32!GetLastError` at `0x1800083ab`
- `KERNEL32!GetProcAddress` at `0x180008342`
- `KERNEL32!GetProcAddress` at `0x18000836f`
- `KERNEL32!GetProcAddress` at `0x180008342`
- `KERNEL32!GetProcAddress` at `0x18000836f`
- `KERNEL32!LoadLibraryExW` at `0x18000835a`
- `KERNEL32!LoadLibraryExW` at `0x18000835a`
- `KERNEL32!GetModuleHandleW` at `0x18000832d`
- `KERNEL32!GetModuleHandleW` at `0x18000832d`

## string_xrefs

- `0x180008326`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180008338`: `RegDeleteKeyExW`
- `0x180008351`: `advapi32.dll`
- `0x180008365`: `RegDeleteKeyW`

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
0x180008308  mov     [rsp+arg_0], rbx
0x18000830d  push    rdi
0x18000830e  sub     rsp, 30h
0x180008312  cmp     qword ptr [rcx+8], 0
0x180008317  mov     rdi, rdx
0x18000831a  mov     rbx, rcx
0x18000831d  jnz     short loc_180008379
0x18000831f  cmp     qword ptr [rcx+10h], 0
0x180008324  jnz     short loc_180008379
0x180008326  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000832d  call    cs:__imp_GetModuleHandleW
0x180008333  test    rax, rax
0x180008336  jz      short loc_18000834E
0x180008338  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000833f  mov     rcx, rax; hModule
0x180008342  call    cs:__imp_GetProcAddress
0x180008348  mov     [rbx+8], rax
0x18000834c  jmp     short loc_180008379
0x18000834e  xor     r8d, r8d; dwFlags
0x180008351  lea     rcx, LibFileName; "advapi32.dll"
0x180008358  xor     edx, edx; hFile
0x18000835a  call    cs:__imp_LoadLibraryExW
0x180008360  test    rax, rax
0x180008363  jz      short loc_180008379
0x180008365  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000836c  mov     rcx, rax; hModule
0x18000836f  call    cs:__imp_GetProcAddress
0x180008375  mov     [rbx+10h], rax
0x180008379  mov     rax, [rbx+8]
0x18000837d  test    rax, rax
0x180008380  jz      short loc_180008395
0x180008382  mov     rcx, [rbx]
0x180008385  xor     r9d, r9d
0x180008388  xor     r8d, r8d
0x18000838b  mov     rdx, rdi
0x18000838e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008393  jmp     short loc_1800083B1
0x180008395  mov     rax, [rbx+10h]
0x180008399  test    rax, rax
0x18000839c  jz      short loc_1800083AB
0x18000839e  mov     rcx, [rbx]
0x1800083a1  mov     rdx, rdi
0x1800083a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083a9  jmp     short loc_1800083B1
0x1800083ab  call    cs:__imp_GetLastError
0x1800083b1  mov     rbx, [rsp+38h+arg_0]
0x1800083b6  add     rsp, 30h
0x1800083ba  pop     rdi
0x1800083bb  retn
```
