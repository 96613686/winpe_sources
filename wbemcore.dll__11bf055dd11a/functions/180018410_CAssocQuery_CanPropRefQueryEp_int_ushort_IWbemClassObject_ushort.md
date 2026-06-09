# CAssocQuery::CanPropRefQueryEp(int,ushort *,IWbemClassObject *,ushort * *)

- ea: `0x180018410`
- end: `0x180018a30`
- name: `?CanPropRefQueryEp@CAssocQuery@@AEAAJHPEAGPEAUIWbemClassObject@@PEAPEAG@Z`
- size: `1568`
- prototype: `__int64 __usercall@<rax>(CAssocQuery *__hidden this@<rcx>, int@<edx>, unsigned __int16 *@<r8>, struct IWbemClassObject *@<r9>, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017890`
- `0x180017b48`
- `0x180095d74`

## callees

- `0x18000b140`
- `0x18000ebd0`
- `0x180018410`
- `0x180018a38`
- `0x18003cfe0`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800185b3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180018732`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18001877d`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800185b3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x180018732`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18001877d`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18001861d`
- `wbemcomn!??ACWStringArray@@QEBAPEAGH@Z` at `0x18001861d`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180018608`
- `wbemcomn!?Size@CWStringArray@@QEBAHXZ` at `0x180018608`
- `wbemcomn!GetMemLogObject` at `0x1800187e2`
- `wbemcomn!GetMemLogObject` at `0x180018860`
- `wbemcomn!GetMemLogObject` at `0x1800188de`
- `wbemcomn!GetMemLogObject` at `0x180018969`
- `wbemcomn!GetMemLogObject` at `0x1800189d8`
- `wbemcomn!GetMemLogObject` at `0x1800187e2`
- `wbemcomn!GetMemLogObject` at `0x180018860`
- `wbemcomn!GetMemLogObject` at `0x1800188de`
- `wbemcomn!GetMemLogObject` at `0x180018969`
- `wbemcomn!GetMemLogObject` at `0x1800189d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800187f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001886e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800188ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018977`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800189e6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800187f0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18001886e`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800188ec`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180018977`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1800189e6`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188cc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800188cc`
- `OLEAUT32!__imp_VariantInit` at `0x1800184a3`
- `OLEAUT32!__imp_VariantInit` at `0x1800184a3`
- `OLEAUT32!__imp_VariantClear` at `0x1800186a7`
- `OLEAUT32!__imp_VariantClear` at `0x1800187b8`
- `OLEAUT32!__imp_VariantClear` at `0x180018836`
- `OLEAUT32!__imp_VariantClear` at `0x180018932`
- `OLEAUT32!__imp_VariantClear` at `0x1800189bd`
- `OLEAUT32!__imp_VariantClear` at `0x1800186a7`
- `OLEAUT32!__imp_VariantClear` at `0x1800187b8`
- `OLEAUT32!__imp_VariantClear` at `0x180018836`
- `OLEAUT32!__imp_VariantClear` at `0x180018932`
- `OLEAUT32!__imp_VariantClear` at `0x1800189bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAssocQuery::CanPropRefQueryEp(
        const unsigned __int16 **this,
        int a2,
        unsigned __int16 *a3,
        struct IWbemClassObject *a4,
        unsigned __int16 **a5)
{
  const unsigned __int16 **v6; // rdi
  unsigned int v7; // r15d
  struct IWbemQualifierSet *v8; // rbx
  BSTR i; // rax
  OLECHAR *v10; // rdi
  WCHAR *j; // rsi
  int v12; // eax
  WCHAR v13; // cx
  CWStringArray *v14; // r12
  WCHAR *v15; // r14
  OLECHAR *k; // rsi
  WCHAR v17; // di
  WCHAR v18; // cx
  int v20; // eax
  int v21; // eax
  CMemoryLog *v22; // rax
  CMemoryLog *v23; // rax
  unsigned __int16 *v24; // rax
  CMemoryLog *v25; // rax
  CMemoryLog *v26; // rax
  CMemoryLog *MemLogObject; // rax
  WCHAR DestStr; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR SrcStr; // [rsp+38h] [rbp-C8h] BYREF
  struct IWbemQualifierSet *v30; // [rsp+40h] [rbp-C0h] BYREF
  struct IWbemQualifierSet *v31; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  CAssocQuery *v33; // [rsp+68h] [rbp-98h]
  OLECHAR psz[511]; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR v35; // [rsp+46Eh] [rbp+36Eh] BYREF

  v6 = this;
  v33 = (CAssocQuery *)this;
  v7 = 0;
  psz[0] = 0;
  if ( !a3 || !a4 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749896LL);
    }
    return 2147749896LL;
  }
  v31 = 0;
  if ( ((int (__fastcall *)(struct IWbemClassObject *, unsigned __int16 *, struct IWbemQualifierSet **))a4->lpVtbl->GetPropertyQualifierSet)(
         a4,
         a3,
         &v31) < 0 )
  {
    v23 = GetMemLogObject();
    CMemoryLog::Write(v23, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749889LL);
    }
    return 2147749889LL;
  }
  v8 = v31;
  v30 = v31;
  VariantInit(&pvarg);
  if ( ((int (__fastcall *)(struct IWbemQualifierSet *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))v31->lpVtbl->Get)(
         v31,
         L"CIMTYPE",
         0,
         &pvarg,
         0) < 0
    || pvarg.vt != 8 )
  {
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids, 2147749889LL);
    }
    VariantClear(&pvarg);
    CReleaseMe::release((CReleaseMe *)&v30);
    return 2147749889LL;
  }
  if ( pvarg.llVal )
  {
    for ( i = pvarg.bstrVal; *i; ++i )
    {
      if ( (unsigned __int64)i >= pvarg.llVal + 1026 )
        break;
    }
    if ( (unsigned __int64)(((__int64)i - pvarg.llVal) >> 1) > 0x200 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, -2147217407);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          193,
          WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids,
          2147749889LL);
      }
      VariantClear(&pvarg);
      if ( v8 )
        ((void (__fastcall *)(struct IWbemQualifierSet *))v8->lpVtbl->Release)(v8);
      v30 = 0;
      return 2147749889LL;
    }
    v10 = psz;
    if ( ((*pvarg.bstrVal - 82) & 0xFFDF) == 0
      && ((*(_WORD *)(pvarg.llVal + 2) - 69) & 0xFFDF) == 0
      && ((*(_WORD *)(pvarg.llVal + 4) - 70) & 0xFFDF) == 0
      && *(_WORD *)(pvarg.llVal + 6) == 58 )
    {
      for ( j = (WCHAR *)(pvarg.llVal + 8); *j; ++j )
      {
        if ( v10 >= &v35 )
          break;
        SrcStr = *j;
        DestStr = 0;
        v12 = LCMapStringW(0x7Fu, 0x200u, &SrcStr, 1, &DestStr, 1);
        v13 = DestStr;
        if ( !v12 )
          v13 = SrcStr;
        *v10++ = v13;
      }
    }
    *v10 = 0;
    v6 = (const unsigned __int16 **)v33;
  }
  if ( !a5 )
    goto LABEL_22;
  *a5 = 0;
  if ( psz[0] )
  {
    v24 = SysAllocString(psz);
    *a5 = v24;
    if ( !v24 )
    {
      v25 = GetMemLogObject();
      CMemoryLog::Write(v25, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          194,
          WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids,
          2147749894LL);
      }
      VariantClear(&pvarg);
      if ( v8 )
        ((void (__fastcall *)(struct IWbemQualifierSet *))v8->lpVtbl->Release)(v8);
      v30 = 0;
      return 2147749894LL;
    }
LABEL_22:
    if ( psz[0] )
    {
      if ( a2 )
      {
        if ( !(unsigned int)wbem_wcsicmp(psz, v6[20]) )
          goto LABEL_39;
      }
      else
      {
        v14 = (CWStringArray *)(v6 + 24);
        while ( (signed int)v7 < CWStringArray::Size(v14) )
        {
          v15 = (WCHAR *)CWStringArray::operator[](v14, v7);
          for ( k = psz; ; ++k )
          {
            v17 = *k;
            if ( *k )
            {
              if ( v17 > 0x7Fu )
              {
                DestStr = *k;
                SrcStr = 0;
                v20 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, &SrcStr, 1);
                v17 = SrcStr;
                if ( !v20 )
                  v17 = DestStr;
              }
              else if ( (unsigned __int16)(v17 - 65) <= 0x19u )
              {
                v17 += 32;
              }
            }
            else if ( !*v15 )
            {
              goto LABEL_39;
            }
            v18 = *v15;
            if ( *v15 > 0x7Fu )
            {
              DestStr = *v15;
              SrcStr = 0;
              v21 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, &SrcStr, 1);
              v18 = SrcStr;
              if ( !v21 )
                v18 = DestStr;
            }
            else if ( (unsigned __int16)(v18 - 65) <= 0x19u )
            {
              v18 += 32;
            }
            if ( v17 != v18 )
              break;
            ++v15;
          }
          ++v7;
        }
        v6 = (const unsigned __int16 **)v33;
      }
    }
  }
  if ( (int)CAssocQuery::CanClassRefReachQueryEp((CAssocQuery *)v6, v31, a2) >= 0 )
  {
LABEL_39:
    VariantClear(&pvarg);
    if ( v8 )
      ((void (__fastcall *)(struct IWbemQualifierSet *))v8->lpVtbl->Release)(v8);
    v30 = 0;
    return 0;
  }
  VariantClear(&pvarg);
  if ( v8 )
    ((void (__fastcall *)(struct IWbemQualifierSet *))v8->lpVtbl->Release)(v8);
  v30 = 0;
  return 2147749890LL;
}

```

## disassembly

```asm
0x180018410  mov     [rsp-8+arg_8], rbx
0x180018415  push    rbp
0x180018416  push    rsi
0x180018417  push    rdi
0x180018418  push    r12
0x18001841a  push    r13
0x18001841c  push    r14
0x18001841e  push    r15
0x180018420  lea     rbp, [rsp-380h]
0x180018428  sub     rsp, 480h
0x18001842f  mov     rax, cs:__security_cookie
0x180018436  xor     rax, rsp
0x180018439  mov     [rbp+3B0h+var_40], rax
0x180018440  mov     r10, r8
0x180018443  mov     r13d, edx
0x180018446  mov     rdi, rcx
0x180018449  mov     [rsp+4B0h+var_448], rcx
0x18001844e  mov     r14, [rbp+3B0h+arg_20]
0x180018455  xor     r15d, r15d
0x180018458  mov     [rsp+4B0h+psz], r15w
0x18001845e  test    r8, r8
0x180018461  jz      loc_1800189D8
0x180018467  test    r9, r9
0x18001846a  jz      loc_1800189D8
0x180018470  mov     [rsp+4B0h+var_468], r15
0x180018475  mov     rax, [r9]
0x180018478  lea     r8, [rsp+4B0h+var_468]
0x18001847d  mov     rdx, r10
0x180018480  mov     rcx, r9
0x180018483  mov     rax, [rax+58h]
0x180018487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001848c  test    eax, eax
0x18001848e  js      loc_180018860
0x180018494  mov     rbx, [rsp+4B0h+var_468]
0x180018499  mov     [rsp+4B0h+var_470], rbx
0x18001849e  lea     rcx, [rsp+4B0h+pvarg]; pvarg
0x1800184a3  call    cs:__imp_VariantInit
0x1800184a9  nop
0x1800184aa  mov     rcx, [rsp+4B0h+var_468]
0x1800184af  mov     rax, [rcx]
0x1800184b2  mov     [rsp+4B0h+lpDestStr], r15
0x1800184b7  lea     r9, [rsp+4B0h+pvarg]
0x1800184bc  xor     r8d, r8d
0x1800184bf  lea     rdx, aCimtype_0; "CIMTYPE"
0x1800184c6  mov     rax, [rax+18h]
0x1800184ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184cf  test    eax, eax
0x1800184d1  js      loc_180018969
0x1800184d7  cmp     word ptr [rsp+4B0h+pvarg], 8
0x1800184dd  jnz     loc_180018969
0x1800184e3  mov     rsi, qword ptr [rsp+4B0h+pvarg+8]
0x1800184e8  test    rsi, rsi
0x1800184eb  jz      loc_1800185E0
0x1800184f1  mov     rax, rsi
0x1800184f4  lea     rcx, [rsi+402h]
0x1800184fb  movzx   edx, word ptr [rsi]
0x1800184fe  test    dx, dx
0x180018501  jz      short loc_180018512
0x180018503  cmp     rax, rcx
0x180018506  jnb     short loc_180018512
0x180018508  add     rax, 2
0x18001850c  cmp     word ptr [rax], 0
0x180018510  jnz     short loc_180018503
0x180018512  sub     rax, rsi
0x180018515  sar     rax, 1
0x180018518  cmp     rax, 200h
0x18001851e  ja      loc_1800187E2
0x180018524  lea     rdi, [rsp+4B0h+psz]
0x180018529  sub     dx, 52h ; 'R'
0x18001852d  mov     ecx, 0FFDFh
0x180018532  test    cx, dx
0x180018535  jnz     loc_1800185D7
0x18001853b  movzx   eax, word ptr [rsi+2]
0x18001853f  sub     ax, 45h ; 'E'
0x180018543  test    cx, ax
0x180018546  jnz     loc_1800185D7
0x18001854c  movzx   eax, word ptr [rsi+4]
0x180018550  sub     ax, 46h ; 'F'
0x180018554  test    cx, ax
0x180018557  jnz     loc_1800185D7
0x18001855d  mov     eax, 3Ah ; ':'
0x180018562  cmp     ax, [rsi+6]
0x180018566  jnz     short loc_1800185D7
0x180018568  add     rsi, 8
0x18001856c  cmp     word ptr [rsi], 0
0x180018570  jz      short loc_1800185D7
0x180018572  lea     rax, [rbp+3B0h+var_42]
0x180018579  cmp     rdi, rax
0x18001857c  jnb     short loc_1800185D7
0x18001857e  movzx   eax, word ptr [rsi]
0x180018581  mov     [rsp+4B0h+SrcStr], ax
0x180018586  mov     [rsp+4B0h+DestStr], r15w
0x18001858c  mov     [rsp+4B0h+cchDest], 1; cchDest
0x180018594  lea     rax, [rsp+4B0h+DestStr]
0x180018599  mov     [rsp+4B0h+lpDestStr], rax; lpDestStr
0x18001859e  mov     r9d, 1; cchSrc
0x1800185a4  lea     r8, [rsp+4B0h+SrcStr]; lpSrcStr
0x1800185a9  mov     edx, 200h; dwMapFlags
0x1800185ae  mov     ecx, 7Fh; Locale
0x1800185b3  call    cs:__imp_LCMapStringW
0x1800185b9  movzx   ecx, [rsp+4B0h+DestStr]
0x1800185be  test    eax, eax
0x1800185c0  cmovz   cx, [rsp+4B0h+SrcStr]
0x1800185c6  mov     [rdi], cx
0x1800185c9  add     rdi, 2
0x1800185cd  add     rsi, 2
0x1800185d1  cmp     word ptr [rsi], 0
0x1800185d5  jnz     short loc_180018572
0x1800185d7  mov     [rdi], r15w
0x1800185db  mov     rdi, [rsp+4B0h+var_448]
0x1800185e0  test    r14, r14
0x1800185e3  jnz     loc_1800188B8
0x1800185e9  cmp     [rsp+4B0h+psz], 0
0x1800185ef  jz      loc_18001868A
0x1800185f5  test    r13d, r13d
0x1800185f8  jnz     loc_180018795
0x1800185fe  lea     r12, [rdi+0C0h]
0x180018605  mov     rcx, r12
0x180018608  call    cs:__imp_?Size@CWStringArray@@QEBAHXZ; CWStringArray::Size(void)
0x18001860e  cmp     r15d, eax
0x180018611  jge     loc_18001895C
0x180018617  mov     edx, r15d
0x18001861a  mov     rcx, r12
0x18001861d  call    cs:__imp_??ACWStringArray@@QEBAPEAGH@Z; CWStringArray::operator[](int)
0x180018623  mov     r14, rax
0x180018626  lea     rsi, [rsp+4B0h+psz]
0x18001862b  nop     dword ptr [rax+rax+00h]
0x180018630  movzx   edi, word ptr [rsi]
0x180018633  test    di, di
0x180018636  jz      short loc_180018681
0x180018638  cmp     di, 7Fh
0x18001863c  ja      loc_1800186FF
0x180018642  lea     eax, [rdi-41h]
0x180018645  cmp     ax, 19h
0x180018649  jbe     short loc_180018675
0x18001864b  movzx   ecx, word ptr [r14]
0x18001864f  cmp     cx, 7Fh
0x180018653  ja      loc_18001874A
0x180018659  lea     eax, [rcx-41h]
0x18001865c  cmp     ax, 19h
0x180018660  jbe     short loc_18001867B
0x180018662  cmp     di, cx
0x180018665  jnz     loc_1800186F7
0x18001866b  add     rsi, 2
0x18001866f  add     r14, 2
0x180018673  jmp     short loc_180018630
0x180018675  add     di, 20h ; ' '
0x180018679  jmp     short loc_18001864B
0x18001867b  add     cx, 20h ; ' '
0x18001867f  jmp     short loc_180018662
0x180018681  cmp     word ptr [r14], 0
0x180018686  jnz     short loc_18001864B
0x180018688  jmp     short loc_1800186A2
0x18001868a  mov     r8d, r13d; int
0x18001868d  mov     rdx, [rsp+4B0h+var_468]; struct IWbemQualifierSet *
0x180018692  mov     rcx, rdi; this
0x180018695  call    ?CanClassRefReachQueryEp@CAssocQuery@@AEAAJPEAUIWbemQualifierSet@@H@Z; CAssocQuery::CanClassRefReachQueryEp(IWbemQualifierSet *,int)
0x18001869a  test    eax, eax
0x18001869c  js      loc_1800187B3
0x1800186a2  lea     rcx, [rsp+4B0h+pvarg]; pvarg
0x1800186a7  call    cs:__imp_VariantClear
0x1800186ad  nop
0x1800186ae  test    rbx, rbx
0x1800186b1  jz      short loc_1800186C2
0x1800186b3  mov     rax, [rbx]
0x1800186b6  mov     rcx, rbx
0x1800186b9  mov     rax, [rax+10h]
0x1800186bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186c2  mov     [rsp+4B0h+var_470], 0
0x1800186cb  xor     eax, eax
0x1800186cd  mov     rcx, [rbp+3B0h+var_40]
0x1800186d4  xor     rcx, rsp; StackCookie
0x1800186d7  call    __security_check_cookie
0x1800186dc  mov     rbx, [rsp+4B0h+arg_8]
0x1800186e4  add     rsp, 480h
0x1800186eb  pop     r15
0x1800186ed  pop     r14
0x1800186ef  pop     r13
0x1800186f1  pop     r12
0x1800186f3  pop     rdi
0x1800186f4  pop     rsi
0x1800186f5  pop     rbp
0x1800186f6  retn
0x1800186f7  inc     r15d
0x1800186fa  jmp     loc_180018605
0x1800186ff  mov     [rsp+4B0h+DestStr], di
0x180018704  xor     eax, eax
0x180018706  mov     [rsp+4B0h+SrcStr], ax
0x18001870b  mov     [rsp+4B0h+cchDest], 1; cchDest
0x180018713  lea     rax, [rsp+4B0h+SrcStr]
0x180018718  mov     [rsp+4B0h+lpDestStr], rax; lpDestStr
0x18001871d  mov     r9d, 1; cchSrc
0x180018723  lea     r8, [rsp+4B0h+DestStr]; lpSrcStr
0x180018728  mov     edx, 100h; dwMapFlags
0x18001872d  mov     ecx, 7Fh; Locale
0x180018732  call    cs:__imp_LCMapStringW
0x180018738  movzx   edi, [rsp+4B0h+SrcStr]
0x18001873d  test    eax, eax
0x18001873f  cmovz   di, [rsp+4B0h+DestStr]
0x180018745  jmp     loc_18001864B
0x18001874a  mov     [rsp+4B0h+DestStr], cx
0x18001874f  xor     eax, eax
0x180018751  mov     [rsp+4B0h+SrcStr], ax
0x180018756  mov     [rsp+4B0h+cchDest], 1; cchDest
0x18001875e  lea     rax, [rsp+4B0h+SrcStr]
0x180018763  mov     [rsp+4B0h+lpDestStr], rax; lpDestStr
0x180018768  mov     r9d, 1; cchSrc
0x18001876e  lea     r8, [rsp+4B0h+DestStr]; lpSrcStr
0x180018773  mov     edx, 100h; dwMapFlags
0x180018778  mov     ecx, 7Fh; Locale
0x18001877d  call    cs:__imp_LCMapStringW
0x180018783  movzx   ecx, [rsp+4B0h+SrcStr]
0x180018788  test    eax, eax
0x18001878a  cmovz   cx, [rsp+4B0h+DestStr]
0x180018790  jmp     loc_180018662
0x180018795  mov     rdx, [rdi+0A0h]; unsigned __int16 *
0x18001879c  lea     rcx, [rsp+4B0h+psz]; unsigned __int16 *
0x1800187a1  call    ?wbem_wcsicmp@@YAHPEBG0@Z; wbem_wcsicmp(ushort const *,ushort const *)
0x1800187a6  test    eax, eax
0x1800187a8  jz      loc_1800186A2
0x1800187ae  jmp     loc_18001868A
0x1800187b3  lea     rcx, [rsp+4B0h+pvarg]; pvarg
0x1800187b8  call    cs:__imp_VariantClear
0x1800187be  nop
0x1800187bf  test    rbx, rbx
0x1800187c2  jz      short loc_1800187D3
0x1800187c4  mov     rax, [rbx]
0x1800187c7  mov     rcx, rbx
0x1800187ca  mov     rax, [rax+10h]
0x1800187ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187d3  mov     [rsp+4B0h+var_470], r15
0x1800187d8  mov     eax, 80041002h
0x1800187dd  jmp     loc_1800186CD
0x1800187e2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800187e8  mov     edx, 80041001h
0x1800187ed  mov     rcx, rax
0x1800187f0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800187f6  lea     rax, WPP_GLOBAL_Control
0x1800187fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180018804  cmp     rcx, rax
0x180018807  jz      short loc_180018831
0x180018809  test    byte ptr [rcx+1Ch], 1
0x18001880d  jz      short loc_180018831
0x18001880f  cmp     byte ptr [rcx+19h], 2
0x180018813  jb      short loc_180018831
0x180018815  mov     edx, 0C1h
0x18001881a  mov     r9d, 80041001h
0x180018820  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x180018827  mov     rcx, [rcx+10h]
0x18001882b  call    WPP_SF_d
0x180018830  nop
0x180018831  lea     rcx, [rsp+4B0h+pvarg]; pvarg
0x180018836  call    cs:__imp_VariantClear
0x18001883c  nop
0x18001883d  test    rbx, rbx
0x180018840  jz      short loc_180018851
0x180018842  mov     rax, [rbx]
0x180018845  mov     rcx, rbx
0x180018848  mov     rax, [rax+10h]
0x18001884c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018851  mov     [rsp+4B0h+var_470], r15
0x180018856  mov     eax, 80041001h
0x18001885b  jmp     loc_1800186CD
0x180018860  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x180018866  mov     edx, 80041001h
0x18001886b  mov     rcx, rax
0x18001886e  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180018874  lea     rax, WPP_GLOBAL_Control
0x18001887b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018882  cmp     rcx, rax
0x180018885  jz      short loc_1800188AE
0x180018887  test    byte ptr [rcx+1Ch], 1
0x18001888b  jz      short loc_1800188AE
0x18001888d  cmp     byte ptr [rcx+19h], 2
0x180018891  jb      short loc_1800188AE
0x180018893  mov     edx, 0BFh
0x180018898  mov     r9d, 80041001h
0x18001889e  lea     r8, WPP_2f04df46b09834ff6d8f033aca1000f6_Traceguids
0x1800188a5  mov     rcx, [rcx+10h]
0x1800188a9  call    WPP_SF_d
0x1800188ae  mov     eax, 80041001h
0x1800188b3  jmp     loc_1800186CD
0x1800188b8  mov     [r14], r15
0x1800188bb  cmp     [rsp+4B0h+psz], 0
0x1800188c1  jz      loc_18001868A
0x1800188c7  lea     rcx, [rsp+4B0h+psz]; psz
0x1800188cc  call    cs:__imp_SysAllocString
0x1800188d2  mov     [r14], rax
0x1800188d5  test    rax, rax
0x1800188d8  jnz     loc_1800185E9
0x1800188de  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x1800188e4  mov     edx, 80041006h
0x1800188e9  mov     rcx, rax
0x1800188ec  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x1800188f2  lea     rax, WPP_GLOBAL_Control
0x1800188f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180018900  cmp     rcx, rax
0x180018903  jz      short loc_18001892D
0x180018905  test    byte ptr [rcx+1Ch], 1
0x180018909  jz      short loc_18001892D
  ... truncated ...
```
