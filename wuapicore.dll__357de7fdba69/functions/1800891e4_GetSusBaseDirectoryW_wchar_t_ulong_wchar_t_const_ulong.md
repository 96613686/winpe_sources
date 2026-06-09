# GetSusBaseDirectoryW(wchar_t *,ulong,wchar_t const *,ulong *)

- ea: `0x1800891e4`
- end: `0x180089499`
- name: `?GetSusBaseDirectoryW@@YAJPEA_WKPEB_WPEAK@Z`
- size: `693`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *, unsigned int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180076b40`
- `0x180076c30`
- `0x180085e7c`

## callees

- `0x180006ac4`
- `0x180007d34`
- `0x180007ecc`
- `0x18001b7dc`
- `0x18002de68`
- `0x1800891e4`
- `0x1800922fc`
- `0x18009b050`
- `0x1800a19e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800893e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800893e6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800892ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800892ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089267`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180089267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008946d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008946d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800893dc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800893dc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800892d9`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800892d9`

## string_xrefs

- `0x180089223`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x1800892fe`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x180089435`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x18008944c`: `C:\__w\1\s\src\Client\lib\util\sdpath.cpp`
- `0x1800892cf`: `%PROGRAMDATA%`
- `0x180089260`: `SOFTWARE\Microsoft\WindowsUpdate\EditionSettings`

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
0x1800891e4  mov     [rsp-38h+arg_8], rbx
0x1800891e9  push    rbp
0x1800891ea  push    rsi
0x1800891eb  push    rdi
0x1800891ec  push    r12
0x1800891ee  push    r13
0x1800891f0  push    r14
0x1800891f2  push    r15
0x1800891f4  mov     rbp, rsp
0x1800891f7  sub     rsp, 50h
0x1800891fb  mov     rax, cs:__security_cookie
0x180089202  xor     rax, rsp
0x180089205  mov     [rbp+var_8], rax
0x180089209  xor     r12d, r12d
0x18008920c  mov     r15, r8
0x18008920f  mov     [rbp+var_20], r12
0x180089213  mov     rdi, rcx
0x180089216  mov     [rbp+var_18], r12
0x18008921a  test    rcx, rcx
0x18008921d  jnz     short loc_18008923F
0x18008921f  mov     rcx, [rbp+38h]; this
0x180089223  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18008922a  mov     ebx, 80004003h
0x18008922f  lea     edx, [rdi+2Dh]; void *
0x180089232  mov     r9d, ebx; char *
0x180089235  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008923a  jmp     loc_180089473
0x18008923f  mov     [rcx], r12w
0x180089243  lea     rax, [rbp+hKey]
0x180089247  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008924e  mov     [rsp+50h+phkResult], rax; unsigned int
0x180089253  mov     r9d, 1; samDesired
0x180089259  mov     [rbp+hKey], r12
0x18008925d  xor     r8d, r8d; ulOptions
0x180089260  lea     rdx, ?c_szEditionSettingsKey@@3QB_WB; "SOFTWARE\\Microsoft\\WindowsUpdate\\Edi"...
0x180089267  call    cs:__imp_RegOpenKeyExW
0x18008926d  or      r14, 0FFFFFFFFFFFFFFFFh
0x180089271  lea     r13d, [r14+5Dh]
0x180089275  test    eax, eax
0x180089277  jnz     short loc_1800892C1
0x180089279  mov     rcx, [rbp+hKey]; HKEY
0x18008927d  mov     r8, rdi; wchar_t *
0x180089280  call    ?RegQueryStringValueWithDefaultAndExpand@@YAJPEAUHKEY__@@PEB_WPEA_WK1H@Z; RegQueryStringValueWithDefaultAndExpand(HKEY__ *,wchar_t const *,wchar_t *,ulong,wchar_t const *,int)
0x180089285  cmp     [rdi], r13w
0x180089289  jnz     short loc_1800892C1
0x18008928b  cmp     [rdi+2], r13w
0x180089290  jnz     short loc_1800892C1
0x180089292  cmp     word ptr [rdi+4], 3Fh ; '?'
0x180089297  jnz     short loc_1800892C1
0x180089299  cmp     [rdi+6], r13w
0x18008929e  jnz     short loc_1800892C1
0x1800892a0  lea     rdx, [rdi+8]; Src
0x1800892a4  mov     r8, r14
0x1800892a7  inc     r8
0x1800892aa  cmp     [rdx+r8*2], r12w
0x1800892af  jnz     short loc_1800892A7
0x1800892b1  lea     r8, ds:2[r8*2]; Size
0x1800892b9  mov     rcx, rdi; void *
0x1800892bc  call    memmove
0x1800892c1  mov     esi, 104h
0x1800892c6  cmp     [rdi], r12w
0x1800892ca  jnz     short loc_18008930F
0x1800892cc  mov     r8d, esi; nSize
0x1800892cf  lea     rcx, Src; "%PROGRAMDATA%"
0x1800892d6  mov     rdx, rdi; lpDst
0x1800892d9  call    cs:__imp_ExpandEnvironmentStringsW
0x1800892df  dec     eax
0x1800892e1  cmp     eax, 103h
0x1800892e6  jbe     short loc_18008930F
0x1800892e8  mov     edx, esi; uSize
0x1800892ea  mov     rcx, rdi; lpBuffer
0x1800892ed  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800892f3  test    eax, eax
0x1800892f5  jnz     short loc_18008930F
0x1800892f7  lea     edx, [rax+5Fh]; void *
0x1800892fa  mov     rcx, [rbp+38h]; this
0x1800892fe  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180089305  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008930a  jmp     loc_180089462
0x18008930f  mov     r8, rsi
0x180089312  mov     rax, rdi
0x180089315  cmp     [rax], r12w
0x180089319  jz      short loc_180089325
0x18008931b  add     rax, 2
0x18008931f  sub     r8, 1
0x180089323  jnz     short loc_180089315
0x180089325  mov     rcx, rsi
0x180089328  mov     rax, r8
0x18008932b  sub     rcx, r8
0x18008932e  neg     rax
0x180089331  mov     rax, r8
0x180089334  sbb     rdx, rdx
0x180089337  and     rdx, rcx
0x18008933a  neg     rax
0x18008933d  sbb     ebx, ebx
0x18008933f  not     ebx
0x180089341  and     ebx, 80070057h
0x180089347  test    r8, r8
0x18008934a  jnz     short loc_180089358
0x18008934c  mov     r9d, ebx
0x18008934f  lea     edx, [r8+63h]
0x180089353  jmp     loc_180089431
0x180089358  test    r15, r15
0x18008935b  jnz     short loc_180089362
0x18008935d  mov     r14, r12
0x180089360  jmp     short loc_180089375
0x180089362  inc     r14
0x180089365  cmp     [r15+r14*2], r12w
0x18008936a  jnz     short loc_180089362
0x18008936c  cmp     [r15], r13w
0x180089370  jz      short loc_180089375
0x180089372  inc     r14
0x180089375  cmp     rdx, rsi
0x180089378  ja      loc_180089448
0x18008937e  lea     rax, [r14+16h]
0x180089382  add     rax, rdx
0x180089385  cmp     rax, rsi
0x180089388  ja      loc_180089448
0x18008938e  cmp     [rdi+rdx*2-2], r13w
0x180089394  jnz     short loc_1800893A2
0x180089396  lea     rax, [rdx-1]
0x18008939a  mov     rdx, rax
0x18008939d  mov     [rdi+rax*2], r12w
0x1800893a2  sub     rsi, rdx
0x1800893a5  mov     [rsp+50h+var_28], r12d; unsigned int
0x1800893aa  lea     rcx, [rdi+rdx*2]; pszDest
0x1800893ae  mov     rdx, rsi; unsigned __int64
0x1800893b1  lea     rax, [rbp+var_18]
0x1800893b5  lea     r9, [rbp+var_20]; wchar_t **
0x1800893b9  mov     [rsp+50h+phkResult], rax; int
0x1800893be  lea     r8, aSoftwaredistri; "\\SoftwareDistribution"
0x1800893c5  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x1800893ca  mov     ebx, eax
0x1800893cc  test    eax, eax
0x1800893ce  jns     short loc_1800893D7
0x1800893d0  mov     edx, 91h
0x1800893d5  jmp     short loc_18008942E
0x1800893d7  xor     edx, edx; lpSecurityAttributes
0x1800893d9  mov     rcx, rdi; lpPathName
0x1800893dc  call    cs:__imp_CreateDirectoryW
0x1800893e2  test    eax, eax
0x1800893e4  jnz     short loc_1800893FD
0x1800893e6  call    cs:__imp_GetLastError
0x1800893ec  cmp     eax, 0B7h
0x1800893f1  jz      short loc_1800893FD
0x1800893f3  mov     edx, 96h
0x1800893f8  jmp     loc_1800892FA
0x1800893fd  test    r15, r15
0x180089400  jz      short loc_180089443
0x180089402  mov     rcx, [rbp+var_20]
0x180089406  mov     rdx, [rbp+var_18]
0x18008940a  cmp     [r15], r13w
0x18008940e  jz      short loc_18008941B
0x180089410  mov     [rcx], r13w
0x180089414  add     rcx, 2; wchar_t *
0x180089418  dec     rdx; unsigned __int64
0x18008941b  mov     r8, r15; wchar_t *
0x18008941e  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180089423  mov     ebx, eax
0x180089425  test    eax, eax
0x180089427  jns     short loc_180089443
0x180089429  mov     edx, 0A2h; void *
0x18008942e  mov     r9d, eax; char *
0x180089431  mov     rcx, [rbp+38h]; this
0x180089435  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x18008943c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089441  jmp     short loc_180089464
0x180089443  mov     ebx, r12d
0x180089446  jmp     short loc_180089464
0x180089448  mov     rcx, [rbp+38h]; this
0x18008944c  lea     r8, aCW1SSrcClientL_21; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180089453  mov     r9d, 7Ah ; 'z'; char *
0x180089459  lea     edx, [r9+0Dh]; void *
0x18008945d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180089462  mov     ebx, eax
0x180089464  mov     rcx, [rbp+hKey]; hKey
0x180089468  test    rcx, rcx
0x18008946b  jz      short loc_180089473
0x18008946d  call    cs:__imp_RegCloseKey
0x180089473  mov     eax, ebx
0x180089475  mov     rcx, [rbp+var_8]
0x180089479  xor     rcx, rsp; StackCookie
0x18008947c  call    __security_check_cookie
0x180089481  mov     rbx, [rsp+50h+arg_8]
0x180089489  add     rsp, 50h
0x18008948d  pop     r15
0x18008948f  pop     r14
0x180089491  pop     r13
0x180089493  pop     r12
0x180089495  pop     rdi
0x180089496  pop     rsi
0x180089497  pop     rbp
0x180089498  retn
```
