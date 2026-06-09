# GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)

- ea: `0x180113cf4`
- end: `0x180113fd4`
- name: `?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z`
- size: `736`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `13`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800133f8`
- `0x180013c88`
- `0x180090b6c`
- `0x180098504`
- `0x180110ec8`
- `0x180115f58`
- `0x18012ce40`
- `0x18013c700`
- `0x180144938`
- `0x18017a430`
- `0x1801b5560`
- `0x1801d0dd8`
- `0x1801e01f0`

## callees

- `0x18000c644`
- `0x18000def4`
- `0x18000df20`
- `0x18003a6c4`
- `0x1800549f4`
- `0x180113cf4`
- `0x18012dfa4`
- `0x180238960`
- `0x180241100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113f0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113f0e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113fb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113fb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113d74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113d74`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180113f04`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180113f04`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180113e01`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180113e01`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180113e14`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180113e14`

## string_xrefs

- `0x180113df7`: `%PROGRAMDATA%`
- `0x180113d30`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x180113f24`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x180113f73`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x180113f9c`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x180113d6d`: `SOFTWARE\Microsoft\WindowsUpdate\EditionSettings`
- `0x180113d96`: `RootDirectory`

## pseudocode

```c
__int64 __fastcall GetSusBaseDirectoryW(wchar_t *a1, unsigned int a2, const wchar_t *a3, unsigned int *a4)
{
  unsigned __int64 v4; // rbx
  unsigned int v7; // ebx
  __int64 v8; // rsi
  wchar_t *v9; // rdx
  __int64 v10; // r8
  DWORD v11; // eax
  const char *v12; // r9
  __int64 v13; // rdx
  unsigned __int64 v14; // r10
  unsigned __int64 v15; // rdx
  wchar_t *v16; // rax
  unsigned __int64 i; // rcx
  unsigned __int64 v18; // rcx
  int v19; // eax
  unsigned __int64 v20; // r9
  __int64 v21; // rdx
  int LastError; // eax
  wchar_t *v23; // rcx
  unsigned __int64 v24; // rdx
  int v25; // eax
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  wchar_t *v29; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v30; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v4 = a2;
  v29 = 0;
  v30 = 0;
  if ( !a1 )
  {
    v7 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v7;
  }
  *a1 = 0;
  hKey = 0;
  v8 = -1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\EditionSettings", 0, 1u, &hKey) )
  {
    RegQueryStringValueWithDefaultAndExpand(hKey, L"RootDirectory", a1, v4, &OutputString, 0);
    if ( (unsigned int)v4 > 4 && *a1 == 92 && a1[1] == 92 && a1[2] == 63 && a1[3] == 92 )
    {
      v9 = a1 + 4;
      v10 = -1;
      do
        ++v10;
      while ( v9[v10] );
      memmove(a1, v9, 2 * v10 + 2);
    }
  }
  if ( !*a1 )
  {
    v11 = ExpandEnvironmentStringsW(L"%PROGRAMDATA%", a1, v4);
    if ( (!v11 || v11 > (unsigned int)v4) && !GetSystemWindowsDirectoryW(a1, v4) )
    {
      v13 = 95;
LABEL_39:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v13,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                    v12);
LABEL_40:
      v7 = LastError;
      goto LABEL_51;
    }
  }
  v14 = v4;
  if ( v4 > 0x7FFFFFFF )
  {
    v7 = -2147024809;
LABEL_49:
    v20 = v7;
    v21 = 99;
    goto LABEL_50;
  }
  v15 = v4;
  v16 = a1;
  for ( i = v4; v15; --v15 )
  {
    if ( !*v16 )
      break;
    ++v16;
  }
  v7 = v15 == 0 ? 0x80070057 : 0;
  if ( v15 )
    v18 = i - v15;
  else
    v18 = 0;
  if ( !v15 )
    goto LABEL_49;
  if ( a3 )
  {
    do
      ++v8;
    while ( a3[v8] );
    if ( *a3 != 92 )
      ++v8;
  }
  else
  {
    v8 = 0;
  }
  if ( v18 > v14 || v18 + v8 + 22 > v14 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x87,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                  (const char *)0x7A,
                  phkResulta);
    goto LABEL_40;
  }
  if ( a1[v18 - 1] == 92 )
    a1[--v18] = 0;
  v19 = StringCchCopyExW(&a1[v18], v14 - v18, L"\\SoftwareDistribution", &v29, &v30, 0);
  v7 = v19;
  if ( v19 >= 0 )
  {
    if ( !CreateDirectoryW(a1, 0) && GetLastError() != 183 )
    {
      v13 = 150;
      goto LABEL_39;
    }
    if ( !a3 )
      goto LABEL_46;
    v23 = v29;
    v24 = v30;
    if ( *a3 != 92 )
    {
      *v29 = 92;
      ++v23;
      --v24;
    }
    v25 = StringCchCopyW(v23, v24, a3);
    v7 = v25;
    if ( v25 >= 0 )
    {
LABEL_46:
      v7 = 0;
      goto LABEL_51;
    }
    v20 = (unsigned int)v25;
    v21 = 162;
  }
  else
  {
    v20 = (unsigned int)v19;
    v21 = 145;
  }
LABEL_50:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v21,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
    (const char *)v20,
    phkResulta);
LABEL_51:
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180113cf4  push    rbp
0x180113cf6  push    rbx
0x180113cf7  push    rsi
0x180113cf8  push    rdi
0x180113cf9  push    r12
0x180113cfb  push    r14
0x180113cfd  push    r15
0x180113cff  mov     rbp, rsp
0x180113d02  sub     rsp, 50h
0x180113d06  mov     rax, cs:__security_cookie
0x180113d0d  xor     rax, rsp
0x180113d10  mov     [rbp+var_8], rax
0x180113d14  xor     r15d, r15d
0x180113d17  mov     ebx, edx
0x180113d19  mov     [rbp+var_20], r15
0x180113d1d  mov     r14, r8
0x180113d20  mov     [rbp+var_18], r15
0x180113d24  mov     rdi, rcx
0x180113d27  test    rcx, rcx
0x180113d2a  jnz     short loc_180113D4C
0x180113d2c  mov     rcx, [rbp+38h]; this
0x180113d30  lea     r8, aCW1SSrcClientL_50; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113d37  mov     ebx, 80004003h
0x180113d3c  lea     edx, [rdi+2Dh]; void *
0x180113d3f  mov     r9d, ebx; char *
0x180113d42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113d47  jmp     loc_180113FB7
0x180113d4c  mov     [rcx], r15w
0x180113d50  lea     rax, [rbp+hKey]
0x180113d54  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180113d5b  mov     [rsp+50h+phkResult], rax; phkResult
0x180113d60  mov     r9d, 1; samDesired
0x180113d66  mov     [rbp+hKey], r15
0x180113d6a  xor     r8d, r8d; ulOptions
0x180113d6d  lea     rdx, ?c_szEditionSettingsKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Edi"...
0x180113d74  call    cs:__imp_RegOpenKeyExW
0x180113d7a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180113d7e  lea     r12d, [rsi+5Dh]
0x180113d82  test    eax, eax
0x180113d84  jnz     short loc_180113DEE
0x180113d86  mov     rcx, [rbp+hKey]; HKEY
0x180113d8a  lea     rax, OutputString
0x180113d91  mov     [rsp+50h+var_28], r15d; int
0x180113d96  lea     rdx, ?c_szRootDirectoryRegValue@@3QB_WB; "RootDirectory"
0x180113d9d  mov     r9d, ebx; unsigned int
0x180113da0  mov     [rsp+50h+phkResult], rax; int
0x180113da5  mov     r8, rdi; wchar_t *
0x180113da8  call    ?RegQueryStringValueWithDefaultAndExpand@@YAJPEAUHKEY__@@PEB_WPEA_WK1H@Z; RegQueryStringValueWithDefaultAndExpand(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *,int)
0x180113dad  cmp     ebx, 4
0x180113db0  jbe     short loc_180113DEE
0x180113db2  cmp     [rdi], r12w
0x180113db6  jnz     short loc_180113DEE
0x180113db8  cmp     [rdi+2], r12w
0x180113dbd  jnz     short loc_180113DEE
0x180113dbf  cmp     word ptr [rdi+4], 3Fh ; '?'
0x180113dc4  jnz     short loc_180113DEE
0x180113dc6  cmp     [rdi+6], r12w
0x180113dcb  jnz     short loc_180113DEE
0x180113dcd  lea     rdx, [rdi+8]; Src
0x180113dd1  mov     r8, rsi
0x180113dd4  inc     r8
0x180113dd7  cmp     [rdx+r8*2], r15w
0x180113ddc  jnz     short loc_180113DD4
0x180113dde  lea     r8, ds:2[r8*2]; Size
0x180113de6  mov     rcx, rdi; void *
0x180113de9  call    memmove
0x180113dee  cmp     [rdi], r15w
0x180113df2  jnz     short loc_180113E26
0x180113df4  mov     r8d, ebx; nSize
0x180113df7  lea     rcx, aProgramdata; "%PROGRAMDATA%"
0x180113dfe  mov     rdx, rdi; lpDst
0x180113e01  call    cs:__imp_ExpandEnvironmentStringsW
0x180113e07  test    eax, eax
0x180113e09  jz      short loc_180113E0F
0x180113e0b  cmp     eax, ebx
0x180113e0d  jbe     short loc_180113E26
0x180113e0f  mov     edx, ebx; uSize
0x180113e11  mov     rcx, rdi; lpBuffer
0x180113e14  call    cs:__imp_GetSystemWindowsDirectoryW
0x180113e1a  test    eax, eax
0x180113e1c  jnz     short loc_180113E26
0x180113e1e  lea     edx, [rax+5Fh]
0x180113e21  jmp     loc_180113F20
0x180113e26  mov     r10, rbx
0x180113e29  cmp     rbx, 7FFFFFFFh
0x180113e30  ja      loc_180113F8B
0x180113e36  mov     rdx, rbx
0x180113e39  mov     rax, rdi
0x180113e3c  mov     rcx, rbx
0x180113e3f  test    rbx, rbx
0x180113e42  jz      short loc_180113E54
0x180113e44  cmp     [rax], r15w
0x180113e48  jz      short loc_180113E54
0x180113e4a  add     rax, 2
0x180113e4e  sub     rdx, 1
0x180113e52  jnz     short loc_180113E44
0x180113e54  mov     rax, rdx
0x180113e57  neg     rax
0x180113e5a  sbb     ebx, ebx
0x180113e5c  not     ebx
0x180113e5e  and     ebx, 80070057h
0x180113e64  test    rdx, rdx
0x180113e67  jz      short loc_180113E6E
0x180113e69  sub     rcx, rdx
0x180113e6c  jmp     short loc_180113E71
0x180113e6e  mov     rcx, r15
0x180113e71  test    rdx, rdx
0x180113e74  jz      loc_180113F90
0x180113e7a  test    r14, r14
0x180113e7d  jnz     short loc_180113E84
0x180113e7f  mov     rsi, r15
0x180113e82  jmp     short loc_180113E97
0x180113e84  inc     rsi
0x180113e87  cmp     [r14+rsi*2], r15w
0x180113e8c  jnz     short loc_180113E84
0x180113e8e  cmp     [r14], r12w
0x180113e92  jz      short loc_180113E97
0x180113e94  inc     rsi
0x180113e97  cmp     rcx, r10
0x180113e9a  ja      loc_180113F6F
0x180113ea0  lea     rax, [rsi+16h]
0x180113ea4  add     rax, rcx
0x180113ea7  cmp     rax, r10
0x180113eaa  ja      loc_180113F6F
0x180113eb0  cmp     [rdi+rcx*2-2], r12w
0x180113eb6  jnz     short loc_180113EC4
0x180113eb8  lea     rax, [rcx-1]
0x180113ebc  mov     rcx, rax
0x180113ebf  mov     [rdi+rax*2], r15w
0x180113ec4  sub     r10, rcx
0x180113ec7  mov     [rsp+50h+var_28], r15d; unsigned int
0x180113ecc  lea     rax, [rbp+var_18]
0x180113ed0  mov     rdx, r10; unsigned __int64
0x180113ed3  lea     rcx, [rdi+rcx*2]; wchar_t *
0x180113ed7  mov     [rsp+50h+phkResult], rax; unsigned __int64 *
0x180113edc  lea     r9, [rbp+var_20]; wchar_t **
0x180113ee0  lea     r8, aSoftwaredistri; "\\SoftwareDistribution"
0x180113ee7  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180113eec  mov     ebx, eax
0x180113eee  test    eax, eax
0x180113ef0  jns     short loc_180113EFF
0x180113ef2  mov     r9d, eax
0x180113ef5  mov     edx, 91h
0x180113efa  jmp     loc_180113F98
0x180113eff  xor     edx, edx; lpSecurityAttributes
0x180113f01  mov     rcx, rdi; lpPathName
0x180113f04  call    cs:__imp_CreateDirectoryW
0x180113f0a  test    eax, eax
0x180113f0c  jnz     short loc_180113F34
0x180113f0e  call    cs:__imp_GetLastError
0x180113f14  cmp     eax, 0B7h
0x180113f19  jz      short loc_180113F34
0x180113f1b  mov     edx, 96h; void *
0x180113f20  mov     rcx, [rbp+38h]; this
0x180113f24  lea     r8, aCW1SSrcClientL_50; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113f2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180113f30  mov     ebx, eax
0x180113f32  jmp     short loc_180113FA8
0x180113f34  test    r14, r14
0x180113f37  jz      short loc_180113F6A
0x180113f39  mov     rcx, [rbp+var_20]
0x180113f3d  mov     rdx, [rbp+var_18]
0x180113f41  cmp     [r14], r12w
0x180113f45  jz      short loc_180113F52
0x180113f47  mov     [rcx], r12w
0x180113f4b  add     rcx, 2; wchar_t *
0x180113f4f  dec     rdx; unsigned __int64
0x180113f52  mov     r8, r14; wchar_t *
0x180113f55  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180113f5a  mov     ebx, eax
0x180113f5c  test    eax, eax
0x180113f5e  jns     short loc_180113F6A
0x180113f60  mov     r9d, eax
0x180113f63  mov     edx, 0A2h
0x180113f68  jmp     short loc_180113F98
0x180113f6a  mov     ebx, r15d
0x180113f6d  jmp     short loc_180113FA8
0x180113f6f  mov     rcx, [rbp+38h]; this
0x180113f73  lea     r8, aCW1SSrcClientL_50; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113f7a  mov     r9d, 7Ah ; 'z'; char *
0x180113f80  lea     edx, [r9+0Dh]; void *
0x180113f84  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180113f89  jmp     short loc_180113F30
0x180113f8b  mov     ebx, 80070057h
0x180113f90  mov     r9d, ebx; char *
0x180113f93  mov     edx, 63h ; 'c'; void *
0x180113f98  mov     rcx, [rbp+38h]; this
0x180113f9c  lea     r8, aCW1SSrcClientL_50; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180113fa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113fa8  mov     rcx, [rbp+hKey]; hKey
0x180113fac  test    rcx, rcx
0x180113faf  jz      short loc_180113FB7
0x180113fb1  call    cs:__imp_RegCloseKey
0x180113fb7  mov     eax, ebx
0x180113fb9  mov     rcx, [rbp+var_8]
0x180113fbd  xor     rcx, rsp; StackCookie
0x180113fc0  call    __security_check_cookie
0x180113fc5  add     rsp, 50h
0x180113fc9  pop     r15
0x180113fcb  pop     r14
0x180113fcd  pop     r12
0x180113fcf  pop     rdi
0x180113fd0  pop     rsi
0x180113fd1  pop     rbx
0x180113fd2  pop     rbp
0x180113fd3  retn
```
