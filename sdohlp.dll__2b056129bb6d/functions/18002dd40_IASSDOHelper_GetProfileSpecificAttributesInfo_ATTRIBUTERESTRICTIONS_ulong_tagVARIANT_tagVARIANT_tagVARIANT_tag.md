# IASSDOHelper::GetProfileSpecificAttributesInfo(_ATTRIBUTERESTRICTIONS,ulong *,tagVARIANT *,tagVARIANT *,tagVARIANT *,tagVARIANT *)

- ea: `0x18002dd40`
- end: `0x18002e555`
- name: `?GetProfileSpecificAttributesInfo@IASSDOHelper@@UEAAJW4_ATTRIBUTERESTRICTIONS@@PEAKPEAUtagVARIANT@@222@Z`
- size: `2069`
- prototype: `__int64 __fastcall(IASSDOHelper *__hidden this, enum _ATTRIBUTERESTRICTIONS, unsigned int *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x1800241bb`
- `0x18002cca4`
- `0x18002cd00`
- `0x18002dd40`
- `0x180042844`
- `0x180042a80`
- `0x180055030`
- `0x1800550f0`
- `0x180058010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002e28f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e2b6`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e28f`
- `OLEAUT32!__imp_SysAllocString` at `0x18002e2b6`
- `OLEAUT32!__imp_VariantInit` at `0x18002e1eb`
- `OLEAUT32!__imp_VariantInit` at `0x18002e1f5`
- `OLEAUT32!__imp_VariantInit` at `0x18002e1eb`
- `OLEAUT32!__imp_VariantInit` at `0x18002e1f5`
- `OLEAUT32!__imp_VariantClear` at `0x18002e2c9`
- `OLEAUT32!__imp_VariantClear` at `0x18002e2d3`
- `OLEAUT32!__imp_VariantClear` at `0x18002e2c9`
- `OLEAUT32!__imp_VariantClear` at `0x18002e2d3`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e212`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e429`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e446`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e467`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e484`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e212`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e429`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e446`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e467`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18002e484`

## string_xrefs

- `0x18002e3cf`: `Not enough memory to create safearray of Info Ids`

## pseudocode

```c
__int64 __fastcall IASSDOHelper::GetProfileSpecificAttributesInfo(
        IASSDOHelper *this,
        enum _ATTRIBUTERESTRICTIONS a2,
        unsigned int *a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *a5,
        struct tagVARIANT *a6,
        struct tagVARIANT *a7)
{
  __int64 v8; // rax
  int v9; // r12d
  int v10; // edx
  enum _ATTRIBUTEID near **v12; // rax
  unsigned int v13; // r13d
  SAFEARRAYBOUND *p_rgsabound; // rdi
  unsigned __int64 v15; // rbx
  __int64 v16; // rcx
  void *v17; // rsp
  void *v18; // rsp
  SAFEARRAYBOUND *v19; // rax
  __int64 v20; // rdx
  unsigned __int64 v21; // r15
  SAFEARRAYBOUND *v22; // rsi
  unsigned __int64 v23; // r14
  __int64 v24; // rax
  void *v25; // rsp
  SAFEARRAYBOUND *v26; // rax
  SAFEARRAYBOUND *v27; // rbx
  __int64 v28; // rax
  void *v29; // rsp
  SAFEARRAYBOUND *v30; // rax
  __int64 v31; // rax
  __int64 v32; // rcx
  SAFEARRAYBOUND *v33; // r9
  SAFEARRAYBOUND *v34; // r8
  SAFEARRAYBOUND *v35; // rax
  __int64 v36; // r14
  SAFEARRAY *v37; // rax
  _DWORD *v38; // rcx
  enum _ATTRIBUTEID near **v39; // rdx
  __int64 v40; // rdx
  unsigned __int64 v41; // rcx
  const OLECHAR *v42; // rcx
  BSTR v43; // rax
  const OLECHAR *v44; // rcx
  BSTR v45; // rax
  SAFEARRAY *v46; // rax
  ULONG *v47; // r10
  __int64 v48; // r8
  IASSDOHelper *v49; // r14
  unsigned __int64 v50; // r15
  SAFEARRAYBOUND *v51; // r11
  enum _ATTRIBUTEID near **v52; // r9
  SAFEARRAYBOUND v53; // rcx
  SAFEARRAYBOUND v54; // rax
  struct tagVARIANT *v55; // rax
  SAFEARRAYBOUND v56; // r14
  LONGLONG v57; // r15
  LONGLONG v58; // r9
  _BYTE v59[32]; // [rsp+0h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+30h] [rbp+0h] BYREF
  SAFEARRAYBOUND v61; // [rsp+38h] [rbp+8h] BYREF
  unsigned __int64 pvData; // [rsp+40h] [rbp+10h]
  enum _ATTRIBUTEID near **v63; // [rsp+48h] [rbp+18h]
  SAFEARRAY *v64; // [rsp+50h] [rbp+20h]
  IASSDOHelper *v65; // [rsp+58h] [rbp+28h]
  ULONG *v66; // [rsp+60h] [rbp+30h]
  VARIANTARG pvarg; // [rsp+68h] [rbp+38h] BYREF
  struct tagVARIANT *v68; // [rsp+80h] [rbp+50h]
  SAFEARRAY *v69; // [rsp+88h] [rbp+58h]
  SAFEARRAY *v70; // [rsp+90h] [rbp+60h]
  VARIANTARG v71; // [rsp+98h] [rbp+68h] BYREF

  v65 = this;
  v68 = a4;
  v66 = a3;
  if ( !a3 || !a4 || !a5 || !a6 || !a7 )
    return 2147500035LL;
  v61 = 0;
  *a3 = 0;
  if ( a2 != ALLOWEDINPROFILE )
  {
    if ( a2 != ALLOWEDINPROXYPROFILE )
      return 0;
    v9 = 0;
    v12 = &CRPAttributes;
    v13 = 10;
LABEL_19:
    p_rgsabound = 0;
    *a3 = v13;
    v63 = v12;
    pvData = v13;
    v15 = 4LL * v13;
    if ( v15 > g_ulMaxStackAllocSize || v15 + g_ulAdditionalProbeSize + 8 < v15 || !(unsigned int)VerifyStackAvailable() )
      goto LABEL_113;
    v16 = v15 + 23;
    if ( v15 + 23 <= v15 + 8 )
      v16 = 0xFFFFFFFFFFFFFF0LL;
    v17 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
    v18 = alloca(v16 & 0xFFFFFFFFFFFFFFF0uLL);
    p_rgsabound = &rgsabound;
    if ( v59 == (_BYTE *)-48LL || (rgsabound.cElements = 1801679955, (p_rgsabound = &v61) == 0) )
    {
LABEL_113:
      if ( v15 + 8 >= v15 )
      {
        v19 = (SAFEARRAYBOUND *)((__int64 (*)(void))g_pfnAllocate)();
        p_rgsabound = v19;
        if ( v19 )
        {
          v19->cElements = 1885431112;
          p_rgsabound = v19 + 1;
        }
      }
    }
    if ( p_rgsabound )
    {
      v21 = 8LL * v13;
      v22 = 0;
      if ( v21 > g_ulMaxStackAllocSize
        || v21 + g_ulAdditionalProbeSize + 8 < v21
        || !(unsigned int)VerifyStackAvailable() )
      {
        goto LABEL_41;
      }
      v23 = v21 + 8;
      v24 = v21 + 23;
      if ( v21 + 23 <= v21 + 8 )
        v24 = 0xFFFFFFFFFFFFFF0LL;
      v25 = alloca(v24 & 0xFFFFFFFFFFFFFFF0uLL);
      v22 = &rgsabound;
      if ( v59 == (_BYTE *)-48LL || (rgsabound.cElements = 1801679955, (v22 = &v61) == 0) )
      {
LABEL_41:
        v23 = v21 + 8;
        if ( v21 + 8 >= v21 )
        {
          v26 = (SAFEARRAYBOUND *)((__int64 (__fastcall *)(unsigned __int64))g_pfnAllocate)(v21 + 8);
          v22 = v26;
          if ( v26 )
          {
            v26->cElements = 1885431112;
            v22 = v26 + 1;
          }
        }
      }
      if ( v22 )
      {
        v27 = 0;
        if ( v21 > g_ulMaxStackAllocSize
          || v21 + g_ulAdditionalProbeSize + 8 < v21
          || !(unsigned int)VerifyStackAvailable() )
        {
          goto LABEL_114;
        }
        v28 = v23 + 15;
        if ( v23 + 15 < v23 )
          v28 = 0xFFFFFFFFFFFFFF0LL;
        v29 = alloca(v28 & 0xFFFFFFFFFFFFFFF0uLL);
        v27 = &rgsabound;
        if ( v59 == (_BYTE *)-48LL || (rgsabound.cElements = 1801679955, (v27 = &v61) == 0) )
        {
LABEL_114:
          if ( v23 >= v21 )
          {
            v30 = (SAFEARRAYBOUND *)((__int64 (__fastcall *)(unsigned __int64))g_pfnAllocate)(v23);
            v27 = v30;
            if ( v30 )
            {
              v30->cElements = 1885431112;
              v27 = v30 + 1;
            }
          }
        }
        if ( v27 )
        {
          v31 = v13 - 1;
          v32 = 0;
          v33 = &v27[v31];
          v34 = &v22[v31];
          if ( (v22 > v33 || v34 < v27)
            && ((v35 = (SAFEARRAYBOUND *)((char *)p_rgsabound + 4 * v31), v22 > v35) || v34 < p_rgsabound)
            && (v27 > v35 || v33 < p_rgsabound) )
          {
            memset_0(p_rgsabound, 0, 4 * pvData);
            memset_0(v27, 0, 8LL * v13);
            memset_0(v22, 0, 8LL * v13);
          }
          else
          {
            do
            {
              *(&p_rgsabound->cElements + v32) = 0;
              v27[v32] = 0;
              v22[v32] = 0;
              v32 = (unsigned int)(v32 + 1);
            }
            while ( (unsigned int)v32 < v13 );
          }
          memset(&pvarg, 0, sizeof(pvarg));
          v36 = 0;
          memset(&v71, 0, sizeof(v71));
          while ( 1 )
          {
            if ( (unsigned int)v36 >= v13 )
            {
              v61.lLbound = 0;
              v61.cElements = *v66;
              rgsabound = (SAFEARRAYBOUND)SafeArrayCreate(3u, 1u, &v61);
              v65 = *(IASSDOHelper **)(*(_QWORD *)&rgsabound + 16LL);
              v69 = SafeArrayCreate(3u, 1u, &v61);
              pvData = (unsigned __int64)v69->pvData;
              v70 = SafeArrayCreate(8u, 1u, &v61);
              v66 = (ULONG *)v70->pvData;
              v46 = SafeArrayCreate(8u, 1u, &v61);
              v47 = v66;
              v48 = 0;
              v49 = v65;
              v50 = pvData;
              v51 = (SAFEARRAYBOUND *)v46->pvData;
              v52 = v63;
              v64 = v46;
              do
              {
                *((_DWORD *)v49 + v48) = *((_DWORD *)v52 + v48);
                *(_DWORD *)(v50 + 4 * v48) = *(&p_rgsabound->cElements + v48);
                v53 = v22[v48];
                if ( v53 )
                  *(SAFEARRAYBOUND *)&v47[2 * v48] = v53;
                v54 = v27[v48];
                if ( v54 )
                  v51[v48] = v54;
                v48 = (unsigned int)(v48 + 1);
              }
              while ( (unsigned int)v48 < v13 );
              v55 = v68;
              v56 = rgsabound;
              v57 = (LONGLONG)v69;
              v58 = (LONGLONG)v64;
              v68->vt = 8195;
              v55->decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)v56;
              a5->vt = 8195;
              a5->llVal = v57;
              a6->llVal = (LONGLONG)v70;
              a6->vt = 8200;
              a7->vt = 8200;
              a7->llVal = v58;
              return (unsigned int)v9;
            }
            VariantInit(&pvarg);
            VariantInit(&v71);
            pvarg.vt = 8195;
            rgsabound = (SAFEARRAYBOUND)3LL;
            v37 = SafeArrayCreate(3u, 1u, &rgsabound);
            if ( !v37 )
              break;
            v38 = v37->pvData;
            v39 = v63;
            *v38 = 2;
            v38[1] = 1;
            v38[2] = 4;
            v40 = *((unsigned int *)v39 + v36);
            pvarg.llVal = (LONGLONG)v37;
            v9 = (*(__int64 (__fastcall **)(_QWORD, __int64, VARIANTARG *, VARIANTARG *))(**((_QWORD **)v65 + 13) + 64LL))(
                   *((_QWORD *)v65 + 13),
                   v40,
                   &pvarg,
                   &v71);
            if ( v9 < 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WppDbgPrint("m_pDict->GetAttributeInfo failed with 0x%x");
                v10 = 29;
                goto LABEL_12;
              }
              return (unsigned int)v9;
            }
            v41 = *(_QWORD *)(v71.llVal + 16);
            pvData = v41;
            *(&p_rgsabound->cElements + v36) = *(_DWORD *)(v41 + 8);
            v42 = *(const OLECHAR **)(v41 + 32);
            if ( !v42 )
              v42 = L" ";
            v43 = SysAllocString(v42);
            v22[v36] = (SAFEARRAYBOUND)v43;
            if ( !v43 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WppDbgPrint("Not enough memory to allocate string");
                v20 = 30;
                goto LABEL_100;
              }
              return 2147942414LL;
            }
            v44 = *(const OLECHAR **)(pvData + 56);
            if ( !v44 )
              v44 = L" ";
            v45 = SysAllocString(v44);
            v27[v36] = (SAFEARRAYBOUND)v45;
            if ( !v45 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
              {
                WppDbgPrint("Not enough memory to allocate string");
                v20 = 31;
                goto LABEL_100;
              }
              return 2147942414LL;
            }
            VariantClear(&pvarg);
            VariantClear(&v71);
            v36 = (unsigned int)(v36 + 1);
          }
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WppDbgPrint("Not enough memory to create safearray of Info Ids");
            v20 = 28;
            goto LABEL_100;
          }
          return 2147942414LL;
        }
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          return 2147942414LL;
        }
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store "
                    "attribute information");
        v20 = 27;
      }
      else
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
        {
          return 2147942414LL;
        }
        WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store "
                    "attribute information");
        v20 = 26;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0 )
      {
        return 2147942414LL;
      }
      WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to store at"
                  "tribute information");
      v20 = 25;
    }
LABEL_100:
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids, "NPSSDO");
    return 2147942414LL;
  }
  v8 = *(_QWORD *)this;
  rgsabound.cElements = 0;
  v9 = (*(__int64 (__fastcall **)(IASSDOHelper *, SAFEARRAYBOUND *))(v8 + 152))(this, &rgsabound);
  if ( v9 >= 0 )
  {
    if ( (int)rgsabound.cElements >= 257 )
    {
      v13 = 18;
      v12 = &RAPAttributes;
    }
    else
    {
      v12 = &RAPAttributesLegacy;
      v13 = 24;
    }
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WppDbgPrint("GetDatabaseVersion failed with 0x%x");
    v10 = 24;
LABEL_12:
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      (unsigned int)WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids,
      (unsigned int)"NPSSDO",
      v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002dd40  push    rbp
0x18002dd42  push    rbx
0x18002dd43  push    rsi
0x18002dd44  push    rdi
0x18002dd45  push    r12
0x18002dd47  push    r13
0x18002dd49  push    r14
0x18002dd4b  push    r15
0x18002dd4d  sub     rsp, 0C8h
0x18002dd54  lea     rbp, [rsp+30h]
0x18002dd59  mov     rax, cs:__security_cookie
0x18002dd60  xor     rax, rbp
0x18002dd63  mov     [rbp+0D0h+var_50], rax
0x18002dd6a  mov     [rbp+0D0h+var_A8], rcx
0x18002dd6e  mov     rax, r9
0x18002dd71  mov     [rbp+0D0h+var_80], rax
0x18002dd75  mov     rbx, r8
0x18002dd78  mov     [rbp+0D0h+var_A0], rbx
0x18002dd7c  test    r8, r8
0x18002dd7f  jz      loc_18002E52D
0x18002dd85  test    rax, rax
0x18002dd88  jz      loc_18002E52D
0x18002dd8e  cmp     [rbp+0D0h+arg_20], 0
0x18002dd96  jz      loc_18002E52D
0x18002dd9c  cmp     [rbp+0D0h+arg_28], 0
0x18002dda4  jz      loc_18002E52D
0x18002ddaa  cmp     [rbp+0D0h+arg_30], 0
0x18002ddb2  jz      loc_18002E52D
0x18002ddb8  mov     qword ptr [rbp+0D0h+var_C8.cElements], 0
0x18002ddc0  mov     dword ptr [r8], 0
0x18002ddc7  cmp     edx, 2
0x18002ddca  jnz     loc_18002DE79
0x18002ddd0  mov     rax, [rcx]
0x18002ddd3  lea     rdx, [rbp+0D0h+rgsabound]
0x18002ddd7  mov     [rbp+0D0h+rgsabound.cElements], 0
0x18002ddde  mov     rax, [rax+98h]
0x18002dde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ddea  mov     r12d, eax
0x18002dded  test    eax, eax
0x18002ddef  jns     short loc_18002DE52
0x18002ddf1  mov     rax, cs:WPP_GLOBAL_Control
0x18002ddf8  lea     rcx, WPP_GLOBAL_Control
0x18002ddff  cmp     rax, rcx
0x18002de02  jz      short loc_18002DE4A
0x18002de04  cmp     byte ptr [rax+19h], 2
0x18002de08  jb      short loc_18002DE4A
0x18002de0a  test    dword ptr [rax+1Ch], 400h
0x18002de11  jz      short loc_18002DE4A
0x18002de13  mov     edx, r12d
0x18002de16  lea     rcx, aGetdatabasever; "GetDatabaseVersion failed with 0x%x"
0x18002de1d  call    WppDbgPrint
0x18002de22  mov     edx, 18h
0x18002de27  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de2e  lea     r9, aNpssdo; "NPSSDO"
0x18002de35  lea     r8, WPP_b2e5ba8d027733d341583b07c20330d3_Traceguids
0x18002de3c  mov     [rsp+100h+var_E0], r12d
0x18002de41  mov     rcx, [rcx+10h]
0x18002de45  call    WPP_SF_sd
0x18002de4a  mov     eax, r12d
0x18002de4d  jmp     loc_18002E532
0x18002de52  cmp     [rbp+0D0h+rgsabound.cElements], 101h
0x18002de59  jge     short loc_18002DE6A
0x18002de5b  lea     rax, ?RAPAttributesLegacy@@3PAW4_ATTRIBUTEID@@A; _ATTRIBUTEID near * RAPAttributesLegacy
0x18002de62  mov     r13d, 18h
0x18002de68  jmp     short loc_18002DE90
0x18002de6a  mov     r13d, 12h
0x18002de70  lea     rax, ?RAPAttributes@@3PAW4_ATTRIBUTEID@@A; _ATTRIBUTEID near * RAPAttributes
0x18002de77  jmp     short loc_18002DE90
0x18002de79  cmp     edx, 8
0x18002de7c  jnz     loc_18002E529
0x18002de82  xor     r12d, r12d
0x18002de85  lea     rax, ?CRPAttributes@@3PAW4_ATTRIBUTEID@@A; _ATTRIBUTEID near * CRPAttributes
0x18002de8c  lea     r13d, [rdx+2]
0x18002de90  mov     esi, r13d
0x18002de93  xor     edi, edi
0x18002de95  mov     [rbx], r13d
0x18002de98  mov     r14, 0FFFFFFFFFFFFFF0h
0x18002dea2  mov     [rbp+0D0h+var_B8], rax
0x18002dea6  mov     [rbp+0D0h+var_C0], rsi
0x18002deaa  lea     rbx, ds:0[rsi*4]
0x18002deb2  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18002deb9  ja      short loc_18002DF0C
0x18002debb  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002dec2  add     rcx, 8
0x18002dec6  add     rcx, rbx
0x18002dec9  cmp     rcx, rbx
0x18002decc  jb      short loc_18002DF0C
0x18002dece  call    VerifyStackAvailable
0x18002ded3  test    eax, eax
0x18002ded5  jz      short loc_18002DF0C
0x18002ded7  lea     rax, [rbx+8]
0x18002dedb  lea     rcx, [rax+0Fh]
0x18002dedf  cmp     rcx, rax
0x18002dee2  ja      short loc_18002DEE7
0x18002dee4  mov     rcx, r14
0x18002dee7  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18002deeb  mov     rax, rcx
0x18002deee  call    _alloca_probe
0x18002def3  sub     rsp, rcx
0x18002def6  lea     rdi, [rsp+100h+rgsabound]
0x18002defb  test    rdi, rdi
0x18002defe  jz      short loc_18002DF0C
0x18002df00  mov     dword ptr [rdi], 6B637453h
0x18002df06  add     rdi, 8
0x18002df0a  jnz     short loc_18002DF33
0x18002df0c  lea     rcx, [rbx+8]
0x18002df10  cmp     rcx, rbx
0x18002df13  jb      short loc_18002DF33
0x18002df15  mov     rax, cs:g_pfnAllocate
0x18002df1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df21  mov     rdi, rax
0x18002df24  test    rax, rax
0x18002df27  jz      short loc_18002DF33
0x18002df29  mov     dword ptr [rax], 70616548h
0x18002df2f  add     rdi, 8
0x18002df33  test    rdi, rdi
0x18002df36  jnz     short loc_18002DF81
0x18002df38  mov     rax, cs:WPP_GLOBAL_Control
0x18002df3f  lea     rcx, WPP_GLOBAL_Control
0x18002df46  cmp     rax, rcx
0x18002df49  jz      loc_18002E3FE
0x18002df4f  cmp     byte ptr [rax+19h], 2
0x18002df53  jb      loc_18002E3FE
0x18002df59  test    dword ptr [rax+1Ch], 400h
0x18002df60  jz      loc_18002E3FE
0x18002df66  lea     rdx, aNpssdo; "NPSSDO"
0x18002df6d  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002df74  call    WppDbgPrint
0x18002df79  lea     edx, [rdi+19h]
0x18002df7c  jmp     loc_18002E3E0
0x18002df81  lea     r15, ds:0[rsi*8]
0x18002df89  xor     esi, esi
0x18002df8b  cmp     r15, cs:g_ulMaxStackAllocSize
0x18002df92  ja      short loc_18002DFE9
0x18002df94  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002df9b  add     rcx, 8
0x18002df9f  add     rcx, r15
0x18002dfa2  cmp     rcx, r15
0x18002dfa5  jb      short loc_18002DFE9
0x18002dfa7  call    VerifyStackAvailable
0x18002dfac  test    eax, eax
0x18002dfae  jz      short loc_18002DFE9
0x18002dfb0  lea     r14, [r15+8]
0x18002dfb4  lea     rax, [r14+0Fh]
0x18002dfb8  cmp     rax, r14
0x18002dfbb  ja      short loc_18002DFC7
0x18002dfbd  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002dfc7  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002dfcb  call    _alloca_probe
0x18002dfd0  sub     rsp, rax
0x18002dfd3  lea     rsi, [rsp+100h+rgsabound]
0x18002dfd8  test    rsi, rsi
0x18002dfdb  jz      short loc_18002DFE9
0x18002dfdd  mov     dword ptr [rsi], 6B637453h
0x18002dfe3  add     rsi, 8
0x18002dfe7  jnz     short loc_18002E013
0x18002dfe9  lea     r14, [r15+8]
0x18002dfed  cmp     r14, r15
0x18002dff0  jb      short loc_18002E013
0x18002dff2  mov     rax, cs:g_pfnAllocate
0x18002dff9  mov     rcx, r14
0x18002dffc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e001  mov     rsi, rax
0x18002e004  test    rax, rax
0x18002e007  jz      short loc_18002E013
0x18002e009  mov     dword ptr [rax], 70616548h
0x18002e00f  add     rsi, 8
0x18002e013  test    rsi, rsi
0x18002e016  jnz     short loc_18002E061
0x18002e018  mov     rax, cs:WPP_GLOBAL_Control
0x18002e01f  lea     rcx, WPP_GLOBAL_Control
0x18002e026  cmp     rax, rcx
0x18002e029  jz      loc_18002E3FE
0x18002e02f  cmp     byte ptr [rax+19h], 2
0x18002e033  jb      loc_18002E3FE
0x18002e039  test    dword ptr [rax+1Ch], 400h
0x18002e040  jz      loc_18002E3FE
0x18002e046  lea     rdx, aNpssdo; "NPSSDO"
0x18002e04d  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002e054  call    WppDbgPrint
0x18002e059  lea     edx, [rsi+1Ah]
0x18002e05c  jmp     loc_18002E3E0
0x18002e061  xor     ebx, ebx
0x18002e063  cmp     r15, cs:g_ulMaxStackAllocSize
0x18002e06a  ja      short loc_18002E0BD
0x18002e06c  mov     rcx, cs:g_ulAdditionalProbeSize
0x18002e073  add     rcx, 8
0x18002e077  add     rcx, r15
0x18002e07a  cmp     rcx, r15
0x18002e07d  jb      short loc_18002E0BD
0x18002e07f  call    VerifyStackAvailable
0x18002e084  test    eax, eax
0x18002e086  jz      short loc_18002E0BD
0x18002e088  lea     rax, [r14+0Fh]
0x18002e08c  cmp     rax, r14
0x18002e08f  ja      short loc_18002E09B
0x18002e091  mov     rax, 0FFFFFFFFFFFFFF0h
0x18002e09b  and     rax, 0FFFFFFFFFFFFFFF0h
0x18002e09f  call    _alloca_probe
0x18002e0a4  sub     rsp, rax
0x18002e0a7  lea     rbx, [rsp+100h+rgsabound]
0x18002e0ac  test    rbx, rbx
0x18002e0af  jz      short loc_18002E0BD
0x18002e0b1  mov     dword ptr [rbx], 6B637453h
0x18002e0b7  add     rbx, 8
0x18002e0bb  jnz     short loc_18002E0E3
0x18002e0bd  cmp     r14, r15
0x18002e0c0  jb      short loc_18002E0E3
0x18002e0c2  mov     rax, cs:g_pfnAllocate
0x18002e0c9  mov     rcx, r14
0x18002e0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e0d1  mov     rbx, rax
0x18002e0d4  test    rax, rax
0x18002e0d7  jz      short loc_18002E0E3
0x18002e0d9  mov     dword ptr [rax], 70616548h
0x18002e0df  add     rbx, 8
0x18002e0e3  test    rbx, rbx
0x18002e0e6  jnz     short loc_18002E131
0x18002e0e8  mov     rax, cs:WPP_GLOBAL_Control
0x18002e0ef  lea     rcx, WPP_GLOBAL_Control
0x18002e0f6  cmp     rax, rcx
0x18002e0f9  jz      loc_18002E3FE
0x18002e0ff  cmp     byte ptr [rax+19h], 2
0x18002e103  jb      loc_18002E3FE
0x18002e109  test    dword ptr [rax+1Ch], 400h
0x18002e110  jz      loc_18002E3FE
0x18002e116  lea     rdx, aNpssdo; "NPSSDO"
0x18002e11d  lea     rcx, aCpuPidTidNowSL; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18002e124  call    WppDbgPrint
0x18002e129  lea     edx, [rbx+1Bh]
0x18002e12c  jmp     loc_18002E3E0
0x18002e131  lea     eax, [r13-1]
0x18002e135  xor     ecx, ecx
0x18002e137  lea     r9, [rbx+rax*8]
0x18002e13b  lea     r8, [rsi+rax*8]
0x18002e13f  cmp     rsi, r9
0x18002e142  ja      short loc_18002E149
0x18002e144  cmp     r8, rbx
0x18002e147  jnb     short loc_18002E161
0x18002e149  lea     rax, [rdi+rax*4]
0x18002e14d  cmp     rsi, rax
0x18002e150  ja      short loc_18002E157
0x18002e152  cmp     r8, rdi
0x18002e155  jnb     short loc_18002E161
0x18002e157  cmp     rbx, rax
0x18002e15a  ja      short loc_18002E181
0x18002e15c  cmp     r9, rdi
0x18002e15f  jb      short loc_18002E181
0x18002e161  mov     dword ptr [rdi+rcx*4], 0
0x18002e168  mov     qword ptr [rbx+rcx*8], 0
0x18002e170  mov     qword ptr [rsi+rcx*8], 0
0x18002e178  inc     ecx
0x18002e17a  cmp     ecx, r13d
0x18002e17d  jb      short loc_18002E161
0x18002e17f  jmp     short loc_18002E1BD
0x18002e181  mov     rax, [rbp+0D0h+var_C0]
0x18002e185  xor     edx, edx; Val
0x18002e187  mov     rcx, rdi; void *
0x18002e18a  lea     r8, ds:0[rax*4]
0x18002e192  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18002e196  call    memset_0
0x18002e19b  mov     r8, r15
0x18002e19e  xor     edx, edx; Val
0x18002e1a0  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x18002e1a4  mov     rcx, rbx; void *
0x18002e1a7  call    memset_0
0x18002e1ac  and     r15, 0FFFFFFFFFFFFFFF8h
0x18002e1b0  xor     edx, edx; Val
0x18002e1b2  mov     r8, r15; Size
0x18002e1b5  mov     rcx, rsi; void *
0x18002e1b8  call    memset_0
0x18002e1bd  xor     eax, eax
0x18002e1bf  xorps   xmm0, xmm0
0x18002e1c2  xorps   xmm1, xmm1
0x18002e1c5  mov     qword ptr [rbp+0D0h+pvarg+10h], rax
0x18002e1c9  movups  xmmword ptr [rbp+0D0h+pvarg], xmm0
0x18002e1cd  mov     qword ptr [rbp+0D0h+var_68+10h], rax
0x18002e1d1  xor     r14d, r14d
0x18002e1d4  movups  xmmword ptr [rbp+0D0h+var_68], xmm1
0x18002e1d8  mov     r15d, 2003h
0x18002e1de  cmp     r14d, r13d
0x18002e1e1  jnb     loc_18002E408
0x18002e1e7  lea     rcx, [rbp+0D0h+pvarg]; pvarg
0x18002e1eb  call    cs:__imp_VariantInit
0x18002e1f1  lea     rcx, [rbp+0D0h+var_68]; pvarg
0x18002e1f5  call    cs:__imp_VariantInit
0x18002e1fb  mov     eax, 3
0x18002e200  mov     word ptr [rbp+0D0h+pvarg], r15w
0x18002e205  mov     ecx, eax; vt
0x18002e207  mov     qword ptr [rbp+0D0h+rgsabound.cElements], rax
0x18002e20b  lea     r8, [rbp+0D0h+rgsabound]; rgsabound
0x18002e20f  lea     edx, [rax-2]; cDims
0x18002e212  call    cs:__imp_SafeArrayCreate
0x18002e218  test    rax, rax
0x18002e21b  jz      loc_18002E3AD
0x18002e221  mov     rcx, [rax+10h]
0x18002e225  lea     r9, [rbp+0D0h+var_68]
0x18002e229  mov     rdx, [rbp+0D0h+var_B8]
0x18002e22d  lea     r8, [rbp+0D0h+pvarg]
0x18002e231  mov     dword ptr [rcx], 2
  ... truncated ...
```
