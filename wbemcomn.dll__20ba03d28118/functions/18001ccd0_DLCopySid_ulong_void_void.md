# DLCopySid(ulong,void *,void *)

- ea: `0x18001ccd0`
- end: `0x18001cd55`
- name: `?DLCopySid@@YAHKPEAX0@Z`
- size: `133`
- prototype: `__int64 __fastcall(unsigned int, void *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001d390`

## callees

- `0x18001ccd0`
- `0x18001d19c`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cd3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001cd3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cd27`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001cd27`

## string_xrefs

- `0x18001cd20`: `CopySid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DLCopySid(unsigned int a1, void *a2, void *a3)
{
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070338;
  if ( qword_180070338 )
    return ((__int64 (__fastcall *)(_QWORD, void *, void *))ProcAddress)(a1, a2, a3);
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
  }
  else
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "CopySid");
    qword_180070338 = (__int64)ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(_QWORD, void *, void *))ProcAddress)(a1, a2, a3);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ccd0  mov     [rsp+arg_0], rbx
0x18001ccd5  mov     [rsp+arg_8], rsi
0x18001ccda  push    rdi
0x18001ccdb  sub     rsp, 20h
0x18001ccdf  mov     rax, cs:qword_180070338
0x18001cce6  mov     rbx, r8
0x18001cce9  mov     rdi, rdx
0x18001ccec  mov     esi, ecx
0x18001ccee  test    rax, rax
0x18001ccf1  jz      short loc_18001CD10
0x18001ccf3  mov     r8, rbx
0x18001ccf6  mov     rdx, rdi
0x18001ccf9  mov     ecx, esi
0x18001ccfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd00  mov     rbx, [rsp+28h+arg_0]
0x18001cd05  mov     rsi, [rsp+28h+arg_8]
0x18001cd0a  add     rsp, 20h
0x18001cd0e  pop     rdi
0x18001cd0f  retn
0x18001cd10  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001cd15  test    eax, eax
0x18001cd17  jnz     short loc_18001CD3B
0x18001cd19  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001cd20  lea     rdx, aCopysid; "CopySid"
0x18001cd27  call    cs:__imp_GetProcAddress
0x18001cd2d  mov     cs:qword_180070338, rax
0x18001cd34  test    rax, rax
0x18001cd37  jnz     short loc_18001CCF3
0x18001cd39  jmp     short loc_18001CD43
0x18001cd3b  mov     ecx, eax; dwErrCode
0x18001cd3d  call    cs:__imp_SetLastError
0x18001cd43  mov     rbx, [rsp+28h+arg_0]
0x18001cd48  xor     eax, eax
0x18001cd4a  mov     rsi, [rsp+28h+arg_8]
0x18001cd4f  add     rsp, 20h
0x18001cd53  pop     rdi
0x18001cd54  retn
```
