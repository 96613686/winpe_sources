# CWbemNamespace::PutInstanceDynamicClass(CWbemInstance *,CWbemClass *,long,IWbemContext *,CBasicObjectSink *,int &,ushort const *)

- ea: `0x18005cc60`
- end: `0x18005d474`
- name: `?PutInstanceDynamicClass@CWbemNamespace@@IEAAJPEAVCWbemInstance@@PEAVCWbemClass@@JPEAUIWbemContext@@PEAVCBasicObjectSink@@AEAHPEBG@Z`
- size: `2068`
- prototype: `__int64 __usercall@<rax>(CWbemNamespace *__hidden this@<rcx>, struct CWbemInstance *@<rdx>, struct CWbemClass *@<r8>, int@<r9d>, struct IWbemContext *, struct CBasicObjectSink *, int *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180049d34`

## callees

- `0x18000b140`
- `0x18000b1dc`
- `0x18001307c`
- `0x18001f6d0`
- `0x18002fee4`
- `0x180039f68`
- `0x18003be20`
- `0x18003cdb8`
- `0x18003cfe0`
- `0x18003d010`
- `0x180056620`
- `0x18005cc60`
- `0x18005d98c`
- `0x18005edf4`
- `0x1800a2c68`
- `0x1800da010`

## import_xrefs

- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18005cd84`
- `wbemcomn!?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z` at `0x18005cd84`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18005cdbb`
- `wbemcomn!??BCVar@@QEAAPEAGXZ` at `0x18005cdbb`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x18005cd98`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18005ccbd`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18005ccbd`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18005ccfb`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18005ccfb`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18005d374`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18005d374`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005cf7d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005d02c`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005cf7d`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18005d02c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18005cfb4`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18005cfb4`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005ce6b`
- `wbemcomn!??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z` at `0x18005ce6b`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005ce93`
- `wbemcomn!??1CInCritSec@@QEAA@XZ` at `0x18005ce93`
- `wbemcomn!GetMemLogObject` at `0x18005d066`
- `wbemcomn!GetMemLogObject` at `0x18005d0b0`
- `wbemcomn!GetMemLogObject` at `0x18005d108`
- `wbemcomn!GetMemLogObject` at `0x18005d1e4`
- `wbemcomn!GetMemLogObject` at `0x18005d225`
- `wbemcomn!GetMemLogObject` at `0x18005d27e`
- `wbemcomn!GetMemLogObject` at `0x18005d2fc`
- `wbemcomn!GetMemLogObject` at `0x18005d38c`
- `wbemcomn!GetMemLogObject` at `0x18005d419`
- `wbemcomn!GetMemLogObject` at `0x18005d066`
- `wbemcomn!GetMemLogObject` at `0x18005d0b0`
- `wbemcomn!GetMemLogObject` at `0x18005d108`
- `wbemcomn!GetMemLogObject` at `0x18005d1e4`
- `wbemcomn!GetMemLogObject` at `0x18005d225`
- `wbemcomn!GetMemLogObject` at `0x18005d27e`
- `wbemcomn!GetMemLogObject` at `0x18005d2fc`
- `wbemcomn!GetMemLogObject` at `0x18005d38c`
- `wbemcomn!GetMemLogObject` at `0x18005d419`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d076`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d0c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d118`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d1ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d230`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d289`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d30c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d397`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d429`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d076`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d0c0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d118`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d1ef`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d230`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d289`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d30c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d397`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18005d429`
- `OLEAUT32!__imp_SysAllocString` at `0x18005ce79`
- `OLEAUT32!__imp_SysAllocString` at `0x18005cfa8`
- `OLEAUT32!__imp_SysAllocString` at `0x18005ce79`
- `OLEAUT32!__imp_SysAllocString` at `0x18005cfa8`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf17`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf41`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf17`
- `OLEAUT32!__imp_SysFreeString` at `0x18005cf41`

## string_xrefs

- `0x18005cd1b`: `Write (PutInstance)`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CWbemNamespace::PutInstanceDynamicClass(
        CWbemNamespace *this,
        struct CWbemInstance *a2,
        struct CWbemClass *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        struct IWbemObjectSinkEx *a6,
        int *a7,
        unsigned __int16 *a8)
{
  const unsigned __int16 *v12; // rdi
  CBasicObjectSink *v13; // r14
  struct CSynchronousSink *v14; // rax
  struct CSynchronousSink *v15; // rsi
  int First_ms_XXX_Locale; // ebx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, __int64, GUID *, __int64 *); // rbx
  __int64 v19; // rax
  int v20; // ebx
  __int64 v21; // rbx
  int v22; // edi
  OLECHAR *v23; // r13
  unsigned int v24; // edi
  OLECHAR *v25; // r12
  struct IWbemClassObject *v26; // r15
  const OLECHAR *v27; // rax
  OLECHAR *v28; // rsi
  unsigned int v30; // ebx
  CMemoryLog *v31; // rax
  int v32; // ebx
  CClientCnt *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  CMemoryLog *v36; // rax
  CBasicObjectSink *v37; // rcx
  CMemoryLog *v38; // rax
  CClientCnt *v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r9
  CMemoryLog *v42; // rax
  CMemoryLog *v43; // rax
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  const unsigned __int16 *LPWSTR; // rax
  CMemoryLog *v47; // rax
  CMemoryLog *MemLogObject; // rax
  bool v49; // [rsp+30h] [rbp-C1h]
  struct IWbemClassObject *v50; // [rsp+68h] [rbp-89h] BYREF
  __int64 v51; // [rsp+70h] [rbp-81h] BYREF
  OLECHAR *v52[2]; // [rsp+78h] [rbp-79h] BYREF
  __int128 v53; // [rsp+88h] [rbp-69h] BYREF
  unsigned __int16 *v54; // [rsp+98h] [rbp-59h] BYREF
  __int64 v55; // [rsp+A0h] [rbp-51h] BYREF
  char v56[8]; // [rsp+A8h] [rbp-49h] BYREF
  void (__fastcall *v57)(__int64); // [rsp+B0h] [rbp-41h]
  __int64 v58; // [rsp+B8h] [rbp-39h]
  _BYTE v59[48]; // [rsp+C8h] [rbp-29h] BYREF
  struct CSynchronousSink *v61; // [rsp+148h] [rbp+57h] BYREF

  v12 = a8;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_qqS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      (unsigned int)WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
      (_DWORD)a2,
      (char)a3,
      (__int64)a8);
  }
  CVar::CVar((CVar *)v59);
  if ( (*(int (__fastcall **)(struct CWbemClass *, const wchar_t *, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a3 + 976LL))(
         a3,
         L"Provider",
         v59,
         0,
         0) < 0
    || CVar::GetType((CVar *)v59) != 8 )
  {
    MemLogObject = GetMemLogObject();
    v32 = -2147217390;
    CMemoryLog::Write(MemLogObject, -2147217390);
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v34 = 123;
    v35 = 2147749906LL;
    goto LABEL_82;
  }
  if ( !CWbemNamespace::InnerAllowedWithSD(
          this,
          (CWbemNamespace *)((char *)this + 216),
          0x10u,
          L"Write (PutInstance)",
          v12,
          v49,
          1) )
  {
    v31 = GetMemLogObject();
    v32 = -2147217405;
    CMemoryLog::Write(v31, -2147217405);
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_83;
    }
    v34 = 124;
    v35 = 2147749891LL;
LABEL_82:
    WPP_SF_d(*((_QWORD *)v33 + 2), v34, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v35);
LABEL_83:
    v37 = (CBasicObjectSink *)a6;
LABEL_84:
    v30 = CBasicObjectSink::Return(v37, v32, 0);
    goto LABEL_32;
  }
  v13 = (CBasicObjectSink *)a6;
  v14 = CSynchronousSink::Create(a6);
  v15 = v14;
  if ( !v14 )
  {
    v36 = GetMemLogObject();
    v32 = -2147217402;
    CMemoryLog::Write(v36, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 125, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    v37 = v13;
    goto LABEL_84;
  }
  (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v14 + 8LL))(v14);
  v61 = v15;
  v55 = 0;
  if ( !*((_QWORD *)this + 31) )
  {
    v38 = GetMemLogObject();
    First_ms_XXX_Locale = -2147217398;
    CMemoryLog::Write(v38, -2147217398);
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v40 = 126;
    v41 = 2147749898LL;
    goto LABEL_48;
  }
  v54 = 0;
  First_ms_XXX_Locale = CMUILocaleList::GetFirst_ms_XXX_Locale((CWbemNamespace *)((char *)this + 176), &v54);
  if ( First_ms_XXX_Locale < 0 )
  {
    v42 = GetMemLogObject();
    CMemoryLog::Write(v42, First_ms_XXX_Locale);
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_49;
    }
    v40 = 127;
    v41 = (unsigned int)First_ms_XXX_Locale;
LABEL_48:
    WPP_SF_d(*((_QWORD *)v39 + 2), v40, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v41);
LABEL_49:
    v30 = CBasicObjectSink::Return(v13, First_ms_XXX_Locale, 0);
LABEL_52:
    CReleaseMe::release((CReleaseMe *)&v61);
LABEL_32:
    CVar::~CVar((CVar *)v59);
    return v30;
  }
  MakeGuard<int (*)(void *),unsigned short *>(v56, CMUILocale::_Free, v54);
  v17 = *((_QWORD *)this + 31);
  v18 = *(__int64 (__fastcall **)(__int64, __int128 *, _QWORD, struct IWbemContext *, _QWORD, _QWORD, unsigned __int16 *, _QWORD, __int64, GUID *, __int64 *))(*(_QWORD *)v17 + 40LL);
  v19 = CVar::operator unsigned short *(v59);
  v53 = 0;
  v20 = v18(v17, &v53, 0, a5, 0, *((_QWORD *)this + 14), v54, 0, v19, &IID_IWbemServices, &v55);
  if ( v20 < 0 )
  {
    v43 = GetMemLogObject();
    CMemoryLog::Write(v43, v20);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        128,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v20);
    }
    v30 = CBasicObjectSink::Return(v13, v20, 0);
    if ( !v56[0] )
      v57(v58);
    (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v15 + 16LL))(v15);
    v61 = 0;
    goto LABEL_32;
  }
  v21 = v55;
  v51 = v55;
  v22 = (*(__int64 (__fastcall **)(__int64, struct CWbemInstance *, _QWORD, struct IWbemContext *, struct CSynchronousSink *))(*(_QWORD *)v55 + 120LL))(
          v55,
          a2,
          a4,
          a5,
          v15);
  v23 = 0;
  if ( v22 < 0 )
  {
    v44 = GetMemLogObject();
    CMemoryLog::Write(v44, v22);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        129,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)v22);
    }
    v50 = 0;
    CSynchronousSink::GetStatus(v15, 0, 0, &v50);
    v52[0] = (OLECHAR *)v50;
    v30 = CBasicObjectSink::Return(v13, v22, v50);
    CReleaseMe::release((CReleaseMe *)v52);
LABEL_51:
    CReleaseMe::release((CReleaseMe *)&v51);
    ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v56);
    goto LABEL_52;
  }
  CSynchronousSink::Block(v15);
  CInCritSec::CInCritSec((CInCritSec *)&v53, (struct _RTL_CRITICAL_SECTION *)v15 + 4);
  v24 = *((_DWORD *)v15 + 8);
  v25 = SysAllocString(*((const OLECHAR **)v15 + 5));
  v26 = (struct IWbemClassObject *)*((_QWORD *)v15 + 6);
  if ( v26 )
    ((void (__fastcall *)(_QWORD))v26->lpVtbl->AddRef)(*((_QWORD *)v15 + 6));
  CInCritSec::~CInCritSec((CInCritSec *)&v53);
  v52[0] = v25;
  v50 = v26;
  (*(void (__fastcall **)(struct CSynchronousSink *))(*(_QWORD *)v15 + 16LL))(v15);
  v61 = 0;
  if ( !*a7 && v24 == -2147217372 )
  {
    v24 = 0;
    goto LABEL_15;
  }
  if ( (v24 & 0x80000000) != 0 )
  {
    COperationError::COperationError((COperationError *)&v53, v13, L"PutInstance", (unsigned __int16 *)&psz, 1);
    if ( (_BYTE)v53 )
    {
      LPWSTR = CVar::GetLPWSTR((CVar *)v59);
      COperationError::ProviderReturned((COperationError *)&v53, LPWSTR, v24, v26);
      v47 = GetMemLogObject();
      CMemoryLog::Write(v47, v24);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 131, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, v24);
      }
      COperationError::~COperationError((COperationError *)&v53);
      CReleaseMe::release((CReleaseMe *)&v50);
      CSysFreeMe::~CSysFreeMe(v52);
      CReleaseMe::release((CReleaseMe *)&v51);
      ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v56);
      CReleaseMe::release((CReleaseMe *)&v61);
      v30 = v24;
      goto LABEL_32;
    }
    v45 = GetMemLogObject();
    v30 = -2147217402;
    CMemoryLog::Write(v45, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids, 2147749894LL);
    }
    COperationError::~COperationError((COperationError *)&v53);
    CReleaseMe::release((CReleaseMe *)&v50);
    CSysFreeMe::~CSysFreeMe(v52);
    goto LABEL_51;
  }
LABEL_15:
  if ( v25 )
  {
    (*(void (__fastcall **)(CBasicObjectSink *, _QWORD, _QWORD, OLECHAR *, _QWORD))(*(_QWORD *)v13 + 32LL))(
      v13,
      0,
      v24,
      v25,
      0);
  }
  else
  {
    v27 = (const OLECHAR *)(*(__int64 (__fastcall **)(struct CWbemInstance *, _QWORD))(*(_QWORD *)a2 + 1040LL))(a2, 0);
    v28 = (OLECHAR *)v27;
    if ( v27 )
    {
      v23 = SysAllocString(v27);
      CWin32DefaultArena::WbemMemFree(v28);
    }
    (*(void (__fastcall **)(CBasicObjectSink *, _QWORD, _QWORD, OLECHAR *, _QWORD))(*(_QWORD *)v13 + 32LL))(
      v13,
      0,
      v24,
      v23,
      0);
    SysFreeString(v23);
  }
  if ( v26 )
    ((void (__fastcall *)(struct IWbemClassObject *))v26->lpVtbl->Release)(v26);
  v50 = 0;
  if ( v25 )
    SysFreeString(v25);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v51 = 0;
  if ( !v56[0] )
    v57(v58);
  v61 = 0;
  CVar::~CVar((CVar *)v59);
  return 0;
}

```

## disassembly

```asm
0x18005cc60  mov     rax, rsp
0x18005cc63  mov     [rax+8], rbx
0x18005cc67  mov     [rax+10h], rdx
0x18005cc6b  push    rbp
0x18005cc6c  push    rsi
0x18005cc6d  push    rdi
0x18005cc6e  push    r12
0x18005cc70  push    r13
0x18005cc72  push    r14
0x18005cc74  push    r15
0x18005cc76  lea     rbp, [rax-3Fh]
0x18005cc7a  sub     rsp, 0F0h
0x18005cc81  movaps  xmmword ptr [rax-48h], xmm6
0x18005cc85  mov     r13d, r9d
0x18005cc88  mov     rbx, r8
0x18005cc8b  mov     r12, rdx
0x18005cc8e  mov     r15, rcx
0x18005cc91  lea     r14, WPP_GLOBAL_Control
0x18005cc98  lea     rsi, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18005cc9f  mov     rdi, [rbp+37h+arg_38]
0x18005cca3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005ccaa  cmp     rcx, r14
0x18005ccad  jz      short loc_18005CCB9
0x18005ccaf  test    byte ptr [rcx+1Ch], 1
0x18005ccb3  jnz     loc_18005D039
0x18005ccb9  lea     rcx, [rbp+37h+var_60]
0x18005ccbd  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18005ccc3  nop
0x18005ccc4  mov     rax, [rbx]
0x18005ccc7  mov     [rsp+120h+var_100], 0
0x18005ccd0  xor     r9d, r9d
0x18005ccd3  lea     r8, [rbp+37h+var_60]
0x18005ccd7  lea     rdx, aProvider_0; "Provider"
0x18005ccde  mov     rcx, rbx
0x18005cce1  mov     rax, [rax+3D0h]
0x18005cce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cced  xor     ebx, ebx
0x18005ccef  test    eax, eax
0x18005ccf1  js      loc_18005D419
0x18005ccf7  lea     rcx, [rbp+37h+var_60]
0x18005ccfb  call    cs:__imp_?GetType@CVar@@QEAAHXZ; CVar::GetType(void)
0x18005cd01  cmp     eax, 8
0x18005cd04  jnz     loc_18005D419
0x18005cd0a  lea     rdx, [r15+0D8h]; struct CNtSecurityDescriptor *
0x18005cd11  mov     [rsp+120h+var_F0], 1; bool
0x18005cd16  mov     [rsp+120h+var_100], rdi; unsigned __int16 *
0x18005cd1b  lea     r9, aWritePutinstan; "Write (PutInstance)"
0x18005cd22  lea     r8d, [rbx+10h]; unsigned int
0x18005cd26  mov     rcx, r15; this
0x18005cd29  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18005cd2e  test    al, al
0x18005cd30  jz      loc_18005D066
0x18005cd36  mov     r14, [rbp+37h+arg_28]
0x18005cd3a  mov     rcx, r14; struct IWbemObjectSinkEx *
0x18005cd3d  call    ?Create@CSynchronousSink@@SAPEAV1@PEAUIWbemObjectSinkEx@@@Z; CSynchronousSink::Create(IWbemObjectSinkEx *)
0x18005cd42  mov     rsi, rax
0x18005cd45  test    rax, rax
0x18005cd48  jz      loc_18005D0B0
0x18005cd4e  mov     rax, [rax]
0x18005cd51  mov     rcx, rsi
0x18005cd54  mov     rax, [rax+8]
0x18005cd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd5d  mov     [rbp+37h+arg_10], rsi
0x18005cd61  mov     [rbp+37h+var_88], rbx
0x18005cd65  cmp     [r15+0F8h], rbx
0x18005cd6c  jz      loc_18005D108
0x18005cd72  xorps   xmm6, xmm6
0x18005cd75  mov     [rbp+37h+var_90], rbx
0x18005cd79  lea     rcx, [r15+0B0h]
0x18005cd80  lea     rdx, [rbp+37h+var_90]
0x18005cd84  call    cs:__imp_?GetFirst_ms_XXX_Locale@CMUILocaleList@@QEAAJPEAPEAG@Z; CMUILocaleList::GetFirst_ms_XXX_Locale(ushort * *)
0x18005cd8a  mov     ebx, eax
0x18005cd8c  test    eax, eax
0x18005cd8e  js      loc_18005D1E4
0x18005cd94  mov     r8, [rbp+37h+var_90]
0x18005cd98  mov     rdx, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18005cd9f  lea     rcx, [rbp+37h+var_80]
0x18005cda3  call    ??$MakeGuard@P6AHPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAG@@P6AHPEAX@ZPEAG@Z; MakeGuard<int (*)(void *),ushort *>(int (*)(void *),ushort *)
0x18005cda8  nop
0x18005cda9  mov     rdi, [r15+0F8h]
0x18005cdb0  mov     rax, [rdi]
0x18005cdb3  mov     rbx, [rax+28h]
0x18005cdb7  lea     rcx, [rbp+37h+var_60]
0x18005cdbb  call    cs:__imp_??BCVar@@QEAAPEAGXZ; CVar::operator ushort *(void)
0x18005cdc1  movdqa  [rbp+37h+var_A0], xmm6
0x18005cdc6  lea     rcx, [rbp+37h+var_88]
0x18005cdca  mov     [rsp+120h+var_D0], rcx
0x18005cdcf  lea     rcx, IID_IWbemServices
0x18005cdd6  mov     [rsp+120h+var_D8], rcx
0x18005cddb  mov     [rsp+120h+var_E0], rax
0x18005cde0  mov     [rsp+120h+var_E8], 0
0x18005cde9  mov     rdx, [rbp+37h+var_90]
0x18005cded  mov     qword ptr [rsp+120h+var_F0], rdx
0x18005cdf2  mov     rdx, [r15+70h]
0x18005cdf6  mov     [rsp+120h+var_F8], rdx
0x18005cdfb  xor     r15d, r15d
0x18005cdfe  mov     [rsp+120h+var_100], r15
0x18005ce03  mov     r9, [rbp+37h+arg_20]
0x18005ce07  xor     r8d, r8d
0x18005ce0a  lea     rdx, [rbp+37h+var_A0]
0x18005ce0e  mov     rcx, rdi
0x18005ce11  mov     rax, rbx
0x18005ce14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce19  mov     ebx, eax
0x18005ce1b  test    eax, eax
0x18005ce1d  js      loc_18005D225
0x18005ce23  mov     rbx, [rbp+37h+var_88]
0x18005ce27  mov     [rsp+120h+var_B8], rbx
0x18005ce2c  mov     rcx, [rbp+37h+var_88]
0x18005ce30  mov     rax, [rcx]
0x18005ce33  mov     [rsp+120h+var_100], rsi
0x18005ce38  mov     r9, [rbp+37h+arg_20]
0x18005ce3c  mov     r8d, r13d
0x18005ce3f  mov     rdx, r12
0x18005ce42  mov     rax, [rax+78h]
0x18005ce46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ce4b  mov     edi, eax
0x18005ce4d  xor     r13d, r13d
0x18005ce50  test    eax, eax
0x18005ce52  js      loc_18005D27E
0x18005ce58  mov     rcx, rsi; this
0x18005ce5b  call    ?Block@CSynchronousSink@@QEAAXXZ; CSynchronousSink::Block(void)
0x18005ce60  lea     rdx, [rsi+0A0h]
0x18005ce67  lea     rcx, [rbp+37h+var_A0]
0x18005ce6b  call    cs:__imp_??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x18005ce71  nop
0x18005ce72  mov     edi, [rsi+20h]
0x18005ce75  mov     rcx, [rsi+28h]; psz
0x18005ce79  call    cs:__imp_SysAllocString
0x18005ce7f  mov     r12, rax
0x18005ce82  mov     r15, [rsi+30h]
0x18005ce86  test    r15, r15
0x18005ce89  jnz     loc_18005CFDE
0x18005ce8f  lea     rcx, [rbp+37h+var_A0]
0x18005ce93  call    cs:__imp_??1CInCritSec@@QEAA@XZ; CInCritSec::~CInCritSec(void)
0x18005ce99  mov     [rbp+37h+var_B0], r12
0x18005ce9d  mov     [rsp+120h+var_C0], r15
0x18005cea2  mov     rax, [rsi]
0x18005cea5  mov     rcx, rsi
0x18005cea8  mov     rax, [rax+10h]
0x18005ceac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005ceb1  mov     [rbp+37h+arg_10], r13
0x18005ceb5  mov     rax, [rbp+37h+arg_30]
0x18005ceb9  cmp     [rax], r13d
0x18005cebc  jz      loc_18005D2BF
0x18005cec2  test    edi, edi
0x18005cec4  js      loc_18005D2D3
0x18005ceca  xor     edx, edx
0x18005cecc  test    r12, r12
0x18005cecf  jnz     loc_18005CFBF
0x18005ced5  mov     rcx, [rbp+37h+arg_8]
0x18005ced9  mov     rax, [rcx]
0x18005cedc  mov     rax, [rax+410h]
0x18005cee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cee8  mov     rsi, rax
0x18005ceeb  test    rax, rax
0x18005ceee  jnz     loc_18005CFA5
0x18005cef4  mov     rcx, [r14]
0x18005cef7  mov     rax, [rcx+20h]
0x18005cefb  mov     [rsp+120h+var_100], 0
0x18005cf04  mov     r9, r13
0x18005cf07  mov     r8d, edi
0x18005cf0a  xor     edx, edx
0x18005cf0c  mov     rcx, r14
0x18005cf0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf14  mov     rcx, r13; bstrString
0x18005cf17  call    cs:__imp_SysFreeString
0x18005cf1d  xor     r13d, r13d
0x18005cf20  test    r15, r15
0x18005cf23  jz      short loc_18005CF34
0x18005cf25  mov     rax, [r15]
0x18005cf28  mov     rcx, r15
0x18005cf2b  mov     rax, [rax+10h]
0x18005cf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf34  mov     [rsp+120h+var_C0], r13
0x18005cf39  test    r12, r12
0x18005cf3c  jz      short loc_18005CF48
0x18005cf3e  mov     rcx, r12; bstrString
0x18005cf41  call    cs:__imp_SysFreeString
0x18005cf47  nop
0x18005cf48  test    rbx, rbx
0x18005cf4b  jz      short loc_18005CF5C
0x18005cf4d  mov     rax, [rbx]
0x18005cf50  mov     rcx, rbx
0x18005cf53  mov     rax, [rax+10h]
0x18005cf57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf5c  mov     [rsp+120h+var_B8], r13
0x18005cf61  cmp     [rbp+37h+var_80], r13b
0x18005cf65  jnz     short loc_18005CF75
0x18005cf67  mov     rcx, [rbp+37h+var_70]
0x18005cf6b  mov     rax, [rbp+37h+var_78]
0x18005cf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cf74  nop
0x18005cf75  mov     [rbp+37h+arg_10], r13
0x18005cf79  lea     rcx, [rbp+37h+var_60]
0x18005cf7d  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18005cf83  xor     eax, eax
0x18005cf85  lea     r11, [rsp+120h+var_30]
0x18005cf8d  mov     rbx, [r11+40h]
0x18005cf91  movaps  xmm6, xmmword ptr [r11-10h]
0x18005cf96  mov     rsp, r11
0x18005cf99  pop     r15
0x18005cf9b  pop     r14
0x18005cf9d  pop     r13
0x18005cf9f  pop     r12
0x18005cfa1  pop     rdi
0x18005cfa2  pop     rsi
0x18005cfa3  pop     rbp
0x18005cfa4  retn
0x18005cfa5  mov     rcx, rsi; psz
0x18005cfa8  call    cs:__imp_SysAllocString
0x18005cfae  mov     r13, rax
0x18005cfb1  mov     rcx, rsi
0x18005cfb4  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18005cfba  jmp     loc_18005CEF4
0x18005cfbf  mov     rax, [r14]
0x18005cfc2  mov     [rsp+120h+var_100], r13
0x18005cfc7  mov     r9, r12
0x18005cfca  mov     r8d, edi
0x18005cfcd  mov     rcx, r14
0x18005cfd0  mov     rax, [rax+20h]
0x18005cfd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfd9  jmp     loc_18005CF20
0x18005cfde  mov     rcx, [r15]
0x18005cfe1  mov     rax, [rcx+8]
0x18005cfe5  mov     rcx, r15
0x18005cfe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cfed  jmp     loc_18005CE8F
0x18005cff2  xor     r8d, r8d; struct IWbemClassObject *
0x18005cff5  mov     edx, ebx; int
0x18005cff7  mov     rcx, r14; this
0x18005cffa  call    ?Return@CBasicObjectSink@@QEAAJJPEAUIWbemClassObject@@@Z; CBasicObjectSink::Return(long,IWbemClassObject *)
0x18005cfff  mov     ebx, eax
0x18005d001  cmp     [rbp+37h+var_80], r15b
0x18005d005  jnz     short loc_18005D015
0x18005d007  mov     rcx, [rbp+37h+var_70]
0x18005d00b  mov     rax, [rbp+37h+var_78]
0x18005d00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d014  nop
0x18005d015  mov     rcx, [rsi]
0x18005d018  mov     rax, [rcx+10h]
0x18005d01c  mov     rcx, rsi
0x18005d01f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d024  mov     [rbp+37h+arg_10], r15
0x18005d028  lea     rcx, [rbp+37h+var_60]
0x18005d02c  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18005d032  mov     eax, ebx
0x18005d034  jmp     loc_18005CF85
0x18005d039  cmp     byte ptr [rcx+19h], 5
0x18005d03d  jb      loc_18005CCB9
0x18005d043  mov     edx, 7Ah ; 'z'
0x18005d048  mov     [rsp+120h+var_F8], rdi
0x18005d04d  mov     [rsp+120h+var_100], rbx
0x18005d052  mov     r9, r12
0x18005d055  mov     r8, rsi
0x18005d058  mov     rcx, [rcx+10h]
0x18005d05c  call    WPP_SF_qqS
0x18005d061  jmp     loc_18005CCB9
0x18005d066  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005d06c  mov     ebx, 80041003h
0x18005d071  mov     edx, ebx
0x18005d073  mov     rcx, rax
0x18005d076  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005d07c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d083  cmp     rcx, r14
0x18005d086  jz      loc_18005D45E
0x18005d08c  test    byte ptr [rcx+1Ch], 1
0x18005d090  jz      loc_18005D45E
0x18005d096  cmp     byte ptr [rcx+19h], 2
0x18005d09a  jb      loc_18005D45E
0x18005d0a0  mov     edx, 7Ch ; '|'
0x18005d0a5  mov     r9d, 80041003h
0x18005d0ab  jmp     loc_18005D452
0x18005d0b0  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005d0b6  mov     ebx, 80041006h
0x18005d0bb  mov     edx, ebx
0x18005d0bd  mov     rcx, rax
0x18005d0c0  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005d0c6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d0cd  lea     rax, WPP_GLOBAL_Control
0x18005d0d4  cmp     rcx, rax
0x18005d0d7  jz      short loc_18005D100
0x18005d0d9  test    byte ptr [rcx+1Ch], 1
0x18005d0dd  jz      short loc_18005D100
0x18005d0df  cmp     byte ptr [rcx+19h], 2
0x18005d0e3  jb      short loc_18005D100
0x18005d0e5  mov     edx, 7Dh ; '}'
0x18005d0ea  mov     r9d, 80041006h
0x18005d0f0  lea     r8, WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids
0x18005d0f7  mov     rcx, [rcx+10h]
0x18005d0fb  call    WPP_SF_d
0x18005d100  mov     rcx, r14
0x18005d103  jmp     loc_18005D462
0x18005d108  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18005d10e  mov     ebx, 8004100Ah
0x18005d113  mov     edx, ebx
0x18005d115  mov     rcx, rax
0x18005d118  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18005d11e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005d125  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
