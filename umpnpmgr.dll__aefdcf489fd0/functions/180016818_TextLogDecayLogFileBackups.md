# TextLogDecayLogFileBackups

- ea: `0x180016818`
- end: `0x180016ca4`
- name: `TextLogDecayLogFileBackups`
- size: `1164`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1800027a0`
- `0x1800056d0`
- `0x18000b160`

## callees

- `0x18000fe68`
- `0x180010384`
- `0x180016724`
- `0x180016818`
- `0x18001812c`
- `0x180018932`
- `0x18001893e`
- `0x180018970`

## import_xrefs

- `msvcrt!wcsrchr` at `0x18001692f`
- `msvcrt!wcsrchr` at `0x18001692f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c69`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180016c69`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016c61`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180016c61`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180016976`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180016976`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016b89`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180016b89`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016b80`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180016b80`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180016bbe`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180016bbe`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180016a4e`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180016a4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016ba8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016ba8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016c52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800169a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016afe`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800169a3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016afe`

## pseudocode

```c
__int64 __fastcall TextLogDecayLogFileBackups(STRSAFE_LPCWSTR pszSrc)
{
  unsigned int v2; // edi
  DWORD v3; // ebx
  __int64 FirstFileW; // r13
  _QWORD *v5; // r15
  wchar_t *v6; // rsi
  unsigned __int16 *FileTitle; // r8
  char *v8; // rcx
  wchar_t *v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  unsigned int i; // r14d
  __int64 v13; // r12
  bool v14; // cc
  char *v15; // rax
  char *v16; // r8
  int v17; // ecx
  int v18; // edx
  int v19; // r8d
  wchar_t *v20; // rax
  __int64 j; // r14
  void *v22; // r8
  unsigned int v24; // [rsp+34h] [rbp-AF4h]
  unsigned int v25; // [rsp+44h] [rbp-AE4h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-AC8h] BYREF
  wchar_t SrcStr[264]; // [rsp+2B0h] [rbp-878h] BYREF
  wchar_t pszDest[264]; // [rsp+4C0h] [rbp-668h] BYREF
  wchar_t Str[264]; // [rsp+6D0h] [rbp-458h] BYREF
  wchar_t FileName[264]; // [rsp+8E0h] [rbp-248h] BYREF

  v2 = 0;
  v3 = 0;
  FirstFileW = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = 0;
  v24 = 0;
  v6 = 0;
  if ( StringCchCopyW(pszDest, 0x104u, pszSrc) >= 0 )
  {
    FileTitle = pSetupGetFileTitle(pszDest);
    if ( FileTitle != pszDest )
    {
      v8 = (char *)(FileTitle - 1);
      if ( *(FileTitle - 1) == 92 || *(_WORD *)v8 == 47 )
      {
        if ( v8 - (char *)pszDest == 4 && pszDest[0] && pszDest[1] == 58 )
          *FileTitle = 0;
        else
          *(_WORD *)v8 = 0;
        if ( StringCchCopyW(Str, 0x104u, pszSrc) >= 0 )
        {
          v9 = wcsrchr(Str, 0x2Eu);
          if ( v9 )
          {
            *v9 = 0;
            if ( StringCchPrintfW(FileName, 0x104u, L"%s.????????_??????.%s", Str, v9 + 1) >= 0 )
            {
              FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
              if ( FirstFileW == -1 )
              {
                v3 = 0;
                goto LABEL_50;
              }
              v10 = HeapAlloc(hHeap, 0, 0x40u);
              v5 = v10;
              if ( !v10 )
              {
LABEL_17:
                v3 = 8;
                goto LABEL_50;
              }
              memset_0(v10, 0, 0x40u);
              while ( StringCchCopyW(SrcStr, 0x104u, pszDest) >= 0
                   && pSetupConcatenatePaths((__int64)SrcStr, FindFileData.cFileName, 0x104u) )
              {
                v11 = -1;
                do
                  ++v11;
                while ( SrcStr[v11] );
                v25 = v11 + 1;
                LCMapStringW(0x7Fu, 0x100u, SrcStr, v11 + 1, SrcStr, v11 + 1);
                v6 = 0;
                for ( i = 0; ; ++i )
                {
                  v13 = i;
                  v14 = i <= v24;
                  if ( i >= v24 )
                    break;
                  v15 = (char *)v5[v13];
                  v16 = (char *)((char *)SrcStr - v15);
                  do
                  {
                    v17 = *(unsigned __int16 *)&v16[(_QWORD)v15];
                    v18 = *(unsigned __int16 *)v15 - v17;
                    if ( v18 )
                      break;
                    v15 += 2;
                  }
                  while ( v17 );
                  if ( v18 < 0 )
                  {
                    if ( v24 >= 8 )
                    {
                      v6 = (wchar_t *)v5[7];
                      v19 = 7;
                    }
                    else
                    {
                      v19 = v24;
                    }
                    memmove_0(&v5[i + 1], &v5[i], 8LL * (v19 - i));
                    v5[v13] = 0;
                    v14 = i <= v24;
                    break;
                  }
                }
                if ( v14 && i < 8 )
                {
                  v20 = (wchar_t *)HeapAlloc(hHeap, 0, 2 * v25);
                  v5[v13] = v20;
                  if ( !v20 )
                    goto LABEL_17;
                  if ( StringCchCopyW(v20, v25, SrcStr) < 0 )
                    break;
                  if ( v24 < 8 )
                    ++v24;
                }
                else
                {
                  v6 = SrcStr;
                }
                if ( v6 )
                {
                  if ( v6 != SrcStr || (FindFileData.dwFileAttributes & 1) != 0 )
                    SetFileAttributesW(v6, 0x80u);
                  DeleteFileW(v6);
                  if ( v6 != SrcStr )
                  {
                    HeapFree(hHeap, 0, v6);
                    v6 = 0;
                  }
                }
                if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
                  goto LABEL_50;
              }
            }
          }
        }
        v3 = 13;
        goto LABEL_50;
      }
    }
  }
  v3 = 87;
LABEL_50:
  if ( v5 )
  {
    for ( j = 0; j != 8; ++j )
    {
      v22 = (void *)v5[j];
      if ( v22 )
        HeapFree(hHeap, 0, v22);
    }
    HeapFree(hHeap, 0, v5);
  }
  if ( v6 && v6 != SrcStr )
    HeapFree(hHeap, 0, v6);
  if ( FirstFileW != -1 )
    FindClose((HANDLE)FirstFileW);
  SetLastError(v3);
  LOBYTE(v2) = v3 == 0;
  return v2;
}

```

## disassembly

```asm
0x180016818  mov     [rsp+arg_8], rbx
0x18001681d  mov     [rsp+arg_10], rsi
0x180016822  push    rdi
0x180016823  push    r12
0x180016825  push    r13
0x180016827  push    r14
0x180016829  push    r15
0x18001682b  sub     rsp, 0B00h
0x180016832  mov     rax, cs:__security_cookie
0x180016839  xor     rax, rsp
0x18001683c  mov     [rsp+0B28h+var_38], rax
0x180016844  mov     r14, rcx
0x180016847  xor     edi, edi
0x180016849  mov     ebx, edi
0x18001684b  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001684f  mov     qword ptr [rsp+0B28h+var_AE4+4], r13
0x180016854  xor     edx, edx; Val
0x180016856  mov     r8d, 250h; Size
0x18001685c  lea     rcx, [rsp+0B28h+FindFileData]; void *
0x180016861  call    memset_0
0x180016866  mov     r15d, edi
0x180016869  mov     [rsp+0B28h+var_AD8], rdi
0x18001686e  mov     [rsp+0B28h+var_AF4], edi
0x180016872  mov     esi, edi
0x180016874  mov     [rsp+0B28h+var_AF0], rdi
0x180016879  mov     r8, r14; pszSrc
0x18001687c  mov     r12d, 104h
0x180016882  mov     edx, r12d; cchDest
0x180016885  lea     rcx, [rsp+0B28h+pszDest]; pszDest
0x18001688d  call    StringCchCopyW
0x180016892  test    eax, eax
0x180016894  js      loc_180016BD4
0x18001689a  lea     rcx, [rsp+0B28h+pszDest]
0x1800168a2  call    pSetupGetFileTitle
0x1800168a7  mov     r8, rax
0x1800168aa  lea     rax, [rsp+0B28h+pszDest]
0x1800168b2  cmp     r8, rax
0x1800168b5  jz      loc_180016BD4
0x1800168bb  lea     rcx, [r8-2]
0x1800168bf  cmp     word ptr [rcx], 5Ch ; '\'
0x1800168c3  jz      short loc_1800168CF
0x1800168c5  cmp     word ptr [rcx], 2Fh ; '/'
0x1800168c9  jnz     loc_180016BD4
0x1800168cf  lea     rdx, [rsp+0B28h+pszDest]
0x1800168d7  mov     rax, rcx
0x1800168da  sub     rax, rdx
0x1800168dd  cmp     rax, 4
0x1800168e1  jnz     short loc_1800168FE
0x1800168e3  cmp     [rsp+0B28h+pszDest], di
0x1800168eb  jz      short loc_1800168FE
0x1800168ed  cmp     [rsp+0B28h+var_666], 3Ah ; ':'
0x1800168f6  jnz     short loc_1800168FE
0x1800168f8  mov     [r8], di
0x1800168fc  jmp     short loc_180016901
0x1800168fe  mov     [rcx], di
0x180016901  mov     r8, r14; pszSrc
0x180016904  mov     rdx, r12; cchDest
0x180016907  lea     rcx, [rsp+0B28h+Str]; pszDest
0x18001690f  call    StringCchCopyW
0x180016914  test    eax, eax
0x180016916  jns     short loc_180016922
0x180016918  mov     ebx, 0Dh
0x18001691d  jmp     loc_180016BD9
0x180016922  mov     edx, 2Eh ; '.'; Ch
0x180016927  lea     rcx, [rsp+0B28h+Str]; Str
0x18001692f  call    cs:__imp_wcsrchr
0x180016935  test    rax, rax
0x180016938  jz      short loc_180016918
0x18001693a  mov     [rax], di
0x18001693d  add     rax, 2
0x180016941  mov     [rsp+0B28h+lpDestStr], rax
0x180016946  lea     r9, [rsp+0B28h+Str]
0x18001694e  lea     r8, aSS; "%s.????????_??????.%s"
0x180016955  mov     rdx, r12; cchDest
0x180016958  lea     rcx, [rsp+0B28h+FileName]; pszDest
0x180016960  call    StringCchPrintfW
0x180016965  test    eax, eax
0x180016967  js      short loc_180016918
0x180016969  lea     rdx, [rsp+0B28h+FindFileData]; lpFindFileData
0x18001696e  lea     rcx, [rsp+0B28h+FileName]; lpFileName
0x180016976  call    cs:__imp_FindFirstFileW
0x18001697c  mov     r13, rax
0x18001697f  mov     qword ptr [rsp+0B28h+var_AE4+4], rax
0x180016984  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016988  jnz     short loc_180016991
0x18001698a  mov     ebx, edi
0x18001698c  jmp     loc_180016BD9
0x180016991  mov     r14d, 40h ; '@'
0x180016997  mov     r8d, r14d; dwBytes
0x18001699a  xor     edx, edx; dwFlags
0x18001699c  mov     rcx, cs:hHeap; hHeap
0x1800169a3  call    cs:__imp_HeapAlloc
0x1800169a9  mov     r15, rax
0x1800169ac  mov     [rsp+0B28h+var_AD8], rax
0x1800169b1  test    rax, rax
0x1800169b4  jnz     short loc_1800169C0
0x1800169b6  mov     ebx, 8
0x1800169bb  jmp     loc_180016BD9
0x1800169c0  mov     r8, r14; Size
0x1800169c3  xor     edx, edx; Val
0x1800169c5  mov     rcx, r15; void *
0x1800169c8  call    memset_0
0x1800169cd  lea     r8, [rsp+0B28h+pszDest]; pszSrc
0x1800169d5  mov     rdx, r12; cchDest
0x1800169d8  lea     rcx, [rsp+0B28h+SrcStr]; pszDest
0x1800169e0  call    StringCchCopyW
0x1800169e5  test    eax, eax
0x1800169e7  js      loc_180016918
0x1800169ed  mov     r8d, r12d
0x1800169f0  lea     rdx, [rsp+0B28h+FindFileData.cFileName]
0x1800169f8  lea     rcx, [rsp+0B28h+SrcStr]
0x180016a00  call    pSetupConcatenatePaths
0x180016a05  test    eax, eax
0x180016a07  jz      loc_180016918
0x180016a0d  lea     rcx, [rsp+0B28h+SrcStr]
0x180016a15  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016a19  inc     rax
0x180016a1c  cmp     [rcx+rax*2], di
0x180016a20  jnz     short loc_180016A19
0x180016a22  inc     eax
0x180016a24  mov     [rsp+0B28h+var_AE4], eax
0x180016a28  mov     [rsp+0B28h+cchDest], eax; cchDest
0x180016a2c  lea     rcx, [rsp+0B28h+SrcStr]
0x180016a34  mov     [rsp+0B28h+lpDestStr], rcx; lpDestStr
0x180016a39  mov     r9d, eax; cchSrc
0x180016a3c  lea     r8, [rsp+0B28h+SrcStr]; lpSrcStr
0x180016a44  mov     edx, 100h; dwMapFlags
0x180016a49  mov     ecx, 7Fh; Locale
0x180016a4e  call    cs:__imp_LCMapStringW
0x180016a54  mov     rsi, rdi
0x180016a57  mov     [rsp+0B28h+var_AF0], rdi
0x180016a5c  mov     r14d, edi
0x180016a5f  mov     [rsp+0B28h+var_AE8], edi
0x180016a63  mov     r9d, [rsp+0B28h+var_AF4]
0x180016a68  mov     eax, r14d
0x180016a6b  lea     r12, ds:0[rax*8]
0x180016a73  cmp     r14d, r9d
0x180016a76  jnb     short loc_180016AE4
0x180016a78  mov     rax, [r12+r15]
0x180016a7c  lea     r8, [rsp+0B28h+SrcStr]
0x180016a84  sub     r8, rax
0x180016a87  movzx   edx, word ptr [rax]
0x180016a8a  movzx   ecx, word ptr [rax+r8]
0x180016a8f  sub     edx, ecx
0x180016a91  jnz     short loc_180016A9B
0x180016a93  add     rax, 2
0x180016a97  test    ecx, ecx
0x180016a99  jnz     short loc_180016A87
0x180016a9b  lea     ecx, [r14+1]
0x180016a9f  test    edx, edx
0x180016aa1  jns     loc_180016B46
0x180016aa7  mov     eax, r14d
0x180016aaa  lea     rdx, [r15+rax*8]; Src
0x180016aae  lea     rcx, [r15+rcx*8]; void *
0x180016ab2  cmp     r9d, 8
0x180016ab6  jnb     short loc_180016ABD
0x180016ab8  mov     r8d, r9d
0x180016abb  jmp     short loc_180016ACC
0x180016abd  mov     rsi, [r15+38h]
0x180016ac1  mov     [rsp+0B28h+var_AF0], rsi
0x180016ac6  mov     r8d, 7
0x180016acc  sub     r8d, r14d
0x180016acf  shl     r8, 3; Size
0x180016ad3  call    memmove_0
0x180016ad8  mov     [r12+r15], rdi
0x180016adc  mov     r9d, [rsp+0B28h+var_AF4]
0x180016ae1  cmp     r14d, r9d
0x180016ae4  ja      short loc_180016B52
0x180016ae6  cmp     r14d, 8
0x180016aea  jnb     short loc_180016B52
0x180016aec  mov     r14d, [rsp+0B28h+var_AE4]
0x180016af1  lea     r8d, [r14+r14]; dwBytes
0x180016af5  xor     edx, edx; dwFlags
0x180016af7  mov     rcx, cs:hHeap; hHeap
0x180016afe  call    cs:__imp_HeapAlloc
0x180016b04  mov     [r12+r15], rax
0x180016b08  test    rax, rax
0x180016b0b  jz      loc_1800169B6
0x180016b11  mov     edx, r14d; cchDest
0x180016b14  lea     r8, [rsp+0B28h+SrcStr]; pszSrc
0x180016b1c  mov     rcx, rax; pszDest
0x180016b1f  call    StringCchCopyW
0x180016b24  test    eax, eax
0x180016b26  js      loc_180016918
0x180016b2c  mov     r9d, [rsp+0B28h+var_AF4]
0x180016b31  cmp     r9d, 8
0x180016b35  jnb     short loc_180016B5F
0x180016b37  inc     r9d
0x180016b3a  mov     [rsp+0B28h+var_AF4], r9d
0x180016b3f  mov     [rsp+0B28h+var_AD0], r9d
0x180016b44  jmp     short loc_180016B5F
0x180016b46  mov     r14d, ecx
0x180016b49  mov     [rsp+0B28h+var_AE8], ecx
0x180016b4d  jmp     loc_180016A68
0x180016b52  lea     rsi, [rsp+0B28h+SrcStr]
0x180016b5a  mov     [rsp+0B28h+var_AF0], rsi
0x180016b5f  test    rsi, rsi
0x180016b62  jz      short loc_180016BB6
0x180016b64  lea     rax, [rsp+0B28h+SrcStr]
0x180016b6c  cmp     rsi, rax
0x180016b6f  jnz     short loc_180016B78
0x180016b71  test    byte ptr [rsp+0B28h+FindFileData.dwFileAttributes], 1
0x180016b76  jz      short loc_180016B86
0x180016b78  mov     edx, 80h; dwFileAttributes
0x180016b7d  mov     rcx, rsi; lpFileName
0x180016b80  call    cs:__imp_SetFileAttributesW
0x180016b86  mov     rcx, rsi; lpFileName
0x180016b89  call    cs:__imp_DeleteFileW
0x180016b8f  lea     rax, [rsp+0B28h+SrcStr]
0x180016b97  cmp     rsi, rax
0x180016b9a  jz      short loc_180016BB6
0x180016b9c  mov     r8, rsi; lpMem
0x180016b9f  xor     edx, edx; dwFlags
0x180016ba1  mov     rcx, cs:hHeap; hHeap
0x180016ba8  call    cs:__imp_HeapFree
0x180016bae  mov     rsi, rdi
0x180016bb1  mov     [rsp+0B28h+var_AF0], rdi
0x180016bb6  lea     rdx, [rsp+0B28h+FindFileData]; lpFindFileData
0x180016bbb  mov     rcx, r13; hFindFile
0x180016bbe  call    cs:__imp_FindNextFileW
0x180016bc4  test    eax, eax
0x180016bc6  mov     r12d, 104h
0x180016bcc  jnz     loc_1800169CD
0x180016bd2  jmp     short loc_180016BDD
0x180016bd4  mov     ebx, 57h ; 'W'
0x180016bd9  mov     [rsp+0B28h+var_AF8], ebx
0x180016bdd  jmp     short loc_180016BF9
0x180016bdf  mov     ebx, 54Fh
0x180016be4  mov     [rsp+0B28h+var_AF8], ebx
0x180016be8  xor     edi, edi
0x180016bea  mov     r13, qword ptr [rsp+0B28h+var_AE4+4]
0x180016bef  mov     r15, [rsp+0B28h+var_AD8]
0x180016bf4  mov     rsi, [rsp+0B28h+var_AF0]
0x180016bf9  test    r15, r15
0x180016bfc  jz      short loc_180016C34
0x180016bfe  mov     r14, rdi
0x180016c01  mov     r8, [r15+r14*8]; lpMem
0x180016c05  test    r8, r8
0x180016c08  jz      short loc_180016C19
0x180016c0a  xor     edx, edx; dwFlags
0x180016c0c  mov     rcx, cs:hHeap; hHeap
0x180016c13  call    cs:__imp_HeapFree
0x180016c19  inc     r14
0x180016c1c  cmp     r14, 8
0x180016c20  jnz     short loc_180016C01
0x180016c22  mov     r8, r15; lpMem
0x180016c25  xor     edx, edx; dwFlags
0x180016c27  mov     rcx, cs:hHeap; hHeap
0x180016c2e  call    cs:__imp_HeapFree
0x180016c34  test    rsi, rsi
0x180016c37  jz      short loc_180016C58
0x180016c39  lea     rax, [rsp+0B28h+SrcStr]
0x180016c41  cmp     rsi, rax
0x180016c44  jz      short loc_180016C58
0x180016c46  mov     r8, rsi; lpMem
0x180016c49  xor     edx, edx; dwFlags
0x180016c4b  mov     rcx, cs:hHeap; hHeap
0x180016c52  call    cs:__imp_HeapFree
0x180016c58  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180016c5c  jz      short loc_180016C67
0x180016c5e  mov     rcx, r13; hFindFile
0x180016c61  call    cs:__imp_FindClose
0x180016c67  mov     ecx, ebx; dwErrCode
0x180016c69  call    cs:__imp_SetLastError
0x180016c6f  test    ebx, ebx
0x180016c71  setz    dil
0x180016c75  mov     eax, edi
0x180016c77  mov     rcx, [rsp+0B28h+var_38]
0x180016c7f  xor     rcx, rsp; StackCookie
0x180016c82  call    __security_check_cookie
0x180016c87  lea     r11, [rsp+0B28h+var_28]
0x180016c8f  mov     rbx, [r11+38h]
0x180016c93  mov     rsi, [r11+40h]
0x180016c97  mov     rsp, r11
0x180016c9a  pop     r15
0x180016c9c  pop     r14
0x180016c9e  pop     r13
0x180016ca0  pop     r12
0x180016ca2  pop     rdi
0x180016ca3  retn
```
