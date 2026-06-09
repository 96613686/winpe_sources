# WUPathCchCombine(wchar_t *,ulong,wchar_t const *,wchar_t const *)

- ea: `0x18000f27c`
- end: `0x18000f52d`
- name: `?WUPathCchCombine@@YAJPEA_WKPEB_W1@Z`
- size: `689`
- prototype: `__int64 __fastcall(wchar_t *, unsigned int, const wchar_t *, const wchar_t *)`
- caller_count: `3`
- callee_count: `6`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18000e05c`
- `0x18000f534`
- `0x18001531c`

## callees

- `0x180003950`
- `0x180009c1c`
- `0x18000b67c`
- `0x18000eea4`
- `0x18000f1e0`
- `0x18000f27c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18000f46f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripToRootW` at `0x18000f46f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18000f434`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x18000f434`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000f390`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18000f390`

## string_xrefs

- `0x18000f2b6`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`
- `0x18000f348`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`
- `0x18000f3cc`: `C:\__w\1\s\src\Client\lib\wusafefn\safepath.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall WUPathCchCombine(wchar_t *a1, unsigned int a2, const wchar_t *a3, const wchar_t *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v8; // rdx
  int v9; // ebx
  int v11; // edi
  __int64 v12; // rdx
  int v13; // ebp
  __int64 v14; // rdx
  wchar_t **v15; // r9
  wchar_t **v16; // r9
  int v17; // [rsp+20h] [rbp-28h]
  unsigned __int64 *v18; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a2;
  if ( !a1 )
  {
    v8 = 274;
LABEL_3:
    v9 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
      (const char *)(unsigned int)v9,
      v17);
    return (unsigned int)v9;
  }
  if ( !a2 )
  {
    v8 = 275;
    goto LABEL_3;
  }
  if ( a3 )
  {
    if ( *a3 )
      goto LABEL_22;
    if ( !a4 )
    {
LABEL_19:
      if ( a2 <= 1 )
      {
        v9 = -2147024774;
        v8 = 288;
        goto LABEL_4;
      }
      *(_DWORD *)a1 = 92;
      return 0;
    }
  }
  else if ( !a4 )
  {
    *a1 = 0;
    return 0;
  }
  if ( !*a4 )
    goto LABEL_19;
  if ( !a3 || !*a3 )
  {
    v11 = StringCchCopyExW(a1, a2, a4, 0, 0, 0x1100u);
    if ( v11 < 0 )
    {
      v12 = 302;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
        (const char *)(unsigned int)v11,
        v17);
      return (unsigned int)v11;
    }
    goto LABEL_44;
  }
LABEL_22:
  if ( !a4 || !*a4 )
  {
    v11 = StringCchCopyExW(a1, a2, a3, 0, 0, 0x1100u);
    if ( v11 < 0 )
    {
      v12 = 309;
      goto LABEL_18;
    }
    goto LABEL_44;
  }
  if ( PathIsRelativeW(a4) )
  {
    v13 = StringCchCopyExW(a1, v4, a3, 0, 0, 0x1100u);
    if ( v13 >= 0 )
    {
      v13 = WUPathCchAddBackslash(a1, v4);
      if ( v13 >= 0 )
      {
        v11 = StringCchCatExW(a1, v4, a4, v15, v18, 0x1100u);
        if ( v11 < 0 )
        {
          v12 = 318;
          goto LABEL_18;
        }
LABEL_44:
        v9 = WUPathCchCanonicalize(a1, v4, a1);
        if ( v9 < 0 )
        {
          v8 = 346;
          goto LABEL_4;
        }
        return 0;
      }
      v14 = 317;
    }
    else
    {
      v14 = 316;
    }
  }
  else
  {
    if ( *a4 != 92 || PathIsUNCW(a4) )
    {
      v11 = StringCchCopyExW(a1, v4, a4, 0, 0, 0x1100u);
      if ( v11 < 0 )
      {
        v12 = 342;
        goto LABEL_18;
      }
      goto LABEL_44;
    }
    v13 = StringCchCopyExW(a1, v4, a3, 0, 0, 0x1100u);
    if ( v13 >= 0 )
    {
      PathStripToRootW(a1);
      v13 = WUPathCchAddBackslash(a1, v4);
      if ( v13 >= 0 )
      {
        v11 = StringCchCatExW(a1, v4, a4 + 1, v16, v18, 0x1100u);
        if ( v11 < 0 )
        {
          v12 = 335;
          goto LABEL_18;
        }
        goto LABEL_44;
      }
      v14 = 332;
    }
    else
    {
      v14 = 326;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\wusafefn\\safepath.cpp",
    (const char *)(unsigned int)v13,
    (int)v18);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000f27c  mov     [rsp+arg_0], rbx
0x18000f281  mov     [rsp+arg_8], rbp
0x18000f286  mov     [rsp+arg_10], rsi
0x18000f28b  push    rdi
0x18000f28c  push    r14
0x18000f28e  push    r15
0x18000f290  sub     rsp, 30h
0x18000f294  xor     r15d, r15d
0x18000f297  mov     esi, edx
0x18000f299  mov     rdi, r9
0x18000f29c  mov     rbp, r8
0x18000f29f  mov     rbx, rcx
0x18000f2a2  test    rcx, rcx
0x18000f2a5  jnz     short loc_18000F2C9
0x18000f2a7  mov     edx, 112h; void *
0x18000f2ac  mov     ebx, 80070057h
0x18000f2b1  mov     rcx, [rsp+48h]; this
0x18000f2b6  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000f2bd  mov     r9d, ebx; char *
0x18000f2c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f2c5  mov     eax, ebx
0x18000f2c7  jmp     short loc_18000F2E4
0x18000f2c9  test    edx, edx
0x18000f2cb  jnz     short loc_18000F2D4
0x18000f2cd  mov     edx, 113h
0x18000f2d2  jmp     short loc_18000F2AC
0x18000f2d4  test    rbp, rbp
0x18000f2d7  jnz     short loc_18000F2FD
0x18000f2d9  test    rdi, rdi
0x18000f2dc  jnz     short loc_18000F308
0x18000f2de  mov     [rcx], r15w
0x18000f2e2  xor     eax, eax
0x18000f2e4  mov     rbx, [rsp+48h+arg_0]
0x18000f2e9  mov     rbp, [rsp+48h+arg_8]
0x18000f2ee  mov     rsi, [rsp+48h+arg_10]
0x18000f2f3  add     rsp, 30h
0x18000f2f7  pop     r15
0x18000f2f9  pop     r14
0x18000f2fb  pop     rdi
0x18000f2fc  retn
0x18000f2fd  cmp     [r8], r15w
0x18000f301  jnz     short loc_18000F37A
0x18000f303  test    rdi, rdi
0x18000f306  jz      short loc_18000F35B
0x18000f308  cmp     [r9], r15w
0x18000f30c  jz      short loc_18000F35B
0x18000f30e  test    rbp, rbp
0x18000f311  jz      short loc_18000F319
0x18000f313  cmp     [r8], r15w
0x18000f317  jnz     short loc_18000F37A
0x18000f319  mov     rdx, rsi; unsigned __int64
0x18000f31c  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f324  xor     r9d, r9d; wchar_t **
0x18000f327  mov     [rsp+48h+var_28], r15; int
0x18000f32c  mov     r8, rdi; wchar_t *
0x18000f32f  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f334  mov     edi, eax
0x18000f336  test    eax, eax
0x18000f338  jns     loc_18000F50C
0x18000f33e  mov     edx, 12Eh; void *
0x18000f343  mov     rcx, [rsp+48h]; this
0x18000f348  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000f34f  mov     r9d, edi; char *
0x18000f352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f357  mov     eax, edi
0x18000f359  jmp     short loc_18000F2E4
0x18000f35b  cmp     esi, 1
0x18000f35e  ja      short loc_18000F36F
0x18000f360  mov     ebx, 8007007Ah
0x18000f365  mov     edx, 120h
0x18000f36a  jmp     loc_18000F2B1
0x18000f36f  mov     dword ptr [rcx], 5Ch ; '\'
0x18000f375  jmp     loc_18000F2E2
0x18000f37a  test    rdi, rdi
0x18000f37d  jz      loc_18000F4E4
0x18000f383  cmp     [r9], r15w
0x18000f387  jz      loc_18000F4E4
0x18000f38d  mov     rcx, rdi; pszPath
0x18000f390  call    cs:__imp_PathIsRelativeW
0x18000f396  test    eax, eax
0x18000f398  jz      loc_18000F423
0x18000f39e  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f3a6  xor     r9d, r9d; wchar_t **
0x18000f3a9  mov     r8, rbp; wchar_t *
0x18000f3ac  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18000f3b1  mov     rdx, rsi; unsigned __int64
0x18000f3b4  mov     rcx, rbx; pszDest
0x18000f3b7  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f3bc  mov     ebp, eax
0x18000f3be  test    eax, eax
0x18000f3c0  jns     short loc_18000F3E2
0x18000f3c2  mov     edx, 13Ch; void *
0x18000f3c7  mov     rcx, [rsp+48h]; this
0x18000f3cc  lea     r8, aCW1SSrcClientL_20; "C:\\__w\\1\\s\\src\\Client\\lib\\wusafe"...
0x18000f3d3  mov     r9d, ebp; char *
0x18000f3d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f3db  mov     eax, ebp
0x18000f3dd  jmp     loc_18000F2E4
0x18000f3e2  mov     edx, esi; unsigned int
0x18000f3e4  mov     rcx, rbx; wchar_t *
0x18000f3e7  call    ?WUPathCchAddBackslash@@YAJPEA_WK@Z; WUPathCchAddBackslash(wchar_t *,ulong)
0x18000f3ec  mov     ebp, eax
0x18000f3ee  test    eax, eax
0x18000f3f0  jns     short loc_18000F3F9
0x18000f3f2  mov     edx, 13Dh
0x18000f3f7  jmp     short loc_18000F3C7
0x18000f3f9  mov     r8, rdi; wchar_t *
0x18000f3fc  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f404  mov     rdx, rsi; unsigned __int64
0x18000f407  mov     rcx, rbx; wchar_t *
0x18000f40a  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f40f  mov     edi, eax
0x18000f411  test    eax, eax
0x18000f413  jns     loc_18000F50C
0x18000f419  mov     edx, 13Eh
0x18000f41e  jmp     loc_18000F343
0x18000f423  mov     eax, 5Ch ; '\'
0x18000f428  cmp     [rdi], ax
0x18000f42b  jnz     loc_18000F4B6
0x18000f431  mov     rcx, rdi; pszPath
0x18000f434  call    cs:__imp_PathIsUNCW
0x18000f43a  test    eax, eax
0x18000f43c  jnz     short loc_18000F4B6
0x18000f43e  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f446  xor     r9d, r9d; wchar_t **
0x18000f449  mov     r8, rbp; wchar_t *
0x18000f44c  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18000f451  mov     rdx, rsi; unsigned __int64
0x18000f454  mov     rcx, rbx; pszDest
0x18000f457  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f45c  mov     ebp, eax
0x18000f45e  test    eax, eax
0x18000f460  jns     short loc_18000F46C
0x18000f462  mov     edx, 146h
0x18000f467  jmp     loc_18000F3C7
0x18000f46c  mov     rcx, rbx; pszPath
0x18000f46f  call    cs:__imp_PathStripToRootW
0x18000f475  mov     edx, esi; unsigned int
0x18000f477  mov     rcx, rbx; wchar_t *
0x18000f47a  call    ?WUPathCchAddBackslash@@YAJPEA_WK@Z; WUPathCchAddBackslash(wchar_t *,ulong)
0x18000f47f  mov     ebp, eax
0x18000f481  test    eax, eax
0x18000f483  jns     short loc_18000F48F
0x18000f485  mov     edx, 14Ch
0x18000f48a  jmp     loc_18000F3C7
0x18000f48f  lea     r8, [rdi+2]; wchar_t *
0x18000f493  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f49b  mov     rdx, rsi; unsigned __int64
0x18000f49e  mov     rcx, rbx; wchar_t *
0x18000f4a1  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f4a6  mov     edi, eax
0x18000f4a8  test    eax, eax
0x18000f4aa  jns     short loc_18000F50C
0x18000f4ac  mov     edx, 14Fh
0x18000f4b1  jmp     loc_18000F343
0x18000f4b6  mov     rdx, rsi; unsigned __int64
0x18000f4b9  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f4c1  xor     r9d, r9d; wchar_t **
0x18000f4c4  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18000f4c9  mov     r8, rdi; wchar_t *
0x18000f4cc  mov     rcx, rbx; pszDest
0x18000f4cf  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f4d4  mov     edi, eax
0x18000f4d6  test    eax, eax
0x18000f4d8  jns     short loc_18000F50C
0x18000f4da  mov     edx, 156h
0x18000f4df  jmp     loc_18000F343
0x18000f4e4  mov     rdx, rsi; unsigned __int64
0x18000f4e7  mov     [rsp+48h+var_20], 1100h; unsigned int
0x18000f4ef  xor     r9d, r9d; wchar_t **
0x18000f4f2  mov     [rsp+48h+var_28], r15; unsigned __int64 *
0x18000f4f7  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18000f4fc  mov     edi, eax
0x18000f4fe  test    eax, eax
0x18000f500  jns     short loc_18000F50C
0x18000f502  mov     edx, 135h
0x18000f507  jmp     loc_18000F343
0x18000f50c  mov     r8, rbx; wchar_t *
0x18000f50f  mov     edx, esi; unsigned int
0x18000f511  mov     rcx, rbx; wchar_t *
0x18000f514  call    ?WUPathCchCanonicalize@@YAJPEA_WKPEB_W@Z; WUPathCchCanonicalize(wchar_t *,ulong,wchar_t const *)
0x18000f519  mov     ebx, eax
0x18000f51b  test    eax, eax
0x18000f51d  jns     loc_18000F2E2
0x18000f523  mov     edx, 15Ah
0x18000f528  jmp     loc_18000F2B1
```
