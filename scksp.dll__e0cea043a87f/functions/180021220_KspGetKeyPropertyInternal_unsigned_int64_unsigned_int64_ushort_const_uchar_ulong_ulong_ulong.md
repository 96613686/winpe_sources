# KspGetKeyPropertyInternal(unsigned __int64,unsigned __int64,ushort const *,uchar *,ulong,ulong *,ulong)

- ea: `0x180021220`
- end: `0x1800229f5`
- name: `?KspGetKeyPropertyInternal@@YAJ_K0PEBGPEAEKPEAKK@Z`
- size: `6101`
- prototype: `__int64 __fastcall(__int64, __int64, const unsigned __int16 *, unsigned __int8 *, DWORD cbOutput, unsigned int *pcbResult, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002ae10`

## callees

- `0x18000a3c8`
- `0x18000a408`
- `0x18000d2a8`
- `0x180011fd8`
- `0x1800122b4`
- `0x1800135dc`
- `0x180013aac`
- `0x1800156c4`
- `0x1800182fc`
- `0x1800183ec`
- `0x180018968`
- `0x180019220`
- `0x180019808`
- `0x180019868`
- `0x18001b0c4`
- `0x180021220`
- `0x18002dd50`
- `0x18003af5c`
- `0x18003bd40`
- `0x18003be1c`
- `0x18003bebc`
- `0x18003c20e`
- `0x18003c240`

## import_xrefs

- `ncrypt!NCryptGetProperty` at `0x180021990`
- `ncrypt!NCryptGetProperty` at `0x1800228f8`
- `ncrypt!NCryptGetProperty` at `0x180021990`
- `ncrypt!NCryptGetProperty` at `0x1800228f8`

## string_xrefs

- `0x1800220d0`: `Security Descr`
- `0x1800220fb`: `SmartCardReader`
- `0x1800221d7`: `SmartCardReaderIcon`

## pseudocode

```c
__int64 __fastcall KspGetKeyPropertyInternal(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int8 *a4,
        DWORD cbOutput,
        unsigned int *pcbResult,
        DWORD dwFlags)
{
  PVOID v10; // rcx
  unsigned int Handle; // esi
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // rcx
  _QWORD *v16; // rcx
  int v17; // edx
  __int64 v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  char IsEnabled; // al
  __int64 v30; // r8
  LPCWSTR v31; // r14
  int v32; // edx
  __int64 v33; // rcx
  __int64 v34; // rcx
  unsigned int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rcx
  bool v38; // cc
  unsigned int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  LPCWSTR v45; // rdi
  __int64 v46; // rcx
  wchar_t *v47; // rcx
  __int64 v48; // rdx
  __int64 v49; // rcx
  int v50; // edx
  __int64 v51; // rcx
  __int64 v52; // rdx
  __int64 v53; // rcx
  WCHAR *v54; // rcx
  __int64 v55; // rcx
  void *v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  _WORD *v59; // rcx
  __int64 v60; // rdx
  __int64 v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 v66; // rdx
  __int64 v67; // rcx
  _WORD *v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 v73; // rcx
  __int64 PqcParamInfoByKeySpec; // rax
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // rcx
  __int64 v79; // rcx
  __int64 v80; // rcx
  __int64 v81; // rdx
  __int64 v82; // rcx
  __int64 v83; // rcx
  LPCWSTR lpValueName; // [rsp+30h] [rbp-61h] BYREF
  void *Src; // [rsp+38h] [rbp-59h] BYREF
  int v87; // [rsp+40h] [rbp-51h]
  unsigned int v88; // [rsp+44h] [rbp-4Dh]
  __int64 v89; // [rsp+48h] [rbp-49h] BYREF
  __int64 v90; // [rsp+50h] [rbp-41h] BYREF
  _QWORD v91[2]; // [rsp+58h] [rbp-39h] BYREF
  __int128 v92; // [rsp+68h] [rbp-29h] BYREF
  unsigned int v93; // [rsp+78h] [rbp-19h]

  v90 = 0;
  lpValueName = 0;
  v89 = 0;
  v92 = 0;
  v93 = 0;
  Src = 0;
  v91[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  v91[1] = 0;
  if ( !a3 || !pcbResult )
  {
    WppTraceIndent(a1, 2);
    v14 = 2148073511LL;
    Handle = -2146893785;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 129;
      goto LABEL_352;
    }
    goto LABEL_353;
  }
  if ( (dwFlags & 0xBFFFFFB0) != 0 )
  {
    WppTraceIndent(a1, 2);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        130,
        (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
        (_DWORD)WPP_pszIndent,
        dwFlags);
    }
    WppTraceIndent(v10, 2);
    Handle = -2146893815;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 131;
LABEL_12:
      v14 = Handle;
LABEL_352:
      WPP_SF_d(v12[2], v13, &WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids, v14);
      goto LABEL_353;
    }
    goto LABEL_353;
  }
  Handle = HtGetHandle(a1, 3, &v90);
  if ( Handle )
  {
    WppTraceIndent(v15, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 132;
    goto LABEL_18;
  }
  v18 = v90;
  Handle = KspEnterCriticalSection(v90 + 16);
  if ( Handle )
  {
    WppTraceIndent(v19, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 133;
    goto LABEL_18;
  }
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(v91, v18 + 16);
  Handle = HtGetHandle(a2, 2, &lpValueName);
  if ( Handle )
  {
    WppTraceIndent(v20, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 134;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"Algorithm Name", a3) )
  {
    Handle = KsppTranslateKeySpecToAlgorithm(*((unsigned int *)lpValueName + 260), &Src);
    if ( Handle )
    {
      WppTraceIndent(v21, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 135;
    }
    else
    {
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)Src + v22) );
      Handle = KsppCopyData(Src, (unsigned int)(2 * v22 + 2), a4, (__int64)pcbResult);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v23, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 136;
    }
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"Export Policy", a3) )
  {
    Handle = KsppCopyData((void *)(lpValueName + 592), 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v24, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 137;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"Key Usage", a3) )
  {
    Handle = KsppCopyData((void *)(lpValueName + 594), 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v25, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 138;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"Length", a3) )
  {
    Handle = KsppCopyData((void *)(lpValueName + 522), 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v26, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 139;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"HWND Handle", a3) )
  {
    Handle = KsppCopyData((void *)(lpValueName + 552), 8u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v27, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 140;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"SmartCardKeyCertificate", a3) )
  {
    Handle = KsppGetCertificate(lpValueName, a4, cbOutput, pcbResult);
    if ( Handle )
    {
      WppTraceIndent(v28, 2);
      v14 = 2148073489LL;
      Handle = -2146893807;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 141;
        goto LABEL_352;
      }
    }
    goto LABEL_353;
  }
  if ( !wcscmp_0(L"Lengths", a3) )
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl);
    v31 = lpValueName;
    v32 = 0;
    if ( IsEnabled && (unsigned int)IsPqcKey(*((unsigned int *)lpValueName + 260)) )
    {
      WppTraceIndent(v33, 2);
      v14 = 2148073513LL;
      Handle = -2146893783;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 142;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    if ( *((_DWORD *)v31 + 262) == v32 )
    {
      v38 = (unsigned int)(*((_DWORD *)v31 + 260) - 1) <= 1;
      v39 = *((_DWORD *)v31 + 261);
      v88 = v39;
      if ( v38 )
      {
        v87 = 512;
        Src = (void *)0x100000000400LL;
        Handle = KsppCopyData(&Src, 0x10u, a4, (__int64)pcbResult);
        if ( !Handle )
          goto LABEL_353;
        WppTraceIndent(v41, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_353;
        }
        v17 = 147;
      }
      else
      {
        v87 = v32;
        HIDWORD(Src) = v39;
        LODWORD(Src) = v39;
        Handle = KsppCopyData(&Src, 0x10u, a4, (__int64)pcbResult);
        if ( !Handle )
          goto LABEL_353;
        WppTraceIndent(v40, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_353;
        }
        v17 = 148;
      }
    }
    else if ( *((_DWORD *)v31 + 264) == v32 )
    {
      Handle = NCryptGetProperty(*((_QWORD *)v31 + 143), a3, a4, cbOutput, pcbResult, dwFlags);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v37, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 146;
    }
    else
    {
      LODWORD(v92) = 1;
      Handle = CspQueryKeySizes(*((_QWORD *)v31 + 136), *((unsigned int *)v31 + 260), v30, &v92);
      if ( Handle )
      {
        WppTraceIndent(v34, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_353;
        }
        v17 = 143;
      }
      else
      {
        if ( (unsigned int)v92 > 1 )
        {
          Handle = -2146435068;
          WppTraceIndent(v34, 2);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              144,
              (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
              (_DWORD)WPP_pszIndent,
              4);
          }
          goto LABEL_353;
        }
        v35 = *((_DWORD *)v31 + 261);
        if ( HIDWORD(v92) < v35 )
        {
          v35 = HIDWORD(v92);
        }
        else if ( DWORD1(v92) > v35 )
        {
          v35 = DWORD2(v92);
        }
        else
        {
          if ( v35 < DWORD2(v92) )
            v35 = DWORD2(v92);
          if ( v93 && v35 % v93 )
            v35 = v93 + v35 - v35 % v93;
        }
        v88 = v35;
        v87 = v93;
        Src = (void *)__PAIR64__(HIDWORD(v92), DWORD1(v92));
        Handle = KsppCopyData(&Src, 0x10u, a4, (__int64)pcbResult);
        if ( !Handle )
          goto LABEL_353;
        WppTraceIndent(v36, 2);
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_353;
        }
        v17 = 145;
      }
    }
LABEL_18:
    WPP_SF_sd(
      v16[2],
      v17,
      (unsigned int)&WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids,
      (_DWORD)WPP_pszIndent,
      Handle);
    goto LABEL_353;
  }
  if ( !wcscmp_0(L"Block Length", a3) )
  {
    if ( *((_DWORD *)lpValueName + 260) != 1 )
    {
      WppTraceIndent(v42, 2);
      v14 = 2148073511LL;
      Handle = -2146893785;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 149;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    LODWORD(lpValueName) = *((_DWORD *)lpValueName + 261) >> 3;
    Handle = KsppCopyData(&lpValueName, 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v43, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 150;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"Unique Name", a3) || !wcscmp_0(L"Name", a3) )
  {
    if ( !*((_DWORD *)lpValueName + 262) )
    {
      WppTraceIndent(lpValueName, 2);
      v14 = 2148073513LL;
      Handle = -2146893783;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 153;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    if ( *((_DWORD *)lpValueName + 264) )
    {
      v81 = -1;
      do
        ++v81;
      while ( lpValueName[v81] );
      Handle = KsppCopyData((void *)lpValueName, (unsigned int)(2 * v81 + 2), a4, (__int64)pcbResult);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v82, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 151;
    }
    else
    {
      Handle = NCryptGetProperty(*((_QWORD *)lpValueName + 143), a3, a4, cbOutput, pcbResult, dwFlags);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v83, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 152;
    }
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"UI Policy") )
  {
    Handle = KsppGetUIPolicy(lpValueName, a4, cbOutput, pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v44, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 154;
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"Algorithm Group") )
  {
    v45 = lpValueName;
    if ( *((_DWORD *)lpValueName + 260) == 1 || *((_DWORD *)lpValueName + 260) == 2 )
    {
      v47 = (wchar_t *)L"RSA";
    }
    else if ( *((_DWORD *)lpValueName + 260) == 3
           || *((_DWORD *)lpValueName + 260) == 4
           || *((_DWORD *)lpValueName + 260) == 5 )
    {
      v47 = L"ECDSA";
    }
    else if ( *((_DWORD *)lpValueName + 260) == 6 || (unsigned int)(*((_DWORD *)lpValueName + 260) - 7) < 2 )
    {
      v47 = L"ECDH";
    }
    else
    {
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
      {
        WppTraceIndent(v46, 2);
        v14 = 2148073511LL;
        Handle = -2146893785;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 156;
          goto LABEL_352;
        }
        goto LABEL_353;
      }
      if ( *((_DWORD *)v45 + 260) != 9 && *((_DWORD *)v45 + 260) != 10 && *((_DWORD *)v45 + 260) != 11 )
      {
        if ( *((_DWORD *)v45 + 260) == 12 || *((_DWORD *)v45 + 260) == 13 || *((_DWORD *)v45 + 260) == 14 )
        {
LABEL_161:
          v47 = L"MLKEM";
          goto LABEL_170;
        }
        if ( *((_DWORD *)v45 + 260) != 64 )
        {
          if ( *((_DWORD *)v45 + 260) != 65 )
          {
            WppTraceIndent((unsigned int)(*((_DWORD *)v45 + 260) - 64), 2);
            v14 = 2148073511LL;
            Handle = -2146893785;
            v12 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v13 = 155;
              goto LABEL_352;
            }
            goto LABEL_353;
          }
          goto LABEL_161;
        }
      }
      v47 = L"MLDSA";
    }
LABEL_170:
    v48 = -1;
    do
      ++v48;
    while ( v47[v48] );
    Handle = KsppCopyData(v47, (unsigned int)(2 * v48 + 2), a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v49, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 157;
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"SmartCardAssociatedECDHKey") )
  {
    v50 = *((_DWORD *)lpValueName + 260);
    if ( (unsigned int)(v50 - 6) <= 2 )
    {
      v52 = -1;
      do
        ++v52;
      while ( lpValueName[v52] );
      Handle = KsppCopyData((void *)lpValueName, (unsigned int)(2 * v52 + 2), a4, (__int64)pcbResult);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v53, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 158;
    }
    else
    {
      if ( (unsigned int)(v50 - 3) > 2 )
      {
        WppTraceIndent(lpValueName, 2);
        v14 = 2148073511LL;
        Handle = -2146893785;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v13 = 159;
          goto LABEL_352;
        }
        goto LABEL_353;
      }
      Handle = KsppGetAssociatedECDHKey(lpValueName);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v51, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 160;
    }
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"SmartCardPinId") )
  {
    v54 = (WCHAR *)(lpValueName + 564);
    if ( !*((_DWORD *)lpValueName + 282) )
    {
      WppTraceIndent(v54, 2);
      v14 = 2148073494LL;
      Handle = -2146893802;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 161;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    Handle = KsppCopyData(v54, 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v55, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 162;
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"SmartCardPinInfo") )
  {
    v56 = (void *)*((_QWORD *)lpValueName + 142);
    if ( !v56 )
    {
      WppTraceIndent(0, 2);
      v14 = 2148073494LL;
      Handle = -2146893802;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 163;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    Handle = KsppCopyData(v56, 0x24u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v57, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 164;
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"Modified", a3) || !wcscmp_0(L"Security Descr", a3) || !wcscmp_0(L"Use Count", a3) )
  {
    WppTraceIndent(v58, 2);
    v14 = 2148073513LL;
    Handle = -2146893783;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 165;
      goto LABEL_352;
    }
    goto LABEL_353;
  }
  if ( !wcscmp_0(a3, L"SmartCardReader") )
  {
    v59 = (_WORD *)*((_QWORD *)lpValueName + 136);
    if ( !v59 || (v59 += 16) == 0 )
    {
      WppTraceIndent(v59, 2);
      v14 = 2148073494LL;
      Handle = -2146893802;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 166;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    v60 = -1;
    do
      ++v60;
    while ( v59[v60] );
    Handle = KsppCopyData(v59, (unsigned int)(2 * v60 + 2), a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v61, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 167;
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"SmartCardReaderIcon") )
  {
    v62 = *((_QWORD *)lpValueName + 136);
    if ( !v62 || (v62 += 32) == 0 )
    {
      WppTraceIndent(v62, 2);
      v14 = 2148073494LL;
      Handle = -2146893802;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 168;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    Handle = KsppGetReaderImage(v62, a4, cbOutput, pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v63, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 169;
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"SmartCardNgcKeyName") )
  {
    v64 = *((_QWORD *)lpValueName + 136);
    if ( !v64 || v64 == -32 )
    {
      WppTraceIndent(lpValueName, 2);
      v14 = 2148073494LL;
      Handle = -2146893802;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 170;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    Handle = KsppGetNgcKeyName(lpValueName, a4, cbOutput, pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v65, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 171;
    goto LABEL_18;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_SmartCardKspPqcSupport>::GetImpl'::`2'::impl) )
  {
    Handle = KsppFindMiscProperty(lpValueName + 596, a3, &v89);
    if ( Handle )
    {
      WppTraceIndent(v79, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 182;
    }
    else
    {
      Handle = KsppCopyData(*(void **)(v89 + 128), *(unsigned int *)(v89 + 136), a4, (__int64)pcbResult);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v80, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 183;
    }
    goto LABEL_18;
  }
  if ( !wcscmp_0(L"ParameterSetName", a3) )
  {
    if ( !(unsigned int)IsPqcKey(*((unsigned int *)lpValueName + 260)) )
    {
      WppTraceIndent(v67, 2);
      v14 = 2148073511LL;
      Handle = -2146893785;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 172;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    v68 = *(_WORD **)(v66 + 1208);
    if ( !v68 )
    {
      WppTraceIndent(0, 2);
      v14 = 2148073489LL;
      Handle = -2146893807;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 173;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    v69 = -1;
    do
      ++v69;
    while ( v68[v69] );
    Handle = KsppCopyData(v68, (unsigned int)(2 * v69 + 2), a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v70, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 174;
    goto LABEL_18;
  }
  if ( !wcscmp_0(a3, L"KEMSharedSecretLength") )
  {
    if ( !(unsigned int)IsMlKemKey(*((unsigned int *)lpValueName + 260)) )
    {
      WppTraceIndent(v71, 2);
      v14 = 2148073511LL;
      Handle = -2146893785;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = 175;
        goto LABEL_352;
      }
      goto LABEL_353;
    }
    LODWORD(lpValueName) = 32;
    Handle = KsppCopyData(&lpValueName, 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v72, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 176;
    goto LABEL_18;
  }
  if ( wcscmp_0(a3, L"KEMCiphertextLength") )
  {
    Handle = KsppFindMiscProperty(lpValueName + 596, a3, &v89);
    if ( Handle )
    {
      WppTraceIndent(v77, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 180;
    }
    else
    {
      Handle = KsppCopyData(*(void **)(v89 + 128), *(unsigned int *)(v89 + 136), a4, (__int64)pcbResult);
      if ( !Handle )
        goto LABEL_353;
      WppTraceIndent(v78, 2);
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_353;
      }
      v17 = 181;
    }
    goto LABEL_18;
  }
  v73 = *((unsigned int *)lpValueName + 260);
  if ( (unsigned int)(v73 - 64) <= 1 || !(unsigned int)((__int64 (*)(void))IsMlKemKey)() )
  {
    WppTraceIndent(v73, 2);
    v14 = 2148073511LL;
    Handle = -2146893785;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = 177;
      goto LABEL_352;
    }
    goto LABEL_353;
  }
  PqcParamInfoByKeySpec = GetPqcParamInfoByKeySpec();
  if ( PqcParamInfoByKeySpec )
  {
    Handle = KsppCopyData((void *)(PqcParamInfoByKeySpec + 28), 4u, a4, (__int64)pcbResult);
    if ( !Handle )
      goto LABEL_353;
    WppTraceIndent(v76, 2);
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_353;
    }
    v17 = 179;
    goto LABEL_18;
  }
  WppTraceIndent(v75, 2);
  Handle = -2146893779;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v13 = 178;
    goto LABEL_12;
  }
LABEL_353:
  v91[0] = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(v91);
  return Handle;
}

```

## disassembly

```asm
0x180021220  push    rbp
0x180021222  push    rbx
0x180021223  push    rsi
0x180021224  push    rdi
0x180021225  push    r12
0x180021227  push    r13
0x180021229  push    r14
0x18002122b  push    r15
0x18002122d  lea     rbp, [rsp-7]
0x180021232  sub     rsp, 98h
0x180021239  mov     rax, cs:__security_cookie
0x180021240  xor     rax, rsp
0x180021243  mov     [rbp+3Fh+var_50], rax
0x180021247  mov     r12, r9
0x18002124a  mov     rdi, r8
0x18002124d  mov     r14, rdx
0x180021250  mov     r15, [rbp+3Fh+arg_28]
0x180021254  xor     ebx, ebx
0x180021256  mov     [rbp+3Fh+var_80], rbx
0x18002125a  mov     [rbp+3Fh+lpValueName], rbx
0x18002125e  mov     [rbp+3Fh+var_88], rbx
0x180021262  xorps   xmm0, xmm0
0x180021265  xor     eax, eax
0x180021267  movups  [rbp+3Fh+var_68], xmm0
0x18002126b  mov     [rbp+3Fh+var_58], eax
0x18002126e  mov     [rbp+3Fh+Src], rbx
0x180021272  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180021279  mov     [rbp+3Fh+var_78], rax
0x18002127d  mov     [rbp+3Fh+var_70], rbx
0x180021281  test    r8, r8
0x180021284  jz      loc_180022978
0x18002128a  test    r15, r15
0x18002128d  jz      loc_180022978
0x180021293  mov     r13d, [rbp+3Fh+arg_30]
0x180021297  test    r13d, 0BFFFFFB0h
0x18002129e  jz      loc_18002132B
0x1800212a4  mov     ebx, 2
0x1800212a9  mov     edx, ebx
0x1800212ab  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800212b0  lea     rdi, WPP_GLOBAL_Control
0x1800212b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800212be  cmp     rcx, rdi
0x1800212c1  jz      short loc_1800212EF
0x1800212c3  test    byte ptr [rcx+1Ch], 1
0x1800212c7  jz      short loc_1800212EF
0x1800212c9  cmp     [rcx+19h], bl
0x1800212cc  jb      short loc_1800212EF
0x1800212ce  mov     edx, 82h
0x1800212d3  mov     dword ptr [rsp+0D0h+pcbResult], r13d
0x1800212d8  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800212df  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x1800212e6  mov     rcx, [rcx+10h]
0x1800212ea  call    WPP_SF_sd
0x1800212ef  mov     edx, ebx
0x1800212f1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800212f6  mov     esi, 80090009h
0x1800212fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180021302  cmp     rcx, rdi
0x180021305  jz      loc_1800229BF
0x18002130b  test    byte ptr [rcx+1Ch], 1
0x18002130f  jz      loc_1800229BF
0x180021315  cmp     [rcx+19h], bl
0x180021318  jb      loc_1800229BF
0x18002131e  mov     edx, 83h
0x180021323  mov     r9d, esi
0x180021326  jmp     loc_1800229AE
0x18002132b  lea     r8, [rbp+3Fh+var_80]
0x18002132f  mov     edx, 3
0x180021334  call    HtGetHandle
0x180021339  mov     esi, eax
0x18002133b  test    eax, eax
0x18002133d  jz      short loc_18002139A
0x18002133f  mov     ebx, 2
0x180021344  mov     edx, ebx
0x180021346  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002134b  lea     rdi, WPP_GLOBAL_Control
0x180021352  mov     rcx, cs:WPP_GLOBAL_Control
0x180021359  cmp     rcx, rdi
0x18002135c  jz      loc_1800229BF
0x180021362  test    byte ptr [rcx+1Ch], 1
0x180021366  jz      loc_1800229BF
0x18002136c  cmp     [rcx+19h], bl
0x18002136f  jb      loc_1800229BF
0x180021375  mov     edx, 84h
0x18002137a  mov     dword ptr [rsp+0D0h+pcbResult], esi
0x18002137e  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180021385  lea     r8, WPP_0b747ea9e75c324d6ca3a604f9d495cb_Traceguids
0x18002138c  mov     rcx, [rcx+10h]
0x180021390  call    WPP_SF_sd
0x180021395  jmp     loc_1800229BF
0x18002139a  mov     rbx, [rbp+3Fh+var_80]
0x18002139e  lea     rcx, [rbx+10h]
0x1800213a2  call    KspEnterCriticalSection
0x1800213a7  mov     esi, eax
0x1800213a9  test    eax, eax
0x1800213ab  jz      short loc_1800213EA
0x1800213ad  mov     ebx, 2
0x1800213b2  mov     edx, ebx
0x1800213b4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800213b9  lea     rdi, WPP_GLOBAL_Control
0x1800213c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800213c7  cmp     rcx, rdi
0x1800213ca  jz      loc_1800229BF
0x1800213d0  test    byte ptr [rcx+1Ch], 1
0x1800213d4  jz      loc_1800229BF
0x1800213da  cmp     [rcx+19h], bl
0x1800213dd  jb      loc_1800229BF
0x1800213e3  mov     edx, 85h
0x1800213e8  jmp     short loc_18002137A
0x1800213ea  lea     rdx, [rbx+10h]
0x1800213ee  lea     rcx, [rbp+3Fh+var_78]
0x1800213f2  call    ?Attach@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Attach(_RTL_CRITICAL_SECTION *)
0x1800213f7  lea     r8, [rbp+3Fh+lpValueName]
0x1800213fb  mov     ebx, 2
0x180021400  mov     edx, ebx
0x180021402  mov     rcx, r14
0x180021405  call    HtGetHandle
0x18002140a  mov     esi, eax
0x18002140c  xor     r14d, r14d
0x18002140f  test    eax, eax
0x180021411  jz      short loc_18002144E
0x180021413  mov     edx, ebx
0x180021415  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002141a  lea     rdi, WPP_GLOBAL_Control
0x180021421  mov     rcx, cs:WPP_GLOBAL_Control
0x180021428  cmp     rcx, rdi
0x18002142b  jz      loc_1800229BF
0x180021431  test    byte ptr [rcx+1Ch], 1
0x180021435  jz      loc_1800229BF
0x18002143b  cmp     [rcx+19h], bl
0x18002143e  jb      loc_1800229BF
0x180021444  mov     edx, 86h
0x180021449  jmp     loc_18002137A
0x18002144e  mov     rdx, rdi; String2
0x180021451  lea     rcx, aAlgorithmName; "Algorithm Name"
0x180021458  call    wcscmp_0
0x18002145d  test    eax, eax
0x18002145f  jnz     loc_180021528
0x180021465  lea     rdx, [rbp+3Fh+Src]
0x180021469  mov     rcx, [rbp+3Fh+lpValueName]
0x18002146d  mov     ecx, [rcx+410h]
0x180021473  call    KsppTranslateKeySpecToAlgorithm
0x180021478  mov     esi, eax
0x18002147a  test    eax, eax
0x18002147c  jz      short loc_1800214B9
0x18002147e  mov     edx, ebx
0x180021480  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021485  lea     rdi, WPP_GLOBAL_Control
0x18002148c  mov     rcx, cs:WPP_GLOBAL_Control
0x180021493  cmp     rcx, rdi
0x180021496  jz      loc_1800229BF
0x18002149c  test    byte ptr [rcx+1Ch], 1
0x1800214a0  jz      loc_1800229BF
0x1800214a6  cmp     [rcx+19h], bl
0x1800214a9  jb      loc_1800229BF
0x1800214af  mov     edx, 87h
0x1800214b4  jmp     loc_18002137A
0x1800214b9  mov     rcx, [rbp+3Fh+Src]; Src
0x1800214bd  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800214c1  inc     rdx
0x1800214c4  cmp     [rcx+rdx*2], r14w
0x1800214c9  jnz     short loc_1800214C1
0x1800214cb  lea     edx, ds:2[rdx*2]; Size
0x1800214d2  mov     [rsp+0D0h+pcbResult], r15; __int64
0x1800214d7  mov     r9d, [rbp+3Fh+cbOutput]
0x1800214db  mov     r8, r12; void *
0x1800214de  call    KsppCopyData
0x1800214e3  mov     esi, eax
0x1800214e5  test    eax, eax
0x1800214e7  jz      loc_1800229BF
0x1800214ed  mov     edx, ebx
0x1800214ef  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800214f4  lea     rdi, WPP_GLOBAL_Control
0x1800214fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180021502  cmp     rcx, rdi
0x180021505  jz      loc_1800229BF
0x18002150b  test    byte ptr [rcx+1Ch], 1
0x18002150f  jz      loc_1800229BF
0x180021515  cmp     [rcx+19h], bl
0x180021518  jb      loc_1800229BF
0x18002151e  mov     edx, 88h
0x180021523  jmp     loc_18002137A
0x180021528  mov     rdx, rdi; String2
0x18002152b  lea     rcx, aExportPolicy; "Export Policy"
0x180021532  call    wcscmp_0
0x180021537  test    eax, eax
0x180021539  jnz     short loc_18002159F
0x18002153b  mov     rcx, [rbp+3Fh+lpValueName]
0x18002153f  add     rcx, 4A0h; Src
0x180021546  mov     [rsp+0D0h+pcbResult], r15; __int64
0x18002154b  mov     r9d, [rbp+3Fh+cbOutput]
0x18002154f  mov     r8, r12; void *
0x180021552  lea     edx, [rax+4]; Size
0x180021555  call    KsppCopyData
0x18002155a  mov     esi, eax
0x18002155c  test    eax, eax
0x18002155e  jz      loc_1800229BF
0x180021564  mov     edx, ebx
0x180021566  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18002156b  lea     rdi, WPP_GLOBAL_Control
0x180021572  mov     rcx, cs:WPP_GLOBAL_Control
0x180021579  cmp     rcx, rdi
0x18002157c  jz      loc_1800229BF
0x180021582  test    byte ptr [rcx+1Ch], 1
0x180021586  jz      loc_1800229BF
0x18002158c  cmp     [rcx+19h], bl
0x18002158f  jb      loc_1800229BF
0x180021595  mov     edx, 89h
0x18002159a  jmp     loc_18002137A
0x18002159f  mov     rdx, rdi; String2
0x1800215a2  lea     rcx, aKeyUsage; "Key Usage"
0x1800215a9  call    wcscmp_0
0x1800215ae  test    eax, eax
0x1800215b0  jnz     short loc_180021616
0x1800215b2  mov     rcx, [rbp+3Fh+lpValueName]
0x1800215b6  add     rcx, 4A4h; Src
0x1800215bd  mov     [rsp+0D0h+pcbResult], r15; __int64
0x1800215c2  mov     r9d, [rbp+3Fh+cbOutput]
0x1800215c6  mov     r8, r12; void *
0x1800215c9  lea     edx, [rax+4]; Size
0x1800215cc  call    KsppCopyData
0x1800215d1  mov     esi, eax
0x1800215d3  test    eax, eax
0x1800215d5  jz      loc_1800229BF
0x1800215db  mov     edx, ebx
0x1800215dd  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800215e2  lea     rdi, WPP_GLOBAL_Control
0x1800215e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800215f0  cmp     rcx, rdi
0x1800215f3  jz      loc_1800229BF
0x1800215f9  test    byte ptr [rcx+1Ch], 1
0x1800215fd  jz      loc_1800229BF
0x180021603  cmp     [rcx+19h], bl
0x180021606  jb      loc_1800229BF
0x18002160c  mov     edx, 8Ah
0x180021611  jmp     loc_18002137A
0x180021616  mov     rdx, rdi; String2
0x180021619  lea     rcx, aLength; "Length"
0x180021620  call    wcscmp_0
0x180021625  test    eax, eax
0x180021627  jnz     short loc_18002168D
0x180021629  mov     rcx, [rbp+3Fh+lpValueName]
0x18002162d  add     rcx, 414h; Src
0x180021634  mov     [rsp+0D0h+pcbResult], r15; __int64
0x180021639  mov     r9d, [rbp+3Fh+cbOutput]
0x18002163d  mov     r8, r12; void *
0x180021640  lea     edx, [rax+4]; Size
0x180021643  call    KsppCopyData
0x180021648  mov     esi, eax
0x18002164a  test    eax, eax
0x18002164c  jz      loc_1800229BF
0x180021652  mov     edx, ebx
0x180021654  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180021659  lea     rdi, WPP_GLOBAL_Control
0x180021660  mov     rcx, cs:WPP_GLOBAL_Control
0x180021667  cmp     rcx, rdi
0x18002166a  jz      loc_1800229BF
0x180021670  test    byte ptr [rcx+1Ch], 1
0x180021674  jz      loc_1800229BF
0x18002167a  cmp     [rcx+19h], bl
0x18002167d  jb      loc_1800229BF
0x180021683  mov     edx, 8Bh
0x180021688  jmp     loc_18002137A
0x18002168d  mov     rdx, rdi; String2
0x180021690  lea     rcx, aHwndHandle; "HWND Handle"
0x180021697  call    wcscmp_0
0x18002169c  test    eax, eax
0x18002169e  jnz     short loc_180021704
0x1800216a0  mov     rcx, [rbp+3Fh+lpValueName]
0x1800216a4  add     rcx, 450h; Src
0x1800216ab  mov     [rsp+0D0h+pcbResult], r15; __int64
0x1800216b0  mov     r9d, [rbp+3Fh+cbOutput]
0x1800216b4  mov     r8, r12; void *
0x1800216b7  lea     edx, [rax+8]; Size
0x1800216ba  call    KsppCopyData
0x1800216bf  mov     esi, eax
0x1800216c1  test    eax, eax
0x1800216c3  jz      loc_1800229BF
0x1800216c9  mov     edx, ebx
0x1800216cb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800216d0  lea     rdi, WPP_GLOBAL_Control
0x1800216d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800216de  cmp     rcx, rdi
0x1800216e1  jz      loc_1800229BF
0x1800216e7  test    byte ptr [rcx+1Ch], 1
0x1800216eb  jz      loc_1800229BF
0x1800216f1  cmp     [rcx+19h], bl
0x1800216f4  jb      loc_1800229BF
0x1800216fa  mov     edx, 8Ch
0x1800216ff  jmp     loc_18002137A
0x180021704  mov     rdx, rdi; String2
0x180021707  lea     rcx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18002170e  call    wcscmp_0
0x180021713  test    eax, eax
0x180021715  jnz     short loc_180021778
0x180021717  mov     r9, r15
0x18002171a  mov     r8d, [rbp+3Fh+cbOutput]
0x18002171e  mov     rdx, r12
0x180021721  mov     rcx, [rbp+3Fh+lpValueName]
0x180021725  call    KsppGetCertificate
  ... truncated ...
```
