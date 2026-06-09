# DLGetSecurityDescriptorOwner(void *,void * *,int *)

- ea: `0x18002bda0`
- end: `0x18002be0e`
- name: `?DLGetSecurityDescriptorOwner@@YAHPEAXPEAPEAXPEAH@Z`
- size: `110`
- prototype: `__int64 __fastcall(void *, void **, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003d1d0`
- `0x18003e600`

## callees

- `0x18001d19c`
- `0x18002bda0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bdcb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bdcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bde1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002bde1`

## string_xrefs

- `0x18002bdda`: `GetSecurityDescriptorOwner`

## pseudocode

```c
__int64 __fastcall DLGetSecurityDescriptorOwner(void *a1, void **a2, int *a3)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  DWORD SecurityDll; // eax

  ProcAddress = (FARPROC)qword_180070330;
  if ( qword_180070330 )
    return ((unsigned int (__fastcall *)(void *, void **, int *))ProcAddress)(a1, a2, a3);
  v7 = 0;
  SecurityDll = DLpLoadSecurityDll();
  if ( !SecurityDll )
  {
    ProcAddress = GetProcAddress(g_hInstSecurityDLL, "GetSecurityDescriptorOwner");
    qword_180070330 = (__int64)ProcAddress;
    if ( !ProcAddress )
      return v7;
    return ((unsigned int (__fastcall *)(void *, void **, int *))ProcAddress)(a1, a2, a3);
  }
  SetLastError(SecurityDll);
  return v7;
}

```

## disassembly

```asm
0x18002bda0  push    rbx
0x18002bda2  push    rbp
0x18002bda3  push    rsi
0x18002bda4  push    rdi
0x18002bda5  sub     rsp, 28h
0x18002bda9  mov     rax, cs:qword_180070330
0x18002bdb0  mov     rdi, r8
0x18002bdb3  mov     rsi, rdx
0x18002bdb6  mov     rbp, rcx
0x18002bdb9  test    rax, rax
0x18002bdbc  jnz     short loc_18002BDF3
0x18002bdbe  xor     ebx, ebx
0x18002bdc0  call    ?DLpLoadSecurityDll@@YAKXZ; DLpLoadSecurityDll(void)
0x18002bdc5  test    eax, eax
0x18002bdc7  jz      short loc_18002BDD3
0x18002bdc9  mov     ecx, eax; dwErrCode
0x18002bdcb  call    cs:__imp_SetLastError
0x18002bdd1  jmp     short loc_18002BE03
0x18002bdd3  mov     rcx, cs:?g_hInstSecurityDLL@@3PEAUHINSTANCE__@@EA; hModule
0x18002bdda  lea     rdx, aGetsecuritydes_3; "GetSecurityDescriptorOwner"
0x18002bde1  call    cs:__imp_GetProcAddress
0x18002bde7  mov     cs:qword_180070330, rax
0x18002bdee  test    rax, rax
0x18002bdf1  jz      short loc_18002BE03
0x18002bdf3  mov     r8, rdi
0x18002bdf6  mov     rdx, rsi
0x18002bdf9  mov     rcx, rbp
0x18002bdfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be01  mov     ebx, eax
0x18002be03  mov     eax, ebx
0x18002be05  add     rsp, 28h
0x18002be09  pop     rdi
0x18002be0a  pop     rsi
0x18002be0b  pop     rbp
0x18002be0c  pop     rbx
0x18002be0d  retn
```
