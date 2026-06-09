# BLBIMGI_BACKUP_FILE::QueryBatBlockListFromExistingBackupFile(ushort const *,__int64,uchar *,ulong * *,__int64 *,ulong *)

- ea: `0x1400ca348`
- end: `0x1400ca8e2`
- name: `?QueryBatBlockListFromExistingBackupFile@BLBIMGI_BACKUP_FILE@@AEAA?AW4_BLBIMG_RESULT_CODE@@PEBG_JPEAEPEAPEAKPEA_JPEAK@Z`
- size: `1434`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1400c7594`

## callees

- `0x14000bb24`
- `0x140014200`
- `0x140014260`
- `0x14003c434`
- `0x14003d228`
- `0x1400c3d08`
- `0x1400c8c74`
- `0x1400c8d84`
- `0x1400c9500`
- `0x1400ca348`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400ca471`
- `KERNEL32!LocalAlloc` at `0x1400ca593`
- `KERNEL32!LocalAlloc` at `0x1400ca64f`
- `KERNEL32!LocalAlloc` at `0x1400ca471`
- `KERNEL32!LocalAlloc` at `0x1400ca593`
- `KERNEL32!LocalAlloc` at `0x1400ca64f`
- `KERNEL32!ReadFile` at `0x1400ca4a5`
- `KERNEL32!ReadFile` at `0x1400ca5d0`
- `KERNEL32!ReadFile` at `0x1400ca68d`
- `KERNEL32!ReadFile` at `0x1400ca4a5`
- `KERNEL32!ReadFile` at `0x1400ca5d0`
- `KERNEL32!ReadFile` at `0x1400ca68d`
- `KERNEL32!LocalFree` at `0x1400ca5b0`
- `KERNEL32!LocalFree` at `0x1400ca66c`
- `KERNEL32!LocalFree` at `0x1400ca741`
- `KERNEL32!LocalFree` at `0x1400ca74a`
- `KERNEL32!LocalFree` at `0x1400ca7e8`
- `KERNEL32!LocalFree` at `0x1400ca7f1`
- `KERNEL32!LocalFree` at `0x1400ca7fa`
- `KERNEL32!LocalFree` at `0x1400ca84f`
- `KERNEL32!LocalFree` at `0x1400ca858`
- `KERNEL32!LocalFree` at `0x1400ca8b9`
- `KERNEL32!LocalFree` at `0x1400ca5b0`
- `KERNEL32!LocalFree` at `0x1400ca66c`
- `KERNEL32!LocalFree` at `0x1400ca741`
- `KERNEL32!LocalFree` at `0x1400ca74a`
- `KERNEL32!LocalFree` at `0x1400ca7e8`
- `KERNEL32!LocalFree` at `0x1400ca7f1`
- `KERNEL32!LocalFree` at `0x1400ca7fa`
- `KERNEL32!LocalFree` at `0x1400ca84f`
- `KERNEL32!LocalFree` at `0x1400ca858`
- `KERNEL32!LocalFree` at `0x1400ca8b9`
- `KERNEL32!GetFileSizeEx` at `0x1400ca3fd`
- `KERNEL32!GetFileSizeEx` at `0x1400ca3fd`
- `KERNEL32!CreateFileW` at `0x1400ca3e3`
- `KERNEL32!CreateFileW` at `0x1400ca3e3`
- `KERNEL32!CloseHandle` at `0x1400ca753`
- `KERNEL32!CloseHandle` at `0x1400ca864`
- `KERNEL32!CloseHandle` at `0x1400ca8c2`
- `KERNEL32!CloseHandle` at `0x1400ca753`
- `KERNEL32!CloseHandle` at `0x1400ca864`
- `KERNEL32!CloseHandle` at `0x1400ca8c2`
- `KERNEL32!GetLastError` at `0x1400ca431`
- `KERNEL32!GetLastError` at `0x1400ca47f`
- `KERNEL32!GetLastError` at `0x1400ca5a1`
- `KERNEL32!GetLastError` at `0x1400ca65d`
- `KERNEL32!GetLastError` at `0x1400ca7b5`
- `KERNEL32!GetLastError` at `0x1400ca822`
- `KERNEL32!GetLastError` at `0x1400ca88c`
- `KERNEL32!GetLastError` at `0x1400ca431`
- `KERNEL32!GetLastError` at `0x1400ca47f`
- `KERNEL32!GetLastError` at `0x1400ca5a1`
- `KERNEL32!GetLastError` at `0x1400ca65d`
- `KERNEL32!GetLastError` at `0x1400ca7b5`
- `KERNEL32!GetLastError` at `0x1400ca822`
- `KERNEL32!GetLastError` at `0x1400ca88c`

## pseudocode

```c
__int64 __fastcall BLBIMGI_BACKUP_FILE::QueryBatBlockListFromExistingBackupFile(
        BLBIMGI_BACKUP_FILE *a1,
        const WCHAR *a2,
        __int64 a3,
        _BYTE *a4,
        unsigned int **a5,
        union _LARGE_INTEGER *a6,
        DWORD *a7)
{
  unsigned int v11; // ebx
  HANDLE FileW; // rax
  void *v13; // r12
  char LastError; // al
  HLOCAL v15; // rax
  void *v16; // rdi
  HLOCAL v17; // rax
  void *v18; // rsi
  SIZE_T v19; // r14
  unsigned int *v20; // rax
  unsigned int *v21; // r15
  DWORD NumberOfBytesRead; // [rsp+40h] [rbp-20h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-18h] BYREF
  __int64 v25; // [rsp+50h] [rbp-10h] BYREF

  FileSize.QuadPart = 0;
  NumberOfBytesRead = 0;
  v25 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
  }
  *a4 = 0;
  v11 = 3;
  FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
    return 0;
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        203,
        (unsigned int)WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids,
        (_DWORD)a2,
        LastError);
    }
    goto LABEL_62;
  }
  *a6 = FileSize;
  v15 = LocalAlloc(0, 0x200u);
  v16 = v15;
  if ( !v15 )
  {
    *a7 = GetLastError();
LABEL_63:
    CloseHandle(v13);
    return v11;
  }
  if ( !ReadFile(v13, v15, 0x200u, &NumberOfBytesRead, 0) || NumberOfBytesRead != 512 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      GetLastError();
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    }
    goto LABEL_68;
  }
  if ( BLBIMGI_BACKUP_FILE::IsValidFooter(a1, (struct _BLBIMGF_DRIVE_FOOTER *)v16, &v25, 0, 0, 0) )
  {
    if ( v25 < a3 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_DDDD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          206,
          WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids,
          v25 >> 32);
      }
      goto LABEL_68;
    }
    v17 = LocalAlloc(0, 0x400u);
    v18 = v17;
    if ( !v17 )
    {
      *a7 = GetLastError();
      goto LABEL_27;
    }
    if ( ReadFile(v13, v17, 0x400u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 1024 )
    {
      if ( BLBIMGI_BACKUP_FILE::IsValidHeader(a1, (struct _BLBIMGF_SPARSE_DRIVE_HEADER *)v18) )
      {
        v19 = (unsigned int)(4 * *((_DWORD *)a1 + 47));
        v20 = (unsigned int *)LocalAlloc(0, v19);
        v21 = v20;
        if ( v20 )
        {
          if ( ReadFile(v13, v20, v19, &NumberOfBytesRead, 0) && NumberOfBytesRead == (_DWORD)v19 )
          {
            if ( BLBIMGI_BACKUP_FILE::IsValidBat(a1, v21) )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids, a2);
              }
              *a4 = 1;
              *a5 = v21;
              LocalFree(v18);
              LocalFree(v16);
              CloseHandle(v13);
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
              }
              return 0;
            }
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            GetLastError();
            WPP_SF_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
          }
          LocalFree(v21);
          LocalFree(v18);
          LocalFree(v16);
          v11 = 0;
          goto LABEL_63;
        }
        *a7 = GetLastError();
        LocalFree(v18);
LABEL_27:
        LocalFree(v16);
        goto LABEL_63;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      GetLastError();
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
    }
    LocalFree(v18);
    LocalFree(v16);
LABEL_62:
    v11 = 0;
    goto LABEL_63;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids);
  }
LABEL_68:
  LocalFree(v16);
  CloseHandle(v13);
  return 0;
}

```

## disassembly

```asm
0x1400ca348  mov     [rsp-38h+arg_0], rbx
0x1400ca34d  mov     [rsp-38h+arg_18], r9
0x1400ca352  mov     [rsp-38h+arg_8], rdx
0x1400ca357  push    rbp
0x1400ca358  push    rsi
0x1400ca359  push    rdi
0x1400ca35a  push    r12
0x1400ca35c  push    r13
0x1400ca35e  push    r14
0x1400ca360  push    r15
0x1400ca362  mov     rbp, rsp
0x1400ca365  sub     rsp, 60h
0x1400ca369  xor     r15d, r15d
0x1400ca36c  mov     rbx, r9
0x1400ca36f  mov     qword ptr [rbp+FileSize], r15
0x1400ca373  mov     rsi, r8
0x1400ca376  mov     [rbp+NumberOfBytesRead], r15d
0x1400ca37a  mov     rdi, rdx
0x1400ca37d  mov     [rbp+var_10], r15
0x1400ca381  mov     r13, rcx
0x1400ca384  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca38b  lea     rax, WPP_GLOBAL_Control
0x1400ca392  mov     r14b, 4
0x1400ca395  cmp     rcx, rax
0x1400ca398  jz      short loc_1400CA3BB
0x1400ca39a  test    [rcx+1Ch], r14b
0x1400ca39e  jz      short loc_1400CA3BB
0x1400ca3a0  cmp     [rcx+19h], r14b
0x1400ca3a4  jb      short loc_1400CA3BB
0x1400ca3a6  mov     rcx, [rcx+10h]
0x1400ca3aa  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca3b1  mov     edx, 0CAh
0x1400ca3b6  call    WPP_SF_
0x1400ca3bb  mov     [rbx], r15b
0x1400ca3be  xor     r9d, r9d; lpSecurityAttributes
0x1400ca3c1  mov     ebx, 3
0x1400ca3c6  mov     [rsp+60h+hTemplateFile], r15; hTemplateFile
0x1400ca3cb  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1400ca3d3  mov     edx, 80000000h; dwDesiredAccess
0x1400ca3d8  mov     rcx, rdi; lpFileName
0x1400ca3db  mov     [rsp+60h+dwCreationDisposition], ebx; dwCreationDisposition
0x1400ca3df  lea     r8d, [rbx-2]; dwShareMode
0x1400ca3e3  call    cs:__imp_CreateFileW
0x1400ca3e9  mov     r12, rax
0x1400ca3ec  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400ca3f0  jz      loc_1400CA8C8
0x1400ca3f6  lea     rdx, [rbp+FileSize]; lpFileSize
0x1400ca3fa  mov     rcx, rax; hFile
0x1400ca3fd  call    cs:__imp_GetFileSizeEx
0x1400ca403  test    eax, eax
0x1400ca405  jnz     short loc_1400CA45F
0x1400ca407  mov     rax, cs:WPP_GLOBAL_Control
0x1400ca40e  lea     r13, WPP_GLOBAL_Control
0x1400ca415  cmp     rax, r13
0x1400ca418  jz      loc_1400CA85E
0x1400ca41e  test    [rax+1Ch], r14b
0x1400ca422  jz      loc_1400CA85E
0x1400ca428  cmp     [rax+19h], bl
0x1400ca42b  jb      loc_1400CA85E
0x1400ca431  call    cs:__imp_GetLastError
0x1400ca437  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca43e  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca445  mov     edx, 0CBh
0x1400ca44a  mov     [rsp+60h+dwCreationDisposition], eax
0x1400ca44e  mov     r9, rdi
0x1400ca451  mov     rcx, [rcx+10h]
0x1400ca455  call    WPP_SF_Sd
0x1400ca45a  jmp     loc_1400CA85E
0x1400ca45f  mov     rcx, qword ptr [rbp+FileSize]
0x1400ca463  mov     edx, 200h; uBytes
0x1400ca468  mov     rax, [rbp+arg_28]
0x1400ca46c  mov     [rax], rcx
0x1400ca46f  xor     ecx, ecx; uFlags
0x1400ca471  call    cs:__imp_LocalAlloc
0x1400ca477  mov     rdi, rax
0x1400ca47a  test    rax, rax
0x1400ca47d  jnz     short loc_1400CA490
0x1400ca47f  call    cs:__imp_GetLastError
0x1400ca485  mov     rcx, [rbp+arg_30]
0x1400ca489  mov     [rcx], eax
0x1400ca48b  jmp     loc_1400CA861
0x1400ca490  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400ca494  mov     qword ptr [rsp+60h+dwCreationDisposition], r15; lpOverlapped
0x1400ca499  mov     r8d, 200h; nNumberOfBytesToRead
0x1400ca49f  mov     rdx, rdi; lpBuffer
0x1400ca4a2  mov     rcx, r12; hFile
0x1400ca4a5  call    cs:__imp_ReadFile
0x1400ca4ab  test    eax, eax
0x1400ca4ad  jz      loc_1400CA86E
0x1400ca4b3  cmp     [rbp+NumberOfBytesRead], 200h
0x1400ca4ba  jnz     loc_1400CA86E
0x1400ca4c0  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], r15; unsigned int *
0x1400ca4c5  lea     r8, [rbp+var_10]; __int64 *
0x1400ca4c9  xor     r9d, r9d; struct _GUID *
0x1400ca4cc  mov     qword ptr [rsp+60h+dwCreationDisposition], r15; unsigned __int8 *
0x1400ca4d1  mov     rdx, rdi; struct _BLBIMGF_DRIVE_FOOTER *
0x1400ca4d4  mov     rcx, r13; this
0x1400ca4d7  call    ?IsValidFooter@BLBIMGI_BACKUP_FILE@@AEAAEPEAU_BLBIMGF_DRIVE_FOOTER@@PEA_JPEAU_GUID@@PEAEPEAK@Z; BLBIMGI_BACKUP_FILE::IsValidFooter(_BLBIMGF_DRIVE_FOOTER *,__int64 *,_GUID *,uchar *,ulong *)
0x1400ca4dc  test    al, al
0x1400ca4de  jnz     short loc_1400CA524
0x1400ca4e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca4e7  lea     r13, WPP_GLOBAL_Control
0x1400ca4ee  cmp     rcx, r13
0x1400ca4f1  jz      loc_1400CA8B6
0x1400ca4f7  test    [rcx+1Ch], r14b
0x1400ca4fb  jz      loc_1400CA8B6
0x1400ca501  cmp     [rcx+19h], bl
0x1400ca504  jb      loc_1400CA8B6
0x1400ca50a  mov     rcx, [rcx+10h]
0x1400ca50e  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca515  mov     edx, 0CDh
0x1400ca51a  call    WPP_SF_
0x1400ca51f  jmp     loc_1400CA8B6
0x1400ca524  mov     r8, [rbp+var_10]
0x1400ca528  cmp     r8, rsi
0x1400ca52b  jge     short loc_1400CA58C
0x1400ca52d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca534  lea     r13, WPP_GLOBAL_Control
0x1400ca53b  cmp     rcx, r13
0x1400ca53e  jz      loc_1400CA8B6
0x1400ca544  test    [rcx+1Ch], r14b
0x1400ca548  jz      loc_1400CA8B6
0x1400ca54e  cmp     [rcx+19h], bl
0x1400ca551  jb      loc_1400CA8B6
0x1400ca557  mov     rcx, [rcx+10h]
0x1400ca55b  mov     r9, r8
0x1400ca55e  mov     dword ptr [rsp+60h+hTemplateFile], esi
0x1400ca562  mov     rax, rsi
0x1400ca565  sar     rax, 20h
0x1400ca569  mov     edx, 0CEh
0x1400ca56e  mov     [rsp+60h+dwFlagsAndAttributes], eax
0x1400ca572  mov     [rsp+60h+dwCreationDisposition], r8d
0x1400ca577  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca57e  sar     r9, 20h
0x1400ca582  call    WPP_SF_DDDD
0x1400ca587  jmp     loc_1400CA8B6
0x1400ca58c  mov     edx, 400h; uBytes
0x1400ca591  xor     ecx, ecx; uFlags
0x1400ca593  call    cs:__imp_LocalAlloc
0x1400ca599  mov     rsi, rax
0x1400ca59c  test    rax, rax
0x1400ca59f  jnz     short loc_1400CA5BB
0x1400ca5a1  call    cs:__imp_GetLastError
0x1400ca5a7  mov     rcx, [rbp+arg_30]
0x1400ca5ab  mov     [rcx], eax
0x1400ca5ad  mov     rcx, rdi; hMem
0x1400ca5b0  call    cs:__imp_LocalFree
0x1400ca5b6  jmp     loc_1400CA861
0x1400ca5bb  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400ca5bf  mov     qword ptr [rsp+60h+dwCreationDisposition], r15; lpOverlapped
0x1400ca5c4  mov     r8d, 400h; nNumberOfBytesToRead
0x1400ca5ca  mov     rdx, rsi; lpBuffer
0x1400ca5cd  mov     rcx, r12; hFile
0x1400ca5d0  call    cs:__imp_ReadFile
0x1400ca5d6  test    eax, eax
0x1400ca5d8  jz      loc_1400CA804
0x1400ca5de  cmp     [rbp+NumberOfBytesRead], 400h
0x1400ca5e5  jnz     loc_1400CA804
0x1400ca5eb  mov     rdx, rsi; struct _BLBIMGF_SPARSE_DRIVE_HEADER *
0x1400ca5ee  mov     rcx, r13; this
0x1400ca5f1  call    ?IsValidHeader@BLBIMGI_BACKUP_FILE@@AEAAEPEAU_BLBIMGF_SPARSE_DRIVE_HEADER@@@Z; BLBIMGI_BACKUP_FILE::IsValidHeader(_BLBIMGF_SPARSE_DRIVE_HEADER *)
0x1400ca5f6  test    al, al
0x1400ca5f8  jnz     short loc_1400CA63E
0x1400ca5fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca601  lea     r13, WPP_GLOBAL_Control
0x1400ca608  cmp     rcx, r13
0x1400ca60b  jz      loc_1400CA84C
0x1400ca611  test    [rcx+1Ch], r14b
0x1400ca615  jz      loc_1400CA84C
0x1400ca61b  cmp     [rcx+19h], bl
0x1400ca61e  jb      loc_1400CA84C
0x1400ca624  mov     rcx, [rcx+10h]
0x1400ca628  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca62f  mov     edx, 0D0h
0x1400ca634  call    WPP_SF_
0x1400ca639  jmp     loc_1400CA84C
0x1400ca63e  mov     eax, [r13+0BCh]
0x1400ca645  xor     ecx, ecx; uFlags
0x1400ca647  shl     eax, 2
0x1400ca64a  mov     edx, eax; uBytes
0x1400ca64c  mov     r14d, eax
0x1400ca64f  call    cs:__imp_LocalAlloc
0x1400ca655  mov     r15, rax
0x1400ca658  test    rax, rax
0x1400ca65b  jnz     short loc_1400CA677
0x1400ca65d  call    cs:__imp_GetLastError
0x1400ca663  mov     rcx, [rbp+arg_30]
0x1400ca667  mov     [rcx], eax
0x1400ca669  mov     rcx, rsi; hMem
0x1400ca66c  call    cs:__imp_LocalFree
0x1400ca672  jmp     loc_1400CA5AD
0x1400ca677  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x1400ca67b  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOverlapped
0x1400ca684  mov     r8d, r14d; nNumberOfBytesToRead
0x1400ca687  mov     rdx, r15; lpBuffer
0x1400ca68a  mov     rcx, r12; hFile
0x1400ca68d  call    cs:__imp_ReadFile
0x1400ca693  test    eax, eax
0x1400ca695  jz      loc_1400CA797
0x1400ca69b  cmp     [rbp+NumberOfBytesRead], r14d
0x1400ca69f  jnz     loc_1400CA797
0x1400ca6a5  mov     rdx, r15; unsigned int *
0x1400ca6a8  mov     rcx, r13; this
0x1400ca6ab  call    ?IsValidBat@BLBIMGI_BACKUP_FILE@@AEAAEPEAK@Z; BLBIMGI_BACKUP_FILE::IsValidBat(ulong *)
0x1400ca6b0  test    al, al
0x1400ca6b2  jnz     short loc_1400CA6F8
0x1400ca6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca6bb  lea     r13, WPP_GLOBAL_Control
0x1400ca6c2  cmp     rcx, r13
0x1400ca6c5  jz      loc_1400CA7E5
0x1400ca6cb  test    byte ptr [rcx+1Ch], 4
0x1400ca6cf  jz      loc_1400CA7E5
0x1400ca6d5  cmp     [rcx+19h], bl
0x1400ca6d8  jb      loc_1400CA7E5
0x1400ca6de  mov     rcx, [rcx+10h]
0x1400ca6e2  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca6e9  mov     edx, 0D2h
0x1400ca6ee  call    WPP_SF_
0x1400ca6f3  jmp     loc_1400CA7E5
0x1400ca6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca6ff  lea     r13, WPP_GLOBAL_Control
0x1400ca706  cmp     rcx, r13
0x1400ca709  jz      short loc_1400CA730
0x1400ca70b  test    byte ptr [rcx+1Ch], 4
0x1400ca70f  jz      short loc_1400CA730
0x1400ca711  cmp     byte ptr [rcx+19h], 4
0x1400ca715  jb      short loc_1400CA730
0x1400ca717  mov     r9, [rbp+arg_8]
0x1400ca71b  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca722  mov     rcx, [rcx+10h]
0x1400ca726  mov     edx, 0D3h
0x1400ca72b  call    WPP_SF_S
0x1400ca730  mov     rax, [rbp+arg_18]
0x1400ca734  mov     rcx, rsi; hMem
0x1400ca737  mov     byte ptr [rax], 1
0x1400ca73a  mov     rax, [rbp+arg_20]
0x1400ca73e  mov     [rax], r15
0x1400ca741  call    cs:__imp_LocalFree
0x1400ca747  mov     rcx, rdi; hMem
0x1400ca74a  call    cs:__imp_LocalFree
0x1400ca750  mov     rcx, r12; hObject
0x1400ca753  call    cs:__imp_CloseHandle
0x1400ca759  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca760  cmp     rcx, r13
0x1400ca763  jz      loc_1400CA8C8
0x1400ca769  test    byte ptr [rcx+1Ch], 4
0x1400ca76d  jz      loc_1400CA8C8
0x1400ca773  cmp     byte ptr [rcx+19h], 4
0x1400ca777  jb      loc_1400CA8C8
0x1400ca77d  mov     rcx, [rcx+10h]
0x1400ca781  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca788  mov     edx, 0D4h
0x1400ca78d  call    WPP_SF_
0x1400ca792  jmp     loc_1400CA8C8
0x1400ca797  mov     rax, cs:WPP_GLOBAL_Control
0x1400ca79e  lea     r13, WPP_GLOBAL_Control
0x1400ca7a5  cmp     rax, r13
0x1400ca7a8  jz      short loc_1400CA7E5
0x1400ca7aa  test    byte ptr [rax+1Ch], 4
0x1400ca7ae  jz      short loc_1400CA7E5
0x1400ca7b0  cmp     [rax+19h], bl
0x1400ca7b3  jb      short loc_1400CA7E5
0x1400ca7b5  call    cs:__imp_GetLastError
0x1400ca7bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca7c2  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca7c9  mov     [rsp+60h+dwFlagsAndAttributes], eax
0x1400ca7cd  mov     edx, 0D1h
0x1400ca7d2  mov     eax, [rbp+NumberOfBytesRead]
0x1400ca7d5  mov     r9d, r14d
0x1400ca7d8  mov     [rsp+60h+dwCreationDisposition], eax
0x1400ca7dc  mov     rcx, [rcx+10h]
0x1400ca7e0  call    WPP_SF_LLL
0x1400ca7e5  mov     rcx, r15; hMem
0x1400ca7e8  call    cs:__imp_LocalFree
0x1400ca7ee  mov     rcx, rsi; hMem
0x1400ca7f1  call    cs:__imp_LocalFree
0x1400ca7f7  mov     rcx, rdi; hMem
0x1400ca7fa  call    cs:__imp_LocalFree
0x1400ca800  xor     ebx, ebx
0x1400ca802  jmp     short loc_1400CA861
0x1400ca804  mov     rax, cs:WPP_GLOBAL_Control
0x1400ca80b  lea     r13, WPP_GLOBAL_Control
0x1400ca812  cmp     rax, r13
0x1400ca815  jz      short loc_1400CA84C
0x1400ca817  test    [rax+1Ch], r14b
0x1400ca81b  jz      short loc_1400CA84C
0x1400ca81d  cmp     [rax+19h], bl
0x1400ca820  jb      short loc_1400CA84C
0x1400ca822  call    cs:__imp_GetLastError
0x1400ca828  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ca82f  lea     r8, WPP_62d9f8f678ff38895ac17dcb4a5adf2a_Traceguids
0x1400ca836  mov     r9d, [rbp+NumberOfBytesRead]
0x1400ca83a  mov     edx, 0CFh
0x1400ca83f  mov     [rsp+60h+dwCreationDisposition], eax
0x1400ca843  mov     rcx, [rcx+10h]
0x1400ca847  call    WPP_SF_dd
0x1400ca84c  mov     rcx, rsi; hMem
0x1400ca84f  call    cs:__imp_LocalFree
0x1400ca855  mov     rcx, rdi; hMem
0x1400ca858  call    cs:__imp_LocalFree
  ... truncated ...
```
