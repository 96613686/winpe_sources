# WdsDeleteDirectory

- ea: `0x18001b4c0`
- end: `0x18001b740`
- name: `WdsDeleteDirectory`
- size: `640`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001b4c0`

## callees

- `0x180014ce0`
- `0x180019a40`
- `0x18001a28c`
- `0x18001b4c0`
- `0x18002e468`
- `0x18002f3ba`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b578`
- `KERNEL32!GetLastError` at `0x18001b6d4`
- `KERNEL32!GetLastError` at `0x18001b701`
- `KERNEL32!GetLastError` at `0x18001b715`
- `KERNEL32!GetLastError` at `0x18001b578`
- `KERNEL32!GetLastError` at `0x18001b6d4`
- `KERNEL32!GetLastError` at `0x18001b701`
- `KERNEL32!GetLastError` at `0x18001b715`
- `KERNEL32!RemoveDirectoryW` at `0x18001b6ed`
- `KERNEL32!RemoveDirectoryW` at `0x18001b6ed`
- `KERNEL32!DeleteFileW` at `0x18001b620`
- `KERNEL32!DeleteFileW` at `0x18001b620`
- `KERNEL32!FindFirstFileW` at `0x18001b55f`
- `KERNEL32!FindFirstFileW` at `0x18001b55f`
- `KERNEL32!FindNextFileW` at `0x18001b63c`
- `KERNEL32!FindNextFileW` at `0x18001b63c`
- `KERNEL32!FindClose` at `0x18001b67b`
- `KERNEL32!FindClose` at `0x18001b67b`

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
0x18001b4c0  mov     rax, rsp
0x18001b4c3  mov     [rax+10h], rbx
0x18001b4c7  mov     [rax+18h], rsi
0x18001b4cb  mov     [rax+20h], rdi
0x18001b4cf  push    rbp
0x18001b4d0  push    r12
0x18001b4d2  push    r14
0x18001b4d4  lea     rbp, [rax-1A8h]
0x18001b4db  sub     rsp, 290h
0x18001b4e2  mov     rax, cs:__security_cookie
0x18001b4e9  xor     rax, rsp
0x18001b4ec  mov     [rbp+1A0h+var_20], rax
0x18001b4f3  xor     r12d, r12d
0x18001b4f6  mov     r14, rcx
0x18001b4f9  lea     rcx, [rsp+2A0h+FindFileData]; void *
0x18001b4fe  mov     [rsp+2A0h+lpFileName], r12
0x18001b503  xor     edx, edx; Val
0x18001b505  mov     [rsp+2A0h+var_280], r12
0x18001b50a  mov     r8d, 250h; Size
0x18001b510  mov     edi, r12d
0x18001b513  call    memset_0
0x18001b518  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001b51c  inc     rdx
0x18001b51f  cmp     [r14+rdx*2], r12w
0x18001b524  jnz     short loc_18001B51C
0x18001b526  add     rdx, 20h ; ' '; unsigned __int64
0x18001b52a  lea     r8, aS_0; "%s\\*"
0x18001b531  mov     r9, r14
0x18001b534  lea     rcx, [rsp+2A0h+lpFileName]; unsigned __int16 **
0x18001b539  call    ?FormatString@@YAKPEAPEAG_KPEBGZZ; FormatString(ushort * *,unsigned __int64,ushort const *,...)
0x18001b53e  mov     r9d, 10DBh
0x18001b544  mov     ecx, eax
0x18001b546  mov     ebx, eax
0x18001b548  call    ElValidateWin32_8
0x18001b54d  test    eax, eax
0x18001b54f  jnz     loc_18001B694
0x18001b555  mov     rcx, [rsp+2A0h+lpFileName]; lpFileName
0x18001b55a  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x18001b55f  call    cs:__imp_FindFirstFileW
0x18001b566  nop     dword ptr [rax+rax+00h]
0x18001b56b  mov     rsi, rax
0x18001b56e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001b572  jnz     loc_18001B665
0x18001b578  call    cs:__imp_GetLastError
0x18001b57f  nop     dword ptr [rax+rax+00h]
0x18001b584  mov     ecx, eax
0x18001b586  mov     r9d, 10E0h
0x18001b58c  call    ElValidateWin32_8
0x18001b591  mov     ebx, eax
0x18001b593  test    eax, eax
0x18001b595  jnz     loc_18001B694
0x18001b59b  lea     ebx, [rsi+20h]
0x18001b59e  jmp     loc_18001B694
0x18001b5a3  lea     r8, [rsp+2A0h+var_280]
0x18001b5a8  mov     rcx, r14
0x18001b5ab  lea     rdx, [rsp+2A0h+FindFileData.cFileName]
0x18001b5b0  call    ConcatenatePaths
0x18001b5b5  mov     r9d, 10F3h
0x18001b5bb  mov     ecx, eax
0x18001b5bd  mov     ebx, eax
0x18001b5bf  call    ElValidateWin32_8
0x18001b5c4  mov     rdi, [rsp+2A0h+var_280]
0x18001b5c9  test    eax, eax
0x18001b5cb  jnz     loc_18001B678
0x18001b5d1  test    byte ptr [rsp+2A0h+FindFileData.dwFileAttributes], 10h
0x18001b5d6  jz      short loc_18001B61D
0x18001b5d8  cmp     [rsp+2A0h+FindFileData.cFileName], 2Eh ; '.'
0x18001b5de  movzx   eax, [rsp+2A0h+FindFileData.cFileName+2]
0x18001b5e3  jnz     short loc_18001B600
0x18001b5e5  test    ax, ax
0x18001b5e8  jz      short loc_18001B634
0x18001b5ea  cmp     [rsp+2A0h+FindFileData.cFileName], 2Eh ; '.'
0x18001b5f0  jnz     short loc_18001B600
0x18001b5f2  cmp     ax, 2Eh ; '.'
0x18001b5f6  jnz     short loc_18001B600
0x18001b5f8  cmp     [rsp+2A0h+FindFileData.cFileName+4], r12w
0x18001b5fe  jz      short loc_18001B634
0x18001b600  mov     rcx, rdi
0x18001b603  call    WdsDeleteDirectory
0x18001b608  mov     r9d, 10FEh
0x18001b60e  mov     ecx, eax
0x18001b610  mov     ebx, eax
0x18001b612  call    ElValidateWin32_8
0x18001b617  test    eax, eax
0x18001b619  jnz     short loc_18001B678
0x18001b61b  jmp     short loc_18001B634
0x18001b61d  mov     rcx, rdi; lpFileName
0x18001b620  call    cs:__imp_DeleteFileW
0x18001b627  nop     dword ptr [rax+rax+00h]
0x18001b62c  test    eax, eax
0x18001b62e  jz      loc_18001B715
0x18001b634  lea     rdx, [rsp+2A0h+FindFileData]; lpFindFileData
0x18001b639  mov     rcx, rsi; hFindFile
0x18001b63c  call    cs:__imp_FindNextFileW
0x18001b643  nop     dword ptr [rax+rax+00h]
0x18001b648  test    eax, eax
0x18001b64a  jz      loc_18001B6D4
0x18001b650  test    rdi, rdi
0x18001b653  jz      short loc_18001B665
0x18001b655  mov     rcx, rdi; lpMem
0x18001b658  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b65d  mov     rdi, r12
0x18001b660  mov     [rsp+2A0h+var_280], r12
0x18001b665  test    [rsp+2A0h+FindFileData.dwFileAttributes], 400h
0x18001b66d  jz      loc_18001B5A3
0x18001b673  mov     ebx, 32h ; '2'
0x18001b678  mov     rcx, rsi; hFindFile
0x18001b67b  call    cs:__imp_FindClose
0x18001b682  nop     dword ptr [rax+rax+00h]
0x18001b687  test    rdi, rdi
0x18001b68a  jz      short loc_18001B694
0x18001b68c  mov     rcx, rdi; lpMem
0x18001b68f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b694  cmp     [rsp+2A0h+lpFileName], r12
0x18001b699  jz      short loc_18001B6A5
0x18001b69b  mov     rcx, [rsp+2A0h+lpFileName]; lpMem
0x18001b6a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b6a5  mov     eax, ebx
0x18001b6a7  mov     rcx, [rbp+1A0h+var_20]
0x18001b6ae  xor     rcx, rsp; StackCookie
0x18001b6b1  call    __security_check_cookie
0x18001b6b6  lea     r11, [rsp+2A0h+var_10]
0x18001b6be  mov     rbx, [r11+28h]
0x18001b6c2  mov     rsi, [r11+30h]
0x18001b6c6  mov     rdi, [r11+38h]
0x18001b6ca  mov     rsp, r11
0x18001b6cd  pop     r14
0x18001b6cf  pop     r12
0x18001b6d1  pop     rbp
0x18001b6d2  retn
0x18001b6d4  call    cs:__imp_GetLastError
0x18001b6db  nop     dword ptr [rax+rax+00h]
0x18001b6e0  mov     ebx, eax
0x18001b6e2  cmp     eax, 12h
0x18001b6e5  jnz     short loc_18001B678
0x18001b6e7  mov     rcx, r14; lpPathName
0x18001b6ea  mov     ebx, r12d
0x18001b6ed  call    cs:__imp_RemoveDirectoryW
0x18001b6f4  nop     dword ptr [rax+rax+00h]
0x18001b6f9  test    eax, eax
0x18001b6fb  jnz     loc_18001B678
0x18001b701  call    cs:__imp_GetLastError
0x18001b708  nop     dword ptr [rax+rax+00h]
0x18001b70d  mov     r9d, 111Bh
0x18001b713  jmp     short loc_18001B727
0x18001b715  call    cs:__imp_GetLastError
0x18001b71c  nop     dword ptr [rax+rax+00h]
0x18001b721  mov     r9d, 1105h
0x18001b727  mov     ecx, eax
0x18001b729  call    ElValidateWin32_8
0x18001b72e  mov     ebx, eax
0x18001b730  test    eax, eax
0x18001b732  jnz     loc_18001B678
0x18001b738  lea     ebx, [rax+1Fh]
0x18001b73b  jmp     loc_18001B678
```
