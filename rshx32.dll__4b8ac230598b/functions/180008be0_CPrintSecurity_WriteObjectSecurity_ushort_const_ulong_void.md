# CPrintSecurity::WriteObjectSecurity(ushort const *,ulong,void *)

- ea: `0x180008be0`
- end: `0x180008cd1`
- name: `?WriteObjectSecurity@CPrintSecurity@@MEAAJPEBGKPEAX@Z`
- size: `241`
- prototype: `__int64 __fastcall(CPrintSecurity *this, WCHAR *, int, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180008be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008caa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008c96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008caa`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180008c28`
- `api-ms-win-security-base-l1-1-0!IsValidSecurityDescriptor` at `0x180008c28`
- `WINSPOOL!ClosePrinter` at `0x180008ca2`
- `WINSPOOL!ClosePrinter` at `0x180008ca2`
- `WINSPOOL!OpenPrinterW` at `0x180008c6e`
- `WINSPOOL!OpenPrinterW` at `0x180008c6e`
- `WINSPOOL!SetPrinterW` at `0x180008c8c`
- `WINSPOOL!SetPrinterW` at `0x180008c8c`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::WriteObjectSecurity(CPrintSecurity *this, WCHAR *a2, int a3, void *a4)
{
  char v5; // bl
  ACCESS_MASK DesiredAccess; // eax
  signed int LastError; // ebx
  HANDLE phPrinter; // [rsp+20h] [rbp-38h] BYREF
  BYTE pPrinter[8]; // [rsp+28h] [rbp-30h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-28h] BYREF

  phPrinter = 0;
  v5 = a3;
  memset(&pDefault, 0, sizeof(pDefault));
  if ( !a3 || !a4 || !a2 )
    return 2147500035LL;
  if ( !IsValidSecurityDescriptor(a4) )
    return 2147942487LL;
  DesiredAccess = pDefault.DesiredAccess;
  if ( (v5 & 3) != 0 )
  {
    DesiredAccess = pDefault.DesiredAccess | 0x80000;
    pDefault.DesiredAccess |= 0x80000u;
  }
  if ( (v5 & 8) != 0 )
  {
    DesiredAccess |= 0x1000000u;
    pDefault.DesiredAccess = DesiredAccess;
  }
  if ( (v5 & 4) != 0 )
    pDefault.DesiredAccess = DesiredAccess | 0x40000;
  if ( OpenPrinterW(a2, &phPrinter, &pDefault) )
  {
    LastError = 0;
    *(_QWORD *)pPrinter = a4;
    if ( !SetPrinterW(phPrinter, 3u, pPrinter, 0) )
      LastError = GetLastError();
    ClosePrinter(phPrinter);
  }
  else
  {
    LastError = GetLastError();
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008be0  push    rbp
0x180008be2  push    rbx
0x180008be3  push    rsi
0x180008be4  push    rdi
0x180008be5  mov     rbp, rsp
0x180008be8  sub     rsp, 58h
0x180008bec  xor     eax, eax
0x180008bee  mov     [rbp+phPrinter], 0
0x180008bf6  mov     qword ptr [rbp+pDefault.DesiredAccess], rax
0x180008bfa  xorps   xmm0, xmm0
0x180008bfd  mov     rdi, r9
0x180008c00  mov     ebx, r8d
0x180008c03  mov     rsi, rdx
0x180008c06  movups  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180008c0a  test    r8d, r8d
0x180008c0d  jz      loc_180008CC3
0x180008c13  test    r9, r9
0x180008c16  jz      loc_180008CC3
0x180008c1c  test    rdx, rdx
0x180008c1f  jz      loc_180008CC3
0x180008c25  mov     rcx, r9; pSecurityDescriptor
0x180008c28  call    cs:__imp_IsValidSecurityDescriptor
0x180008c2e  test    eax, eax
0x180008c30  jnz     short loc_180008C3C
0x180008c32  mov     eax, 80070057h
0x180008c37  jmp     loc_180008CC8
0x180008c3c  mov     eax, [rbp+pDefault.DesiredAccess]
0x180008c3f  test    bl, 3
0x180008c42  jz      short loc_180008C4B
0x180008c44  bts     eax, 13h
0x180008c48  mov     [rbp+pDefault.DesiredAccess], eax
0x180008c4b  test    bl, 8
0x180008c4e  jz      short loc_180008C57
0x180008c50  bts     eax, 18h
0x180008c54  mov     [rbp+pDefault.DesiredAccess], eax
0x180008c57  test    bl, 4
0x180008c5a  jz      short loc_180008C63
0x180008c5c  bts     eax, 12h
0x180008c60  mov     [rbp+pDefault.DesiredAccess], eax
0x180008c63  lea     r8, [rbp+pDefault]; pDefault
0x180008c67  mov     rcx, rsi; pPrinterName
0x180008c6a  lea     rdx, [rbp+phPrinter]; phPrinter
0x180008c6e  call    cs:__imp_OpenPrinterW
0x180008c74  test    eax, eax
0x180008c76  jz      short loc_180008CAA
0x180008c78  mov     rcx, [rbp+phPrinter]; hPrinter
0x180008c7c  lea     r8, [rbp+pPrinter]; pPrinter
0x180008c80  xor     ebx, ebx
0x180008c82  mov     qword ptr [rbp+pPrinter], rdi
0x180008c86  xor     r9d, r9d; Command
0x180008c89  lea     edx, [rbx+3]; Level
0x180008c8c  call    cs:__imp_SetPrinterW
0x180008c92  test    eax, eax
0x180008c94  jnz     short loc_180008C9E
0x180008c96  call    cs:__imp_GetLastError
0x180008c9c  mov     ebx, eax
0x180008c9e  mov     rcx, [rbp+phPrinter]; hPrinter
0x180008ca2  call    cs:__imp_ClosePrinter
0x180008ca8  jmp     short loc_180008CB2
0x180008caa  call    cs:__imp_GetLastError
0x180008cb0  mov     ebx, eax
0x180008cb2  test    ebx, ebx
0x180008cb4  jle     short loc_180008CBF
0x180008cb6  movzx   ebx, bx
0x180008cb9  or      ebx, 80070000h
0x180008cbf  mov     eax, ebx
0x180008cc1  jmp     short loc_180008CC8
0x180008cc3  mov     eax, 80004003h
0x180008cc8  add     rsp, 58h
0x180008ccc  pop     rdi
0x180008ccd  pop     rsi
0x180008cce  pop     rbx
0x180008ccf  pop     rbp
0x180008cd0  retn
```
