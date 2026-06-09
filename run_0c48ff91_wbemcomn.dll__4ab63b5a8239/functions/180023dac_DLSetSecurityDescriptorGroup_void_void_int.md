# DLSetSecurityDescriptorGroup(void *,void *,int)

- ea: `0x180023dac`
- end: `0x180023e24`
- name: `?DLSetSecurityDescriptorGroup@@YAHPEAX0H@Z`
- size: `120`
- prototype: `__int64 __fastcall(void *, void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023800`

## callees

- `0x18001d19c`
- `0x180023dac`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dda`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023dda`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023df0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023df0`

## string_xrefs

- `0x180023de9`: `SetSecurityDescriptorGroup`

## pseudocode

```c
__int64 __fastcall DLSetSecurityDescriptorGroup(void *a1, void *a2)
{
  FARPROC ProcAddress; // rax
  unsigned int v5; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070328;
  if ( qword_180070328 )
    return ((unsigned int (__fastcall *)(void *, void *, _QWORD))ProcAddress)(a1, a2, 0);
  v5 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "SetSecurityDescriptorGroup");
    qword_180070328 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v5;
    return ((unsigned int (__fastcall *)(void *, void *, _QWORD))ProcAddress)(a1, a2, 0);
  }
  SetLastError(SecurityDll);
  return v5;
}

```

## disassembly

```asm
0x180023dac  mov     [rsp+arg_0], rbx
0x180023db1  mov     [rsp+arg_8], rsi
0x180023db6  push    rdi
0x180023db7  sub     rsp, 20h
0x180023dbb  mov     rax, cs:qword_180070328
0x180023dc2  mov     rdi, rdx
0x180023dc5  mov     rsi, rcx
0x180023dc8  test    rax, rax
0x180023dcb  jnz     short loc_180023E02
0x180023dcd  xor     ebx, ebx
0x180023dcf  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x180023dd4  test    eax, eax
0x180023dd6  jz      short loc_180023DE2
0x180023dd8  mov     ecx, eax; dwErrCode
0x180023dda  call    cs:__imp_SetLastError
0x180023de0  jmp     short loc_180023E12
0x180023de2  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x180023de9  lea     rdx, aSetsecuritydes_1; "SetSecurityDescriptorGroup"
0x180023df0  call    cs:__imp_GetProcAddress
0x180023df6  mov     cs:qword_180070328, rax
0x180023dfd  test    rax, rax
0x180023e00  jz      short loc_180023E12
0x180023e02  xor     r8d, r8d
0x180023e05  mov     rdx, rdi
0x180023e08  mov     rcx, rsi
0x180023e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e10  mov     ebx, eax
0x180023e12  mov     rsi, [rsp+28h+arg_8]
0x180023e17  mov     eax, ebx
0x180023e19  mov     rbx, [rsp+28h+arg_0]
0x180023e1e  add     rsp, 20h
0x180023e22  pop     rdi
0x180023e23  retn
```
