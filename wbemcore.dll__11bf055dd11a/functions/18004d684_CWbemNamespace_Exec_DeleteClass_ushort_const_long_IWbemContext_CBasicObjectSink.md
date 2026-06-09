# CWbemNamespace::Exec_DeleteClass(ushort const *,long,IWbemContext *,CBasicObjectSink *)

- ea: `0x18004d684`
- end: `0x18004e2aa`
- name: `?Exec_DeleteClass@CWbemNamespace@@QEAAJPEBGJPEAUIWbemContext@@PEAVCBasicObjectSink@@@Z`
- size: `3110`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct IWbemContext *@<r9>, struct CBasicObjectSink *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18004e2b0`

## callees

- `0x18000b140`
- `0x18000b17c`
- `0x18000e950`
- `0x18000e99c`
- `0x18000fa74`
- `0x180011700`
- `0x18001307c`
- `0x18001f6d0`
- `0x18002fee4`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x18003d010`
- `0x18004d2f8`
- `0x18004d684`
- `0x18005d98c`
- `0x18005edf4`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18004d78f`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18004d78f`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004decd`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004e15e`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004decd`
- `wbemcomn!?PublishRepDelete@CPublishWMIOperationEvent@@SAJKPEAGPEAUIWbemContext@@K0_KH@Z` at `0x18004e15e`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x18004d7e8`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18004dd34`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18004dd34`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004dd62`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18004dd62`
- `wbemcomn!GetMemLogObject` at `0x18004d715`
- `wbemcomn!GetMemLogObject` at `0x18004d79b`
- `wbemcomn!GetMemLogObject` at `0x18004d847`
- `wbemcomn!GetMemLogObject` at `0x18004d8e3`
- `wbemcomn!GetMemLogObject` at `0x18004d9b9`
- `wbemcomn!GetMemLogObject` at `0x18004da34`
- `wbemcomn!GetMemLogObject` at `0x18004da90`
- `wbemcomn!GetMemLogObject` at `0x18004db13`
- `wbemcomn!GetMemLogObject` at `0x18004dc32`
- `wbemcomn!GetMemLogObject` at `0x18004dca9`
- `wbemcomn!GetMemLogObject` at `0x18004dd97`
- `wbemcomn!GetMemLogObject` at `0x18004df3f`
- `wbemcomn!GetMemLogObject` at `0x18004e04b`
- `wbemcomn!GetMemLogObject` at `0x18004e1c0`
- `wbemcomn!GetMemLogObject` at `0x18004e232`
- `wbemcomn!GetMemLogObject` at `0x18004d715`
- `wbemcomn!GetMemLogObject` at `0x18004d79b`
- `wbemcomn!GetMemLogObject` at `0x18004d847`
- `wbemcomn!GetMemLogObject` at `0x18004d8e3`
- `wbemcomn!GetMemLogObject` at `0x18004d9b9`
- `wbemcomn!GetMemLogObject` at `0x18004da34`
- `wbemcomn!GetMemLogObject` at `0x18004da90`
- `wbemcomn!GetMemLogObject` at `0x18004db13`
- `wbemcomn!GetMemLogObject` at `0x18004dc32`
- `wbemcomn!GetMemLogObject` at `0x18004dca9`
- `wbemcomn!GetMemLogObject` at `0x18004dd97`
- `wbemcomn!GetMemLogObject` at `0x18004df3f`
- `wbemcomn!GetMemLogObject` at `0x18004e04b`
- `wbemcomn!GetMemLogObject` at `0x18004e1c0`
- `wbemcomn!GetMemLogObject` at `0x18004e232`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d725`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d7a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d852`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d8ee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d9c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004da44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004daa2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004db25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004dc40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004dcb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004dda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004df4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004e05b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004e1cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004e242`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d725`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d7a6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d852`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d8ee`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004d9c9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004da44`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004daa2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004db25`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004dc40`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004dcb9`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004dda3`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004df4b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004e05b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004e1cb`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18004e242`
- `OLEAUT32!__imp_SysAllocString` at `0x18004db00`
- `OLEAUT32!__imp_SysAllocString` at `0x18004db00`
- `OLEAUT32!__imp_SysFreeString` at `0x18004dfb9`
- `OLEAUT32!__imp_SysFreeString` at `0x18004dfb9`
- `OLEAUT32!__imp_VariantInit` at `0x18004de68`
- `OLEAUT32!__imp_VariantInit` at `0x18004e0fd`
- `OLEAUT32!__imp_VariantInit` at `0x18004de68`
- `OLEAUT32!__imp_VariantInit` at `0x18004e0fd`
- `OLEAUT32!__imp_VariantClear` at `0x18004e21c`
- `OLEAUT32!__imp_VariantClear` at `0x18004e21c`

## string_xrefs

- `0x18004d999`: `Delete (DeleteClass)`
- `0x18004dc85`: `Delete (DeleteClass)`
- `0x18004e032`: `Delete (DeleteClass)`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWbemNamespace::Exec_DeleteClass(
        CWbemNamespace *this,
        unsigned __int16 *a2,
        unsigned int a3,
        struct IWbemContext *a4,
        struct CBasicObjectSink *a5)
{
  __int64 v9; // rbx
  CBasicObjectSink *v10; // r15
  CMemoryLog *v11; // rax
  int First_ms_XXX_Locale; // ebx
  CClientCnt *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  CMemoryLog *v16; // rax
  int v17; // ebx
  CMemoryLog *v18; // rax
  unsigned int v19; // ebx
  int v21; // edi
  CMemoryLog *v22; // rax
  __int64 v23; // rdi
  int ObjectW; // eax
  struct IWbemClassObject *v25; // rsi
  CMemoryLog *v26; // rax
  int v27; // ebx
  CClientCnt *v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // r9
  int v31; // edx
  CMemoryLog *v32; // rax
  struct CSynchronousSink *v33; // rax
  struct CSynchronousSink *v34; // r12
  CMemoryLog *v35; // rax
  OLECHAR *v36; // rax
  CMemoryLog *v37; // rax
  unsigned int v38; // r14d
  int v39; // eax
  CMemoryLog *v40; // rax
  unsigned int v41; // ebx
  CClientCnt *v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // r9
  CMemoryLog *v45; // rax
  int v46; // r12d
  struct IWbemClassObject *v47; // rcx
  CMemoryLog *v48; // rax
  __int64 v49; // r10
  struct IWbemContext *v50; // r12
  int v51; // eax
  CMemoryLog *v52; // rax
  CMemoryLog *v53; // rax
  int IsLocalMachine; // eax
  int v55; // esi
  CMemoryLog *v56; // rax
  HRESULT v57; // eax
  struct IErrorInfo *v58; // rdx
  CMemoryLog *MemLogObject; // rax
  bool v60[8]; // [rsp+30h] [rbp-99h]
  __int64 v61; // [rsp+58h] [rbp-71h] BYREF
  struct IWbemClassObject *v62; // [rsp+60h] [rbp-69h] BYREF
  __int64 v63; // [rsp+68h] [rbp-61h] BYREF
  struct CSynchronousSink *v64; // [rsp+70h] [rbp-59h] BYREF
  struct IWbemClassObject *v65; // [rsp+78h] [rbp-51h]
  struct IWbemClassObject *v66; // [rsp+80h] [rbp-49h] BYREF
  __int64 v67; // [rsp+88h] [rbp-41h]
  OLECHAR *v68; // [rsp+90h] [rbp-39h] BYREF
  __int64 v69; // [rsp+98h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-29h] BYREF
  struct IWbemClassObject *v71; // [rsp+B8h] [rbp-11h] BYREF
  BSTR bstrString; // [rsp+C0h] [rbp-9h]
  struct CSynchronousSink *v73; // [rsp+C8h] [rbp-1h]
  _BYTE v74[64]; // [rsp+D8h] [rbp+Fh] BYREF
  unsigned __int16 *v75; // [rsp+130h] [rbp+67h] BYREF
  unsigned int v76; // [rsp+138h] [rbp+6Fh]
  struct IWbemContext *v77; // [rsp+140h] [rbp+77h]

  v77 = a4;
  v76 = a3;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, a2);
  }
  v9 = 0;
  v67 = 0;
  v66 = 0;
  v10 = a5;
  if ( !a2 || !a5 )
  {
    MemLogObject = GetMemLogObject();
    First_ms_XXX_Locale = -2147217400;
    CMemoryLog::Write(MemLogObject, -2147217400);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return CBasicObjectSink::Return(v10, First_ms_XXX_Locale, 0);
    }
    v14 = 62;
    v15 = 2147749896LL;
    goto LABEL_140;
  }
  if ( *a2 != 95 )
  {
    if ( !*((_DWORD *)this + 66) && *((_QWORD *)this + 31) )
    {
      v75 = 0;
      First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale((CWbemNamespace *)((char *)this + 176), &v75);
      if ( First_ms_XXX_Locale < 0 )
      {
        v16 = GetMemLogObject();
        CMemoryLog::Write(v16, First_ms_XXX_Locale);
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          return CBasicObjectSink::Return(v10, First_ms_XXX_Locale, 0);
        }
        v14 = 64;
        v15 = (unsigned int)First_ms_XXX_Locale;
        goto LABEL_140;
      }
      MakeGuard<int (*)(void *),unsigned short *>(&pvarg, CMUILocale::_Free, v75);
      *(_QWORD *)v60 = *((_QWORD *)this + 12);
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct IWbemContext *, _QWORD, unsigned __int16 *))(**((_QWORD **)this + 31) + 32LL))(
              *((_QWORD *)this + 31),
              0,
              a4,
              *((_QWORD *)this + 14),
              v75);
      if ( v17 < 0 )
      {
        v18 = GetMemLogObject();
        CMemoryLog::Write(v18, v17);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            65,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v17);
        }
        v19 = CBasicObjectSink::Return(v10, v17, 0);
        ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)&pvarg);
        return v19;
      }
      ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)&pvarg);
      v9 = v67;
    }
    v69 = v9;
    v63 = 0;
    v21 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 32) + 224LL))(
            *((_QWORD *)this + 32),
            &v63);
    if ( v21 < 0 )
    {
      v22 = GetMemLogObject();
      CMemoryLog::Write(v22, v21);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          66,
          WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
          (unsigned int)v21);
      }
      v19 = CBasicObjectSink::Return(v10, v21, 0);
      goto LABEL_122;
    }
    v23 = v63;
    v61 = v63;
    if ( *((_DWORD *)this + 66) || !*((_QWORD *)this + 31) )
    {
      if ( !CWbemNamespace::InnerAllowedWithSD(
              this,
              (CWbemNamespace *)((char *)this + 216),
              4u,
              L"Delete (DeleteClass)",
              a2,
              v60[0],
              1) )
      {
        v53 = GetMemLogObject();
        CMemoryLog::Write(v53, -2147217405);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            67,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            2147749891LL);
        }
        v19 = CBasicObjectSink::Return(v10, -2147217405, 0);
        goto LABEL_121;
      }
      if ( v63 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)v63 + 40LL))(
          v63,
          8,
          a3,
          a4,
          0,
          *((_QWORD *)this + 12),
          a2);
      VariantInit(&pvarg);
      if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))a4->lpVtbl->GetValue)(
             a4,
             L"__GroupOperationId",
             0,
             &pvarg) >= 0 )
      {
        IsLocalMachine = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
        CPublishWMIOperationEvent::PublishRepDelete(
          pvarg.cyVal.Lo,
          a2,
          a4,
          *((_DWORD *)this + 76),
          *((unsigned __int16 **)this + 36),
          *((_QWORD *)this + 37),
          IsLocalMachine);
      }
      v55 = CRepository::DeleteByPath(*((struct IWmiDbSession **)this + 5), *((struct IWmiDbHandle **)this + 7), a2, a3);
      if ( v63 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *, _QWORD))(*(_QWORD *)v63 + 48LL))(
          v63,
          8,
          (unsigned int)v55,
          a4,
          0,
          *((_QWORD *)this + 12),
          a2,
          0);
      if ( v55 < 0 )
      {
        v56 = GetMemLogObject();
        CMemoryLog::Write(v56, v55);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            68,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v55);
        }
      }
      v38 = CBasicObjectSink::Return(v10, v55, 0);
      v57 = VariantClear(&pvarg);
      if ( v57 < 0 )
        _com_issue_error(v57, v58);
      goto LABEL_65;
    }
    ObjectW = CRepository::GetObjectW(
                *((struct IWmiDbSession **)this + 5),
                *((struct IWmiDbHandle **)this + 7),
                a2,
                0,
                &v66);
    v25 = v66;
    v62 = v66;
    if ( ObjectW < 0 )
    {
      LODWORD(v75) = 0;
    }
    else
    {
      if ( !CWbemNamespace::InnerAllowedWithSD(
              this,
              (CWbemNamespace *)((char *)this + 216),
              4u,
              L"Delete (DeleteClass)",
              a2,
              v60[0],
              1) )
      {
        v26 = GetMemLogObject();
        v27 = -2147217405;
        CMemoryLog::Write(v26, -2147217405);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v29 = 69;
        v30 = 2147749891LL;
LABEL_41:
        WPP_SF_d(*((_QWORD *)v28 + 2), v29, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v30);
LABEL_42:
        v31 = v27;
LABEL_43:
        v19 = CBasicObjectSink::Return(v10, v31, 0);
LABEL_44:
        CReleaseMe::release((CReleaseMe *)&v62);
LABEL_121:
        CReleaseMe::release((CReleaseMe *)&v61);
LABEL_122:
        CReleaseMe::release((CReleaseMe *)&v69);
        return v19;
      }
      LODWORD(v75) = 1;
      if ( !v66 )
      {
        v32 = GetMemLogObject();
        v27 = -2147217398;
        CMemoryLog::Write(v32, -2147217398);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_42;
        }
        v29 = 70;
        v30 = 2147749898LL;
        goto LABEL_41;
      }
    }
    v33 = CSynchronousSink::Create(0);
    v34 = v33;
    v73 = v33;
    if ( !v33 )
    {
      v35 = GetMemLogObject();
      CMemoryLog::Write(v35, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
      }
      v31 = -2147217402;
      goto LABEL_43;
    }
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v33 + 8LL))(v33);
    v64 = v34;
    v36 = SysAllocString(a2);
    bstrString = v36;
    if ( !v36 )
    {
      v37 = GetMemLogObject();
      CMemoryLog::Write(v37, -2147217402);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
      }
      v38 = CBasicObjectSink::Return(v10, -2147217402, 0);
      (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v34 + 16LL))(v34);
      v64 = 0;
      if ( v25 )
        ((void (__fastcall *)(struct IWbemClassObject *))v25->lpVtbl->Release)(v25);
      v62 = 0;
LABEL_65:
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v61 = 0;
      v69 = 0;
      return v38;
    }
    v68 = v36;
    if ( (_DWORD)v75 )
    {
      v76 |= 0x10000u;
    }
    else if ( !CWbemNamespace::InnerAllowedWithSD(
                 this,
                 (CWbemNamespace *)((char *)this + 216),
                 0x10u,
                 L"Delete (DeleteClass)",
                 a2,
                 v60[0],
                 1) )
    {
      v45 = GetMemLogObject();
      v41 = -2147217405;
      CMemoryLog::Write(v45, -2147217405);
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_84;
      }
      v43 = 73;
      v44 = 2147749891LL;
      goto LABEL_83;
    }
    v39 = (*(__int64 (__fastcall **)(__int64, BSTR, _QWORD, struct IWbemContext *, struct CSynchronousSink *))(*(_QWORD *)v67 + 88LL))(
            v67,
            bstrString,
            v76,
            v77,
            v34);
    LODWORD(v65) = v39;
    if ( v39 >= 0 || v39 == -2147217406 || v39 == -2147217389 )
    {
      CSynchronousSink::Block(v34);
      CInCritSec::CInCritSec((CInCritSec *)v74, (struct _RTL_CRITICAL_SECTION *)v34 + 4);
      v46 = *((_DWORD *)v34 + 8);
      v47 = (struct IWbemClassObject *)*((_QWORD *)v73 + 6);
      v65 = v47;
      if ( v47 )
        ((void (__fastcall *)(struct IWbemClassObject *))v47->lpVtbl->AddRef)(v47);
      CInCritSec::~CInCritSec((CInCritSec *)v74);
      v71 = v65;
      if ( v46 < 0 && (!(_DWORD)v75 || v46 != -2147217389) )
      {
        CBasicObjectSink::Return(v10, v46, v65);
        v48 = GetMemLogObject();
        CMemoryLog::Write(v48, v46);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            75,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v46);
        }
        CReleaseMe::release((CReleaseMe *)&v71);
        CSysFreeMe::~CSysFreeMe(&v68);
        CReleaseMe::release((CReleaseMe *)&v64);
        CReleaseMe::release((CReleaseMe *)&v62);
        CReleaseMe::release((CReleaseMe *)&v61);
        v19 = v46;
        goto LABEL_122;
      }
      v49 = v63;
      if ( v63 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *))(*(_QWORD *)v63 + 40LL))(
          v63,
          8,
          v76,
          v77,
          0,
          *((_QWORD *)this + 12),
          a2);
        v49 = v63;
      }
      if ( (_DWORD)v75 )
      {
        VariantInit(&pvarg);
        v50 = v77;
        if ( ((int (__fastcall *)(struct IWbemContext *, const wchar_t *, _QWORD, VARIANTARG *))v77->lpVtbl->GetValue)(
               v77,
               L"__GroupOperationId",
               0,
               &pvarg) >= 0 )
        {
          v51 = CWbemNamespace::IsLocalMachine(*((wchar_t **)this + 35));
          CPublishWMIOperationEvent::PublishRepDelete(
            pvarg.cyVal.Lo,
            a2,
            v50,
            *((_DWORD *)this + 76),
            *((unsigned __int16 **)this + 36),
            *((_QWORD *)this + 37),
            v51);
        }
        v46 = CRepository::DeleteByPath(
                *((struct IWmiDbSession **)this + 5),
                *((struct IWmiDbHandle **)this + 7),
                a2,
                v76);
        _variant_t::~_variant_t(&pvarg);
        v49 = v63;
      }
      if ( v49 )
        (*(void (__fastcall **)(__int64, __int64, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *, _QWORD))(*(_QWORD *)v49 + 48LL))(
          v49,
          8,
          (unsigned int)v46,
          v77,
          0,
          *((_QWORD *)this + 12),
          a2,
          0);
      if ( v46 < 0 )
      {
        v52 = GetMemLogObject();
        CMemoryLog::Write(v52, v46);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            76,
            WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
            (unsigned int)v46);
        }
      }
      v38 = CBasicObjectSink::Return(v10, v46, 0);
      if ( v65 )
        ((void (__fastcall *)(struct IWbemClassObject *))v65->lpVtbl->Release)(v65);
      v71 = 0;
      SysFreeString(bstrString);
      (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v73 + 16LL))(v73);
      v64 = 0;
      if ( v25 )
        ((void (__fastcall *)(struct IWbemClassObject *))v25->lpVtbl->Release)(v25);
      v62 = 0;
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      v61 = 0;
      v69 = 0;
      return v38;
    }
    v40 = GetMemLogObject();
    v41 = (unsigned int)v65;
    CMemoryLog::Write(v40, (_DWORD)v65);
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_84:
      v19 = CBasicObjectSink::Return(v10, v41, 0);
      CSysFreeMe::~CSysFreeMe(&v68);
      CReleaseMe::release((CReleaseMe *)&v64);
      goto LABEL_44;
    }
    v43 = 74;
    v44 = v41;
LABEL_83:
    WPP_SF_d(*((_QWORD *)v42 + 2), v43, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v44);
    goto LABEL_84;
  }
  v11 = GetMemLogObject();
  First_ms_XXX_Locale = -2147217386;
  CMemoryLog::Write(v11, -2147217386);
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    return CBasicObjectSink::Return(v10, First_ms_XXX_Locale, 0);
  }
  v14 = 63;
  v15 = 2147749910LL;
LABEL_140:
  WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v15);
  return CBasicObjectSink::Return(v10, First_ms_XXX_Locale, 0);
}

```

## disassembly

```asm
0x18004d684  mov     rax, rsp
0x18004d687  mov     [rax+8], rbx
0x18004d68b  mov     [rax+20h], r9
0x18004d68f  mov     [rax+18h], r8d
0x18004d693  push    rbp
0x18004d694  push    rsi
0x18004d695  push    rdi
0x18004d696  push    r12
0x18004d698  push    r13
0x18004d69a  push    r14
0x18004d69c  push    r15
0x18004d69e  lea     rbp, [rax-57h]
0x18004d6a2  sub     rsp, 0E0h
0x18004d6a9  mov     r12, r9
0x18004d6ac  mov     esi, r8d
0x18004d6af  mov     r13, rdx
0x18004d6b2  mov     r14, rcx
0x18004d6b5  xor     edi, edi
0x18004d6b7  lea     rax, WPP_GLOBAL_Control
0x18004d6be  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d6c5  cmp     rcx, rax
0x18004d6c8  jz      short loc_18004D6EC
0x18004d6ca  test    byte ptr [rcx+1Ch], 1
0x18004d6ce  jz      short loc_18004D6EC
0x18004d6d0  cmp     byte ptr [rcx+19h], 5
0x18004d6d4  jb      short loc_18004D6EC
0x18004d6d6  lea     edx, [rdi+3Dh]
0x18004d6d9  mov     r9, r13
0x18004d6dc  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004d6e3  mov     rcx, [rcx+10h]
0x18004d6e7  call    WPP_SF_S
0x18004d6ec  mov     rbx, rdi
0x18004d6ef  mov     [rbp+4Fh+var_90], rbx
0x18004d6f3  mov     [rbp+4Fh+var_98], rdi
0x18004d6f7  mov     r15, [rbp+4Fh+arg_20]
0x18004d6fb  test    r13, r13
0x18004d6fe  jz      loc_18004E232
0x18004d704  test    r15, r15
0x18004d707  jz      loc_18004E232
0x18004d70d  cmp     word ptr [r13+0], 5Fh ; '_'
0x18004d713  jnz     short loc_18004D766
0x18004d715  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d71b  mov     ebx, 80041016h
0x18004d720  mov     edx, ebx
0x18004d722  mov     rcx, rax
0x18004d725  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d72b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d732  lea     rax, WPP_GLOBAL_Control
0x18004d739  cmp     rcx, rax
0x18004d73c  jz      loc_18004E282
0x18004d742  test    byte ptr [rcx+1Ch], 1
0x18004d746  jz      loc_18004E282
0x18004d74c  cmp     byte ptr [rcx+19h], 2
0x18004d750  jb      loc_18004E282
0x18004d756  mov     edx, 3Fh ; '?'
0x18004d75b  mov     r9d, 80041016h
0x18004d761  jmp     loc_18004E272
0x18004d766  cmp     [r14+108h], edi
0x18004d76d  jnz     loc_18004D8BB
0x18004d773  cmp     [r14+0F8h], rdi
0x18004d77a  jz      loc_18004D8BB
0x18004d780  mov     [rbp+4Fh+arg_8], rdi
0x18004d784  lea     rcx, [r14+0B0h]
0x18004d78b  lea     rdx, [rbp+4Fh+arg_8]
0x18004d78f  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x18004d795  mov     ebx, eax
0x18004d797  test    eax, eax
0x18004d799  jns     short loc_18004D7E4
0x18004d79b  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d7a1  mov     edx, ebx
0x18004d7a3  mov     rcx, rax
0x18004d7a6  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d7ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d7b3  lea     rax, WPP_GLOBAL_Control
0x18004d7ba  cmp     rcx, rax
0x18004d7bd  jz      loc_18004E282
0x18004d7c3  test    byte ptr [rcx+1Ch], 1
0x18004d7c7  jz      loc_18004E282
0x18004d7cd  cmp     byte ptr [rcx+19h], 2
0x18004d7d1  jb      loc_18004E282
0x18004d7d7  mov     edx, 40h ; '@'
0x18004d7dc  mov     r9d, ebx
0x18004d7df  jmp     loc_18004E272
0x18004d7e4  mov     r8, [rbp+4Fh+arg_8]
0x18004d7e8  mov     rdx, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18004d7ef  lea     rcx, [rbp+4Fh+pvarg]
0x18004d7f3  call    ??$MakeGuard@P6AHPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAG@@P6AHPEAX@ZPEAG@Z; MakeGuard<int (*)(void *),ushort *>(int (*)(void *),ushort *)
0x18004d7f8  nop
0x18004d7f9  mov     rcx, [r14+0F8h]
0x18004d800  mov     rax, [rcx]
0x18004d803  lea     rdx, [rbp+4Fh+var_90]
0x18004d807  mov     [rsp+40h], rdx
0x18004d80c  lea     rdx, IID_IWbemServices
0x18004d813  mov     [rsp+110h+var_D8], rdx
0x18004d818  mov     qword ptr [rsp+110h+var_E0], rdi
0x18004d81d  mov     rdx, [r14+60h]
0x18004d821  mov     qword ptr [rsp+110h+var_E8], rdx; bool
0x18004d826  mov     rdx, [rbp+4Fh+arg_8]
0x18004d82a  mov     [rsp+110h+var_F0], rdx
0x18004d82f  mov     r9, [r14+70h]
0x18004d833  mov     r8, r12
0x18004d836  xor     edx, edx
0x18004d838  mov     rax, [rax+20h]
0x18004d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d841  mov     ebx, eax
0x18004d843  test    eax, eax
0x18004d845  jns     short loc_18004D8AE
0x18004d847  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d84d  mov     edx, ebx
0x18004d84f  mov     rcx, rax
0x18004d852  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d858  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d85f  lea     rax, WPP_GLOBAL_Control
0x18004d866  cmp     rcx, rax
0x18004d869  jz      short loc_18004D88F
0x18004d86b  test    byte ptr [rcx+1Ch], 1
0x18004d86f  jz      short loc_18004D88F
0x18004d871  cmp     byte ptr [rcx+19h], 2
0x18004d875  jb      short loc_18004D88F
0x18004d877  mov     edx, 41h ; 'A'
0x18004d87c  mov     r9d, ebx
0x18004d87f  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004d886  mov     rcx, [rcx+10h]
0x18004d88a  call    WPP_SF_d
0x18004d88f  xor     r8d, r8d; struct IWbemClassObject *
0x18004d892  mov     edx, ebx; int
0x18004d894  mov     rcx, r15; this
0x18004d897  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x18004d89c  mov     ebx, eax
0x18004d89e  lea     rcx, [rbp+4Fh+pvarg]
0x18004d8a2  call    ??1?$ScopeGuardImpl1@P6AHPEAUAUTHZ_AUDIT_EVENT_HANDLE__@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(void)
0x18004d8a7  mov     eax, ebx
0x18004d8a9  jmp     loc_18004E28F
0x18004d8ae  lea     rcx, [rbp+4Fh+pvarg]
0x18004d8b2  call    ??1?$ScopeGuardImpl1@P6AHPEAUAUTHZ_AUDIT_EVENT_HANDLE__@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>(void)
0x18004d8b7  mov     rbx, [rbp+4Fh+var_90]
0x18004d8bb  mov     [rbp+4Fh+var_80], rbx
0x18004d8bf  mov     [rbp+4Fh+var_B0], rdi
0x18004d8c3  mov     rcx, [r14+100h]
0x18004d8ca  mov     rax, [rcx]
0x18004d8cd  lea     rdx, [rbp+4Fh+var_B0]
0x18004d8d1  mov     rax, [rax+0E0h]
0x18004d8d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d8dd  mov     edi, eax
0x18004d8df  test    eax, eax
0x18004d8e1  jns     short loc_18004D93F
0x18004d8e3  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d8e9  mov     edx, edi
0x18004d8eb  mov     rcx, rax
0x18004d8ee  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d8fb  lea     rax, WPP_GLOBAL_Control
0x18004d902  cmp     rcx, rax
0x18004d905  jz      short loc_18004D92B
0x18004d907  test    byte ptr [rcx+1Ch], 1
0x18004d90b  jz      short loc_18004D92B
0x18004d90d  cmp     byte ptr [rcx+19h], 2
0x18004d911  jb      short loc_18004D92B
0x18004d913  mov     edx, 42h ; 'B'
0x18004d918  mov     r9d, edi
0x18004d91b  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004d922  mov     rcx, [rcx+10h]
0x18004d926  call    WPP_SF_d
0x18004d92b  xor     r8d, r8d; struct IWbemClassObject *
0x18004d92e  mov     edx, edi; int
0x18004d930  mov     rcx, r15; this
0x18004d933  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x18004d938  mov     ebx, eax
0x18004d93a  jmp     loc_18004E0B4
0x18004d93f  mov     rdi, [rbp+4Fh+var_B0]
0x18004d943  mov     [rbp+4Fh+var_C0], rdi
0x18004d947  cmp     dword ptr [r14+108h], 0
0x18004d94f  jnz     loc_18004E021
0x18004d955  cmp     qword ptr [r14+0F8h], 0
0x18004d95d  jz      loc_18004E021
0x18004d963  lea     rax, [rbp+4Fh+var_98]
0x18004d967  mov     [rsp+110h+var_F0], rax; struct IWbemClassObject **
0x18004d96c  xor     r9d, r9d; unsigned int
0x18004d96f  mov     r8, r13; unsigned __int16 *
0x18004d972  mov     rdx, [r14+38h]; struct IWmiDbHandle *
0x18004d976  mov     rcx, [r14+28h]; struct IWmiDbSession *
0x18004d97a  call    ?GetObjectW@CRepository@@SAJPEAUIWmiDbSession@@PEAUIWmiDbHandle@@PEBGKPEAPEAUIWbemClassObject@@@Z; CRepository::GetObjectW(IWmiDbSession *,IWmiDbHandle *,ushort const *,ulong,IWbemClassObject * *)
0x18004d97f  mov     rsi, [rbp+4Fh+var_98]
0x18004d983  mov     [rbp+4Fh+var_B8], rsi
0x18004d987  test    eax, eax
0x18004d989  js      loc_18004DA76
0x18004d98f  mov     [rsp+110h+var_E0], 1; bool
0x18004d994  mov     [rsp+110h+var_F0], r13; unsigned __int16 *
0x18004d999  lea     r9, aDeleteDeletecl; "Delete (DeleteClass)"
0x18004d9a0  mov     r8d, 4; unsigned int
0x18004d9a6  lea     rdx, [r14+0D8h]; struct CNtSecurityDescriptor *
0x18004d9ad  mov     rcx, r14; this
0x18004d9b0  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18004d9b5  test    al, al
0x18004d9b7  jnz     short loc_18004DA26
0x18004d9b9  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004d9bf  mov     ebx, 80041003h
0x18004d9c4  mov     edx, ebx
0x18004d9c6  mov     rcx, rax
0x18004d9c9  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004d9cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d9d6  lea     rax, WPP_GLOBAL_Control
0x18004d9dd  cmp     rcx, rax
0x18004d9e0  jz      short loc_18004DA09
0x18004d9e2  test    byte ptr [rcx+1Ch], 1
0x18004d9e6  jz      short loc_18004DA09
0x18004d9e8  cmp     byte ptr [rcx+19h], 2
0x18004d9ec  jb      short loc_18004DA09
0x18004d9ee  mov     edx, 45h ; 'E'
0x18004d9f3  mov     r9d, 80041003h
0x18004d9f9  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004da00  mov     rcx, [rcx+10h]
0x18004da04  call    WPP_SF_d
0x18004da09  mov     edx, ebx; int
0x18004da0b  xor     r8d, r8d; struct IWbemClassObject *
0x18004da0e  mov     rcx, r15; this
0x18004da11  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x18004da16  mov     ebx, eax
0x18004da18  lea     rcx, [rbp+4Fh+var_B8]; this
0x18004da1c  call    ?release@CReleaseMe@@QEAAXXZ; CReleaseMe::release(void)
0x18004da21  jmp     loc_18004E0AA
0x18004da26  mov     dword ptr [rbp+4Fh+arg_8], 1
0x18004da2d  cmp     [rbp+4Fh+var_98], 0
0x18004da32  jnz     short loc_18004DA7D
0x18004da34  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004da3a  mov     ebx, 8004100Ah
0x18004da3f  mov     edx, ebx
0x18004da41  mov     rcx, rax
0x18004da44  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004da4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004da51  lea     rax, WPP_GLOBAL_Control
0x18004da58  cmp     rcx, rax
0x18004da5b  jz      short loc_18004DA09
0x18004da5d  test    byte ptr [rcx+1Ch], 1
0x18004da61  jz      short loc_18004DA09
0x18004da63  cmp     byte ptr [rcx+19h], 2
0x18004da67  jb      short loc_18004DA09
0x18004da69  mov     edx, 46h ; 'F'
0x18004da6e  mov     r9d, 8004100Ah
0x18004da74  jmp     short loc_18004D9F9
0x18004da76  mov     dword ptr [rbp+4Fh+arg_8], 0
0x18004da7d  xor     ecx, ecx; struct IWbemObjectSinkEx *
0x18004da7f  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18004da84  mov     r12, rax
0x18004da87  mov     [rbp+4Fh+var_50], rax
0x18004da8b  test    rax, rax
0x18004da8e  jnz     short loc_18004DAEA
0x18004da90  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004da96  mov     r14d, 80041006h
0x18004da9c  mov     edx, r14d
0x18004da9f  mov     rcx, rax
0x18004daa2  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004daa8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004daaf  lea     rax, WPP_GLOBAL_Control
0x18004dab6  cmp     rcx, rax
0x18004dab9  jz      short loc_18004DAE2
0x18004dabb  test    byte ptr [rcx+1Ch], 1
0x18004dabf  jz      short loc_18004DAE2
0x18004dac1  cmp     byte ptr [rcx+19h], 2
0x18004dac5  jb      short loc_18004DAE2
0x18004dac7  lea     edx, [r12+47h]
0x18004dacc  mov     r9d, 80041006h
0x18004dad2  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004dad9  mov     rcx, [rcx+10h]
0x18004dadd  call    WPP_SF_d
0x18004dae2  mov     edx, r14d
0x18004dae5  jmp     loc_18004DA0B
0x18004daea  mov     rax, [rax]
0x18004daed  mov     rcx, r12
0x18004daf0  mov     rax, [rax+8]
0x18004daf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daf9  mov     [rbp+4Fh+var_A8], r12
0x18004dafd  mov     rcx, r13; psz
0x18004db00  call    cs:__imp_SysAllocString
0x18004db06  mov     [rbp+4Fh+bstrString], rax
0x18004db0a  test    rax, rax
0x18004db0d  jnz     loc_18004DBDD
0x18004db13  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004db19  mov     r14d, 80041006h
0x18004db1f  mov     edx, r14d
0x18004db22  mov     rcx, rax
0x18004db25  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18004db2b  mov     rcx, cs:WPP_GLOBAL_Control
0x18004db32  lea     rax, WPP_GLOBAL_Control
0x18004db39  cmp     rcx, rax
0x18004db3c  jz      short loc_18004DB65
0x18004db3e  test    byte ptr [rcx+1Ch], 1
0x18004db42  jz      short loc_18004DB65
0x18004db44  cmp     byte ptr [rcx+19h], 2
0x18004db48  jb      short loc_18004DB65
0x18004db4a  mov     edx, 48h ; 'H'
0x18004db4f  mov     r9d, 80041006h
0x18004db55  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18004db5c  mov     rcx, [rcx+10h]
0x18004db60  call    WPP_SF_d
0x18004db65  xor     r8d, r8d; struct IWbemClassObject *
0x18004db68  mov     edx, r14d; int
0x18004db6b  mov     rcx, r15; this
0x18004db6e  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x18004db73  mov     r14d, eax
  ... truncated ...
```
