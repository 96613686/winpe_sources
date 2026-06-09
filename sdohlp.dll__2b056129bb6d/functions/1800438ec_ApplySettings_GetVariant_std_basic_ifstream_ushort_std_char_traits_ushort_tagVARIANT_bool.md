# ApplySettings::GetVariant(std::basic_ifstream<ushort,std::char_traits<ushort>> &,tagVARIANT &,bool)

- ea: `0x1800438ec`
- end: `0x180043d86`
- name: `?GetVariant@ApplySettings@@AEAAJAEAV?$basic_ifstream@GU?$char_traits@G@std@@@std@@AEAUtagVARIANT@@_N@Z`
- size: `1178`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004520c`

## callees

- `0x18002cca4`
- `0x1800388a0`
- `0x180038ad0`
- `0x180042a80`
- `0x1800438ec`
- `0x180046fdc`
- `0x180047140`
- `0x1800471b4`
- `0x180055030`

## import_xrefs

- `msvcrt!wcstol` at `0x180043a9d`
- `msvcrt!wcstol` at `0x180043be1`
- `msvcrt!wcstol` at `0x180043c97`
- `msvcrt!wcstol` at `0x180043a9d`
- `msvcrt!wcstol` at `0x180043be1`
- `msvcrt!wcstol` at `0x180043c97`
- `msvcrt!free` at `0x180043a1d`
- `msvcrt!free` at `0x180043a38`
- `msvcrt!free` at `0x180043d3c`
- `msvcrt!free` at `0x180043d57`
- `msvcrt!free` at `0x180043a1d`
- `msvcrt!free` at `0x180043a38`
- `msvcrt!free` at `0x180043d3c`
- `msvcrt!free` at `0x180043d57`
- `KERNEL32!GetLastError` at `0x180043ca5`
- `KERNEL32!GetLastError` at `0x180043ca5`
- `OLEAUT32!__imp_SysAllocString` at `0x180043c73`
- `OLEAUT32!__imp_SysAllocString` at `0x180043c73`
- `OLEAUT32!__imp_VariantInit` at `0x180043a7f`
- `OLEAUT32!__imp_VariantInit` at `0x180043a7f`
- `OLEAUT32!__imp_VariantClear` at `0x180043c28`
- `OLEAUT32!__imp_VariantClear` at `0x180043c28`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800439a3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1800439a3`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043c1c`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x180043c1c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043b70`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x180043b70`

## string_xrefs

- `0x180043cef`: `[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!`
- `0x180043b0f`: `Unexpected data: error in your configuration file`
- `0x1800439d5`: `Could not create safearray\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ApplySettings::GetVariant(__int64 a1, __int64 a2, _WORD *a3, char a4)
{
  __int64 i; // rbx
  char *v6; // rdi
  unsigned __int64 v7; // r14
  __int64 v8; // rcx
  void *v9; // rbx
  unsigned int v11; // esi
  unsigned __int64 v12; // rbx
  char *v13; // r13
  SAFEARRAY *v14; // r15
  __int64 v15; // rbx
  const wchar_t *v16; // rcx
  int v17; // eax
  unsigned __int64 v18; // rsi
  const OLECHAR *v19; // rcx
  bool v20; // cf
  char *v21; // rbx
  char *v22; // rax
  unsigned __int64 v23; // r8
  SAFEARRAY *Vector; // r15
  char *v25; // rcx
  unsigned __int64 v26; // rax
  bool v27; // cf
  char *v28; // rax
  char *v29; // rax
  unsigned __int64 v30; // rbx
  const wchar_t *v31; // rcx
  signed int LastError; // eax
  char v33; // bl
  int v34; // r8d
  int v35; // r9d
  _WORD *v36; // rax
  VARIANTARG pvarg; // [rsp+38h] [rbp-61h] BYREF
  SAFEARRAY *psa; // [rsp+50h] [rbp-49h]
  LONG rgIndices[2]; // [rsp+58h] [rbp-41h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+60h] [rbp-39h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-31h]
  void *Block[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v44; // [rsp+80h] [rbp-19h]
  void *v45[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v46; // [rsp+98h] [rbp-1h]
  _WORD *v47; // [rsp+A0h] [rbp+7h]
  wchar_t String[4]; // [rsp+A8h] [rbp+Fh] BYREF

  v47 = a3;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  *(_OWORD *)Block = 0;
  v44 = 0;
  for ( i = a1 + 16; ; std::vector<std::wstring>::push_back(v45, i) )
  {
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, i);
    if ( (unsigned __int8)std::operator==<unsigned short>(i, L"----------------------------------------") )
      break;
    std::vector<std::wstring>::push_back(Block, i);
    std::getline<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(a2, i);
  }
  v6 = (char *)v45[0];
  v7 = ((char *)v45[1] - (char *)v45[0]) >> 5;
  rgsabound.cElements = v7;
  rgsabound.lLbound = 0;
  psa = SafeArrayCreate(0xCu, 1u, &rgsabound);
  if ( !psa )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WppDbgPrint("Could not create safearray\n");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, &WPP_70cc9e363f77355498ae630336bd681a_Traceguids, "NPSDS");
    }
    v9 = Block[0];
    if ( Block[0] )
    {
      std::vector<std::wstring>::_Destroy(v8, Block[0], Block[1]);
      free(v9);
    }
    if ( v6 )
    {
      std::vector<std::wstring>::_Destroy(v8, v6, v45[1]);
      free(v6);
    }
    return 2147942414LL;
  }
  v11 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  *(_QWORD *)rgIndices = 0;
  v12 = 0;
  v13 = (char *)Block[0];
  v14 = psa;
  while ( 1 )
  {
    v42 = v12;
    if ( v12 >= v7 )
    {
      v36 = v47;
      *v47 = 8204;
      *((_QWORD *)v36 + 1) = v14;
      goto LABEL_70;
    }
    VariantInit(&pvarg);
    v15 = 32 * v12;
    v16 = (const wchar_t *)&v13[v15];
    if ( *(_QWORD *)&v13[v15 + 24] >= 8u )
      v16 = *(const wchar_t **)v16;
    v17 = wcstol(v16, 0, 10);
    v18 = 0;
    if ( a4 )
    {
      pvarg.vt = 8;
      v19 = (const OLECHAR *)&v6[v15];
      v20 = *(_QWORD *)&v6[v15 + 24] < 8u;
LABEL_55:
      if ( !v20 )
        v19 = *(const OLECHAR **)v19;
      pvarg.llVal = (LONGLONG)SysAllocString(v19);
      goto LABEL_49;
    }
    switch ( v17 )
    {
      case 3:
        pvarg.vt = 3;
        v31 = (const wchar_t *)&v6[v15];
        if ( *(_QWORD *)&v6[v15 + 24] >= 8u )
          v31 = *(const wchar_t **)v31;
        pvarg.lVal = wcstol(v31, 0, 10);
        break;
      case 8:
        pvarg.vt = 8;
        v19 = (const OLECHAR *)&v6[v15];
        v20 = *(_QWORD *)&v6[v15 + 24] < 8u;
        goto LABEL_55;
      case 11:
        pvarg.vt = 11;
        pvarg.iVal = (unsigned __int8)std::operator==<unsigned short>(&v6[v15], L"-1") ? -1 : 0;
        break;
      case 8209:
        pvarg.vt = 8209;
        v21 = &v6[v15];
        if ( *((_QWORD *)v21 + 3) < 8u )
          v22 = v21;
        else
          v22 = *(char **)v21;
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)&v22[2 * v23] );
        Vector = SafeArrayCreateVector(0x11u, 0, v23 >> 1);
        if ( Vector )
        {
          while ( 1 )
          {
            v25 = *((_QWORD *)v21 + 3) < 8u ? v21 : *(char **)v21;
            v26 = -1;
            do
              ++v26;
            while ( *(_WORD *)&v25[2 * v26] );
            if ( v18 >= v26 )
              break;
            v27 = *((_QWORD *)v21 + 3) < 8u;
            if ( *((_QWORD *)v21 + 3) < 8u )
              v28 = v21;
            else
              v28 = *(char **)v21;
            String[0] = *(_WORD *)&v28[2 * v18];
            if ( v27 )
              v29 = v21;
            else
              v29 = *(char **)v21;
            String[1] = *(_WORD *)&v29[2 * v18 + 2];
            String[2] = 0;
            *((_BYTE *)Vector->pvData + (v18 >> 1)) = wcstol(String, 0, 16);
            v18 += 2LL;
          }
          pvarg.llVal = (LONGLONG)Vector;
          v6 = (char *)v45[0];
          v13 = (char *)Block[0];
        }
        v14 = psa;
        break;
      default:
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
        {
          WppDbgPrint("Unexpected data: error in your configuration file");
          WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_70cc9e363f77355498ae630336bd681a_Traceguids, "NPSDS");
        }
        break;
    }
LABEL_49:
    v30 = v42;
    rgIndices[0] = v42;
    v11 = SafeArrayPutElement(v14, rgIndices, &pvarg);
    VariantClear(&pvarg);
    if ( v11 )
      break;
    v12 = v30 + 1;
  }
  LastError = GetLastError();
  v33 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v33 = LastError;
  }
  else
  {
    v33 = 5;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]$COMPID$ %s returned hr = %!HRESULT!");
    WPP_SF_ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, v34, v35, (__int64)"SafeArrayPutElement", v33);
  }
LABEL_70:
  if ( v13 )
  {
    std::vector<std::wstring>::_Destroy(v8, v13, Block[1]);
    free(v13);
  }
  if ( v6 )
  {
    std::vector<std::wstring>::_Destroy(v8, v6, v45[1]);
    free(v6);
  }
  return v11;
}

```

## disassembly

```asm
0x1800438ec  mov     [rsp-8+arg_18], rbx
0x1800438f1  push    rbp
0x1800438f2  push    rsi
0x1800438f3  push    rdi
0x1800438f4  push    r12
0x1800438f6  push    r13
0x1800438f8  push    r14
0x1800438fa  push    r15
0x1800438fc  lea     rbp, [rsp-27h]
0x180043901  sub     rsp, 0C0h
0x180043908  mov     rax, cs:__security_cookie
0x18004390f  xor     rax, rsp
0x180043912  mov     [rbp+57h+var_40], rax
0x180043916  mov     [rbp+57h+var_C0], r9b
0x18004391a  mov     [rbp+57h+var_50], r8
0x18004391e  mov     rdi, rdx
0x180043921  xorps   xmm0, xmm0
0x180043924  movdqu  xmmword ptr [rbp+57h+var_68], xmm0
0x180043929  xor     r15d, r15d
0x18004392c  mov     [rbp+57h+var_58], r15
0x180043930  movdqu  xmmword ptr [rbp+57h+Block], xmm0
0x180043935  mov     [rbp+57h+var_70], r15
0x180043939  lea     rbx, [rcx+10h]
0x18004393d  mov     rdx, rbx
0x180043940  mov     rcx, rdi
0x180043943  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180043948  lea     rdx, asc_1800667F0; "---------------------------------------"...
0x18004394f  mov     rcx, rbx
0x180043952  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180043957  test    al, al
0x180043959  jnz     short loc_180043980
0x18004395b  mov     rdx, rbx
0x18004395e  lea     rcx, [rbp+57h+Block]
0x180043962  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x180043967  mov     rdx, rbx
0x18004396a  mov     rcx, rdi
0x18004396d  call    ??$getline@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@YAAEAV?$basic_istream@GU?$char_traits@G@std@@@0@AEAV10@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@@Z; std::getline<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_istream<ushort> &,std::wstring &)
0x180043972  mov     rdx, rbx
0x180043975  lea     rcx, [rbp+57h+var_68]
0x180043979  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18004397e  jmp     short loc_18004393D
0x180043980  mov     r14, [rbp+57h+var_68+8]
0x180043984  mov     rdi, [rbp+57h+var_68]
0x180043988  sub     r14, rdi
0x18004398b  sar     r14, 5
0x18004398f  mov     [rbp+57h+rgsabound.cElements], r14d
0x180043993  mov     [rbp+57h+rgsabound.lLbound], r15d
0x180043997  mov     ecx, 0Ch; vt
0x18004399c  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x1800439a0  lea     edx, [rcx-0Bh]; cDims
0x1800439a3  call    cs:__imp_SafeArrayCreate
0x1800439a9  mov     [rbp+57h+psa], rax
0x1800439ad  test    rax, rax
0x1800439b0  jnz     loc_180043A48
0x1800439b6  lea     r12, WPP_GLOBAL_Control
0x1800439bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800439c4  cmp     rax, r12
0x1800439c7  jz      short loc_180043A05
0x1800439c9  cmp     byte ptr [rax+19h], 2
0x1800439cd  jb      short loc_180043A05
0x1800439cf  test    byte ptr [rax+1Ch], 10h
0x1800439d3  jz      short loc_180043A05
0x1800439d5  lea     rcx, aCouldNotCreate; "Could not create safearray\n"
0x1800439dc  call    WppDbgPrint
0x1800439e1  mov     edx, 43h ; 'C'
0x1800439e6  lea     r9, aNpsds; "NPSDS"
0x1800439ed  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x1800439f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439fb  mov     rcx, [rcx+10h]
0x1800439ff  call    WPP_SF_s
0x180043a04  nop
0x180043a05  mov     rbx, [rbp+57h+Block]
0x180043a09  test    rbx, rbx
0x180043a0c  jz      short loc_180043A24
0x180043a0e  mov     r8, [rbp+57h+Block+8]
0x180043a12  mov     rdx, rbx
0x180043a15  call    ?_Destroy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@0@Z; std::vector<std::wstring>::_Destroy(std::wstring *,std::wstring *)
0x180043a1a  mov     rcx, rbx; Block
0x180043a1d  call    cs:__imp_free
0x180043a23  nop
0x180043a24  test    rdi, rdi
0x180043a27  jz      short loc_180043A3E
0x180043a29  mov     r8, [rbp+57h+var_68+8]
0x180043a2d  mov     rdx, rdi
0x180043a30  call    ?_Destroy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@0@Z; std::vector<std::wstring>::_Destroy(std::wstring *,std::wstring *)
0x180043a35  mov     rcx, rdi; Block
0x180043a38  call    cs:__imp_free
0x180043a3e  mov     eax, 8007000Eh
0x180043a43  jmp     loc_180043D5F
0x180043a48  mov     esi, r15d
0x180043a4b  xorps   xmm0, xmm0
0x180043a4e  xor     eax, eax
0x180043a50  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x180043a54  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x180043a58  mov     qword ptr [rbp+57h+rgIndices], r15
0x180043a5c  mov     rbx, r15
0x180043a5f  lea     r12, WPP_GLOBAL_Control
0x180043a66  mov     r13, [rbp+57h+Block]
0x180043a6a  mov     r15, [rbp+57h+psa]
0x180043a6e  mov     [rbp+57h+var_88], rbx
0x180043a72  cmp     rbx, r14
0x180043a75  jnb     loc_180043D1B
0x180043a7b  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043a7f  call    cs:__imp_VariantInit
0x180043a85  shl     rbx, 5
0x180043a89  lea     rcx, [rbx+r13]
0x180043a8d  cmp     qword ptr [rcx+18h], 8
0x180043a92  jb      short loc_180043A97
0x180043a94  mov     rcx, [rcx]; String
0x180043a97  xor     edx, edx; EndPtr
0x180043a99  lea     r8d, [rdx+0Ah]; Radix
0x180043a9d  call    cs:__imp_wcstol
0x180043aa3  xor     esi, esi
0x180043aa5  cmp     [rbp+57h+var_C0], sil
0x180043aa9  jz      short loc_180043ABF
0x180043aab  lea     eax, [rsi+8]
0x180043aae  mov     word ptr [rbp+57h+pvarg], ax
0x180043ab2  lea     rcx, [rdi+rbx]
0x180043ab6  cmp     [rcx+18h], rax
0x180043aba  jmp     loc_180043C6E
0x180043abf  mov     ecx, 3
0x180043ac4  cmp     eax, ecx
0x180043ac6  jz      loc_180043C7F
0x180043acc  lea     edx, [rcx+5]
0x180043acf  cmp     eax, edx
0x180043ad1  jz      loc_180043C62
0x180043ad7  lea     ecx, [rdx+3]
0x180043ada  cmp     eax, ecx
0x180043adc  jz      loc_180043C3A
0x180043ae2  mov     ecx, 2011h
0x180043ae7  cmp     eax, ecx
0x180043ae9  jz      short loc_180043B43
0x180043aeb  mov     rax, cs:WPP_GLOBAL_Control
0x180043af2  cmp     rax, r12
0x180043af5  jz      loc_180043C0A
0x180043afb  cmp     byte ptr [rax+19h], 2
0x180043aff  jb      loc_180043C0A
0x180043b05  test    byte ptr [rax+1Ch], 10h
0x180043b09  jz      loc_180043C0A
0x180043b0f  lea     rcx, aUnexpectedData; "Unexpected data: error in your configur"...
0x180043b16  call    WppDbgPrint
0x180043b1b  mov     edx, 44h ; 'D'
0x180043b20  lea     r9, aNpsds; "NPSDS"
0x180043b27  lea     r8, WPP_70cc9e363f77355498ae630336bd681a_Traceguids
0x180043b2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b35  mov     rcx, [rcx+10h]
0x180043b39  call    WPP_SF_s
0x180043b3e  jmp     loc_180043C0A
0x180043b43  mov     word ptr [rbp+57h+pvarg], cx
0x180043b47  add     rbx, rdi
0x180043b4a  cmp     [rbx+18h], rdx
0x180043b4e  jb      short loc_180043B55
0x180043b50  mov     rax, [rbx]
0x180043b53  jmp     short loc_180043B58
0x180043b55  mov     rax, rbx
0x180043b58  or      r8, 0FFFFFFFFFFFFFFFFh
0x180043b5c  inc     r8
0x180043b5f  cmp     [rax+r8*2], si
0x180043b64  jnz     short loc_180043B5C
0x180043b66  shr     r8, 1; cElements
0x180043b69  mov     ecx, 11h; vt
0x180043b6e  xor     edx, edx; lLbound
0x180043b70  call    cs:__imp_SafeArrayCreateVector
0x180043b76  mov     r15, rax
0x180043b79  test    rax, rax
0x180043b7c  jz      loc_180043C06
0x180043b82  mov     r13d, 8
0x180043b88  cmp     [rbx+18h], r13
0x180043b8c  jb      short loc_180043B93
0x180043b8e  mov     rcx, [rbx]
0x180043b91  jmp     short loc_180043B96
0x180043b93  mov     rcx, rbx
0x180043b96  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043b9a  xor     edx, edx; EndPtr
0x180043b9c  inc     rax
0x180043b9f  cmp     [rcx+rax*2], dx
0x180043ba3  jnz     short loc_180043B9C
0x180043ba5  cmp     rsi, rax
0x180043ba8  jnb     short loc_180043BFA
0x180043baa  cmp     [rbx+18h], r13
0x180043bae  jb      short loc_180043BB5
0x180043bb0  mov     rax, [rbx]
0x180043bb3  jmp     short loc_180043BB8
0x180043bb5  mov     rax, rbx
0x180043bb8  movzx   eax, word ptr [rax+rsi*2]
0x180043bbc  mov     [rbp+57h+String], ax
0x180043bc0  jb      short loc_180043BC7
0x180043bc2  mov     rax, [rbx]
0x180043bc5  jmp     short loc_180043BCA
0x180043bc7  mov     rax, rbx
0x180043bca  movzx   eax, word ptr [rax+rsi*2+2]
0x180043bcf  mov     [rbp+57h+var_46], ax
0x180043bd3  mov     [rbp+57h+var_44], dx
0x180043bd7  mov     r8d, 10h; Radix
0x180043bdd  lea     rcx, [rbp+57h+String]; String
0x180043be1  call    cs:__imp_wcstol
0x180043be7  mov     rdx, rsi
0x180043bea  shr     rdx, 1
0x180043bed  mov     rcx, [r15+10h]
0x180043bf1  mov     [rdx+rcx], al
0x180043bf4  add     rsi, 2
0x180043bf8  jmp     short loc_180043B88
0x180043bfa  mov     qword ptr [rbp+57h+pvarg+8], r15
0x180043bfe  mov     rdi, [rbp+57h+var_68]
0x180043c02  mov     r13, [rbp+57h+Block]
0x180043c06  mov     r15, [rbp+57h+psa]
0x180043c0a  mov     rbx, [rbp+57h+var_88]
0x180043c0e  mov     [rbp+57h+rgIndices], ebx
0x180043c11  lea     r8, [rbp+57h+pvarg]; pv
0x180043c15  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x180043c19  mov     rcx, r15; psa
0x180043c1c  call    cs:__imp_SafeArrayPutElement
0x180043c22  mov     esi, eax
0x180043c24  lea     rcx, [rbp+57h+pvarg]; pvarg
0x180043c28  call    cs:__imp_VariantClear
0x180043c2e  test    esi, esi
0x180043c30  jnz     short loc_180043CA5
0x180043c32  inc     rbx
0x180043c35  jmp     loc_180043A6E
0x180043c3a  mov     word ptr [rbp+57h+pvarg], cx
0x180043c3e  lea     rcx, [rbx+rdi]
0x180043c42  lea     rdx, a1; "-1"
0x180043c49  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBG@Z; std::operator==<ushort>(std::wstring const &,ushort const *)
0x180043c4e  test    al, al
0x180043c50  jz      short loc_180043C5C
0x180043c52  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043c56  mov     word ptr [rbp+57h+pvarg+8], ax
0x180043c5a  jmp     short loc_180043C0A
0x180043c5c  mov     word ptr [rbp+57h+pvarg+8], si
0x180043c60  jmp     short loc_180043C0A
0x180043c62  mov     word ptr [rbp+57h+pvarg], dx
0x180043c66  lea     rcx, [rbx+rdi]
0x180043c6a  cmp     [rcx+18h], rdx
0x180043c6e  jb      short loc_180043C73
0x180043c70  mov     rcx, [rcx]; psz
0x180043c73  call    cs:__imp_SysAllocString
0x180043c79  mov     qword ptr [rbp+57h+pvarg+8], rax
0x180043c7d  jmp     short loc_180043C0A
0x180043c7f  mov     word ptr [rbp+57h+pvarg], cx
0x180043c83  lea     rcx, [rbx+rdi]
0x180043c87  cmp     qword ptr [rcx+18h], 8
0x180043c8c  jb      short loc_180043C91
0x180043c8e  mov     rcx, [rcx]; String
0x180043c91  xor     edx, edx; EndPtr
0x180043c93  lea     r8d, [rdx+0Ah]; Radix
0x180043c97  call    cs:__imp_wcstol
0x180043c9d  mov     dword ptr [rbp+57h+pvarg+8], eax
0x180043ca0  jmp     loc_180043C0A
0x180043ca5  call    cs:__imp_GetLastError
0x180043cab  mov     ebx, eax
0x180043cad  test    eax, eax
0x180043caf  jz      short loc_180043CBE
0x180043cb1  jle     short loc_180043CC3
0x180043cb3  movzx   ebx, ax
0x180043cb6  or      ebx, 80070000h
0x180043cbc  jmp     short loc_180043CC3
0x180043cbe  mov     ebx, 80004005h
0x180043cc3  mov     rax, cs:WPP_GLOBAL_Control
0x180043cca  cmp     rax, r12
0x180043ccd  jz      short loc_180043D28
0x180043ccf  cmp     byte ptr [rax+19h], 2
0x180043cd3  jb      short loc_180043D28
0x180043cd5  test    byte ptr [rax+1Ch], 10h
0x180043cd9  jz      short loc_180043D28
0x180043cdb  mov     r9d, ebx
0x180043cde  lea     r14, aSafearrayputel; "SafeArrayPutElement"
0x180043ce5  mov     r8, r14
0x180043ce8  lea     rdx, aNpsds; "NPSDS"
0x180043cef  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x180043cf6  call    WppDbgPrint
0x180043cfb  mov     edx, 45h ; 'E'
0x180043d00  mov     [rsp+0F0h+var_C8], ebx
0x180043d04  mov     [rsp+0F0h+var_D0], r14
0x180043d09  mov     rcx, cs:WPP_GLOBAL_Control
0x180043d10  mov     rcx, [rcx+10h]
0x180043d14  call    WPP_SF_ssd
0x180043d19  jmp     short loc_180043D28
0x180043d1b  mov     rax, [rbp+57h+var_50]
0x180043d1f  mov     word ptr [rax], 200Ch
0x180043d24  mov     [rax+8], r15
0x180043d28  test    r13, r13
0x180043d2b  jz      short loc_180043D43
0x180043d2d  mov     r8, [rbp+57h+Block+8]
0x180043d31  mov     rdx, r13
0x180043d34  call    ?_Destroy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@0@Z; std::vector<std::wstring>::_Destroy(std::wstring *,std::wstring *)
0x180043d39  mov     rcx, r13; Block
0x180043d3c  call    cs:__imp_free
0x180043d42  nop
0x180043d43  test    rdi, rdi
0x180043d46  jz      short loc_180043D5D
0x180043d48  mov     r8, [rbp+57h+var_68+8]
0x180043d4c  mov     rdx, rdi
0x180043d4f  call    ?_Destroy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@0@Z; std::vector<std::wstring>::_Destroy(std::wstring *,std::wstring *)
0x180043d54  mov     rcx, rdi; Block
0x180043d57  call    cs:__imp_free
0x180043d5d  mov     eax, esi
0x180043d5f  mov     rcx, [rbp+57h+var_40]
0x180043d63  xor     rcx, rsp; StackCookie
0x180043d66  call    __security_check_cookie
0x180043d6b  mov     rbx, [rsp+0F0h+arg_18]
  ... truncated ...
```
