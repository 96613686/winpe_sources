# UmpoImportTempDirectoryCleanup

- ea: `0x18001257c`
- end: `0x180012742`
- name: `UmpoImportTempDirectoryCleanup`
- size: `454`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180012254`

## callees

- `0x180001170`
- `0x18000abb0`
- `0x180010070`
- `0x180010946`
- `0x18001257c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800125be`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800125be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001270f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800126e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001270f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180012636`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180012636`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800126c4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800126c4`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800126d6`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800126d6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180012707`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180012707`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800126f8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800126f8`

## pseudocode

```c
__int64 __fastcall UmpoImportTempDirectoryCleanup(STRSAFE_PCNZWCH pszSrc)
{
  wchar_t *v2; // rax
  size_t *v3; // r8
  DWORD LastError; // ebx
  size_t cchToCopy; // rax
  HANDLE FirstFileW; // rdi
  int v7; // edx
  int v8; // edx
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t FileName[264]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t v13[264]; // [rsp+6A0h] [rbp+5A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v2 = wcsrchr(pszSrc, 0x5Cu);
  if ( !v2 )
    return 3;
  cchToCopy = v2 - pszSrc;
  if ( cchToCopy > 0x7FFFFFFE
    || StringCopyWorkerW(pszDest, 0x104u, v3, pszSrc, cchToCopy) < 0
    || StringCchPrintfW(FileName, 0x104u, L"%s\\*.*", pszDest) < 0 )
  {
    return 87;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return GetLastError();
  while ( 1 )
  {
    v7 = FindFileData.cFileName[0] - 46;
    if ( FindFileData.cFileName[0] == 46 )
      v7 = FindFileData.cFileName[1];
    if ( v7 )
    {
      v8 = FindFileData.cFileName[0] - 46;
      if ( FindFileData.cFileName[0] == 46 )
      {
        v8 = FindFileData.cFileName[1] - 46;
        if ( FindFileData.cFileName[1] == 46 )
          v8 = FindFileData.cFileName[2];
      }
      if ( v8 )
        break;
    }
LABEL_17:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
    {
      LastError = GetLastError();
      if ( LastError != 18 )
        goto LABEL_21;
      if ( RemoveDirectoryW(pszDest) )
      {
        LastError = 0;
        goto LABEL_21;
      }
LABEL_22:
      LastError = GetLastError();
      goto LABEL_21;
    }
  }
  if ( StringCchPrintfW(v13, 0x104u, L"%s\\%s", pszDest, FindFileData.cFileName) >= 0 )
  {
    if ( !DeleteFileW(v13) )
      goto LABEL_22;
    goto LABEL_17;
  }
  LastError = 87;
LABEL_21:
  FindClose(FirstFileW);
  return LastError;
}

```

## disassembly

```asm
0x18001257c  push    rbp
0x18001257e  push    rbx
0x18001257f  push    rsi
0x180012580  push    rdi
0x180012581  lea     rbp, [rsp-7C8h]
0x180012589  sub     rsp, 8C8h
0x180012590  mov     rax, cs:__security_cookie
0x180012597  xor     rax, rsp
0x18001259a  mov     [rbp+7E0h+var_30], rax
0x1800125a1  mov     rbx, rcx
0x1800125a4  xor     edx, edx; Val
0x1800125a6  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x1800125ab  mov     r8d, 250h; Size
0x1800125b1  call    memset_0
0x1800125b6  mov     edx, 5Ch ; '\'; Ch
0x1800125bb  mov     rcx, rbx; Str
0x1800125be  call    cs:__imp_wcsrchr
0x1800125c4  test    rax, rax
0x1800125c7  jnz     short loc_1800125D1
0x1800125c9  lea     ebx, [rax+3]
0x1800125cc  jmp     loc_180012725
0x1800125d1  sub     rax, rbx
0x1800125d4  sar     rax, 1
0x1800125d7  cmp     rax, 7FFFFFFEh
0x1800125dd  ja      loc_180012720
0x1800125e3  mov     esi, 104h
0x1800125e8  mov     [rsp+8E0h+cchToCopy], rax; cchToCopy
0x1800125ed  mov     edx, esi; cchDest
0x1800125ef  lea     rcx, [rbp+7E0h+pszDest]; pszDest
0x1800125f6  mov     r9, rbx; pszSrc
0x1800125f9  call    StringCopyWorkerW
0x1800125fe  test    eax, eax
0x180012600  js      loc_180012720
0x180012606  lea     r9, [rbp+7E0h+pszDest]
0x18001260d  mov     edx, esi; cchDest
0x18001260f  lea     r8, aS; "%s\\*.*"
0x180012616  lea     rcx, [rbp+7E0h+FileName]; pszDest
0x18001261d  call    StringCchPrintfW
0x180012622  test    eax, eax
0x180012624  js      loc_180012720
0x18001262a  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18001262f  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x180012636  call    cs:__imp_FindFirstFileW
0x18001263c  mov     rdi, rax
0x18001263f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180012643  jnz     short loc_180012652
0x180012645  call    cs:__imp_GetLastError
0x18001264b  mov     ebx, eax
0x18001264d  jmp     loc_180012725
0x180012652  mov     ebx, 2Eh ; '.'
0x180012657  movzx   edx, [rsp+8E0h+FindFileData.cFileName]
0x18001265c  sub     edx, ebx
0x18001265e  jnz     short loc_18001266C
0x180012660  movzx   edx, [rsp+8E0h+FindFileData.cFileName+2]
0x180012665  xor     eax, eax
0x180012667  movzx   ecx, ax
0x18001266a  sub     edx, ecx
0x18001266c  test    edx, edx
0x18001266e  jz      short loc_1800126CE
0x180012670  movzx   edx, [rsp+8E0h+FindFileData.cFileName]
0x180012675  sub     edx, ebx
0x180012677  jnz     short loc_18001268E
0x180012679  movzx   edx, [rsp+8E0h+FindFileData.cFileName+2]
0x18001267e  sub     edx, ebx
0x180012680  jnz     short loc_18001268E
0x180012682  movzx   edx, [rsp+8E0h+FindFileData.cFileName+4]
0x180012687  xor     eax, eax
0x180012689  movzx   ecx, ax
0x18001268c  sub     edx, ecx
0x18001268e  test    edx, edx
0x180012690  jz      short loc_1800126CE
0x180012692  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x180012697  mov     rdx, rsi; cchDest
0x18001269a  lea     r9, [rbp+7E0h+pszDest]
0x1800126a1  mov     [rsp+8E0h+cchToCopy], rax
0x1800126a6  lea     r8, aSS; "%s\\%s"
0x1800126ad  lea     rcx, [rbp+7E0h+var_240]; pszDest
0x1800126b4  call    StringCchPrintfW
0x1800126b9  test    eax, eax
0x1800126bb  js      short loc_180012719
0x1800126bd  lea     rcx, [rbp+7E0h+var_240]; lpFileName
0x1800126c4  call    cs:__imp_DeleteFileW
0x1800126ca  test    eax, eax
0x1800126cc  jz      short loc_18001270F
0x1800126ce  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x1800126d3  mov     rcx, rdi; hFindFile
0x1800126d6  call    cs:__imp_FindNextFileW
0x1800126dc  test    eax, eax
0x1800126de  jnz     loc_180012657
0x1800126e4  call    cs:__imp_GetLastError
0x1800126ea  mov     ebx, eax
0x1800126ec  cmp     eax, 12h
0x1800126ef  jnz     short loc_180012704
0x1800126f1  lea     rcx, [rbp+7E0h+pszDest]; lpPathName
0x1800126f8  call    cs:__imp_RemoveDirectoryW
0x1800126fe  test    eax, eax
0x180012700  jz      short loc_18001270F
0x180012702  xor     ebx, ebx
0x180012704  mov     rcx, rdi; hFindFile
0x180012707  call    cs:__imp_FindClose
0x18001270d  jmp     short loc_180012725
0x18001270f  call    cs:__imp_GetLastError
0x180012715  mov     ebx, eax
0x180012717  jmp     short loc_180012704
0x180012719  mov     ebx, 57h ; 'W'
0x18001271e  jmp     short loc_180012704
0x180012720  mov     ebx, 57h ; 'W'
0x180012725  mov     eax, ebx
0x180012727  mov     rcx, [rbp+7E0h+var_30]
0x18001272e  xor     rcx, rsp; StackCookie
0x180012731  call    __security_check_cookie
0x180012736  add     rsp, 8C8h
0x18001273d  pop     rdi
0x18001273e  pop     rsi
0x18001273f  pop     rbx
0x180012740  pop     rbp
0x180012741  retn
```
