# WdsCopyDirectoryEngineRecursive

- ea: `0x18001a1c8`
- end: `0x18001a5d5`
- name: `WdsCopyDirectoryEngineRecursive`
- size: `1037`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a0f8`
- `0x18001a1c8`

## callees

- `0x180019aec`
- `0x18001a1c8`
- `0x18001a880`
- `0x18001acf0`
- `0x18001b0cc`
- `0x18001c060`
- `0x18001c610`
- `0x180030362`
- `0x180030390`
- `0x180031010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001a471`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a48e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a57b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a58f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a5a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a471`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a48e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a57b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a58f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001a5a3`
- `KERNEL32!FindClose` at `0x18001a560`
- `KERNEL32!FindClose` at `0x18001a560`
- `KERNEL32!FindNextFileW` at `0x18001a4ad`
- `KERNEL32!FindNextFileW` at `0x18001a4ad`
- `KERNEL32!SetFileAttributesW` at `0x18001a3d6`
- `KERNEL32!SetFileAttributesW` at `0x18001a3d6`
- `KERNEL32!CopyFileW` at `0x18001a3bb`
- `KERNEL32!CopyFileW` at `0x18001a3bb`
- `KERNEL32!FindFirstFileW` at `0x18001a2d5`
- `KERNEL32!FindFirstFileW` at `0x18001a2d5`
- `KERNEL32!GetLastError` at `0x18001a2ec`
- `KERNEL32!GetLastError` at `0x18001a4c1`
- `KERNEL32!GetLastError` at `0x18001a4e5`
- `KERNEL32!GetLastError` at `0x18001a4f9`
- `KERNEL32!GetLastError` at `0x18001a2ec`
- `KERNEL32!GetLastError` at `0x18001a4c1`
- `KERNEL32!GetLastError` at `0x18001a4e5`
- `KERNEL32!GetLastError` at `0x18001a4f9`

## pseudocode

```c
__int64 __fastcall WdsCopyDirectoryEngineRecursive(
        const WCHAR *a1,
        __int64 a2,
        __int64 (__fastcall *a3)(LPCWSTR, __int64),
        __int64 a4)
{
  WCHAR *v7; // rdi
  WCHAR *v8; // rsi
  WCHAR *v9; // r14
  signed int Path; // ebx
  int v11; // r14d
  __int64 v12; // rdx
  __int64 v13; // r8
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  int v17; // eax
  int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  signed int v27; // eax
  DWORD v28; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // eax
  int v33; // ebx
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR lpExistingFileName; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v38; // [rsp+48h] [rbp-B8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  v38 = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  lpNewFileName = 0;
  v7 = 0;
  lpExistingFileName = 0;
  v8 = 0;
  lpFileName = 0;
  v9 = 0;
  if ( !a2 || !a1 )
  {
    Path = -2147024809;
    goto LABEL_60;
  }
  if ( !(unsigned int)WdsDirectoryExists(a1) )
    return (unsigned int)-2147024809;
  Path = WdsCreatePath(a2, 0, 1);
  if ( Path >= 0 )
  {
    Path = CopyStreams(a1);
    if ( Path >= 0 )
    {
      v11 = ConcatenatePaths(a1, L"*", &lpFileName);
      if ( (unsigned int)ElValidateWin32_8((unsigned int)v11, v12, v13, 1610) )
      {
        if ( v11 > 0 )
          Path = (unsigned __int16)v11 | 0x80070000;
        else
          Path = v11;
        v9 = (WCHAR *)lpFileName;
        goto LABEL_60;
      }
      v9 = (WCHAR *)lpFileName;
      lpFileName = (LPCWSTR)FindFirstFileW(lpFileName, &FindFileData);
      if ( lpFileName == (LPCWSTR)-1LL )
      {
        LastError = GetLastError();
        v17 = ElValidateWin32_8(LastError, v15, v16, 1619);
        Path = v17;
        if ( v17 > 0 )
          Path = (unsigned __int16)v17 | 0x80070000;
        if ( Path >= 0 )
          Path = -2147467259;
        goto LABEL_60;
      }
      while ( 1 )
      {
        v18 = ConcatenatePaths(a2, FindFileData.cFileName, &lpNewFileName);
        if ( (unsigned int)ElValidateWin32_8((unsigned int)v18, v19, v20, 1631) )
        {
          if ( v18 > 0 )
          {
            v33 = (unsigned __int16)v18;
            v7 = (WCHAR *)lpNewFileName;
            goto LABEL_57;
          }
          goto LABEL_55;
        }
        v18 = ConcatenatePaths(a1, FindFileData.cFileName, &lpExistingFileName);
        v23 = ElValidateWin32_8((unsigned int)v18, v21, v22, 1640);
        v8 = (WCHAR *)lpExistingFileName;
        if ( v23 )
        {
          if ( v18 > 0 )
          {
            Path = (unsigned __int16)v18 | 0x80070000;
LABEL_53:
            v7 = (WCHAR *)lpNewFileName;
            goto LABEL_58;
          }
LABEL_55:
          Path = v18;
          goto LABEL_53;
        }
        v7 = (WCHAR *)lpNewFileName;
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( FindFileData.cFileName[0] == 46
            && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
          {
            goto LABEL_35;
          }
          if ( !a3 )
            goto LABEL_33;
          v26 = a3(lpExistingFileName, v38);
          if ( v26 != 1 )
          {
            if ( v26 == 2 )
            {
LABEL_43:
              Path = 1223;
              goto LABEL_58;
            }
LABEL_33:
            v25 = WdsCopyDirectoryEngineRecursive(v8, v7, a3, v38, 0);
            goto LABEL_34;
          }
        }
        else
        {
          if ( !a3 )
            goto LABEL_23;
          v24 = a3(lpExistingFileName, v38);
          if ( v24 != 1 )
          {
            if ( v24 == 2 )
              goto LABEL_43;
LABEL_23:
            if ( !CopyFileW(v8, v7, 0) )
            {
              v28 = GetLastError();
              v31 = 1680;
              goto LABEL_46;
            }
            if ( !SetFileAttributesW(v7, FindFileData.dwFileAttributes) )
            {
              v28 = GetLastError();
              v31 = 1691;
LABEL_46:
              v32 = ElValidateWin32_8(v28, v29, v30, v31);
              Path = v32;
              if ( v32 > 0 )
                Path = (unsigned __int16)v32 | 0x80070000;
              if ( Path >= 0 )
                Path = -2147467259;
              goto LABEL_58;
            }
            v25 = CopySecurityInformation(v8, v7, 1);
LABEL_34:
            Path = v25;
            if ( v25 < 0 )
              goto LABEL_58;
LABEL_35:
            if ( v8 )
            {
              operator delete(v8);
              v8 = 0;
              lpExistingFileName = 0;
            }
            if ( v7 )
            {
              operator delete(v7);
              v7 = 0;
              lpNewFileName = 0;
            }
          }
        }
        if ( !FindNextFileW((HANDLE)lpFileName, &FindFileData) )
        {
          v27 = GetLastError();
          if ( v27 == 18 )
            goto LABEL_58;
          if ( v27 <= 0 )
          {
            Path = v27;
            goto LABEL_58;
          }
          v33 = (unsigned __int16)v27;
LABEL_57:
          Path = v33 | 0x80070000;
LABEL_58:
          FindClose((HANDLE)lpFileName);
LABEL_60:
          if ( v9 )
            operator delete(v9);
          if ( v8 )
            operator delete(v8);
          if ( v7 )
            operator delete(v7);
          return (unsigned int)Path;
        }
      }
    }
  }
  return (unsigned int)Path;
}

```

## disassembly

```asm
0x18001a1c8  push    rbp
0x18001a1ca  push    rbx
0x18001a1cb  push    rsi
0x18001a1cc  push    rdi
0x18001a1cd  push    r12
0x18001a1cf  push    r13
0x18001a1d1  push    r14
0x18001a1d3  push    r15
0x18001a1d5  lea     rbp, [rsp-1B8h]
0x18001a1dd  sub     rsp, 2B8h
0x18001a1e4  mov     rax, cs:__security_cookie
0x18001a1eb  xor     rax, rsp
0x18001a1ee  mov     [rbp+1F0h+var_50], rax
0x18001a1f5  mov     r12, r8
0x18001a1f8  mov     [rsp+2F0h+var_2A8], r9
0x18001a1fd  mov     r13, rdx
0x18001a200  mov     r15, rcx
0x18001a203  xor     edx, edx; Val
0x18001a205  lea     rcx, [rsp+2F0h+FindFileData]; void *
0x18001a20a  mov     r8d, 250h; Size
0x18001a210  call    memset_0
0x18001a215  xor     ebx, ebx
0x18001a217  mov     [rsp+2F0h+lpNewFileName], rbx
0x18001a21c  mov     edi, ebx
0x18001a21e  mov     [rsp+2F0h+lpExistingFileName], rbx
0x18001a223  mov     esi, ebx
0x18001a225  mov     [rsp+2F0h+lpFileName], rbx
0x18001a22a  mov     r14d, ebx
0x18001a22d  test    r13, r13
0x18001a230  jz      loc_18001A56E
0x18001a236  test    r15, r15
0x18001a239  jz      loc_18001A56E
0x18001a23f  mov     rcx, r15
0x18001a242  call    WdsDirectoryExists
0x18001a247  test    eax, eax
0x18001a249  jnz     short loc_18001A255
0x18001a24b  mov     ebx, 80070057h
0x18001a250  jmp     loc_18001A5AF
0x18001a255  xor     edx, edx
0x18001a257  mov     rcx, r13
0x18001a25a  lea     r8d, [rdx+1]
0x18001a25e  call    WdsCreatePath
0x18001a263  mov     ebx, eax
0x18001a265  test    eax, eax
0x18001a267  js      loc_18001A5AF
0x18001a26d  mov     rdx, r13
0x18001a270  mov     rcx, r15; lpFileName
0x18001a273  call    CopyStreams
0x18001a278  mov     ebx, eax
0x18001a27a  test    eax, eax
0x18001a27c  js      loc_18001A5AF
0x18001a282  lea     r8, [rsp+2F0h+lpFileName]
0x18001a287  mov     rcx, r15
0x18001a28a  lea     rdx, asc_180036A84; "*"
0x18001a291  call    ConcatenatePaths
0x18001a296  mov     r9d, 64Ah
0x18001a29c  mov     ecx, eax
0x18001a29e  mov     r14d, eax
0x18001a2a1  call    ElValidateWin32_8
0x18001a2a6  test    eax, eax
0x18001a2a8  jz      short loc_18001A2C8
0x18001a2aa  test    r14d, r14d
0x18001a2ad  jg      short loc_18001A2BC
0x18001a2af  mov     ebx, r14d
0x18001a2b2  mov     r14, [rsp+2F0h+lpFileName]
0x18001a2b7  jmp     loc_18001A573
0x18001a2bc  movzx   ebx, r14w
0x18001a2c0  or      ebx, 80070000h
0x18001a2c6  jmp     short loc_18001A2B2
0x18001a2c8  mov     r14, [rsp+2F0h+lpFileName]
0x18001a2cd  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18001a2d2  mov     rcx, r14; lpFileName
0x18001a2d5  call    cs:__imp_FindFirstFileW
0x18001a2dc  nop     dword ptr [rax+rax+00h]
0x18001a2e1  mov     [rsp+2F0h+lpFileName], rax
0x18001a2e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a2ea  jnz     short loc_18001A326
0x18001a2ec  call    cs:__imp_GetLastError
0x18001a2f3  nop     dword ptr [rax+rax+00h]
0x18001a2f8  mov     ecx, eax
0x18001a2fa  mov     r9d, 653h
0x18001a300  call    ElValidateWin32_8
0x18001a305  mov     ebx, eax
0x18001a307  test    eax, eax
0x18001a309  jle     short loc_18001A314
0x18001a30b  movzx   ebx, ax
0x18001a30e  or      ebx, 80070000h
0x18001a314  test    ebx, ebx
0x18001a316  js      loc_18001A573
0x18001a31c  mov     ebx, 80004005h
0x18001a321  jmp     loc_18001A573
0x18001a326  lea     r8, [rsp+2F0h+lpNewFileName]
0x18001a32b  mov     rcx, r13
0x18001a32e  lea     rdx, [rsp+2F0h+FindFileData.cFileName]
0x18001a333  call    ConcatenatePaths
0x18001a338  mov     r9d, 65Fh
0x18001a33e  mov     ecx, eax
0x18001a340  mov     edi, eax
0x18001a342  call    ElValidateWin32_8
0x18001a347  test    eax, eax
0x18001a349  jnz     loc_18001A545
0x18001a34f  lea     r8, [rsp+2F0h+lpExistingFileName]
0x18001a354  mov     rcx, r15
0x18001a357  lea     rdx, [rsp+2F0h+FindFileData.cFileName]
0x18001a35c  call    ConcatenatePaths
0x18001a361  mov     r9d, 668h
0x18001a367  mov     ecx, eax
0x18001a369  mov     edi, eax
0x18001a36b  call    ElValidateWin32_8
0x18001a370  mov     rsi, [rsp+2F0h+lpExistingFileName]
0x18001a375  xor     ecx, ecx
0x18001a377  test    eax, eax
0x18001a379  jnz     loc_18001A531
0x18001a37f  test    byte ptr [rsp+2F0h+FindFileData.dwFileAttributes], 10h
0x18001a384  mov     rdi, [rsp+2F0h+lpNewFileName]
0x18001a389  jnz     short loc_18001A3FD
0x18001a38b  test    r12, r12
0x18001a38e  jz      short loc_18001A3B2
0x18001a390  mov     rdx, [rsp+2F0h+var_2A8]
0x18001a395  mov     rcx, rsi
0x18001a398  mov     rax, r12
0x18001a39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3a0  cmp     eax, 1
0x18001a3a3  jz      loc_18001A4A3
0x18001a3a9  cmp     eax, 2
0x18001a3ac  jz      loc_18001A4DE
0x18001a3b2  xor     r8d, r8d; bFailIfExists
0x18001a3b5  mov     rdx, rdi; lpNewFileName
0x18001a3b8  mov     rcx, rsi; lpExistingFileName
0x18001a3bb  call    cs:__imp_CopyFileW
0x18001a3c2  nop     dword ptr [rax+rax+00h]
0x18001a3c7  test    eax, eax
0x18001a3c9  jz      loc_18001A4F9
0x18001a3cf  mov     edx, [rsp+2F0h+FindFileData.dwFileAttributes]; dwFileAttributes
0x18001a3d3  mov     rcx, rdi; lpFileName
0x18001a3d6  call    cs:__imp_SetFileAttributesW
0x18001a3dd  nop     dword ptr [rax+rax+00h]
0x18001a3e2  test    eax, eax
0x18001a3e4  jz      loc_18001A4E5
0x18001a3ea  mov     r8d, 1
0x18001a3f0  mov     rdx, rdi; LPWSTR
0x18001a3f3  mov     rcx, rsi; pObjectName
0x18001a3f6  call    CopySecurityInformation
0x18001a3fb  jmp     short loc_18001A45F
0x18001a3fd  cmp     [rsp+2F0h+FindFileData.cFileName], 2Eh ; '.'
0x18001a403  movzx   eax, [rsp+2F0h+FindFileData.cFileName+2]
0x18001a408  jnz     short loc_18001A423
0x18001a40a  test    ax, ax
0x18001a40d  jz      short loc_18001A469
0x18001a40f  cmp     [rsp+2F0h+FindFileData.cFileName], 2Eh ; '.'
0x18001a415  jnz     short loc_18001A423
0x18001a417  cmp     ax, 2Eh ; '.'
0x18001a41b  jnz     short loc_18001A423
0x18001a41d  cmp     [rbp+1F0h+FindFileData.cFileName+4], cx
0x18001a421  jz      short loc_18001A469
0x18001a423  test    r12, r12
0x18001a426  jz      short loc_18001A448
0x18001a428  mov     rdx, [rsp+2F0h+var_2A8]
0x18001a42d  mov     rcx, rsi
0x18001a430  mov     rax, r12
0x18001a433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a438  cmp     eax, 1
0x18001a43b  jz      short loc_18001A4A3
0x18001a43d  cmp     eax, 2
0x18001a440  jz      loc_18001A4DE
0x18001a446  xor     ecx, ecx
0x18001a448  mov     r9, [rsp+2F0h+var_2A8]
0x18001a44d  mov     r8, r12
0x18001a450  mov     [rsp+2F0h+var_2D0], ecx
0x18001a454  mov     rdx, rdi
0x18001a457  mov     rcx, rsi
0x18001a45a  call    WdsCopyDirectoryEngineRecursive
0x18001a45f  mov     ebx, eax
0x18001a461  test    eax, eax
0x18001a463  js      loc_18001A55B
0x18001a469  test    rsi, rsi
0x18001a46c  jz      short loc_18001A486
0x18001a46e  mov     rcx, rsi
0x18001a471  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a478  nop     dword ptr [rax+rax+00h]
0x18001a47d  xor     ecx, ecx
0x18001a47f  mov     esi, ecx
0x18001a481  mov     [rsp+2F0h+lpExistingFileName], rcx
0x18001a486  test    rdi, rdi
0x18001a489  jz      short loc_18001A4A3
0x18001a48b  mov     rcx, rdi
0x18001a48e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a495  nop     dword ptr [rax+rax+00h]
0x18001a49a  xor     eax, eax
0x18001a49c  mov     edi, eax
0x18001a49e  mov     [rsp+2F0h+lpNewFileName], rax
0x18001a4a3  mov     rcx, [rsp+2F0h+lpFileName]; hFindFile
0x18001a4a8  lea     rdx, [rsp+2F0h+FindFileData]; lpFindFileData
0x18001a4ad  call    cs:__imp_FindNextFileW
0x18001a4b4  nop     dword ptr [rax+rax+00h]
0x18001a4b9  test    eax, eax
0x18001a4bb  jnz     loc_18001A326
0x18001a4c1  call    cs:__imp_GetLastError
0x18001a4c8  nop     dword ptr [rax+rax+00h]
0x18001a4cd  cmp     eax, 12h
0x18001a4d0  jz      loc_18001A55B
0x18001a4d6  test    eax, eax
0x18001a4d8  jg      short loc_18001A52C
0x18001a4da  mov     ebx, eax
0x18001a4dc  jmp     short loc_18001A55B
0x18001a4de  mov     ebx, 4C7h
0x18001a4e3  jmp     short loc_18001A55B
0x18001a4e5  call    cs:__imp_GetLastError
0x18001a4ec  nop     dword ptr [rax+rax+00h]
0x18001a4f1  mov     r9d, 69Bh
0x18001a4f7  jmp     short loc_18001A50B
0x18001a4f9  call    cs:__imp_GetLastError
0x18001a500  nop     dword ptr [rax+rax+00h]
0x18001a505  mov     r9d, 690h
0x18001a50b  mov     ecx, eax
0x18001a50d  call    ElValidateWin32_8
0x18001a512  mov     ebx, eax
0x18001a514  test    eax, eax
0x18001a516  jle     short loc_18001A521
0x18001a518  movzx   ebx, ax
0x18001a51b  or      ebx, 80070000h
0x18001a521  test    ebx, ebx
0x18001a523  js      short loc_18001A55B
0x18001a525  mov     ebx, 80004005h
0x18001a52a  jmp     short loc_18001A55B
0x18001a52c  movzx   ebx, ax
0x18001a52f  jmp     short loc_18001A555
0x18001a531  test    edi, edi
0x18001a533  jle     short loc_18001A549
0x18001a535  movzx   ebx, di
0x18001a538  or      ebx, 80070000h
0x18001a53e  mov     rdi, [rsp+2F0h+lpNewFileName]
0x18001a543  jmp     short loc_18001A55B
0x18001a545  test    edi, edi
0x18001a547  jg      short loc_18001A54D
0x18001a549  mov     ebx, edi
0x18001a54b  jmp     short loc_18001A53E
0x18001a54d  movzx   ebx, di
0x18001a550  mov     rdi, [rsp+2F0h+lpNewFileName]
0x18001a555  or      ebx, 80070000h
0x18001a55b  mov     rcx, [rsp+2F0h+lpFileName]; hFindFile
0x18001a560  call    cs:__imp_FindClose
0x18001a567  nop     dword ptr [rax+rax+00h]
0x18001a56c  jmp     short loc_18001A573
0x18001a56e  mov     ebx, 80070057h
0x18001a573  test    r14, r14
0x18001a576  jz      short loc_18001A587
0x18001a578  mov     rcx, r14
0x18001a57b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a582  nop     dword ptr [rax+rax+00h]
0x18001a587  test    rsi, rsi
0x18001a58a  jz      short loc_18001A59B
0x18001a58c  mov     rcx, rsi
0x18001a58f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a596  nop     dword ptr [rax+rax+00h]
0x18001a59b  test    rdi, rdi
0x18001a59e  jz      short loc_18001A5AF
0x18001a5a0  mov     rcx, rdi
0x18001a5a3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001a5aa  nop     dword ptr [rax+rax+00h]
0x18001a5af  mov     eax, ebx
0x18001a5b1  mov     rcx, [rbp+1F0h+var_50]
0x18001a5b8  xor     rcx, rsp; StackCookie
0x18001a5bb  call    __security_check_cookie
0x18001a5c0  add     rsp, 2B8h
0x18001a5c7  pop     r15
0x18001a5c9  pop     r14
0x18001a5cb  pop     r13
0x18001a5cd  pop     r12
0x18001a5cf  pop     rdi
0x18001a5d0  pop     rsi
0x18001a5d1  pop     rbx
0x18001a5d2  pop     rbp
0x18001a5d3  retn
```
