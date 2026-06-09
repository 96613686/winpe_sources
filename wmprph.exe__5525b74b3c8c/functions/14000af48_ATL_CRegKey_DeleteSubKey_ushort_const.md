# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x14000af48`
- end: `0x14000affc`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `180`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b6b8`
- `0x14000bbf0`

## callees

- `0x14000af48`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000af82`
- `KERNEL32!GetProcAddress` at `0x14000afaf`
- `KERNEL32!GetProcAddress` at `0x14000af82`
- `KERNEL32!GetProcAddress` at `0x14000afaf`
- `KERNEL32!LoadLibraryExW` at `0x14000af9a`
- `KERNEL32!LoadLibraryExW` at `0x14000af9a`
- `KERNEL32!GetModuleHandleW` at `0x14000af6d`
- `KERNEL32!GetModuleHandleW` at `0x14000af6d`
- `KERNEL32!GetLastError` at `0x14000afeb`
- `KERNEL32!GetLastError` at `0x14000afeb`

## string_xrefs

- `0x14000af66`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x14000af78`: `RegDeleteKeyExW`
- `0x14000af91`: `advapi32.dll`
- `0x14000afa5`: `RegDeleteKeyW`

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
0x14000af48  mov     [rsp+arg_0], rbx
0x14000af4d  push    rdi
0x14000af4e  sub     rsp, 30h
0x14000af52  cmp     qword ptr [rcx+8], 0
0x14000af57  mov     rdi, rdx
0x14000af5a  mov     rbx, rcx
0x14000af5d  jnz     short loc_14000AFB9
0x14000af5f  cmp     qword ptr [rcx+10h], 0
0x14000af64  jnz     short loc_14000AFB9
0x14000af66  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x14000af6d  call    cs:__imp_GetModuleHandleW
0x14000af73  test    rax, rax
0x14000af76  jz      short loc_14000AF8E
0x14000af78  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x14000af7f  mov     rcx, rax; hModule
0x14000af82  call    cs:__imp_GetProcAddress
0x14000af88  mov     [rbx+8], rax
0x14000af8c  jmp     short loc_14000AFB9
0x14000af8e  xor     r8d, r8d; dwFlags
0x14000af91  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x14000af98  xor     edx, edx; hFile
0x14000af9a  call    cs:__imp_LoadLibraryExW
0x14000afa0  test    rax, rax
0x14000afa3  jz      short loc_14000AFB9
0x14000afa5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x14000afac  mov     rcx, rax; hModule
0x14000afaf  call    cs:__imp_GetProcAddress
0x14000afb5  mov     [rbx+10h], rax
0x14000afb9  mov     rax, [rbx+8]
0x14000afbd  test    rax, rax
0x14000afc0  jz      short loc_14000AFD5
0x14000afc2  mov     rcx, [rbx]
0x14000afc5  xor     r9d, r9d
0x14000afc8  xor     r8d, r8d
0x14000afcb  mov     rdx, rdi
0x14000afce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afd3  jmp     short loc_14000AFF1
0x14000afd5  mov     rax, [rbx+10h]
0x14000afd9  test    rax, rax
0x14000afdc  jz      short loc_14000AFEB
0x14000afde  mov     rcx, [rbx]
0x14000afe1  mov     rdx, rdi
0x14000afe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afe9  jmp     short loc_14000AFF1
0x14000afeb  call    cs:__imp_GetLastError
0x14000aff1  mov     rbx, [rsp+38h+arg_0]
0x14000aff6  add     rsp, 30h
0x14000affa  pop     rdi
0x14000affb  retn
```
