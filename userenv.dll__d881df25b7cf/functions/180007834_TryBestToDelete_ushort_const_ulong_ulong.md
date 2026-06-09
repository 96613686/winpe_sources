# _TryBestToDelete(ushort const *,ulong,ulong)

- ea: `0x180007834`
- end: `0x1800079e8`
- name: `?_TryBestToDelete@@YAJPEBGKK@Z`
- size: `436`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800070c8`
- `0x18001aa00`

## callees

- `0x180007834`
- `0x18000dc50`
- `0x18001ad88`
- `0x18001b3b4`
- `0x18001b3e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007945`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007873`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007945`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007860`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000789e`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x180007860`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18000789e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800078c7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007931`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800078c7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180007931`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800078b9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180007923`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800078b9`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180007923`

## string_xrefs

- `0x18000796d`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x18000798d`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`
- `0x1800079c2`: `onecore\ds\security\gina\profile\userenv\lib\copydir.cpp`

## pseudocode

```c
__int64 __fastcall _TryBestToDelete(WCHAR *lpFileName, DWORD a2, char a3)
{
  int v3; // r12d
  DWORD v5; // ebp
  BOOL v7; // r14d
  unsigned int v8; // ebx
  BOOL v9; // eax
  signed int LastError; // eax
  BOOL v11; // eax
  signed int v12; // eax
  int v15; // [rsp+20h] [rbp-48h]
  char *v16; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = 0;
  v5 = a2;
  v7 = 1;
  if ( (a2 & 5) != 0 )
  {
    v5 = a2 & 0xFFFFFFFA;
    if ( !SetFileAttributesW(lpFileName, a2 & 0xFFFFFFFA) )
    {
      v7 = 0;
      if ( GetLastError() == 5 && (a3 & 2) != 0 && (int)_TakeOwnerAndAddAccess(lpFileName) >= 0 )
      {
        v3 = 1;
        v7 = SetFileAttributesW(lpFileName, v5);
      }
    }
  }
  v8 = 0;
  if ( (v5 & 0x10) != 0 )
    v9 = RemoveDirectoryW(lpFileName);
  else
    v9 = DeleteFileW(lpFileName);
  if ( v9 )
    return v8;
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError != 5 )
  {
    if ( LastError <= 0 )
      goto LABEL_27;
    goto LABEL_26;
  }
  if ( !v7 || v3 || (a3 & 2) == 0 )
  {
LABEL_26:
    v8 = (unsigned __int16)LastError | 0x80070000;
LABEL_27:
    if ( v8 != -2147024864 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC95,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
        (const char *)v8,
        v15);
    return v8;
  }
  if ( (int)_TakeOwnerAndAddAccess(lpFileName) < 0 )
    return (unsigned int)wil::details::in1diag3::Log_Hr(
                           retaddr,
                           (void *)0xC8F,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                           (const char *)0x80070005LL,
                           v15);
  v8 = 0;
  if ( (v5 & 0x10) != 0 )
    v11 = RemoveDirectoryW(lpFileName);
  else
    v11 = DeleteFileW(lpFileName);
  if ( !v11 )
  {
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    LODWORD(v16) = v5;
    return (unsigned int)wil::details::in1diag3::Log_HrMsg(
                           retaddr,
                           (void *)0xC8A,
                           (unsigned int)"onecore\\ds\\security\\gina\\profile\\userenv\\lib\\copydir.cpp",
                           (const char *)(unsigned int)v12,
                           (int)"dwAttributes= %ul",
                           v16);
  }
  return v8;
}

```

## disassembly

```asm
0x180007834  push    rbx
0x180007836  push    rbp
0x180007837  push    rsi
0x180007838  push    rdi
0x180007839  push    r12
0x18000783b  push    r14
0x18000783d  push    r15
0x18000783f  sub     rsp, 30h
0x180007843  xor     r12d, r12d
0x180007846  mov     r15d, r8d
0x180007849  mov     ebp, edx
0x18000784b  mov     rdi, rcx
0x18000784e  lea     ebx, [r12+1]
0x180007853  mov     r14d, ebx
0x180007856  test    dl, 5
0x180007859  jz      short loc_1800078AD
0x18000785b  and     ebp, 0FFFFFFFAh
0x18000785e  mov     edx, ebp; dwFileAttributes
0x180007860  call    cs:__imp_SetFileAttributesW
0x180007867  nop     dword ptr [rax+rax+00h]
0x18000786c  test    eax, eax
0x18000786e  jnz     short loc_1800078AD
0x180007870  xor     r14d, r14d
0x180007873  call    cs:__imp_GetLastError
0x18000787a  nop     dword ptr [rax+rax+00h]
0x18000787f  cmp     eax, 5
0x180007882  jnz     short loc_1800078AD
0x180007884  test    r15b, 2
0x180007888  jz      short loc_1800078AD
0x18000788a  mov     rcx, rdi; pObjectName
0x18000788d  call    ?_TakeOwnerAndAddAccess@@YAJPEBG@Z; _TakeOwnerAndAddAccess(ushort const *)
0x180007892  test    eax, eax
0x180007894  js      short loc_1800078AD
0x180007896  mov     edx, ebp; dwFileAttributes
0x180007898  mov     rcx, rdi; lpFileName
0x18000789b  mov     r12d, ebx
0x18000789e  call    cs:__imp_SetFileAttributesW
0x1800078a5  nop     dword ptr [rax+rax+00h]
0x1800078aa  mov     r14d, eax
0x1800078ad  xor     ebx, ebx
0x1800078af  mov     esi, ebp
0x1800078b1  mov     rcx, rdi; lpFileName
0x1800078b4  and     esi, 10h
0x1800078b7  jz      short loc_1800078C7
0x1800078b9  call    cs:__imp_RemoveDirectoryW
0x1800078c0  nop     dword ptr [rax+rax+00h]
0x1800078c5  jmp     short loc_1800078D3
0x1800078c7  call    cs:__imp_DeleteFileW
0x1800078ce  nop     dword ptr [rax+rax+00h]
0x1800078d3  test    eax, eax
0x1800078d5  jnz     loc_1800079D6
0x1800078db  call    cs:__imp_GetLastError
0x1800078e2  nop     dword ptr [rax+rax+00h]
0x1800078e7  mov     ebx, eax
0x1800078e9  cmp     eax, 5
0x1800078ec  jnz     loc_1800079A8
0x1800078f2  test    r14d, r14d
0x1800078f5  jz      loc_1800079AC
0x1800078fb  test    r12d, r12d
0x1800078fe  jnz     loc_1800079AC
0x180007904  test    r15b, 2
0x180007908  jz      loc_1800079AC
0x18000790e  mov     rcx, rdi; pObjectName
0x180007911  call    ?_TakeOwnerAndAddAccess@@YAJPEBG@Z; _TakeOwnerAndAddAccess(ushort const *)
0x180007916  test    eax, eax
0x180007918  js      short loc_180007988
0x18000791a  xor     ebx, ebx
0x18000791c  mov     rcx, rdi; lpFileName
0x18000791f  test    esi, esi
0x180007921  jz      short loc_180007931
0x180007923  call    cs:__imp_RemoveDirectoryW
0x18000792a  nop     dword ptr [rax+rax+00h]
0x18000792f  jmp     short loc_18000793D
0x180007931  call    cs:__imp_DeleteFileW
0x180007938  nop     dword ptr [rax+rax+00h]
0x18000793d  test    eax, eax
0x18000793f  jnz     loc_1800079D6
0x180007945  call    cs:__imp_GetLastError
0x18000794c  nop     dword ptr [rax+rax+00h]
0x180007951  test    eax, eax
0x180007953  jle     short loc_18000795D
0x180007955  movzx   eax, ax
0x180007958  or      eax, 80070000h
0x18000795d  mov     rcx, [rsp+68h]; this
0x180007962  lea     rdx, aDwattributesUl; "dwAttributes= %ul"
0x180007969  mov     dword ptr [rsp+68h+var_40], ebp; char *
0x18000796d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007974  mov     qword ptr [rsp+68h+var_48], rdx; int
0x180007979  mov     r9d, eax; char *
0x18000797c  mov     edx, 0C8Ah; void *
0x180007981  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180007986  jmp     short loc_1800079A4
0x180007988  mov     rcx, [rsp+68h]; this
0x18000798d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x180007994  mov     r9d, 80070005h; char *
0x18000799a  mov     edx, 0C8Fh; void *
0x18000799f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800079a4  mov     ebx, eax
0x1800079a6  jmp     short loc_1800079D6
0x1800079a8  test    eax, eax
0x1800079aa  jle     short loc_1800079B5
0x1800079ac  movzx   ebx, ax
0x1800079af  or      ebx, 80070000h
0x1800079b5  cmp     ebx, 80070020h
0x1800079bb  jz      short loc_1800079D6
0x1800079bd  mov     rcx, [rsp+68h]; this
0x1800079c2  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\u"...
0x1800079c9  mov     r9d, ebx; char *
0x1800079cc  mov     edx, 0C95h; void *
0x1800079d1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800079d6  mov     eax, ebx
0x1800079d8  add     rsp, 30h
0x1800079dc  pop     r15
0x1800079de  pop     r14
0x1800079e0  pop     r12
0x1800079e2  pop     rdi
0x1800079e3  pop     rsi
0x1800079e4  pop     rbp
0x1800079e5  pop     rbx
0x1800079e6  retn
```
