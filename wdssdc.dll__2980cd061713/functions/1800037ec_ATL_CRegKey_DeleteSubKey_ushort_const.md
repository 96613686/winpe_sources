# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x1800037ec`
- end: `0x1800038bf`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `211`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18000409c`
- `0x18000459c`
- `0x180007d28`

## callees

- `0x1800037ec`
- `0x18000d010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800038a7`
- `KERNEL32!GetLastError` at `0x1800038a7`
- `KERNEL32!GetProcAddress` at `0x18000382c`
- `KERNEL32!GetProcAddress` at `0x180003865`
- `KERNEL32!GetProcAddress` at `0x18000382c`
- `KERNEL32!GetProcAddress` at `0x180003865`
- `KERNEL32!GetModuleHandleW` at `0x180003811`
- `KERNEL32!GetModuleHandleW` at `0x180003811`
- `KERNEL32!LoadLibraryExW` at `0x18000384a`
- `KERNEL32!LoadLibraryExW` at `0x18000384a`

## string_xrefs

- `0x18000380a`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x180003822`: `RegDeleteKeyExW`
- `0x180003841`: `advapi32.dll`
- `0x18000385b`: `RegDeleteKeyW`

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
0x1800037ec  mov     [rsp+arg_0], rbx
0x1800037f1  push    rdi
0x1800037f2  sub     rsp, 30h
0x1800037f6  cmp     qword ptr [rcx+8], 0
0x1800037fb  mov     rdi, rdx
0x1800037fe  mov     rbx, rcx
0x180003801  jnz     short loc_180003875
0x180003803  cmp     qword ptr [rcx+10h], 0
0x180003808  jnz     short loc_180003875
0x18000380a  lea     rcx, ModuleName; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x180003811  call    cs:__imp_GetModuleHandleW
0x180003818  nop     dword ptr [rax+rax+00h]
0x18000381d  test    rax, rax
0x180003820  jz      short loc_18000383E
0x180003822  lea     rdx, ProcName; "RegDeleteKeyExW"
0x180003829  mov     rcx, rax; hModule
0x18000382c  call    cs:__imp_GetProcAddress
0x180003833  nop     dword ptr [rax+rax+00h]
0x180003838  mov     [rbx+8], rax
0x18000383c  jmp     short loc_180003875
0x18000383e  xor     r8d, r8d; dwFlags
0x180003841  lea     rcx, LibFileName; "advapi32.dll"
0x180003848  xor     edx, edx; hFile
0x18000384a  call    cs:__imp_LoadLibraryExW
0x180003851  nop     dword ptr [rax+rax+00h]
0x180003856  test    rax, rax
0x180003859  jz      short loc_180003875
0x18000385b  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x180003862  mov     rcx, rax; hModule
0x180003865  call    cs:__imp_GetProcAddress
0x18000386c  nop     dword ptr [rax+rax+00h]
0x180003871  mov     [rbx+10h], rax
0x180003875  mov     rax, [rbx+8]
0x180003879  test    rax, rax
0x18000387c  jz      short loc_180003891
0x18000387e  mov     rcx, [rbx]
0x180003881  xor     r9d, r9d
0x180003884  xor     r8d, r8d
0x180003887  mov     rdx, rdi
0x18000388a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000388f  jmp     short loc_1800038B3
0x180003891  mov     rax, [rbx+10h]
0x180003895  test    rax, rax
0x180003898  jz      short loc_1800038A7
0x18000389a  mov     rcx, [rbx]
0x18000389d  mov     rdx, rdi
0x1800038a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038a5  jmp     short loc_1800038B3
0x1800038a7  call    cs:__imp_GetLastError
0x1800038ae  nop     dword ptr [rax+rax+00h]
0x1800038b3  mov     rbx, [rsp+38h+arg_0]
0x1800038b8  add     rsp, 30h
0x1800038bc  pop     rdi
0x1800038bd  retn
```
