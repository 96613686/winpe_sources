# SDOGetAdvancedAttributesInfo(ISdoDictionaryOld *,bool,_ATTRIBUTERESTRICTIONS,ulong *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *)

- ea: `0x18002b1c0`
- end: `0x18002c0b1`
- name: `?SDOGetAdvancedAttributesInfo@@YAJPEAUISdoDictionaryOld@@_NW4_ATTRIBUTERESTRICTIONS@@PEAKPEAUtagVARIANT@@4444@Z`
- size: `3825`
- prototype: `__int64 __fastcall(struct ISdoDictionaryOld *, bool, enum _ATTRIBUTERESTRICTIONS, unsigned int *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002e560`
- `0x18002e610`

## callees

- `0x1800241bb`
- `0x180024ddc`
- `0x18002b1c0`
- `0x18002cca4`
- `0x18002cd00`
- `0x180042844`
- `0x180042a80`
- `0x180055030`
- `0x1800550f0`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002bd2d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bd58`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bd2d`
- `OLEAUT32!__imp_SysAllocString` at `0x18002bd58`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2a3`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2b0`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2ba`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2c7`
- `OLEAUT32!__imp_VariantInit` at `0x18002bbfc`
- `OLEAUT32!__imp_VariantInit` at `0x18002bc09`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2a3`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2b0`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2ba`
- `OLEAUT32!__imp_VariantInit` at `0x18002b2c7`
- `OLEAUT32!__imp_VariantInit` at `0x18002bbfc`
- `OLEAUT32!__imp_VariantInit` at `0x18002bc09`
- `OLEAUT32!__imp_VariantClear` at `0x18002bd72`
- `OLEAUT32!__imp_VariantClear` at `0x18002bd7f`
- `OLEAUT32!__imp_VariantClear` at `0x18002bd72`
- `OLEAUT32!__imp_VariantClear` at `0x18002bd7f`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bc2c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf2c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf49`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf66`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf83`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bfa4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bc2c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf2c`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf49`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf66`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bf83`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002bfa4`

## string_xrefs

- `0x18002be9a`: `Not enough memory to create safearray of Info Ids`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SDOGetAdvancedAttributesInfo(
        struct ISdoDictionaryOld *a1,
        char a2,
        enum _ATTRIBUTERESTRICTIONS a3,
        unsigned int *a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6,
        struct tagVARIANT *a7,
        struct tagVARIANT *a8,
        struct tagVARIANT *a9)
{
  void **v10; // r14
  int v11; // ebx
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rbx
  void **v14; // rax
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  void *v17; // rsp
  _DWORD *v18; // rax
  __int64 v19; // rdx
  void **v20; // r13
  unsigned __int64 v21; // rcx
  __int64 v22; // rax
  void *v23; // rsp
  _DWORD *v24; // rax
  unsigned __int64 v25; // r15
  int *v26; // rax
  __int64 v27; // rcx
  unsigned __int64 v28; // rcx
  void *v29; // rsp
  void *v30; // rsp
  int *v31; // rax
  void **v32; // r12
  __int64 v33; // rax
  void *v34; // rsp
  _DWORD *v35; // rax
  __int64 v36; // rcx
  void *v37; // rsp
  void *v38; // rsp
  _DWORD *v39; // rax
  void **v40; // r15
  __int64 v41; // rcx
  unsigned __int64 v42; // rcx
  void *v43; // rsp
  void *v44; // rsp
  _DWORD *v45; // rax
  _QWORD *v46; // rdi
  unsigned __int64 v47; // rdx
  unsigned __int64 v48; // r8
  SAFEARRAYBOUND v49; // rcx
  unsigned __int64 v50; // rdi
  size_t v51; // rdi
  int v52; // edx
  char *v53; // rax
  SAFEARRAYBOUND v54; // rbx
  SAFEARRAY *v55; // rax
  _DWORD *pvData; // rcx
  int v57; // edx
  unsigned __int64 v58; // rdx
  void *v59; // rcx
  int v60; // eax
  char v61; // r8
  const OLECHAR *v62; // rcx
  BSTR v63; // rax
  const OLECHAR *v64; // rcx
  BSTR v65; // rax
  __int64 v66; // rdx
  SAFEARRAY *v68; // r13
  SAFEARRAY *v69; // r8
  char *v70; // r9
  __int64 v71; // rdx
  unsigned __int64 v72; // rcx
  struct ISdoDictionaryOld *v73; // r10
  unsigned __int64 v74; // r11
  unsigned int *v75; // r13
  struct ISdoDictionaryOldVtbl *v76; // rax
  __int64 v77; // r8
  void *v78; // rax
  _BYTE v79[32]; // [rsp+0h] [rbp-30h] BYREF
  int v80; // [rsp+30h] [rbp+0h] BYREF
  void *v81; // [rsp+38h] [rbp+8h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp+10h] BYREF
  char v83; // [rsp+48h] [rbp+18h]
  unsigned __int64 v84; // [rsp+50h] [rbp+20h]
  SAFEARRAYBOUND v85; // [rsp+58h] [rbp+28h] BYREF
  __int64 v86; // [rsp+60h] [rbp+30h]
  unsigned int *v87; // [rsp+68h] [rbp+38h]
  enum _ATTRIBUTERESTRICTIONS v88; // [rsp+70h] [rbp+40h]
  SAFEARRAY *v89; // [rsp+78h] [rbp+48h] BYREF
  SAFEARRAY *v90; // [rsp+80h] [rbp+50h] BYREF
  SAFEARRAY *v91; // [rsp+88h] [rbp+58h] BYREF
  SAFEARRAY *v92; // [rsp+90h] [rbp+60h] BYREF
  struct ISdoDictionaryOld *v93; // [rsp+98h] [rbp+68h]
  VARIANTARG v94; // [rsp+A0h] [rbp+70h] BYREF
  VARIANTARG v95; // [rsp+B8h] [rbp+88h] BYREF
  _QWORD v96[2]; // [rsp+D0h] [rbp+A0h] BYREF
  _QWORD v97[2]; // [rsp+E0h] [rbp+B0h] BYREF
  _QWORD v98[2]; // [rsp+F0h] [rbp+C0h] BYREF
  _QWORD v99[2]; // [rsp+100h] [rbp+D0h] BYREF
  VARIANTARG pvarg; // [rsp+110h] [rbp+E0h] BYREF
  VARIANTARG v101; // [rsp+128h] [rbp+F8h] BYREF

  v87 = a4;
  v88 = a3;
  v83 = a2;
  v93 = a1;
  v10 = 0;
  v85 = 0;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v89 = 0;
  if ( !a1 || !a4 || !a5 || !a6 || !a7 || !a9 )
    return 2147500035LL;
  *a4 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v101, 0, sizeof(v101));
  memset(&v94, 0, sizeof(v94));
  memset(&v95, 0, sizeof(v95));
  VariantInit(&pvarg);
  VariantInit(&v101);
  VariantInit(&v94);
  VariantInit(&v95);
  v11 = ((__int64 (__fastcall *)(struct ISdoDictionaryOld *, VARIANTARG *, VARIANTARG *))a1->lpVtbl->EnumAttributes)(
          a1,
          &pvarg,
          &v101);
  v80 = v11;
  v99[0] = &v80;
  v99[1] = &v90;
  v98[0] = &v80;
  v98[1] = &v91;
  v97[0] = &v80;
  v97[1] = &v92;
  v96[0] = &v80;
  v96[1] = &v89;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      WppDbgPrint("pDict->EnumAttributes failed with 0x%x");
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        (unsigned int)WPP_9723200e762c301790c48b34da45e129_Traceguids,
        (unsigned int)"NPSSDO",
        v80);
      goto LABEL_12;
    }
    goto LABEL_195;
  }
  v12 = *(unsigned int *)(pvarg.llVal + 24);
  v86 = *(_QWORD *)(pvarg.llVal + 16);
  v13 = 4 * v12;
  v14 = 0;
  rgsabound = 0;
  if ( 4 * v12 && v13 <= g_ulMaxStackAllocSize && v13 + g_ulAdditionalProbeSize + 8 >= v13 )
  {
    if ( (unsigned int)VerifyStackAvailable() )
    {
      v15 = v13 + 8;
      v16 = v13 + 23;
      if ( v13 + 23 <= v13 + 8 )
        v16 = 0xFFFFFFFFFFFFFF0LL;
      v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
      v14 = (void **)&v80;
      rgsabound = (SAFEARRAYBOUND)&v80;
      if ( v79 != (_BYTE *)-48LL )
      {
        v80 = 1801679955;
        v14 = &v81;
        rgsabound = (SAFEARRAYBOUND)&v81;
        if ( &v81 )
          goto LABEL_26;
      }
    }
    else
    {
      v14 = (void **)rgsabound;
    }
  }
  v15 = v13 + 8;
  if ( v13 + 8 >= v13 )
  {
    v18 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64))g_pfnAllocate)(v13 + 8);
    rgsabound = (SAFEARRAYBOUND)v18;
    if ( !v18 )
      goto LABEL_27;
    *v18 = 1885431112;
    v14 = (void **)(v18 + 2);
    rgsabound = (SAFEARRAYBOUND)v14;
  }
LABEL_26:
  if ( !v14 )
  {
LABEL_27:
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_116;
    }
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store attr"
                "ibute information");
    v19 = 45;
LABEL_115:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, WPP_9723200e762c301790c48b34da45e129_Traceguids, "NPSSDO");
LABEL_116:
    v11 = -2147024882;
    goto LABEL_195;
  }
  v20 = 0;
  if ( !v13
    || v13 > g_ulMaxStackAllocSize
    || v13 + g_ulAdditionalProbeSize + 8 < v13
    || !(unsigned int)VerifyStackAvailable() )
  {
    v21 = v15;
LABEL_41:
    if ( v21 >= v13 )
    {
      v24 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v20 = (void **)v24;
      if ( v24 )
      {
        *v24 = 1885431112;
        v20 = (void **)(v24 + 2);
      }
    }
    goto LABEL_44;
  }
  v21 = v13 + 8;
  v22 = v13 + 23;
  if ( v13 + 23 <= v13 + 8 )
    v22 = 0xFFFFFFFFFFFFFF0LL;
  v23 = alloca(v22 & 0xFFFFFFFFFFFFFFF0uLL);
  v20 = (void **)&v80;
  if ( v79 == (_BYTE *)-48LL )
    goto LABEL_41;
  v80 = 1801679955;
  v20 = &v81;
  if ( !&v81 )
    goto LABEL_41;
LABEL_44:
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_116;
    }
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store attr"
                "ibute information");
    v19 = 46;
    goto LABEL_115;
  }
  v25 = 8 * v12;
  v26 = 0;
  v81 = 0;
  if ( 8 * v12 && v25 <= g_ulMaxStackAllocSize && v25 + g_ulAdditionalProbeSize + 8 >= v25 )
  {
    if ( (unsigned int)VerifyStackAvailable() )
    {
      v27 = v25 + 23;
      if ( v25 + 23 <= v25 + 8 )
        v27 = 0xFFFFFFFFFFFFFF0LL;
      v28 = v27 & 0xFFFFFFFFFFFFFFF0uLL;
      v29 = alloca(v28);
      v30 = alloca(v28);
      v26 = &v80;
      v81 = &v80;
      if ( v79 != (_BYTE *)-48LL )
      {
        v80 = 1801679955;
        v26 = (int *)&v81;
        v81 = &v81;
        if ( &v81 )
          goto LABEL_62;
      }
    }
    else
    {
      v26 = (int *)v81;
    }
  }
  if ( v25 + 8 >= v25 )
  {
    v31 = (int *)((__int64 (*)(void))g_pfnAllocate)();
    v81 = v31;
    if ( !v31 )
      goto LABEL_63;
    *v31 = 1885431112;
    v26 = v31 + 2;
    v81 = v26;
  }
LABEL_62:
  if ( !v26 )
  {
LABEL_63:
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_116;
    }
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store attr"
                "ibute information");
    v19 = 47;
    goto LABEL_115;
  }
  v32 = 0;
  if ( !v13
    || v13 > g_ulMaxStackAllocSize
    || v13 + g_ulAdditionalProbeSize + 8 < v13
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_210;
  }
  v33 = v15 + 15;
  if ( v15 + 15 < v15 )
    v33 = 0xFFFFFFFFFFFFFF0LL;
  v34 = alloca(v33 & 0xFFFFFFFFFFFFFFF0uLL);
  v32 = (void **)&v80;
  if ( v79 == (_BYTE *)-48LL || (v80 = 1801679955, (v32 = &v81) == 0) )
  {
LABEL_210:
    if ( v15 >= v13 )
    {
      v35 = (_DWORD *)((__int64 (__fastcall *)(unsigned __int64))g_pfnAllocate)(v15);
      v32 = (void **)v35;
      if ( v35 )
      {
        *v35 = 1885431112;
        v32 = (void **)(v35 + 2);
      }
    }
  }
  if ( !v32 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_116;
    }
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store attr"
                "ibute information");
    v19 = 48;
    goto LABEL_115;
  }
  if ( !v25
    || v25 > g_ulMaxStackAllocSize
    || v25 + g_ulAdditionalProbeSize + 8 < v25
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_211;
  }
  v36 = v25 + 23;
  if ( v25 + 23 <= v25 + 8 )
    v36 = 0xFFFFFFFFFFFFFF0LL;
  v37 = alloca(v36 & 0xFFFFFFFFFFFFFFF0uLL);
  v38 = alloca(v36 & 0xFFFFFFFFFFFFFFF0uLL);
  v10 = (void **)&v80;
  if ( v79 == (_BYTE *)-48LL || (v80 = 1801679955, (v10 = &v81) == 0) )
  {
LABEL_211:
    if ( v25 + 8 >= v25 )
    {
      v39 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v10 = (void **)v39;
      if ( v39 )
      {
        *v39 = 1885431112;
        v10 = (void **)(v39 + 2);
      }
    }
  }
  if ( !v10 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_116;
    }
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store attr"
                "ibute information");
    v19 = 49;
    goto LABEL_115;
  }
  v40 = 0;
  if ( !v12
    || v12 > g_ulMaxStackAllocSize
    || v12 + g_ulAdditionalProbeSize + 8 < v12
    || !(unsigned int)VerifyStackAvailable() )
  {
    goto LABEL_212;
  }
  v41 = v12 + 23;
  if ( v12 + 23 <= v12 + 8 )
    v41 = 0xFFFFFFFFFFFFFF0LL;
  v42 = v41 & 0xFFFFFFFFFFFFFFF0uLL;
  v43 = alloca(v42);
  v44 = alloca(v42);
  v40 = (void **)&v80;
  if ( v79 == (_BYTE *)-48LL || (v80 = 1801679955, (v40 = &v81) == 0) )
  {
LABEL_212:
    if ( v12 + 8 >= v12 )
    {
      v45 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      v40 = (void **)v45;
      if ( v45 )
      {
        *v45 = 1885431112;
        v40 = (void **)(v45 + 2);
      }
    }
  }
  if ( !v40 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
    {
      goto LABEL_116;
    }
    WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store attr"
                "ibute information");
    v19 = 50;
    goto LABEL_115;
  }
  v46 = v81;
  if ( !v12 )
    goto LABEL_154;
  v47 = 0;
  if ( v12 >= 2 )
  {
    v48 = (unsigned __int64)v40 + v12 - 1;
    if ( (v40 > (void **)v81 + v12 - 1 || v48 < (unsigned __int64)v81)
      && (v40 > &v10[v12 - 1] || v48 < (unsigned __int64)v10) )
    {
      v49 = rgsabound;
      if ( (unsigned __int64)v40 <= *(_QWORD *)&rgsabound - 4LL + 4 * v12 && v48 >= *(_QWORD *)&rgsabound
        || v40 <= (void **)((char *)v20 + 4 * v12 - 4) && v48 >= (unsigned __int64)v20
        || v40 <= (void **)((char *)v32 + 4 * v12 - 4) && v48 >= (unsigned __int64)v32
        || v81 <= &v10[v12 - 1] && (char *)v81 + 8 * v12 - 8 >= (char *)v10
        || (unsigned __int64)v81 <= v13 + *(_QWORD *)&rgsabound - 4LL
        && (unsigned __int64)v81 + 8 * v12 - 8 >= *(_QWORD *)&rgsabound
        || v81 <= (char *)v20 + v13 - 4 && (char *)v81 + 8 * v12 - 8 >= (char *)v20
        || v81 <= (char *)v32 + v13 - 4 && (char *)v81 + 8 * v12 - 8 >= (char *)v32
        || (unsigned __int64)v10 <= *(_QWORD *)&rgsabound - 4LL + 4 * v12
        && (unsigned __int64)&v10[v12 - 1] >= *(_QWORD *)&rgsabound
        || v10 <= (void **)((char *)v20 + 4 * v12 - 4) && &v10[v12 - 1] >= v20
        || v10 <= (void **)((char *)v32 + 4 * v12 - 4) && &v10[v12 - 1] >= v32
        || *(_QWORD *)&rgsabound <= (unsigned __int64)v20 + 4 * v12 - 4
        && *(_QWORD *)&rgsabound - 4LL + 4 * v12 >= (unsigned __int64)v20
        || *(_QWORD *)&rgsabound <= (unsigned __int64)v32 + 4 * v12 - 4
        && *(_QWORD *)&rgsabound - 4LL + 4 * v12 >= (unsigned __int64)v32
        || v20 <= (void **)((char *)v32 + 4 * v12 - 4) && (void **)((char *)v20 + 4 * v12 - 4) >= v32 )
      {
        goto LABEL_153;
      }
      v50 = v12 & 0xFFFFFFFFFFFFFFFEuLL;
      do
        v47 += 2LL;
      while ( v47 < v50 );
      v84 = v47;
      v51 = (v50 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
      memset_0(v32, 0, 4 * v51);
      memset_0(v20, 0, 4 * v51);
      memset_0(*(void **)&rgsabound, 0, 4 * v51);
      memset_0(v10, 0, 8 * v51);
      memset_0(v81, 0, 8 * v51);
      LOBYTE(v52) = 1;
      memset_0(v40, v52, v51);
      v47 = v84;
      v46 = v81;
      if ( v84 >= v12 )
        goto LABEL_154;
    }
  }
  v49 = rgsabound;
  do
  {
LABEL_153:
    *((_DWORD *)v32 + v47) = 0;
    *((_DWORD *)v20 + v47) = 0;
    *(_DWORD *)(*(_QWORD *)&v49 + 4 * v47) = 0;
    v10[v47] = 0;
    v46[v47] = 0;
    *((_BYTE *)v40 + v47++) = 1;
  }
  while ( v47 < v12 );
LABEL_154:
  v53 = 0;
  v54 = rgsabound;
  while ( 1 )
  {
    v81 = v53;
    if ( (unsigned __int64)v53 >= v12 )
      break;
    VariantInit(&v94);
    VariantInit(&v95);
    v94.vt = 8195;
    rgsabound = (SAFEARRAYBOUND)5LL;
    v55 = SafeArrayCreate(3u, 1u, &rgsabound);
    if ( !v55 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("Not enough memory to create safearray of Info Ids");
        v66 = 51;
LABEL_193:
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v66, WPP_9723200e762c301790c48b34da45e129_Traceguids, "NPSSDO");
      }
LABEL_194:
      v11 = -2147024882;
      v80 = -2147024882;
      goto LABEL_195;
    }
    pvData = v55->pvData;
    *pvData = 2;
    pvData[1] = 3;
    pvData[2] = 1;
    pvData[3] = 5;
    pvData[4] = 4;
    v94.llVal = (LONGLONG)v55;
    v57 = ((__int64 (__fastcall *)(struct ISdoDictionaryOld *, _QWORD, VARIANTARG *, VARIANTARG *))v93->lpVtbl->GetAttributeInfo)(
            v93,
            *(unsigned int *)(v86 + 4LL * (_QWORD)v81),
            &v94,
            &v95);
    v80 = v57;
    if ( v57 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        WppDbgPrint("m_pDict->GetAttributeInfo failed with 0x%x");
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)WPP_9723200e762c301790c48b34da45e129_Traceguids,
          (unsigned int)"NPSSDO",
          v80);
        v57 = v80;
      }
      v11 = v57;
      goto LABEL_195;
    }
    v58 = *(_QWORD *)(v95.llVal + 16);
    v84 = v58;
    v59 = v81;
    *(_DWORD *)(*(_QWORD *)&v54 + 4LL * (_QWORD)v81) = *(_DWORD *)(v58 + 8);
    *((_DWORD *)v20 + (_QWORD)v59) = *(_DWORD *)(v58 + 32);
    v60 = *(_DWORD *)(v58 + 80);
    *((_DWORD *)v32 + (_QWORD)v59) = v60;
    v61 = v83;
    if ( v83 )
    {
      if ( v60 || *(_DWORD *)(v86 + 4LL * (_QWORD)v59) > 0xFFu )
        goto LABEL_164;
    }
    else if ( !v60 && *(_DWORD *)(v86 + 4LL * (_QWORD)v59) <= 0xFFu )
    {
LABEL_164:
      if ( v88 == (v88 & *((_DWORD *)v20 + (_QWORD)v59)) )
        goto LABEL_166;
    }
    *((_BYTE *)v59 + (_QWORD)v40) = 0;
LABEL_166:
    if ( *(_DWORD *)(v86 + 4LL * (_QWORD)v59) == 26 )
      *((_BYTE *)v59 + (_QWORD)v40) = v61;
    if ( *((_BYTE *)v59 + (_QWORD)v40) )
    {
      ++*v87;
      v62 = *(const OLECHAR **)(v58 + 56);
      if ( !v62 )
        v62 = L" ";
      v63 = SysAllocString(v62);
      v46[(_QWORD)v81] = v63;
      if ( !v63 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("Not enough memory to allocate string");
          v66 = 53;
          goto LABEL_193;
        }
        goto LABEL_194;
      }
      v64 = *(const OLECHAR **)(v84 + 104);
      if ( !v64 )
        v64 = L" ";
      v65 = SysAllocString(v64);
      v10[(_QWORD)v81] = v65;
      if ( !v65 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
        {
          WppDbgPrint("Not enough memory to allocate string");
          v66 = 54;
          goto LABEL_193;
        }
        goto LABEL_194;
      }
    }
    VariantClear(&v94);
    VariantClear(&v95);
    v53 = (char *)v81 + 1;
  }
  v85.cElements = *v87;
  v85.lLbound = 0;
  v90 = SafeArrayCreate(3u, 1u, &v85);
  v87 = (unsigned int *)v90->pvData;
  v91 = SafeArrayCreate(3u, 1u, &v85);
  v81 = v91->pvData;
  v92 = SafeArrayCreate(8u, 1u, &v85);
  v93 = (struct ISdoDictionaryOld *)v92->pvData;
  v68 = SafeArrayCreate(3u, 1u, &v85);
  rgsabound = (SAFEARRAYBOUND)v68;
  v84 = (unsigned __int64)v68->pvData;
  v69 = SafeArrayCreate(8u, 1u, &v85);
  v89 = v69;
  v70 = (char *)v69->pvData;
  v71 = 0;
  v72 = 0;
  if ( v12 )
  {
    v73 = v93;
    v74 = v84;
    v75 = v87;
    do
    {
      if ( *((_BYTE *)v40 + v72) )
      {
        v75[v71] = *(_DWORD *)(v86 + 4 * v72);
        *((_DWORD *)v81 + v71) = *(_DWORD *)(*(_QWORD *)&v54 + 4 * v72);
        v76 = (struct ISdoDictionaryOldVtbl *)v46[v72];
        v77 = v71;
        if ( v76 )
          v73[v77].lpVtbl = v76;
        *(_DWORD *)(v74 + 4 * v71) = *((_DWORD *)v32 + v72);
        v78 = v10[v72];
        if ( v78 )
          *(_QWORD *)&v70[v77 * 8] = v78;
        ++v71;
      }
      ++v72;
    }
    while ( v72 < v12 );
    v69 = v89;
    v68 = (SAFEARRAY *)rgsabound;
  }
  a5->vt = 8195;
  a5->llVal = (LONGLONG)v90;
  a6->vt = 8195;
  a6->llVal = (LONGLONG)v91;
  a7->vt = 8200;
  a7->llVal = (LONGLONG)v92;
  a8->vt = 8195;
  a8->llVal = (LONGLONG)v68;
  a9->vt = 8200;
  a9->llVal = (LONGLONG)v69;
LABEL_12:
  v11 = v80;
LABEL_195:
  SafeArrayCleanupOnError::~SafeArrayCleanupOnError((SafeArrayCleanupOnError *)v96);
  SafeArrayCleanupOnError::~SafeArrayCleanupOnError((SafeArrayCleanupOnError *)v97);
  SafeArrayCleanupOnError::~SafeArrayCleanupOnError((SafeArrayCleanupOnError *)v98);
  SafeArrayCleanupOnError::~SafeArrayCleanupOnError((SafeArrayCleanupOnError *)v99);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002b1c0  push    rbp
0x18002b1c2  push    rbx
0x18002b1c3  push    rsi
0x18002b1c4  push    rdi
0x18002b1c5  push    r12
0x18002b1c7  push    r13
0x18002b1c9  push    r14
0x18002b1cb  push    r15
0x18002b1cd  sub     rsp, 158h
0x18002b1d4  lea     rbp, [rsp+30h]
0x18002b1d9  mov     rax, cs:__security_cookie
0x18002b1e0  xor     rax, rbp
0x18002b1e3  mov     [rbp+160h+var_50], rax
0x18002b1ea  mov     rax, r9
0x18002b1ed  mov     [rbp+160h+var_128], rax
0x18002b1f1  mov     [rbp+160h+var_120], r8d
0x18002b1f5  mov     [rbp+160h+var_148], dl
0x18002b1f8  mov     rbx, rcx
0x18002b1fb  mov     [rbp+160h+var_F8], rcx
0x18002b1ff  xor     r14d, r14d
0x18002b202  mov     qword ptr [rbp+160h+var_138.cElements], r14
0x18002b206  mov     [rbp+160h+var_110], r14
0x18002b20a  mov     [rbp+160h+var_108], r14
0x18002b20e  mov     [rbp+160h+var_100], r14
0x18002b212  mov     [rbp+160h+var_118], r14
0x18002b216  test    rcx, rcx
0x18002b219  jz      loc_18002C089
0x18002b21f  test    rax, rax
0x18002b222  jz      loc_18002C089
0x18002b228  cmp     [rbp+160h+arg_20], r14
0x18002b22f  jz      loc_18002C089
0x18002b235  cmp     [rbp+160h+arg_28], r14
0x18002b23c  jz      loc_18002C089
0x18002b242  cmp     [rbp+160h+arg_30], r14
0x18002b249  jz      loc_18002C089
0x18002b24f  cmp     [rbp+160h+arg_40], r14
0x18002b256  jz      loc_18002C089
0x18002b25c  mov     [r9], r14d
0x18002b25f  xorps   xmm0, xmm0
0x18002b262  xor     eax, eax
0x18002b264  movups  xmmword ptr [rbp+160h+pvarg], xmm0
0x18002b26b  mov     qword ptr [rbp+160h+pvarg+10h], rax
0x18002b272  xorps   xmm1, xmm1
0x18002b275  movups  xmmword ptr [rbp+160h+var_68], xmm1
0x18002b27c  mov     qword ptr [rbp+160h+var_68+10h], rax
0x18002b283  movups  xmmword ptr [rbp+160h+var_F0], xmm0
0x18002b287  mov     qword ptr [rbp+160h+var_F0+10h], rax
0x18002b28e  movups  xmmword ptr [rbp+160h+var_D8], xmm1
0x18002b295  mov     qword ptr [rbp+160h+var_D8+10h], rax
0x18002b29c  lea     rcx, [rbp+160h+pvarg]; pvarg
0x18002b2a3  call    cs:__imp_VariantInit
0x18002b2a9  lea     rcx, [rbp+160h+var_68]; pvarg
0x18002b2b0  call    cs:__imp_VariantInit
0x18002b2b6  lea     rcx, [rbp+160h+var_F0]; pvarg
0x18002b2ba  call    cs:__imp_VariantInit
0x18002b2c0  lea     rcx, [rbp+160h+var_D8]; pvarg
0x18002b2c7  call    cs:__imp_VariantInit
0x18002b2cd  mov     rax, [rbx]
0x18002b2d0  lea     r8, [rbp+160h+var_68]
0x18002b2d7  lea     rdx, [rbp+160h+pvarg]
0x18002b2de  mov     rcx, rbx
0x18002b2e1  mov     rax, [rax+38h]
0x18002b2e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b2ea  mov     ebx, eax
0x18002b2ec  mov     [rbp+160h+var_160], eax
0x18002b2ef  lea     rax, [rbp+160h+var_160]
0x18002b2f3  mov     [rbp+160h+var_90], rax
0x18002b2fa  lea     rax, [rbp+160h+var_110]
0x18002b2fe  mov     [rbp+160h+var_88], rax
0x18002b305  lea     rax, [rbp+160h+var_160]
0x18002b309  mov     [rbp+160h+var_A0], rax
0x18002b310  lea     rax, [rbp+160h+var_108]
0x18002b314  mov     [rbp+160h+var_98], rax
0x18002b31b  lea     rax, [rbp+160h+var_160]
0x18002b31f  mov     [rbp+160h+var_B0], rax
0x18002b326  lea     rax, [rbp+160h+var_100]
0x18002b32a  mov     [rbp+160h+var_A8], rax
0x18002b331  lea     rax, [rbp+160h+var_160]
0x18002b335  mov     [rbp+160h+var_C0], rax
0x18002b33c  lea     rax, [rbp+160h+var_118]
0x18002b340  mov     [rbp+160h+var_B8], rax
0x18002b347  test    ebx, ebx
0x18002b349  jns     short loc_18002B3B8
0x18002b34b  lea     rax, WPP_GLOBAL_Control
0x18002b352  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b359  cmp     rcx, rax
0x18002b35c  jz      loc_18002BED1
0x18002b362  cmp     byte ptr [rcx+19h], 2
0x18002b366  jb      loc_18002BED1
0x18002b36c  test    dword ptr [rcx+1Ch], 400h
0x18002b373  jz      loc_18002BED1
0x18002b379  mov     edx, ebx
0x18002b37b  lea     rcx, aPdictEnumattri; "pDict->EnumAttributes failed with 0x%x"
0x18002b382  call    WppDbgPrint
0x18002b387  lea     edx, [r14+2Ch]
0x18002b38b  mov     eax, [rbp+160h+var_160]
0x18002b38e  mov     [rsp+190h+var_170], eax
0x18002b392  lea     r9, aNpssdo; "NPSSDO"
0x18002b399  lea     r8, WPP_9723200e762c301790c48b34da45e129_Traceguids
0x18002b3a0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3a7  mov     rcx, [rcx+10h]
0x18002b3ab  call    WPP_SF_sd
0x18002b3b0  mov     ebx, [rbp+160h+var_160]
0x18002b3b3  jmp     loc_18002BED1
0x18002b3b8  mov     rax, qword ptr [rbp+160h+pvarg+8]
0x18002b3bf  mov     esi, [rax+18h]
0x18002b3c2  mov     rax, [rax+10h]
0x18002b3c6  mov     [rbp+160h+var_130], rax
0x18002b3ca  lea     rbx, ds:0[rsi*4]
0x18002b3d2  mov     rax, r14
0x18002b3d5  mov     qword ptr [rbp+160h+rgsabound.cElements], rax
0x18002b3d9  mov     r15d, 6B637453h
0x18002b3df  mov     r12, 0FFFFFFFFFFFFFF0h
0x18002b3e9  test    rbx, rbx
0x18002b3ec  jz      short loc_18002B450
0x18002b3ee  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002b3f5  ja      short loc_18002B450
0x18002b3f7  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b3fe  add     rcx, 8
0x18002b402  add     rcx, rbx
0x18002b405  cmp     rcx, rbx
0x18002b408  jb      short loc_18002B450
0x18002b40a  call    VerifyStackAvailable
0x18002b40f  test    eax, eax
0x18002b411  jz      short loc_18002B44C
0x18002b413  lea     rdi, [rbx+8]
0x18002b417  lea     rax, [rdi+0Fh]
0x18002b41b  cmp     rax, rdi
0x18002b41e  ja      short loc_18002B423
0x18002b420  mov     rax, r12
0x18002b423  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002b427  call    _alloca_probe
0x18002b42c  sub     rsp, rax
0x18002b42f  lea     rax, [rsp+190h+var_160]
0x18002b434  mov     qword ptr [rbp+160h+rgsabound.cElements], rax
0x18002b438  test    rax, rax
0x18002b43b  jz      short loc_18002B450
0x18002b43d  mov     [rax], r15d
0x18002b440  add     rax, 8
0x18002b444  mov     qword ptr [rbp+160h+rgsabound.cElements], rax
0x18002b448  jz      short loc_18002B450
0x18002b44a  jmp     short loc_18002B47F
0x18002b44c  mov     rax, qword ptr [rbp+160h+rgsabound.cElements]
0x18002b450  lea     rdi, [rbx+8]
0x18002b454  cmp     rdi, rbx
0x18002b457  jb      short loc_18002B47F
0x18002b459  mov     rcx, rdi
0x18002b45c  mov     rax, cs:g_pfnAllocate
0x18002b463  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b468  mov     qword ptr [rbp+160h+rgsabound.cElements], rax
0x18002b46c  test    rax, rax
0x18002b46f  jz      short loc_18002B484
0x18002b471  mov     dword ptr [rax], 70616548h
0x18002b477  add     rax, 8
0x18002b47b  mov     qword ptr [rbp+160h+rgsabound.cElements], rax
0x18002b47f  test    rax, rax
0x18002b482  jnz     short loc_18002B4CF
0x18002b484  lea     rax, WPP_GLOBAL_Control
0x18002b48b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b492  cmp     rcx, rax
0x18002b495  jz      loc_18002B93F
0x18002b49b  cmp     byte ptr [rcx+19h], 2
0x18002b49f  jb      loc_18002B93F
0x18002b4a5  test    dword ptr [rcx+1Ch], 400h
0x18002b4ac  jz      loc_18002B93F
0x18002b4b2  lea     rdx, aNpssdo; "NPSSDO"
0x18002b4b9  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002b4c0  call    WppDbgPrint
0x18002b4c5  mov     edx, 2Dh ; '-'
0x18002b4ca  jmp     loc_18002B921
0x18002b4cf  mov     r13, r14
0x18002b4d2  test    rbx, rbx
0x18002b4d5  jz      short loc_18002B52E
0x18002b4d7  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002b4de  ja      short loc_18002B52E
0x18002b4e0  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b4e7  add     rcx, 8
0x18002b4eb  add     rcx, rbx
0x18002b4ee  cmp     rcx, rbx
0x18002b4f1  jb      short loc_18002B52E
0x18002b4f3  call    VerifyStackAvailable
0x18002b4f8  test    eax, eax
0x18002b4fa  jz      short loc_18002B52E
0x18002b4fc  lea     rcx, [rbx+8]
0x18002b500  lea     rax, [rcx+0Fh]
0x18002b504  cmp     rax, rcx
0x18002b507  ja      short loc_18002B50C
0x18002b509  mov     rax, r12
0x18002b50c  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002b510  call    _alloca_probe
0x18002b515  sub     rsp, rax
0x18002b518  lea     r13, [rsp+190h+var_160]
0x18002b51d  test    r13, r13
0x18002b520  jz      short loc_18002B531
0x18002b522  mov     [r13+0], r15d
0x18002b526  add     r13, 8
0x18002b52a  jnz     short loc_18002B554
0x18002b52c  jmp     short loc_18002B531
0x18002b52e  mov     rcx, rdi
0x18002b531  cmp     rcx, rbx
0x18002b534  jb      short loc_18002B554
0x18002b536  mov     rax, cs:g_pfnAllocate
0x18002b53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b542  mov     r13, rax
0x18002b545  test    rax, rax
0x18002b548  jz      short loc_18002B554
0x18002b54a  mov     dword ptr [rax], 70616548h
0x18002b550  add     r13, 8
0x18002b554  test    r13, r13
0x18002b557  jnz     short loc_18002B5A3
0x18002b559  lea     rax, WPP_GLOBAL_Control
0x18002b560  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b567  cmp     rcx, rax
0x18002b56a  jz      loc_18002B93F
0x18002b570  cmp     byte ptr [rcx+19h], 2
0x18002b574  jb      loc_18002B93F
0x18002b57a  test    dword ptr [rcx+1Ch], 400h
0x18002b581  jz      loc_18002B93F
0x18002b587  lea     rdx, aNpssdo; "NPSSDO"
0x18002b58e  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002b595  call    WppDbgPrint
0x18002b59a  lea     edx, [r13+2Eh]
0x18002b59e  jmp     loc_18002B921
0x18002b5a3  lea     r15, ds:0[rsi*8]
0x18002b5ab  mov     rax, r14
0x18002b5ae  mov     [rbp+160h+var_158], rax
0x18002b5b2  test    r15, r15
0x18002b5b5  jz      short loc_18002B61F
0x18002b5b7  cmp     r15, cs:g_ulMaxStackAllocSize
0x18002b5be  ja      short loc_18002B61F
0x18002b5c0  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b5c7  add     rcx, 8
0x18002b5cb  add     rcx, r15
0x18002b5ce  cmp     rcx, r15
0x18002b5d1  jb      short loc_18002B61F
0x18002b5d3  call    VerifyStackAvailable
0x18002b5d8  test    eax, eax
0x18002b5da  jz      short loc_18002B61B
0x18002b5dc  lea     rax, [r15+8]
0x18002b5e0  lea     rcx, [rax+0Fh]
0x18002b5e4  cmp     rcx, rax
0x18002b5e7  ja      short loc_18002B5EC
0x18002b5e9  mov     rcx, r12
0x18002b5ec  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002b5f0  mov     rax, rcx
0x18002b5f3  call    _alloca_probe
0x18002b5f8  sub     rsp, rcx
0x18002b5fb  lea     rax, [rsp+190h+var_160]
0x18002b600  mov     [rbp+160h+var_158], rax
0x18002b604  test    rax, rax
0x18002b607  jz      short loc_18002B61F
0x18002b609  mov     dword ptr [rax], 6B637453h
0x18002b60f  add     rax, 8
0x18002b613  mov     [rbp+160h+var_158], rax
0x18002b617  jnz     short loc_18002B64B
0x18002b619  jmp     short loc_18002B61F
0x18002b61b  mov     rax, [rbp+160h+var_158]
0x18002b61f  lea     rcx, [r15+8]
0x18002b623  cmp     rcx, r15
0x18002b626  jb      short loc_18002B64B
0x18002b628  mov     rax, cs:g_pfnAllocate
0x18002b62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b634  mov     [rbp+160h+var_158], rax
0x18002b638  test    rax, rax
0x18002b63b  jz      short loc_18002B650
0x18002b63d  mov     dword ptr [rax], 70616548h
0x18002b643  add     rax, 8
0x18002b647  mov     [rbp+160h+var_158], rax
0x18002b64b  test    rax, rax
0x18002b64e  jnz     short loc_18002B69B
0x18002b650  lea     rax, WPP_GLOBAL_Control
0x18002b657  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b65e  cmp     rcx, rax
0x18002b661  jz      loc_18002B93F
0x18002b667  cmp     byte ptr [rcx+19h], 2
0x18002b66b  jb      loc_18002B93F
0x18002b671  test    dword ptr [rcx+1Ch], 400h
0x18002b678  jz      loc_18002B93F
0x18002b67e  lea     rdx, aNpssdo; "NPSSDO"
0x18002b685  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002b68c  call    WppDbgPrint
0x18002b691  mov     edx, 2Fh ; '/'
0x18002b696  jmp     loc_18002B921
0x18002b69b  mov     r12, r14
0x18002b69e  test    rbx, rbx
0x18002b6a1  jz      short loc_18002B6FF
0x18002b6a3  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002b6aa  ja      short loc_18002B6FF
0x18002b6ac  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002b6b3  add     rcx, 8
0x18002b6b7  add     rcx, rbx
0x18002b6ba  cmp     rcx, rbx
0x18002b6bd  jb      short loc_18002B6FF
0x18002b6bf  call    VerifyStackAvailable
0x18002b6c4  test    eax, eax
0x18002b6c6  jz      short loc_18002B6FF
0x18002b6c8  lea     rax, [rdi+0Fh]
0x18002b6cc  cmp     rax, rdi
0x18002b6cf  ja      short loc_18002B6DB
0x18002b6d1  mov     rax, 0FFFFFFFFFFFFFF0h
  ... truncated ...
```
