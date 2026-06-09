# WdsDeleteDirectory

- ea: `0x18001c370`
- end: `0x18001c605`
- name: `WdsDeleteDirectory`
- size: `661`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001c370`

## callees

- `0x180015a00`
- `0x18001a880`
- `0x18001b0cc`
- `0x18001c370`
- `0x180030362`
- `0x180030390`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001c508`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c546`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c55e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c508`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c546`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001c55e`
- `KERNEL32!FindClose` at `0x18001c532`
- `KERNEL32!FindClose` at `0x18001c532`
- `KERNEL32!FindNextFileW` at `0x18001c4ec`
- `KERNEL32!FindNextFileW` at `0x18001c4ec`
- `KERNEL32!FindFirstFileW` at `0x18001c40f`
- `KERNEL32!FindFirstFileW` at `0x18001c40f`
- `KERNEL32!DeleteFileW` at `0x18001c4d0`
- `KERNEL32!DeleteFileW` at `0x18001c4d0`
- `KERNEL32!RemoveDirectoryW` at `0x18001c5b2`
- `KERNEL32!RemoveDirectoryW` at `0x18001c5b2`
- `KERNEL32!GetLastError` at `0x18001c428`
- `KERNEL32!GetLastError` at `0x18001c599`
- `KERNEL32!GetLastError` at `0x18001c5c6`
- `KERNEL32!GetLastError` at `0x18001c5da`
- `KERNEL32!GetLastError` at `0x18001c428`
- `KERNEL32!GetLastError` at `0x18001c599`
- `KERNEL32!GetLastError` at `0x18001c5c6`
- `KERNEL32!GetLastError` at `0x18001c5da`

## pseudocode

```c
__int64 __fastcall WdsDeleteDirectory(const WCHAR *a1)
{
  WCHAR *v2; // rdi
  __int64 v3; // rdx
  __int64 v4; // rbx
  __int64 v5; // rdx
  __int64 v6; // r8
  HANDLE FirstFileW; // rsi
  DWORD LastError; // eax
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // r8
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  DWORD v17; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  LPCWSTR v21; // [rsp+28h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+38h] [rbp-D0h] BYREF

  lpFileName = 0;
  v21 = 0;
  v2 = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v3 = -1;
  do
    ++v3;
  while ( a1[v3] );
  LODWORD(v4) = FormatString((unsigned __int16 **)&lpFileName, v3 + 32, L"%s\\*", a1);
  if ( !(unsigned int)ElValidateWin32_8((unsigned int)v4, v5, v6, 4315) )
  {
    FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
    if ( FirstFileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      LODWORD(v4) = ElValidateWin32_8(LastError, v9, v10, 4320);
      if ( !(_DWORD)v4 )
        LODWORD(v4) = 31;
    }
    else
    {
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x400) != 0 )
        {
          LODWORD(v4) = 50;
          goto LABEL_21;
        }
        v4 = (unsigned int)ConcatenatePaths(a1, FindFileData.cFileName, &v21);
        v13 = ElValidateWin32_8(v4, v11, v12, 4339);
        v2 = (WCHAR *)v21;
        if ( v13 )
          goto LABEL_21;
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          if ( FindFileData.cFileName[0] != 46
            || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
          {
            LODWORD(v4) = WdsDeleteDirectory(v21);
            if ( (unsigned int)ElValidateWin32_8((unsigned int)v4, v14, v15, 4350) )
              goto LABEL_21;
          }
        }
        else if ( !DeleteFileW(v21) )
        {
          v17 = GetLastError();
          v20 = 4357;
          goto LABEL_30;
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          break;
        if ( v2 )
        {
          operator delete(v2);
          v2 = 0;
          v21 = 0;
        }
      }
      LODWORD(v4) = GetLastError();
      if ( (_DWORD)v4 != 18 )
        goto LABEL_21;
      LODWORD(v4) = 0;
      if ( RemoveDirectoryW(a1) )
        goto LABEL_21;
      v17 = GetLastError();
      v20 = 4379;
LABEL_30:
      LODWORD(v4) = ElValidateWin32_8(v17, v18, v19, v20);
      if ( !(_DWORD)v4 )
        LODWORD(v4) = 31;
LABEL_21:
      FindClose(FirstFileW);
      if ( v2 )
        operator delete(v2);
    }
  }
  if ( lpFileName )
    operator delete((void *)lpFileName);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001c370  mov     rax, rsp
0x18001c373  mov     [rax+10h], rbx
0x18001c377  mov     [rax+18h], rsi
0x18001c37b  mov     [rax+20h], rdi
0x18001c37f  push    rbp
0x18001c380  push    r12
0x18001c382  push    r14
0x18001c384  lea     rbp, [rax-1A8h]
0x18001c38b  sub     rsp, 290h
0x18001c392  mov     rax, cs:__security_cookie
0x18001c399  xor     rax, rsp
0x18001c39c  mov     [rbp+1A0h+var_20], rax
0x18001c3a3  xor     r12d, r12d
0x18001c3a6  mov     r14, rcx
0x18001c3a9  lea     rcx, [rsp+2A0h+FindFileData]; void *
0x18001c3ae  mov     [rsp+2A0h+lpFileName], r12
0x18001c3b3  xor     edx, edx; Val
0x18001c3b5  mov     [rsp+2A0h+var_280], r12
0x18001c3ba  mov     r8d, 250h; Size
0x18001c3c0  mov     edi, r12d
0x18001c3c3  call    memset_0
0x18001c3c8  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001c3cc  inc     rdx
0x18001c3cf  cmp     [r14+rdx*2], r12w
0x18001c3d4  jnz     short loc_18001C3CC
0x18001c3d6  add     rdx, 20h ; ' '; unsigned __int64
0x18001c3da  lea     r8, aS_0; "%s\\*"
0x18001c3e1  mov     r9, r14
0x18001c3e4  lea     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 **
0x18001c3e9  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18001c3ee  mov     r9d, 10DBh
0x18001c3f4  mov     ecx, eax
0x18001c3f6  mov     ebx, eax
0x18001c3f8  call    ElValidateWin32_8
0x18001c3fd  test    eax, eax
0x18001c3ff  jnz     loc_18001C552
0x18001c405  mov     rcx, [rsp+2A0h+lpFileName]; lpFileName
0x18001c40a  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x18001c40f  call    cs:__imp_FindFirstFileW
0x18001c416  nop     dword ptr [rax+rax+00h]
0x18001c41b  mov     rsi, rax
0x18001c41e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001c422  jnz     loc_18001C51C
0x18001c428  call    cs:__imp_GetLastError
0x18001c42f  nop     dword ptr [rax+rax+00h]
0x18001c434  mov     ecx, eax
0x18001c436  mov     r9d, 10E0h
0x18001c43c  call    ElValidateWin32_8
0x18001c441  mov     ebx, eax
0x18001c443  test    eax, eax
0x18001c445  jnz     loc_18001C552
0x18001c44b  lea     ebx, [rsi+20h]
0x18001c44e  jmp     loc_18001C552
0x18001c453  lea     r8, [rsp+2A0h+var_280]
0x18001c458  mov     rcx, r14
0x18001c45b  lea     rdx, [rsp+2A0h+FindFileData.cFileName]
0x18001c460  call    ConcatenatePaths
0x18001c465  mov     r9d, 10F3h
0x18001c46b  mov     ecx, eax
0x18001c46d  mov     ebx, eax
0x18001c46f  call    ElValidateWin32_8
0x18001c474  mov     rdi, [rsp+2A0h+var_280]
0x18001c479  test    eax, eax
0x18001c47b  jnz     loc_18001C52F
0x18001c481  test    byte ptr [rsp+2A0h+FindFileData.dwFileAttributes], 10h
0x18001c486  jz      short loc_18001C4CD
0x18001c488  cmp     [rsp+2A0h+FindFileData.cFileName], 2Eh ; '.'
0x18001c48e  movzx   eax, [rsp+2A0h+FindFileData.cFileName+2]
0x18001c493  jnz     short loc_18001C4B0
0x18001c495  test    ax, ax
0x18001c498  jz      short loc_18001C4E4
0x18001c49a  cmp     [rsp+2A0h+FindFileData.cFileName], 2Eh ; '.'
0x18001c4a0  jnz     short loc_18001C4B0
0x18001c4a2  cmp     ax, 2Eh ; '.'
0x18001c4a6  jnz     short loc_18001C4B0
0x18001c4a8  cmp     [rsp+2A0h+FindFileData.cFileName+4], r12w
0x18001c4ae  jz      short loc_18001C4E4
0x18001c4b0  mov     rcx, rdi
0x18001c4b3  call    WdsDeleteDirectory
0x18001c4b8  mov     r9d, 10FEh
0x18001c4be  mov     ecx, eax
0x18001c4c0  mov     ebx, eax
0x18001c4c2  call    ElValidateWin32_8
0x18001c4c7  test    eax, eax
0x18001c4c9  jnz     short loc_18001C52F
0x18001c4cb  jmp     short loc_18001C4E4
0x18001c4cd  mov     rcx, rdi; lpFileName
0x18001c4d0  call    cs:__imp_DeleteFileW
0x18001c4d7  nop     dword ptr [rax+rax+00h]
0x18001c4dc  test    eax, eax
0x18001c4de  jz      loc_18001C5DA
0x18001c4e4  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x18001c4e9  mov     rcx, rsi; hFindFile
0x18001c4ec  call    cs:__imp_FindNextFileW
0x18001c4f3  nop     dword ptr [rax+rax+00h]
0x18001c4f8  test    eax, eax
0x18001c4fa  jz      loc_18001C599
0x18001c500  test    rdi, rdi
0x18001c503  jz      short loc_18001C51C
0x18001c505  mov     rcx, rdi
0x18001c508  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c50f  nop     dword ptr [rax+rax+00h]
0x18001c514  mov     rdi, r12
0x18001c517  mov     [rsp+2A0h+var_280], r12
0x18001c51c  test    [rsp+2A0h+FindFileData.dwFileAttributes], 400h
0x18001c524  jz      loc_18001C453
0x18001c52a  mov     ebx, 32h ; '2'
0x18001c52f  mov     rcx, rsi; hFindFile
0x18001c532  call    cs:__imp_FindClose
0x18001c539  nop     dword ptr [rax+rax+00h]
0x18001c53e  test    rdi, rdi
0x18001c541  jz      short loc_18001C552
0x18001c543  mov     rcx, rdi
0x18001c546  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c54d  nop     dword ptr [rax+rax+00h]
0x18001c552  cmp     [rsp+2A0h+lpFileName], r12
0x18001c557  jz      short loc_18001C56A
0x18001c559  mov     rcx, [rsp+2A0h+lpFileName]
0x18001c55e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001c565  nop     dword ptr [rax+rax+00h]
0x18001c56a  mov     eax, ebx
0x18001c56c  mov     rcx, [rbp+1A0h+var_20]
0x18001c573  xor     rcx, rsp; StackCookie
0x18001c576  call    __security_check_cookie
0x18001c57b  lea     r11, [rsp+2A0h+var_10]
0x18001c583  mov     rbx, [r11+28h]
0x18001c587  mov     rsi, [r11+30h]
0x18001c58b  mov     rdi, [r11+38h]
0x18001c58f  mov     rsp, r11
0x18001c592  pop     r14
0x18001c594  pop     r12
0x18001c596  pop     rbp
0x18001c597  retn
0x18001c599  call    cs:__imp_GetLastError
0x18001c5a0  nop     dword ptr [rax+rax+00h]
0x18001c5a5  mov     ebx, eax
0x18001c5a7  cmp     eax, 12h
0x18001c5aa  jnz     short loc_18001C52F
0x18001c5ac  mov     rcx, r14; lpPathName
0x18001c5af  mov     ebx, r12d
0x18001c5b2  call    cs:__imp_RemoveDirectoryW
0x18001c5b9  nop     dword ptr [rax+rax+00h]
0x18001c5be  test    eax, eax
0x18001c5c0  jnz     loc_18001C52F
0x18001c5c6  call    cs:__imp_GetLastError
0x18001c5cd  nop     dword ptr [rax+rax+00h]
0x18001c5d2  mov     r9d, 111Bh
0x18001c5d8  jmp     short loc_18001C5EC
0x18001c5da  call    cs:__imp_GetLastError
0x18001c5e1  nop     dword ptr [rax+rax+00h]
0x18001c5e6  mov     r9d, 1105h
0x18001c5ec  mov     ecx, eax
0x18001c5ee  call    ElValidateWin32_8
0x18001c5f3  mov     ebx, eax
0x18001c5f5  test    eax, eax
0x18001c5f7  jnz     loc_18001C52F
0x18001c5fd  lea     ebx, [rax+1Fh]
0x18001c600  jmp     loc_18001C52F
```
