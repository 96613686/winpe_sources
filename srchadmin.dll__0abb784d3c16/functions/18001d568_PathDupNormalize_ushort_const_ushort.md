# PathDupNormalize(ushort const *,ushort * *)

- ea: `0x18001d568`
- end: `0x18001d951`
- name: `?PathDupNormalize@@YAJPEBGPEAPEAG@Z`
- size: `1001`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `4`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18000d58c`
- `0x18000d78c`
- `0x18000d8f4`
- `0x18000db14`
- `0x18002d3a0`

## callees

- `0x180004fdc`
- `0x180005cc0`
- `0x18000957c`
- `0x18001d568`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001d6f8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001d711`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001d6f8`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001d711`
- `SHLWAPI!UrlIsW` at `0x18001d85b`
- `SHLWAPI!UrlIsW` at `0x18001d85b`
- `SHLWAPI!PathCreateFromUrlW` at `0x18001d87e`
- `SHLWAPI!PathCreateFromUrlW` at `0x18001d8ef`
- `SHLWAPI!PathCreateFromUrlW` at `0x18001d87e`
- `SHLWAPI!PathCreateFromUrlW` at `0x18001d8ef`
- `SHLWAPI!UrlCanonicalizeW` at `0x18001d7d6`
- `SHLWAPI!UrlCanonicalizeW` at `0x18001d811`
- `SHLWAPI!UrlCanonicalizeW` at `0x18001d7d6`
- `SHLWAPI!UrlCanonicalizeW` at `0x18001d811`
- `SHLWAPI!UrlEscapeW` at `0x18001d73a`
- `SHLWAPI!UrlEscapeW` at `0x18001d796`
- `SHLWAPI!UrlEscapeW` at `0x18001d73a`
- `SHLWAPI!UrlEscapeW` at `0x18001d796`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d628`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d66e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d6d9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d628`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d66e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001d6d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d91c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d91c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d89d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d7e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001d89d`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18001d902`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18001d902`

## pseudocode

```c
__int64 __fastcall PathDupNormalize(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v2; // r12
  const WCHAR *v4; // rdi
  __int64 v5; // rsi
  HRESULT v6; // ebx
  WCHAR *v7; // rsi
  char v8; // r14
  HRESULT v9; // eax
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  const WCHAR *v12; // r15
  WCHAR *v13; // rdi
  SIZE_T v14; // rcx
  unsigned __int16 *v15; // rax
  WCHAR *v16; // rdx
  int lpString2; // [rsp+20h] [rbp-49h]
  DWORD pcchEscaped; // [rsp+30h] [rbp-39h] BYREF
  WCHAR pszEscaped[2]; // [rsp+34h] [rbp-35h] BYREF
  DWORD pcchCanonicalized; // [rsp+38h] [rbp-31h] BYREF
  WCHAR pszCanonicalized; // [rsp+3Ch] [rbp-2Dh] BYREF
  DWORD pcchPath; // [rsp+40h] [rbp-29h] BYREF
  WCHAR v24[8]; // [rsp+48h] [rbp-21h] BYREF
  WCHAR String1[12]; // [rsp+58h] [rbp-11h] BYREF
  WCHAR v26[12]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v2 = -1;
  v4 = a1;
  if ( !a1 )
  {
    wcscpy(String1, L"\\\\?\\UNC\\");
LABEL_3:
    wcscpy(v26, L"\\\\?\\Volume{");
LABEL_11:
    v6 = -2147024809;
    v7 = 0;
    wcscpy(v24, L"\\\\?\\");
    v8 = 0;
    goto LABEL_25;
  }
  v5 = -1;
  do
    ++v5;
  while ( a1[v5] );
  wcscpy(String1, L"\\\\?\\UNC\\");
  if ( (int)v5 < 2 || (unsigned int)v5 >= 9 && CompareStringW(0x7Fu, 1u, String1, 8, a1, 8) == 2 )
    goto LABEL_3;
  v6 = 0;
  wcscpy(v26, L"\\\\?\\Volume{");
  if ( (unsigned int)v5 >= 0xC && CompareStringW(0x7Fu, 1u, v26, 11, v4, 11) == 2 )
    goto LABEL_11;
  wcscpy(v24, L"\\\\?\\");
  if ( (unsigned int)v5 >= 5 && CompareStringW(0x7Fu, 1u, v24, 4, v4, 4) == 2 )
    v4 += 4;
  v8 = 0;
  v7 = 0;
  if ( wcsstr(v4, L"\\") && wcsstr(v4, L"file:///") == v4 )
  {
    pszEscaped[0] = 0;
    pcchEscaped = 1;
    v9 = UrlEscapeW(v4, pszEscaped, &pcchEscaped, 0);
    v6 = v9;
    if ( v9 != -2147467261 )
    {
      if ( v9 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x236,
          (unsigned int)"shell\\cpls\\srchadmin\\cpl\\main.cpp",
          (const char *)(unsigned int)v9,
          lpString2);
      return (unsigned int)v6;
    }
    v10 = (WCHAR *)CoTaskMemAlloc(2LL * pcchEscaped);
    v7 = v10;
    if ( v10 )
    {
      v6 = UrlEscapeW(v4, v10, &pcchEscaped, 0);
      if ( v6 < 0 )
      {
        v11 = v7;
LABEL_47:
        CoTaskMemFree(v11);
        return (unsigned int)v6;
      }
      v8 = 1;
    }
    else
    {
      v6 = -2147024882;
    }
  }
LABEL_25:
  pcchCanonicalized = 1;
  v12 = v7;
  if ( !v8 )
    v12 = v4;
  v13 = 0;
  if ( v6 >= 0 )
  {
    if ( UrlCanonicalizeW(v12, &pszCanonicalized, &pcchCanonicalized, 0) == -2147467261 )
    {
      v13 = (WCHAR *)CoTaskMemAlloc(2LL * pcchCanonicalized);
      v6 = v13 == 0 ? 0x8007000E : 0;
      if ( v13 )
        v6 = UrlCanonicalizeW(v12, v13, &pcchCanonicalized, 0);
    }
    else
    {
      v6 = -2147418113;
    }
  }
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v6 >= 0 )
  {
    do
      ++v2;
    while ( v13[v2] );
    if ( v13[v2 - 1] == 42 )
      v13[v2 - 1] = 0;
    if ( !UrlIsW(v13, URLIS_FILEURL) )
    {
      *a2 = v13;
      return (unsigned int)v6;
    }
    pcchEscaped = 1;
    if ( PathCreateFromUrlW(v13, pszEscaped, &pcchEscaped, 0) == -2147467261 )
    {
      v14 = 2LL * (pcchEscaped + 9);
      pcchEscaped += 9;
      v15 = (unsigned __int16 *)CoTaskMemAlloc(v14);
      *a2 = v15;
      v6 = v15 == 0 ? 0x8007000E : 0;
      if ( v15 )
      {
        v6 = StringCchCopyW(v15, pcchEscaped, L"file:///");
        if ( v6 >= 0 )
        {
          v16 = *a2 + 8;
          pcchPath = pcchEscaped - 9;
          v6 = PathCreateFromUrlW(v13, v16, &pcchPath, 0);
          if ( v6 >= 0 )
          {
            v6 = PathCchAddBackslash(*a2, pcchEscaped);
            if ( v6 == 1 )
              v6 = 0;
          }
        }
      }
    }
    else
    {
      v6 = -2147418113;
    }
    v11 = v13;
    goto LABEL_47;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001d568  mov     [rsp-8+arg_10], rbx
0x18001d56d  push    rbp
0x18001d56e  push    rsi
0x18001d56f  push    rdi
0x18001d570  push    r12
0x18001d572  push    r13
0x18001d574  push    r14
0x18001d576  push    r15
0x18001d578  lea     rbp, [rsp-27h]
0x18001d57d  sub     rsp, 90h
0x18001d584  mov     rax, cs:__security_cookie
0x18001d58b  xor     rax, rsp
0x18001d58e  mov     [rbp+57h+var_38], rax
0x18001d592  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001d596  xor     r15d, r15d
0x18001d599  mov     r13, rdx
0x18001d59c  mov     rdi, rcx
0x18001d59f  mov     r14d, 1
0x18001d5a5  test    rcx, rcx
0x18001d5a8  jnz     short loc_18001D5DD
0x18001d5aa  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC\\"
0x18001d5b1  movzx   eax, word ptr cs:aUnc+10h; ""
0x18001d5b8  mov     [rbp+57h+var_58], ax
0x18001d5bc  movups  xmmword ptr [rbp+57h+String1], xmm0
0x18001d5c0  movups  xmm0, xmmword ptr cs:aVolume; "\\\\?\\Volume{"
0x18001d5c7  movsd   xmm1, qword ptr cs:aVolume+10h; "me{"
0x18001d5cf  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001d5d3  movsd   [rbp+57h+var_40], xmm1
0x18001d5d8  jmp     loc_18001D679
0x18001d5dd  mov     rsi, r12
0x18001d5e0  inc     rsi
0x18001d5e3  cmp     [rcx+rsi*2], r15w
0x18001d5e8  jnz     short loc_18001D5E0
0x18001d5ea  movzx   eax, word ptr cs:aUnc+10h; ""
0x18001d5f1  mov     [rbp+57h+var_58], ax
0x18001d5f5  movups  xmm0, xmmword ptr cs:aUnc; "\\\\?\\UNC\\"
0x18001d5fc  movups  xmmword ptr [rbp+57h+String1], xmm0
0x18001d600  cmp     esi, 2
0x18001d603  jl      short loc_18001D5C0
0x18001d605  cmp     esi, 9
0x18001d608  jb      short loc_18001D633
0x18001d60a  mov     r9d, 8; cchCount1
0x18001d610  mov     [rsp+0C0h+cchCount2], 8; cchCount2
0x18001d618  lea     r8, [rbp+57h+String1]; lpString1
0x18001d61c  mov     [rsp+0C0h+lpString2], rdi; lpString2
0x18001d621  mov     edx, r14d; dwCmpFlags
0x18001d624  lea     ecx, [r9+77h]; Locale
0x18001d628  call    cs:__imp_CompareStringW
0x18001d62e  cmp     eax, 2
0x18001d631  jz      short loc_18001D5C0
0x18001d633  movsd   xmm1, qword ptr cs:aVolume+10h; "me{"
0x18001d63b  mov     ebx, r15d
0x18001d63e  movsd   [rbp+57h+var_40], xmm1
0x18001d643  movups  xmm0, xmmword ptr cs:aVolume; "\\\\?\\Volume{"
0x18001d64a  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001d64e  cmp     esi, 0Ch
0x18001d651  jb      short loc_18001D6A1
0x18001d653  mov     r9d, 0Bh; cchCount1
0x18001d659  lea     r8, [rbp+57h+var_50]; lpString1
0x18001d65d  mov     [rsp+0C0h+cchCount2], r9d; cchCount2
0x18001d662  mov     edx, r14d; dwCmpFlags
0x18001d665  mov     [rsp+0C0h+lpString2], rdi; lpString2
0x18001d66a  lea     ecx, [r9+74h]; Locale
0x18001d66e  call    cs:__imp_CompareStringW
0x18001d674  cmp     eax, 2
0x18001d677  jnz     short loc_18001D6A1
0x18001d679  movsd   xmm0, qword ptr cs:asc_180037090; "\\\\?\\"
0x18001d681  mov     ebx, 80070057h
0x18001d686  movzx   eax, word ptr cs:asc_180037090+8; ""
0x18001d68d  mov     rsi, r15
0x18001d690  movsd   qword ptr [rbp+57h+var_78], xmm0
0x18001d695  mov     r14b, r15b
0x18001d698  mov     [rbp+57h+var_70], ax
0x18001d69c  jmp     loc_18001D7AD
0x18001d6a1  movsd   xmm0, qword ptr cs:asc_180037090; "\\\\?\\"
0x18001d6a9  movzx   eax, word ptr cs:asc_180037090+8; ""
0x18001d6b0  movsd   qword ptr [rbp+57h+var_78], xmm0
0x18001d6b5  mov     [rbp+57h+var_70], ax
0x18001d6b9  cmp     esi, 5
0x18001d6bc  jb      short loc_18001D6E8
0x18001d6be  mov     r9d, 4; cchCount1
0x18001d6c4  lea     r8, [rbp+57h+var_78]; lpString1
0x18001d6c8  mov     [rsp+0C0h+cchCount2], r9d; cchCount2
0x18001d6cd  mov     edx, r14d; dwCmpFlags
0x18001d6d0  mov     [rsp+0C0h+lpString2], rdi; int
0x18001d6d5  lea     ecx, [r9+7Bh]; Locale
0x18001d6d9  call    cs:__imp_CompareStringW
0x18001d6df  cmp     eax, 2
0x18001d6e2  jnz     short loc_18001D6E8
0x18001d6e4  add     rdi, 8
0x18001d6e8  lea     rdx, SubStr; "\\"
0x18001d6ef  mov     rcx, rdi; Str
0x18001d6f2  mov     r14b, r15b
0x18001d6f5  mov     rsi, r15
0x18001d6f8  call    cs:__imp_wcsstr
0x18001d6fe  test    rax, rax
0x18001d701  jz      loc_18001D7AD
0x18001d707  lea     rdx, aFile_1; "file:///"
0x18001d70e  mov     rcx, rdi; Str
0x18001d711  call    cs:__imp_wcsstr
0x18001d717  cmp     rax, rdi
0x18001d71a  jnz     loc_18001D7AD
0x18001d720  xor     r9d, r9d; dwFlags
0x18001d723  mov     [rbp+57h+pszEscaped], r15w
0x18001d728  lea     r8, [rbp+57h+pcchEscaped]; pcchEscaped
0x18001d72c  mov     [rbp+57h+pcchEscaped], 1
0x18001d733  lea     rdx, [rbp+57h+pszEscaped]; pszEscaped
0x18001d737  mov     rcx, rdi; pszUrl
0x18001d73a  call    cs:__imp_UrlEscapeW
0x18001d740  mov     ebx, eax
0x18001d742  cmp     eax, 80004003h
0x18001d747  jz      short loc_18001D76E
0x18001d749  test    eax, eax
0x18001d74b  jns     loc_18001D928
0x18001d751  mov     rcx, [rbp+5Fh]; this
0x18001d755  lea     r8, aShellCplsSrcha_1; "shell\\cpls\\srchadmin\\cpl\\main.cpp"
0x18001d75c  mov     r9d, eax; char *
0x18001d75f  mov     edx, 236h; void *
0x18001d764  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d769  jmp     loc_18001D928
0x18001d76e  mov     ecx, [rbp+57h+pcchEscaped]
0x18001d771  add     rcx, rcx; cb
0x18001d774  call    cs:__imp_CoTaskMemAlloc
0x18001d77a  mov     rsi, rax
0x18001d77d  test    rax, rax
0x18001d780  jnz     short loc_18001D789
0x18001d782  mov     ebx, 8007000Eh
0x18001d787  jmp     short loc_18001D7AD
0x18001d789  xor     r9d, r9d; dwFlags
0x18001d78c  lea     r8, [rbp+57h+pcchEscaped]; pcchEscaped
0x18001d790  mov     rdx, rsi; pszEscaped
0x18001d793  mov     rcx, rdi; pszUrl
0x18001d796  call    cs:__imp_UrlEscapeW
0x18001d79c  mov     ebx, eax
0x18001d79e  test    eax, eax
0x18001d7a0  jns     short loc_18001D7AA
0x18001d7a2  mov     rcx, rsi
0x18001d7a5  jmp     loc_18001D91C
0x18001d7aa  mov     r14b, 1
0x18001d7ad  test    r14b, r14b
0x18001d7b0  mov     [rbp+57h+pcchCanonicalized], 1
0x18001d7b7  mov     r15, rsi
0x18001d7ba  cmovz   r15, rdi
0x18001d7be  xor     r14d, r14d
0x18001d7c1  mov     edi, r14d
0x18001d7c4  test    ebx, ebx
0x18001d7c6  js      short loc_18001D820
0x18001d7c8  xor     r9d, r9d; dwFlags
0x18001d7cb  lea     r8, [rbp+57h+pcchCanonicalized]; pcchCanonicalized
0x18001d7cf  lea     rdx, [rbp+57h+pszCanonicalized]; pszCanonicalized
0x18001d7d3  mov     rcx, r15; pszUrl
0x18001d7d6  call    cs:__imp_UrlCanonicalizeW
0x18001d7dc  cmp     eax, 80004003h
0x18001d7e1  jnz     short loc_18001D81B
0x18001d7e3  mov     ecx, [rbp+57h+pcchCanonicalized]
0x18001d7e6  add     rcx, rcx; cb
0x18001d7e9  call    cs:__imp_CoTaskMemAlloc
0x18001d7ef  mov     rdi, rax
0x18001d7f2  neg     rax
0x18001d7f5  sbb     ebx, ebx
0x18001d7f7  not     ebx
0x18001d7f9  and     ebx, 8007000Eh
0x18001d7ff  test    rdi, rdi
0x18001d802  jz      short loc_18001D820
0x18001d804  xor     r9d, r9d; dwFlags
0x18001d807  lea     r8, [rbp+57h+pcchCanonicalized]; pcchCanonicalized
0x18001d80b  mov     rdx, rdi; pszCanonicalized
0x18001d80e  mov     rcx, r15; pszUrl
0x18001d811  call    cs:__imp_UrlCanonicalizeW
0x18001d817  mov     ebx, eax
0x18001d819  jmp     short loc_18001D820
0x18001d81b  mov     ebx, 8000FFFFh
0x18001d820  test    rsi, rsi
0x18001d823  jz      short loc_18001D82E
0x18001d825  mov     rcx, rsi; pv
0x18001d828  call    cs:__imp_CoTaskMemFree
0x18001d82e  test    ebx, ebx
0x18001d830  js      loc_18001D928
0x18001d836  inc     r12
0x18001d839  cmp     [rdi+r12*2], r14w
0x18001d83e  jnz     short loc_18001D836
0x18001d840  mov     eax, 2Ah ; '*'
0x18001d845  cmp     ax, [rdi+r12*2-2]
0x18001d84b  jnz     short loc_18001D853
0x18001d84d  mov     [rdi+r12*2-2], r14w
0x18001d853  mov     edx, 3; UrlIs
0x18001d858  mov     rcx, rdi; pszUrl
0x18001d85b  call    cs:__imp_UrlIsW
0x18001d861  test    eax, eax
0x18001d863  jz      loc_18001D924
0x18001d869  xor     r9d, r9d; dwFlags
0x18001d86c  mov     [rbp+57h+pcchEscaped], 1
0x18001d873  lea     r8, [rbp+57h+pcchEscaped]; pcchPath
0x18001d877  mov     rcx, rdi; pszUrl
0x18001d87a  lea     rdx, [rbp+57h+pszEscaped]; pszPath
0x18001d87e  call    cs:__imp_PathCreateFromUrlW
0x18001d884  cmp     eax, 80004003h
0x18001d889  jnz     loc_18001D914
0x18001d88f  mov     eax, [rbp+57h+pcchEscaped]
0x18001d892  add     eax, 9
0x18001d895  mov     ecx, eax
0x18001d897  add     rcx, rcx; cb
0x18001d89a  mov     [rbp+57h+pcchEscaped], eax
0x18001d89d  call    cs:__imp_CoTaskMemAlloc
0x18001d8a3  mov     rcx, rax
0x18001d8a6  mov     [r13+0], rax
0x18001d8aa  neg     rcx
0x18001d8ad  sbb     ebx, ebx
0x18001d8af  not     ebx
0x18001d8b1  and     ebx, 8007000Eh
0x18001d8b7  test    rax, rax
0x18001d8ba  jz      short loc_18001D919
0x18001d8bc  mov     edx, [rbp+57h+pcchEscaped]; unsigned __int64
0x18001d8bf  lea     r8, aFile_1; "file:///"
0x18001d8c6  mov     rcx, rax; unsigned __int16 *
0x18001d8c9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d8ce  mov     ebx, eax
0x18001d8d0  test    eax, eax
0x18001d8d2  js      short loc_18001D919
0x18001d8d4  mov     eax, [rbp+57h+pcchEscaped]
0x18001d8d7  lea     r8, [rbp+57h+pcchPath]; pcchPath
0x18001d8db  mov     rdx, [r13+0]
0x18001d8df  add     eax, 0FFFFFFF7h
0x18001d8e2  add     rdx, 10h; pszPath
0x18001d8e6  mov     [rbp+57h+pcchPath], eax
0x18001d8e9  xor     r9d, r9d; dwFlags
0x18001d8ec  mov     rcx, rdi; pszUrl
0x18001d8ef  call    cs:__imp_PathCreateFromUrlW
0x18001d8f5  mov     ebx, eax
0x18001d8f7  test    eax, eax
0x18001d8f9  js      short loc_18001D919
0x18001d8fb  mov     edx, [rbp+57h+pcchEscaped]; cchPath
0x18001d8fe  mov     rcx, [r13+0]; pszPath
0x18001d902  call    cs:__imp_PathCchAddBackslash
0x18001d908  mov     ebx, eax
0x18001d90a  cmp     eax, 1
0x18001d90d  jnz     short loc_18001D919
0x18001d90f  mov     ebx, r14d
0x18001d912  jmp     short loc_18001D919
0x18001d914  mov     ebx, 8000FFFFh
0x18001d919  mov     rcx, rdi; pv
0x18001d91c  call    cs:__imp_CoTaskMemFree
0x18001d922  jmp     short loc_18001D928
0x18001d924  mov     [r13+0], rdi
0x18001d928  mov     eax, ebx
0x18001d92a  mov     rcx, [rbp+57h+var_38]
0x18001d92e  xor     rcx, rsp; StackCookie
0x18001d931  call    __security_check_cookie
0x18001d936  mov     rbx, [rsp+0C0h+arg_10]
0x18001d93e  add     rsp, 90h
0x18001d945  pop     r15
0x18001d947  pop     r14
0x18001d949  pop     r13
0x18001d94b  pop     r12
0x18001d94d  pop     rdi
0x18001d94e  pop     rsi
0x18001d94f  pop     rbp
0x18001d950  retn
```
