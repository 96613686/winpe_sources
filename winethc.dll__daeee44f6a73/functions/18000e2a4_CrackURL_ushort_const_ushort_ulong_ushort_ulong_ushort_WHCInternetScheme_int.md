# CrackURL(ushort const *,ushort *,ulong,ushort *,ulong,ushort *,WHCInternetScheme *,int *)

- ea: `0x18000e2a4`
- end: `0x18000e50f`
- name: `?CrackURL@@YAJPEBGPEAGK1K1PEAW4WHCInternetScheme@@PEAH@Z`
- size: `619`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int, unsigned __int16 *, unsigned int, unsigned __int16 *, enum WHCInternetScheme *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800082f0`

## callees

- `0x18000c998`
- `0x18000caac`
- `0x18000e2a4`
- `0x180012d6e`
- `0x180012db0`
- `0x180012e40`

## import_xrefs

- `SHLWAPI!PathIsUNCW` at `0x18000e442`
- `SHLWAPI!PathIsUNCW` at `0x18000e442`
- `WININET!InternetCrackUrlW` at `0x18000e3fe`
- `WININET!InternetCrackUrlW` at `0x18000e3fe`

## string_xrefs

- `0x18000e344`: `www.microsoft.com`

## pseudocode

```c
__int64 __fastcall CrackURL(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        enum WHCInternetScheme *a7,
        int *a8)
{
  __int64 v11; // rax
  unsigned int v12; // r14d
  INTERNET_SCHEME nScheme; // ecx
  int nPort; // edx
  __int32 v15; // ecx
  __int32 v16; // ecx
  __int32 v17; // ecx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  $2B4FDC4BF487E67F052937EE78FAE255 UrlComponents; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPath[2048]; // [rsp+A0h] [rbp-60h] BYREF

  if ( !a1 || !a2 || !a4 || !a6 || !a7 || !a8 )
    return 2147942487LL;
  v11 = -1;
  do
    ++v11;
  while ( a1[v11] );
  if ( !v11 )
  {
    v12 = StringCchCopyW(a4, 0x100u, L"www.microsoft.com");
    if ( (v12 & 0x80000000) == 0 )
    {
      *a6 = 80;
      v19 = 80;
      v12 = StringCchPrintfW(a2, 0x12Bu, L"http://%s:%i/", a4, v19);
      if ( (v12 & 0x80000000) == 0 )
      {
        *(_DWORD *)a7 = 0;
        *a8 = 1;
      }
    }
    return v12;
  }
  *a8 = 0;
  memset_0(&UrlComponents, 0, sizeof(UrlComponents));
  UrlComponents.dwStructSize = 104;
  UrlComponents.lpszHostName = a4;
  UrlComponents.dwHostNameLength = 256;
  memset_0(pszPath, 0, sizeof(pszPath));
  UrlComponents.dwUrlPathLength = 2048;
  UrlComponents.lpszUrlPath = pszPath;
  if ( InternetCrackUrlW(a1, 0, 0x10000000u, &UrlComponents) )
  {
    nScheme = UrlComponents.nScheme;
    v12 = 0;
    nPort = UrlComponents.nPort;
    *a6 = UrlComponents.nPort;
    v15 = nScheme - 1;
    if ( !v15 )
    {
      v22 = nPort;
      StringCchPrintfW(a2, 0x12Bu, L"ftp://%s:%i/", a4, v22);
      *(_DWORD *)a7 = 2;
      return v12;
    }
    v16 = v15 - 2;
    if ( !v16 )
    {
      v21 = nPort;
      StringCchPrintfW(a2, 0x12Bu, L"http://%s:%i/", a4, v21);
      *(_DWORD *)a7 = 0;
      return v12;
    }
    v17 = v16 - 1;
    if ( !v17 )
    {
      v20 = nPort;
      StringCchPrintfW(a2, 0x12Bu, L"https://%s:%i/", a4, v20);
      *(_DWORD *)a7 = 1;
      return v12;
    }
    if ( v17 == 1 && PathIsUNCW(pszPath) )
    {
      StringCchCopyW(a2, 0x12Bu, pszPath);
      *(_DWORD *)a7 = 3;
      return v12;
    }
  }
  return 2147954405LL;
}

```

## disassembly

```asm
0x18000e2a4  mov     [rsp-8+arg_10], rbx
0x18000e2a9  push    rbp
0x18000e2aa  push    rsi
0x18000e2ab  push    rdi
0x18000e2ac  push    r12
0x18000e2ae  push    r13
0x18000e2b0  push    r14
0x18000e2b2  push    r15
0x18000e2b4  lea     rbp, [rsp-0FB0h]
0x18000e2bc  mov     eax, 10B0h
0x18000e2c1  call    _alloca_probe
0x18000e2c6  sub     rsp, rax
0x18000e2c9  mov     rax, cs:__security_cookie
0x18000e2d0  xor     rax, rsp
0x18000e2d3  mov     [rbp+0FE0h+var_40], rax
0x18000e2da  mov     r15, [rbp+0FE0h+arg_28]
0x18000e2e1  xor     r13d, r13d
0x18000e2e4  mov     rbx, [rbp+0FE0h+arg_30]
0x18000e2eb  mov     rdi, r9
0x18000e2ee  mov     r12, [rbp+0FE0h+arg_38]
0x18000e2f5  mov     rsi, rdx
0x18000e2f8  mov     r14, rcx
0x18000e2fb  test    rcx, rcx
0x18000e2fe  jz      loc_18000E4DF
0x18000e304  test    rdx, rdx
0x18000e307  jz      loc_18000E4DF
0x18000e30d  test    r9, r9
0x18000e310  jz      loc_18000E4DF
0x18000e316  test    r15, r15
0x18000e319  jz      loc_18000E4DF
0x18000e31f  test    rbx, rbx
0x18000e322  jz      loc_18000E4DF
0x18000e328  test    r12, r12
0x18000e32b  jz      loc_18000E4DF
0x18000e331  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e335  inc     rax
0x18000e338  cmp     [rcx+rax*2], r13w
0x18000e33d  jnz     short loc_18000E335
0x18000e33f  test    rax, rax
0x18000e342  jnz     short loc_18000E3A2
0x18000e344  lea     r8, aWwwMicrosoftCo; "www.microsoft.com"
0x18000e34b  mov     edx, 100h; unsigned __int64
0x18000e350  mov     rcx, rdi; unsigned __int16 *
0x18000e353  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e358  mov     r14d, eax
0x18000e35b  test    eax, eax
0x18000e35d  js      loc_18000E4D3
0x18000e363  mov     eax, 50h ; 'P'
0x18000e368  lea     r8, aHttpSI; "http://%s:%i/"
0x18000e36f  mov     r9, rdi
0x18000e372  mov     [r15], ax
0x18000e376  mov     edx, 12Bh; unsigned __int64
0x18000e37b  mov     [rsp+10E0h+var_10C0], eax
0x18000e37f  mov     rcx, rsi; unsigned __int16 *
0x18000e382  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e387  mov     r14d, eax
0x18000e38a  test    eax, eax
0x18000e38c  js      loc_18000E4D3
0x18000e392  mov     [rbx], r13d
0x18000e395  mov     dword ptr [r12], 1
0x18000e39d  jmp     loc_18000E4D3
0x18000e3a2  mov     [r12], r13d
0x18000e3a6  lea     rcx, [rsp+10E0h+UrlComponents]; void *
0x18000e3ab  mov     r12d, 68h ; 'h'
0x18000e3b1  xor     edx, edx; Val
0x18000e3b3  mov     r8d, r12d; Size
0x18000e3b6  call    memset_0
0x18000e3bb  xor     edx, edx; Val
0x18000e3bd  mov     [rsp+10E0h+UrlComponents.dwStructSize], r12d
0x18000e3c2  mov     r8d, 1000h; Size
0x18000e3c8  mov     [rsp+10E0h+UrlComponents.lpszHostName], rdi
0x18000e3cd  lea     rcx, [rbp+0FE0h+pszPath]; void *
0x18000e3d1  mov     [rsp+10E0h+UrlComponents.dwHostNameLength], 100h
0x18000e3d9  call    memset_0
0x18000e3de  lea     rax, [rbp+0FE0h+pszPath]
0x18000e3e2  mov     [rbp+0FE0h+UrlComponents.dwUrlPathLength], 800h
0x18000e3e9  lea     r9, [rsp+10E0h+UrlComponents]; lpUrlComponents
0x18000e3ee  mov     [rsp+10E0h+UrlComponents.lpszUrlPath], rax
0x18000e3f3  xor     edx, edx; dwUrlLength
0x18000e3f5  mov     r8d, 10000000h; dwFlags
0x18000e3fb  mov     rcx, r14; lpszUrl
0x18000e3fe  call    cs:__imp_InternetCrackUrlW
0x18000e405  nop     dword ptr [rax+rax+00h]
0x18000e40a  test    eax, eax
0x18000e40c  jz      loc_18000E4D8
0x18000e412  mov     ecx, [rsp+10E0h+UrlComponents.nScheme]
0x18000e416  mov     r14d, r13d
0x18000e419  movzx   edx, [rsp+10E0h+UrlComponents.nPort]
0x18000e41e  mov     [r15], dx
0x18000e422  sub     ecx, 1
0x18000e425  jz      loc_18000E4B2
0x18000e42b  sub     ecx, 2
0x18000e42e  jz      short loc_18000E492
0x18000e430  sub     ecx, 1
0x18000e433  jz      short loc_18000E46F
0x18000e435  cmp     ecx, 1
0x18000e438  jnz     loc_18000E4D8
0x18000e43e  lea     rcx, [rbp+0FE0h+pszPath]; pszPath
0x18000e442  call    cs:__imp_PathIsUNCW
0x18000e449  nop     dword ptr [rax+rax+00h]
0x18000e44e  test    eax, eax
0x18000e450  jz      loc_18000E4D8
0x18000e456  lea     r8, [rbp+0FE0h+pszPath]; unsigned __int16 *
0x18000e45a  mov     edx, 12Bh; unsigned __int64
0x18000e45f  mov     rcx, rsi; unsigned __int16 *
0x18000e462  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e467  mov     dword ptr [rbx], 3
0x18000e46d  jmp     short loc_18000E4D3
0x18000e46f  mov     [rsp+10E0h+var_10C0], edx
0x18000e473  lea     r8, aHttpsSI; "https://%s:%i/"
0x18000e47a  mov     edx, 12Bh; unsigned __int64
0x18000e47f  mov     r9, rdi
0x18000e482  mov     rcx, rsi; unsigned __int16 *
0x18000e485  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e48a  mov     dword ptr [rbx], 1
0x18000e490  jmp     short loc_18000E4D3
0x18000e492  mov     [rsp+10E0h+var_10C0], edx
0x18000e496  lea     r8, aHttpSI; "http://%s:%i/"
0x18000e49d  mov     edx, 12Bh; unsigned __int64
0x18000e4a2  mov     r9, rdi
0x18000e4a5  mov     rcx, rsi; unsigned __int16 *
0x18000e4a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e4ad  mov     [rbx], r13d
0x18000e4b0  jmp     short loc_18000E4D3
0x18000e4b2  mov     [rsp+10E0h+var_10C0], edx
0x18000e4b6  lea     r8, aFtpSI; "ftp://%s:%i/"
0x18000e4bd  mov     edx, 12Bh; unsigned __int64
0x18000e4c2  mov     r9, rdi
0x18000e4c5  mov     rcx, rsi; unsigned __int16 *
0x18000e4c8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000e4cd  mov     dword ptr [rbx], 2
0x18000e4d3  mov     eax, r14d
0x18000e4d6  jmp     short loc_18000E4E4
0x18000e4d8  mov     eax, 80072EE5h
0x18000e4dd  jmp     short loc_18000E4E4
0x18000e4df  mov     eax, 80070057h
0x18000e4e4  mov     rcx, [rbp+0FE0h+var_40]
0x18000e4eb  xor     rcx, rsp; StackCookie
0x18000e4ee  call    __security_check_cookie
0x18000e4f3  mov     rbx, [rsp+10E0h+arg_10]
0x18000e4fb  add     rsp, 10B0h
0x18000e502  pop     r15
0x18000e504  pop     r14
0x18000e506  pop     r13
0x18000e508  pop     r12
0x18000e50a  pop     rdi
0x18000e50b  pop     rsi
0x18000e50c  pop     rbp
0x18000e50d  retn
```
