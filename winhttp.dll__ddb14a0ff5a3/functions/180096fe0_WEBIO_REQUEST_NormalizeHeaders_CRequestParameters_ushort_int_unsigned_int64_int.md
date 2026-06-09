# WEBIO_REQUEST::_NormalizeHeaders(CRequestParameters *,ushort *,int,unsigned __int64,int)

- ea: `0x180096fe0`
- end: `0x18009748c`
- name: `?_NormalizeHeaders@WEBIO_REQUEST@@AEAAKPEAVCRequestParameters@@PEAGH_KH@Z`
- size: `1196`
- prototype: `__int64 __fastcall(WEBIO_REQUEST *this, LPCSTR *, unsigned __int16 *, int, unsigned __int64, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18002d250`

## callees

- `0x180029d50`
- `0x18002aac4`
- `0x18004aa40`
- `0x18008a2b8`
- `0x18008da14`
- `0x180096fe0`
- `0x1800a1d10`
- `0x1800cf008`
- `0x1800db6b0`
- `0x1800dbae4`
- `0x1800dc054`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180097266`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180097281`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180097307`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180097266`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180097281`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpNICA` at `0x180097307`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800972af`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800972df`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18009733a`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800972af`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800972df`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x18009733a`

## pseudocode

```c
__int64 __fastcall WEBIO_REQUEST::_NormalizeHeaders(
        WEBIO_REQUEST *this,
        LPCSTR *a2,
        unsigned __int16 *a3,
        int a4,
        unsigned __int64 a5,
        int a6)
{
  unsigned int v6; // ebx
  unsigned int v9; // ebp
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // r15d
  bool v13; // zf
  const CHAR *v14; // rcx
  unsigned __int16 v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // eax
  PCNZCH lpString2; // [rsp+20h] [rbp-78h]
  size_t pcbRemaining[2]; // [rsp+40h] [rbp-58h] BYREF
  char pszDest[8]; // [rsp+50h] [rbp-48h] BYREF
  int v22; // [rsp+58h] [rbp-40h]

  v6 = 0;
  if ( !a3 || (v9 = 69, a4 == 2) )
    v9 = 23;
  if ( (*((_DWORD *)this + 59) & 0x400000) != 0 )
  {
    *(_QWORD *)pszDest = "Close";
    v22 = 5;
    if ( (unsigned int)CWebIORequestHeadersShim::FindHeaderWithToken(a2, 23, pszDest) )
    {
      if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
        WPP_SF_(769, 59, WPP_e088ccaf4b453557444769b982cec156_Traceguids);
      *((_DWORD *)this + 59) &= ~0x400000u;
    }
    else if ( a6 )
    {
      v6 = CWebIORequestHeadersShim::SetHeader((CWebIORequestHeadersShim *)a2, v9, "Keep-Alive", 0xAu);
      if ( v6 )
        return v6;
    }
  }
  if ( (*((_DWORD *)this + 59) & 0x400000) != 0
    || (*(_QWORD *)pszDest = "Close",
        v22 = 5,
        (unsigned int)CWebIORequestHeadersShim::FindHeaderWithToken(a2, 23, pszDest))
    || *((_DWORD *)a2 + 22) <= 1u && (*((_DWORD *)a2 + 22) != 1 || !*((_DWORD *)a2 + 23))
    || !a6
    || (v6 = CWebIORequestHeadersShim::SetHeader((CWebIORequestHeadersShim *)a2, 0x17u, "Close", 5u)) == 0 )
  {
    if ( (unsigned int)CWebIORequestHeadersShim::IsHeaderPresent((CWebIORequestHeadersShim *)a2, 0x3Fu) )
    {
      v22 = 8;
      *(_QWORD *)pszDest = "identity";
      if ( !(unsigned int)CWebIORequestHeadersShim::FindHeaderWithToken(a2, 63, pszDest) )
      {
        if ( (unsigned int)CWebIORequestHeadersShim::IsHeaderPresent((CWebIORequestHeadersShim *)a2, 5u) )
        {
          if ( (xmmword_180107A50 & 2) != 0 )
          {
            v10 = 60;
            v11 = 513;
LABEL_33:
            WPP_SF_(v11, v10, WPP_e088ccaf4b453557444769b982cec156_Traceguids);
          }
          return 87;
        }
        if ( *((_DWORD *)this + 58) == 3 )
        {
          if ( (xmmword_180107A60 & 2) == 0 )
            return 87;
          v10 = 61;
LABEL_32:
          v11 = 1025;
          goto LABEL_33;
        }
        *((_DWORD *)this + 58) = 2;
        if ( (xmmword_180107A60 & 2) != 0 )
          WPP_SF_(1025, 62, WPP_e088ccaf4b453557444769b982cec156_Traceguids);
        return v6;
      }
    }
    if ( (unsigned int)CWebIORequestHeadersShim::IsHeaderPresent((CWebIORequestHeadersShim *)a2, 5u) )
    {
      if ( *((_DWORD *)this + 58) != 3 )
      {
        *((_QWORD *)this + 27) = a5;
        *((_QWORD *)this + 28) = a5;
        *((_DWORD *)this + 58) = 1;
        return v6;
      }
      if ( (xmmword_180107A60 & 2) == 0 )
        return 87;
      v10 = 63;
      goto LABEL_32;
    }
    v12 = 0;
    if ( g_fKirHttpBugFix2605 )
    {
      if ( StrCmpNICA(a2[12], "PUT", 3) )
      {
        v13 = StrCmpNICA(a2[12], "POST", 4) == 0;
        goto LABEL_41;
      }
    }
    else if ( CompareStringA(0x7Fu, 1u, a2[12], -1, "PUT", -1) != 2 )
    {
      v13 = CompareStringA(0x7Fu, 1u, a2[12], -1, "POST", -1) == 2;
LABEL_41:
      if ( !v13 )
        goto LABEL_43;
    }
    v12 = 1;
LABEL_43:
    v14 = a2[12];
    if ( g_fKirHttpBugFix2605 )
    {
      if ( !StrCmpNICA(v14, "BITS_POST", 9) )
        v12 = 1;
    }
    else if ( CompareStringA(0x7Fu, 1u, v14, -1, "BITS_POST", -1) == 2 )
    {
      v12 = 1;
    }
    if ( (a5 || v12) && *((_DWORD *)this + 58) != 3 )
    {
      pcbRemaining[0] = 0;
      if ( StringCbPrintfExA(pszDest, 0xBu, 0, pcbRemaining, 0, "%u", a5) < 0 )
        return 111;
      v15 = 11 - LOWORD(pcbRemaining[0]);
      *((_DWORD *)this + 58) = 1;
      v16 = CWebIORequestHeadersShim::SetHeader((CWebIORequestHeadersShim *)a2, 5u, pszDest, v15);
      v6 = v16;
      if ( v16 )
      {
        if ( g_fKirHttpBugFix2605 )
        {
          if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
            WPP_SF_d(769, 64, WPP_e088ccaf4b453557444769b982cec156_Traceguids, v16, lpString2);
        }
        else if ( (BYTE8(xmmword_180107A50) & 2) != 0 )
        {
          v17 = (unsigned int)InternetMapError(v16);
          WPP_SF_sd(769, 65, (unsigned int)WPP_e088ccaf4b453557444769b982cec156_Traceguids, v17, v6);
        }
        return v6;
      }
      if ( (xmmword_180107A60 & 2) != 0 )
        WPP_SF_s(1025, 66, WPP_e088ccaf4b453557444769b982cec156_Traceguids, pszDest);
    }
    *((_QWORD *)this + 27) = a5;
    *((_QWORD *)this + 28) = a5;
  }
  return v6;
}

```

## disassembly

```asm
0x180096fe0  mov     [rsp+arg_10], rbx
0x180096fe5  push    rbp
0x180096fe6  push    rsi
0x180096fe7  push    rdi
0x180096fe8  push    r14
0x180096fea  push    r15
0x180096fec  sub     rsp, 70h
0x180096ff0  mov     rax, cs:__security_cookie
0x180096ff7  xor     rax, rsp
0x180096ffa  mov     [rsp+98h+var_38], rax
0x180096fff  xor     ebx, ebx
0x180097001  mov     rsi, rdx
0x180097004  mov     rdi, rcx
0x180097007  test    r8, r8
0x18009700a  jz      short loc_180097017
0x18009700c  mov     ebp, 45h ; 'E'
0x180097011  cmp     r9d, 2
0x180097015  jnz     short loc_18009701C
0x180097017  mov     ebp, 17h
0x18009701c  test    dword ptr [rcx+0ECh], 400000h
0x180097026  lea     r15, aClose; "Close"
0x18009702d  mov     r14d, [rsp+98h+arg_28]
0x180097035  jz      short loc_1800970B3
0x180097037  mov     eax, [rsp+98h+var_3C]
0x18009703b  lea     r8, [rsp+98h+pszDest]
0x180097040  mov     edx, 17h
0x180097045  mov     [rsp+98h+var_3C], eax
0x180097049  mov     rcx, rsi
0x18009704c  mov     qword ptr [rsp+98h+pszDest], r15
0x180097051  mov     [rsp+98h+var_40], 5
0x180097059  call    ?FindHeaderWithToken@CWebIORequestHeadersShim@@QEBAHKU?$string@D@@@Z; CWebIORequestHeadersShim::FindHeaderWithToken(ulong,string<char>)
0x18009705e  test    eax, eax
0x180097060  jz      short loc_18009708D
0x180097062  test    byte ptr cs:xmmword_180107A50+8, 2
0x180097069  jz      short loc_180097081
0x18009706b  mov     edx, 3Bh ; ';'
0x180097070  lea     r8, WPP_e088ccaf4b453557444769b982cec156_Traceguids
0x180097077  mov     ecx, 301h
0x18009707c  call    WPP_SF_
0x180097081  and     dword ptr [rdi+0ECh], 0FFBFFFFFh
0x18009708b  jmp     short loc_1800970B3
0x18009708d  test    r14d, r14d
0x180097090  jz      short loc_1800970B3
0x180097092  mov     r9d, 0Ah; unsigned __int16
0x180097098  lea     r8, aKeepAlive; "Keep-Alive"
0x18009709f  mov     edx, ebp; unsigned int
0x1800970a1  mov     rcx, rsi; this
0x1800970a4  call    ?SetHeader@CWebIORequestHeadersShim@@QEAAKKPEBDG@Z; CWebIORequestHeadersShim::SetHeader(ulong,char const *,ushort)
0x1800970a9  mov     ebx, eax
0x1800970ab  test    eax, eax
0x1800970ad  jnz     loc_180097469
0x1800970b3  test    dword ptr [rdi+0ECh], 400000h
0x1800970bd  jnz     short loc_18009711D
0x1800970bf  mov     ecx, [rsp+98h+var_3C]
0x1800970c3  lea     r8, [rsp+98h+pszDest]
0x1800970c8  mov     [rsp+98h+var_3C], ecx
0x1800970cc  mov     edx, 17h
0x1800970d1  mov     rcx, rsi
0x1800970d4  mov     qword ptr [rsp+98h+pszDest], r15
0x1800970d9  mov     [rsp+98h+var_40], 5
0x1800970e1  call    ?FindHeaderWithToken@CWebIORequestHeadersShim@@QEBAHKU?$string@D@@@Z; CWebIORequestHeadersShim::FindHeaderWithToken(ulong,string<char>)
0x1800970e6  test    eax, eax
0x1800970e8  jnz     short loc_18009711D
0x1800970ea  cmp     dword ptr [rsi+58h], 1
0x1800970ee  ja      short loc_1800970F8
0x1800970f0  jnz     short loc_18009711D
0x1800970f2  cmp     dword ptr [rsi+5Ch], 1
0x1800970f6  jb      short loc_18009711D
0x1800970f8  test    r14d, r14d
0x1800970fb  jz      short loc_18009711D
0x1800970fd  mov     r9d, 5; unsigned __int16
0x180097103  mov     r8, r15; char *
0x180097106  mov     edx, 17h; unsigned int
0x18009710b  mov     rcx, rsi; this
0x18009710e  call    ?SetHeader@CWebIORequestHeadersShim@@QEAAKKPEBDG@Z; CWebIORequestHeadersShim::SetHeader(ulong,char const *,ushort)
0x180097113  mov     ebx, eax
0x180097115  test    eax, eax
0x180097117  jnz     loc_180097469
0x18009711d  mov     edx, 3Fh ; '?'; unsigned int
0x180097122  mov     rcx, rsi; this
0x180097125  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x18009712a  test    eax, eax
0x18009712c  jz      loc_1800971D9
0x180097132  lea     rax, aIdentity; "identity"
0x180097139  mov     [rsp+98h+var_40], 8
0x180097141  mov     qword ptr [rsp+98h+pszDest], rax
0x180097146  lea     r8, [rsp+98h+pszDest]
0x18009714b  mov     eax, [rsp+98h+var_3C]
0x18009714f  mov     edx, 3Fh ; '?'
0x180097154  mov     rcx, rsi
0x180097157  mov     [rsp+98h+var_3C], eax
0x18009715b  call    ?FindHeaderWithToken@CWebIORequestHeadersShim@@QEBAHKU?$string@D@@@Z; CWebIORequestHeadersShim::FindHeaderWithToken(ulong,string<char>)
0x180097160  test    eax, eax
0x180097162  jnz     short loc_1800971D9
0x180097164  mov     edx, 5; unsigned int
0x180097169  mov     rcx, rsi; this
0x18009716c  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x180097171  test    eax, eax
0x180097173  jz      short loc_18009718E
0x180097175  test    byte ptr cs:xmmword_180107A50, 2
0x18009717c  jz      loc_180097212
0x180097182  mov     edx, 3Ch ; '<'
0x180097187  mov     ecx, 201h
0x18009718c  jmp     short loc_180097206
0x18009718e  cmp     dword ptr [rdi+0E8h], 3
0x180097195  jnz     short loc_1800971A7
0x180097197  test    byte ptr cs:xmmword_180107A60, 2
0x18009719e  jz      short loc_180097212
0x1800971a0  mov     edx, 3Dh ; '='
0x1800971a5  jmp     short loc_180097201
0x1800971a7  mov     dword ptr [rdi+0E8h], 2
0x1800971b1  test    byte ptr cs:xmmword_180107A60, 2
0x1800971b8  jz      loc_180097469
0x1800971be  mov     edx, 3Eh ; '>'
0x1800971c3  lea     r8, WPP_e088ccaf4b453557444769b982cec156_Traceguids
0x1800971ca  mov     ecx, 401h
0x1800971cf  call    WPP_SF_
0x1800971d4  jmp     loc_180097469
0x1800971d9  mov     edx, 5; unsigned int
0x1800971de  mov     rcx, rsi; this
0x1800971e1  call    ?IsHeaderPresent@CWebIORequestHeadersShim@@QEAAHK@Z; CWebIORequestHeadersShim::IsHeaderPresent(ulong)
0x1800971e6  test    eax, eax
0x1800971e8  jz      short loc_180097241
0x1800971ea  cmp     dword ptr [rdi+0E8h], 3
0x1800971f1  jnz     short loc_18009721C
0x1800971f3  test    byte ptr cs:xmmword_180107A60, 2
0x1800971fa  jz      short loc_180097212
0x1800971fc  mov     edx, 3Fh ; '?'
0x180097201  mov     ecx, 401h
0x180097206  lea     r8, WPP_e088ccaf4b453557444769b982cec156_Traceguids
0x18009720d  call    WPP_SF_
0x180097212  mov     ebx, 57h ; 'W'
0x180097217  jmp     loc_180097469
0x18009721c  mov     rax, [rsp+98h+arg_20]
0x180097224  mov     [rdi+0D8h], rax
0x18009722b  mov     [rdi+0E0h], rax
0x180097232  mov     dword ptr [rdi+0E8h], 1
0x18009723c  jmp     loc_180097469
0x180097241  mov     rax, [rsi+60h]
0x180097245  xor     r15d, r15d
0x180097248  cmp     cs:g_fKirHttpBugFix2605, r15b
0x18009724f  mov     ebp, 1
0x180097254  jz      short loc_18009728B
0x180097256  mov     r8d, 3; nChar
0x18009725c  lea     rdx, aPut; "PUT"
0x180097263  mov     rcx, rax; pszStr1
0x180097266  call    cs:__imp_StrCmpNICA
0x18009726c  test    eax, eax
0x18009726e  jz      short loc_1800972EA
0x180097270  mov     rcx, [rsi+60h]; pszStr1
0x180097274  lea     rdx, aPost; "POST"
0x18009727b  mov     r8d, 4; nChar
0x180097281  call    cs:__imp_StrCmpNICA
0x180097287  test    eax, eax
0x180097289  jmp     short loc_1800972E8
0x18009728b  lea     rcx, aPut; "PUT"
0x180097292  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x18009729a  mov     [rsp+98h+lpString2], rcx; lpString2
0x18009729f  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800972a5  mov     ecx, 7Fh; Locale
0x1800972aa  mov     r8, rax; lpString1
0x1800972ad  mov     edx, ebp; dwCmpFlags
0x1800972af  call    cs:__imp_CompareStringA
0x1800972b5  cmp     eax, 2
0x1800972b8  jz      short loc_1800972EA
0x1800972ba  mov     r8, [rsi+60h]; lpString1
0x1800972be  lea     rax, aPost; "POST"
0x1800972c5  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800972cd  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800972d3  mov     edx, ebp; dwCmpFlags
0x1800972d5  mov     [rsp+98h+lpString2], rax; lpString2
0x1800972da  mov     ecx, 7Fh; Locale
0x1800972df  call    cs:__imp_CompareStringA
0x1800972e5  cmp     eax, 2
0x1800972e8  jnz     short loc_1800972ED
0x1800972ea  mov     r15d, ebp
0x1800972ed  cmp     cs:g_fKirHttpBugFix2605, 0
0x1800972f4  mov     rcx, [rsi+60h]; pszStr1
0x1800972f8  jz      short loc_180097316
0x1800972fa  mov     r8d, 9; nChar
0x180097300  lea     rdx, aBitsPost; "BITS_POST"
0x180097307  call    cs:__imp_StrCmpNICA
0x18009730d  test    eax, eax
0x18009730f  jnz     short loc_180097347
0x180097311  mov     r15d, ebp
0x180097314  jmp     short loc_180097347
0x180097316  lea     rax, aBitsPost; "BITS_POST"
0x18009731d  mov     [rsp+98h+cchCount2], 0FFFFFFFFh; cchCount2
0x180097325  mov     r8, rcx; lpString1
0x180097328  mov     [rsp+98h+lpString2], rax; lpString2
0x18009732d  mov     ecx, 7Fh; Locale
0x180097332  mov     r9d, 0FFFFFFFFh; cchCount1
0x180097338  mov     edx, ebp; dwCmpFlags
0x18009733a  call    cs:__imp_CompareStringA
0x180097340  cmp     eax, 2
0x180097343  cmovz   r15d, ebp
0x180097347  mov     r14, [rsp+98h+arg_20]
0x18009734f  test    r14, r14
0x180097352  jnz     short loc_18009735D
0x180097354  test    r15d, r15d
0x180097357  jz      loc_18009745B
0x18009735d  cmp     dword ptr [rdi+0E8h], 3
0x180097364  jz      loc_18009745B
0x18009736a  lea     rax, aU_0; "%u"
0x180097371  mov     [rsp+98h+var_68], r14d
0x180097376  mov     qword ptr [rsp+98h+cchCount2], rax; pszFormat
0x18009737b  lea     r9, [rsp+98h+pcbRemaining]; pcbRemaining
0x180097380  mov     ebx, 0Bh
0x180097385  mov     [rsp+98h+lpString2], 0; dwFlags
0x18009738e  mov     edx, ebx; cbDest
0x180097390  mov     [rsp+98h+pcbRemaining], 0
0x180097399  xor     r8d, r8d; ppszDestEnd
0x18009739c  lea     rcx, [rsp+98h+pszDest]; pszDest
0x1800973a1  call    StringCbPrintfExA
0x1800973a6  test    eax, eax
0x1800973a8  jns     short loc_1800973B4
0x1800973aa  mov     ebx, 6Fh ; 'o'
0x1800973af  jmp     loc_180097469
0x1800973b4  sub     bx, word ptr [rsp+98h+pcbRemaining]
0x1800973b9  lea     r8, [rsp+98h+pszDest]; char *
0x1800973be  movzx   r9d, bx; unsigned __int16
0x1800973c2  mov     [rdi+0E8h], ebp
0x1800973c8  mov     edx, 5; unsigned int
0x1800973cd  mov     rcx, rsi; this
0x1800973d0  call    ?SetHeader@CWebIORequestHeadersShim@@QEAAKKPEBDG@Z; CWebIORequestHeadersShim::SetHeader(ulong,char const *,ushort)
0x1800973d5  mov     ebx, eax
0x1800973d7  test    eax, eax
0x1800973d9  jz      short loc_180097437
0x1800973db  cmp     cs:g_fKirHttpBugFix2605, 0
0x1800973e2  jz      short loc_180097408
0x1800973e4  test    byte ptr cs:xmmword_180107A50+8, 2
0x1800973eb  jz      short loc_180097469
0x1800973ed  mov     edx, 40h ; '@'
0x1800973f2  lea     r8, WPP_e088ccaf4b453557444769b982cec156_Traceguids
0x1800973f9  mov     ecx, 301h
0x1800973fe  mov     r9d, eax
0x180097401  call    WPP_SF_d
0x180097406  jmp     short loc_180097469
0x180097408  test    byte ptr cs:xmmword_180107A50+8, 2
0x18009740f  jz      short loc_180097469
0x180097411  mov     ecx, ebx; unsigned int
0x180097413  call    ?InternetMapError@@YAPEADK@Z; InternetMapError(ulong)
0x180097418  mov     r9, rax
0x18009741b  mov     dword ptr [rsp+98h+lpString2], ebx
0x18009741f  mov     edx, 41h ; 'A'
0x180097424  lea     r8, WPP_e088ccaf4b453557444769b982cec156_Traceguids
0x18009742b  mov     ecx, 301h
0x180097430  call    WPP_SF_sd
0x180097435  jmp     short loc_180097469
0x180097437  test    byte ptr cs:xmmword_180107A60, 2
0x18009743e  jz      short loc_18009745B
0x180097440  mov     edx, 42h ; 'B'
0x180097445  lea     r9, [rsp+98h+pszDest]
0x18009744a  mov     ecx, 401h
0x18009744f  lea     r8, WPP_e088ccaf4b453557444769b982cec156_Traceguids
0x180097456  call    WPP_SF_s
0x18009745b  mov     [rdi+0D8h], r14
0x180097462  mov     [rdi+0E0h], r14
0x180097469  mov     eax, ebx
0x18009746b  mov     rcx, [rsp+98h+var_38]
0x180097470  xor     rcx, rsp; StackCookie
0x180097473  call    __security_check_cookie
0x180097478  mov     rbx, [rsp+98h+arg_10]
0x180097480  add     rsp, 70h
0x180097484  pop     r15
0x180097486  pop     r14
0x180097488  pop     rdi
0x180097489  pop     rsi
0x18009748a  pop     rbp
0x18009748b  retn
```
