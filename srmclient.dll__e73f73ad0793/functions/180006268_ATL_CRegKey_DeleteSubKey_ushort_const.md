# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x180006268`
- end: `0x18000631d`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `181`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x1800082d8`
- `0x1800087a0`

## callees

- `0x180006268`
- `0x1800d5010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800062a2`
- `KERNEL32!GetProcAddress` at `0x1800062cf`
- `KERNEL32!GetProcAddress` at `0x1800062a2`
- `KERNEL32!GetProcAddress` at `0x1800062cf`
- `KERNEL32!GetModuleHandleW` at `0x18000628d`
- `KERNEL32!GetModuleHandleW` at `0x18000628d`
- `KERNEL32!LoadLibraryExW` at `0x1800062ba`
- `KERNEL32!LoadLibraryExW` at `0x1800062ba`
- `KERNEL32!GetLastError` at `0x18000630b`
- `KERNEL32!GetLastError` at `0x18000630b`

## string_xrefs

- `0x180006286`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180006298`: `RegDeleteKeyExW`
- `0x1800062b3`: `advapi32.dll`
- `0x1800062c5`: `RegDeleteKeyW`

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
0x180006268  mov     [rsp+arg_0], rbx
0x18000626d  push    rdi
0x18000626e  sub     rsp, 30h
0x180006272  mov     rdi, rdx
0x180006275  mov     rbx, rcx
0x180006278  cmp     qword ptr [rcx+8], 0
0x18000627d  jnz     short loc_1800062D9
0x18000627f  cmp     qword ptr [rcx+10h], 0
0x180006284  jnz     short loc_1800062D9
0x180006286  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18000628d  call    cs:__imp_GetModuleHandleW
0x180006293  test    rax, rax
0x180006296  jz      short loc_1800062AE
0x180006298  lea     rdx, ProcName; "RegDeleteKeyExW"
0x18000629f  mov     rcx, rax; hModule
0x1800062a2  call    cs:__imp_GetProcAddress
0x1800062a8  mov     [rbx+8], rax
0x1800062ac  jmp     short loc_1800062D9
0x1800062ae  xor     r8d, r8d; dwFlags
0x1800062b1  xor     edx, edx; hFile
0x1800062b3  lea     rcx, LibFileName; "advapi32.dll"
0x1800062ba  call    cs:__imp_LoadLibraryExW
0x1800062c0  test    rax, rax
0x1800062c3  jz      short loc_1800062D9
0x1800062c5  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x1800062cc  mov     rcx, rax; hModule
0x1800062cf  call    cs:__imp_GetProcAddress
0x1800062d5  mov     [rbx+10h], rax
0x1800062d9  mov     rax, [rbx+8]
0x1800062dd  test    rax, rax
0x1800062e0  jz      short loc_1800062F5
0x1800062e2  xor     r9d, r9d
0x1800062e5  xor     r8d, r8d
0x1800062e8  mov     rdx, rdi
0x1800062eb  mov     rcx, [rbx]
0x1800062ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f3  jmp     short loc_180006312
0x1800062f5  mov     rax, [rbx+10h]
0x1800062f9  test    rax, rax
0x1800062fc  jz      short loc_18000630B
0x1800062fe  mov     rdx, rdi
0x180006301  mov     rcx, [rbx]
0x180006304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006309  jmp     short loc_180006312
0x18000630b  call    cs:__imp_GetLastError
0x180006311  nop
0x180006312  mov     rbx, [rsp+38h+arg_0]
0x180006317  add     rsp, 30h
0x18000631b  pop     rdi
0x18000631c  retn
```
