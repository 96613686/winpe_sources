# CExFileOperation::FOCopyFile(ushort const *,ushort const *,int)

- ea: `0x383a987e4`
- end: `0x383a9892b`
- name: `?FOCopyFile@CExFileOperation@@QEAAJPEBG0H@Z`
- size: `327`
- prototype: `int(CExFileOperation *__hidden this, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x383a98984`

## callees

- `0x383a987e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x383a988ab`
- `KERNEL32!GetLastError` at `0x383a988da`
- `KERNEL32!GetLastError` at `0x383a9890e`
- `KERNEL32!GetLastError` at `0x383a988ab`
- `KERNEL32!GetLastError` at `0x383a988da`
- `KERNEL32!GetLastError` at `0x383a9890e`
- `KERNEL32!CopyFileW` at `0x383a988d0`
- `KERNEL32!CopyFileW` at `0x383a988d0`
- `ADVAPI32!SetFileSecurityW` at `0x383a98904`
- `ADVAPI32!SetFileSecurityW` at `0x383a98904`
- `ADVAPI32!GetFileSecurityW` at `0x383a98849`
- `ADVAPI32!GetFileSecurityW` at `0x383a988a1`
- `ADVAPI32!GetFileSecurityW` at `0x383a98849`
- `ADVAPI32!GetFileSecurityW` at `0x383a988a1`

## pseudocode

```c
__int64 __fastcall CExFileOperation::FOCopyFile(
        PSECURITY_DESCRIPTOR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rax
  unsigned int v7; // ebx
  BOOL FileSecurityW; // eax
  __int64 v9; // rbx
  void *v10; // rax
  signed int LastError; // eax
  signed int v12; // r11d
  __int64 result; // rax
  DWORD nLengthNeeded; // [rsp+40h] [rbp+8h] BYREF

  nLengthNeeded = 0;
  if ( !*this )
  {
    v6 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl->Alloc)(g_pMO, 120);
    *this = (PSECURITY_DESCRIPTOR)v6;
    if ( !v6 )
      return (unsigned int)-2147024882;
  }
  FileSecurityW = GetFileSecurityW(a2, 4u, *this, 0x78u, &nLengthNeeded);
  v9 = nLengthNeeded;
  if ( nLengthNeeded > 0x78 )
  {
    if ( *this )
      ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl->Free)(g_pMO);
    *this = 0;
    v10 = (void *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl->Alloc)(g_pMO, v9);
    *this = v10;
    if ( !v10 )
      return (unsigned int)-2147024882;
    FileSecurityW = GetFileSecurityW(a2, 4u, v10, v9, &nLengthNeeded);
  }
  if ( FileSecurityW )
  {
    v7 = 0;
  }
  else
  {
    LastError = GetLastError();
    v7 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v7 = LastError;
  }
  if ( (v7 & 0x80000000) != 0 )
    return v7;
  if ( CopyFileW(a2, a3, 0) )
  {
    if ( *this && !SetFileSecurityW(a3, 4u, *this) )
      GetLastError();
    return v7;
  }
  v12 = GetLastError();
  result = (unsigned __int16)v12 | 0x80070000;
  if ( v12 <= 0 )
    return (unsigned int)v12;
  return result;
}

```

## disassembly

```asm
0x383a987e4  mov     rax, rsp
0x383a987e7  mov     [rax+10h], rbx
0x383a987eb  mov     [rax+18h], rbp
0x383a987ef  mov     [rax+20h], rsi
0x383a987f3  push    rdi
0x383a987f4  sub     rsp, 30h
0x383a987f8  and     dword ptr [rax+8], 0
0x383a987fc  cmp     qword ptr [rcx], 0
0x383a98800  mov     rbp, r8
0x383a98803  mov     rsi, rdx
0x383a98806  mov     rdi, rcx
0x383a98809  jnz     short loc_383A9882F
0x383a9880b  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98812  mov     edx, 78h ; 'x'
0x383a98817  mov     rax, [rcx]
0x383a9881a  call    qword ptr [rax+18h]
0x383a9881d  mov     [rdi], rax
0x383a98820  test    rax, rax
0x383a98823  jnz     short loc_383A9882F
0x383a98825  mov     ebx, 8007000Eh
0x383a9882a  jmp     loc_383A98914
0x383a9882f  mov     r8, [rdi]; pSecurityDescriptor
0x383a98832  mov     r9d, 78h ; 'x'; nLength
0x383a98838  lea     rax, [rsp+38h+nLengthNeeded]
0x383a9883d  lea     edx, [r9-74h]; RequestedInformation
0x383a98841  mov     rcx, rsi; lpFileName
0x383a98844  mov     [rsp+38h+lpnLengthNeeded], rax; lpnLengthNeeded
0x383a98849  call    cs:__imp_GetFileSecurityW
0x383a9884f  mov     ebx, [rsp+38h+nLengthNeeded]
0x383a98853  cmp     ebx, 78h ; 'x'
0x383a98856  jbe     short loc_383A988A7
0x383a98858  mov     rdx, [rdi]
0x383a9885b  test    rdx, rdx
0x383a9885e  jz      short loc_383A9886D
0x383a98860  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98867  mov     rax, [rcx]
0x383a9886a  call    qword ptr [rax+28h]
0x383a9886d  and     qword ptr [rdi], 0
0x383a98871  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98878  mov     rdx, rbx
0x383a9887b  mov     rax, [rcx]
0x383a9887e  call    qword ptr [rax+18h]
0x383a98881  mov     [rdi], rax
0x383a98884  test    rax, rax
0x383a98887  jz      short loc_383A98825
0x383a98889  lea     rcx, [rsp+38h+nLengthNeeded]
0x383a9888e  mov     r9d, ebx; nLength
0x383a98891  mov     r8, rax; pSecurityDescriptor
0x383a98894  mov     [rsp+38h+lpnLengthNeeded], rcx; lpnLengthNeeded
0x383a98899  mov     rcx, rsi; lpFileName
0x383a9889c  mov     edx, 4; RequestedInformation
0x383a988a1  call    cs:__imp_GetFileSecurityW
0x383a988a7  test    eax, eax
0x383a988a9  jnz     short loc_383A988C1
0x383a988ab  call    cs:__imp_GetLastError
0x383a988b1  movzx   ebx, ax
0x383a988b4  or      ebx, 80070000h
0x383a988ba  test    eax, eax
0x383a988bc  cmovle  ebx, eax
0x383a988bf  jmp     short loc_383A988C3
0x383a988c1  xor     ebx, ebx
0x383a988c3  test    ebx, ebx
0x383a988c5  js      short loc_383A98914
0x383a988c7  xor     r8d, r8d; bFailIfExists
0x383a988ca  mov     rdx, rbp; lpNewFileName
0x383a988cd  mov     rcx, rsi; lpExistingFileName
0x383a988d0  call    cs:__imp_CopyFileW
0x383a988d6  test    eax, eax
0x383a988d8  jnz     short loc_383A988F4
0x383a988da  call    cs:__imp_GetLastError
0x383a988e0  mov     r11d, eax
0x383a988e3  movzx   eax, ax
0x383a988e6  or      eax, 80070000h
0x383a988eb  test    r11d, r11d
0x383a988ee  cmovle  eax, r11d
0x383a988f2  jmp     short loc_383A98916
0x383a988f4  mov     r8, [rdi]; pSecurityDescriptor
0x383a988f7  test    r8, r8
0x383a988fa  jz      short loc_383A98914
0x383a988fc  mov     edx, 4; SecurityInformation
0x383a98901  mov     rcx, rbp; lpFileName
0x383a98904  call    cs:__imp_SetFileSecurityW
0x383a9890a  test    eax, eax
0x383a9890c  jnz     short loc_383A98914
0x383a9890e  call    cs:__imp_GetLastError
0x383a98914  mov     eax, ebx
0x383a98916  mov     rbx, [rsp+38h+arg_8]
0x383a9891b  mov     rbp, [rsp+38h+arg_10]
0x383a98920  mov     rsi, [rsp+38h+arg_18]
0x383a98925  add     rsp, 30h
0x383a98929  pop     rdi
0x383a9892a  retn
```
