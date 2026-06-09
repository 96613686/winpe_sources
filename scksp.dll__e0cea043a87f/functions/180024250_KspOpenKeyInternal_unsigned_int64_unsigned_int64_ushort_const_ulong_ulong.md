# KspOpenKeyInternal(unsigned __int64,unsigned __int64 *,ushort const *,ulong,ulong)

- ea: `0x180024250`
- end: `0x180024e91`
- name: `?KspOpenKeyInternal@@YAJ_KPEA_KPEBGKK@Z`
- size: `3137`
- prototype: `int(unsigned __int64, unsigned __int64 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002af10`

## callees

- `0x180009e82`
- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011444`
- `0x180011fd8`
- `0x1800122b4`
- `0x180012b24`
- `0x1800135dc`
- `0x180013734`
- `0x180013aac`
- `0x18001423c`
- `0x180014ecc`
- `0x18001594c`
- `0x18001abb4`
- `0x180024250`
- `0x18002b140`
- `0x18002d7f0`
- `0x18002ec0c`
- `0x18002ef78`
- `0x18002f034`
- `0x18003af5c`
- `0x18003bdd4`
- `0x18003c240`
- `0x18003d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall KspOpenKeyInternal(__int64 a1, unsigned __int64 *a2, unsigned __int16 *a3, int a4, unsigned int a5)
{
  _DWORD *v9; // rdi
  PVOID v10; // rcx
  PVOID v11; // rcx
  unsigned int Handle; // ebx
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rcx
  _QWORD *v17; // rcx
  int v18; // edx
  __int64 v19; // r13
  __int64 v20; // rcx
  __int64 v21; // rcx
  _DWORD *v22; // rax
  __int64 v23; // rcx
  int v24; // r15d
  int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // ebx
  int v29; // r11d
  unsigned int v30; // eax
  _QWORD *v31; // rcx
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  unsigned __int16 v37; // si
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // ebx
  char v42; // r11
  int v43; // eax
  __int64 v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // eax
  __int64 v47; // rcx
  unsigned int *v48; // rbx
  __int64 PqcParamInfoByPublicKeyLength; // rax
  bool v50; // zf
  unsigned int v51; // eax
  unsigned int v52; // eax
  unsigned int v53; // eax
  unsigned int v54; // eax
  unsigned int v55; // eax
  unsigned int v56; // eax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  __int64 v67; // rcx
  __int64 v68; // rcx
  int v70; // [rsp+28h] [rbp-D8h]
  _BYTE v71[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v72; // [rsp+44h] [rbp-BCh] BYREF
  void **v73; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+58h] [rbp-A8h]
  __int64 v75; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v76[2]; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 *v77; // [rsp+78h] [rbp-88h]
  __int128 v78; // [rsp+80h] [rbp-80h] BYREF
  __int128 v79; // [rsp+90h] [rbp-70h]
  __int64 v80; // [rsp+A0h] [rbp-60h]
  unsigned __int16 v81[41]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v82; // [rsp+102h] [rbp+2h]
  unsigned __int16 v83; // [rsp+104h] [rbp+4h]
  unsigned __int16 v84[40]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v85[264]; // [rsp+160h] [rbp+60h] BYREF

  v77 = a2;
  v9 = 0;
  v72 = 0;
  v75 = 0;
  memset_0(v85, 0, 0x208u);
  memset_0(v84, 0, sizeof(v84));
  memset_0(v81, 0, 0x56u);
  v71[0] = 0;
  v78 = 0;
  v79 = 0;
  v80 = 0;
  v73 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v74 = 0;
  v76[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v76[1] = 0;
  WppTraceIndent(0, 0);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, WPP_pszIndent);
  }
  if ( !a2 || !a3 )
  {
    WppTraceIndent((__int64)v10, 2u);
    Handle = -2146893785;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, 2148073511LL);
    }
    goto LABEL_173;
  }
  if ( (a5 & 0xFFFFFE9F) != 0 )
  {
    WppTraceIndent((__int64)v10, 2u);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        237,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        a5);
    }
    WppTraceIndent((__int64)v11, 2u);
    Handle = -2146893815;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = 238;
LABEL_16:
      v15 = Handle;
LABEL_17:
      WPP_SF_d(v13[2], v14, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v15);
      goto LABEL_173;
    }
    goto LABEL_173;
  }
  *a2 = 0;
  Handle = HtGetHandle(a1, 3, &v75);
  if ( Handle )
  {
    WppTraceIndent(v16, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_173;
    }
    v18 = 239;
    goto LABEL_23;
  }
  v19 = v75;
  Handle = KspEnterCriticalSection(v75 + 16);
  if ( Handle )
  {
    WppTraceIndent(v20, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_173;
    }
    v18 = 240;
    goto LABEL_23;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v76, v19 + 16);
  Handle = KsppAnalyzeContainerName(a3, v85, v84, v70, (__int64)&v72);
  if ( Handle )
  {
    WppTraceIndent(v21, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_173;
    }
    v18 = 241;
    goto LABEL_23;
  }
  v22 = MIDL_user_allocate(0x4C0u);
  v9 = v22;
  if ( !v22 )
  {
    Handle = -2146893810;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        242,
        &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        WPP_pszIndent);
    }
    goto LABEL_173;
  }
  memset_0(v22, 0, 0x4C0u);
  v9[266] = a5 & 0x140 | *(_DWORD *)(v19 + 60) & 0x40;
  v24 = HIDWORD(v72);
  if ( (a5 & 0x100) != 0 )
  {
    if ( !HIDWORD(v72) )
    {
      WppTraceIndent(v23, 2u);
      v15 = 2148073511LL;
      Handle = -2146893785;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 243;
        goto LABEL_17;
      }
      goto LABEL_173;
    }
    v25 = v72;
    if ( (_DWORD)v72 )
    {
      v25 = 0;
      memset_0(v84, 0, sizeof(v84));
    }
  }
  else
  {
    v25 = v72;
  }
  Handle = KsppCardConnect(
             v19,
             (unsigned __int64)v84 & -(__int64)(v25 != 0),
             (unsigned __int64)v85 & -(__int64)(v24 != 0),
             (int)v9 + 1072,
             v9[266],
             *(_QWORD *)(v19 + 104));
  if ( Handle )
  {
    WppTraceIndent(v26, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_173;
    }
    v18 = 244;
    goto LABEL_23;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v73, *((_QWORD *)v9 + 136) + 624LL);
  if ( v84[0] )
  {
    v28 = StringCchCopyW(v81, 0x28u, v84);
    if ( v28 < 0 )
    {
      WppTraceIndent(v27, v29 + 2);
      v30 = HR_Remap((unsigned int)v28);
      Handle = v30;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v32 = 245;
      goto LABEL_59;
    }
    Handle = ContainerMapFindContainer(*((_QWORD *)v9 + 136), v81, v71);
    if ( Handle )
    {
      WppTraceIndent(v33, 2u);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v18 = 246;
      goto LABEL_23;
    }
LABEL_77:
    v37 = v82;
    goto LABEL_78;
  }
  v34 = *((_QWORD *)v9 + 136);
  if ( (a5 & 0x100) == 0 )
  {
    Handle = ContainerMapGetDefaultContainer(v34, v81, v71);
    if ( Handle )
    {
      WppTraceIndent(v38, 2u);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v18 = 248;
      goto LABEL_23;
    }
    goto LABEL_77;
  }
  v35 = *(_QWORD *)(v34 + 8);
  LODWORD(v72) = 0;
  Handle = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v35 + 520))(*(_QWORD *)(v34 + 8), &v72);
  if ( Handle )
  {
    WppTraceIndent(v36, 2u);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_173;
    }
    v18 = 247;
    goto LABEL_23;
  }
  v37 = WORD1(v72);
  v82 = WORD1(v72);
LABEL_78:
  v41 = StringCchCopyW((unsigned __int16 *)v9, 0x104u, v81);
  if ( v41 < 0 )
  {
    WppTraceIndent(v40, 2u);
    v30 = HR_Remap((unsigned int)v41);
    Handle = v30;
    v31 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_173;
    }
    v32 = 249;
    goto LABEL_59;
  }
  *((_BYTE *)v9 + 1068) = v42;
  v9[262] = 1;
  v9[264] = 1;
  if ( !a4 )
  {
    LOBYTE(v39) = v42;
    Handle = CspGetContainerInfo(*((_QWORD *)v9 + 136), v39, 0, &v78);
    if ( Handle )
    {
      WppTraceIndent(v44, 2u);
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_173;
      }
      v18 = 251;
      goto LABEL_23;
    }
    v40 = 0;
    v45 = 0;
    v46 = v83;
    if ( !v83 )
    {
      if ( !v37 )
      {
LABEL_108:
        v40 = v80;
        v45 = v46;
        v9[261] = v46;
LABEL_109:
        if ( !v40 )
          goto LABEL_94;
        Handle = KsppTranslateAlgIdToKeySpec(v40, v45, v9 + 260);
        if ( !Handle )
          goto LABEL_94;
        WppTraceIndent(v40, 2u);
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_173;
        }
        v18 = 252;
LABEL_23:
        WPP_SF_sd(
          v17[2],
          v18,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          Handle);
        goto LABEL_173;
      }
      v40 = v79;
      v45 = v37;
      v9[261] = v37;
    }
    if ( v37 )
      goto LABEL_109;
    goto LABEL_108;
  }
  if ( (unsigned int)(a4 - 2) <= 3 )
  {
    v43 = v37;
  }
  else
  {
    if ( a4 != 1 && (unsigned int)(a4 - 6) > 2 )
    {
      WppTraceIndent(v40, 2u);
      v15 = 2148073511LL;
      Handle = -2146893785;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 250;
        goto LABEL_17;
      }
      goto LABEL_173;
    }
    v43 = v83;
  }
  v9[261] = v43;
  v9[260] = a4;
LABEL_94:
  if ( v9[261] )
  {
    v48 = v9 + 260;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl)
      && *v48 - 64 <= 1 )
    {
      PqcParamInfoByPublicKeyLength = GetPqcParamInfoByPublicKeyLength((unsigned int)v9[261]);
      v47 = PqcParamInfoByPublicKeyLength;
      if ( !PqcParamInfoByPublicKeyLength )
      {
        WppTraceIndent(0, 2u);
        v15 = 2148073511LL;
        Handle = -2146893785;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v14 = 254;
          goto LABEL_17;
        }
        goto LABEL_173;
      }
      *v48 = *(_DWORD *)(PqcParamInfoByPublicKeyLength + 32);
      *((_QWORD *)v9 + 151) = *(_QWORD *)PqcParamInfoByPublicKeyLength;
    }
    if ( a4 && a4 != *v48 )
    {
      WppTraceIndent(v47, 2u);
      v15 = 2148073511LL;
      Handle = -2146893785;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v14 = 255;
        goto LABEL_17;
      }
      goto LABEL_173;
    }
    v50 = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) == 0;
    v51 = *v48;
    if ( v50 )
    {
      v61 = v51 - 1;
      if ( v61 )
      {
        v62 = v61 - 1;
        if ( v62 )
        {
          v63 = v62 - 1;
          if ( v63 )
          {
            v64 = v63 - 1;
            if ( v64 )
            {
              v65 = v64 - 1;
              if ( v65 )
              {
                v66 = v65 - 1;
                if ( v66 && v66 - 1 >= 2 )
                {
                  WppTraceIndent(0, 2u);
                  v15 = 2148073511LL;
                  Handle = -2146893785;
                  v13 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    v14 = 257;
                    goto LABEL_17;
                  }
                  goto LABEL_173;
                }
                goto LABEL_138;
              }
            }
          }
        }
        goto LABEL_160;
      }
    }
    else
    {
      if ( v51 > 8 )
      {
        v57 = v51 - 9;
        if ( v57 )
        {
          v58 = v57 - 1;
          if ( v58 )
          {
            v59 = v58 - 1;
            if ( v59 )
            {
              v60 = v59 - 1;
              if ( !v60 || v60 - 1 < 2 )
              {
                v9[297] = 0xFFFFFF;
                goto LABEL_162;
              }
              goto LABEL_144;
            }
          }
        }
LABEL_160:
        v9[297] = 2;
        goto LABEL_162;
      }
      if ( v51 == 8 )
      {
LABEL_138:
        v9[297] = 4;
LABEL_162:
        if ( v74 )
        {
          v74 = 0;
          KsppEndCardCall(v9 + 268);
        }
        Handle = HtAddHandle(v9, 2, v77);
        if ( (Handle & 0x80000000) == 0 )
          goto LABEL_173;
        WppTraceIndent(v67, 2u);
        v30 = HR_Remap(Handle);
        Handle = v30;
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_173;
        }
        v32 = 258;
LABEL_59:
        WPP_SF_sd(
          v31[2],
          v32,
          (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
          (_DWORD)WPP_pszIndent,
          v30);
        goto LABEL_173;
      }
      v52 = v51 - 1;
      if ( v52 )
      {
        v53 = v52 - 1;
        if ( v53 )
        {
          v54 = v53 - 1;
          if ( v54 )
          {
            v55 = v54 - 1;
            if ( v55 )
            {
              v56 = v55 - 1;
              if ( v56 )
              {
                if ( v56 - 1 <= 1 )
                  goto LABEL_138;
LABEL_144:
                WppTraceIndent(0, 2u);
                v15 = 2148073511LL;
                Handle = -2146893785;
                v13 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  v14 = 256;
                  goto LABEL_17;
                }
                goto LABEL_173;
              }
            }
          }
        }
        goto LABEL_160;
      }
    }
    v9[297] = 3;
    goto LABEL_162;
  }
  WppTraceIndent(v40, 2u);
  Handle = -2146893802;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v14 = 253;
    goto LABEL_16;
  }
LABEL_173:
  if ( v74 )
  {
    v74 = 0;
    KsppEndCardCall(v9 + 268);
  }
  if ( v9 && Handle )
    CspFreeH(v9);
  if ( (_QWORD)v79 )
    CspFreeH(v79);
  v68 = v80;
  if ( v80 )
    CspFreeH(v80);
  WppTraceIndent(v68, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      259,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
  }
  v76[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v76);
  v73 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v73);
  return Handle;
}

```

## disassembly

```asm
0x180024250  mov     [rsp-8+arg_18], rbx
0x180024255  push    rbp
0x180024256  push    rsi
0x180024257  push    rdi
0x180024258  push    r12
0x18002425a  push    r13
0x18002425c  push    r14
0x18002425e  push    r15
0x180024260  lea     rbp, [rsp-280h]
0x180024268  sub     rsp, 380h
0x18002426f  mov     rax, cs:__security_cookie
0x180024276  xor     rax, rsp
0x180024279  mov     [rbp+2B0h+var_40], rax
0x180024280  mov     r14d, r9d
0x180024283  mov     r12, r8
0x180024286  mov     r15, rdx
0x180024289  mov     [rsp+3B0h+var_338], rdx
0x18002428e  mov     rbx, rcx
0x180024291  xor     edi, edi
0x180024293  mov     dword ptr [rsp+3B0h+var_36C], edi
0x180024297  mov     dword ptr [rsp+3B0h+var_36C+4], edi
0x18002429b  mov     [rsp+3B0h+var_350], rdi
0x1800242a0  xor     edx, edx; Val
0x1800242a2  mov     r8d, 208h; Size
0x1800242a8  lea     rcx, [rbp+2B0h+var_250]; void *
0x1800242ac  call    memset_0
0x1800242b1  xor     edx, edx; Val
0x1800242b3  lea     r8d, [rdi+50h]; Size
0x1800242b7  lea     rcx, [rbp+2B0h+var_2A0]; void *
0x1800242bb  call    memset_0
0x1800242c0  xor     edx, edx; Val
0x1800242c2  lea     r8d, [rdi+56h]; Size
0x1800242c6  lea     rcx, [rbp+2B0h+var_300]; void *
0x1800242ca  call    memset_0
0x1800242cf  xor     ecx, ecx
0x1800242d1  mov     [rsp+3B0h+var_370], cl
0x1800242d5  xorps   xmm0, xmm0
0x1800242d8  xor     eax, eax
0x1800242da  movups  [rbp+2B0h+var_330], xmm0
0x1800242de  movups  [rbp+2B0h+var_320], xmm0
0x1800242e2  mov     [rbp+2B0h+var_310], rax
0x1800242e6  lea     rsi, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x1800242ed  mov     [rsp+3B0h+var_360], rsi
0x1800242f2  mov     [rsp+3B0h+var_358], rcx
0x1800242f7  mov     [rsp+3B0h+var_348], rsi
0x1800242fc  mov     [rsp+3B0h+var_340], rcx
0x180024301  xor     edx, edx
0x180024303  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024308  lea     r13, WPP_GLOBAL_Control
0x18002430f  mov     rcx, cs:WPP_GLOBAL_Control
0x180024316  cmp     rcx, r13
0x180024319  jz      short loc_180024343
0x18002431b  test    byte ptr [rcx+1Ch], 2
0x18002431f  jz      short loc_180024343
0x180024321  cmp     byte ptr [rcx+19h], 5
0x180024325  jb      short loc_180024343
0x180024327  mov     edx, 0EBh
0x18002432c  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024333  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002433a  mov     rcx, [rcx+10h]
0x18002433e  call    WPP_SF_s
0x180024343  xor     eax, eax
0x180024345  test    r15, r15
0x180024348  jz      loc_180024D69
0x18002434e  test    r12, r12
0x180024351  jz      loc_180024D69
0x180024357  mov     esi, [rbp+2B0h+arg_20]
0x18002435d  test    esi, 0FFFFFE9Fh
0x180024363  jz      loc_1800243F9
0x180024369  lea     edx, [rax+2]
0x18002436c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024371  mov     rcx, cs:WPP_GLOBAL_Control
0x180024378  cmp     rcx, r13
0x18002437b  jz      short loc_1800243A9
0x18002437d  test    byte ptr [rcx+1Ch], 1
0x180024381  jz      short loc_1800243A9
0x180024383  cmp     byte ptr [rcx+19h], 2
0x180024387  jb      short loc_1800243A9
0x180024389  mov     edx, 0EDh
0x18002438e  mov     dword ptr [rsp+3B0h+var_390], esi
0x180024392  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024399  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800243a0  mov     rcx, [rcx+10h]
0x1800243a4  call    WPP_SF_sd
0x1800243a9  mov     edx, 2
0x1800243ae  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800243b3  mov     ebx, 80090009h
0x1800243b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800243bf  cmp     rcx, r13
0x1800243c2  jz      loc_180024DB2
0x1800243c8  test    byte ptr [rcx+1Ch], 1
0x1800243cc  jz      loc_180024DB2
0x1800243d2  cmp     byte ptr [rcx+19h], 2
0x1800243d6  jb      loc_180024DB2
0x1800243dc  mov     edx, 0EEh
0x1800243e1  mov     r9d, ebx
0x1800243e4  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800243eb  mov     rcx, [rcx+10h]
0x1800243ef  call    WPP_SF_d
0x1800243f4  jmp     loc_180024DB2
0x1800243f9  mov     [r15], rax
0x1800243fc  lea     r8, [rsp+3B0h+var_350]
0x180024401  mov     edx, 3
0x180024406  mov     rcx, rbx
0x180024409  call    HtGetHandle
0x18002440e  mov     ebx, eax
0x180024410  test    eax, eax
0x180024412  jz      short loc_180024467
0x180024414  mov     edx, 2
0x180024419  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002441e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024425  cmp     rcx, r13
0x180024428  jz      loc_180024DB2
0x18002442e  test    byte ptr [rcx+1Ch], 1
0x180024432  jz      loc_180024DB2
0x180024438  cmp     byte ptr [rcx+19h], 2
0x18002443c  jb      loc_180024DB2
0x180024442  mov     edx, 0EFh
0x180024447  mov     dword ptr [rsp+3B0h+var_390], ebx
0x18002444b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024452  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180024459  mov     rcx, [rcx+10h]
0x18002445d  call    WPP_SF_sd
0x180024462  jmp     loc_180024DB2
0x180024467  mov     r13, [rsp+3B0h+var_350]
0x18002446c  lea     rcx, [r13+10h]
0x180024470  call    KspEnterCriticalSection
0x180024475  mov     ebx, eax
0x180024477  test    eax, eax
0x180024479  jz      short loc_1800244B7
0x18002447b  mov     edx, 2
0x180024480  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024485  mov     rcx, cs:WPP_GLOBAL_Control
0x18002448c  lea     r13, WPP_GLOBAL_Control
0x180024493  cmp     rcx, r13
0x180024496  jz      loc_180024DB2
0x18002449c  test    byte ptr [rcx+1Ch], 1
0x1800244a0  jz      loc_180024DB2
0x1800244a6  cmp     byte ptr [rcx+19h], 2
0x1800244aa  jb      loc_180024DB2
0x1800244b0  mov     edx, 0F0h
0x1800244b5  jmp     short loc_180024447
0x1800244b7  lea     rdx, [r13+10h]
0x1800244bb  lea     rcx, [rsp+3B0h+var_348]
0x1800244c0  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x1800244c5  lea     rax, [rsp+3B0h+var_36C]
0x1800244ca  mov     [rsp+3B0h+var_380], rax; __int64
0x1800244cf  lea     rax, [rbp+2B0h+var_2A0]
0x1800244d3  mov     [rsp+3B0h+var_390], rax; unsigned __int16 *
0x1800244d8  lea     r9, [rsp+3B0h+var_36C+4]
0x1800244dd  lea     rdx, [rbp+2B0h+var_250]; unsigned __int16 *
0x1800244e1  mov     rcx, r12; unsigned __int16 *
0x1800244e4  call    KsppAnalyzeContainerName
0x1800244e9  mov     ebx, eax
0x1800244eb  test    eax, eax
0x1800244ed  jz      short loc_18002452E
0x1800244ef  mov     edx, 2
0x1800244f4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800244f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180024500  lea     r13, WPP_GLOBAL_Control
0x180024507  cmp     rcx, r13
0x18002450a  jz      loc_180024DB2
0x180024510  test    byte ptr [rcx+1Ch], 1
0x180024514  jz      loc_180024DB2
0x18002451a  cmp     byte ptr [rcx+19h], 2
0x18002451e  jb      loc_180024DB2
0x180024524  mov     edx, 0F1h
0x180024529  jmp     loc_180024447
0x18002452e  mov     ebx, 4C0h
0x180024533  mov     ecx, ebx; size
0x180024535  call    MIDL_user_allocate
0x18002453a  mov     rdi, rax
0x18002453d  test    rax, rax
0x180024540  jnz     short loc_180024593
0x180024542  mov     ebx, 8009000Eh
0x180024547  mov     rcx, cs:WPP_GLOBAL_Control
0x18002454e  lea     r13, WPP_GLOBAL_Control
0x180024555  cmp     rcx, r13
0x180024558  jz      loc_180024DB2
0x18002455e  test    byte ptr [rcx+1Ch], 1
0x180024562  jz      loc_180024DB2
0x180024568  cmp     byte ptr [rcx+19h], 2
0x18002456c  jb      loc_180024DB2
0x180024572  mov     edx, 0F2h
0x180024577  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18002457e  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x180024585  mov     rcx, [rcx+10h]
0x180024589  call    WPP_SF_s
0x18002458e  jmp     loc_180024DB2
0x180024593  mov     r8, rbx; Size
0x180024596  xor     edx, edx; Val
0x180024598  mov     rcx, rdi; void *
0x18002459b  call    memset_0
0x1800245a0  mov     eax, [r13+3Ch]
0x1800245a4  and     eax, 40h
0x1800245a7  or      eax, esi
0x1800245a9  and     eax, 140h
0x1800245ae  mov     [rdi+428h], eax
0x1800245b4  mov     r15d, dword ptr [rsp+3B0h+var_36C+4]
0x1800245b9  and     esi, 100h
0x1800245bf  jz      short loc_180024629
0x1800245c1  xor     eax, eax
0x1800245c3  test    r15d, r15d
0x1800245c6  jnz     short loc_18002460E
0x1800245c8  lea     edx, [rax+2]
0x1800245cb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800245d0  mov     r9d, 80090027h
0x1800245d6  mov     ebx, r9d
0x1800245d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800245e0  lea     r13, WPP_GLOBAL_Control
0x1800245e7  cmp     rcx, r13
0x1800245ea  jz      loc_180024DB2
0x1800245f0  test    byte ptr [rcx+1Ch], 1
0x1800245f4  jz      loc_180024DB2
0x1800245fa  cmp     byte ptr [rcx+19h], 2
0x1800245fe  jb      loc_180024DB2
0x180024604  mov     edx, 0F3h
0x180024609  jmp     loc_1800243E4
0x18002460e  mov     ebx, dword ptr [rsp+3B0h+var_36C]
0x180024612  test    ebx, ebx
0x180024614  jz      short loc_18002462D
0x180024616  mov     ebx, eax
0x180024618  xor     edx, edx; Val
0x18002461a  lea     r8d, [rdx+50h]; Size
0x18002461e  lea     rcx, [rbp+2B0h+var_2A0]; void *
0x180024622  call    memset_0
0x180024627  jmp     short loc_18002462D
0x180024629  mov     ebx, dword ptr [rsp+3B0h+var_36C]
0x18002462d  mov     rax, [r13+68h]
0x180024631  mov     r9d, [rdi+428h]
0x180024638  lea     r12, [rdi+430h]
0x18002463f  neg     r15d
0x180024642  sbb     r8, r8
0x180024645  lea     rcx, [rbp+2B0h+var_250]
0x180024649  and     r8, rcx
0x18002464c  neg     ebx
0x18002464e  sbb     rdx, rdx
0x180024651  lea     rcx, [rbp+2B0h+var_2A0]
0x180024655  and     rdx, rcx
0x180024658  mov     [rsp+3B0h+var_388], rax
0x18002465d  mov     dword ptr [rsp+3B0h+var_390], r9d
0x180024662  mov     r9, r12
0x180024665  mov     rcx, r13
0x180024668  call    KsppCardConnect
0x18002466d  mov     ebx, eax
0x18002466f  test    eax, eax
0x180024671  jz      short loc_1800246B2
0x180024673  mov     edx, 2
0x180024678  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002467d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024684  lea     r13, WPP_GLOBAL_Control
0x18002468b  cmp     rcx, r13
0x18002468e  jz      loc_180024DB2
0x180024694  test    byte ptr [rcx+1Ch], 1
0x180024698  jz      loc_180024DB2
0x18002469e  cmp     byte ptr [rcx+19h], 2
0x1800246a2  jb      loc_180024DB2
0x1800246a8  mov     edx, 0F4h
0x1800246ad  jmp     loc_180024447
0x1800246b2  mov     rdx, [rdi+440h]
0x1800246b9  add     rdx, 270h
0x1800246c0  lea     rcx, [rsp+3B0h+var_360]
0x1800246c5  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x1800246ca  xor     r11d, r11d
0x1800246cd  cmp     [rbp+2B0h+var_2A0], r11w
0x1800246d2  jz      loc_180024798
0x1800246d8  lea     r8, [rbp+2B0h+var_2A0]; unsigned __int16 *
0x1800246dc  lea     edx, [r11+28h]; unsigned __int64
0x1800246e0  lea     rcx, [rbp+2B0h+var_300]; unsigned __int16 *
0x1800246e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800246e9  mov     ebx, eax
0x1800246eb  test    eax, eax
0x1800246ed  jns     short loc_18002473A
0x1800246ef  lea     edx, [r11+2]
0x1800246f3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800246f8  mov     ecx, ebx
0x1800246fa  call    HR_Remap
0x1800246ff  mov     ebx, eax
0x180024701  mov     rcx, cs:WPP_GLOBAL_Control
0x180024708  lea     r13, WPP_GLOBAL_Control
0x18002470f  cmp     rcx, r13
0x180024712  jz      loc_180024DB2
0x180024718  test    byte ptr [rcx+1Ch], 1
0x18002471c  jz      loc_180024DB2
0x180024722  cmp     byte ptr [rcx+19h], 2
0x180024726  jb      loc_180024DB2
0x18002472c  mov     edx, 0F5h
0x180024731  mov     dword ptr [rsp+3B0h+var_390], eax
0x180024735  jmp     loc_18002444B
0x18002473a  lea     r8, [rsp+3B0h+var_370]
0x18002473f  lea     rdx, [rbp+2B0h+var_300]
0x180024743  mov     rcx, [rdi+440h]
0x18002474a  call    ContainerMapFindContainer
0x18002474f  mov     ebx, eax
0x180024751  test    eax, eax
0x180024753  jz      loc_180024869
0x180024759  mov     edx, 2
0x18002475e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024763  mov     rcx, cs:WPP_GLOBAL_Control
0x18002476a  lea     r13, WPP_GLOBAL_Control
  ... truncated ...
```
