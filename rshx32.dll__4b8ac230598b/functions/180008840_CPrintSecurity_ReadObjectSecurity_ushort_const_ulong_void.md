# CPrintSecurity::ReadObjectSecurity(ushort const *,ulong,void * *)

- ea: `0x180008840`
- end: `0x180008947`
- name: `?ReadObjectSecurity@CPrintSecurity@@MEAAJPEBGKPEAPEAX@Z`
- size: `263`
- prototype: `__int64 __fastcall(CPrintSecurity *this, WCHAR *, int, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000847c`
- `0x180008840`
- `0x18001d32e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000890c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008920`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000890c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008920`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800088f3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x1800088f3`
- `WINSPOOL!ClosePrinter` at `0x180008918`
- `WINSPOOL!ClosePrinter` at `0x180008918`
- `WINSPOOL!OpenPrinterW` at `0x1800088c2`
- `WINSPOOL!OpenPrinterW` at `0x1800088c2`

## pseudocode

```c
__int64 __fastcall CPrintSecurity::ReadObjectSecurity(CPrintSecurity *this, WCHAR *a2, int a3, unsigned __int8 **a4)
{
  ACCESS_MASK DesiredAccess; // eax
  unsigned __int8 *v7; // rbx
  signed int LastError; // edi
  DWORD SecurityDescriptorLength; // eax
  unsigned __int8 *v10; // [rsp+20h] [rbp-28h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+28h] [rbp-20h] BYREF
  HANDLE phPrinter; // [rsp+88h] [rbp+40h] BYREF

  phPrinter = 0;
  memset(&pDefault, 0, sizeof(pDefault));
  if ( !a4 || !a2 )
    return 2147500035LL;
  if ( !a3 )
    return 2147942487LL;
  DesiredAccess = pDefault.DesiredAccess;
  if ( (a3 & 7) != 0 )
    DesiredAccess = 0x20000;
  pDefault.DesiredAccess = DesiredAccess;
  if ( (a3 & 8) != 0 )
    pDefault.DesiredAccess = (a3 & 7) != 0 ? 16908288 : 0x1000000;
  *a4 = 0;
  if ( OpenPrinterW(a2, &phPrinter, &pDefault) )
  {
    v10 = 0;
    if ( (unsigned int)GetPrinterAlloc(phPrinter, 3u, &v10) )
    {
      v7 = v10;
      LastError = 0;
      SecurityDescriptorLength = GetSecurityDescriptorLength(*(PSECURITY_DESCRIPTOR *)v10);
      *a4 = v7;
      memmove_0(v7, *(const void **)v7, SecurityDescriptorLength);
    }
    else
    {
      LastError = GetLastError();
    }
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
0x180008840  push    rbp
0x180008842  push    rbx
0x180008843  push    rsi
0x180008844  push    rdi
0x180008845  mov     rbp, rsp
0x180008848  sub     rsp, 48h
0x18000884c  xor     eax, eax
0x18000884e  mov     [rbp+phPrinter], 0
0x180008856  mov     qword ptr [rbp+pDefault.DesiredAccess], rax
0x18000885a  xorps   xmm0, xmm0
0x18000885d  mov     rsi, r9
0x180008860  mov     r10, rdx
0x180008863  movups  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x180008867  test    r9, r9
0x18000886a  jz      loc_180008939
0x180008870  test    rdx, rdx
0x180008873  jz      loc_180008939
0x180008879  test    r8d, r8d
0x18000887c  jnz     short loc_180008888
0x18000887e  mov     eax, 80070057h
0x180008883  jmp     loc_18000893E
0x180008888  mov     eax, [rbp+pDefault.DesiredAccess]
0x18000888b  mov     ecx, r8d
0x18000888e  and     ecx, 7
0x180008891  mov     edx, 20000h
0x180008896  cmovnz  eax, edx
0x180008899  mov     [rbp+pDefault.DesiredAccess], eax
0x18000889c  test    r8b, 8
0x1800088a0  jz      short loc_1800088B0
0x1800088a2  neg     ecx
0x1800088a4  sbb     eax, eax
0x1800088a6  and     eax, edx
0x1800088a8  add     eax, 1000000h
0x1800088ad  mov     [rbp+pDefault.DesiredAccess], eax
0x1800088b0  lea     r8, [rbp+pDefault]; pDefault
0x1800088b4  mov     qword ptr [r9], 0
0x1800088bb  lea     rdx, [rbp+phPrinter]; phPrinter
0x1800088bf  mov     rcx, r10; pPrinterName
0x1800088c2  call    cs:__imp_OpenPrinterW
0x1800088c8  test    eax, eax
0x1800088ca  jz      short loc_180008920
0x1800088cc  mov     rcx, [rbp+phPrinter]; hPrinter
0x1800088d0  lea     r8, [rbp+var_28]; unsigned __int8 **
0x1800088d4  mov     edx, 3; Level
0x1800088d9  mov     [rbp+var_28], 0
0x1800088e1  call    ?GetPrinterAlloc@@YAHPEAXKPEAPEAE@Z; GetPrinterAlloc(void *,ulong,uchar * *)
0x1800088e6  test    eax, eax
0x1800088e8  jz      short loc_18000890C
0x1800088ea  mov     rbx, [rbp+var_28]
0x1800088ee  xor     edi, edi
0x1800088f0  mov     rcx, [rbx]; pSecurityDescriptor
0x1800088f3  call    cs:__imp_GetSecurityDescriptorLength
0x1800088f9  mov     [rsi], rbx
0x1800088fc  mov     rcx, rbx; void *
0x1800088ff  mov     rdx, [rbx]; Src
0x180008902  mov     r8d, eax; Size
0x180008905  call    memmove_0
0x18000890a  jmp     short loc_180008914
0x18000890c  call    cs:__imp_GetLastError
0x180008912  mov     edi, eax
0x180008914  mov     rcx, [rbp+phPrinter]; hPrinter
0x180008918  call    cs:__imp_ClosePrinter
0x18000891e  jmp     short loc_180008928
0x180008920  call    cs:__imp_GetLastError
0x180008926  mov     edi, eax
0x180008928  test    edi, edi
0x18000892a  jle     short loc_180008935
0x18000892c  movzx   edi, di
0x18000892f  or      edi, 80070000h
0x180008935  mov     eax, edi
0x180008937  jmp     short loc_18000893E
0x180008939  mov     eax, 80004003h
0x18000893e  add     rsp, 48h
0x180008942  pop     rdi
0x180008943  pop     rsi
0x180008944  pop     rbx
0x180008945  pop     rbp
0x180008946  retn
```
