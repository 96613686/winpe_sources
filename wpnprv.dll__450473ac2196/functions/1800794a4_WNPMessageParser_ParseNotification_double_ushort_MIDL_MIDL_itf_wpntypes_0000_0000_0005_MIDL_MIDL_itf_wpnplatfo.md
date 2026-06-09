# WNPMessageParser::ParseNotification(double *,ushort * *,__MIDL___MIDL_itf_wpntypes_0000_0000_0005 *,__MIDL___MIDL_itf_wpnplatform_0000_0007_0005 *,__MIDL___MIDL_itf_wpntypes_0000_0000_0007 *,double *,ushort * *,ushort * *,ushort * *,ulong *,int *,ushort * *,int *,ushort * *,ushort * *,ushort * *,ushort * *,ushort * *,uchar * *,uint *,__MIDL___MIDL_itf_wpntypes_0000_0000_0006 *,ushort * *)

- ea: `0x1800794a4`
- end: `0x18007b086`
- name: `?ParseNotification@WNPMessageParser@@QEAAJPEANPEAPEAGPEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@PEAW4__MIDL___MIDL_itf_wpnplatform_0000_0007_0005@@PEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0007@@0111PEAKPEAH1611111PEAPEAEPEAIPEAW4__MIDL___MIDL_itf_wpntypes_0000_0000_0006@@1@Z`
- size: `7138`
- prototype: `__int64 __fastcall(WNPMessageParser *this, double *, unsigned __int16 **, enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 *, enum __MIDL___MIDL_itf_wpnplatform_0000_0007_0005 *, enum __MIDL___MIDL_itf_wpntypes_0000_0000_0007 *, double *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned int *, int *, unsigned __int16 **, int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int8 **, unsigned int *, enum __MIDL___MIDL_itf_wpntypes_0000_0000_0006 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x180070d10`

## callees

- `0x18000a7b8`
- `0x18000aadc`
- `0x18000af1c`
- `0x18000fddc`
- `0x18000fe2c`
- `0x18000fe54`
- `0x18001ce24`
- `0x18006a718`
- `0x1800771ec`
- `0x180077820`
- `0x180077a3c`
- `0x180078164`
- `0x180078358`
- `0x1800794a4`
- `0x18007b08c`
- `0x18007b1bc`
- `0x18007b718`
- `0x18007ba48`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18007987a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180079937`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18007a2f5`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18007987a`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180079937`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x18007a2f5`

## string_xrefs

- `0x18007a441`: `Cached`

## pseudocode

```c
__int64 __fastcall WNPMessageParser::ParseNotification(
        WNPMessageParser *this,
        double *a2,
        unsigned __int16 **a3,
        enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005 *a4,
        enum __MIDL___MIDL_itf_wpnplatform_0000_0007_0005 *a5,
        enum __MIDL___MIDL_itf_wpntypes_0000_0000_0007 *a6,
        double *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9,
        unsigned __int16 **a10,
        unsigned int *a11,
        int *a12,
        unsigned __int16 **a13,
        int *a14,
        unsigned __int16 **a15,
        unsigned __int16 **a16,
        unsigned __int16 **a17,
        unsigned __int16 **a18,
        unsigned __int16 **a19,
        unsigned __int8 **a20,
        unsigned int *a21,
        enum __MIDL___MIDL_itf_wpntypes_0000_0000_0006 *a22,
        unsigned __int16 **a23)
{
  unsigned __int16 *v27; // r13
  int *v28; // r12
  char IsEnabled; // al
  enum __MIDL___MIDL_itf_wpntypes_0000_0000_0006 *v30; // rsi
  unsigned int DateHeader; // ebx
  PVOID *v32; // rcx
  __int64 v33; // rdx
  unsigned __int16 *v34; // rdi
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 v37; // r8
  __int64 v38; // r9
  WNPMessageParser *v39; // rcx
  unsigned __int16 *v40; // rbx
  unsigned __int16 *v41; // rbx
  unsigned __int16 *v42; // rbx
  unsigned __int16 *v43; // rsi
  unsigned __int16 *v44; // r14
  unsigned __int16 *v45; // r12
  __int64 v46; // r9
  int v47; // ecx
  WNPMessageParser *v48; // rcx
  int v49; // eax
  _QWORD *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // r9
  unsigned __int16 *v53; // rbx
  unsigned __int16 *v54; // rbx
  unsigned __int16 *v55; // rbx
  __int64 v56; // r8
  __int64 v57; // r9
  const char *v58; // rdx
  int BundleHeader; // eax
  unsigned __int16 *v60; // rax
  unsigned __int16 *v61; // rax
  unsigned __int16 *v62; // rax
  unsigned __int16 *v63; // rax
  unsigned __int16 *v64; // rax
  int v66; // [rsp+20h] [rbp-B1h]
  int v67; // [rsp+20h] [rbp-B1h]
  LPCCH lpMultiByteStr; // [rsp+40h] [rbp-91h] BYREF
  bool v69; // [rsp+48h] [rbp-89h] BYREF
  unsigned __int16 *v70; // [rsp+50h] [rbp-81h] BYREF
  unsigned __int16 *v71; // [rsp+58h] [rbp-79h] BYREF
  unsigned __int16 *v72[4]; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int16 *v73; // [rsp+80h] [rbp-51h]
  unsigned __int16 *v74; // [rsp+88h] [rbp-49h] BYREF
  unsigned __int16 *v75; // [rsp+90h] [rbp-41h] BYREF
  unsigned __int16 *v76; // [rsp+98h] [rbp-39h] BYREF
  unsigned __int16 *v77; // [rsp+A0h] [rbp-31h] BYREF
  unsigned __int16 *v78; // [rsp+A8h] [rbp-29h] BYREF
  unsigned __int16 *v79; // [rsp+B0h] [rbp-21h] BYREF
  unsigned __int16 *v80; // [rsp+B8h] [rbp-19h] BYREF
  unsigned __int16 *v81; // [rsp+C0h] [rbp-11h] BYREF
  unsigned __int16 *v82; // [rsp+C8h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_21a3201469733e5c8660b272590c09d0_Traceguids);
  }
  lpMultiByteStr = 0;
  v81 = 0;
  v72[0] = 0;
  v71 = 0;
  v70 = 0;
  v80 = 0;
  v79 = 0;
  v73 = 0;
  v78 = 0;
  v82 = 0;
  v77 = 0;
  v76 = 0;
  v75 = 0;
  v27 = 0;
  v74 = 0;
  v69 = 0;
  *a11 = 0;
  *a12 = 0;
  v28 = a14;
  *a14 = 0;
  *a3 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *a13 = 0;
  *a15 = 0;
  *a16 = 0;
  *a17 = 0;
  *a18 = 0;
  *a19 = 0;
  *a20 = 0;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID60125902>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID60125902>::GetImpl'::`2'::impl);
  v30 = a22;
  if ( IsEnabled )
  {
    *(_DWORD *)a22 = 1;
    *a23 = 0;
  }
  DateHeader = WNPMessageParser::ScanHeaders(this);
  if ( (DateHeader & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)DateHeader,
      v66);
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v33 = 40;
LABEL_376:
        v46 = DateHeader;
        goto LABEL_377;
      }
      goto LABEL_379;
    }
    goto LABEL_383;
  }
  DateHeader = WNPMessageParser::GetDateHeader(this, "Time", 0, a2);
  v34 = 0;
  if ( (DateHeader & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)DateHeader,
      v66);
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v33 = 42;
        goto LABEL_376;
      }
LABEL_379:
      if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 2) != 0 && *((_BYTE *)v32 + 25) >= 6u )
        WPP_SF_d(v32[2], 136, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
      goto LABEL_383;
    }
    goto LABEL_383;
  }
  DateHeader = WNPMessageParser::GetDateHeader(this, "TTL", 1, a7);
  if ( (DateHeader & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
    }
    if ( DateHeader != -2147024637 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x145,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)DateHeader,
        v66);
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_383;
      if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_379;
      v33 = 44;
      goto LABEL_376;
    }
    DateHeader = WNPMessageParser::GetDateHeader(this, "Expiry", 0, a7);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
      }
      if ( DateHeader != -2147024637 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          goto LABEL_383;
        if ( *((char *)WPP_GLOBAL_Control + 28) >= 0 )
          goto LABEL_379;
        v33 = 46;
        goto LABEL_376;
      }
    }
  }
  DateHeader = WNPMessageParser::GetStringHeader(this, "Method", &lpMultiByteStr);
  if ( (DateHeader & 0x80000000) == 0 )
  {
    if ( (unsigned int)_o__stricmp("PUT", lpMultiByteStr, v35, v36) )
    {
      if ( (unsigned int)_o__stricmp("DEL", lpMultiByteStr, v37, v38) )
      {
        DateHeader = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            2147549183LL);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)0x8000FFFFLL,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 50;
            v46 = 2147549183LL;
LABEL_377:
            WPP_SF_d(v32[2], v33, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v46);
LABEL_378:
            v32 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_379;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v40 = v70;
      if ( v70 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a14);
        MemoryFree(v40);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a14);
      }
      v70 = 0;
      v41 = v72[0];
      if ( v72[0] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a14);
        MemoryFree(v41);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a14);
      }
      v72[0] = 0;
      v42 = v71;
      if ( v71 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a14);
        MemoryFree(v42);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a14);
      }
      v71 = 0;
      DateHeader = WNPMessageParser::GetMatchHeader(this, "Match", a4, &v71, v72, &v70, &v69);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x15D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 48;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      *(_DWORD *)a6 = 2 - v69;
      v43 = 0;
      v44 = 0;
      v45 = 0;
      goto LABEL_81;
    }
    *(_DWORD *)a6 = 0;
LABEL_44:
    DateHeader = WNPMessageParser::GetStringHeader(this, "Type", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)DateHeader,
        v66);
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v33 = 56;
          goto LABEL_376;
        }
        goto LABEL_379;
      }
      goto LABEL_383;
    }
    DateHeader = WNPMessageParser::ParseNotificationType(v39, lpMultiByteStr, a4);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)DateHeader,
        v66);
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v33 = 58;
          goto LABEL_376;
        }
        goto LABEL_379;
      }
      goto LABEL_383;
    }
    v47 = 2;
    if ( *(_DWORD *)a4 != 4 )
      v47 = 0;
    *(_DWORD *)a5 = v47;
    v44 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID60125902>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID60125902>::GetImpl'::`2'::impl) )
      goto LABEL_122;
    DateHeader = WNPMessageParser::GetStringHeader(this, "SubType", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B9,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 67;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v50 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v51 = 64;
        v52 = 2147942659LL;
        goto LABEL_111;
      }
    }
    else
    {
      v49 = WNPMessageParser::ParseNotificationSubType(v48, lpMultiByteStr, v30);
      if ( v49 < 0 )
      {
        v50 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v51 = 63;
          v52 = (unsigned int)v49;
LABEL_111:
          WPP_SF_d(v50[2], v51, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, v52);
        }
      }
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "SubTypeMetadata", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1CF,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 73;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
      }
    }
    else
    {
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v74);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1C2,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 69;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v27 = v74;
    }
LABEL_122:
    DateHeader = WNPMessageParser::GetStringHeader(this, "Tag", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1E7,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 79;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
      }
    }
    else
    {
      v53 = v72[0];
      if ( v72[0] )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a14);
        MemoryFree(v53);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a14);
      }
      v72[0] = 0;
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, v72);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1DA,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 75;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "Group", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1FE,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 85;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
      }
    }
    else
    {
      v54 = v71;
      if ( v71 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a14);
        MemoryFree(v54);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a14);
      }
      v71 = 0;
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v71);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1F1,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 81;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "CollectionId", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x215,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 91;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 88, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
      }
    }
    else
    {
      v55 = v70;
      if ( v70 )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&a14);
        MemoryFree(v55);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&a14);
      }
      v70 = 0;
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v70);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 86, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x208,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 87;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "SuppressPopup", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x22D,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 95;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
      }
    }
    else if ( !(unsigned int)_o__stricmp("true", lpMultiByteStr, v56, v57) )
    {
      *v28 = 1;
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "Priority", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            100,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x244,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 101;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 98, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
      }
      v34 = 0;
    }
    else
    {
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v76);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x237,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 97;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v34 = v76;
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "Cached", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x25B,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 107;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          104,
          WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
          2147942659LL);
      }
      v43 = 0;
    }
    else
    {
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v75);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x24E,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 103;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v43 = v75;
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "Encryption", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x272,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 113;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          110,
          WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
          2147942659LL);
      }
    }
    else
    {
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v79);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            108,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x265,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 109;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v44 = v79;
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "Crypto-Key", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            118,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x289,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 119;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          116,
          WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
          2147942659LL);
      }
      v45 = v73;
    }
    else
    {
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v78);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            114,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x27C,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 115;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v45 = v78;
    }
    DateHeader = WNPMessageParser::GetStringHeader(this, "Content-Encoding", &lpMultiByteStr);
    if ( (DateHeader & 0x80000000) != 0 )
    {
      if ( DateHeader != -2147024637 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            124,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2A0,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 125;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          122,
          WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
          2147942659LL);
      }
    }
    else
    {
      DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v77);
      if ( (DateHeader & 0x80000000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            120,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            DateHeader);
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
          (const char *)DateHeader,
          v66);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v33 = 121;
            goto LABEL_376;
          }
          goto LABEL_379;
        }
        goto LABEL_383;
      }
      v82 = v77;
    }
    goto LABEL_81;
  }
  if ( DateHeader != -2147024637 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x17B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)DateHeader,
      v66);
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v33 = 54;
        goto LABEL_376;
      }
      goto LABEL_379;
    }
    goto LABEL_383;
  }
  *(_DWORD *)a6 = 0;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_44;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    goto LABEL_44;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    goto LABEL_44;
  WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, 2147942659LL);
  if ( !*(_DWORD *)a6 )
    goto LABEL_44;
  v34 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
LABEL_81:
  DateHeader = WNPMessageParser::GetStringHeader(this, "Channel", &lpMultiByteStr);
  if ( (DateHeader & 0x80000000) == 0 )
  {
    DateHeader = WpnUtf8ToUtf16(lpMultiByteStr, &v81);
    if ( (DateHeader & 0x80000000) == 0 )
    {
      BundleHeader = WNPMessageParser::GetBundleHeader(this, v58, a11, a12, &v80);
      DateHeader = BundleHeader;
      if ( BundleHeader < 0 )
      {
        if ( BundleHeader != -2147024637 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              132,
              WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
              (unsigned int)BundleHeader);
          }
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x2BB,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
            (const char *)DateHeader,
            v67);
          v32 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v33 = 133;
              goto LABEL_376;
            }
            goto LABEL_379;
          }
          goto LABEL_383;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            130,
            WPP_21a3201469733e5c8660b272590c09d0_Traceguids,
            2147942659LL);
        }
      }
      DateHeader = WNPMessageParser::GetPayload(this, a20, a21);
      if ( (DateHeader & 0x80000000) == 0 )
      {
        v60 = v81;
        v81 = 0;
        *a3 = v60;
        v61 = v72[0];
        v72[0] = 0;
        *a8 = v61;
        v62 = v71;
        v71 = 0;
        *a9 = v62;
        v63 = v70;
        v70 = 0;
        *a10 = v63;
        v64 = v80;
        v80 = 0;
        *a13 = v64;
        v76 = 0;
        *a15 = v34;
        v75 = 0;
        *a16 = v43;
        v79 = 0;
        *a17 = v44;
        v78 = 0;
        *a18 = v45;
        v77 = 0;
        *a19 = v82;
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID60125902>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID60125902>::GetImpl'::`2'::impl) )
        {
          v74 = 0;
          *a23 = v27;
        }
        goto LABEL_378;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C2,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)DateHeader,
        v67);
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v33 = 135;
          goto LABEL_376;
        }
        goto LABEL_379;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2AC,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
        (const char *)DateHeader,
        v66);
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
        {
          v33 = 129;
          goto LABEL_376;
        }
        goto LABEL_379;
      }
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_21a3201469733e5c8660b272590c09d0_Traceguids, DateHeader);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2A8,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\wnp\\wnpmessageparser.cpp",
      (const char *)DateHeader,
      v66);
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v33 = 127;
        goto LABEL_376;
      }
      goto LABEL_379;
    }
  }
LABEL_383:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v74);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v75);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v76);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v77);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v78);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v79);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v80);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v70);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v71);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v72);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v81);
  return DateHeader;
}

```

## disassembly

```asm
0x1800794a4  mov     [rsp-8+arg_10], r8
0x1800794a9  push    rbp
0x1800794aa  push    rbx
0x1800794ab  push    rsi
0x1800794ac  push    rdi
0x1800794ad  push    r12
0x1800794af  push    r13
0x1800794b1  push    r14
0x1800794b3  push    r15
0x1800794b5  lea     rbp, [rsp-7]
0x1800794ba  sub     rsp, 0D8h
0x1800794c1  mov     r14, r9
0x1800794c4  mov     rbx, r8
0x1800794c7  mov     rdi, rdx
0x1800794ca  mov     r15, rcx
0x1800794cd  lea     rax, WPP_GLOBAL_Control
0x1800794d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800794db  cmp     rcx, rax
0x1800794de  jz      short loc_180079501
0x1800794e0  test    byte ptr [rcx+1Ch], 2
0x1800794e4  jz      short loc_180079501
0x1800794e6  cmp     byte ptr [rcx+19h], 6
0x1800794ea  jb      short loc_180079501
0x1800794ec  mov     edx, 26h ; '&'
0x1800794f1  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800794f8  mov     rcx, [rcx+10h]
0x1800794fc  call    WPP_SF_
0x180079501  xor     ecx, ecx
0x180079503  mov     [rsp+110h+lpMultiByteStr], rcx
0x180079508  mov     [rbp+3Fh+var_50], rcx
0x18007950c  mov     [rbp+3Fh+var_B0], rcx
0x180079510  mov     [rbp+3Fh+var_B8], rcx
0x180079514  mov     [rsp+110h+var_C0], rcx
0x180079519  mov     [rbp+3Fh+var_58], rcx
0x18007951d  mov     [rbp+3Fh+var_60], rcx
0x180079521  mov     [rbp+3Fh+var_90], rcx
0x180079525  mov     [rbp+3Fh+var_68], rcx
0x180079529  mov     [rbp+3Fh+var_48], rcx
0x18007952d  mov     [rbp+3Fh+var_70], rcx
0x180079531  mov     [rbp+3Fh+var_78], rcx
0x180079535  mov     [rbp+3Fh+var_80], rcx
0x180079539  mov     r13d, ecx
0x18007953c  mov     [rbp+3Fh+var_88], rcx
0x180079540  mov     [rsp+110h+var_C8], cl
0x180079544  mov     rax, [rbp+3Fh+arg_50]
0x18007954b  mov     [rax], ecx
0x18007954d  mov     rax, [rbp+3Fh+arg_58]
0x180079554  mov     [rax], ecx
0x180079556  mov     r12, [rbp+3Fh+arg_68]
0x18007955d  mov     [r12], ecx
0x180079561  mov     [rbx], rcx
0x180079564  mov     rax, [rbp+3Fh+arg_38]
0x18007956b  mov     [rax], rcx
0x18007956e  mov     rax, [rbp+3Fh+arg_40]
0x180079575  mov     [rax], rcx
0x180079578  mov     rax, [rbp+3Fh+arg_48]
0x18007957f  mov     [rax], rcx
0x180079582  mov     rax, [rbp+3Fh+arg_60]
0x180079589  mov     [rax], rcx
0x18007958c  mov     rax, [rbp+3Fh+arg_70]
0x180079593  mov     [rax], rcx
0x180079596  mov     rax, [rbp+3Fh+arg_78]
0x18007959d  mov     [rax], rcx
0x1800795a0  mov     rax, [rbp+3Fh+arg_80]
0x1800795a7  mov     [rax], rcx
0x1800795aa  mov     rax, [rbp+3Fh+arg_88]
0x1800795b1  mov     [rax], rcx
0x1800795b4  mov     rax, [rbp+3Fh+arg_90]
0x1800795bb  mov     [rax], rcx
0x1800795be  mov     rax, [rbp+3Fh+arg_98]
0x1800795c5  mov     [rax], rcx
0x1800795c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID60125902@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID60125902@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID60125902> `wil::Feature<__WilFeatureTraits_Feature_ID60125902>::GetImpl(void)'::`2'::impl
0x1800795cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID60125902@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID60125902>::__private_IsEnabled(void)
0x1800795d4  mov     rsi, [rbp+3Fh+arg_A8]
0x1800795db  test    al, al
0x1800795dd  jz      short loc_1800795EF
0x1800795df  mov     dword ptr [rsi], 1
0x1800795e5  mov     rax, [rbp+3Fh+arg_B0]
0x1800795ec  mov     [rax], r13
0x1800795ef  mov     rcx, r15; this
0x1800795f2  call    ?ScanHeaders@WNPMessageParser@@AEAAJXZ; WNPMessageParser::ScanHeaders(void)
0x1800795f7  mov     ebx, eax
0x1800795f9  test    eax, eax
0x1800795fb  jns     short loc_180079677
0x1800795fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180079604  lea     rax, WPP_GLOBAL_Control
0x18007960b  cmp     rcx, rax
0x18007960e  jz      short loc_180079634
0x180079610  test    byte ptr [rcx+1Ch], 2
0x180079614  jz      short loc_180079634
0x180079616  cmp     byte ptr [rcx+19h], 2
0x18007961a  jb      short loc_180079634
0x18007961c  mov     edx, 27h ; '''
0x180079621  mov     r9d, ebx
0x180079624  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x18007962b  mov     rcx, [rcx+10h]
0x18007962f  call    WPP_SF_d
0x180079634  mov     rcx, [rbp+47h]; this
0x180079638  mov     r9d, ebx; char *
0x18007963b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180079642  mov     edx, 138h; void *
0x180079647  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007964c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079653  lea     rdi, WPP_GLOBAL_Control
0x18007965a  cmp     rcx, rdi
0x18007965d  jz      loc_18007B00C
0x180079663  test    byte ptr [rcx+1Ch], 80h
0x180079667  jz      loc_18007AFE3
0x18007966d  mov     edx, 28h ; '('
0x180079672  jmp     loc_18007AFC9
0x180079677  mov     r9, rdi; double *
0x18007967a  xor     r8d, r8d; bool
0x18007967d  lea     rdx, aTime; "Time"
0x180079684  mov     rcx, r15; this
0x180079687  call    ?GetDateHeader@WNPMessageParser@@AEAAJPEBD_NPEAN@Z; WNPMessageParser::GetDateHeader(char const *,bool,double *)
0x18007968c  mov     ebx, eax
0x18007968e  xor     edi, edi
0x180079690  test    eax, eax
0x180079692  jns     short loc_18007970C
0x180079694  mov     rcx, cs:WPP_GLOBAL_Control
0x18007969b  lea     rax, WPP_GLOBAL_Control
0x1800796a2  cmp     rcx, rax
0x1800796a5  jz      short loc_1800796C9
0x1800796a7  test    byte ptr [rcx+1Ch], 2
0x1800796ab  jz      short loc_1800796C9
0x1800796ad  cmp     byte ptr [rcx+19h], 2
0x1800796b1  jb      short loc_1800796C9
0x1800796b3  lea     edx, [rdi+29h]
0x1800796b6  mov     r9d, ebx
0x1800796b9  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800796c0  mov     rcx, [rcx+10h]
0x1800796c4  call    WPP_SF_d
0x1800796c9  mov     rcx, [rbp+47h]; this
0x1800796cd  mov     r9d, ebx; char *
0x1800796d0  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800796d7  mov     edx, 13Ch; void *
0x1800796dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800796e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800796e8  lea     rdi, WPP_GLOBAL_Control
0x1800796ef  cmp     rcx, rdi
0x1800796f2  jz      loc_18007B00C
0x1800796f8  test    byte ptr [rcx+1Ch], 80h
0x1800796fc  jz      loc_18007AFE3
0x180079702  mov     edx, 2Ah ; '*'
0x180079707  jmp     loc_18007AFC9
0x18007970c  mov     r9, [rbp+3Fh+arg_30]; double *
0x180079710  mov     r8b, 1; bool
0x180079713  lea     rdx, aTtl; "TTL"
0x18007971a  mov     rcx, r15; this
0x18007971d  call    ?GetDateHeader@WNPMessageParser@@AEAAJPEBD_NPEAN@Z; WNPMessageParser::GetDateHeader(char const *,bool,double *)
0x180079722  mov     ebx, eax
0x180079724  test    eax, eax
0x180079726  jns     loc_180079850
0x18007972c  mov     rcx, cs:WPP_GLOBAL_Control
0x180079733  lea     rax, WPP_GLOBAL_Control
0x18007973a  cmp     rcx, rax
0x18007973d  jz      short loc_180079763
0x18007973f  test    byte ptr [rcx+1Ch], 2
0x180079743  jz      short loc_180079763
0x180079745  cmp     byte ptr [rcx+19h], 2
0x180079749  jb      short loc_180079763
0x18007974b  mov     edx, 2Bh ; '+'
0x180079750  mov     r9d, ebx
0x180079753  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x18007975a  mov     rcx, [rcx+10h]
0x18007975e  call    WPP_SF_d
0x180079763  cmp     ebx, 80070103h
0x180079769  jz      short loc_1800797AE
0x18007976b  mov     rcx, [rbp+47h]; this
0x18007976f  mov     r9d, ebx; char *
0x180079772  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180079779  mov     edx, 145h; void *
0x18007977e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079783  mov     rcx, cs:WPP_GLOBAL_Control
0x18007978a  lea     rdi, WPP_GLOBAL_Control
0x180079791  cmp     rcx, rdi
0x180079794  jz      loc_18007B00C
0x18007979a  test    byte ptr [rcx+1Ch], 80h
0x18007979e  jz      loc_18007AFE3
0x1800797a4  mov     edx, 2Ch ; ','
0x1800797a9  jmp     loc_18007AFC9
0x1800797ae  mov     r9, [rbp+3Fh+arg_30]; double *
0x1800797b2  xor     r8d, r8d; bool
0x1800797b5  lea     rdx, aExpiry; "Expiry"
0x1800797bc  mov     rcx, r15; this
0x1800797bf  call    ?GetDateHeader@WNPMessageParser@@AEAAJPEBD_NPEAN@Z; WNPMessageParser::GetDateHeader(char const *,bool,double *)
0x1800797c4  mov     ebx, eax
0x1800797c6  test    eax, eax
0x1800797c8  jns     loc_180079850
0x1800797ce  mov     rcx, cs:WPP_GLOBAL_Control
0x1800797d5  lea     rax, WPP_GLOBAL_Control
0x1800797dc  cmp     rcx, rax
0x1800797df  jz      short loc_180079805
0x1800797e1  test    byte ptr [rcx+1Ch], 2
0x1800797e5  jz      short loc_180079805
0x1800797e7  cmp     byte ptr [rcx+19h], 2
0x1800797eb  jb      short loc_180079805
0x1800797ed  mov     edx, 2Dh ; '-'
0x1800797f2  mov     r9d, ebx
0x1800797f5  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800797fc  mov     rcx, [rcx+10h]
0x180079800  call    WPP_SF_d
0x180079805  cmp     ebx, 80070103h
0x18007980b  jz      short loc_180079850
0x18007980d  mov     rcx, [rbp+47h]; this
0x180079811  mov     r9d, ebx; char *
0x180079814  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18007981b  mov     edx, 14Dh; void *
0x180079820  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079825  mov     rcx, cs:WPP_GLOBAL_Control
0x18007982c  lea     rdi, WPP_GLOBAL_Control
0x180079833  cmp     rcx, rdi
0x180079836  jz      loc_18007B00C
0x18007983c  test    byte ptr [rcx+1Ch], 80h
0x180079840  jz      loc_18007AFE3
0x180079846  mov     edx, 2Eh ; '.'
0x18007984b  jmp     loc_18007AFC9
0x180079850  lea     r8, [rsp+110h+lpMultiByteStr]; char **
0x180079855  lea     rdx, aMethod; "Method"
0x18007985c  mov     rcx, r15; this
0x18007985f  call    ?GetStringHeader@WNPMessageParser@@AEAAJPEBDPEAPEBD@Z; WNPMessageParser::GetStringHeader(char const *,char const * *)
0x180079864  mov     ebx, eax
0x180079866  test    eax, eax
0x180079868  js      loc_180079B25
0x18007986e  mov     rdx, [rsp+110h+lpMultiByteStr]
0x180079873  lea     rcx, aPut; "PUT"
0x18007987a  call    cs:__imp__o__stricmp
0x180079880  test    eax, eax
0x180079882  jnz     loc_18007992B
0x180079888  mov     rax, [rbp+3Fh+arg_28]
0x18007988c  mov     [rax], edi
0x18007988e  mov     edi, 2
0x180079893  lea     r8, [rsp+110h+lpMultiByteStr]; char **
0x180079898  lea     rdx, aType_0; "Type"
0x18007989f  mov     rcx, r15; this
0x1800798a2  call    ?GetStringHeader@WNPMessageParser@@AEAAJPEBDPEAPEBD@Z; WNPMessageParser::GetStringHeader(char const *,char const * *)
0x1800798a7  mov     ebx, eax
0x1800798a9  test    eax, eax
0x1800798ab  jns     loc_180079C2D
0x1800798b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800798b8  lea     rax, WPP_GLOBAL_Control
0x1800798bf  cmp     rcx, rax
0x1800798c2  jz      short loc_1800798E8
0x1800798c4  test    [rcx+1Ch], dil
0x1800798c8  jz      short loc_1800798E8
0x1800798ca  cmp     [rcx+19h], dil
0x1800798ce  jb      short loc_1800798E8
0x1800798d0  mov     edx, 37h ; '7'
0x1800798d5  mov     r9d, ebx
0x1800798d8  lea     r8, WPP_21a3201469733e5c8660b272590c09d0_Traceguids
0x1800798df  mov     rcx, [rcx+10h]
0x1800798e3  call    WPP_SF_d
0x1800798e8  mov     rcx, [rbp+47h]; this
0x1800798ec  mov     r9d, ebx; char *
0x1800798ef  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800798f6  mov     edx, 185h; void *
0x1800798fb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180079900  mov     rcx, cs:WPP_GLOBAL_Control
0x180079907  lea     rdi, WPP_GLOBAL_Control
0x18007990e  cmp     rcx, rdi
0x180079911  jz      loc_18007B00C
0x180079917  test    byte ptr [rcx+1Ch], 80h
0x18007991b  jz      loc_18007AFE3
0x180079921  mov     edx, 38h ; '8'
0x180079926  jmp     loc_18007AFC9
0x18007992b  mov     rdx, [rsp+110h+lpMultiByteStr]
0x180079930  lea     rcx, aDel; "DEL"
0x180079937  call    cs:__imp__o__stricmp
0x18007993d  test    eax, eax
0x18007993f  jnz     loc_180079AA0
0x180079945  mov     rbx, [rsp+110h+var_C0]
0x18007994a  test    rbx, rbx
0x18007994d  jz      short loc_18007996F
0x18007994f  lea     rcx, [rbp+3Fh+arg_68]; this
0x180079956  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18007995b  mov     rcx, rbx; void *
0x18007995e  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180079963  lea     rcx, [rbp+3Fh+arg_68]; this
0x18007996a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007996f  mov     [rsp+110h+var_C0], rdi
0x180079974  mov     rbx, [rbp+3Fh+var_B0]
0x180079978  test    rbx, rbx
0x18007997b  jz      short loc_18007999D
0x18007997d  lea     rcx, [rbp+3Fh+arg_68]; this
0x180079984  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180079989  mov     rcx, rbx; void *
0x18007998c  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x180079991  lea     rcx, [rbp+3Fh+arg_68]; this
0x180079998  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18007999d  mov     [rbp+3Fh+var_B0], rdi
0x1800799a1  mov     rbx, [rbp+3Fh+var_B8]
0x1800799a5  test    rbx, rbx
0x1800799a8  jz      short loc_1800799CA
0x1800799aa  lea     rcx, [rbp+3Fh+arg_68]; this
0x1800799b1  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800799b6  mov     rcx, rbx; void *
0x1800799b9  call    ?MemoryFree@@YAXPEAX@Z; MemoryFree(void *)
0x1800799be  lea     rcx, [rbp+3Fh+arg_68]; this
0x1800799c5  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800799ca  mov     [rbp+3Fh+var_B8], rdi
  ... truncated ...
```
