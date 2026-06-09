# CWbemNamespace::Exec_PutClass(IWbemClassObject *,long,IWbemContext *,CBasicObjectSink *,int)

- ea: `0x18005b874`
- end: `0x18005cc5a`
- name: `?Exec_PutClass@CWbemNamespace@@QEAAJPEAUIWbemClassObject@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@H@Z`
- size: `5094`
- prototype: `__int64 __fastcall(CWbemNamespace *this, struct IWbemClassObject *, unsigned int, struct IWbemContext *, struct CBasicObjectSink *)`
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18005ada0`
- `0x18005ae80`

## callees

- `0x18000b104`
- `0x18000b140`
- `0x18000e950`
- `0x18000e99c`
- `0x18000fa74`
- `0x180011700`
- `0x18001307c`
- `0x18001f6d0`
- `0x18002fee4`
- `0x180039d40`
- `0x180039f68`
- `0x180039f98`
- `0x18003be20`
- `0x18003c000`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x18003d010`
- `0x180049580`
- `0x18004b934`
- `0x18005b874`
- `0x18005d98c`
- `0x18008531c`
- `0x18009bd1c`
- `0x1800a02dc`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18005bf25`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18005bf25`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18005bd5a`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18005cb0d`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18005cbfa`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18005bd5a`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18005cb0d`
- `wbemcomn!?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z` at `0x18005cbfa`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x18005bf3c`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005bc11`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005bc11`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005bc2f`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005bc2f`
- `wbemcomn!GetMemLogObject` at `0x18005c2c8`
- `wbemcomn!GetMemLogObject` at `0x18005c482`
- `wbemcomn!GetMemLogObject` at `0x18005c4da`
- `wbemcomn!GetMemLogObject` at `0x18005c50d`
- `wbemcomn!GetMemLogObject` at `0x18005c571`
- `wbemcomn!GetMemLogObject` at `0x18005c5d5`
- `wbemcomn!GetMemLogObject` at `0x18005c663`
- `wbemcomn!GetMemLogObject` at `0x18005c6ba`
- `wbemcomn!GetMemLogObject` at `0x18005c710`
- `wbemcomn!GetMemLogObject` at `0x18005c804`
- `wbemcomn!GetMemLogObject` at `0x18005c857`
- `wbemcomn!GetMemLogObject` at `0x18005c8bb`
- `wbemcomn!GetMemLogObject` at `0x18005c981`
- `wbemcomn!GetMemLogObject` at `0x18005cc0d`
- `wbemcomn!GetMemLogObject` at `0x18005c2c8`
- `wbemcomn!GetMemLogObject` at `0x18005c482`
- `wbemcomn!GetMemLogObject` at `0x18005c4da`
- `wbemcomn!GetMemLogObject` at `0x18005c50d`
- `wbemcomn!GetMemLogObject` at `0x18005c571`
- `wbemcomn!GetMemLogObject` at `0x18005c5d5`
- `wbemcomn!GetMemLogObject` at `0x18005c663`
- `wbemcomn!GetMemLogObject` at `0x18005c6ba`
- `wbemcomn!GetMemLogObject` at `0x18005c710`
- `wbemcomn!GetMemLogObject` at `0x18005c804`
- `wbemcomn!GetMemLogObject` at `0x18005c857`
- `wbemcomn!GetMemLogObject` at `0x18005c8bb`
- `wbemcomn!GetMemLogObject` at `0x18005c981`
- `wbemcomn!GetMemLogObject` at `0x18005cc0d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c2d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c490`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c4e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c51d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c581`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c5e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c671`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c6c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c71b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c815`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c8cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c98d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005cc1b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c2d6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c490`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c4e5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c51d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c581`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c5e0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c671`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c6c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c71b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c815`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c867`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c8cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005c98d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005cc1b`
- `FastProx!?IsIllegalDerivedClass@CSystemProperties@@SAHPEBG@Z` at `0x18005c149`
- `FastProx!?IsIllegalDerivedClass@CSystemProperties@@SAHPEBG@Z` at `0x18005c149`
- `OLEAUT32!__imp_VariantInit` at `0x18005b8ff`
- `OLEAUT32!__imp_VariantInit` at `0x18005b9e6`
- `OLEAUT32!__imp_VariantInit` at `0x18005bce7`
- `OLEAUT32!__imp_VariantInit` at `0x18005c00a`
- `OLEAUT32!__imp_VariantInit` at `0x18005ca2f`
- `OLEAUT32!__imp_VariantInit` at `0x18005ca99`
- `OLEAUT32!__imp_VariantInit` at `0x18005b8ff`
- `OLEAUT32!__imp_VariantInit` at `0x18005b9e6`
- `OLEAUT32!__imp_VariantInit` at `0x18005bce7`
- `OLEAUT32!__imp_VariantInit` at `0x18005c00a`
- `OLEAUT32!__imp_VariantInit` at `0x18005ca2f`
- `OLEAUT32!__imp_VariantInit` at `0x18005ca99`
- `OLEAUT32!__imp_VariantClear` at `0x18005bdfa`
- `OLEAUT32!__imp_VariantClear` at `0x18005be6e`
- `OLEAUT32!__imp_VariantClear` at `0x18005bea2`
- `OLEAUT32!__imp_VariantClear` at `0x18005bec5`
- `OLEAUT32!__imp_VariantClear` at `0x18005bee6`
- `OLEAUT32!__imp_VariantClear` at `0x18005c0c3`
- `OLEAUT32!__imp_VariantClear` at `0x18005c107`
- `OLEAUT32!__imp_VariantClear` at `0x18005c176`
- `OLEAUT32!__imp_VariantClear` at `0x18005c233`
- `OLEAUT32!__imp_VariantClear` at `0x18005c35c`
- `OLEAUT32!__imp_VariantClear` at `0x18005c9fa`
- `OLEAUT32!__imp_VariantClear` at `0x18005bdfa`
- `OLEAUT32!__imp_VariantClear` at `0x18005be6e`
- `OLEAUT32!__imp_VariantClear` at `0x18005bea2`
- `OLEAUT32!__imp_VariantClear` at `0x18005bec5`
- `OLEAUT32!__imp_VariantClear` at `0x18005bee6`
- `OLEAUT32!__imp_VariantClear` at `0x18005c0c3`
- `OLEAUT32!__imp_VariantClear` at `0x18005c107`
- `OLEAUT32!__imp_VariantClear` at `0x18005c176`
- `OLEAUT32!__imp_VariantClear` at `0x18005c233`
- `OLEAUT32!__imp_VariantClear` at `0x18005c35c`
- `OLEAUT32!__imp_VariantClear` at `0x18005c9fa`

## string_xrefs

- `0x18005bba0`: `Write (PutClass)`
- `0x18005bc5b`: `Write (PutClass)`
- `0x18005bfd2`: `Write (PutClass)`
- `0x18005c393`: `Full write repository permission is not enabled for the current user.`
- `0x18005cb4f`: `Full write repository permission is not enabled for the current user.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CWbemNamespace::Exec_PutClass(
        CWbemNamespace *this,
        struct IWbemClassObject *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  unsigned int v6; // eax
  int v9; // ebx
  unsigned __int16 *bstrVal; // r14
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdx
  int v13; // edi
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rsi
  int v19; // eax
  __int64 v20; // rdi
  const unsigned __int16 *v21; // r8
  int ObjectW; // eax
  struct IWbemClassObject *v23; // r14
  struct CSynchronousSink *v24; // rax
  struct CSynchronousSink *v25; // r12
  int v26; // eax
  int v27; // eax
  int v28; // r13d
  struct IWbemClassObject *v29; // r12
  unsigned __int16 *v30; // r13
  struct IWbemClassObject *v31; // r9
  LONGLONG v32; // rdx
  struct IWbemClassObject *v33; // r12
  const struct _GUID *v34; // r8
  int v35; // eax
  int v36; // r13d
  LONGLONG v37; // r8
  unsigned int v38; // r15d
  HRESULT v39; // eax
  int v41; // edx
  int v42; // eax
  unsigned int v43; // ebx
  int First_ms_XXX_Locale; // edi
  __int64 v45; // rdx
  int v46; // edi
  __int64 v47; // r8
  struct IWbemClassObject *v48; // r9
  const struct _GUID *v49; // r8
  unsigned int v50; // r14d
  LONGLONG v51; // rdx
  int v52; // r14d
  HRESULT v53; // eax
  int IsIllegalDerivedClass; // eax
  struct IWbemClassObject *v55; // r9
  unsigned __int16 *v56; // r8
  int v57; // edx
  int v58; // edi
  int v59; // r15d
  CObjectSink *v60; // r15
  CMemoryLog *v61; // rax
  CClientCnt *v62; // rcx
  __int64 v63; // rdx
  CMemoryLog *v64; // rax
  CMemoryLog *v65; // rax
  CClientCnt *v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // r9
  CMemoryLog *v69; // rax
  CMemoryLog *v70; // rax
  CMemoryLog *v71; // rax
  struct IWbemClassObject *v72; // r9
  unsigned __int16 *v73; // r8
  int v74; // edx
  CMemoryLog *v75; // rax
  CMemoryLog *v76; // rax
  CMemoryLog *v77; // rax
  struct IWbemClassObject *v78; // r9
  int v79; // eax
  CMemoryLog *v80; // rax
  CMemoryLog *v81; // rax
  CMemoryLog *v82; // rax
  struct IWbemClassObject *v83; // r9
  CMemoryLog *v84; // rax
  int v85; // r8d
  const struct _GUID *v86; // r8
  int v87; // eax
  LONGLONG llVal; // rdx
  int IsLocalMachine; // eax
  CMemoryLog *MemLogObject; // rax
  bool v91[8]; // [rsp+28h] [rbp-D8h]
  bool v92; // [rsp+28h] [rbp-D8h]
  __int64 v93; // [rsp+50h] [rbp-B0h] BYREF
  char v94[8]; // [rsp+58h] [rbp-A8h] BYREF
  CObjectSink *v95; // [rsp+60h] [rbp-A0h]
  __int64 v96; // [rsp+68h] [rbp-98h] BYREF
  __int64 v97; // [rsp+70h] [rbp-90h] BYREF
  struct IWbemClassObject *v98; // [rsp+78h] [rbp-88h] BYREF
  int v99; // [rsp+80h] [rbp-80h]
  __int64 v100; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v101; // [rsp+90h] [rbp-70h] BYREF
  struct CSynchronousSink *v102; // [rsp+A8h] [rbp-58h] BYREF
  VARIANTARG pvarg; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v104; // [rsp+C8h] [rbp-38h]
  __int64 v105; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 *v106; // [rsp+D8h] [rbp-28h] BYREF
  struct IWbemClassObject *v107; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v108; // [rsp+E8h] [rbp-18h]
  VARIANTARG v109; // [rsp+F0h] [rbp-10h] BYREF
  struct CSynchronousSink *v110; // [rsp+108h] [rbp+8h]
  VARIANTARG v111; // [rsp+110h] [rbp+10h] BYREF
  char v112[8]; // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG v113; // [rsp+138h] [rbp+38h] BYREF
  unsigned int v118; // [rsp+1B8h] [rbp+B8h]
  signed int v119; // [rsp+1B8h] [rbp+B8h]

  v6 = a3;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 92, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
    v6 = a3;
  }
  v108 = 0;
  v107 = 0;
  if ( !a5 || (v6 & 0x20000000) != 0 )
  {
    MemLogObject = GetMemLogObject();
    CMemoryLog::Write(MemLogObject, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    return 2147749896LL;
  }
  if ( !a2 )
  {
    v64 = GetMemLogObject();
    CMemoryLog::Write(v64, -2147217400);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 94, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749896LL);
    }
    return CBasicObjectSink::Return(a5, -2147217400, 0);
  }
  VariantInit(&pvarg);
  v9 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a2->lpVtbl->Get)(
         a2,
         L"__CLASS",
         0,
         &pvarg,
         0,
         0);
  if ( v9 < 0 )
  {
    v65 = GetMemLogObject();
    CMemoryLog::Write(v65, v9);
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_164;
    }
    v67 = 95;
    v68 = (unsigned int)v9;
    goto LABEL_163;
  }
  bstrVal = (unsigned __int16 *)&psz;
  v104 = (unsigned __int16 *)&psz;
  if ( pvarg.vt == 8 )
  {
    if ( pvarg.llVal )
      bstrVal = pvarg.bstrVal;
    v104 = bstrVal;
  }
  v11 = wcslen_max(bstrVal, (unsigned int)g_IdentifierLimit);
  if ( v11 > v12 )
  {
    v69 = GetMemLogObject();
    v9 = -2147217300;
    CMemoryLog::Write(v69, -2147217300);
    v66 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_164;
    }
    v67 = 96;
    v68 = 2147749996LL;
LABEL_163:
    WPP_SF_d(*((_QWORD *)v66 + 2), v67, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v68);
LABEL_164:
    v43 = CBasicObjectSink::Return(a5, v9, 0);
    goto LABEL_70;
  }
  COperationError::COperationError((COperationError *)v94, a5, L"PutClass", bstrVal, 1);
  if ( !v94[0] )
  {
    v70 = GetMemLogObject();
    CMemoryLog::Write(v70, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v43 = CBasicObjectSink::Return(a5, -2147217402, 0);
    goto LABEL_69;
  }
  v105 = 0;
  v13 = ((__int64 (__fastcall *)(struct IWbemClassObject *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
          a2,
          &IID__IWmiObject,
          &v105);
  v14 = v105;
  v93 = v105;
  if ( v13 < 0 )
  {
    v71 = GetMemLogObject();
    CMemoryLog::Write(v71, v13);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        98,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v13);
    }
    v73 = L"Invalid IWbemClassObject was specified.";
    v74 = -2147217400;
    goto LABEL_176;
  }
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v105 + 600LL))(v105) )
  {
    v75 = GetMemLogObject();
    CMemoryLog::Write(v75, -2147217386);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749910LL);
    }
    v73 = L"IWbemClassObject represents an instance. This operation is valid only for class.";
    v74 = -2147217386;
LABEL_176:
    v43 = COperationError::ErrorOccurredWithMessage((COperationError *)v94, v74, v73, v72);
    goto LABEL_68;
  }
  VariantInit(&v101);
  v91[0] = 0;
  v15 = ((__int64 (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD))a2->lpVtbl->Get)(
          a2,
          L"__SuperClass",
          0,
          &v101,
          0);
  if ( v15 < 0 )
  {
    v42 = COperationError::ErrorOccurredWithMessage((COperationError *)v94, v15, L"Unable to get the superclass.", 0);
    goto LABEL_66;
  }
  v16 = -1;
  if ( v101.vt == 8 )
  {
    if ( v101.llVal )
    {
      v17 = -1;
      do
        ++v17;
      while ( *(_WORD *)(v101.llVal + 2 * v17) );
      if ( v17 )
      {
        IsIllegalDerivedClass = CSystemProperties::IsIllegalDerivedClass(v101.bstrVal);
        v55 = 0;
        if ( IsIllegalDerivedClass )
        {
          v56 = L"Superclass is invalid.";
          v57 = -2147217395;
LABEL_96:
          v58 = COperationError::ErrorOccurredWithMessage((COperationError *)v94, v57, v56, v55);
          VariantClear(&v101);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          v93 = 0;
          if ( v95 )
            CObjectSink::Release(v95);
          v43 = v58;
          goto LABEL_70;
        }
      }
    }
  }
  if ( pvarg.vt != 8 || !pvarg.llVal || *pvarg.bstrVal == 95 )
  {
    v41 = -2147217386;
LABEL_65:
    v42 = COperationError::ErrorOccurred((COperationError *)v94, v41, 0);
LABEL_66:
    v43 = v42;
LABEL_67:
    VariantClear(&v101);
LABEL_68:
    CReleaseMe::release((CReleaseMe *)&v93);
LABEL_69:
    COperationError::~COperationError((COperationError *)v94);
LABEL_70:
    VariantClear(&pvarg);
    return v43;
  }
  do
    ++v16;
  while ( *(_WORD *)(pvarg.llVal + 2 * v16) );
  if ( *(_WORD *)(pvarg.llVal + 2 * v16 - 2) == 95 )
  {
    v41 = -2147217393;
    goto LABEL_65;
  }
  if ( !*((_DWORD *)this + 66) && *((_QWORD *)this + 31) )
  {
    v106 = 0;
    First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale((CWbemNamespace *)((char *)this + 176), &v106);
    if ( First_ms_XXX_Locale < 0 )
    {
      v76 = GetMemLogObject();
      CMemoryLog::Write(v76, First_ms_XXX_Locale);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          100,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)First_ms_XXX_Locale);
      }
      v56 = L"Unable to get the locale list.";
      v57 = First_ms_XXX_Locale;
      goto LABEL_96;
    }
    MakeGuard<int (*)(void *),unsigned short *>(&v109, CMUILocale::_Free, v106);
    *(_QWORD *)v91 = *((_QWORD *)this + 12);
    v46 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemContext *, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 31) + 32LL))(
            *((_QWORD *)this + 31),
            0,
            a4,
            *((_QWORD *)this + 14),
            v106);
    if ( v46 < 0 )
    {
      v77 = GetMemLogObject();
      CMemoryLog::Write(v77, v46);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          101,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v46);
      }
      v43 = COperationError::ErrorOccurredWithMessage(
              (COperationError *)v94,
              v46,
              L"Unable to get the class providers for this namespace.",
              v78);
      ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(&v109);
      goto LABEL_67;
    }
    if ( !LOBYTE(v109.vt) )
      ((void (__fastcall *)(IRecordInfo *, __int64, __int64, _QWORD))v109.llVal)(v109.pRecInfo, v45, v47, 0);
  }
  v18 = v108;
  v96 = v108;
  v100 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 32) + 224LL))(*((_QWORD *)this + 32), &v100);
  if ( v19 < 0 )
  {
    v43 = COperationError::ErrorOccurred((COperationError *)v94, v19, 0);
LABEL_197:
    CReleaseMe::release((CReleaseMe *)&v96);
    goto LABEL_67;
  }
  v20 = v100;
  v97 = v100;
  if ( *((_DWORD *)this + 66) || !*((_QWORD *)this + 31) )
  {
    if ( CWbemNamespace::InnerAllowedWithSD(
           this,
           (CWbemNamespace *)((char *)this + 216),
           4u,
           L"Write (PutClass)",
           bstrVal,
           v91[0],
           1) )
    {
      if ( v100 )
      {
        llVal = 0;
        if ( pvarg.vt == 8 )
          llVal = pvarg.llVal;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, LONGLONG, struct IWbemClassObject *))(*(_QWORD *)v100 + 24LL))(
          v100,
          4,
          a3,
          a4,
          0,
          *((_QWORD *)this + 12),
          llVal,
          a2);
      }
      VariantInit(&v111);
      if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a4->lpVtbl->GetValue)(
             a4,
             L"__GroupOperationId",
             0,
             &v111) >= 0 )
      {
        IsLocalMachine = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
        CPublishWMIOperationEvent::PublishRepUpdate(
          v111.cyVal.Lo,
          bstrVal,
          a3,
          a4,
          *((_DWORD *)this + 76),
          *((unsigned __int16 **)this + 36),
          *((_QWORD *)this + 37),
          IsLocalMachine);
      }
      v50 = CRepository::PutObject(
              *((struct IWmiDbSession **)this + 5),
              *((struct IWmiDbHandle **)this + 7),
              v49,
              a2,
              a3);
      if ( v100 )
      {
        v51 = 0;
        if ( pvarg.vt == 8 )
          v51 = pvarg.llVal;
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, LONGLONG, struct IWbemClassObject *, _QWORD))(*(_QWORD *)v100 + 32LL))(
          v100,
          4,
          v50,
          a4,
          0,
          *((_QWORD *)this + 12),
          v51,
          a2,
          0);
      }
      v52 = COperationError::ErrorOccurred((COperationError *)v94, v50, 0);
      v53 = VariantClear(&v111);
      if ( v53 < 0 )
        _com_issue_error(v53);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v97 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v96 = 0;
      VariantClear(&v101);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v93 = 0;
      if ( v95 )
        CObjectSink::Release(v95);
      v43 = v52;
      goto LABEL_70;
    }
    v43 = COperationError::ErrorOccurredWithMessage(
            (COperationError *)v94,
            -2147217405,
            L"Full write repository permission is not enabled for the current user.",
            v48);
    goto LABEL_196;
  }
  v99 = 0;
  v21 = 0;
  if ( pvarg.vt == 8 )
    v21 = pvarg.bstrVal;
  ObjectW = CRepository::GetObjectW(
              *((struct IWmiDbSession **)this + 5),
              *((struct IWmiDbHandle **)this + 7),
              v21,
              0,
              &v107);
  v23 = v107;
  v98 = v107;
  if ( ObjectW >= 0 )
  {
    if ( !v107 )
    {
      v81 = GetMemLogObject();
      CMemoryLog::Write(v81, -2147217398);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          103,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          2147749898LL);
      }
      v79 = COperationError::ErrorOccurred((COperationError *)v94, -2147217398, 0);
      goto LABEL_195;
    }
    if ( (a3 & 0x20000) != 0 )
    {
      v119 = CWbemNamespace::SplitLocalized(this, (struct CWbemObject *)a2, (struct CWbemObject *)v107);
      if ( v119 < 0 )
      {
        v80 = GetMemLogObject();
        CMemoryLog::Write(v80, v119);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v119);
        }
        v79 = CBasicObjectSink::Return(a5, v119, 0);
        goto LABEL_195;
      }
    }
    v99 = 1;
  }
  v24 = CSynchronousSink::Create(0);
  v25 = v24;
  v110 = v24;
  if ( !v24 )
  {
    v82 = GetMemLogObject();
    CMemoryLog::Write(v82, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v79 = COperationError::ErrorOccurredWithMessage(
            (COperationError *)v94,
            -2147217402,
            L"WMI Server is low in memory.",
            v83);
LABEL_195:
    v43 = v79;
    CReleaseMe::release((CReleaseMe *)&v98);
LABEL_196:
    CReleaseMe::release((CReleaseMe *)&v97);
    goto LABEL_197;
  }
  (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v24 + 8LL))(v24);
  v102 = v25;
  v26 = a3 | 0x10000;
  if ( !v99 )
    v26 = a3;
  v118 = v26;
  if ( !CWbemNamespace::InnerAllowedWithSD(
          this,
          (CWbemNamespace *)((char *)this + 216),
          0x10u,
          L"Write (PutClass)",
          v104,
          v91[0],
          1) )
  {
    v27 = -2147217405;
LABEL_103:
    v59 = COperationError::ErrorOccurred((COperationError *)v94, v27, 0);
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v25 + 16LL))(v25);
LABEL_104:
    v102 = 0;
    if ( v23 )
      ((void (__fastcall *)(struct IWbemClassObject *))v23->lpVtbl->Release)(v23);
    v98 = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v97 = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v96 = 0;
    VariantClear(&v101);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v93 = 0;
    if ( v95 )
      CObjectSink::Release(v95);
    v43 = v59;
    goto LABEL_70;
  }
  if ( !v108 )
  {
    v60 = v95;
    if ( v95 )
      COperationErrorSink::SetStatus(v95, 0, -2147217407, 0, 0);
    v61 = GetMemLogObject();
    CMemoryLog::Write(v61, -2147217407);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_ffbbabd785873c07a1ea9257e814c720_Traceguids, 2147749889LL);
    }
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v25 + 16LL))(v25);
    v102 = 0;
    if ( v23 )
      ((void (__fastcall *)(struct IWbemClassObject *))v23->lpVtbl->Release)(v23);
    v98 = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v97 = 0;
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    v96 = 0;
    VariantClear(&v101);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v93 = 0;
    if ( v60 )
      CObjectSink::Release(v60);
    v43 = -2147217407;
    goto LABEL_70;
  }
  v27 = (*(__int64 (__fastcall **)(__int64, struct IWbemClassObject *, _QWORD, struct IWbemContext *, struct CSynchronousSink *))(*(_QWORD *)v108 + 72LL))(
          v108,
          a2,
          v118,
          a4,
          v25);
  if ( v27 < 0 && v27 != -2147217406 && v27 != -2147217389 )
    goto LABEL_103;
  CSynchronousSink::Block(v25);
  CInCritSec::CInCritSec((CInCritSec *)v112, (struct _RTL_CRITICAL_SECTION *)v25 + 4);
  v28 = *((_DWORD *)v25 + 8);
  v29 = (struct IWbemClassObject *)*((_QWORD *)v25 + 6);
  if ( v29 )
    ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->AddRef)(v29);
  CInCritSec::~CInCritSec((CInCritSec *)v112);
  if ( v28 >= 0 )
  {
    if ( !v99 )
    {
      CBasicObjectSink::Return(a5, v28, v29);
      if ( v29 )
        ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
      v62 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_226;
      }
      v63 = 105;
      goto LABEL_225;
    }
  }
  else if ( v28 != -2147217406 && v28 != -2147217389 )
  {
    CBasicObjectSink::Return(a5, v28, v29);
    if ( v29 )
      ((void (__fastcall *)(struct IWbemClassObject *))v29->lpVtbl->Release)(v29);
    v84 = GetMemLogObject();
    CMemoryLog::Write(v84, v28);
    v62 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_226;
    }
    v63 = 106;
LABEL_225:
    WPP_SF_d(*((_QWORD *)v62 + 2), v63, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, (unsigned int)v28);
LABEL_226:
    CReleaseMe::release((CReleaseMe *)&v102);
    CReleaseMe::release((CReleaseMe *)&v98);
    CReleaseMe::release((CReleaseMe *)&v97);
    CReleaseMe::release((CReleaseMe *)&v96);
    VariantClear(&v101);
    CReleaseMe::release((CReleaseMe *)&v93);
    COperationError::~COperationError((COperationError *)v94);
    v43 = v28;
    goto LABEL_70;
  }
  v30 = v104;
  if ( !CWbemNamespace::InnerAllowedWithSD(
          this,
          (CWbemNamespace *)((char *)this + 216),
          4u,
          L"Write (PutClass)",
          v104,
          v92,
          1) )
  {
    v59 = COperationError::ErrorOccurredWithMessage(
            (COperationError *)v94,
            -2147217405,
            L"Full write repository permission is not enabled for the current user.",
            v31);
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v110 + 16LL))(v110);
    goto LABEL_104;
  }
  if ( v100 )
  {
    v32 = 0;
    if ( pvarg.vt == 8 )
      v32 = pvarg.llVal;
    v33 = a2;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, LONGLONG, struct IWbemClassObject *))(*(_QWORD *)v100 + 24LL))(
      v100,
      4,
      v118,
      a4,
      0,
      *((_QWORD *)this + 12),
      v32,
      a2);
  }
  else
  {
    v33 = a2;
  }
  VariantInit(&v113);
  if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a4->lpVtbl->GetValue)(
         a4,
         L"__GroupOperationId",
         0,
         &v113) >= 0 )
  {
    v35 = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
    CPublishWMIOperationEvent::PublishRepUpdate(
      v113.cyVal.Lo,
      v30,
      v118,
      a4,
      *((_DWORD *)this + 76),
      *((unsigned __int16 **)this + 36),
      *((_QWORD *)this + 37),
      v35);
  }
  v36 = CRepository::PutObject(
          *((struct IWmiDbSession **)this + 5),
          *((struct IWmiDbHandle **)this + 7),
          v34,
          v33,
          v118);
  if ( v36 == -2147217370 && (a3 & 0x40) != 0 )
  {
    VariantInit(&v109);
    if ( ((int (__fastcall *)(struct IWbemClassObject *, const unsigned __int16 *, _QWORD, VARIANTARG *))v33->lpVtbl->Get)(
           v33,
           L"__CLASS",
           0,
           &v109) >= 0
      && v109.vt == 8 )
    {
      v36 = CWbemNamespace::DeleteObject(this, v109.bstrVal, v85, a4, 0);
      if ( v36 >= 0 )
      {
        VariantInit(&v111);
        if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a4->lpVtbl->GetValue)(
               a4,
               L"__GroupOperationId",
               0,
               &v111) >= 0 )
        {
          v87 = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
          CPublishWMIOperationEvent::PublishRepUpdate(
            v111.cyVal.Lo,
            v104,
            v118,
            a4,
            *((_DWORD *)this + 76),
            *((unsigned __int16 **)this + 36),
            *((_QWORD *)this + 37),
            v87);
        }
        v36 = CRepository::PutObject(
                *((struct IWmiDbSession **)this + 5),
                *((struct IWmiDbHandle **)this + 7),
                v86,
                v33,
                v118);
        _variant_t::~_variant_t((_variant_t *)&v111);
      }
    }
    else
    {
      v36 = -2147217370;
    }
    _variant_t::~_variant_t((_variant_t *)&v109);
  }
  if ( v100 )
  {
    v37 = 0;
    if ( pvarg.vt == 8 )
      v37 = pvarg.llVal;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, LONGLONG, struct IWbemClassObject *, _QWORD))(*(_QWORD *)v100 + 32LL))(
      v100,
      4,
      (unsigned int)v36,
      a4,
      0,
      *((_QWORD *)this + 12),
      v37,
      v33,
      0);
  }
  v38 = COperationError::ErrorOccurred((COperationError *)v94, v36, 0);
  v39 = VariantClear(&v113);
  if ( v39 < 0 )
    _com_issue_error(v39);
  (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v110 + 16LL))(v110);
  v102 = 0;
  if ( v23 )
    ((void (__fastcall *)(struct IWbemClassObject *))v23->lpVtbl->Release)(v23);
  v98 = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v97 = 0;
  if ( v18 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  v96 = 0;
  VariantClear(&v101);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  v93 = 0;
  if ( v95 )
    CObjectSink::Release(v95);
  VariantClear(&pvarg);
  return v38;
}

```

## disassembly

```asm
0x18005b874  mov     rax, rsp
0x18005b877  mov     [rax+8], rbx
0x18005b87b  mov     [rax+20h], r9
0x18005b87f  mov     [rax+18h], r8d
0x18005b883  mov     [rax+10h], rdx
0x18005b887  push    rbp
0x18005b888  push    rsi
0x18005b889  push    rdi
0x18005b88a  push    r12
0x18005b88c  push    r13
0x18005b88e  push    r14
0x18005b890  push    r15
0x18005b892  lea     rbp, [rsp-50h]
0x18005b897  sub     rsp, 150h
0x18005b89e  mov     rsi, r9
0x18005b8a1  mov     eax, r8d
0x18005b8a4  mov     r13, rdx
0x18005b8a7  mov     r15, rcx
0x18005b8aa  xor     edi, edi
0x18005b8ac  lea     r14, WPP_GLOBAL_Control
0x18005b8b3  lea     rbx, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18005b8ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b8c1  cmp     rcx, r14
0x18005b8c4  jz      short loc_18005B8D0
0x18005b8c6  test    byte ptr [rcx+1Ch], 1
0x18005b8ca  jnz     loc_18005C459
0x18005b8d0  mov     [rbp+80h+var_98], rdi
0x18005b8d4  mov     [rbp+80h+var_A0], rdi
0x18005b8d8  mov     r12, [rbp+80h+arg_20]
0x18005b8df  test    r12, r12
0x18005b8e2  jz      loc_18005CC0D
0x18005b8e8  bt      eax, 1Dh
0x18005b8ec  jb      loc_18005CC0D
0x18005b8f2  test    r13, r13
0x18005b8f5  jz      loc_18005C482
0x18005b8fb  lea     rcx, [rbp+80h+pvarg]; pvarg
0x18005b8ff  call    cs:__imp_VariantInit
0x18005b905  nop
0x18005b906  mov     rax, [r13+0]
0x18005b90a  mov     qword ptr [rsp+180h+var_158], rdi
0x18005b90f  mov     [rsp+180h+var_160], rdi
0x18005b914  lea     r9, [rbp+80h+pvarg]
0x18005b918  xor     r8d, r8d
0x18005b91b  lea     rdx, aClass_0; "__CLASS"
0x18005b922  mov     rcx, r13
0x18005b925  mov     rax, [rax+20h]
0x18005b929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b92e  mov     ebx, eax
0x18005b930  test    eax, eax
0x18005b932  js      loc_18005C4DA
0x18005b938  lea     r14, psz
0x18005b93f  mov     [rbp+80h+var_B8], r14
0x18005b943  mov     eax, 8
0x18005b948  cmp     ax, word ptr [rbp+80h+pvarg]
0x18005b94c  jz      loc_18005C26A
0x18005b952  mov     edx, cs:?g_IdentifierLimit@@3KA; unsigned __int64
0x18005b958  mov     rcx, r14; unsigned __int16 *
0x18005b95b  call    ?wcslen_max@@YA_KPEBG_K@Z; wcslen_max(ushort const *,unsigned __int64)
0x18005b960  cmp     rax, rdx
0x18005b963  ja      loc_18005C50D
0x18005b969  mov     dword ptr [rsp+180h+var_160], 1; int
0x18005b971  mov     r9, r14; unsigned __int16 *
0x18005b974  lea     r8, aPutclass; "PutClass"
0x18005b97b  mov     rdx, r12; struct CBasicObjectSink *
0x18005b97e  lea     rcx, [rsp+180h+var_128]; this
0x18005b983  call    ??0COperationError@@QEAA@PEAVCBasicObjectSink@@PEBG1H@Z; COperationError::COperationError(CBasicObjectSink *,ushort const *,ushort const *,int)
0x18005b988  nop
0x18005b989  cmp     [rsp+180h+var_128], dil
0x18005b98e  jz      loc_18005C571
0x18005b994  mov     [rbp+80h+var_B0], rdi
0x18005b998  mov     rax, [r13+0]
0x18005b99c  lea     r8, [rbp+80h+var_B0]
0x18005b9a0  lea     rdx, IID__IWmiObject
0x18005b9a7  mov     rcx, r13
0x18005b9aa  mov     rax, [rax]
0x18005b9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9b2  mov     edi, eax
0x18005b9b4  mov     rbx, [rbp+80h+var_B0]
0x18005b9b8  mov     [rsp+180h+var_130], rbx
0x18005b9bd  test    eax, eax
0x18005b9bf  js      loc_18005C5D5
0x18005b9c5  mov     rcx, [rbp+80h+var_B0]
0x18005b9c9  mov     rax, [rcx]
0x18005b9cc  mov     rax, [rax+258h]
0x18005b9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b9d8  xor     edi, edi
0x18005b9da  test    eax, eax
0x18005b9dc  jz      loc_18005C663
0x18005b9e2  lea     rcx, [rbp+80h+var_F0]; pvarg
0x18005b9e6  call    cs:__imp_VariantInit
0x18005b9ec  nop
0x18005b9ed  mov     rax, [r13+0]
0x18005b9f1  mov     qword ptr [rsp+180h+var_158], rdi; bool
0x18005b9f6  mov     [rsp+180h+var_160], rdi
0x18005b9fb  lea     r9, [rbp+80h+var_F0]
0x18005b9ff  xor     r8d, r8d
0x18005ba02  lea     rdx, aSuperclass_1; "__SuperClass"
0x18005ba09  mov     rcx, r13
0x18005ba0c  mov     rax, [rax+20h]
0x18005ba10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ba15  xor     r9d, r9d; struct IWbemClassObject *
0x18005ba18  test    eax, eax
0x18005ba1a  js      loc_18005C698
0x18005ba20  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005ba24  movzx   edx, word ptr [rbp+80h+var_F0]
0x18005ba28  lea     r10d, [r9+8]
0x18005ba2c  cmp     dx, r10w
0x18005ba30  jnz     short loc_18005BA5C
0x18005ba32  mov     r8, qword ptr [rbp+80h+var_F0+8]
0x18005ba36  test    r8, r8
0x18005ba39  jz      short loc_18005BA5C
0x18005ba3b  mov     ecx, r9d
0x18005ba3e  cmp     dx, r10w
0x18005ba42  cmovz   rcx, r8
0x18005ba46  mov     rax, rdi
0x18005ba49  inc     rax
0x18005ba4c  cmp     [rcx+rax*2], r9w
0x18005ba51  jnz     short loc_18005BA49
0x18005ba53  test    rax, rax
0x18005ba56  jnz     loc_18005C13E
0x18005ba5c  movzx   ecx, word ptr [rbp+80h+pvarg]
0x18005ba60  cmp     cx, r10w
0x18005ba64  jnz     loc_18005BEAD
0x18005ba6a  mov     r8, qword ptr [rbp+80h+pvarg+8]
0x18005ba6e  test    r8, r8
0x18005ba71  jz      loc_18005BEAD
0x18005ba77  mov     rax, r9
0x18005ba7a  cmp     cx, r10w
0x18005ba7e  cmovz   rax, r8
0x18005ba82  mov     edx, 5Fh ; '_'
0x18005ba87  cmp     [rax], dx
0x18005ba8a  jz      loc_18005BEAD
0x18005ba90  mov     rax, r9
0x18005ba93  cmp     cx, r10w
0x18005ba97  cmovz   rax, r8
0x18005ba9b  inc     rdi
0x18005ba9e  cmp     [rax+rdi*2], r9w
0x18005baa3  jnz     short loc_18005BA9B
0x18005baa5  cmp     [rax+rdi*2-2], dx
0x18005baaa  jz      loc_18005C6B0
0x18005bab0  cmp     [r15+108h], r9d
0x18005bab7  jz      loc_18005BF09
0x18005babd  mov     rsi, [rbp+80h+var_98]
0x18005bac1  mov     [rsp+180h+var_118], rsi
0x18005bac6  mov     [rbp+80h+var_F8], r9
0x18005baca  mov     rcx, [r15+100h]
0x18005bad1  mov     rax, [rcx]
0x18005bad4  lea     rdx, [rbp+80h+var_F8]
0x18005bad8  mov     rax, [rax+0E0h]
0x18005badf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bae4  xor     ecx, ecx
0x18005bae6  test    eax, eax
0x18005bae8  js      loc_18005C77B
0x18005baee  mov     rdi, [rbp+80h+var_F8]
0x18005baf2  mov     [rsp+180h+var_110], rdi
0x18005baf7  cmp     [r15+108h], ecx
0x18005bafe  jnz     loc_18005BFC1
0x18005bb04  cmp     [r15+0F8h], rcx
0x18005bb0b  jz      loc_18005BFC1
0x18005bb11  mov     [rbp+80h+var_100], ecx
0x18005bb14  mov     r8d, ecx
0x18005bb17  lea     eax, [rcx+8]
0x18005bb1a  cmp     word ptr [rbp+80h+pvarg], ax
0x18005bb1e  cmovz   r8, qword ptr [rbp+80h+pvarg+8]; unsigned __int16 *
0x18005bb23  lea     rax, [rbp+80h+var_A0]
0x18005bb27  mov     [rsp+180h+var_160], rax; struct IWbemClassObject **
0x18005bb2c  xor     r9d, r9d; unsigned int
0x18005bb2f  mov     rdx, [r15+38h]; struct IWmiDbHandle *
0x18005bb33  mov     rcx, [r15+28h]; struct IWmiDbSession *
0x18005bb37  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x18005bb3c  mov     r14, [rbp+80h+var_A0]
0x18005bb40  mov     [rsp+180h+var_108], r14
0x18005bb45  test    eax, eax
0x18005bb47  jns     loc_18005C7DA
0x18005bb4d  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x18005bb4f  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18005bb54  mov     r12, rax
0x18005bb57  mov     [rbp+80h+var_78], rax
0x18005bb5b  test    rax, rax
0x18005bb5e  jz      loc_18005C8BB
0x18005bb64  mov     rax, [rax]
0x18005bb67  mov     rcx, r12
0x18005bb6a  mov     rax, [rax+8]
0x18005bb6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bb73  mov     [rbp+80h+var_D8], r12
0x18005bb77  mov     eax, [rbp+80h+arg_10]
0x18005bb7d  bts     eax, 10h
0x18005bb81  cmp     [rbp+80h+var_100], 0
0x18005bb85  cmovz   eax, [rbp+80h+arg_10]
0x18005bb8c  mov     [rbp+80h+arg_28], eax
0x18005bb92  mov     [rsp+180h+var_150], 1; bool
0x18005bb97  mov     rdx, [rbp+80h+var_B8]
0x18005bb9b  mov     [rsp+180h+var_160], rdx; unsigned __int16 *
0x18005bba0  lea     r9, aWritePutclass; "Write (PutClass)"
0x18005bba7  mov     r8d, 10h; unsigned int
0x18005bbad  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x18005bbb4  mov     rcx, r15; this
0x18005bbb7  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18005bbbc  xor     edx, edx; int
0x18005bbbe  test    al, al
0x18005bbc0  jz      loc_18005C1B6
0x18005bbc6  mov     rcx, [rbp+80h+var_98]
0x18005bbca  test    rcx, rcx
0x18005bbcd  jz      loc_18005C2A5
0x18005bbd3  mov     rax, [rcx]
0x18005bbd6  mov     [rsp+180h+var_160], r12
0x18005bbdb  mov     r9, [rbp+80h+arg_18]
0x18005bbe2  mov     r8d, [rbp+80h+arg_28]
0x18005bbe9  mov     rdx, r13
0x18005bbec  mov     rax, [rax+48h]
0x18005bbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbf5  test    eax, eax
0x18005bbf7  js      loc_18005C43E
0x18005bbfd  mov     rcx, r12; this
0x18005bc00  call    ?Block@CSynchronousSink@@QEAAXXZ; CSynchronousSink::Block(void)
0x18005bc05  lea     rdx, [r12+0A0h]
0x18005bc0d  lea     rcx, [rbp+80h+var_50]
0x18005bc11  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18005bc17  nop
0x18005bc18  mov     r13d, [r12+20h]
0x18005bc1d  mov     r12, [r12+30h]
0x18005bc22  test    r12, r12
0x18005bc25  jnz     loc_18005C3C4
0x18005bc2b  lea     rcx, [rbp+80h+var_50]
0x18005bc2f  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18005bc35  xor     eax, eax
0x18005bc37  test    r13d, r13d
0x18005bc3a  jns     loc_18005C3D9
0x18005bc40  cmp     r13d, 80041002h
0x18005bc47  jnz     loc_18005C94D
0x18005bc4d  mov     [rsp+180h+var_150], 1; bool
0x18005bc52  mov     r13, [rbp+80h+var_B8]
0x18005bc56  mov     [rsp+180h+var_160], r13; unsigned __int16 *
0x18005bc5b  lea     r9, aWritePutclass; "Write (PutClass)"
0x18005bc62  mov     r8d, 4; unsigned int
0x18005bc68  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x18005bc6f  mov     rcx, r15; this
0x18005bc72  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18005bc77  xor     r12d, r12d
0x18005bc7a  test    al, al
0x18005bc7c  jz      loc_18005C393
0x18005bc82  mov     rcx, [rbp+80h+var_F8]
0x18005bc86  test    rcx, rcx
0x18005bc89  jz      loc_18005C299
0x18005bc8f  mov     rax, [rcx]
0x18005bc92  mov     edx, r12d
0x18005bc95  lea     r8d, [r12+8]
0x18005bc9a  cmp     word ptr [rbp+80h+pvarg], r8w
0x18005bc9f  cmovz   rdx, qword ptr [rbp+80h+pvarg+8]
0x18005bca4  mov     r12, [rbp+80h+arg_8]
0x18005bcab  mov     [rsp+180h+var_148], r12
0x18005bcb0  mov     qword ptr [rsp+180h+var_150], rdx
0x18005bcb5  mov     rdx, [r15+60h]
0x18005bcb9  mov     qword ptr [rsp+180h+var_158], rdx
0x18005bcbe  mov     [rsp+180h+var_160], 0
0x18005bcc7  mov     r9, [rbp+80h+arg_18]
0x18005bcce  mov     r8d, [rbp+80h+arg_28]
0x18005bcd5  mov     edx, 4
0x18005bcda  mov     rax, [rax+18h]
0x18005bcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bce3  lea     rcx, [rbp+80h+var_48]; pvarg
0x18005bce7  call    cs:__imp_VariantInit
0x18005bced  nop
0x18005bcee  mov     rcx, [rbp+80h+arg_18]
0x18005bcf5  mov     rax, [rcx]
0x18005bcf8  lea     r9, [rbp+80h+var_48]
0x18005bcfc  xor     r8d, r8d
0x18005bcff  lea     rdx, aGroupoperation; "__GroupOperationId"
0x18005bd06  mov     rax, [rax+48h]
0x18005bd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd0f  test    eax, eax
0x18005bd11  js      short loc_18005BD60
0x18005bd13  mov     rcx, [r15+118h]; String2
0x18005bd1a  call    ?IsLocalMachine@CWbemNamespace@@KAHPEBG@Z; CWbemNamespace::IsLocalMachine(ushort const *)
0x18005bd1f  mov     dword ptr [rsp+180h+var_148], eax
0x18005bd23  mov     rax, [r15+128h]
0x18005bd2a  mov     qword ptr [rsp+180h+var_150], rax
0x18005bd2f  mov     rax, [r15+120h]
0x18005bd36  mov     qword ptr [rsp+180h+var_158], rax
0x18005bd3b  mov     eax, [r15+130h]
0x18005bd42  mov     dword ptr [rsp+180h+var_160], eax
0x18005bd46  mov     r9, [rbp+80h+arg_18]
0x18005bd4d  mov     r8d, [rbp+80h+arg_28]
0x18005bd54  mov     rdx, r13
0x18005bd57  mov     ecx, dword ptr [rbp+80h+var_48+8]
0x18005bd5a  call    cs:__imp_?PublishRepUpdate@CPublishWMIOperationEvent@@SAJKPEAGKPEAUIWbemContext@@K0_KH@Z; CPublishWMIOperationEvent::PublishRepUpdate(ulong,ushort *,ulong,IWbemContext *,ulong,ushort *,unsigned __int64,int)
0x18005bd60  mov     eax, [rbp+80h+arg_28]
0x18005bd66  mov     dword ptr [rsp+180h+var_160], eax; unsigned int
0x18005bd6a  mov     r9, r12; void *
0x18005bd6d  mov     rdx, [r15+38h]; struct IWmiDbHandle *
0x18005bd71  mov     rcx, [r15+28h]; struct IWmiDbSession *
0x18005bd75  call    ?PutObject@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@AEBU_GUID@@PEAXK@Z; CRepository::PutObject(IWmiDbSession *,IWmiDbHandle *,_GUID const &,void *,ulong)
0x18005bd7a  mov     r13d, eax
0x18005bd7d  cmp     eax, 80041026h
0x18005bd82  jz      loc_18005CA1E
0x18005bd88  mov     rcx, [rbp+80h+var_F8]
0x18005bd8c  xor     edx, edx
0x18005bd8e  test    rcx, rcx
0x18005bd91  jz      loc_18005C291
0x18005bd97  mov     rax, [rcx]
  ... truncated ...
```
