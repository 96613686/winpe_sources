# KsppFinalizeKey

- ea: `0x180016adc`
- end: `0x180017b1c`
- name: `KsppFinalizeKey`
- size: `4160`
- prototype: ``
- caller_count: `2`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800206e8`
- `0x1800232ec`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x18000d9d0`
- `0x180011fd8`
- `0x1800122b4`
- `0x180013734`
- `0x180013aac`
- `0x180014648`
- `0x180014ecc`
- `0x18001594c`
- `0x180016adc`
- `0x18001b0c4`
- `0x18001b2b4`
- `0x18001c778`
- `0x18002b140`
- `0x18002ce34`
- `0x18002d368`
- `0x18002db88`
- `0x18002dd50`
- `0x18002ec40`
- `0x18002ee0c`
- `0x18002f034`
- `0x18002f108`
- `0x18003bebc`
- `0x18003bee4`
- `0x18003c240`

## import_xrefs

- `ncrypt!NCryptDeleteKey` at `0x180016dae`
- `ncrypt!NCryptDeleteKey` at `0x180016dae`
- `ncrypt!NCryptFinalizeKey` at `0x180017654`
- `ncrypt!NCryptFinalizeKey` at `0x180017654`
- `ncrypt!NCryptExportKey` at `0x1800177c0`
- `ncrypt!NCryptExportKey` at `0x180017895`
- `ncrypt!NCryptExportKey` at `0x1800177c0`
- `ncrypt!NCryptExportKey` at `0x180017895`
- `ncrypt!NCryptCreatePersistedKey` at `0x180017137`
- `ncrypt!NCryptCreatePersistedKey` at `0x180017137`
- `ncrypt!NCryptSetProperty` at `0x1800171be`
- `ncrypt!NCryptSetProperty` at `0x180017299`
- `ncrypt!NCryptSetProperty` at `0x18001730c`
- `ncrypt!NCryptSetProperty` at `0x180017371`
- `ncrypt!NCryptSetProperty` at `0x180017467`
- `ncrypt!NCryptSetProperty` at `0x1800174dc`
- `ncrypt!NCryptSetProperty` at `0x180017532`
- `ncrypt!NCryptSetProperty` at `0x1800175ac`
- `ncrypt!NCryptSetProperty` at `0x180017602`
- `ncrypt!NCryptSetProperty` at `0x1800171be`
- `ncrypt!NCryptSetProperty` at `0x180017299`
- `ncrypt!NCryptSetProperty` at `0x18001730c`
- `ncrypt!NCryptSetProperty` at `0x180017371`
- `ncrypt!NCryptSetProperty` at `0x180017467`
- `ncrypt!NCryptSetProperty` at `0x1800174dc`
- `ncrypt!NCryptSetProperty` at `0x180017532`
- `ncrypt!NCryptSetProperty` at `0x1800175ac`
- `ncrypt!NCryptSetProperty` at `0x180017602`

## pseudocode

```c
__int64 __fastcall KsppFinalizeKey(_QWORD *a1, __int64 a2, int a3)
{
  int v6; // r13d
  BYTE *v7; // r12
  PVOID v8; // rcx
  __int64 v9; // r9
  unsigned int Container; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // edx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned __int64 v23; // rcx
  NCRYPT_KEY_HANDLE v24; // rcx
  unsigned int v26; // r8d
  unsigned int v27; // r11d
  unsigned int v28; // r9d
  _DWORD *v29; // r10
  unsigned int v30; // eax
  int v31; // r8d
  int v32; // r9d
  int v33; // r8d
  int v34; // r9d
  int v35; // esi
  __int64 v36; // rcx
  __int64 v37; // rcx
  char IsEnabled; // al
  DWORD v39; // edx
  SECURITY_STATUS v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rcx
  BYTE *v43; // r8
  __int64 v44; // r9
  SECURITY_STATUS v45; // eax
  __int64 v46; // rcx
  SECURITY_STATUS v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  const WCHAR *v51; // rbx
  __int64 v52; // rcx
  DWORD v53; // r9d
  BYTE *v54; // r8
  __int64 v55; // rcx
  __int64 v56; // rcx
  DWORD v57; // r9d
  BYTE *v58; // r8
  __int64 v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  BYTE *v62; // rdx
  const WCHAR *v63; // r14
  unsigned int v64; // eax
  __int64 v65; // rcx
  unsigned int v66; // eax
  __int64 v67; // rcx
  __int64 v68; // rcx
  BYTE *v69; // rax
  __int64 v70; // rcx
  __int64 v71; // rcx
  int v72; // edx
  __int64 v73; // rcx
  int v74; // r8d
  __int64 v75; // rcx
  _BYTE *v76; // rax
  __int64 v77; // rcx
  unsigned __int8 dwLegacyKeySpec; // [rsp+20h] [rbp-E0h]
  NCRYPT_KEY_HANDLE hKey; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v80[4]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbOutput; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE pbInput[8]; // [rsp+50h] [rbp-B0h] BYREF
  const WCHAR *v83; // [rsp+58h] [rbp-A8h] BYREF
  void **v84; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v85; // [rsp+68h] [rbp-98h]
  LPCWSTR pszAlgId[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v87[96]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v88; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v89; // [rsp+F0h] [rbp-10h]
  __int64 v90; // [rsp+F8h] [rbp-8h] BYREF
  int v91; // [rsp+100h] [rbp+0h]

  *(_DWORD *)pbInput = 3;
  pszAlgId[0] = 0;
  v90 = 0;
  v91 = 0;
  v89 = 0;
  v83 = 0;
  v84 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  hKey = 0;
  v6 = 0;
  cbOutput = 0;
  v88 = 0;
  v7 = 0;
  v80[0] = 0;
  v85 = 0;
  WppTraceIndent(a1, 0);
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, WPP_pszIndent);
  }
  if ( *(_DWORD *)(a2 + 1048) )
  {
    WppTraceIndent(v8, 2);
    v9 = 2148073483LL;
    Container = -2146893813;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = 99;
LABEL_10:
      WPP_SF_d(v11[2], v12, &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids, v9);
      goto LABEL_36;
    }
    goto LABEL_36;
  }
  if ( *(_WORD *)a2 )
  {
    LODWORD(v13) = a2 + 520;
    if ( !*(_WORD *)(a2 + 520) )
    {
      LODWORD(v13) = 0;
      if ( a1[18] )
        v13 = a1[18];
    }
    v14 = *(_QWORD *)(a2 + 1088);
    if ( v14 )
    {
      CardStateReleaseRef(v14, 0);
      *(_QWORD *)(a2 + 1088) = 0;
    }
    *(_DWORD *)(a2 + 1064) |= a3 & 0x40;
    Container = KsppCardConnect(
                  (_DWORD)a1,
                  a2,
                  v13,
                  (int)a2 + 1072,
                  *(_DWORD *)(a2 + 1064) | a3 | 8u,
                  *(_QWORD *)(a2 + 1104));
    if ( Container )
    {
      WppTraceIndent(v15, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v17 = 101;
      goto LABEL_26;
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(&v84, *(_QWORD *)(a2 + 1088) + 624LL);
    Container = CspQueryCapabilities(*(_QWORD *)(a2 + 1088), &v90);
    if ( Container )
    {
      WppTraceIndent(v18, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v17 = 102;
      goto LABEL_26;
    }
    v20 = *(unsigned int *)(a2 + 1040);
    v21 = *(_QWORD *)(a2 + 1088);
    LODWORD(v88) = 1;
    v22 = CspQueryKeySizes(v21, v20, v19, &v88);
    Container = v22;
    if ( v22 == -2146435068 )
    {
LABEL_35:
      Container = -2146893816;
      goto LABEL_36;
    }
    if ( v22 )
    {
      if ( v22 != 87 )
        goto LABEL_36;
      goto LABEL_35;
    }
    if ( *(_DWORD *)(a2 + 1052) )
    {
      v26 = v89;
      v27 = HIDWORD(v88);
      v28 = DWORD1(v88);
      if ( !*(_DWORD *)(a2 + 1060) )
      {
        v29 = (_DWORD *)(a2 + 1044);
        if ( a2 == -1044 || (unsigned int)v88 > 1 )
        {
          Container = -2146435068;
          WppTraceIndent(v23, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              103,
              (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
              (_DWORD)WPP_pszIndent,
              4);
          }
          goto LABEL_36;
        }
        if ( HIDWORD(v88) < *v29 )
        {
          v23 = HIDWORD(v88);
        }
        else
        {
          v23 = DWORD2(v88);
          if ( DWORD1(v88) <= *v29 )
          {
            if ( *v29 >= DWORD2(v88) )
              v23 = (unsigned int)*v29;
            if ( v89 && (unsigned int)v23 % v89 )
              v23 = v89 - (unsigned int)v23 % v89 + (unsigned int)v23;
          }
        }
        *v29 = v23;
      }
      v30 = *(_DWORD *)(a2 + 1044);
      if ( v30 < v28 || v30 > v27 )
      {
        WppTraceIndent(v23, 2);
        v23 = (unsigned __int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_sddd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            104,
            v31,
            v32,
            SBYTE4(v88),
            SBYTE12(v88),
            *(_DWORD *)(a2 + 1044));
        }
        v26 = v89;
        v28 = DWORD1(v88);
      }
      if ( v26 )
      {
        if ( (*(_DWORD *)(a2 + 1044) - v28) % v26 )
        {
          WppTraceIndent(v23, 2);
          v23 = (unsigned __int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_sddd(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, v33, v34, SBYTE4(v88), v89, *(_DWORD *)(a2 + 1044));
          }
        }
      }
    }
    v35 = 1;
    if ( (*(_BYTE *)(a2 + 1184) & 0xC) != 0 )
    {
      if ( dword_18004C298 )
      {
        WppTraceIndent(v23, 2);
        v9 = 2148073513LL;
        Container = -2146893783;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 106;
          goto LABEL_10;
        }
        goto LABEL_36;
      }
      v35 = 0;
    }
    if ( v91 )
    {
      if ( v35 )
      {
LABEL_207:
        Container = KsppAuthenticateUser(a2 + 1072, 1, 0, *(unsigned int *)(a2 + 1112));
        if ( Container )
        {
          WppTraceIndent(v70, 2);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v17 = 127;
        }
        else
        {
          Container = ContainerMapAddContainer(
                        *(_QWORD *)(a2 + 1088),
                        (unsigned __int16 *)a2,
                        *(_DWORD *)(a2 + 1044),
                        *(_DWORD *)(a2 + 1040),
                        dwLegacyKeySpec,
                        (unsigned __int8 *)(a2 + 1096));
          if ( Container )
          {
            WppTraceIndent(v71, 2);
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_36;
            }
            v17 = 128;
          }
          else
          {
            v6 = 1;
            if ( (unsigned int)ContainerMapGetDefaultContainer(*(_QWORD *)(a2 + 1088), v87, 0) == -2146893802
              && (Container = ContainerMapSetDefaultContainer(*(_QWORD *)(a2 + 1088), a2)) != 0 )
            {
              WppTraceIndent(v73, 2);
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_36;
              }
              v17 = 129;
            }
            else
            {
              if ( v35 )
                v74 = (*(_QWORD *)(a2 + 1160) != 0) + 1;
              else
                v74 = 2;
              v75 = (__int64)v7;
              if ( *(_QWORD *)(a2 + 1160) )
                v75 = *(_QWORD *)(a2 + 1160);
              LOBYTE(v72) = *(_BYTE *)(a2 + 1096);
              Container = CspCreateContainer(
                            *(_QWORD *)(a2 + 1088),
                            v72,
                            v74,
                            *(_DWORD *)(a2 + 1040),
                            *(_DWORD *)(a2 + 1044),
                            v75);
              if ( !Container )
              {
                *(_BYTE *)(a2 + 1068) = *(_BYTE *)(a2 + 1096);
                v76 = *(_BYTE **)(a2 + 1160);
                *(_DWORD *)(a2 + 1048) = 1;
                *(_DWORD *)(a2 + 1056) = 1;
                if ( v76 )
                {
                  v77 = *(unsigned int *)(a2 + 1168);
                  if ( *(_DWORD *)(a2 + 1168) )
                  {
                    do
                    {
                      *v76++ = 0;
                      --v77;
                    }
                    while ( v77 );
                  }
                  CspFreeH(*(_QWORD *)(a2 + 1160));
                }
                *(_QWORD *)(a2 + 1160) = 0;
                goto LABEL_36;
              }
              WppTraceIndent(0, 2);
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_36;
              }
              v17 = 130;
            }
          }
        }
LABEL_26:
        WPP_SF_sd(
          v16[2],
          v17,
          (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
          (_DWORD)WPP_pszIndent,
          Container);
        goto LABEL_36;
      }
    }
    else
    {
      if ( dword_18004C298 )
      {
        WppTraceIndent(v23, 2);
        v9 = 2148073513LL;
        Container = -2146893783;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v12 = 107;
          goto LABEL_10;
        }
        goto LABEL_36;
      }
      v35 = 0;
    }
    Container = KsppTranslateKeySpecToAlgorithm(*(unsigned int *)(a2 + 1040), pszAlgId);
    if ( Container )
    {
      WppTraceIndent(v36, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v17 = 108;
      goto LABEL_26;
    }
    Container = NCryptCreatePersistedKey(*(_QWORD *)(*a1 + 224LL), &hKey, pszAlgId[0], 0, 0, 0);
    if ( Container )
    {
      WppTraceIndent(v37, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v17 = 109;
      goto LABEL_26;
    }
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl);
    v39 = 0;
    if ( IsEnabled )
    {
      if ( *(_DWORD *)(a2 + 1052) )
      {
        v40 = NCryptSetProperty(hKey, L"Length", (PBYTE)(a2 + 1044), 4u, 0);
        v39 = 0;
        Container = v40;
        if ( v40 )
        {
          WppTraceIndent(v41, 2);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v17 = 110;
          goto LABEL_26;
        }
      }
      else if ( (unsigned int)IsPqcKey(*(unsigned int *)(a2 + 1040)) )
      {
        v43 = *(BYTE **)(a2 + 1208);
        if ( !v43 )
        {
          WppTraceIndent(v42, 2);
          v9 = 2148073483LL;
          Container = -2146893813;
          v11 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v12 = 111;
            goto LABEL_10;
          }
          goto LABEL_36;
        }
        v44 = -1;
        do
          ++v44;
        while ( *(_WORD *)&v43[2 * v44] != (_WORD)v39 );
        v45 = NCryptSetProperty(hKey, L"ParameterSetName", v43, 2 * v44 + 2, v39);
        v39 = 0;
        Container = v45;
        if ( v45 )
        {
          WppTraceIndent(v46, 2);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v17 = 112;
          goto LABEL_26;
        }
      }
    }
    else if ( *(_DWORD *)(a2 + 1052) )
    {
      v47 = NCryptSetProperty(hKey, L"Length", (PBYTE)(a2 + 1044), 4u, 0);
      v39 = 0;
      Container = v47;
      if ( v47 )
      {
        WppTraceIndent(v48, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v17 = 113;
        goto LABEL_26;
      }
    }
    Container = NCryptSetProperty(hKey, L"Export Policy", pbInput, 4u, v39);
    if ( Container )
    {
      WppTraceIndent(v49, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v17 = 114;
      goto LABEL_26;
    }
    if ( *(_QWORD *)(a2 + 1160) )
    {
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
      {
        if ( (unsigned int)IsPqcKey(*(unsigned int *)(a2 + 1040)) )
        {
          v51 = *(const WCHAR **)(a2 + 1176);
          if ( !(unsigned int)IsValidPqcPrivateBlobType(v50, v51) )
          {
            WppTraceIndent(0, 2);
            v9 = 2148073511LL;
            Container = -2146893785;
            v11 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v12 = 115;
              goto LABEL_10;
            }
            goto LABEL_36;
          }
          Container = NCryptSetProperty(hKey, v51, *(PBYTE *)(a2 + 1160), *(_DWORD *)(a2 + 1168), 0);
          if ( Container )
          {
            WppTraceIndent(v52, 2);
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_36;
            }
            v17 = 116;
            goto LABEL_26;
          }
        }
        else
        {
          v53 = *(_DWORD *)(a2 + 1168);
          v54 = *(BYTE **)(a2 + 1160);
          if ( (unsigned int)(v50 - 1) <= 1 )
          {
            Container = NCryptSetProperty(hKey, L"CAPIPRIVATEBLOB", v54, v53, 0);
            if ( Container )
            {
              WppTraceIndent(v56, 2);
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_36;
              }
              v17 = 117;
              goto LABEL_26;
            }
          }
          else
          {
            Container = NCryptSetProperty(hKey, L"ECCPRIVATEBLOB", v54, v53, 0);
            if ( Container )
            {
              WppTraceIndent(v55, 2);
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_36;
              }
              v17 = 118;
              goto LABEL_26;
            }
          }
        }
      }
      else
      {
        v57 = *(_DWORD *)(a2 + 1168);
        v58 = *(BYTE **)(a2 + 1160);
        if ( (unsigned int)(*(_DWORD *)(a2 + 1040) - 1) <= 1 )
        {
          Container = NCryptSetProperty(hKey, L"CAPIPRIVATEBLOB", v58, v57, 0);
          if ( Container )
          {
            WppTraceIndent(v60, 2);
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_36;
            }
            v17 = 119;
            goto LABEL_26;
          }
        }
        else
        {
          Container = NCryptSetProperty(hKey, L"ECCPRIVATEBLOB", v58, v57, 0);
          if ( Container )
          {
            WppTraceIndent(v59, 2);
            v16 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_36;
            }
            v17 = 120;
            goto LABEL_26;
          }
        }
      }
    }
    Container = NCryptFinalizeKey(hKey, 0);
    if ( Container )
    {
      WppTraceIndent(v61, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_36;
      }
      v17 = 121;
      goto LABEL_26;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
    {
      if ( *(_QWORD *)(a2 + 1160) && (unsigned int)IsPqcKey(*(unsigned int *)(a2 + 1040)) )
      {
        v63 = *(const WCHAR **)(a2 + 1176);
LABEL_191:
        Container = NCryptExportKey(hKey, 0, v63, 0, v62, (DWORD)v62, &cbOutput, (DWORD)v62);
        if ( Container )
        {
          WppTraceIndent(v68, 2);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v17 = 124;
          goto LABEL_26;
        }
        v69 = (BYTE *)MIDL_user_allocate(cbOutput);
        v7 = v69;
        if ( !v69 )
        {
          Container = -2146893810;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              125,
              &WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
              WPP_pszIndent);
          }
          goto LABEL_36;
        }
        Container = NCryptExportKey(hKey, 0, v63, 0, v69, cbOutput, &cbOutput, 0);
        if ( Container )
        {
          WppTraceIndent(0, 2);
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_36;
          }
          v17 = 126;
          goto LABEL_26;
        }
        *(_QWORD *)(a2 + 1144) = hKey;
        hKey = 0;
        goto LABEL_207;
      }
      v64 = KsppTranslateKeySpecToBlobType(*(unsigned int *)(a2 + 1040), &v83, 1);
      v62 = 0;
      Container = v64;
      if ( v64 )
      {
        WppTraceIndent(v65, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v17 = 122;
        goto LABEL_26;
      }
    }
    else
    {
      v66 = KsppTranslateKeySpecToBlobType(*(unsigned int *)(a2 + 1040), &v83, 1);
      v62 = 0;
      Container = v66;
      if ( v66 )
      {
        WppTraceIndent(v67, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_36;
        }
        v17 = 123;
        goto LABEL_26;
      }
    }
    v63 = v83;
    goto LABEL_191;
  }
  WppTraceIndent(v8, 2);
  v9 = 2148073511LL;
  Container = -2146893785;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v12 = 100;
    goto LABEL_10;
  }
LABEL_36:
  v24 = hKey;
  if ( hKey )
    NCryptDeleteKey(hKey, 0);
  if ( v7 )
    CspFreeH(v7);
  if ( Container && v6 )
    ContainerMapDeleteContainer(*(_QWORD *)(a2 + 1088), a2, v80);
  if ( v85 )
  {
    v85 = 0;
    KsppEndCardCall(a2 + 1072);
  }
  WppTraceIndent(v24, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      131,
      (unsigned int)&WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids,
      (_DWORD)WPP_pszIndent,
      Container);
  }
  v84 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v84);
  return Container;
}

```

## disassembly

```asm
0x180016adc  mov     [rsp-8+arg_18], rbx
0x180016ae1  push    rbp
0x180016ae2  push    rsi
0x180016ae3  push    rdi
0x180016ae4  push    r12
0x180016ae6  push    r13
0x180016ae8  push    r14
0x180016aea  push    r15
0x180016aec  lea     rbp, [rsp-10h]
0x180016af1  sub     rsp, 110h
0x180016af8  mov     rax, cs:__security_cookie
0x180016aff  xor     rax, rsp
0x180016b02  mov     [rbp+40h+var_38], rax
0x180016b06  xor     ebx, ebx
0x180016b08  mov     dword ptr [rsp+140h+pbInput], 3
0x180016b10  xor     eax, eax
0x180016b12  mov     [rsp+140h+pszAlgId], rbx
0x180016b17  mov     [rbp+40h+var_48], rax
0x180016b1b  mov     rdi, rdx
0x180016b1e  mov     [rbp+40h+var_40], eax
0x180016b21  xorps   xmm0, xmm0
0x180016b24  mov     [rbp+40h+var_50], eax
0x180016b27  xor     edx, edx
0x180016b29  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180016b30  mov     [rsp+140h+var_E8], rbx
0x180016b35  mov     [rsp+140h+var_E0], rax
0x180016b3a  mov     esi, r8d
0x180016b3d  mov     r14, rcx
0x180016b40  mov     [rsp+140h+hKey], rbx
0x180016b45  mov     r13d, ebx
0x180016b48  mov     [rsp+140h+cbOutput], ebx
0x180016b4c  movups  [rbp+40h+var_60], xmm0
0x180016b50  mov     r12d, ebx
0x180016b53  mov     [rsp+140h+var_F8], bl
0x180016b57  mov     [rsp+140h+var_D8], rbx
0x180016b5c  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b68  lea     r15, WPP_GLOBAL_Control
0x180016b6f  cmp     rcx, r15
0x180016b72  jz      short loc_180016B9A
0x180016b74  test    byte ptr [rcx+1Ch], 2
0x180016b78  jz      short loc_180016B9A
0x180016b7a  cmp     byte ptr [rcx+19h], 5
0x180016b7e  jb      short loc_180016B9A
0x180016b80  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180016b87  lea     edx, [rbx+62h]
0x180016b8a  mov     rcx, [rcx+10h]
0x180016b8e  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180016b95  call    WPP_SF_s
0x180016b9a  cmp     [rdi+418h], ebx
0x180016ba0  jz      short loc_180016BF3
0x180016ba2  mov     edx, 2
0x180016ba7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016bac  mov     r9d, 8009000Bh
0x180016bb2  mov     ebx, r9d
0x180016bb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bbc  cmp     rcx, r15
0x180016bbf  jz      loc_180016DA2
0x180016bc5  test    byte ptr [rcx+1Ch], 1
0x180016bc9  jz      loc_180016DA2
0x180016bcf  cmp     byte ptr [rcx+19h], 2
0x180016bd3  jb      loc_180016DA2
0x180016bd9  mov     edx, 63h ; 'c'
0x180016bde  mov     rcx, [rcx+10h]
0x180016be2  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180016be9  call    WPP_SF_d
0x180016bee  jmp     loc_180016DA2
0x180016bf3  cmp     bx, [rdi]
0x180016bf6  jnz     short loc_180016C36
0x180016bf8  mov     edx, 2
0x180016bfd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016c02  mov     r9d, 80090027h
0x180016c08  mov     ebx, r9d
0x180016c0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180016c12  cmp     rcx, r15
0x180016c15  jz      loc_180016DA2
0x180016c1b  test    byte ptr [rcx+1Ch], 1
0x180016c1f  jz      loc_180016DA2
0x180016c25  cmp     byte ptr [rcx+19h], 2
0x180016c29  jb      loc_180016DA2
0x180016c2f  mov     edx, 64h ; 'd'
0x180016c34  jmp     short loc_180016BDE
0x180016c36  lea     rbx, [rdi+208h]
0x180016c3d  xor     edx, edx
0x180016c3f  cmp     dx, [rbx]
0x180016c42  jnz     short loc_180016C54
0x180016c44  mov     rax, [r14+90h]
0x180016c4b  mov     ebx, edx
0x180016c4d  test    rax, rax
0x180016c50  cmovnz  rbx, rax
0x180016c54  lea     r15, [rdi+430h]
0x180016c5b  mov     rcx, [r15+10h]
0x180016c5f  test    rcx, rcx
0x180016c62  jz      short loc_180016C70
0x180016c64  call    CardStateReleaseRef
0x180016c69  mov     [rdi+440h], r12
0x180016c70  mov     eax, esi
0x180016c72  mov     r9, r15
0x180016c75  and     eax, 40h
0x180016c78  mov     r8, rbx
0x180016c7b  or      [rdi+428h], eax
0x180016c81  mov     rdx, rdi
0x180016c84  or      esi, [rdi+428h]
0x180016c8a  mov     rcx, r14
0x180016c8d  mov     rax, [rdi+450h]
0x180016c94  or      esi, 8
0x180016c97  mov     qword ptr [rsp+140h+dwFlags], rax
0x180016c9c  mov     [rsp+140h+dwLegacyKeySpec], esi
0x180016ca0  call    KsppCardConnect
0x180016ca5  mov     ebx, eax
0x180016ca7  test    eax, eax
0x180016ca9  jz      short loc_180016D05
0x180016cab  mov     edx, 2
0x180016cb0  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cbc  lea     r15, WPP_GLOBAL_Control
0x180016cc3  cmp     rcx, r15
0x180016cc6  jz      loc_180016DA2
0x180016ccc  test    byte ptr [rcx+1Ch], 1
0x180016cd0  jz      loc_180016DA2
0x180016cd6  cmp     byte ptr [rcx+19h], 2
0x180016cda  jb      loc_180016DA2
0x180016ce0  mov     edx, 65h ; 'e'
0x180016ce5  mov     [rsp+140h+dwLegacyKeySpec], ebx
0x180016ce9  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180016cf0  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180016cf7  mov     rcx, [rcx+10h]
0x180016cfb  call    WPP_SF_sd
0x180016d00  jmp     loc_180016DA2
0x180016d05  mov     rdx, [rdi+440h]
0x180016d0c  lea     rcx, [rsp+140h+var_E0]
0x180016d11  add     rdx, 270h
0x180016d18  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x180016d1d  mov     rcx, [rdi+440h]
0x180016d24  lea     rdx, [rbp+40h+var_48]
0x180016d28  call    CspQueryCapabilities
0x180016d2d  mov     ebx, eax
0x180016d2f  test    eax, eax
0x180016d31  jz      short loc_180016D63
0x180016d33  mov     edx, 2
0x180016d38  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180016d44  lea     r15, WPP_GLOBAL_Control
0x180016d4b  cmp     rcx, r15
0x180016d4e  jz      short loc_180016DA2
0x180016d50  test    byte ptr [rcx+1Ch], 1
0x180016d54  jz      short loc_180016DA2
0x180016d56  cmp     byte ptr [rcx+19h], 2
0x180016d5a  jb      short loc_180016DA2
0x180016d5c  mov     edx, 66h ; 'f'
0x180016d61  jmp     short loc_180016CE5
0x180016d63  mov     edx, [rdi+410h]
0x180016d69  lea     r9, [rbp+40h+var_60]
0x180016d6d  mov     rcx, [rdi+440h]
0x180016d74  mov     dword ptr [rbp+40h+var_60], 1
0x180016d7b  call    CspQueryKeySizes
0x180016d80  mov     ebx, eax
0x180016d82  cmp     eax, 80100004h
0x180016d87  jz      short loc_180016D96
0x180016d89  test    eax, eax
0x180016d8b  jz      loc_180016E7A
0x180016d91  cmp     eax, 57h ; 'W'
0x180016d94  jnz     short loc_180016D9B
0x180016d96  mov     ebx, 80090008h
0x180016d9b  lea     r15, WPP_GLOBAL_Control
0x180016da2  mov     rcx, [rsp+140h+hKey]; hKey
0x180016da7  test    rcx, rcx
0x180016daa  jz      short loc_180016DB4
0x180016dac  xor     edx, edx; dwFlags
0x180016dae  call    cs:__imp_NCryptDeleteKey
0x180016db4  test    r12, r12
0x180016db7  jz      short loc_180016DC1
0x180016db9  mov     rcx, r12
0x180016dbc  call    CspFreeH
0x180016dc1  xor     r12d, r12d
0x180016dc4  test    ebx, ebx
0x180016dc6  jz      short loc_180016DE1
0x180016dc8  test    r13d, r13d
0x180016dcb  jz      short loc_180016DE1
0x180016dcd  mov     rcx, [rdi+440h]
0x180016dd4  lea     r8, [rsp+140h+var_F8]
0x180016dd9  mov     rdx, rdi
0x180016ddc  call    ContainerMapDeleteContainer
0x180016de1  cmp     [rsp+140h+var_D8], r12
0x180016de6  jz      short loc_180016DF9
0x180016de8  lea     rcx, [rdi+430h]
0x180016def  mov     [rsp+140h+var_D8], r12
0x180016df4  call    KsppEndCardCall
0x180016df9  mov     edx, 1
0x180016dfe  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180016e0a  cmp     rcx, r15
0x180016e0d  jz      short loc_180016E3B
0x180016e0f  test    byte ptr [rcx+1Ch], 2
0x180016e13  jz      short loc_180016E3B
0x180016e15  cmp     byte ptr [rcx+19h], 5
0x180016e19  jb      short loc_180016E3B
0x180016e1b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180016e22  lea     r8, WPP_07049c9bf5c539752b8880ba2bd26898_Traceguids
0x180016e29  mov     rcx, [rcx+10h]
0x180016e2d  mov     edx, 83h
0x180016e32  mov     [rsp+140h+dwLegacyKeySpec], ebx
0x180016e36  call    WPP_SF_sd
0x180016e3b  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180016e42  lea     rcx, [rsp+140h+var_E0]
0x180016e47  mov     [rsp+140h+var_E0], rax
0x180016e4c  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180016e51  mov     eax, ebx
0x180016e53  mov     rcx, [rbp+40h+var_38]
0x180016e57  xor     rcx, rsp; StackCookie
0x180016e5a  call    __security_check_cookie
0x180016e5f  mov     rbx, [rsp+140h+arg_18]
0x180016e67  add     rsp, 110h
0x180016e6e  pop     r15
0x180016e70  pop     r14
0x180016e72  pop     r13
0x180016e74  pop     r12
0x180016e76  pop     rdi
0x180016e77  pop     rsi
0x180016e78  pop     rbp
0x180016e79  retn
0x180016e7a  xor     ebx, ebx
0x180016e7c  cmp     [rdi+41Ch], ebx
0x180016e82  jz      loc_180017008
0x180016e88  mov     r8d, [rbp+40h+var_50]
0x180016e8c  mov     r11d, dword ptr [rbp+40h+var_60+0Ch]
0x180016e90  mov     r9d, dword ptr [rbp+40h+var_60+4]
0x180016e94  cmp     [rdi+424h], ebx
0x180016e9a  jnz     short loc_180016EE9
0x180016e9c  lea     r10, [rdi+414h]
0x180016ea3  test    r10, r10
0x180016ea6  jz      loc_180016F56
0x180016eac  cmp     dword ptr [rbp+40h+var_60], 1
0x180016eb0  ja      loc_180016F56
0x180016eb6  cmp     r11d, [r10]
0x180016eb9  jb      short loc_180016EE3
0x180016ebb  mov     ecx, dword ptr [rbp+40h+var_60+8]
0x180016ebe  cmp     r9d, [r10]
0x180016ec1  ja      short loc_180016EE6
0x180016ec3  cmp     [r10], ecx
0x180016ec6  cmovnb  ecx, [r10]
0x180016eca  test    r8d, r8d
0x180016ecd  jz      short loc_180016EE6
0x180016ecf  xor     edx, edx
0x180016ed1  mov     eax, ecx
0x180016ed3  div     r8d
0x180016ed6  test    edx, edx
0x180016ed8  jz      short loc_180016EE6
0x180016eda  mov     eax, r8d
0x180016edd  sub     eax, edx
0x180016edf  add     ecx, eax
0x180016ee1  jmp     short loc_180016EE6
0x180016ee3  mov     ecx, r11d
0x180016ee6  mov     [r10], ecx
0x180016ee9  mov     eax, [rdi+414h]
0x180016eef  cmp     eax, r9d
0x180016ef2  jb      short loc_180016EFD
0x180016ef4  cmp     eax, r11d
0x180016ef7  jbe     loc_180016FA2
0x180016efd  mov     edx, 2
0x180016f02  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f0e  lea     rsi, WPP_GLOBAL_Control
0x180016f15  cmp     rcx, rsi
0x180016f18  jz      short loc_180016F4C
0x180016f1a  test    byte ptr [rcx+1Ch], 1
0x180016f1e  jz      short loc_180016F4C
0x180016f20  cmp     byte ptr [rcx+19h], 3
0x180016f24  jb      short loc_180016F4C
0x180016f26  mov     eax, [rdi+414h]
0x180016f2c  mov     edx, 68h ; 'h'
0x180016f31  mov     rcx, [rcx+10h]
0x180016f35  mov     dword ptr [rsp+140h+pcbResult], eax
0x180016f39  mov     eax, dword ptr [rbp+40h+var_60+0Ch]
0x180016f3c  mov     [rsp+140h+dwFlags], eax
0x180016f40  mov     eax, dword ptr [rbp+40h+var_60+4]
0x180016f43  mov     [rsp+140h+dwLegacyKeySpec], eax
0x180016f47  call    WPP_SF_sddd
0x180016f4c  mov     r8d, [rbp+40h+var_50]
0x180016f50  mov     r9d, dword ptr [rbp+40h+var_60+4]
0x180016f54  jmp     short loc_180016FA9
0x180016f56  mov     edx, 2
0x180016f5b  mov     ebx, 80100004h
0x180016f60  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180016f65  mov     rcx, cs:WPP_GLOBAL_Control
0x180016f6c  lea     r15, WPP_GLOBAL_Control
0x180016f73  cmp     rcx, r15
0x180016f76  jz      loc_180016DA2
0x180016f7c  test    byte ptr [rcx+1Ch], 1
0x180016f80  jz      loc_180016DA2
0x180016f86  cmp     byte ptr [rcx+19h], 2
0x180016f8a  jb      loc_180016DA2
0x180016f90  mov     edx, 67h ; 'g'
0x180016f95  mov     [rsp+140h+dwLegacyKeySpec], 80100004h
0x180016f9d  jmp     loc_180016CE9
0x180016fa2  lea     rsi, WPP_GLOBAL_Control
0x180016fa9  test    r8d, r8d
0x180016fac  jz      short loc_180017008
0x180016fae  mov     eax, [rdi+414h]
0x180016fb4  xor     edx, edx
  ... truncated ...
```
