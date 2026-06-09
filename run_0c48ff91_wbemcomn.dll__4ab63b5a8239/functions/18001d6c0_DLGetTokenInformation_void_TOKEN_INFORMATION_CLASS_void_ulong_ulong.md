# DLGetTokenInformation(void *,_TOKEN_INFORMATION_CLASS,void *,ulong,ulong *)

- ea: `0x18001d6c0`
- end: `0x18001d73d`
- name: `?DLGetTokenInformation@@YAHPEAXW4_TOKEN_INFORMATION_CLASS@@0KPEAK@Z`
- size: `125`
- prototype: `__int64 __fastcall(void *, enum _TOKEN_INFORMATION_CLASS, void *, unsigned int, unsigned int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d390`
- `0x18001d600`
- `0x180030a10`
- `0x180030cd0`
- `0x180034850`

## callees

- `0x18001d19c`
- `0x18001d6c0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d711`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d711`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d729`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001d729`

## string_xrefs

- `0x18001d722`: `GetTokenInformation`

## pseudocode

```c
__int64 __fastcall DLGetTokenInformation(void *a1, unsigned int a2, void *a3, unsigned int a4, unsigned int *a5)
{
  FARPROC ProcAddress; // rax
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070310;
  if ( qword_180070310 )
    return ((__int64 (__fastcall *)(void *, _QWORD, void *, _QWORD, unsigned int *))ProcAddress)(a1, a2, a3, a4, a5);
  SecurityDll = DLpLoadSecurityDll();
  if ( SecurityDll )
  {
    SetLastError(SecurityDll);
  }
  else
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetTokenInformation");
    qword_180070310 = (__int64)ProcAddress;
    if ( ProcAddress )
      return ((__int64 (__fastcall *)(void *, _QWORD, void *, _QWORD, unsigned int *))ProcAddress)(a1, a2, a3, a4, a5);
  }
  return 0;
}

```

## disassembly

```asm
0x18001d6c0  push    rbx
0x18001d6c2  push    rbp
0x18001d6c3  push    rsi
0x18001d6c4  push    rdi
0x18001d6c5  sub     rsp, 38h
0x18001d6c9  mov     rax, cs:qword_180070310
0x18001d6d0  mov     ebx, r9d
0x18001d6d3  mov     rdi, r8
0x18001d6d6  mov     esi, edx
0x18001d6d8  mov     rbp, rcx
0x18001d6db  test    rax, rax
0x18001d6de  jz      short loc_18001D706
0x18001d6e0  mov     rcx, [rsp+58h+arg_20]
0x18001d6e8  mov     r9d, ebx
0x18001d6eb  mov     [rsp+58h+var_38], rcx
0x18001d6f0  mov     r8, rdi
0x18001d6f3  mov     rcx, rbp
0x18001d6f6  mov     edx, esi
0x18001d6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6fd  add     rsp, 38h
0x18001d701  pop     rdi
0x18001d702  pop     rsi
0x18001d703  pop     rbp
0x18001d704  pop     rbx
0x18001d705  retn
0x18001d706  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18001d70b  test    eax, eax
0x18001d70d  jz      short loc_18001D71B
0x18001d70f  mov     ecx, eax; dwErrCode
0x18001d711  call    cs:__imp_SetLastError
0x18001d717  xor     eax, eax
0x18001d719  jmp     short loc_18001D6FD
0x18001d71b  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18001d722  lea     rdx, aGettokeninform; "GetTokenInformation"
0x18001d729  call    cs:__imp_GetProcAddress
0x18001d72f  mov     cs:qword_180070310, rax
0x18001d736  test    rax, rax
0x18001d739  jz      short loc_18001D717
0x18001d73b  jmp     short loc_18001D6E0
```
