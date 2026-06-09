# GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)

- ea: `0x18000c0e4`
- end: `0x18000c399`
- name: `?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z`
- size: `693`
- prototype: `__int64 __fastcall(wchar_t *, __int64, const wchar_t *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000b9d0`
- `0x18000d9e8`
- `0x18002b2d4`

## callees

- `0x180001cc8`
- `0x180003950`
- `0x180003974`
- `0x180009c1c`
- `0x18000b658`
- `0x18000c0e4`
- `0x18000ff74`
- `0x180042630`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c2e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000c1ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18000c1ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c36d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c36d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c167`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000c167`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000c1d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000c1d9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c2dc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000c2dc`

## string_xrefs

- `0x18000c123`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18000c1fe`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18000c335`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18000c34c`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18000c1cf`: `%PROGRAMDATA%`
- `0x18000c160`: `SOFTWARE\Microsoft\WindowsUpdate\EditionSettings`

## pseudocode

```c
__int64 __fastcall GetSusBaseDirectoryW(wchar_t *a1, __int64 a2, const wchar_t *a3, unsigned int *a4)
{
  unsigned int v6; // ebx
  const wchar_t *v7; // rdx
  unsigned int v8; // r9d
  __int64 v9; // r14
  wchar_t *v10; // rdx
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rdx
  int LastError; // eax
  __int64 v15; // r8
  wchar_t *v16; // rax
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  int v20; // eax
  wchar_t *v21; // rcx
  unsigned __int64 v22; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  const wchar_t *phkResulta; // [rsp+20h] [rbp-30h]
  unsigned int v26; // [rsp+28h] [rbp-28h]
  wchar_t *v27; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int64 v28; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  v27 = 0;
  v28 = 0;
  if ( !a1 )
  {
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)0x80004003LL,
      phkResult);
    return v6;
  }
  *a1 = 0;
  hKey = 0;
  v9 = -1;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\WindowsUpdate\\EditionSettings", 0, 1u, &hKey) )
  {
    RegQueryStringValueWithDefaultAndExpand(hKey, v7, a1, v8, phkResulta, v26);
    if ( *a1 == 92 && a1[1] == 92 && a1[2] == 63 && a1[3] == 92 )
    {
      v10 = a1 + 4;
      v11 = -1;
      do
        ++v11;
      while ( v10[v11] );
      memmove(a1, v10, 2 * v11 + 2);
    }
  }
  if ( *a1
    || ExpandEnvironmentStringsW(L"%PROGRAMDATA%", a1, 0x104u) - 1 <= 0x103
    || GetSystemWindowsDirectoryW(a1, 0x104u) )
  {
    v15 = 260;
    v16 = a1;
    do
    {
      if ( !*v16 )
        break;
      ++v16;
      --v15;
    }
    while ( v15 );
    v17 = (260 - v15) & -(__int64)(v15 != 0);
    v6 = v15 == 0 ? 0x80070057 : 0;
    if ( v15 )
    {
      if ( a3 )
      {
        do
          ++v9;
        while ( a3[v9] );
        if ( *a3 != 92 )
          ++v9;
      }
      else
      {
        v9 = 0;
      }
      if ( v17 > 0x104 || v17 + v9 + 22 > 0x104 )
      {
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x87,
                      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                      (const char *)0x7A,
                      (unsigned int)phkResulta);
        goto LABEL_44;
      }
      if ( a1[v17 - 1] == 92 )
        a1[--v17] = 0;
      v20 = StringCchCopyExW(&a1[v17], 260 - v17, L"\\SoftwareDistribution", &v27, &v28, 0);
      v6 = v20;
      if ( v20 >= 0 )
      {
        if ( !CreateDirectoryW(a1, 0) && GetLastError() != 183 )
        {
          v13 = 150;
          goto LABEL_15;
        }
        if ( !a3 )
          goto LABEL_42;
        v21 = v27;
        v22 = v28;
        if ( *a3 != 92 )
        {
          *v27 = 92;
          ++v21;
          --v22;
        }
        v20 = StringCchCopyW(v21, v22, a3);
        v6 = v20;
        if ( v20 >= 0 )
        {
LABEL_42:
          v6 = 0;
          goto LABEL_45;
        }
        v19 = 162;
      }
      else
      {
        v19 = 145;
      }
      v18 = (unsigned int)v20;
    }
    else
    {
      v18 = v6;
      v19 = 99;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
      (const char *)v18,
      (int)phkResulta);
    goto LABEL_45;
  }
  v13 = 95;
LABEL_15:
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v13,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\sdpath.cpp",
                v12);
LABEL_44:
  v6 = LastError;
LABEL_45:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x18000c0e4  mov     [rsp-38h+arg_8], rbx
0x18000c0e9  push    rbp
0x18000c0ea  push    rsi
0x18000c0eb  push    rdi
0x18000c0ec  push    r12
0x18000c0ee  push    r13
0x18000c0f0  push    r14
0x18000c0f2  push    r15
0x18000c0f4  mov     rbp, rsp
0x18000c0f7  sub     rsp, 50h
0x18000c0fb  mov     rax, cs:__security_cookie
0x18000c102  xor     rax, rsp
0x18000c105  mov     [rbp+var_8], rax
0x18000c109  xor     r12d, r12d
0x18000c10c  mov     r15, r8
0x18000c10f  mov     [rbp+var_20], r12
0x18000c113  mov     rdi, rcx
0x18000c116  mov     [rbp+var_18], r12
0x18000c11a  test    rcx, rcx
0x18000c11d  jnz     short loc_18000C13F
0x18000c11f  mov     rcx, [rbp+38h]; this
0x18000c123  lea     r8, aCW1SSrcClientL_18; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000c12a  mov     ebx, 80004003h
0x18000c12f  lea     edx, [rdi+2Dh]; void *
0x18000c132  mov     r9d, ebx; char *
0x18000c135  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c13a  jmp     loc_18000C373
0x18000c13f  mov     [rcx], r12w
0x18000c143  lea     rax, [rbp+hKey]
0x18000c147  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000c14e  mov     [rsp+50h+phkResult], rax; unsigned int
0x18000c153  mov     r9d, 1; samDesired
0x18000c159  mov     [rbp+hKey], r12
0x18000c15d  xor     r8d, r8d; ulOptions
0x18000c160  lea     rdx, ?c_szEditionSettingsKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Edi"...
0x18000c167  call    cs:__imp_RegOpenKeyExW
0x18000c16d  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000c171  lea     r13d, [r14+5Dh]
0x18000c175  test    eax, eax
0x18000c177  jnz     short loc_18000C1C1
0x18000c179  mov     rcx, [rbp+hKey]; HKEY
0x18000c17d  mov     r8, rdi; wchar_t *
0x18000c180  call    ?RegQueryStringValueWithDefaultAndExpand@@YAJPEAUHKEY__@@PEB_WPEA_WK1H@Z; RegQueryStringValueWithDefaultAndExpand(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *,int)
0x18000c185  cmp     [rdi], r13w
0x18000c189  jnz     short loc_18000C1C1
0x18000c18b  cmp     [rdi+2], r13w
0x18000c190  jnz     short loc_18000C1C1
0x18000c192  cmp     word ptr [rdi+4], 3Fh ; '?'
0x18000c197  jnz     short loc_18000C1C1
0x18000c199  cmp     [rdi+6], r13w
0x18000c19e  jnz     short loc_18000C1C1
0x18000c1a0  lea     rdx, [rdi+8]; Src
0x18000c1a4  mov     r8, r14
0x18000c1a7  inc     r8
0x18000c1aa  cmp     [rdx+r8*2], r12w
0x18000c1af  jnz     short loc_18000C1A7
0x18000c1b1  lea     r8, ds:2[r8*2]; Size
0x18000c1b9  mov     rcx, rdi; void *
0x18000c1bc  call    memmove
0x18000c1c1  mov     esi, 104h
0x18000c1c6  cmp     [rdi], r12w
0x18000c1ca  jnz     short loc_18000C20F
0x18000c1cc  mov     r8d, esi; nSize
0x18000c1cf  lea     rcx, Src; "%PROGRAMDATA%"
0x18000c1d6  mov     rdx, rdi; lpDst
0x18000c1d9  call    cs:__imp_ExpandEnvironmentStringsW
0x18000c1df  dec     eax
0x18000c1e1  cmp     eax, 103h
0x18000c1e6  jbe     short loc_18000C20F
0x18000c1e8  mov     edx, esi; uSize
0x18000c1ea  mov     rcx, rdi; lpBuffer
0x18000c1ed  call    cs:__imp_GetSystemWindowsDirectoryW
0x18000c1f3  test    eax, eax
0x18000c1f5  jnz     short loc_18000C20F
0x18000c1f7  lea     edx, [rax+5Fh]; void *
0x18000c1fa  mov     rcx, [rbp+38h]; this
0x18000c1fe  lea     r8, aCW1SSrcClientL_18; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000c205  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c20a  jmp     loc_18000C362
0x18000c20f  mov     r8, rsi
0x18000c212  mov     rax, rdi
0x18000c215  cmp     [rax], r12w
0x18000c219  jz      short loc_18000C225
0x18000c21b  add     rax, 2
0x18000c21f  sub     r8, 1
0x18000c223  jnz     short loc_18000C215
0x18000c225  mov     rcx, rsi
0x18000c228  mov     rax, r8
0x18000c22b  sub     rcx, r8
0x18000c22e  neg     rax
0x18000c231  mov     rax, r8
0x18000c234  sbb     rdx, rdx
0x18000c237  and     rdx, rcx
0x18000c23a  neg     rax
0x18000c23d  sbb     ebx, ebx
0x18000c23f  not     ebx
0x18000c241  and     ebx, 80070057h
0x18000c247  test    r8, r8
0x18000c24a  jnz     short loc_18000C258
0x18000c24c  mov     r9d, ebx
0x18000c24f  lea     edx, [r8+63h]
0x18000c253  jmp     loc_18000C331
0x18000c258  test    r15, r15
0x18000c25b  jnz     short loc_18000C262
0x18000c25d  mov     r14, r12
0x18000c260  jmp     short loc_18000C275
0x18000c262  inc     r14
0x18000c265  cmp     [r15+r14*2], r12w
0x18000c26a  jnz     short loc_18000C262
0x18000c26c  cmp     [r15], r13w
0x18000c270  jz      short loc_18000C275
0x18000c272  inc     r14
0x18000c275  cmp     rdx, rsi
0x18000c278  ja      loc_18000C348
0x18000c27e  lea     rax, [r14+16h]
0x18000c282  add     rax, rdx
0x18000c285  cmp     rax, rsi
0x18000c288  ja      loc_18000C348
0x18000c28e  cmp     [rdi+rdx*2-2], r13w
0x18000c294  jnz     short loc_18000C2A2
0x18000c296  lea     rax, [rdx-1]
0x18000c29a  mov     rdx, rax
0x18000c29d  mov     [rdi+rax*2], r12w
0x18000c2a2  sub     rsi, rdx
0x18000c2a5  mov     [rsp+50h+var_28], r12d; unsigned int
0x18000c2aa  lea     rcx, [rdi+rdx*2]; pszDest
0x18000c2ae  mov     rdx, rsi; unsigned __int64
0x18000c2b1  lea     rax, [rbp+var_18]
0x18000c2b5  lea     r9, [rbp+var_20]; wchar_t **
0x18000c2b9  mov     [rsp+50h+phkResult], rax; int
0x18000c2be  lea     r8, aSoftwaredistri; "\\SoftwareDistribution"
0x18000c2c5  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000c2ca  mov     ebx, eax
0x18000c2cc  test    eax, eax
0x18000c2ce  jns     short loc_18000C2D7
0x18000c2d0  mov     edx, 91h
0x18000c2d5  jmp     short loc_18000C32E
0x18000c2d7  xor     edx, edx; lpSecurityAttributes
0x18000c2d9  mov     rcx, rdi; lpPathName
0x18000c2dc  call    cs:__imp_CreateDirectoryW
0x18000c2e2  test    eax, eax
0x18000c2e4  jnz     short loc_18000C2FD
0x18000c2e6  call    cs:__imp_GetLastError
0x18000c2ec  cmp     eax, 0B7h
0x18000c2f1  jz      short loc_18000C2FD
0x18000c2f3  mov     edx, 96h
0x18000c2f8  jmp     loc_18000C1FA
0x18000c2fd  test    r15, r15
0x18000c300  jz      short loc_18000C343
0x18000c302  mov     rcx, [rbp+var_20]
0x18000c306  mov     rdx, [rbp+var_18]
0x18000c30a  cmp     [r15], r13w
0x18000c30e  jz      short loc_18000C31B
0x18000c310  mov     [rcx], r13w
0x18000c314  add     rcx, 2; wchar_t *
0x18000c318  dec     rdx; unsigned __int64
0x18000c31b  mov     r8, r15; wchar_t *
0x18000c31e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000c323  mov     ebx, eax
0x18000c325  test    eax, eax
0x18000c327  jns     short loc_18000C343
0x18000c329  mov     edx, 0A2h; void *
0x18000c32e  mov     r9d, eax; char *
0x18000c331  mov     rcx, [rbp+38h]; this
0x18000c335  lea     r8, aCW1SSrcClientL_18; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000c33c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c341  jmp     short loc_18000C364
0x18000c343  mov     ebx, r12d
0x18000c346  jmp     short loc_18000C364
0x18000c348  mov     rcx, [rbp+38h]; this
0x18000c34c  lea     r8, aCW1SSrcClientL_18; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18000c353  mov     r9d, 7Ah ; 'z'; char *
0x18000c359  lea     edx, [r9+0Dh]; void *
0x18000c35d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000c362  mov     ebx, eax
0x18000c364  mov     rcx, [rbp+hKey]; hKey
0x18000c368  test    rcx, rcx
0x18000c36b  jz      short loc_18000C373
0x18000c36d  call    cs:__imp_RegCloseKey
0x18000c373  mov     eax, ebx
0x18000c375  mov     rcx, [rbp+var_8]
0x18000c379  xor     rcx, rsp; StackCookie
0x18000c37c  call    __security_check_cookie
0x18000c381  mov     rbx, [rsp+50h+arg_8]
0x18000c389  add     rsp, 50h
0x18000c38d  pop     r15
0x18000c38f  pop     r14
0x18000c391  pop     r13
0x18000c393  pop     r12
0x18000c395  pop     rdi
0x18000c396  pop     rsi
0x18000c397  pop     rbp
0x18000c398  retn
```
