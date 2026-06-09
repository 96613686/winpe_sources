# WipeFilesOnVolume

- ea: `0x1800a2c3c`
- end: `0x1800a2f81`
- name: `WipeFilesOnVolume`
- size: `837`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x1800a1a1c`

## callees

- `0x180001f88`
- `0x18009f590`
- `0x18009fa48`
- `0x18009fad4`
- `0x1800a1be0`
- `0x1800a2498`
- `0x1800a26c4`
- `0x1800a2a4c`
- `0x1800a2c3c`
- `0x1800a3380`
- `0x1800a3bc8`
- `0x1800a3c84`
- `0x1800b1ad8`
- `0x1800cf56a`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!lstrlenA` at `0x1800a2cf6`
- `KERNEL32!lstrlenA` at `0x1800a2e3d`
- `KERNEL32!lstrlenA` at `0x1800a2cf6`
- `KERNEL32!lstrlenA` at `0x1800a2e3d`
- `KERNEL32!FindClose` at `0x1800a2e03`
- `KERNEL32!FindClose` at `0x1800a2e03`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800a2ea8`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryA` at `0x1800a2ea8`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800a2e8f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesA` at `0x1800a2e8f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800a2e6c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x1800a2e6c`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a2ca6`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800a2ca6`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a2f41`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800a2f41`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryA` at `0x1800a2e59`
- `api-ms-win-core-processenvironment-l1-1-0!SetCurrentDirectoryA` at `0x1800a2e59`

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
0x1800a2c3c  mov     [rsp-8+arg_18], rbx
0x1800a2c41  push    rbp
0x1800a2c42  push    rsi
0x1800a2c43  push    rdi
0x1800a2c44  push    r12
0x1800a2c46  push    r13
0x1800a2c48  push    r14
0x1800a2c4a  push    r15
0x1800a2c4c  lea     rbp, [rsp-2D0h]
0x1800a2c54  sub     rsp, 3D0h
0x1800a2c5b  mov     rax, cs:__security_cookie
0x1800a2c62  xor     rax, rsp
0x1800a2c65  mov     [rbp+300h+var_40], rax
0x1800a2c6c  mov     r14, r8
0x1800a2c6f  mov     r15d, edx
0x1800a2c72  mov     r12d, ecx
0x1800a2c75  xor     edx, edx; Val
0x1800a2c77  mov     r8d, 140h; Size
0x1800a2c7d  lea     rcx, [rsp+400h+FindFileData]; void *
0x1800a2c82  call    memset_0
0x1800a2c87  mov     r13d, [r14+0DE4h]
0x1800a2c8e  xor     edi, edi
0x1800a2c90  mov     [rsp+400h+hFindFile], 0
0x1800a2c99  mov     [r14+0DE4h], r15d
0x1800a2ca0  lea     edx, [rdi+4]; dwBytes
0x1800a2ca3  lea     ecx, [rdi+2]; uFlags
0x1800a2ca6  call    cs:__imp_GlobalAlloc
0x1800a2cad  nop     dword ptr [rax+rax+00h]
0x1800a2cb2  mov     rbx, rax
0x1800a2cb5  test    rax, rax
0x1800a2cb8  jz      loc_1800A2F4D
0x1800a2cbe  xor     edx, edx
0x1800a2cc0  mov     rcx, rax; hMem
0x1800a2cc3  call    SetDirCount
0x1800a2cc8  mov     esi, 114h
0x1800a2ccd  lea     rdx, [rbp+300h+String]
0x1800a2cd4  mov     r8d, esi
0x1800a2cd7  mov     ecx, r12d
0x1800a2cda  call    GetRootDirName
0x1800a2cdf  lea     rcx, [rbp+300h+String]
0x1800a2ce6  call    DBCS_IsLastBackSlash
0x1800a2ceb  test    eax, eax
0x1800a2ced  jz      short loc_1800A2D19
0x1800a2cef  lea     rcx, [rbp+300h+String]; lpString
0x1800a2cf6  call    cs:__imp_lstrlenA
0x1800a2cfd  nop     dword ptr [rax+rax+00h]
0x1800a2d02  movsxd  rcx, eax
0x1800a2d05  dec     rcx
0x1800a2d08  cmp     rcx, rsi
0x1800a2d0b  jnb     loc_1800A2DF0
0x1800a2d11  mov     [rbp+rcx+300h+String], dil
0x1800a2d19  mov     edi, 1
0x1800a2d1e  lea     r8, [rbp+300h+String]; pszSrc
0x1800a2d25  mov     rdx, rsi; cchDest
0x1800a2d28  lea     rcx, [rbp+300h+pszDest]; pszDest
0x1800a2d2f  call    StringCchCopyA
0x1800a2d34  lea     r9, [rbp+300h+String]
0x1800a2d3b  mov     [rsp+400h+var_3D8], r14
0x1800a2d40  lea     r8, [rsp+400h+hFindFile]
0x1800a2d45  mov     dword ptr [rsp+400h+var_3E0], esi
0x1800a2d49  lea     rdx, [rsp+400h+FindFileData]
0x1800a2d4e  mov     ecx, r12d
0x1800a2d51  call    FindFirstDir
0x1800a2d56  test    eax, eax
0x1800a2d58  jz      loc_1800A2E0F
0x1800a2d5e  lea     rdx, [rbp+300h+String]; pszSrc
0x1800a2d65  mov     rcx, rbx; hMem
0x1800a2d68  call    PushDir
0x1800a2d6d  test    rax, rax
0x1800a2d70  lea     r8, [rbp+300h+pszDest]; pszSrc
0x1800a2d77  mov     rdx, rsi; cchDest
0x1800a2d7a  lea     rcx, [rbp+300h+String]; pszDest
0x1800a2d81  cmovnz  rbx, rax
0x1800a2d85  neg     rax
0x1800a2d88  sbb     eax, eax
0x1800a2d8a  and     edi, eax
0x1800a2d8c  call    StringCchCopyA
0x1800a2d91  test    edi, edi
0x1800a2d93  jz      short loc_1800A2DF6
0x1800a2d95  mov     r9d, esi
0x1800a2d98  mov     [rsp+400h+var_3E0], r14; __int64
0x1800a2d9d  lea     r8, [rbp+300h+String]
0x1800a2da4  lea     rdx, [rsp+400h+hFindFile]
0x1800a2da9  lea     rcx, [rsp+400h+FindFileData]; lpFindFileData
0x1800a2dae  call    FindNextDir
0x1800a2db3  test    eax, eax
0x1800a2db5  jz      short loc_1800A2DF8
0x1800a2db7  lea     rdx, [rbp+300h+String]; pszSrc
0x1800a2dbe  mov     rcx, rbx; hMem
0x1800a2dc1  call    PushDir
0x1800a2dc6  test    rax, rax
0x1800a2dc9  lea     r8, [rbp+300h+pszDest]; pszSrc
0x1800a2dd0  mov     rdx, rsi; cchDest
0x1800a2dd3  lea     rcx, [rbp+300h+String]; pszDest
0x1800a2dda  cmovnz  rbx, rax
0x1800a2dde  neg     rax
0x1800a2de1  sbb     eax, eax
0x1800a2de3  and     edi, eax
0x1800a2de5  call    StringCchCopyA
0x1800a2dea  test    edi, edi
0x1800a2dec  jnz     short loc_1800A2D95
0x1800a2dee  jmp     short loc_1800A2DF8
0x1800a2df0  call    __report_rangecheckfailure
0x1800a2df6  xor     edi, edi
0x1800a2df8  mov     rcx, [rsp+400h+hFindFile]; hFindFile
0x1800a2dfd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a2e01  jz      short loc_1800A2E0F
0x1800a2e03  call    cs:__imp_FindClose
0x1800a2e0a  nop     dword ptr [rax+rax+00h]
0x1800a2e0f  mov     rcx, r14
0x1800a2e12  call    dzPump
0x1800a2e17  mov     rcx, r14
0x1800a2e1a  call    CheckForAbort
0x1800a2e1f  test    eax, eax
0x1800a2e21  jnz     loc_1800A2F39
0x1800a2e27  mov     edx, r15d
0x1800a2e2a  lea     rcx, [rbp+300h+String]; pszSrc
0x1800a2e31  call    WipeFilesHere
0x1800a2e36  lea     rcx, [rbp+300h+String]; lpString
0x1800a2e3d  call    cs:__imp_lstrlenA
0x1800a2e44  nop     dword ptr [rax+rax+00h]
0x1800a2e49  cmp     eax, 2
0x1800a2e4c  jle     loc_1800A2F18
0x1800a2e52  lea     rcx, PathName; ".."
0x1800a2e59  call    cs:__imp_SetCurrentDirectoryA
0x1800a2e60  nop     dword ptr [rax+rax+00h]
0x1800a2e65  lea     rcx, [rbp+300h+String]; lpFileName
0x1800a2e6c  call    cs:__imp_GetFileAttributesA
0x1800a2e73  nop     dword ptr [rax+rax+00h]
0x1800a2e78  mov     esi, eax
0x1800a2e7a  mov     eax, r15d
0x1800a2e7d  and     eax, esi
0x1800a2e7f  test    al, 7
0x1800a2e81  jz      short loc_1800A2E9B
0x1800a2e83  and     esi, 0FFFFFFF8h
0x1800a2e86  lea     rcx, [rbp+300h+String]; lpFileName
0x1800a2e8d  mov     edx, esi; dwFileAttributes
0x1800a2e8f  call    cs:__imp_SetFileAttributesA
0x1800a2e96  nop     dword ptr [rax+rax+00h]
0x1800a2e9b  test    sil, 7
0x1800a2e9f  jnz     short loc_1800A2EFE
0x1800a2ea1  lea     rcx, [rbp+300h+String]; lpPathName
0x1800a2ea8  call    cs:__imp_RemoveDirectoryA
0x1800a2eaf  nop     dword ptr [rax+rax+00h]
0x1800a2eb4  test    eax, eax
0x1800a2eb6  jnz     short loc_1800A2EFE
0x1800a2eb8  mov     esi, 114h
0x1800a2ebd  lea     r8, [rbp+300h+String]; pszSrc
0x1800a2ec4  mov     edx, esi; cchDest
0x1800a2ec6  lea     rcx, [rbp+300h+pszDest]; pszDest
0x1800a2ecd  call    StringCchCopyA
0x1800a2ed2  lea     rdx, [rbp+300h+String]; pszDest
0x1800a2ed9  mov     rcx, rbx; hMem
0x1800a2edc  call    PopDir
0x1800a2ee1  test    eax, eax
0x1800a2ee3  jz      short loc_1800A2F3E
0x1800a2ee5  lea     rdx, [rbp+300h+pszDest]; pszSrc
0x1800a2eec  mov     rcx, rbx; hMem
0x1800a2eef  call    PushDir
0x1800a2ef4  test    rax, rax
0x1800a2ef7  jz      short loc_1800A2F35
0x1800a2ef9  mov     rbx, rax
0x1800a2efc  jmp     short loc_1800A2F2B
0x1800a2efe  lea     rdx, [rbp+300h+String]; pszDest
0x1800a2f05  mov     rcx, rbx; hMem
0x1800a2f08  call    PopDir
0x1800a2f0d  test    eax, eax
0x1800a2f0f  jz      short loc_1800A2F3E
0x1800a2f11  mov     esi, 114h
0x1800a2f16  jmp     short loc_1800A2F2B
0x1800a2f18  lea     rdx, [rbp+300h+String]; pszDest
0x1800a2f1f  mov     rcx, rbx; hMem
0x1800a2f22  call    PopDir
0x1800a2f27  test    eax, eax
0x1800a2f29  jz      short loc_1800A2F3E
0x1800a2f2b  test    edi, edi
0x1800a2f2d  jnz     loc_1800A2D1E
0x1800a2f33  jmp     short loc_1800A2F3E
0x1800a2f35  xor     edi, edi
0x1800a2f37  jmp     short loc_1800A2F3E
0x1800a2f39  mov     edi, 1
0x1800a2f3e  mov     rcx, rbx; hMem
0x1800a2f41  call    cs:__imp_GlobalFree
0x1800a2f48  nop     dword ptr [rax+rax+00h]
0x1800a2f4d  mov     [r14+0DE4h], r13d
0x1800a2f54  mov     eax, edi
0x1800a2f56  mov     rcx, [rbp+300h+var_40]
0x1800a2f5d  xor     rcx, rsp; StackCookie
0x1800a2f60  call    __security_check_cookie
0x1800a2f65  mov     rbx, [rsp+400h+arg_18]
0x1800a2f6d  add     rsp, 3D0h
0x1800a2f74  pop     r15
0x1800a2f76  pop     r14
0x1800a2f78  pop     r13
0x1800a2f7a  pop     r12
0x1800a2f7c  pop     rdi
0x1800a2f7d  pop     rsi
0x1800a2f7e  pop     rbp
0x1800a2f7f  retn
```
