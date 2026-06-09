# CWbemNamespace::UniversalConnect(CWbemNamespace *,IWbemContext *,ushort const *,ushort const *,ushort const *,_IWmiCallSec *,_IWmiUserHandle *,ulong,ulong,ulong,ulong,int,int,ushort const *,ushort const *,ulong,unsigned __int64,_GUID const &,void * *)

- ea: `0x18002e7f8`
- end: `0x18002f011`
- name: `?UniversalConnect@CWbemNamespace@@SAJPEAV1@PEAUIWbemContext@@PEBG22PEAU_IWmiCallSec@@PEAU_IWmiUserHandle@@KKKKHH22K_KAEBU_GUID@@PEAPEAX@Z`
- size: `2073`
- prototype: `static int(struct CWbemNamespace *, struct IWbemContext *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct _IWmiCallSec *, struct _IWmiUserHandle *, unsigned int, unsigned int, unsigned int, unsigned int, int, int, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002dda4`
- `0x18002f020`

## callees

- `0x18000b140`
- `0x18000e950`
- `0x18000fa74`
- `0x18001cce0`
- `0x18001d390`
- `0x18002a998`
- `0x18002dd24`
- `0x18002e7f8`
- `0x180036db0`
- `0x18005fc7c`
- `0x1800604f8`
- `0x18007daf4`
- `0x1800903d0`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?ms_XXX_Locale_To_LCID@CMUILocale@@SAJPEBGPEAK@Z` at `0x18002e97e`
- `wbemcomn!?ms_XXX_Locale_To_LCID@CMUILocale@@SAJPEBGPEAK@Z` at `0x18002e97e`
- `wbemcomn!?CheckLangNeutral@CMUILocale@@SAJPEBGPEA_N@Z` at `0x18002ea01`
- `wbemcomn!?CheckLangNeutral@CMUILocale@@SAJPEBGPEA_N@Z` at `0x18002ea01`
- `wbemcomn!?LocaleName_To_LCID@CMUILocale@@SAJPEBGPEA_NPEAK@Z` at `0x18002ea77`
- `wbemcomn!?LocaleName_To_LCID@CMUILocale@@SAJPEBGPEA_NPEAK@Z` at `0x18002ea77`
- `wbemcomn!?LCID_To_ms_XXX_Format@CMUILocale@@SAJKPEAG_K@Z` at `0x18002ead7`
- `wbemcomn!?LCID_To_ms_XXX_Format@CMUILocale@@SAJKPEAG_K@Z` at `0x18002ead7`
- `wbemcomn!?Publish@CPublishWMIOperationEvent@@SAJPEAGKK0000K_K0H@Z` at `0x18002eeb2`
- `wbemcomn!?Publish@CPublishWMIOperationEvent@@SAJPEAGKK0000K_K0H@Z` at `0x18002eeb2`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ebaa`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18002ebaa`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002ecbf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002ecd3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002efd8`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002ecbf`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002ecd3`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18002efd8`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002e9e6`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002e9e6`
- `wbemcomn!GetMemLogObject` at `0x18002e8c5`
- `wbemcomn!GetMemLogObject` at `0x18002e98a`
- `wbemcomn!GetMemLogObject` at `0x18002ea0e`
- `wbemcomn!GetMemLogObject` at `0x18002ea84`
- `wbemcomn!GetMemLogObject` at `0x18002eae3`
- `wbemcomn!GetMemLogObject` at `0x18002eb3f`
- `wbemcomn!GetMemLogObject` at `0x18002ebbc`
- `wbemcomn!GetMemLogObject` at `0x18002ec25`
- `wbemcomn!GetMemLogObject` at `0x18002ec74`
- `wbemcomn!GetMemLogObject` at `0x18002ecef`
- `wbemcomn!GetMemLogObject` at `0x18002edd5`
- `wbemcomn!GetMemLogObject` at `0x18002ef2a`
- `wbemcomn!GetMemLogObject` at `0x18002e8c5`
- `wbemcomn!GetMemLogObject` at `0x18002e98a`
- `wbemcomn!GetMemLogObject` at `0x18002ea0e`
- `wbemcomn!GetMemLogObject` at `0x18002ea84`
- `wbemcomn!GetMemLogObject` at `0x18002eae3`
- `wbemcomn!GetMemLogObject` at `0x18002eb3f`
- `wbemcomn!GetMemLogObject` at `0x18002ebbc`
- `wbemcomn!GetMemLogObject` at `0x18002ec25`
- `wbemcomn!GetMemLogObject` at `0x18002ec74`
- `wbemcomn!GetMemLogObject` at `0x18002ecef`
- `wbemcomn!GetMemLogObject` at `0x18002edd5`
- `wbemcomn!GetMemLogObject` at `0x18002ef2a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e8d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e995`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ea1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ea90`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eaee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eb4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ebcc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ec30`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ec7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ecff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ede1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ef35`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e8d5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e995`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ea1a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ea90`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eaee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002eb4a`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ebcc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ec30`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ec7f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ecff`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ede1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002ef35`
- `OLEAUT32!__imp_VariantInit` at `0x18002ee29`
- `OLEAUT32!__imp_VariantInit` at `0x18002ee29`

## string_xrefs

- `0x18002eea2`: `IWbemServices::Connect`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CWbemNamespace::UniversalConnect(
        struct CWbemNamespace *a1,
        struct IWbemContext *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _IWmiCallSec *a6,
        struct _IWmiUserHandle *a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned int a11,
        int a12,
        int a13,
        unsigned __int16 *String2,
        unsigned __int16 *a15,
        int a16,
        unsigned __int64 a17,
        const struct _GUID *a18,
        void **a19)
{
  unsigned __int16 *v19; // rdi
  unsigned int v20; // r15d
  CMemoryLog *MemLogObject; // rax
  int v22; // edi
  const unsigned __int16 *v24; // r14
  unsigned __int16 v25; // ax
  unsigned __int16 *v26; // rcx
  int v27; // esi
  CMemoryLog *v28; // rax
  CClientCnt *v29; // rcx
  __int64 v30; // rdx
  unsigned __int16 *v31; // rsi
  int v32; // r15d
  CMemoryLog *v33; // rax
  CClientCnt *v34; // rcx
  __int64 v35; // rdx
  CMemoryLog *v36; // rax
  CMemoryLog *v37; // rax
  CMemoryLog *v38; // rax
  __int64 v39; // r14
  unsigned __int16 *v40; // rax
  CMemoryLog *v41; // rax
  CClientCnt *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  struct CWbemNamespace *Instance; // r14
  CMemoryLog *v48; // rax
  unsigned int v49; // r12d
  int v50; // r15d
  CMemoryLog *v51; // rax
  unsigned __int16 *bstrVal; // r15
  CMemoryLog *v53; // rax
  int v54[2]; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v55; // [rsp+40h] [rbp-C0h]
  int v56; // [rsp+58h] [rbp-A8h]
  bool v57; // [rsp+70h] [rbp-90h] BYREF
  bool v58; // [rsp+71h] [rbp-8Fh] BYREF
  unsigned int v59; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v60; // [rsp+78h] [rbp-88h]
  int IsLocalMachine; // [rsp+7Ch] [rbp-84h]
  unsigned __int16 *v62; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v63; // [rsp+88h] [rbp-78h]
  unsigned __int16 *v64; // [rsp+90h] [rbp-70h]
  unsigned __int64 v65; // [rsp+98h] [rbp-68h] BYREF
  struct IWbemContext *v66; // [rsp+A0h] [rbp-60h]
  void **v67; // [rsp+A8h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v69[264]; // [rsp+D0h] [rbp-30h] BYREF

  v19 = a3;
  v66 = a2;
  v62 = a5;
  v64 = String2;
  v63 = a15;
  v67 = a19;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), a16, (_DWORD)a3, (_DWORD)a3, (__int64)a5, (__int64)String2, a16);
  }
  IsLocalMachine = CWbemNamespace::IsLocalMachine(String2);
  v20 = (a8 >> 6) & 1;
  v60 = v20;
  if ( !v19 )
  {
    MemLogObject = GetMemLogObject();
    v22 = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 499, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    return (unsigned int)v22;
  }
  if ( *(_QWORD *)&a18->Data1 != *(_QWORD *)&IID_IWbemServices.Data1
    || *(_QWORD *)a18->Data4 != *(_QWORD *)IID_IWbemServices.Data4 )
  {
    return 2147500034LL;
  }
  v24 = v19;
  v25 = *v19;
  if ( *v19 )
  {
    v26 = v19;
    do
    {
      if ( v25 == 92 && v26[1] )
        v24 = v26 + 1;
      v25 = *++v26;
    }
    while ( *v26 );
  }
  v59 = 0;
  v27 = CMUILocale::ms_XXX_Locale_To_LCID(v24, &v59);
  if ( v27 < 0 )
  {
    v28 = GetMemLogObject();
    CMemoryLog::Write(v28, v27);
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return (unsigned int)v27;
    }
    v30 = 500;
LABEL_24:
    WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v27);
    return (unsigned int)v27;
  }
  v31 = 0;
  if ( !v59 && !(unsigned __int8)CWbemInstallObject::IsOffline() )
  {
    v57 = 0;
    v32 = CMUILocale::CheckLangNeutral(v24, &v57);
    if ( v32 < 0 )
    {
      v33 = GetMemLogObject();
      CMemoryLog::Write(v33, v32);
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        return (unsigned int)v32;
      }
      v35 = 501;
LABEL_33:
      WPP_SF_d(*((_QWORD *)v34 + 2), v35, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v32);
      return (unsigned int)v32;
    }
    if ( !v57 )
    {
      v58 = 0;
      v32 = CMUILocale::LocaleName_To_LCID(v24, &v58, &v59);
      if ( v32 < 0 )
      {
        v36 = GetMemLogObject();
        CMemoryLog::Write(v36, v32);
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v32;
        }
        v35 = 502;
        goto LABEL_33;
      }
    }
    if ( (v59 & 0x3FF) != 0 )
    {
      v27 = CMUILocale::LCID_To_ms_XXX_Format(v59, v69, 0x104u);
      if ( v27 < 0 )
      {
        v37 = GetMemLogObject();
        CMemoryLog::Write(v37, v27);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v27;
        }
        v30 = 503;
        goto LABEL_24;
      }
      v27 = StringCchLengthW(v19, 0x7FFFFFFFu, &v65);
      if ( v27 < 0 )
      {
        v38 = GetMemLogObject();
        CMemoryLog::Write(v38, v27);
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return (unsigned int)v27;
        }
        v30 = 504;
        goto LABEL_24;
      }
      v39 = v24 - v19;
      v19[v39] = 0;
      v40 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v39 + 260, 2u));
      v31 = v40;
      v65 = (unsigned __int64)v40;
      if ( !v40 )
      {
        v41 = GetMemLogObject();
        v22 = -2147217402;
        CMemoryLog::Write(v41, -2147217402);
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_71;
        }
        v43 = 505;
        v44 = 2147749894LL;
LABEL_70:
        WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v44);
LABEL_71:
        CWin32DefaultArena::WbemMemFree(v31);
        return (unsigned int)v22;
      }
      if ( v39 )
      {
        v22 = StringCchCopyW(v40, v39 + 260, v19);
        if ( v22 < 0 )
        {
          v45 = GetMemLogObject();
          CMemoryLog::Write(v45, v22);
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_71;
          }
          v43 = 506;
          goto LABEL_69;
        }
      }
      else
      {
        *v40 = 0;
      }
      v22 = StringCchCatW(v31, v39 + 260, v69);
      if ( v22 < 0 )
      {
        v46 = GetMemLogObject();
        CMemoryLog::Write(v46, v22);
        v42 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_71;
        }
        v43 = 507;
LABEL_69:
        v44 = (unsigned int)v22;
        goto LABEL_70;
      }
      v65 = 0;
      v19 = v31;
      CWin32DefaultArena::WbemMemFree(0);
    }
    v20 = v60;
  }
  v65 = (unsigned __int64)v31;
  Instance = CWbemNamespace::CreateInstance();
  if ( !Instance )
  {
    v48 = GetMemLogObject();
    v22 = -2147217402;
    CMemoryLog::Write(v48, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 508, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    goto LABEL_71;
  }
  v49 = _InterlockedIncrement((volatile signed __int32 *)&g_WMIOperation_Id);
  v50 = CWbemNamespace::Initialize(Instance, v19, v62, a10, a11, a12, v20, v64, v63, a16, a17, v56, 0, v49);
  if ( v50 < 0 )
  {
    CWbemNamespace::Release(Instance);
    v51 = GetMemLogObject();
    CMemoryLog::Write(v51, v50);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        509,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v50);
    }
    v22 = v50;
    goto LABEL_71;
  }
  VariantInit(&pvarg);
  bstrVal = 0;
  if ( v66
    && ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))v66->lpVtbl->GetValue)(
         v66,
         L"__CorrelationId",
         0,
         &pvarg) >= 0
    && pvarg.vt == 8 )
  {
    bstrVal = pvarg.bstrVal;
  }
  CPublishWMIOperationEvent::Publish(
    bstrVal,
    v49,
    v49,
    L"IWbemServices::Connect",
    v64,
    v63,
    v62,
    a16,
    a17,
    v19,
    IsLocalMachine);
  if ( g_cntWinmgmtTraceLogging && v49 )
  {
    LODWORD(v55) = IsLocalMachine;
    v54[0] = a16;
    WinmgmtTelemetrylogging(v49, 11, bstrVal, v64, v63, v62, *(_QWORD *)v54, a17, v55, v19);
  }
  v22 = CWbemNamespace::CloneClientCtx(Instance, v66);
  if ( v22 < 0 )
  {
    CWbemNamespace::Release(Instance);
    v53 = GetMemLogObject();
    CMemoryLog::Write(v53, v22);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        510,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v22);
    }
    _variant_t::~_variant_t(&pvarg);
    goto LABEL_71;
  }
  *((_DWORD *)Instance + 30) = (a8 >> 8) & 1;
  *v67 = Instance;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 511, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 0);
  }
  _variant_t::~_variant_t(&pvarg);
  CWin32DefaultArena::WbemMemFree(v31);
  return 0;
}

```

## disassembly

```asm
0x18002e7f8  mov     [rsp-8+arg_0], rbx
0x18002e7fd  push    rbp
0x18002e7fe  push    rsi
0x18002e7ff  push    rdi
0x18002e800  push    r12
0x18002e802  push    r13
0x18002e804  push    r14
0x18002e806  push    r15
0x18002e808  lea     rbp, [rsp-1F0h]
0x18002e810  sub     rsp, 2F0h
0x18002e817  mov     rax, cs:__security_cookie
0x18002e81e  xor     rax, rsp
0x18002e821  mov     [rbp+220h+var_40], rax
0x18002e828  mov     rdi, r8
0x18002e82b  mov     [rbp+220h+var_280], rdx
0x18002e82f  mov     rax, [rbp+220h+arg_20]
0x18002e836  mov     [rbp+220h+var_2A0], rax
0x18002e83a  mov     rbx, [rbp+220h+String2]
0x18002e841  mov     [rbp+220h+var_290], rbx
0x18002e845  mov     rcx, [rbp+220h+arg_70]
0x18002e84c  mov     [rbp+220h+var_298], rcx
0x18002e850  mov     rcx, [rbp+220h+arg_90]
0x18002e857  mov     [rbp+220h+var_278], rcx
0x18002e85b  lea     rsi, WPP_GLOBAL_Control
0x18002e862  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e869  cmp     rcx, rsi
0x18002e86c  jz      short loc_18002E89A
0x18002e86e  test    byte ptr [rcx+1Ch], 1
0x18002e872  jz      short loc_18002E89A
0x18002e874  cmp     byte ptr [rcx+19h], 5
0x18002e878  jb      short loc_18002E89A
0x18002e87a  mov     edx, [rbp+220h+arg_78]
0x18002e880  mov     [rsp+320h+var_2F0], edx
0x18002e884  mov     qword ptr [rsp+320h+var_2F8], rbx
0x18002e889  mov     qword ptr [rsp+320h+var_300], rax
0x18002e88e  mov     r9, r8
0x18002e891  mov     rcx, [rcx+10h]
0x18002e895  call    WPP_SF_SSSd
0x18002e89a  mov     rcx, rbx; String2
0x18002e89d  call    ?IsLocalMachine@CWbemNamespace@@KAHPEBG@Z; CWbemNamespace::IsLocalMachine(ushort const *)
0x18002e8a2  mov     [rsp+320h+var_2A4], eax
0x18002e8a6  mov     r13d, [rbp+220h+arg_38]
0x18002e8ad  mov     r15d, r13d
0x18002e8b0  shr     r15d, 6
0x18002e8b4  and     r15d, 1
0x18002e8b8  mov     [rsp+320h+var_2A8], r15d
0x18002e8bd  xor     r12d, r12d
0x18002e8c0  test    rdi, rdi
0x18002e8c3  jnz     short loc_18002E919
0x18002e8c5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e8cb  mov     edi, 80041008h
0x18002e8d0  mov     edx, edi
0x18002e8d2  mov     rcx, rax
0x18002e8d5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e8db  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e8e2  cmp     rcx, rsi
0x18002e8e5  jz      short loc_18002E912
0x18002e8e7  test    byte ptr [rcx+1Ch], 1
0x18002e8eb  jz      short loc_18002E912
0x18002e8ed  lea     ebx, [r12+2]
0x18002e8f2  cmp     [rcx+19h], bl
0x18002e8f5  jb      short loc_18002E912
0x18002e8f7  mov     edx, 1F3h
0x18002e8fc  mov     r9d, 80041008h
0x18002e902  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002e909  mov     rcx, [rcx+10h]
0x18002e90d  call    WPP_SF_d
0x18002e912  mov     eax, edi
0x18002e914  jmp     loc_18002EFE7
0x18002e919  mov     rcx, [rbp+220h+arg_88]
0x18002e920  mov     rax, [rcx]
0x18002e923  cmp     rax, qword ptr cs:IID_IWbemServices.Data1
0x18002e92a  jnz     loc_18002EFE2
0x18002e930  mov     rax, [rcx+8]
0x18002e934  cmp     rax, qword ptr cs:IID_IWbemServices.Data4
0x18002e93b  jnz     loc_18002EFE2
0x18002e941  mov     r14, rdi
0x18002e944  movzx   eax, word ptr [rdi]
0x18002e947  mov     ebx, 2
0x18002e94c  test    ax, ax
0x18002e94f  jz      short loc_18002E971
0x18002e951  mov     rcx, rdi
0x18002e954  cmp     ax, 5Ch ; '\'
0x18002e958  jnz     short loc_18002E966
0x18002e95a  lea     rax, [rcx+2]
0x18002e95e  cmp     [rax], r12w
0x18002e962  cmovnz  r14, rax
0x18002e966  add     rcx, rbx
0x18002e969  movzx   eax, word ptr [rcx]
0x18002e96c  test    ax, ax
0x18002e96f  jnz     short loc_18002E954
0x18002e971  mov     [rsp+320h+var_2AC], r12d
0x18002e976  lea     rdx, [rsp+320h+var_2AC]
0x18002e97b  mov     rcx, r14
0x18002e97e  call    cs:__imp_?ms_XXX_Locale_To_LCID@CMUILocale@@SAJPEBGPEAK@Z; CMUILocale::ms_XXX_Locale_To_LCID(ushort const *,ulong *)
0x18002e984  mov     esi, eax
0x18002e986  test    eax, eax
0x18002e988  jns     short loc_18002E9D8
0x18002e98a  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e990  mov     edx, esi
0x18002e992  mov     rcx, rax
0x18002e995  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e99b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e9a2  lea     rax, WPP_GLOBAL_Control
0x18002e9a9  cmp     rcx, rax
0x18002e9ac  jz      short loc_18002E9D1
0x18002e9ae  test    byte ptr [rcx+1Ch], 1
0x18002e9b2  jz      short loc_18002E9D1
0x18002e9b4  cmp     [rcx+19h], bl
0x18002e9b7  jb      short loc_18002E9D1
0x18002e9b9  mov     edx, 1F4h
0x18002e9be  mov     r9d, esi
0x18002e9c1  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002e9c8  mov     rcx, [rcx+10h]
0x18002e9cc  call    WPP_SF_d
0x18002e9d1  mov     eax, esi
0x18002e9d3  jmp     loc_18002EFE7
0x18002e9d8  mov     rsi, r12
0x18002e9db  cmp     [rsp+320h+var_2AC], r12d
0x18002e9e0  jnz     loc_18002ECDE
0x18002e9e6  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18002e9ec  test    al, al
0x18002e9ee  jnz     loc_18002ECDE
0x18002e9f4  mov     [rsp+320h+var_2B0], r12b
0x18002e9f9  lea     rdx, [rsp+320h+var_2B0]
0x18002e9fe  mov     rcx, r14
0x18002ea01  call    cs:__imp_?CheckLangNeutral@CMUILocale@@SAJPEBGPEA_N@Z; CMUILocale::CheckLangNeutral(ushort const *,bool *)
0x18002ea07  mov     r15d, eax
0x18002ea0a  test    eax, eax
0x18002ea0c  jns     short loc_18002EA5E
0x18002ea0e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ea14  mov     edx, r15d
0x18002ea17  mov     rcx, rax
0x18002ea1a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ea20  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea27  lea     rax, WPP_GLOBAL_Control
0x18002ea2e  cmp     rcx, rax
0x18002ea31  jz      short loc_18002EA56
0x18002ea33  test    byte ptr [rcx+1Ch], 1
0x18002ea37  jz      short loc_18002EA56
0x18002ea39  cmp     [rcx+19h], bl
0x18002ea3c  jb      short loc_18002EA56
0x18002ea3e  mov     edx, 1F5h
0x18002ea43  mov     r9d, r15d
0x18002ea46  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002ea4d  mov     rcx, [rcx+10h]
0x18002ea51  call    WPP_SF_d
0x18002ea56  mov     eax, r15d
0x18002ea59  jmp     loc_18002EFE7
0x18002ea5e  cmp     [rsp+320h+var_2B0], r12b
0x18002ea63  jnz     short loc_18002EABB
0x18002ea65  mov     [rsp+320h+var_2AF], r12b
0x18002ea6a  lea     r8, [rsp+320h+var_2AC]
0x18002ea6f  lea     rdx, [rsp+320h+var_2AF]
0x18002ea74  mov     rcx, r14
0x18002ea77  call    cs:__imp_?LocaleName_To_LCID@CMUILocale@@SAJPEBGPEA_NPEAK@Z; CMUILocale::LocaleName_To_LCID(ushort const *,bool *,ulong *)
0x18002ea7d  mov     r15d, eax
0x18002ea80  test    eax, eax
0x18002ea82  jns     short loc_18002EABB
0x18002ea84  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ea8a  mov     edx, r15d
0x18002ea8d  mov     rcx, rax
0x18002ea90  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ea96  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ea9d  lea     rax, WPP_GLOBAL_Control
0x18002eaa4  cmp     rcx, rax
0x18002eaa7  jz      short loc_18002EA56
0x18002eaa9  test    byte ptr [rcx+1Ch], 1
0x18002eaad  jz      short loc_18002EA56
0x18002eaaf  cmp     [rcx+19h], bl
0x18002eab2  jb      short loc_18002EA56
0x18002eab4  mov     edx, 1F6h
0x18002eab9  jmp     short loc_18002EA43
0x18002eabb  mov     ecx, [rsp+320h+var_2AC]
0x18002eabf  mov     eax, 3FFh
0x18002eac4  test    ax, cx
0x18002eac7  jz      loc_18002ECD9
0x18002eacd  mov     r8d, 104h
0x18002ead3  lea     rdx, [rbp+220h+var_250]
0x18002ead7  call    cs:__imp_?LCID_To_ms_XXX_Format@CMUILocale@@SAJKPEAG_K@Z; CMUILocale::LCID_To_ms_XXX_Format(ulong,ushort *,unsigned __int64)
0x18002eadd  mov     esi, eax
0x18002eadf  test    eax, eax
0x18002eae1  jns     short loc_18002EB28
0x18002eae3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002eae9  mov     edx, esi
0x18002eaeb  mov     rcx, rax
0x18002eaee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002eaf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eafb  lea     rax, WPP_GLOBAL_Control
0x18002eb02  cmp     rcx, rax
0x18002eb05  jz      loc_18002E9D1
0x18002eb0b  test    byte ptr [rcx+1Ch], 1
0x18002eb0f  jz      loc_18002E9D1
0x18002eb15  cmp     [rcx+19h], bl
0x18002eb18  jb      loc_18002E9D1
0x18002eb1e  mov     edx, 1F7h
0x18002eb23  jmp     loc_18002E9BE
0x18002eb28  lea     r8, [rbp+220h+var_288]; unsigned __int64 *
0x18002eb2c  mov     edx, 7FFFFFFFh; unsigned __int64
0x18002eb31  mov     rcx, rdi; unsigned __int16 *
0x18002eb34  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002eb39  mov     esi, eax
0x18002eb3b  test    eax, eax
0x18002eb3d  jns     short loc_18002EB84
0x18002eb3f  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002eb45  mov     edx, esi
0x18002eb47  mov     rcx, rax
0x18002eb4a  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002eb50  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eb57  lea     rax, WPP_GLOBAL_Control
0x18002eb5e  cmp     rcx, rax
0x18002eb61  jz      loc_18002E9D1
0x18002eb67  test    byte ptr [rcx+1Ch], 1
0x18002eb6b  jz      loc_18002E9D1
0x18002eb71  cmp     [rcx+19h], bl
0x18002eb74  jb      loc_18002E9D1
0x18002eb7a  mov     edx, 1F8h
0x18002eb7f  jmp     loc_18002E9BE
0x18002eb84  sub     r14, rdi
0x18002eb87  sar     r14, 1
0x18002eb8a  mov     [rdi+r14*2], r12w
0x18002eb8f  lea     r15, [r14+104h]
0x18002eb96  mov     rax, rbx
0x18002eb99  mul     r15
0x18002eb9c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002eba3  cmovb   rax, rcx
0x18002eba7  mov     rcx, rax
0x18002ebaa  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18002ebb0  mov     rsi, rax
0x18002ebb3  mov     [rbp+220h+var_288], rax
0x18002ebb7  test    rax, rax
0x18002ebba  jnz     short loc_18002EC0C
0x18002ebbc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ebc2  mov     edi, 80041006h
0x18002ebc7  mov     edx, edi
0x18002ebc9  mov     rcx, rax
0x18002ebcc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ebd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ebd9  lea     rax, WPP_GLOBAL_Control
0x18002ebe0  cmp     rcx, rax
0x18002ebe3  jz      loc_18002ECBC
0x18002ebe9  test    byte ptr [rcx+1Ch], 1
0x18002ebed  jz      loc_18002ECBC
0x18002ebf3  cmp     [rcx+19h], bl
0x18002ebf6  jb      loc_18002ECBC
0x18002ebfc  mov     edx, 1F9h
0x18002ec01  mov     r9d, 80041006h
0x18002ec07  jmp     loc_18002ECAB
0x18002ec0c  test    r14, r14
0x18002ec0f  jz      short loc_18002EC5B
0x18002ec11  mov     r8, rdi; unsigned __int16 *
0x18002ec14  mov     rdx, r15; unsigned __int64
0x18002ec17  mov     rcx, rsi; unsigned __int16 *
0x18002ec1a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002ec1f  mov     edi, eax
0x18002ec21  test    eax, eax
0x18002ec23  jns     short loc_18002EC5F
0x18002ec25  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ec2b  mov     edx, edi
0x18002ec2d  mov     rcx, rax
0x18002ec30  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ec36  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec3d  lea     rax, WPP_GLOBAL_Control
0x18002ec44  cmp     rcx, rax
0x18002ec47  jz      short loc_18002ECBC
0x18002ec49  test    byte ptr [rcx+1Ch], 1
0x18002ec4d  jz      short loc_18002ECBC
0x18002ec4f  cmp     [rcx+19h], bl
0x18002ec52  jb      short loc_18002ECBC
0x18002ec54  mov     edx, 1FAh
0x18002ec59  jmp     short loc_18002ECA8
0x18002ec5b  mov     [rax], r12w
0x18002ec5f  lea     r8, [rbp+220h+var_250]; unsigned __int16 *
0x18002ec63  mov     rdx, r15; unsigned __int64
0x18002ec66  mov     rcx, rsi; unsigned __int16 *
0x18002ec69  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002ec6e  mov     edi, eax
0x18002ec70  test    eax, eax
0x18002ec72  jns     short loc_18002ECCA
0x18002ec74  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002ec7a  mov     edx, edi
0x18002ec7c  mov     rcx, rax
0x18002ec7f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002ec85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ec8c  lea     rax, WPP_GLOBAL_Control
0x18002ec93  cmp     rcx, rax
0x18002ec96  jz      short loc_18002ECBC
0x18002ec98  test    byte ptr [rcx+1Ch], 1
0x18002ec9c  jz      short loc_18002ECBC
0x18002ec9e  cmp     [rcx+19h], bl
0x18002eca1  jb      short loc_18002ECBC
0x18002eca3  mov     edx, 1FBh
0x18002eca8  mov     r9d, edi
0x18002ecab  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18002ecb2  mov     rcx, [rcx+10h]
0x18002ecb6  call    WPP_SF_d
0x18002ecbb  nop
0x18002ecbc  mov     rcx, rsi
0x18002ecbf  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18002ecc5  jmp     loc_18002E912
  ... truncated ...
```
