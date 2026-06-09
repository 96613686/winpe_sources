# CEXAutoBackupFile::BackupFile(ushort const *)

- ea: `0x383a98984`
- end: `0x383a98b51`
- name: `?BackupFile@CEXAutoBackupFile@@QEAAJPEBG@Z`
- size: `461`
- prototype: `__int64 __fastcall(CEXAutoBackupFile *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x3839fb130`

## callees

- `0x3838434c0`
- `0x38387da60`
- `0x3839adac0`
- `0x383a987e4`
- `0x383a98984`

## import_xrefs

- `MSVCR100!_wsplitpath_s` at `0x383a98a07`
- `MSVCR100!_wsplitpath_s` at `0x383a98a07`
- `KERNEL32!GetLastError` at `0x383a98ac1`
- `KERNEL32!GetLastError` at `0x383a98ac1`
- `KERNEL32!GetTempFileNameW` at `0x383a98ab7`
- `KERNEL32!GetTempFileNameW` at `0x383a98ab7`

## pseudocode

```c
__int64 __fastcall CEXAutoBackupFile::BackupFile(CEXAutoBackupFile *this, const unsigned __int16 *a2)
{
  __int64 result; // rax
  int v5; // edi
  __int64 v6; // rax
  unsigned __int64 v7; // rbp
  __int64 v8; // rax
  unsigned __int64 v9; // kr00_8
  __int64 v10; // rax
  unsigned __int16 *v11; // rcx
  signed int v12; // edi
  signed int LastError; // eax
  wchar_t Drive[264]; // [rsp+50h] [rbp-648h] BYREF
  wchar_t PrefixString[256]; // [rsp+260h] [rbp-438h] BYREF
  wchar_t Dir[264]; // [rsp+460h] [rbp-238h] BYREF

  if ( *((_QWORD *)this + 2) && *((_QWORD *)this + 1) )
    return 2147500037LL;
  _wsplitpath_s(a2, Drive, 0x104u, Dir, 0x104u, PrefixString, 0x100u, 0, 0);
  result = StringCchCatW(Drive, 0x104u, Dir);
  v5 = result;
  if ( (int)result >= 0 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = v6 + 1;
    v9 = v6 + 1;
    v8 = 2 * (v6 + 1);
    if ( !is_mul_ok(v9, 2u) )
      v8 = -1;
    *((_QWORD *)this + 1) = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, v8);
    v10 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Free)(g_pMO, 520);
    v11 = (unsigned __int16 *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 2) = v10;
    if ( !v11 || !v10 )
      v5 = -2147024882;
    if ( v5 < 0 )
      goto LABEL_26;
    result = StringCchCopyW(v11, v7, a2);
    v12 = result;
    if ( (int)result < 0 )
      return result;
    if ( !GetTempFileNameW(Drive, PrefixString, 0, *((LPWSTR *)this + 2)) )
    {
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
    }
    if ( v12 < 0
      || (int)CExFileOperation::FOCopyFile(
                (PSECURITY_DESCRIPTOR *)this,
                *((const unsigned __int16 **)this + 1),
                *((const unsigned __int16 **)this + 2)) < 0 )
    {
LABEL_26:
      if ( *((_QWORD *)this + 2) )
      {
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
        *((_QWORD *)this + 2) = 0;
      }
      if ( *((_QWORD *)this + 1) )
      {
        ((void (__fastcall *)(struct IMalloc *))g_pMO->lpVtbl[1].DidAlloc)(g_pMO);
        *((_QWORD *)this + 1) = 0;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x383a98984  mov     [rsp+arg_10], rbx
0x383a98989  mov     [rsp+arg_18], rbp
0x383a9898e  push    rsi
0x383a9898f  push    rdi
0x383a98990  push    r14
0x383a98992  sub     rsp, 680h
0x383a98999  mov     rax, cs:__security_cookie
0x383a989a0  xor     rax, rsp
0x383a989a3  mov     [rsp+698h+var_28], rax
0x383a989ab  xor     r14d, r14d
0x383a989ae  mov     rsi, rdx
0x383a989b1  mov     rbx, rcx
0x383a989b4  cmp     [rcx+10h], r14
0x383a989b8  jz      short loc_383A989CA
0x383a989ba  cmp     [rcx+8], r14
0x383a989be  jz      short loc_383A989CA
0x383a989c0  mov     eax, 80004005h
0x383a989c5  jmp     loc_383A98B29
0x383a989ca  mov     [rsp+698h+ExtCount], r14; ExtCount
0x383a989cf  mov     [rsp+698h+Ext], r14; Ext
0x383a989d4  lea     rax, [rsp+698h+PrefixString]
0x383a989dc  mov     edi, 104h
0x383a989e1  mov     [rsp+698h+FilenameCount], 100h; FilenameCount
0x383a989ea  mov     [rsp+698h+Filename], rax; Filename
0x383a989ef  lea     r9, [rsp+698h+Dir]; Dir
0x383a989f7  lea     rdx, [rsp+698h+Drive]; Drive
0x383a989fc  mov     rcx, rsi; FullPath
0x383a989ff  mov     r8d, edi; DriveCount
0x383a98a02  mov     [rsp+698h+DirCount], rdi; DirCount
0x383a98a07  call    cs:__imp__wsplitpath_s
0x383a98a0d  lea     r8, [rsp+698h+Dir]; unsigned __int16 *
0x383a98a15  lea     rcx, [rsp+698h+Drive]; unsigned __int16 *
0x383a98a1a  mov     edx, edi; unsigned __int64
0x383a98a1c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x383a98a21  mov     edi, eax
0x383a98a23  test    eax, eax
0x383a98a25  js      loc_383A98B29
0x383a98a2b  or      r9, 0FFFFFFFFFFFFFFFFh
0x383a98a2f  mov     rax, r9
0x383a98a32  inc     rax
0x383a98a35  cmp     [rsi+rax*2], r14w
0x383a98a3a  jnz     short loc_383A98A32
0x383a98a3c  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98a43  lea     rbp, [rax+1]
0x383a98a47  mov     eax, 2
0x383a98a4c  mov     r8, [rcx]
0x383a98a4f  mul     rbp
0x383a98a52  cmovo   rax, r9
0x383a98a56  mov     rdx, rax
0x383a98a59  call    qword ptr [r8+70h]
0x383a98a5d  mov     edx, 208h
0x383a98a62  mov     [rbx+8], rax
0x383a98a66  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98a6d  mov     rax, [rcx]
0x383a98a70  call    qword ptr [rax+70h]
0x383a98a73  mov     rcx, [rbx+8]; unsigned __int16 *
0x383a98a77  mov     [rbx+10h], rax
0x383a98a7b  test    rcx, rcx
0x383a98a7e  jz      short loc_383A98A85
0x383a98a80  test    rax, rax
0x383a98a83  jnz     short loc_383A98A8A
0x383a98a85  mov     edi, 8007000Eh
0x383a98a8a  test    edi, edi
0x383a98a8c  js      short loc_383A98AED
0x383a98a8e  mov     r8, rsi; unsigned __int16 *
0x383a98a91  mov     rdx, rbp; unsigned __int64
0x383a98a94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x383a98a99  mov     edi, eax
0x383a98a9b  test    eax, eax
0x383a98a9d  js      loc_383A98B29
0x383a98aa3  mov     r9, [rbx+10h]; lpTempFileName
0x383a98aa7  lea     rdx, [rsp+698h+PrefixString]; lpPrefixString
0x383a98aaf  lea     rcx, [rsp+698h+Drive]; lpPathName
0x383a98ab4  xor     r8d, r8d; uUnique
0x383a98ab7  call    cs:__imp_GetTempFileNameW
0x383a98abd  test    eax, eax
0x383a98abf  jnz     short loc_383A98AD5
0x383a98ac1  call    cs:__imp_GetLastError
0x383a98ac7  movzx   edi, ax
0x383a98aca  or      edi, 80070000h
0x383a98ad0  test    eax, eax
0x383a98ad2  cmovle  edi, eax
0x383a98ad5  test    edi, edi
0x383a98ad7  js      short loc_383A98AED
0x383a98ad9  mov     r8, [rbx+10h]; unsigned __int16 *
0x383a98add  mov     rdx, [rbx+8]; unsigned __int16 *
0x383a98ae1  mov     rcx, rbx; this
0x383a98ae4  call    ?FOCopyFile@CExFileOperation@@QEAAJPEBG0H@Z; CExFileOperation::FOCopyFile(ushort const *,ushort const *,int)
0x383a98ae9  test    eax, eax
0x383a98aeb  jns     short loc_383A98B27
0x383a98aed  mov     rdx, [rbx+10h]
0x383a98af1  test    rdx, rdx
0x383a98af4  jz      short loc_383A98B0A
0x383a98af6  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98afd  mov     rax, [rcx]
0x383a98b00  call    qword ptr [rax+80h]
0x383a98b06  mov     [rbx+10h], r14
0x383a98b0a  mov     rdx, [rbx+8]
0x383a98b0e  test    rdx, rdx
0x383a98b11  jz      short loc_383A98B27
0x383a98b13  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x383a98b1a  mov     rax, [rcx]
0x383a98b1d  call    qword ptr [rax+80h]
0x383a98b23  mov     [rbx+8], r14
0x383a98b27  xor     eax, eax
0x383a98b29  mov     rcx, [rsp+698h+var_28]
0x383a98b31  xor     rcx, rsp; StackCookie
0x383a98b34  call    __security_check_cookie
0x383a98b39  lea     r11, [rsp+698h+var_18]
0x383a98b41  mov     rbx, [r11+30h]
0x383a98b45  mov     rbp, [r11+38h]
0x383a98b49  mov     rsp, r11
0x383a98b4c  pop     r14
0x383a98b4e  pop     rdi
0x383a98b4f  pop     rsi
0x383a98b50  retn
```
