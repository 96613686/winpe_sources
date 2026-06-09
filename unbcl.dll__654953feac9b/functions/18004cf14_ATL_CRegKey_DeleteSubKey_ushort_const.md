# ATL::CRegKey::DeleteSubKey(ushort const *)

- ea: `0x18004cf14`
- end: `0x18004cfd3`
- name: `?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x18004d000`
- `0x18004d2c0`

## callees

- `0x18004cf14`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x18004cf70`
- `KERNEL32!LoadLibraryExW` at `0x18004cf70`
- `KERNEL32!GetModuleHandleW` at `0x18004cf43`
- `KERNEL32!GetModuleHandleW` at `0x18004cf43`
- `KERNEL32!GetProcAddress` at `0x18004cf58`
- `KERNEL32!GetProcAddress` at `0x18004cf85`
- `KERNEL32!GetProcAddress` at `0x18004cf58`
- `KERNEL32!GetProcAddress` at `0x18004cf85`
- `KERNEL32!GetLastError` at `0x18004cfc1`
- `KERNEL32!GetLastError` at `0x18004cfc1`

## string_xrefs

- `0x18004cf3c`: `API-MS-Win-Core-LocalRegistry-L1-1-0.dll`
- `0x18004cf69`: `advapi32.dll`
- `0x18004cf4e`: `RegDeleteKeyExW`
- `0x18004cf7b`: `RegDeleteKeyW`

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
0x18004cf14  push    rdi
0x18004cf16  sub     rsp, 40h
0x18004cf1a  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18004cf23  mov     [rsp+48h+arg_0], rbx
0x18004cf28  mov     rdi, rdx
0x18004cf2b  mov     rbx, rcx
0x18004cf2e  cmp     qword ptr [rcx+8], 0
0x18004cf33  jnz     short loc_18004CF8F
0x18004cf35  cmp     qword ptr [rcx+10h], 0
0x18004cf3a  jnz     short loc_18004CF8F
0x18004cf3c  lea     rcx, aApiMsWinCoreLo; "API-MS-Win-Core-LocalRegistry-L1-1-0.dl"...
0x18004cf43  call    cs:__imp_GetModuleHandleW
0x18004cf49  test    rax, rax
0x18004cf4c  jz      short loc_18004CF64
0x18004cf4e  lea     rdx, aRegdeletekeyex; "RegDeleteKeyExW"
0x18004cf55  mov     rcx, rax; hModule
0x18004cf58  call    cs:__imp_GetProcAddress
0x18004cf5e  mov     [rbx+8], rax
0x18004cf62  jmp     short loc_18004CF8F
0x18004cf64  xor     r8d, r8d; dwFlags
0x18004cf67  xor     edx, edx; hFile
0x18004cf69  lea     rcx, aAdvapi32Dll_0; "advapi32.dll"
0x18004cf70  call    cs:__imp_LoadLibraryExW
0x18004cf76  test    rax, rax
0x18004cf79  jz      short loc_18004CF8F
0x18004cf7b  lea     rdx, aRegdeletekeyw; "RegDeleteKeyW"
0x18004cf82  mov     rcx, rax; hModule
0x18004cf85  call    cs:__imp_GetProcAddress
0x18004cf8b  mov     [rbx+10h], rax
0x18004cf8f  mov     rax, [rbx+8]
0x18004cf93  test    rax, rax
0x18004cf96  jz      short loc_18004CFAB
0x18004cf98  xor     r9d, r9d
0x18004cf9b  xor     r8d, r8d
0x18004cf9e  mov     rdx, rdi
0x18004cfa1  mov     rcx, [rbx]
0x18004cfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfa9  jmp     short loc_18004CFC8
0x18004cfab  mov     rax, [rbx+10h]
0x18004cfaf  test    rax, rax
0x18004cfb2  jz      short loc_18004CFC1
0x18004cfb4  mov     rdx, rdi
0x18004cfb7  mov     rcx, [rbx]
0x18004cfba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cfbf  jmp     short loc_18004CFC8
0x18004cfc1  call    cs:__imp_GetLastError
0x18004cfc7  nop
0x18004cfc8  mov     rbx, [rsp+48h+arg_0]
0x18004cfcd  add     rsp, 40h
0x18004cfd1  pop     rdi
0x18004cfd2  retn
```
