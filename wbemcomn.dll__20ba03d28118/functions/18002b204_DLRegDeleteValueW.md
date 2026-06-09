# DLRegDeleteValueW

- ea: `0x18002b204`
- end: `0x18002b267`
- name: `DLRegDeleteValueW`
- size: `99`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002c170`

## callees

- `0x1800101cc`
- `0x18002b204`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b249`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b237`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002b237`

## string_xrefs

- `0x18002b230`: `RegDeleteValueW`

## pseudocode

```c
DWORD __fastcall DLRegDeleteValueW(__int64 a1, __int64 a2)
{
  FARPROC ProcAddress; // rax
  DWORD result; // eax

  ProcAddress = (FARPROC)qword_1800703D8;
  if ( qword_1800703D8 )
    return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
  result = DLpLoadRegistryDll();
  if ( result )
    return result;
  ProcAddress = GetProcAddress(g_hInstRegistryDLL, "RegDeleteValueW");
  qword_1800703D8 = (__int64)ProcAddress;
  if ( ProcAddress )
    return ((__int64 (__fastcall *)(__int64, __int64))ProcAddress)(a1, a2);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x18002b204  mov     [rsp+arg_0], rbx
0x18002b209  push    rdi
0x18002b20a  sub     rsp, 20h
0x18002b20e  mov     rax, cs:qword_1800703D8
0x18002b215  mov     rbx, rdx
0x18002b218  mov     rdi, rcx
0x18002b21b  test    rax, rax
0x18002b21e  jnz     short loc_18002B251
0x18002b220  call    ?DLpLoadRegistryDll@@YAKXZ; DLpLoadRegistryDll(void)
0x18002b225  test    eax, eax
0x18002b227  jnz     short loc_18002B25C
0x18002b229  mov     rcx, cs:?g_hInstRegistryDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18002b230  lea     rdx, aRegdeletevalue; "RegDeleteValueW"
0x18002b237  call    cs:__imp_GetProcAddress
0x18002b23d  mov     cs:qword_1800703D8, rax
0x18002b244  test    rax, rax
0x18002b247  jnz     short loc_18002B251
0x18002b249  call    cs:__imp_GetLastError
0x18002b24f  jmp     short loc_18002B25C
0x18002b251  mov     rdx, rbx
0x18002b254  mov     rcx, rdi
0x18002b257  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b25c  mov     rbx, [rsp+28h+arg_0]
0x18002b261  add     rsp, 20h
0x18002b265  pop     rdi
0x18002b266  retn
```
