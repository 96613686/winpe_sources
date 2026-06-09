# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180004724`
- end: `0x1800047f7`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `211`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b204`
- `0x18000b6fc`
- `0x180010cb8`

## callees

- `0x180004724`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800047df`
- `KERNEL32!GetLastError` at `0x1800047df`
- `KERNEL32!GetProcAddress` at `0x180004764`
- `KERNEL32!GetProcAddress` at `0x18000479d`
- `KERNEL32!GetProcAddress` at `0x180004764`
- `KERNEL32!GetProcAddress` at `0x18000479d`
- `KERNEL32!LoadLibraryExW` at `0x180004782`
- `KERNEL32!LoadLibraryExW` at `0x180004782`
- `KERNEL32!GetModuleHandleW` at `0x180004749`
- `KERNEL32!GetModuleHandleW` at `0x180004749`

## string_xrefs

- `0x180004742`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18000475a`: `RegDeleteKeyExW`
- `0x180004779`: `advapi32.dll`
- `0x180004793`: `RegDeleteKeyW`

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
0x180004724  mov     [rsp+arg_0], rbx
0x180004729  push    rdi
0x18000472a  sub     rsp, 30h
0x18000472e  cmp     qword ptr [rcx+8], 0
0x180004733  mov     rdi, rdx
0x180004736  mov     rbx, rcx
0x180004739  jnz     short loc_1800047AD
0x18000473b  cmp     qword ptr [rcx+10h], 0
0x180004740  jnz     short loc_1800047AD
0x180004742  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180004749  call    cs:__imp_GetModuleHandleW
0x180004750  nop     dword ptr [rax+rax+00h]
0x180004755  test    rax, rax
0x180004758  jz      short loc_180004776
0x18000475a  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180004761  mov     rcx, rax; hModule
0x180004764  call    cs:__imp_GetProcAddress
0x18000476b  nop     dword ptr [rax+rax+00h]
0x180004770  mov     [rbx+8], rax
0x180004774  jmp     short loc_1800047AD
0x180004776  xor     r8d, r8d; dwFlags
0x180004779  lea     rcx, LibFileName; "advapi32.dll"
0x180004780  xor     edx, edx; hFile
0x180004782  call    cs:__imp_LoadLibraryExW
0x180004789  nop     dword ptr [rax+rax+00h]
0x18000478e  test    rax, rax
0x180004791  jz      short loc_1800047AD
0x180004793  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18000479a  mov     rcx, rax; hModule
0x18000479d  call    cs:__imp_GetProcAddress
0x1800047a4  nop     dword ptr [rax+rax+00h]
0x1800047a9  mov     [rbx+10h], rax
0x1800047ad  mov     rax, [rbx+8]
0x1800047b1  test    rax, rax
0x1800047b4  jz      short loc_1800047C9
0x1800047b6  mov     rcx, [rbx]
0x1800047b9  xor     r9d, r9d
0x1800047bc  xor     r8d, r8d
0x1800047bf  mov     rdx, rdi
0x1800047c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047c7  jmp     short loc_1800047EB
0x1800047c9  mov     rax, [rbx+10h]
0x1800047cd  test    rax, rax
0x1800047d0  jz      short loc_1800047DF
0x1800047d2  mov     rcx, [rbx]
0x1800047d5  mov     rdx, rdi
0x1800047d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047dd  jmp     short loc_1800047EB
0x1800047df  call    cs:__imp_GetLastError
0x1800047e6  nop     dword ptr [rax+rax+00h]
0x1800047eb  mov     rbx, [rsp+38h+arg_0]
0x1800047f0  add     rsp, 30h
0x1800047f4  pop     rdi
0x1800047f5  retn
```
