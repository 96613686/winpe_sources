# BINDING_TABLE::TranslateBindingStringToUrlPrefix(ushort const *,ushort const *,ulong,STRU *,STRU *)

- ea: `0x1800115b8`
- end: `0x180011d3e`
- name: `?TranslateBindingStringToUrlPrefix@BINDING_TABLE@@AEAAJPEBG0KPEAVSTRU@@1@Z`
- size: `1926`
- prototype: `int(BINDING_TABLE *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, struct STRU *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800108c0`

## callees

- `0x1800115b8`
- `0x180014514`
- `0x1800160a0`

## import_xrefs

- `msvcrt!wcstoul` at `0x18001179d`
- `msvcrt!wcstoul` at `0x180011994`
- `msvcrt!wcstoul` at `0x18001179d`
- `msvcrt!wcstoul` at `0x180011994`
- `msvcrt!wcschr` at `0x18001164a`
- `msvcrt!wcschr` at `0x180011662`
- `msvcrt!wcschr` at `0x1800116c4`
- `msvcrt!wcschr` at `0x18001164a`
- `msvcrt!wcschr` at `0x180011662`
- `msvcrt!wcschr` at `0x1800116c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011805`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011805`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x180011a7b`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x180011ac5`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x180011a7b`
- `api-ms-win-core-normalization-l1-1-0!IdnToNameprepUnicode` at `0x180011ac5`
- `iisutil!PuDbgPrintError` at `0x18001172b`
- `iisutil!PuDbgPrintError` at `0x1800118ca`
- `iisutil!PuDbgPrintError` at `0x180011937`
- `iisutil!PuDbgPrintError` at `0x18001172b`
- `iisutil!PuDbgPrintError` at `0x1800118ca`
- `iisutil!PuDbgPrintError` at `0x180011937`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011b46`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180011b46`
- `iisutil!PuDbgPrint` at `0x180011d1f`
- `iisutil!PuDbgPrint` at `0x180011d1f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011ce8`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180011ce8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011ab0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011adc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011b3a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011ab0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011adc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180011b3a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011690`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011d2e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011690`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180011d2e`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180011607`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180011607`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180011aa2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180011aa2`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800119f0`
- `iisutil!?Reset@STRU@@QEAAXXZ` at `0x1800119f0`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011a90`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180011a90`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011a1c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011b6f`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011bb3`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011bf8`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011c5a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011c97`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011a1c`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011b6f`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011bb3`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011bf8`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011c5a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180011c97`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011a01`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180011a01`

## string_xrefs

- `0x180011724`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x1800118b5`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x18001190d`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`
- `0x180011d01`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dt\binding_table.cxx`

## pseudocode

```c
__int64 __fastcall BINDING_TABLE::TranslateBindingStringToUrlPrefix(
        BINDING_TABLE *this,
        wchar_t *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        struct STRU *a5,
        struct STRU *a6)
{
  const unsigned __int16 *v7; // r13
  int v9; // edi
  const wchar_t *v10; // rcx
  __int64 v11; // r12
  wchar_t *v12; // rax
  const wchar_t *v13; // rsi
  wchar_t v14; // cx
  signed int v15; // ebx
  wchar_t *v17; // rax
  __int64 v18; // rcx
  const char *v19; // rax
  __int64 v20; // r8
  int v21; // edi
  int v22; // eax
  int v23; // esi
  wchar_t *v24; // r9
  unsigned int v25; // eax
  signed int LastError; // eax
  unsigned int i; // r8d
  int v28; // edx
  unsigned int v29; // eax
  _WORD *v30; // rdi
  const unsigned __int16 *v31; // rsi
  STRU *v32; // rbx
  __int64 v33; // rax
  int v34; // r12d
  int v35; // eax
  unsigned int cchNameprepChar; // ebx
  WCHAR *v37; // rax
  int v38; // ebx
  unsigned __int16 *Ptr; // rax
  unsigned int v40; // r8d
  unsigned int v41; // ebx
  unsigned __int16 *v42; // r9
  int v43; // r8d
  const unsigned __int16 *v44; // rax
  int v45; // eax
  unsigned int v46; // r8d
  const unsigned __int16 *v47; // rdx
  const wchar_t *Str; // rax
  int v49; // [rsp+40h] [rbp-59h]
  int v50; // [rsp+44h] [rbp-55h]
  wchar_t *EndPtr; // [rsp+48h] [rbp-51h] BYREF
  unsigned int v52; // [rsp+50h] [rbp-49h]
  const unsigned __int16 *v53; // [rsp+58h] [rbp-41h]
  wchar_t *v54; // [rsp+60h] [rbp-39h]
  STRU *v55; // [rsp+68h] [rbp-31h]
  const unsigned __int16 *v56; // [rsp+70h] [rbp-29h]
  _BYTE v57[48]; // [rsp+78h] [rbp-21h] BYREF

  v7 = 0;
  v56 = a3;
  v55 = a5;
  EndPtr = 0;
  v52 = a4;
  BUFFER::BUFFER((BUFFER *)v57);
  if ( a2 && a3 && a6 )
  {
    v9 = 1;
    v10 = a2;
    if ( *a2 == 91 )
    {
      v17 = wcschr(a2, 0x5Du);
      if ( v17 )
      {
        v18 = v17 - a2;
        v11 = (unsigned int)(v18 + 1);
        v49 = v11;
        if ( (unsigned int)v11 >= 4 )
        {
          for ( i = 1; i < (unsigned int)v18; ++i )
          {
            v28 = a2[i];
            if ( (unsigned __int16)(v28 - 48) > 9u
              && (unsigned __int16)(v28 - 65) > 5u
              && (unsigned __int16)(v28 - 97) > 5u
              && (_WORD)v28 != 58
              && v28 != 46 )
            {
              v15 = -2147024883;
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                  2169,
                  "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                  -2147024883,
                  "Invalid IPV6 address. Illegal character %c.\n",
                  a2[i]);
              goto LABEL_11;
            }
          }
          v10 = &a2[v11];
          if ( *v10 == 58 )
            goto LABEL_6;
          v15 = -2147024883;
          if ( (g_dwDebugFlags & 0xF) != 0 )
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
              2201,
              "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
              -2147024883,
              "Invalid binding string. At index %d expecting ':' found '%c'",
              v11,
              *v10);
          goto LABEL_11;
        }
        v15 = -2147024883;
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_11;
        v19 = "Invalid IPV6 address. Too short.\n";
        v20 = 2150;
      }
      else
      {
        v15 = -2147024883;
        if ( (g_dwDebugFlags & 0xF) == 0 )
          goto LABEL_11;
        v19 = "Invalid IPV6 address. Couldn't find the closing ].\n";
        v20 = 2132;
      }
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
        v20,
        "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
        -2147024883,
        v19);
      goto LABEL_11;
    }
    LODWORD(v11) = 0;
    v49 = 0;
    v9 = 0;
LABEL_6:
    v12 = wcschr(v10, 0x3Au);
    if ( !v12 )
      goto LABEL_10;
    v13 = v12 + 1;
    v53 = v12 + 1;
    v54 = wcschr(v12 + 1, 0x3Au);
    if ( !v54 )
      goto LABEL_10;
    v14 = *a2;
    if ( *a2 != 58 )
    {
      v7 = a2;
      if ( !v9 )
      {
        LODWORD(v11) = v13 - a2 - 1;
        v49 = v11;
        if ( v14 == 42 )
        {
          if ( (unsigned int)(v13 - a2) != 2 )
            goto LABEL_10;
        }
        else
        {
          if ( (unsigned int)v11 > 0xF )
            goto LABEL_10;
          v21 = 0;
          v22 = 1;
          v23 = 1;
          v50 = 1;
          v24 = a2;
LABEL_21:
          if ( v14 != 58 )
          {
            do
            {
              if ( (unsigned __int16)(v14 - 48) > 9u )
                break;
              v25 = wcstoul(v24, &EndPtr, 10);
              v24 = EndPtr;
              if ( !EndPtr || *EndPtr != 58 && *EndPtr != 46 )
                break;
              if ( v25 > 0xFF )
                break;
              if ( v25 && (v23 = 0, v25 == 255) )
              {
                v22 = v50;
              }
              else
              {
                v22 = 0;
                v50 = 0;
              }
              if ( (unsigned int)++v21 > 4 )
                break;
              v14 = *EndPtr;
              if ( *EndPtr != 46 )
                goto LABEL_21;
              v24 = EndPtr + 1;
              v14 = EndPtr[1];
            }
            while ( v14 != 58 );
            goto LABEL_10;
          }
          if ( v21 && (v21 != 4 || v23 || v22) )
            goto LABEL_10;
          v13 = v53;
        }
      }
    }
    if ( *v13 != 58 )
    {
      v29 = wcstoul(v13, &EndPtr, 10);
      if ( v29 )
      {
        if ( EndPtr && *EndPtr == 58 && v29 <= 0xFFFF )
        {
          v30 = v54 + 1;
          if ( !v54[1] || (v31 = v54 + 1, *v30 == 42) && !v54[2] )
            v31 = 0;
          v32 = v55;
          if ( v55 )
          {
            STRU::Reset(v55);
            if ( v31 )
            {
              v15 = STRU::Copy(v32, v31);
              if ( v15 < 0 )
                goto LABEL_11;
            }
          }
          v15 = STRU::Append(a6, v56, v52);
          if ( v15 >= 0 )
          {
            if ( v31 )
            {
              v33 = -1;
              do
                ++v33;
              while ( v31[v33] );
              v34 = v33 + 1;
              v35 = IdnToNameprepUnicode(0, v31, v33 + 1, 0, 0);
              if ( v35
                && BUFFER::Resize((BUFFER *)v57, 2 * v35)
                && (cchNameprepChar = BUFFER::QuerySize((BUFFER *)v57) >> 1,
                    v37 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v57),
                    (v38 = IdnToNameprepUnicode(0, v31, v34, v37, cchNameprepChar)) != 0) )
              {
                Ptr = (unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v57);
                v40 = 0;
                v41 = v38 - 1;
                v42 = Ptr;
                while ( 1 )
                {
                  if ( v40 >= v41 )
                  {
                    v44 = (const unsigned __int16 *)BUFFER::QueryPtr((BUFFER *)v57);
                    v45 = STRU::Append(a6, v44);
                    LODWORD(v11) = v49;
                    goto LABEL_91;
                  }
                  if ( (unsigned int)IsIllegalChar(v42[v40]) )
                    break;
                  v40 = v43 + 1;
                }
                v15 = -2147024809;
                if ( (g_dwDebugFlags & 0xF) != 0 )
                  PuDbgPrintError(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                    2534,
                    "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                    -2147024809,
                    "Invalid character in hostname.\n");
              }
              else
              {
                LastError = GetLastError();
                v15 = LastError;
                if ( LastError > 0 )
                  v15 = (unsigned __int16)LastError | 0x80070000;
              }
              goto LABEL_11;
            }
            if ( v7 )
            {
              v46 = v11;
              v47 = v7;
            }
            else
            {
              v46 = 1;
              v47 = L"*";
            }
            v45 = STRU::Append(a6, v47, v46);
LABEL_91:
            v15 = v45;
            if ( v45 >= 0 )
            {
              v15 = STRU::Append(a6, L":", 1u);
              if ( v15 >= 0 )
              {
                v15 = STRU::Append(a6, v53, v30 - v53 - 1);
                if ( v15 >= 0 )
                {
                  if ( v7 && v31 && *v7 != 42 )
                  {
                    v15 = STRU::Append(a6, L":", 1u);
                    if ( v15 < 0 )
                    {
                      if ( (g_dwDebugFlags & 0xF) != 0 )
                        PuDbgPrintError(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                          2616,
                          "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                          v15,
                          "Appending to string failed\n");
                      goto LABEL_11;
                    }
                    v15 = STRU::Append(a6, v7, v11);
                    if ( v15 < 0 )
                    {
                      if ( (g_dwDebugFlags & 0xF) != 0 )
                        PuDbgPrintError(
                          g_pDebug,
                          "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                          2628,
                          "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                          v15,
                          "Appending to string failed\n");
                      goto LABEL_11;
                    }
                  }
                  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x200000) != 0 )
                  {
                    Str = STRU::QueryStr(a6);
                    PuDbgPrint(
                      g_pDebug,
                      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                      2642,
                      "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                      "Converted metabase binding: '%S' to UL binding: '%S'\n",
                      a2,
                      Str);
                  }
                  goto LABEL_11;
                }
                if ( (g_dwDebugFlags & 0xF) != 0 )
                  PuDbgPrintError(
                    g_pDebug,
                    "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                    2588,
                    "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                    v15,
                    "Appending to string failed\n");
              }
              else if ( (g_dwDebugFlags & 0xF) != 0 )
              {
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                  2575,
                  "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                  v15,
                  "Appending to string failed\n");
              }
            }
            else if ( (g_dwDebugFlags & 0xF) != 0 )
            {
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
                2562,
                "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
                v45,
                "Appending to string failed\n");
            }
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dt\\binding_table.cxx",
              2462,
              "BINDING_TABLE::TranslateBindingStringToUrlPrefix",
              v15,
              "Appending to string failed\n");
          }
LABEL_11:
          BUFFER::~BUFFER((BUFFER *)v57);
          return (unsigned int)v15;
        }
      }
    }
LABEL_10:
    v15 = -2147024883;
    goto LABEL_11;
  }
  BUFFER::~BUFFER((BUFFER *)v57);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800115b8  mov     [rsp-8+arg_0], rbx
0x1800115bd  push    rbp
0x1800115be  push    rsi
0x1800115bf  push    rdi
0x1800115c0  push    r12
0x1800115c2  push    r13
0x1800115c4  push    r14
0x1800115c6  push    r15
0x1800115c8  lea     rbp, [rsp-17h]
0x1800115cd  sub     rsp, 0B0h
0x1800115d4  mov     rax, cs:__security_cookie
0x1800115db  xor     rax, rsp
0x1800115de  mov     [rbp+47h+var_38], rax
0x1800115e2  mov     rax, [rbp+47h+arg_20]
0x1800115e6  lea     rcx, [rbp+47h+var_68]
0x1800115ea  mov     r15, [rbp+47h+arg_28]
0x1800115ee  mov     rbx, r8
0x1800115f1  xor     r13d, r13d
0x1800115f4  mov     [rbp+47h+var_70], rbx
0x1800115f8  mov     [rbp+47h+var_78], rax
0x1800115fc  mov     r14, rdx
0x1800115ff  mov     [rbp+47h+EndPtr], r13
0x180011603  mov     [rbp+47h+var_90], r9d
0x180011607  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001160d  test    r14, r14
0x180011610  jz      loc_180011D2A
0x180011616  test    rbx, rbx
0x180011619  jz      loc_180011D2A
0x18001161f  test    r15, r15
0x180011622  jz      loc_180011D2A
0x180011628  cmp     word ptr [r14], 5Bh ; '['
0x18001162d  lea     edi, [r13+1]
0x180011631  mov     rcx, r14; Str
0x180011634  jz      loc_1800116BF
0x18001163a  mov     r12d, r13d
0x18001163d  mov     [rbp+47h+var_A0], r13d
0x180011641  mov     edi, r13d
0x180011644  lea     ebx, [r13+3Ah]
0x180011648  mov     edx, ebx; Ch
0x18001164a  call    cs:__imp_wcschr
0x180011650  test    rax, rax
0x180011653  jz      short loc_180011687
0x180011655  lea     rsi, [rax+2]
0x180011659  mov     edx, ebx; Ch
0x18001165b  mov     rcx, rsi; Str
0x18001165e  mov     [rbp+47h+var_88], rsi
0x180011662  call    cs:__imp_wcschr
0x180011668  mov     [rbp+47h+var_80], rax
0x18001166c  test    rax, rax
0x18001166f  jz      short loc_180011687
0x180011671  movzx   ecx, word ptr [r14]
0x180011675  cmp     cx, bx
0x180011678  jnz     loc_180011736
0x18001167e  cmp     [rsi], bx
0x180011681  jnz     loc_180011987
0x180011687  mov     ebx, 8007000Dh
0x18001168c  lea     rcx, [rbp+47h+var_68]
0x180011690  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180011696  mov     eax, ebx
0x180011698  mov     rcx, [rbp+47h+var_38]
0x18001169c  xor     rcx, rsp; StackCookie
0x18001169f  call    __security_check_cookie
0x1800116a4  mov     rbx, [rsp+0E0h+arg_0]
0x1800116ac  add     rsp, 0B0h
0x1800116b3  pop     r15
0x1800116b5  pop     r14
0x1800116b7  pop     r13
0x1800116b9  pop     r12
0x1800116bb  pop     rdi
0x1800116bc  pop     rsi
0x1800116bd  pop     rbp
0x1800116be  retn
0x1800116bf  mov     edx, 5Dh ; ']'; Ch
0x1800116c4  call    cs:__imp_wcschr
0x1800116ca  mov     rcx, rax
0x1800116cd  test    rax, rax
0x1800116d0  jz      loc_180011823
0x1800116d6  sub     rcx, r14
0x1800116d9  sar     rcx, 1
0x1800116dc  lea     r12d, [rcx+1]
0x1800116e0  mov     [rbp+47h+var_A0], r12d
0x1800116e4  cmp     r12d, 4
0x1800116e8  jnb     loc_180011847
0x1800116ee  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800116f5  mov     ebx, 8007000Dh
0x1800116fa  jz      short loc_18001168C
0x1800116fc  lea     rax, aInvalidIpv6Add_0; "Invalid IPV6 address. Too short.\n"
0x180011703  mov     r8d, 866h
0x180011709  mov     [rsp+0E0h+var_B8], rax
0x18001170e  mov     [rsp+0E0h+cchNameprepChar], 8007000Dh
0x180011716  mov     rcx, cs:g_pDebug
0x18001171d  lea     r9, aBindingTableTr; "BINDING_TABLE::TranslateBindingStringTo"...
0x180011724  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001172b  call    cs:__imp_PuDbgPrintError
0x180011731  jmp     loc_18001168C
0x180011736  xor     edx, edx
0x180011738  mov     r13, r14
0x18001173b  test    edi, edi
0x18001173d  jnz     loc_18001167E
0x180011743  mov     r12, rsi
0x180011746  sub     r12, r14
0x180011749  sar     r12, 1
0x18001174c  dec     r12d
0x18001174f  mov     [rbp+47h+var_A0], r12d
0x180011753  cmp     cx, 2Ah ; '*'
0x180011757  jz      loc_180011942
0x18001175d  cmp     r12d, 0Fh
0x180011761  ja      loc_180011687
0x180011767  lea     r8d, [rdx+1]
0x18001176b  mov     edi, edx
0x18001176d  mov     eax, r8d
0x180011770  mov     esi, r8d
0x180011773  mov     [rbp+47h+var_9C], eax
0x180011776  mov     r9, r14
0x180011779  cmp     cx, bx
0x18001177c  jz      loc_180011961
0x180011782  sub     cx, 30h ; '0'
0x180011786  cmp     cx, 9
0x18001178a  ja      loc_180011687
0x180011790  mov     r8d, 0Ah; Radix
0x180011796  lea     rdx, [rbp+47h+EndPtr]; EndPtr
0x18001179a  mov     rcx, r9; String
0x18001179d  call    cs:__imp_wcstoul
0x1800117a3  mov     r9, [rbp+47h+EndPtr]
0x1800117a7  xor     edx, edx
0x1800117a9  test    r9, r9
0x1800117ac  jz      loc_180011687
0x1800117b2  cmp     [r9], bx
0x1800117b6  jnz     loc_180011951
0x1800117bc  cmp     eax, 0FFh
0x1800117c1  ja      loc_180011687
0x1800117c7  test    eax, eax
0x1800117c9  jnz     short loc_1800117F7
0x1800117cb  mov     eax, edx
0x1800117cd  mov     [rbp+47h+var_9C], edx
0x1800117d0  inc     edi
0x1800117d2  cmp     edi, 4
0x1800117d5  ja      loc_180011687
0x1800117db  movzx   ecx, word ptr [r9]
0x1800117df  cmp     cx, 2Eh ; '.'
0x1800117e3  jnz     short loc_180011779
0x1800117e5  add     r9, 2
0x1800117e9  movzx   ecx, word ptr [r9]
0x1800117ed  cmp     cx, bx
0x1800117f0  jnz     short loc_180011782
0x1800117f2  jmp     loc_180011687
0x1800117f7  mov     esi, edx
0x1800117f9  cmp     eax, 0FFh
0x1800117fe  jnz     short loc_1800117CB
0x180011800  mov     eax, [rbp+47h+var_9C]
0x180011803  jmp     short loc_1800117D0
0x180011805  call    cs:__imp_GetLastError
0x18001180b  mov     ebx, eax
0x18001180d  test    eax, eax
0x18001180f  jle     loc_18001168C
0x180011815  movzx   ebx, ax
0x180011818  or      ebx, 80070000h
0x18001181e  jmp     loc_18001168C
0x180011823  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001182a  mov     ebx, 8007000Dh
0x18001182f  jz      loc_18001168C
0x180011835  lea     rax, aInvalidIpv6Add; "Invalid IPV6 address. Couldn't find the"...
0x18001183c  mov     r8d, 854h
0x180011842  jmp     loc_180011709
0x180011847  mov     r8d, edi
0x18001184a  mov     ebx, 3Ah ; ':'
0x18001184f  cmp     r8d, ecx
0x180011852  jnb     loc_1800118DD
0x180011858  mov     eax, r8d
0x18001185b  movzx   edx, word ptr [r14+rax*2]
0x180011860  lea     eax, [rdx-30h]
0x180011863  cmp     ax, 9
0x180011867  jbe     short loc_1800118D5
0x180011869  lea     eax, [rdx-41h]
0x18001186c  cmp     ax, 5
0x180011870  jbe     short loc_1800118D5
0x180011872  lea     eax, [rdx-61h]
0x180011875  cmp     ax, 5
0x180011879  jbe     short loc_1800118D5
0x18001187b  cmp     dx, bx
0x18001187e  jz      short loc_1800118D5
0x180011880  cmp     edx, 2Eh ; '.'
0x180011883  jz      short loc_1800118D5
0x180011885  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001188c  mov     ebx, 8007000Dh
0x180011891  jz      loc_18001168C
0x180011897  mov     rcx, cs:g_pDebug
0x18001189e  lea     rax, aInvalidIpv6Add_1; "Invalid IPV6 address. Illegal character"...
0x1800118a5  mov     dword ptr [rsp+0E0h+var_B0], edx
0x1800118a9  lea     r9, aBindingTableTr; "BINDING_TABLE::TranslateBindingStringTo"...
0x1800118b0  mov     [rsp+0E0h+var_B8], rax
0x1800118b5  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800118bc  mov     r8d, 879h
0x1800118c2  mov     [rsp+0E0h+cchNameprepChar], 8007000Dh
0x1800118ca  call    cs:__imp_PuDbgPrintError
0x1800118d0  jmp     loc_18001168C
0x1800118d5  add     r8d, edi
0x1800118d8  jmp     loc_18001184F
0x1800118dd  lea     rcx, [r14+r12*2]
0x1800118e1  cmp     [rcx], bx
0x1800118e4  jz      loc_180011648
0x1800118ea  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800118f1  mov     ebx, 8007000Dh
0x1800118f6  jz      loc_18001168C
0x1800118fc  movzx   eax, word ptr [rcx]
0x1800118ff  lea     r9, aBindingTableTr; "BINDING_TABLE::TranslateBindingStringTo"...
0x180011906  mov     rcx, cs:g_pDebug
0x18001190d  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180011914  mov     [rsp+0E0h+var_A8], eax
0x180011918  mov     r8d, 899h
0x18001191e  lea     rax, aInvalidBinding; "Invalid binding string. At index %d exp"...
0x180011925  mov     dword ptr [rsp+0E0h+var_B0], r12d
0x18001192a  mov     [rsp+0E0h+var_B8], rax
0x18001192f  mov     [rsp+0E0h+cchNameprepChar], 8007000Dh
0x180011937  call    cs:__imp_PuDbgPrintError
0x18001193d  jmp     loc_18001168C
0x180011942  cmp     r12d, 1
0x180011946  jz      loc_18001167E
0x18001194c  jmp     loc_180011687
0x180011951  cmp     word ptr [r9], 2Eh ; '.'
0x180011956  jnz     loc_180011687
0x18001195c  jmp     loc_1800117BC
0x180011961  test    edi, edi
0x180011963  jz      short loc_18001197E
0x180011965  cmp     edi, 4
0x180011968  jnz     loc_180011687
0x18001196e  test    esi, esi
0x180011970  jnz     loc_180011687
0x180011976  test    eax, eax
0x180011978  jnz     loc_180011687
0x18001197e  mov     rsi, [rbp+47h+var_88]
0x180011982  jmp     loc_18001167E
0x180011987  mov     r8d, 0Ah; Radix
0x18001198d  lea     rdx, [rbp+47h+EndPtr]; EndPtr
0x180011991  mov     rcx, rsi; String
0x180011994  call    cs:__imp_wcstoul
0x18001199a  xor     edx, edx
0x18001199c  test    eax, eax
0x18001199e  jz      loc_180011687
0x1800119a4  mov     rcx, [rbp+47h+EndPtr]
0x1800119a8  test    rcx, rcx
0x1800119ab  jz      loc_180011687
0x1800119b1  cmp     [rcx], bx
0x1800119b4  jnz     loc_180011687
0x1800119ba  cmp     eax, 0FFFFh
0x1800119bf  ja      loc_180011687
0x1800119c5  mov     rdi, [rbp+47h+var_80]
0x1800119c9  add     rdi, 2
0x1800119cd  cmp     [rdi], dx
0x1800119d0  jz      short loc_1800119E1
0x1800119d2  cmp     word ptr [rdi], 2Ah ; '*'
0x1800119d6  mov     rsi, rdi
0x1800119d9  jnz     short loc_1800119E4
0x1800119db  cmp     [rdi+2], dx
0x1800119df  jnz     short loc_1800119E4
0x1800119e1  mov     rsi, rdx
0x1800119e4  mov     rbx, [rbp+47h+var_78]
0x1800119e8  test    rbx, rbx
0x1800119eb  jz      short loc_180011A11
0x1800119ed  mov     rcx, rbx
0x1800119f0  call    cs:__imp_?Reset@STRU@@QEAAXXZ; STRU::Reset(void)
0x1800119f6  test    rsi, rsi
0x1800119f9  jz      short loc_180011A11
0x1800119fb  mov     rdx, rsi
0x1800119fe  mov     rcx, rbx
0x180011a01  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180011a07  mov     ebx, eax
0x180011a09  test    eax, eax
0x180011a0b  js      loc_18001168C
0x180011a11  mov     r8d, [rbp+47h+var_90]
0x180011a15  mov     rcx, r15
0x180011a18  mov     rdx, [rbp+47h+var_70]
0x180011a1c  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180011a22  mov     ebx, eax
0x180011a24  test    eax, eax
0x180011a26  jns     short loc_180011A50
0x180011a28  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180011a2f  jz      loc_18001168C
0x180011a35  lea     rax, aAppendingToStr; "Appending to string failed\n"
0x180011a3c  mov     r8d, 99Eh
0x180011a42  mov     [rsp+0E0h+var_B8], rax
0x180011a47  mov     [rsp+0E0h+cchNameprepChar], ebx
0x180011a4b  jmp     loc_180011716
0x180011a50  xor     ebx, ebx
0x180011a52  test    rsi, rsi
0x180011a55  jz      loc_180011B52
0x180011a5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011a5f  inc     rax
0x180011a62  cmp     [rsi+rax*2], bx
0x180011a66  jnz     short loc_180011A5F
0x180011a68  lea     r12d, [rax+1]
0x180011a6c  mov     [rsp+0E0h+cchNameprepChar], ebx; cchNameprepChar
0x180011a70  mov     r8d, r12d; cchUnicodeChar
0x180011a73  xor     r9d, r9d; lpNameprepCharStr
0x180011a76  mov     rdx, rsi; lpUnicodeCharStr
0x180011a79  xor     ecx, ecx; dwFlags
0x180011a7b  call    cs:__imp_IdnToNameprepUnicode
0x180011a81  test    eax, eax
0x180011a83  jz      loc_180011805
0x180011a89  lea     edx, [rax+rax]
  ... truncated ...
```
