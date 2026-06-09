# SxspDeleteDirectoryHelper

- ea: `0x180068510`
- end: `0x18006871c`
- name: `SxspDeleteDirectoryHelper`
- size: `524`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x1800683a4`
- `0x180068510`

## callees

- `0x180032350`
- `0x180050650`
- `0x180057c40`
- `0x18005ce38`
- `0x18005d5a4`
- `0x18005d6b8`
- `0x180068510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006855f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800686ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800686ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006855f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068659`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800686ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800686ec`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180068548`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800686d7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180068548`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800686d7`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180068538`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180068634`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180068538`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180068634`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006861b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180068644`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006861b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180068644`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006866f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18006866f`

## pseudocode

```c
DWORD __fastcall SxspDeleteDirectoryHelper(__int64 a1, struct _WIN32_FIND_DATAW *a2, DWORD *a3)
{
  DWORD result; // eax
  __int64 v7; // r15
  DWORD dwFileAttributes; // r14d
  __int64 v9; // rcx
  __int64 v10; // r8
  HANDLE hFindFile; // [rsp+50h] [rbp+8h] BYREF

  SetFileAttributesW(*(LPCWSTR *)(a1 + 16), 0x80u);
  result = RemoveDirectoryW(*(LPCWSTR *)(a1 + 16));
  if ( !result )
  {
    result = GetLastError();
    if ( result == 145 )
    {
      v7 = *(_QWORD *)(a1 + 32);
      hFindFile = (HANDLE)-1LL;
      if ( !(unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(a1, L"\\*", 2)
        || !CFindFile::Win32FindFirstFile((CFindFile *)&hFindFile, *(const unsigned __int16 **)(a1 + 16), a2) )
      {
        goto LABEL_30;
      }
      do
      {
        if ( !(unsigned int)FusionpIsDotOrDotDot(a2->cFileName) )
        {
          dwFileAttributes = a2->dwFileAttributes;
          CGenericBaseStringBuffer<CUnicodeCharTraits>::Left(a1, v7 + 1);
          v10 = -1;
          do
            ++v10;
          while ( a2->cFileName[v10] );
          if ( (unsigned int)CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(v9, a2->cFileName, v10) )
          {
            if ( (dwFileAttributes & 0x10) != 0 )
            {
              SxspDeleteDirectoryHelper(a1, a2, a3);
            }
            else if ( !DeleteFileW(*(LPCWSTR *)(a1 + 16)) )
            {
              SetFileAttributesW(*(LPCWSTR *)(a1 + 16), 0x80u);
              if ( !DeleteFileW(*(LPCWSTR *)(a1 + 16)) && !*a3 )
                *a3 = GetLastError();
            }
          }
        }
      }
      while ( FindNextFileW(hFindFile, a2) );
      if ( GetLastError() != 18 )
      {
LABEL_30:
        if ( !*a3 )
          *a3 = GetLastError();
      }
      if ( !(unsigned int)CHandleTemplate<&void * hInvalidValue,COperatorFindClose>::Win32Close(&hFindFile) && !*a3 )
        *a3 = GetLastError();
      CGenericBaseStringBuffer<CUnicodeCharTraits>::Left(a1, v7);
      if ( !RemoveDirectoryW(*(LPCWSTR *)(a1 + 16)) && !*a3 )
        *a3 = GetLastError();
      return CHandleTemplate<&void * hInvalidValue,COperatorFindClose>::~CHandleTemplate<&void * hInvalidValue,COperatorFindClose>(&hFindFile);
    }
    else if ( !*a3 )
    {
      *a3 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180068510  mov     [rsp+arg_8], rbx
0x180068515  mov     [rsp+arg_10], rbp
0x18006851a  push    rsi
0x18006851b  push    rdi
0x18006851c  push    r12
0x18006851e  push    r14
0x180068520  push    r15
0x180068522  sub     rsp, 20h
0x180068526  mov     rsi, rdx
0x180068529  mov     rdi, rcx
0x18006852c  mov     rcx, [rcx+10h]; lpFileName
0x180068530  mov     edx, 80h; dwFileAttributes
0x180068535  mov     rbx, r8
0x180068538  call    cs:__imp_SetFileAttributesW
0x18006853f  nop     dword ptr [rax+rax+00h]
0x180068544  mov     rcx, [rdi+10h]; lpPathName
0x180068548  call    cs:__imp_RemoveDirectoryW
0x18006854f  nop     dword ptr [rax+rax+00h]
0x180068554  xor     r12d, r12d
0x180068557  test    eax, eax
0x180068559  jnz     loc_180068704
0x18006855f  call    cs:__imp_GetLastError
0x180068566  nop     dword ptr [rax+rax+00h]
0x18006856b  cmp     eax, 91h
0x180068570  jz      short loc_180068582
0x180068572  cmp     [rbx], r12d
0x180068575  jnz     loc_180068704
0x18006857b  mov     [rbx], eax
0x18006857d  jmp     loc_180068704
0x180068582  mov     r15, [rdi+20h]
0x180068586  lea     rdx, asc_18008DC78; "\\*"
0x18006858d  mov     r8d, 2
0x180068593  mov     [rsp+48h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18006859c  mov     rcx, rdi
0x18006859f  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x1800685a4  test    eax, eax
0x1800685a6  jz      loc_180068694
0x1800685ac  mov     rdx, [rdi+10h]; unsigned __int16 *
0x1800685b0  lea     rcx, [rsp+48h+hFindFile]; this
0x1800685b5  mov     r8, rsi; struct _WIN32_FIND_DATAW *
0x1800685b8  call    ?Win32FindFirstFile@CFindFile@@QEAAHPEBGPEAU_WIN32_FIND_DATAW@@@Z; CFindFile::Win32FindFirstFile(ushort const *,_WIN32_FIND_DATAW *)
0x1800685bd  test    eax, eax
0x1800685bf  jz      loc_180068694
0x1800685c5  lea     rcx, [rsi+2Ch]; unsigned __int16 *
0x1800685c9  call    ?FusionpIsDotOrDotDot@@YAHPEBG@Z; FusionpIsDotOrDotDot(ushort const *)
0x1800685ce  test    eax, eax
0x1800685d0  jnz     loc_180068667
0x1800685d6  mov     r14d, [rsi]
0x1800685d9  lea     rdx, [r15+1]
0x1800685dd  mov     rcx, rdi
0x1800685e0  call    ?Left@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Left(unsigned __int64)
0x1800685e5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800685e9  inc     r8
0x1800685ec  cmp     [rsi+r8*2+2Ch], r12w
0x1800685f2  jnz     short loc_1800685E9
0x1800685f4  lea     rdx, [rsi+2Ch]
0x1800685f8  call    ?Win32Append@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAHPEBG_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Win32Append(ushort const *,unsigned __int64)
0x1800685fd  test    eax, eax
0x1800685ff  jz      short loc_180068667
0x180068601  test    r14b, 10h
0x180068605  jz      short loc_180068617
0x180068607  mov     r8, rbx
0x18006860a  mov     rdx, rsi
0x18006860d  mov     rcx, rdi
0x180068610  call    SxspDeleteDirectoryHelper
0x180068615  jmp     short loc_180068667
0x180068617  mov     rcx, [rdi+10h]; lpFileName
0x18006861b  call    cs:__imp_DeleteFileW
0x180068622  nop     dword ptr [rax+rax+00h]
0x180068627  test    eax, eax
0x180068629  jnz     short loc_180068667
0x18006862b  mov     rcx, [rdi+10h]; lpFileName
0x18006862f  mov     edx, 80h; dwFileAttributes
0x180068634  call    cs:__imp_SetFileAttributesW
0x18006863b  nop     dword ptr [rax+rax+00h]
0x180068640  mov     rcx, [rdi+10h]; lpFileName
0x180068644  call    cs:__imp_DeleteFileW
0x18006864b  nop     dword ptr [rax+rax+00h]
0x180068650  test    eax, eax
0x180068652  jnz     short loc_180068667
0x180068654  cmp     [rbx], r12d
0x180068657  jnz     short loc_180068667
0x180068659  call    cs:__imp_GetLastError
0x180068660  nop     dword ptr [rax+rax+00h]
0x180068665  mov     [rbx], eax
0x180068667  mov     rcx, [rsp+48h+hFindFile]; hFindFile
0x18006866c  mov     rdx, rsi; lpFindFileData
0x18006866f  call    cs:__imp_FindNextFileW
0x180068676  nop     dword ptr [rax+rax+00h]
0x18006867b  test    eax, eax
0x18006867d  jnz     loc_1800685C5
0x180068683  call    cs:__imp_GetLastError
0x18006868a  nop     dword ptr [rax+rax+00h]
0x18006868f  cmp     eax, 12h
0x180068692  jz      short loc_1800686A7
0x180068694  cmp     [rbx], r12d
0x180068697  jnz     short loc_1800686A7
0x180068699  call    cs:__imp_GetLastError
0x1800686a0  nop     dword ptr [rax+rax+00h]
0x1800686a5  mov     [rbx], eax
0x1800686a7  lea     rcx, [rsp+48h+hFindFile]
0x1800686ac  call    ?Win32Close@?$CHandleTemplate@$1?hInvalidValue@@3QEAXEAVCOperatorFindClose@@@@QEAAHXZ; CHandleTemplate<&void * hInvalidValue,COperatorFindClose>::Win32Close(void)
0x1800686b1  test    eax, eax
0x1800686b3  jnz     short loc_1800686C8
0x1800686b5  cmp     [rbx], r12d
0x1800686b8  jnz     short loc_1800686C8
0x1800686ba  call    cs:__imp_GetLastError
0x1800686c1  nop     dword ptr [rax+rax+00h]
0x1800686c6  mov     [rbx], eax
0x1800686c8  mov     rdx, r15
0x1800686cb  mov     rcx, rdi
0x1800686ce  call    ?Left@?$CGenericBaseStringBuffer@VCUnicodeCharTraits@@@@QEAAH_K@Z; CGenericBaseStringBuffer<CUnicodeCharTraits>::Left(unsigned __int64)
0x1800686d3  mov     rcx, [rdi+10h]; lpPathName
0x1800686d7  call    cs:__imp_RemoveDirectoryW
0x1800686de  nop     dword ptr [rax+rax+00h]
0x1800686e3  test    eax, eax
0x1800686e5  jnz     short loc_1800686FA
0x1800686e7  cmp     [rbx], r12d
0x1800686ea  jnz     short loc_1800686FA
0x1800686ec  call    cs:__imp_GetLastError
0x1800686f3  nop     dword ptr [rax+rax+00h]
0x1800686f8  mov     [rbx], eax
0x1800686fa  lea     rcx, [rsp+48h+hFindFile]
0x1800686ff  call    ??1?$CHandleTemplate@$1?hInvalidValue@@3QEAXEAVCOperatorFindClose@@@@QEAA@XZ; CHandleTemplate<&void * hInvalidValue,COperatorFindClose>::~CHandleTemplate<&void * hInvalidValue,COperatorFindClose>(void)
0x180068704  mov     rbx, [rsp+48h+arg_8]
0x180068709  mov     rbp, [rsp+48h+arg_10]
0x18006870e  add     rsp, 20h
0x180068712  pop     r15
0x180068714  pop     r14
0x180068716  pop     r12
0x180068718  pop     rdi
0x180068719  pop     rsi
0x18006871a  retn
```
