# CShellProvider::InternalCompareUPnPItems(ShellAggregateResultSortContext const *,ShellAggregateResultItem const *,ShellAggregateResultItem const *,_WMCSortItem const *)

- ea: `0x140025210`
- end: `0x140025aa1`
- name: `?InternalCompareUPnPItems@CShellProvider@@SAHPEBUShellAggregateResultSortContext@@PEBUShellAggregateResultItem@@1PEBU_WMCSortItem@@@Z`
- size: `2193`
- prototype: `__int64 __fastcall(const struct ShellAggregateResultSortContext *, const struct ShellAggregateResultItem *, const struct ShellAggregateResultItem *, const struct _WMCSortItem *)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x140025130`
- `0x140074840`

## callees

- `0x140024688`
- `0x140025210`
- `0x140025ab0`
- `0x140025f38`
- `0x140025f74`
- `0x1400396dc`
- `0x14003f17c`
- `0x14005480c`
- `0x14007f2c4`
- `0x140080750`
- `0x14009ad04`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1400256d2`
- `KERNEL32!CompareStringW` at `0x140025986`
- `KERNEL32!CompareStringW` at `0x140025a59`
- `KERNEL32!CompareStringW` at `0x1400256d2`
- `KERNEL32!CompareStringW` at `0x140025986`
- `KERNEL32!CompareStringW` at `0x140025a59`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1400254f8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140025559`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1400254f8`
- `OLEAUT32!__imp_SafeArrayLock` at `0x140025559`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1400259ff`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140025a15`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1400259ff`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x140025a15`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x1400255ca`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x140025646`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x1400255ca`
- `OLEAUT32!__imp_SafeArrayPtrOfIndex` at `0x140025646`
- `ole32!PropVariantClear` at `0x140025291`
- `ole32!PropVariantClear` at `0x14002529b`
- `ole32!PropVariantClear` at `0x1400253d5`
- `ole32!PropVariantClear` at `0x1400253df`
- `ole32!PropVariantClear` at `0x1400257d4`
- `ole32!PropVariantClear` at `0x1400257de`
- `ole32!PropVariantClear` at `0x140025899`
- `ole32!PropVariantClear` at `0x1400258a3`
- `ole32!PropVariantClear` at `0x1400258c3`
- `ole32!PropVariantClear` at `0x1400258cd`
- `ole32!PropVariantClear` at `0x1400258f0`
- `ole32!PropVariantClear` at `0x1400258fa`
- `ole32!PropVariantClear` at `0x140025291`
- `ole32!PropVariantClear` at `0x14002529b`
- `ole32!PropVariantClear` at `0x1400253d5`
- `ole32!PropVariantClear` at `0x1400253df`
- `ole32!PropVariantClear` at `0x1400257d4`
- `ole32!PropVariantClear` at `0x1400257de`
- `ole32!PropVariantClear` at `0x140025899`
- `ole32!PropVariantClear` at `0x1400258a3`
- `ole32!PropVariantClear` at `0x1400258c3`
- `ole32!PropVariantClear` at `0x1400258cd`
- `ole32!PropVariantClear` at `0x1400258f0`
- `ole32!PropVariantClear` at `0x1400258fa`
- `ole32!CoTaskMemAlloc` at `0x140025737`
- `ole32!CoTaskMemAlloc` at `0x140025838`
- `ole32!CoTaskMemAlloc` at `0x140025737`
- `ole32!CoTaskMemAlloc` at `0x140025838`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CShellProvider::InternalCompareUPnPItems(
        const struct ShellAggregateResultSortContext *a1,
        CShellQueryResults **a2,
        CShellQueryResults **a3,
        const struct _WMCSortItem *a4)
{
  const struct ShellAggregateResultSortContext *v6; // r9
  unsigned int v7; // r13d
  unsigned int v8; // ebx
  int v9; // r14d
  int AtomForElementAttribute; // eax
  __int64 v11; // r8
  CShellQueryResults *v13; // rcx
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rdx
  int v16; // r12d
  unsigned __int64 v17; // rdx
  struct IHMEMediaContainer *v18; // rbx
  __int64 (__fastcall *v19)(struct IHMEMediaContainer *, PROPERTYKEY *, _QWORD, _QWORD, PROPVARIANT *); // rax
  int ValueFromContainer; // esi
  int v21; // edi
  CShellQueryResults *v22; // rcx
  unsigned __int64 v23; // rax
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, PROPERTYKEY *, _QWORD, _QWORD, PROPVARIANT *); // rax
  SAFEARRAY *v28; // r10
  SAFEARRAY *lpString2; // r9
  HRESULT v30; // eax
  int v31; // ebx
  HRESULT v32; // eax
  int v33; // ebx
  HRESULT v34; // eax
  int v35; // ebx
  HRESULT v36; // eax
  int v37; // ebx
  bool v38; // cf
  bool v39; // cc
  __int64 v40; // rdx
  __int64 v41; // r8
  struct IHMEMediaContainer *v42; // rbx
  __int64 v43; // rdi
  void *v44; // rax
  int v45; // eax
  void *ppvData; // [rsp+40h] [rbp-40h] BYREF
  struct IHMEMediaContainer *v47; // [rsp+48h] [rbp-38h] BYREF
  PROPVARIANT Buf2[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v49; // [rsp+60h] [rbp-20h]
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v51; // [rsp+78h] [rbp-8h]
  __int64 rgIndices; // [rsp+D8h] [rbp+58h] BYREF

  v6 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqqLL(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, a1, a2, a3, *(_DWORD *)a4, *((_DWORD *)a4 + 1));
  }
  v7 = *(_DWORD *)a4;
  v8 = *((_DWORD *)a4 + 1);
  LODWORD(rgIndices) = v8;
  *(_OWORD *)pvar = 0;
  v51 = 0;
  *(_OWORD *)Buf2 = 0;
  v49 = 0;
  v9 = 0;
  AtomForElementAttribute = CdsValues::GetAtomForElementAttribute(v7, v8, a3, v6);
  if ( (unsigned int)(AtomForElementAttribute - 1) > 0x52 )
    goto LABEL_3;
  v21 = -1;
  if ( !*((_DWORD *)&CShellProvider::s_SortableItemsByCdsValue + AtomForElementAttribute)
    && AtomForElementAttribute != 17 )
  {
    goto LABEL_20;
  }
  v43 = 10LL * AtomForElementAttribute;
  if ( !qword_1400BC4B8[10 * AtomForElementAttribute] )
  {
LABEL_3:
    PropVariantClear(pvar);
    PropVariantClear(Buf2);
    goto LABEL_4;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_LL(*((_QWORD *)WPP_GLOBAL_Control + 2), &_ImageBase, v11, v7, v8);
  }
  v13 = *a2;
  v14 = *((_QWORD *)*a2 + 5);
  v15 = *((unsigned int *)a2 + 2);
  v16 = -2147023728;
  if ( v15 < v14 )
  {
    ppvData = 0;
    CShellQueryResults::GetContainer(v13, v15, (struct IHMEMediaContainer **)&ppvData);
    v44 = CoTaskMemAlloc(0x800u);
    pvar[1] = v44;
    if ( v44 )
    {
      LOWORD(pvar[0]) = 31;
      ValueFromContainer = CShellProvider::GetValueFromContainer(ppvData, v7, v8, v44, 1024);
    }
    else
    {
      ValueFromContainer = -2147024882;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppvData);
  }
  else
  {
    v17 = v15 - v14;
    if ( v17 >= *((_QWORD *)v13 + 9) )
      ATL::AtlThrowImpl(-2147024809);
    _mm_lfence();
    v18 = *(struct IHMEMediaContainer **)(*((_QWORD *)v13 + 8) + 8 * v17);
    v47 = v18;
    (*(void (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v18 + 8LL))(v18);
    v19 = (__int64 (__fastcall *)(struct IHMEMediaContainer *, PROPERTYKEY *, _QWORD, _QWORD, PROPVARIANT *))qword_1400BC4B8[v43];
    if ( v19 )
      ValueFromContainer = v19(v18, (&off_1400BC4B0)[v43], 0, *((_QWORD *)*a2 + 3), pvar);
    else
      ValueFromContainer = -2147023728;
    if ( v18 )
      (*(void (__fastcall **)(struct IHMEMediaContainer *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( ValueFromContainer < 0 )
    goto LABEL_19;
  v22 = *a3;
  v23 = *((_QWORD *)*a3 + 5);
  v24 = *((unsigned int *)a3 + 2);
  if ( v24 < v23 )
  {
    v47 = 0;
    CShellQueryResults::GetContainer(v22, v24, &v47);
    lpString2 = (SAFEARRAY *)CoTaskMemAlloc(0x800u);
    Buf2[1] = lpString2;
    v42 = v47;
    v28 = (SAFEARRAY *)pvar[1];
    if ( pvar[1] )
    {
      LOWORD(Buf2[0]) = 31;
      v16 = CShellProvider::GetValueFromContainer(v47, v7, (unsigned int)rgIndices, lpString2, 1024);
      v28 = (SAFEARRAY *)pvar[1];
      lpString2 = (SAFEARRAY *)Buf2[1];
    }
    else
    {
      v16 = -2147024882;
    }
    if ( v42 )
    {
      (*(void (__fastcall **)(struct IHMEMediaContainer *, __int64, __int64, SAFEARRAY *))(*(_QWORD *)v42 + 16LL))(
        v42,
        v40,
        v41,
        lpString2);
      v28 = (SAFEARRAY *)pvar[1];
      lpString2 = (SAFEARRAY *)Buf2[1];
    }
  }
  else
  {
    v25 = v24 - v23;
    if ( v25 >= *((_QWORD *)v22 + 9) )
      ATL::AtlThrowImpl(-2147024809);
    _mm_lfence();
    v26 = *(_QWORD *)(*((_QWORD *)v22 + 8) + 8 * v25);
    rgIndices = v26;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
    v27 = (__int64 (__fastcall *)(__int64, PROPERTYKEY *, _QWORD, _QWORD, PROPVARIANT *))qword_1400BC4B8[v43];
    if ( v27 )
      v16 = v27(v26, (&off_1400BC4B0)[v43], 0, *((_QWORD *)*a3 + 3), Buf2);
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v28 = (SAFEARRAY *)pvar[1];
    lpString2 = (SAFEARRAY *)Buf2[1];
  }
  if ( v16 < 0 )
    goto LABEL_19;
  if ( !LOWORD(pvar[0]) )
  {
    if ( !LOWORD(Buf2[0]) )
    {
      v9 = 0;
      PropVariantClear(pvar);
      PropVariantClear(Buf2);
      goto LABEL_4;
    }
    v21 = -1;
    goto LABEL_93;
  }
  if ( LOWORD(Buf2[0]) )
  {
    if ( LOWORD(pvar[0]) != LOWORD(Buf2[0]) )
      goto LABEL_19;
    if ( LOWORD(pvar[0]) > 0x15u )
    {
      if ( LOWORD(pvar[0]) != 31 )
      {
        if ( LOWORD(pvar[0]) == 72 )
        {
          v9 = memcmp_0(v28, lpString2, 0x10u);
        }
        else if ( LOWORD(pvar[0]) == 8204 )
        {
          v30 = SafeArrayLock(v28);
          v31 = v30;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v30 >> 31) & 0xFFFFFFFD) + 5 )
          {
            WPP_SF_dq(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              208,
              &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
              (unsigned int)v30,
              pvar[1]);
          }
          if ( v31 >= 0 )
          {
            v32 = SafeArrayLock((SAFEARRAY *)Buf2[1]);
            v33 = v32;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v32 >> 31) & 0xFFFFFFFD) + 5 )
            {
              WPP_SF_dq(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                209,
                &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
                (unsigned int)v32,
                Buf2[1]);
            }
            if ( v33 < 0 )
            {
              v21 = -1;
            }
            else
            {
              LODWORD(rgIndices) = 0;
              ppvData = 0;
              v34 = SafeArrayPtrOfIndex((SAFEARRAY *)pvar[1], (LONG *)&rgIndices, &ppvData);
              v35 = v34;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v34 >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_dq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  210,
                  &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
                  (unsigned int)v34,
                  ppvData);
              }
              if ( v35 < 0 || *(_WORD *)ppvData != 8 )
                goto LABEL_111;
              v47 = 0;
              v36 = SafeArrayPtrOfIndex((SAFEARRAY *)Buf2[1], (LONG *)&rgIndices, (void **)&v47);
              v37 = v36;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
                && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= ((v36 >> 31) & 0xFFFFFFFD) + 5 )
              {
                WPP_SF_dq(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  211,
                  &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
                  (unsigned int)v36,
                  v47);
              }
              if ( v37 >= 0 )
              {
                v21 = -1;
                if ( *(_WORD *)v47 == 8 )
                {
                  v9 = CompareStringW(0x400u, 1u, *((PCNZWCH *)ppvData + 1), -1, *((PCNZWCH *)v47 + 1), -1);
                  if ( v9 )
                    v9 -= 2;
                }
              }
              else
              {
LABEL_111:
                v21 = -1;
              }
              SafeArrayUnlock((SAFEARRAY *)Buf2[1]);
            }
            SafeArrayUnlock((SAFEARRAY *)pvar[1]);
            goto LABEL_20;
          }
        }
LABEL_19:
        v21 = -1;
        goto LABEL_20;
      }
      v21 = -1;
      v9 = CompareStringW(0x400u, 1u, &v28->cDims, -1, &lpString2->cDims, -1);
      if ( v9 )
        v9 -= 2;
LABEL_20:
      PropVariantClear(pvar);
      PropVariantClear(Buf2);
      if ( !v9 )
        goto LABEL_4;
      goto LABEL_21;
    }
    switch ( LOWORD(pvar[0]) )
    {
      case 0x15u:
        v38 = v28 < lpString2;
        v39 = v28 <= lpString2;
        break;
      case 7u:
        v21 = -1;
        if ( *(double *)&Buf2[1] <= *(double *)&pvar[1] )
        {
          if ( *(double *)&pvar[1] > *(double *)&Buf2[1] )
            v9 = 1;
          goto LABEL_20;
        }
        goto LABEL_93;
      case 8u:
        v21 = -1;
        v45 = CompareStringW(0x400u, 1u, &v28->cDims, -1, &lpString2->cDims, -1);
        v9 = v45 - 2;
        if ( !v45 )
          v9 = 0;
        goto LABEL_20;
      case 0xBu:
        v21 = -1;
        if ( LOWORD(pvar[1]) )
        {
          if ( !LOWORD(Buf2[1]) )
            v9 = 1;
        }
        else if ( LOWORD(Buf2[1]) == 0xFFFF )
        {
          v9 = -1;
        }
        goto LABEL_20;
      case 0x13u:
        v38 = LODWORD(pvar[1]) < LODWORD(Buf2[1]);
        v39 = LODWORD(pvar[1]) <= LODWORD(Buf2[1]);
        break;
      default:
        goto LABEL_19;
    }
    v21 = -1;
    if ( !v38 )
    {
      if ( !v39 )
        v9 = 1;
      goto LABEL_20;
    }
LABEL_93:
    v9 = -1;
    PropVariantClear(pvar);
    PropVariantClear(Buf2);
    goto LABEL_21;
  }
  v9 = 1;
  PropVariantClear(pvar);
  PropVariantClear(Buf2);
  v21 = -1;
LABEL_21:
  if ( !*((_DWORD *)a4 + 2) )
  {
    if ( v9 < 0 )
      v21 = 1;
    v9 = v21;
  }
LABEL_4:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      212,
      &WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids,
      (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140025210  mov     [rsp-38h+arg_0], rbx
0x140025215  mov     [rsp-38h+arg_10], r8
0x14002521a  push    rbp
0x14002521b  push    rsi
0x14002521c  push    rdi
0x14002521d  push    r12
0x14002521f  push    r13
0x140025221  push    r14
0x140025223  push    r15
0x140025225  mov     rbp, rsp
0x140025228  sub     rsp, 80h
0x14002522f  mov     r15, r9
0x140025232  mov     rsi, rdx
0x140025235  mov     r9, rcx
0x140025238  lea     r12, WPP_GLOBAL_Control
0x14002523f  mov     rcx, cs:WPP_GLOBAL_Control
0x140025246  cmp     rcx, r12
0x140025249  jnz     loc_1400252D5
0x14002524f  mov     r13d, [r15]
0x140025252  mov     ebx, [r15+4]
0x140025256  mov     dword ptr [rbp+rgIndices], ebx
0x140025259  xorps   xmm0, xmm0
0x14002525c  xor     eax, eax
0x14002525e  movups  xmmword ptr [rbp+pvar], xmm0
0x140025262  mov     [rbp+var_8], rax
0x140025266  xorps   xmm1, xmm1
0x140025269  movups  xmmword ptr [rbp+Buf2], xmm1
0x14002526d  mov     [rbp+var_20], rax
0x140025271  xor     r14d, r14d
0x140025274  mov     edx, ebx
0x140025276  mov     ecx, r13d
0x140025279  call    ?GetAtomForElementAttribute@CdsValues@@SA?AW4Value@CdsValue@@W4CDS_ELEMENT_VALUE@@W4CDS_ATTRIBUTE_VALUE@@@Z; CdsValues::GetAtomForElementAttribute(CDS_ELEMENT_VALUE,CDS_ATTRIBUTE_VALUE)
0x14002527e  movsxd  rcx, eax
0x140025281  lea     eax, [rcx-1]
0x140025284  cmp     eax, 52h ; 'R'
0x140025287  jbe     loc_1400257A5
0x14002528d  lea     rcx, [rbp+pvar]; pvar
0x140025291  call    cs:__imp_PropVariantClear
0x140025297  lea     rcx, [rbp+Buf2]; pvar
0x14002529b  call    cs:__imp_PropVariantClear
0x1400252a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400252a8  cmp     rcx, r12
0x1400252ab  jz      short loc_1400252B7
0x1400252ad  test    byte ptr [rcx+1Ch], 1
0x1400252b1  jnz     loc_140025A7A
0x1400252b7  mov     eax, r14d
0x1400252ba  mov     rbx, [rsp+80h+arg_0]
0x1400252c2  add     rsp, 80h
0x1400252c9  pop     r15
0x1400252cb  pop     r14
0x1400252cd  pop     r13
0x1400252cf  pop     r12
0x1400252d1  pop     rdi
0x1400252d2  pop     rsi
0x1400252d3  pop     rbp
0x1400252d4  retn
0x1400252d5  test    byte ptr [rcx+1Ch], 1
0x1400252d9  jz      loc_14002524F
0x1400252df  cmp     byte ptr [rcx+19h], 5
0x1400252e3  jb      loc_14002524F
0x1400252e9  mov     eax, [r15+4]
0x1400252ed  mov     [rsp+80h+var_48], eax
0x1400252f1  mov     eax, [r15]
0x1400252f4  mov     [rsp+80h+var_50], eax
0x1400252f8  mov     qword ptr [rsp+80h+cchCount2], r8
0x1400252fd  mov     [rsp+80h+lpString2], rsi
0x140025302  mov     rcx, [rcx+10h]
0x140025306  call    WPP_SF_qqqLL
0x14002530b  jmp     loc_14002524F
0x140025310  mov     rcx, cs:WPP_GLOBAL_Control
0x140025317  cmp     rcx, r12
0x14002531a  jz      short loc_140025326
0x14002531c  test    byte ptr [rcx+1Ch], 2
0x140025320  jnz     loc_1400257F4
0x140025326  mov     rcx, [rsi]; this
0x140025329  mov     rax, [rcx+28h]
0x14002532d  mov     edx, [rsi+8]; unsigned __int64
0x140025330  mov     r12d, 80070490h
0x140025336  cmp     rdx, rax
0x140025339  jb      loc_140025826
0x14002533f  sub     rdx, rax
0x140025342  cmp     rdx, [rcx+48h]
0x140025346  jnb     loc_140025813
0x14002534c  lfence
0x14002534f  mov     rbx, [rcx+40h]
0x140025353  mov     rbx, [rbx+rdx*8]
0x140025357  mov     [rbp+var_38], rbx
0x14002535b  mov     rax, [rbx]
0x14002535e  mov     rcx, rbx
0x140025361  mov     rax, [rax+8]
0x140025365  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002536a  lea     rdx, __ImageBase
0x140025371  mov     rax, rva qword_1400BC4B8[rdx+rdi*8]
0x140025379  test    rax, rax
0x14002537c  jz      loc_14002581E
0x140025382  mov     r9, [rsi]
0x140025385  lea     rcx, [rbp+pvar]
0x140025389  mov     [rsp+80h+lpString2], rcx
0x14002538e  mov     r9, [r9+18h]
0x140025392  xor     r8d, r8d
0x140025395  mov     rdx, rva off_1400BC4B0[rdx+rdi*8]
0x14002539d  mov     rcx, rbx
0x1400253a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400253a5  mov     esi, eax
0x1400253a7  test    rbx, rbx
0x1400253aa  jz      short loc_1400253BC
0x1400253ac  mov     rax, [rbx]
0x1400253af  mov     rcx, rbx
0x1400253b2  mov     rax, [rax+10h]
0x1400253b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400253bb  nop
0x1400253bc  test    esi, esi
0x1400253be  jns     short loc_140025407
0x1400253c0  lea     r12, WPP_GLOBAL_Control
0x1400253c7  mov     edi, 0FFFFFFFFh
0x1400253cc  mov     ebx, 1
0x1400253d1  lea     rcx, [rbp+pvar]; pvar
0x1400253d5  call    cs:__imp_PropVariantClear
0x1400253db  lea     rcx, [rbp+Buf2]; pvar
0x1400253df  call    cs:__imp_PropVariantClear
0x1400253e5  test    r14d, r14d
0x1400253e8  jz      loc_1400252A1
0x1400253ee  cmp     dword ptr [r15+8], 0
0x1400253f3  jnz     loc_1400252A1
0x1400253f9  test    r14d, r14d
0x1400253fc  cmovs   edi, ebx
0x1400253ff  mov     r14d, edi
0x140025402  jmp     loc_1400252A1
0x140025407  mov     rsi, [rbp+arg_10]
0x14002540b  mov     rcx, [rsi]; this
0x14002540e  mov     rax, [rcx+28h]
0x140025412  mov     edx, [rsi+8]; unsigned __int64
0x140025415  cmp     rdx, rax
0x140025418  jb      loc_140025721
0x14002541e  sub     rdx, rax
0x140025421  cmp     rdx, [rcx+48h]
0x140025425  jnb     loc_140025881
0x14002542b  lfence
0x14002542e  mov     rbx, [rcx+40h]
0x140025432  mov     rbx, [rbx+rdx*8]
0x140025436  mov     [rbp+rgIndices], rbx
0x14002543a  mov     rax, [rbx]
0x14002543d  mov     rcx, rbx
0x140025440  mov     rax, [rax+8]
0x140025444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025449  lea     rdx, __ImageBase
0x140025450  mov     rax, rva qword_1400BC4B8[rdx+rdi*8]
0x140025458  test    rax, rax
0x14002545b  jz      short loc_140025483
0x14002545d  mov     r9, [rsi]
0x140025460  lea     rcx, [rbp+Buf2]
0x140025464  mov     [rsp+80h+lpString2], rcx
0x140025469  mov     r9, [r9+18h]
0x14002546d  xor     r8d, r8d
0x140025470  mov     rdx, rva off_1400BC4B0[rdx+rdi*8]
0x140025478  mov     rcx, rbx
0x14002547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025480  mov     r12d, eax
0x140025483  test    rbx, rbx
0x140025486  jz      short loc_140025498
0x140025488  mov     rax, [rbx]
0x14002548b  mov     rcx, rbx
0x14002548e  mov     rax, [rax+10h]
0x140025492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025497  nop
0x140025498  mov     r10, [rbp+pvar+8]
0x14002549c  mov     r9, [rbp+Buf2+8]
0x1400254a0  test    r12d, r12d
0x1400254a3  js      loc_1400253C0
0x1400254a9  xor     eax, eax
0x1400254ab  movzx   ecx, word ptr [rbp+pvar]
0x1400254af  cmp     ax, cx
0x1400254b2  jz      loc_14002588C
0x1400254b8  movzx   edx, word ptr [rbp+Buf2]
0x1400254bc  cmp     ax, dx
0x1400254bf  jz      loc_1400258E4
0x1400254c5  cmp     cx, dx
0x1400254c8  jnz     loc_1400253C0
0x1400254ce  cmp     ecx, 15h
0x1400254d1  jbe     loc_1400256EC
0x1400254d7  cmp     ecx, 1Fh
0x1400254da  jz      loc_140025A39
0x1400254e0  cmp     ecx, 48h ; 'H'
0x1400254e3  jz      loc_140025A20
0x1400254e9  cmp     ecx, 200Ch
0x1400254ef  jnz     loc_1400253C0
0x1400254f5  mov     rcx, r10; psa
0x1400254f8  call    cs:__imp_SafeArrayLock
0x1400254fe  mov     ebx, eax
0x140025500  mov     rcx, cs:WPP_GLOBAL_Control
0x140025507  lea     r12, WPP_GLOBAL_Control
0x14002550e  cmp     rcx, r12
0x140025511  jz      short loc_14002554D
0x140025513  test    byte ptr [rcx+1Ch], 2
0x140025517  jz      short loc_14002554D
0x140025519  mov     edx, eax
0x14002551b  sar     edx, 1Fh
0x14002551e  and     edx, 0FFFFFFFDh
0x140025521  add     edx, 5
0x140025524  movzx   eax, byte ptr [rcx+19h]
0x140025528  cmp     eax, edx
0x14002552a  jb      short loc_14002554D
0x14002552c  mov     edx, 0D0h
0x140025531  mov     rax, [rbp+pvar+8]
0x140025535  mov     [rsp+80h+lpString2], rax
0x14002553a  mov     r9d, ebx
0x14002553d  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x140025544  mov     rcx, [rcx+10h]
0x140025548  call    WPP_SF_dq
0x14002554d  test    ebx, ebx
0x14002554f  js      loc_1400253C7
0x140025555  mov     rcx, [rbp+Buf2+8]; psa
0x140025559  call    cs:__imp_SafeArrayLock
0x14002555f  mov     ebx, eax
0x140025561  mov     rcx, cs:WPP_GLOBAL_Control
0x140025568  cmp     rcx, r12
0x14002556b  jz      short loc_1400255A7
0x14002556d  test    byte ptr [rcx+1Ch], 2
0x140025571  jz      short loc_1400255A7
0x140025573  mov     edx, eax
0x140025575  sar     edx, 1Fh
0x140025578  and     edx, 0FFFFFFFDh
0x14002557b  add     edx, 5
0x14002557e  movzx   eax, byte ptr [rcx+19h]
0x140025582  cmp     eax, edx
0x140025584  jb      short loc_1400255A7
0x140025586  mov     edx, 0D1h
0x14002558b  mov     rax, [rbp+Buf2+8]
0x14002558f  mov     [rsp+80h+lpString2], rax
0x140025594  mov     r9d, ebx
0x140025597  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14002559e  mov     rcx, [rcx+10h]
0x1400255a2  call    WPP_SF_dq
0x1400255a7  test    ebx, ebx
0x1400255a9  js      loc_140025A07
0x1400255af  mov     dword ptr [rbp+rgIndices], 0
0x1400255b6  mov     [rbp+ppvData], 0
0x1400255be  lea     r8, [rbp+ppvData]; ppvData
0x1400255c2  lea     rdx, [rbp+rgIndices]; rgIndices
0x1400255c6  mov     rcx, [rbp+pvar+8]; psa
0x1400255ca  call    cs:__imp_SafeArrayPtrOfIndex
0x1400255d0  mov     ebx, eax
0x1400255d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400255d9  cmp     rcx, r12
0x1400255dc  jz      short loc_140025618
0x1400255de  test    byte ptr [rcx+1Ch], 2
0x1400255e2  jz      short loc_140025618
0x1400255e4  mov     edx, eax
0x1400255e6  sar     edx, 1Fh
0x1400255e9  and     edx, 0FFFFFFFDh
0x1400255ec  add     edx, 5
0x1400255ef  movzx   eax, byte ptr [rcx+19h]
0x1400255f3  cmp     eax, edx
0x1400255f5  jb      short loc_140025618
0x1400255f7  mov     edx, 0D2h
0x1400255fc  mov     rax, [rbp+ppvData]
0x140025600  mov     [rsp+80h+lpString2], rax
0x140025605  mov     r9d, ebx
0x140025608  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14002560f  mov     rcx, [rcx+10h]
0x140025613  call    WPP_SF_dq
0x140025618  test    ebx, ebx
0x14002561a  js      loc_1400259F1
0x140025620  mov     edi, 8
0x140025625  mov     rax, [rbp+ppvData]
0x140025629  cmp     di, [rax]
0x14002562c  jnz     loc_1400259F1
0x140025632  mov     [rbp+var_38], 0
0x14002563a  lea     r8, [rbp+var_38]; ppvData
0x14002563e  lea     rdx, [rbp+rgIndices]; rgIndices
0x140025642  mov     rcx, [rbp+Buf2+8]; psa
0x140025646  call    cs:__imp_SafeArrayPtrOfIndex
0x14002564c  mov     ebx, eax
0x14002564e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025655  cmp     rcx, r12
0x140025658  jz      short loc_140025694
0x14002565a  test    byte ptr [rcx+1Ch], 2
0x14002565e  jz      short loc_140025694
0x140025660  mov     edx, eax
0x140025662  sar     edx, 1Fh
0x140025665  and     edx, 0FFFFFFFDh
0x140025668  add     edx, 5
0x14002566b  movzx   eax, byte ptr [rcx+19h]
0x14002566f  cmp     eax, edx
0x140025671  jb      short loc_140025694
0x140025673  mov     edx, 0D3h
0x140025678  mov     rax, [rbp+var_38]
0x14002567c  mov     [rsp+80h+lpString2], rax
0x140025681  mov     r9d, ebx
0x140025684  lea     r8, WPP_5803cf0ad32a310b66152e4dc6018844_Traceguids
0x14002568b  mov     rcx, [rcx+10h]
0x14002568f  call    WPP_SF_dq
0x140025694  test    ebx, ebx
0x140025696  mov     ebx, 1
0x14002569b  js      loc_1400259F6
0x1400256a1  mov     rax, [rbp+var_38]
0x1400256a5  cmp     di, [rax]
0x1400256a8  mov     edi, 0FFFFFFFFh
0x1400256ad  jnz     loc_1400259FB
0x1400256b3  mov     [rsp+80h+cchCount2], edi; cchCount2
  ... truncated ...
```
