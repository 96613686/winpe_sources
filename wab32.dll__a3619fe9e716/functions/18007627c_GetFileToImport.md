# _GetFileToImport

- ea: `0x18007627c`
- end: `0x1800763fa`
- name: `_GetFileToImport`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180075bf8`

## callees

- `0x1800045e4`
- `0x180005d08`
- `0x180009aec`
- `0x18007627c`
- `0x180091eaa`
- `0x180091ef0`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x180076314`
- `SHLWAPI!PathRemoveBlanksW` at `0x180076314`
- `KERNEL32!CopyFileW` at `0x180076386`
- `KERNEL32!CopyFileW` at `0x180076386`
- `KERNEL32!SetFileAttributesW` at `0x1800763a9`
- `KERNEL32!SetFileAttributesW` at `0x1800763a9`
- `KERNEL32!GetFileAttributesW` at `0x180076321`
- `KERNEL32!GetFileAttributesW` at `0x180076395`
- `KERNEL32!GetFileAttributesW` at `0x180076321`
- `KERNEL32!GetFileAttributesW` at `0x180076395`
- `KERNEL32!GetTempPathW` at `0x180076344`
- `KERNEL32!GetTempPathW` at `0x180076344`
- `KERNEL32!GetTempFileNameW` at `0x18007636d`
- `KERNEL32!GetTempFileNameW` at `0x18007636d`

## pseudocode

```c
__int64 __fastcall GetFileToImport(__int64 a1, const unsigned __int16 *a2, void **a3)
{
  __int64 v5; // rax
  int v6; // ecx
  WCHAR TempFileName[264]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPath[264]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR Buffer[264]; // [rsp+440h] [rbp+340h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(TempFileName, 0, 0x208u);
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    if ( v5 )
    {
      StringCchCopyW(pszPath, 0x104u, a2);
      PathRemoveBlanksW(pszPath);
    }
  }
  if ( GetFileAttributesW(pszPath) == -1 )
    return (unsigned int)-2147467259;
  if ( !GetTempPathW(0x104u, Buffer) || !GetTempFileNameW(Buffer, L"WAB_IMPORT", 0, TempFileName) )
    return (unsigned int)HrGetLastError();
  if ( !CopyFileW(pszPath, TempFileName, 0) || GetFileAttributesW(TempFileName) == -1 )
  {
    return (unsigned int)-2147467259;
  }
  else
  {
    SetFileAttributesW(TempFileName, 0x80u);
    memset_0(a3[1], 0, 2LL * *(unsigned int *)a3);
    *(_DWORD *)a3 = 0;
    v6 = STRW::Append((STRW *)a3, TempFileName);
    if ( v6 >= 0 )
      return 0;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18007627c  mov     [rsp-8+arg_0], rbx
0x180076281  push    rbp
0x180076282  push    rsi
0x180076283  push    rdi
0x180076284  lea     rbp, [rsp-560h]
0x18007628c  sub     rsp, 660h
0x180076293  mov     rax, cs:__security_cookie
0x18007629a  xor     rax, rsp
0x18007629d  mov     [rbp+570h+var_20], rax
0x1800762a4  mov     rdi, r8
0x1800762a7  lea     rcx, [rbp+570h+pszPath]; void *
0x1800762ae  mov     rbx, rdx
0x1800762b1  mov     esi, 208h
0x1800762b6  mov     r8d, esi; Size
0x1800762b9  xor     edx, edx; Val
0x1800762bb  call    memset_0
0x1800762c0  mov     r8d, esi; Size
0x1800762c3  lea     rcx, [rbp+570h+Buffer]; void *
0x1800762ca  xor     edx, edx; Val
0x1800762cc  call    memset_0
0x1800762d1  mov     r8d, esi; Size
0x1800762d4  lea     rcx, [rsp+670h+TempFileName]; void *
0x1800762d9  xor     edx, edx; Val
0x1800762db  call    memset_0
0x1800762e0  xor     esi, esi
0x1800762e2  test    rbx, rbx
0x1800762e5  jz      short loc_18007631A
0x1800762e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800762eb  inc     rax
0x1800762ee  cmp     [rbx+rax*2], si
0x1800762f2  jnz     short loc_1800762EB
0x1800762f4  test    rax, rax
0x1800762f7  jz      short loc_18007631A
0x1800762f9  mov     r8, rbx; unsigned __int16 *
0x1800762fc  lea     rcx, [rbp+570h+pszPath]; unsigned __int16 *
0x180076303  mov     edx, 104h; unsigned __int64
0x180076308  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007630d  lea     rcx, [rbp+570h+pszPath]; pszPath
0x180076314  call    cs:__imp_PathRemoveBlanksW
0x18007631a  lea     rcx, [rbp+570h+pszPath]; lpFileName
0x180076321  call    cs:__imp_GetFileAttributesW
0x180076327  or      ebx, 0FFFFFFFFh
0x18007632a  cmp     eax, ebx
0x18007632c  jnz     short loc_180076338
0x18007632e  mov     ecx, 80004005h
0x180076333  jmp     loc_1800763D6
0x180076338  lea     rdx, [rbp+570h+Buffer]; lpBuffer
0x18007633f  mov     ecx, 104h; nBufferLength
0x180076344  call    cs:__imp_GetTempPathW
0x18007634a  test    eax, eax
0x18007634c  jnz     short loc_180076357
0x18007634e  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180076353  mov     ecx, eax
0x180076355  jmp     short loc_1800763D6
0x180076357  lea     r9, [rsp+670h+TempFileName]; lpTempFileName
0x18007635c  xor     r8d, r8d; uUnique
0x18007635f  lea     rdx, aWabImport; "WAB_IMPORT"
0x180076366  lea     rcx, [rbp+570h+Buffer]; lpPathName
0x18007636d  call    cs:__imp_GetTempFileNameW
0x180076373  test    eax, eax
0x180076375  jz      short loc_18007634E
0x180076377  xor     r8d, r8d; bFailIfExists
0x18007637a  lea     rdx, [rsp+670h+TempFileName]; lpNewFileName
0x18007637f  lea     rcx, [rbp+570h+pszPath]; lpExistingFileName
0x180076386  call    cs:__imp_CopyFileW
0x18007638c  test    eax, eax
0x18007638e  jz      short loc_18007632E
0x180076390  lea     rcx, [rsp+670h+TempFileName]; lpFileName
0x180076395  call    cs:__imp_GetFileAttributesW
0x18007639b  cmp     eax, ebx
0x18007639d  jz      short loc_18007632E
0x18007639f  mov     edx, 80h; dwFileAttributes
0x1800763a4  lea     rcx, [rsp+670h+TempFileName]; lpFileName
0x1800763a9  call    cs:__imp_SetFileAttributesW
0x1800763af  mov     r8d, [rdi]
0x1800763b2  xor     edx, edx; Val
0x1800763b4  mov     rcx, [rdi+8]; void *
0x1800763b8  add     r8, r8; Size
0x1800763bb  call    memset_0
0x1800763c0  lea     rdx, [rsp+670h+TempFileName]; unsigned __int16 *
0x1800763c5  mov     [rdi], esi
0x1800763c7  mov     rcx, rdi; this
0x1800763ca  call    ?Append@STRW@@QEAAJPEBG@Z; STRW::Append(ushort const *)
0x1800763cf  test    eax, eax
0x1800763d1  mov     ecx, eax
0x1800763d3  cmovns  ecx, esi
0x1800763d6  mov     eax, ecx
0x1800763d8  mov     rcx, [rbp+570h+var_20]
0x1800763df  xor     rcx, rsp; StackCookie
0x1800763e2  call    __security_check_cookie
0x1800763e7  mov     rbx, [rsp+670h+arg_0]
0x1800763ef  add     rsp, 660h
0x1800763f6  pop     rdi
0x1800763f7  pop     rsi
0x1800763f8  pop     rbp
0x1800763f9  retn
```
