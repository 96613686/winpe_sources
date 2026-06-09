# WipeFilesOnVolume

- ea: `0x18009e22c`
- end: `0x18009e53a`
- name: `WipeFilesOnVolume`
- size: `782`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x18009d12c`

## callees

- `0x180001f18`
- `0x18009ae64`
- `0x18009b2f0`
- `0x18009b37c`
- `0x18009d2f0`
- `0x18009db1c`
- `0x18009dd18`
- `0x18009e050`
- `0x18009e22c`
- `0x18009e8f0`
- `0x18009f0e4`
- `0x18009f184`
- `0x1800ac3ac`
- `0x1800c97da`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x18009e2e0`
- `KERNEL32!lstrlenA` at `0x18009e41b`
- `KERNEL32!lstrlenA` at `0x18009e2e0`
- `KERNEL32!lstrlenA` at `0x18009e41b`
- `KERNEL32!FindClose` at `0x18009e3e7`
- `KERNEL32!FindClose` at `0x18009e3e7`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x18009e46e`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x18009e46e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x18009e45b`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x18009e45b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18009e43e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x18009e43e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18009e296`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18009e296`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009e501`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18009e501`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryA` at `0x18009e431`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryA` at `0x18009e431`

## pseudocode

```c
__int64 __fastcall WipeFilesOnVolume(unsigned int a1, int a2, __int64 a3)
{
  int v6; // r13d
  unsigned int v7; // edi
  HGLOBAL v8; // rax
  void *v9; // rbx
  unsigned __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  DWORD FileAttributesA; // esi
  __int64 v14; // rax
  HANDLE hFindFile[2]; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  CHAR String[288]; // [rsp+180h] [rbp+80h] BYREF
  char pszDest[288]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v6 = *(_DWORD *)(a3 + 3556);
  v7 = 0;
  hFindFile[0] = 0;
  *(_DWORD *)(a3 + 3556) = a2;
  v8 = GlobalAlloc(2u, 4u);
  v9 = v8;
  if ( v8 )
  {
    SetDirCount(v8);
    GetRootDirName(a1, String, 276);
    if ( (unsigned int)DBCS_IsLastBackSlash(String) )
    {
      v10 = lstrlenA(String) - 1LL;
      if ( v10 >= 0x114 )
        _report_rangecheckfailure();
      String[v10] = 0;
    }
    v7 = 1;
    while ( 1 )
    {
      StringCchCopyA(pszDest, 0x114u, String);
      if ( (unsigned int)FindFirstDir(a1, &FindFileData, hFindFile, String, 276, a3) )
      {
        v11 = PushDir(v9, String);
        if ( v11 )
          v9 = (void *)v11;
        v7 &= -(v11 != 0);
        StringCchCopyA(String, 0x114u, pszDest);
        if ( v7 )
        {
          do
          {
            if ( !(unsigned int)FindNextDir(&FindFileData, a3) )
              break;
            v12 = PushDir(v9, String);
            if ( v12 )
              v9 = (void *)v12;
            v7 &= -(v12 != 0);
            StringCchCopyA(String, 0x114u, pszDest);
          }
          while ( v7 );
        }
        else
        {
          v7 = 0;
        }
        if ( hFindFile[0] != (HANDLE)-1LL )
          FindClose(hFindFile[0]);
      }
      dzPump(a3);
      if ( (unsigned int)CheckForAbort(a3) )
        break;
      WipeFilesHere(String);
      if ( lstrlenA(String) <= 2 )
      {
        if ( !(unsigned int)PopDir(v9, String) )
          goto LABEL_35;
      }
      else
      {
        SetCurrentDirectoryA("..");
        FileAttributesA = GetFileAttributesA(String);
        if ( ((unsigned __int8)FileAttributesA & (unsigned __int8)a2 & 7) != 0 )
        {
          FileAttributesA &= 0xFFFFFFF8;
          SetFileAttributesA(String, FileAttributesA);
        }
        if ( (FileAttributesA & 7) != 0 || RemoveDirectoryA(String) )
        {
          if ( !(unsigned int)PopDir(v9, String) )
            goto LABEL_35;
        }
        else
        {
          StringCchCopyA(pszDest, 0x114u, String);
          if ( !(unsigned int)PopDir(v9, String) )
            goto LABEL_35;
          v14 = PushDir(v9, pszDest);
          if ( !v14 )
          {
            v7 = 0;
            goto LABEL_35;
          }
          v9 = (void *)v14;
        }
      }
      if ( !v7 )
        goto LABEL_35;
    }
    v7 = 1;
LABEL_35:
    GlobalFree(v9);
  }
  *(_DWORD *)(a3 + 3556) = v6;
  return v7;
}

```

## disassembly

```asm
0x18009e22c  mov     [rsp-8+arg_18], rbx
0x18009e231  push    rbp
0x18009e232  push    rsi
0x18009e233  push    rdi
0x18009e234  push    r12
0x18009e236  push    r13
0x18009e238  push    r14
0x18009e23a  push    r15
0x18009e23c  lea     rbp, [rsp-2D0h]
0x18009e244  sub     rsp, 3D0h
0x18009e24b  mov     rax, cs:__security_cookie
0x18009e252  xor     rax, rsp
0x18009e255  mov     [rbp+300h+var_40], rax
0x18009e25c  mov     r14, r8
0x18009e25f  mov     r15d, edx
0x18009e262  mov     r12d, ecx
0x18009e265  xor     edx, edx; Val
0x18009e267  mov     r8d, 140h; Size
0x18009e26d  lea     rcx, [rsp+400h+FindFileData]; void *
0x18009e272  call    memset_0
0x18009e277  mov     r13d, [r14+0DE4h]
0x18009e27e  xor     edi, edi
0x18009e280  mov     [rsp+400h+hFindFile], 0
0x18009e289  mov     [r14+0DE4h], r15d
0x18009e290  lea     edx, [rdi+4]; dwBytes
0x18009e293  lea     ecx, [rdi+2]; uFlags
0x18009e296  call    cs:__imp_GlobalAlloc
0x18009e29c  mov     rbx, rax
0x18009e29f  test    rax, rax
0x18009e2a2  jz      loc_18009E507
0x18009e2a8  xor     edx, edx
0x18009e2aa  mov     rcx, rax; hMem
0x18009e2ad  call    SetDirCount
0x18009e2b2  mov     esi, 114h
0x18009e2b7  lea     rdx, [rbp+300h+String]
0x18009e2be  mov     r8d, esi
0x18009e2c1  mov     ecx, r12d
0x18009e2c4  call    GetRootDirName
0x18009e2c9  lea     rcx, [rbp+300h+String]
0x18009e2d0  call    DBCS_IsLastBackSlash
0x18009e2d5  test    eax, eax
0x18009e2d7  jz      short loc_18009E2FD
0x18009e2d9  lea     rcx, [rbp+300h+String]; lpString
0x18009e2e0  call    cs:__imp_lstrlenA
0x18009e2e6  movsxd  rcx, eax
0x18009e2e9  dec     rcx
0x18009e2ec  cmp     rcx, rsi
0x18009e2ef  jnb     loc_18009E3D4
0x18009e2f5  mov     [rbp+rcx+300h+String], dil
0x18009e2fd  mov     edi, 1
0x18009e302  lea     r8, [rbp+300h+String]; pszSrc
0x18009e309  mov     rdx, rsi; cchDest
0x18009e30c  lea     rcx, [rbp+300h+pszDest]; pszDest
0x18009e313  call    StringCchCopyA
0x18009e318  lea     r9, [rbp+300h+String]
0x18009e31f  mov     [rsp+400h+var_3D8], r14
0x18009e324  lea     r8, [rsp+400h+hFindFile]
0x18009e329  mov     dword ptr [rsp+400h+var_3E0], esi
0x18009e32d  lea     rdx, [rsp+400h+FindFileData]
0x18009e332  mov     ecx, r12d
0x18009e335  call    FindFirstDir
0x18009e33a  test    eax, eax
0x18009e33c  jz      loc_18009E3ED
0x18009e342  lea     rdx, [rbp+300h+String]; pszSrc
0x18009e349  mov     rcx, rbx; hMem
0x18009e34c  call    PushDir
0x18009e351  test    rax, rax
0x18009e354  lea     r8, [rbp+300h+pszDest]; pszSrc
0x18009e35b  mov     rdx, rsi; cchDest
0x18009e35e  lea     rcx, [rbp+300h+String]; pszDest
0x18009e365  cmovnz  rbx, rax
0x18009e369  neg     rax
0x18009e36c  sbb     eax, eax
0x18009e36e  and     edi, eax
0x18009e370  call    StringCchCopyA
0x18009e375  test    edi, edi
0x18009e377  jz      short loc_18009E3DA
0x18009e379  mov     r9d, esi
0x18009e37c  mov     [rsp+400h+var_3E0], r14; __int64
0x18009e381  lea     r8, [rbp+300h+String]
0x18009e388  lea     rdx, [rsp+400h+hFindFile]
0x18009e38d  lea     rcx, [rsp+400h+FindFileData]; lpFindFileData
0x18009e392  call    FindNextDir
0x18009e397  test    eax, eax
0x18009e399  jz      short loc_18009E3DC
0x18009e39b  lea     rdx, [rbp+300h+String]; pszSrc
0x18009e3a2  mov     rcx, rbx; hMem
0x18009e3a5  call    PushDir
0x18009e3aa  test    rax, rax
0x18009e3ad  lea     r8, [rbp+300h+pszDest]; pszSrc
0x18009e3b4  mov     rdx, rsi; cchDest
0x18009e3b7  lea     rcx, [rbp+300h+String]; pszDest
0x18009e3be  cmovnz  rbx, rax
0x18009e3c2  neg     rax
0x18009e3c5  sbb     eax, eax
0x18009e3c7  and     edi, eax
0x18009e3c9  call    StringCchCopyA
0x18009e3ce  test    edi, edi
0x18009e3d0  jnz     short loc_18009E379
0x18009e3d2  jmp     short loc_18009E3DC
0x18009e3d4  call    __report_rangecheckfailure
0x18009e3da  xor     edi, edi
0x18009e3dc  mov     rcx, [rsp+400h+hFindFile]; hFindFile
0x18009e3e1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18009e3e5  jz      short loc_18009E3ED
0x18009e3e7  call    cs:__imp_FindClose
0x18009e3ed  mov     rcx, r14
0x18009e3f0  call    dzPump
0x18009e3f5  mov     rcx, r14
0x18009e3f8  call    CheckForAbort
0x18009e3fd  test    eax, eax
0x18009e3ff  jnz     loc_18009E4F9
0x18009e405  mov     edx, r15d
0x18009e408  lea     rcx, [rbp+300h+String]; pszSrc
0x18009e40f  call    WipeFilesHere
0x18009e414  lea     rcx, [rbp+300h+String]; lpString
0x18009e41b  call    cs:__imp_lstrlenA
0x18009e421  cmp     eax, 2
0x18009e424  jle     loc_18009E4D8
0x18009e42a  lea     rcx, PathName; ".."
0x18009e431  call    cs:__imp_SetCurrentDirectoryA
0x18009e437  lea     rcx, [rbp+300h+String]; lpFileName
0x18009e43e  call    cs:__imp_GetFileAttributesA
0x18009e444  mov     esi, eax
0x18009e446  mov     eax, r15d
0x18009e449  and     eax, esi
0x18009e44b  test    al, 7
0x18009e44d  jz      short loc_18009E461
0x18009e44f  and     esi, 0FFFFFFF8h
0x18009e452  lea     rcx, [rbp+300h+String]; lpFileName
0x18009e459  mov     edx, esi; dwFileAttributes
0x18009e45b  call    cs:__imp_SetFileAttributesA
0x18009e461  test    sil, 7
0x18009e465  jnz     short loc_18009E4BE
0x18009e467  lea     rcx, [rbp+300h+String]; lpPathName
0x18009e46e  call    cs:__imp_RemoveDirectoryA
0x18009e474  test    eax, eax
0x18009e476  jnz     short loc_18009E4BE
0x18009e478  mov     esi, 114h
0x18009e47d  lea     r8, [rbp+300h+String]; pszSrc
0x18009e484  mov     edx, esi; cchDest
0x18009e486  lea     rcx, [rbp+300h+pszDest]; pszDest
0x18009e48d  call    StringCchCopyA
0x18009e492  lea     rdx, [rbp+300h+String]; pszDest
0x18009e499  mov     rcx, rbx; hMem
0x18009e49c  call    PopDir
0x18009e4a1  test    eax, eax
0x18009e4a3  jz      short loc_18009E4FE
0x18009e4a5  lea     rdx, [rbp+300h+pszDest]; pszSrc
0x18009e4ac  mov     rcx, rbx; hMem
0x18009e4af  call    PushDir
0x18009e4b4  test    rax, rax
0x18009e4b7  jz      short loc_18009E4F5
0x18009e4b9  mov     rbx, rax
0x18009e4bc  jmp     short loc_18009E4EB
0x18009e4be  lea     rdx, [rbp+300h+String]; pszDest
0x18009e4c5  mov     rcx, rbx; hMem
0x18009e4c8  call    PopDir
0x18009e4cd  test    eax, eax
0x18009e4cf  jz      short loc_18009E4FE
0x18009e4d1  mov     esi, 114h
0x18009e4d6  jmp     short loc_18009E4EB
0x18009e4d8  lea     rdx, [rbp+300h+String]; pszDest
0x18009e4df  mov     rcx, rbx; hMem
0x18009e4e2  call    PopDir
0x18009e4e7  test    eax, eax
0x18009e4e9  jz      short loc_18009E4FE
0x18009e4eb  test    edi, edi
0x18009e4ed  jnz     loc_18009E302
0x18009e4f3  jmp     short loc_18009E4FE
0x18009e4f5  xor     edi, edi
0x18009e4f7  jmp     short loc_18009E4FE
0x18009e4f9  mov     edi, 1
0x18009e4fe  mov     rcx, rbx; hMem
0x18009e501  call    cs:__imp_GlobalFree
0x18009e507  mov     [r14+0DE4h], r13d
0x18009e50e  mov     eax, edi
0x18009e510  mov     rcx, [rbp+300h+var_40]
0x18009e517  xor     rcx, rsp; StackCookie
0x18009e51a  call    __security_check_cookie
0x18009e51f  mov     rbx, [rsp+400h+arg_18]
0x18009e527  add     rsp, 3D0h
0x18009e52e  pop     r15
0x18009e530  pop     r14
0x18009e532  pop     r13
0x18009e534  pop     r12
0x18009e536  pop     rdi
0x18009e537  pop     rsi
0x18009e538  pop     rbp
0x18009e539  retn
```
