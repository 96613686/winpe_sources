# CWbemLevel1Login::LoginUser(ushort *,ushort *,long,IWbemContext *,bool,_GUID const &,void * *,bool)

- ea: `0x18002dda4`
- end: `0x18002e7f1`
- name: `?LoginUser@CWbemLevel1Login@@AEAAJPEAG0JPEAUIWbemContext@@_NAEBU_GUID@@PEAPEAX2@Z`
- size: `2637`
- prototype: `int(CWbemLevel1Login *__hidden this, unsigned __int16 *, unsigned __int16 *, int, struct IWbemContext *, bool, const struct _GUID *, void **, bool)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180062150`

## callees

- `0x18000b140`
- `0x18000b274`
- `0x18000e8c0`
- `0x18001f6d0`
- `0x180023250`
- `0x18002d324`
- `0x18002dda4`
- `0x18002e7f8`
- `0x18002f020`
- `0x18002f504`
- `0x18002fee4`
- `0x18003cfe0`
- `0x18003d010`
- `0x1800ce4c6`
- `0x1800ce510`
- `0x1800da010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002e536`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002e73b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002dea8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002e536`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18002e73b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002e5a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002e78e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002df84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002e5a8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18002e78e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e694`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e799`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e694`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18002e799`
- `wbemcomn!?Initialize@CMUILocaleList@@QEAAJPEAG_N@Z` at `0x18002dfad`
- `wbemcomn!?Initialize@CMUILocaleList@@QEAAJPEAG_N@Z` at `0x18002dfad`
- `wbemcomn!?_Free@CMUILocale@@SAHPEAX@Z` at `0x18002de55`
- `wbemcomn!?PublishClientRequestFailure@CPublishWMIOperationEvent@@SAJPEBGPEAG1K10J0@Z` at `0x18002e784`
- `wbemcomn!?PublishClientRequestFailure@CPublishWMIOperationEvent@@SAJPEBGPEAG1K10J0@Z` at `0x18002e784`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002df9a`
- `wbemcomn!?IsOffline@CWbemInstallObject@@SA_NXZ` at `0x18002df9a`
- `wbemcomn!GetMemLogObject` at `0x18002e0c2`
- `wbemcomn!GetMemLogObject` at `0x18002e131`
- `wbemcomn!GetMemLogObject` at `0x18002e14e`
- `wbemcomn!GetMemLogObject` at `0x18002e171`
- `wbemcomn!GetMemLogObject` at `0x18002e1e5`
- `wbemcomn!GetMemLogObject` at `0x18002e251`
- `wbemcomn!GetMemLogObject` at `0x18002e315`
- `wbemcomn!GetMemLogObject` at `0x18002e398`
- `wbemcomn!GetMemLogObject` at `0x18002e3e2`
- `wbemcomn!GetMemLogObject` at `0x18002e4d7`
- `wbemcomn!GetMemLogObject` at `0x18002e5d1`
- `wbemcomn!GetMemLogObject` at `0x18002e6c6`
- `wbemcomn!GetMemLogObject` at `0x18002e79f`
- `wbemcomn!GetMemLogObject` at `0x18002e0c2`
- `wbemcomn!GetMemLogObject` at `0x18002e131`
- `wbemcomn!GetMemLogObject` at `0x18002e14e`
- `wbemcomn!GetMemLogObject` at `0x18002e171`
- `wbemcomn!GetMemLogObject` at `0x18002e1e5`
- `wbemcomn!GetMemLogObject` at `0x18002e251`
- `wbemcomn!GetMemLogObject` at `0x18002e315`
- `wbemcomn!GetMemLogObject` at `0x18002e398`
- `wbemcomn!GetMemLogObject` at `0x18002e3e2`
- `wbemcomn!GetMemLogObject` at `0x18002e4d7`
- `wbemcomn!GetMemLogObject` at `0x18002e5d1`
- `wbemcomn!GetMemLogObject` at `0x18002e6c6`
- `wbemcomn!GetMemLogObject` at `0x18002e79f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e0ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e13c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e159`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e17c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e1f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e25d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e320`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e3a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e3f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e4e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e5dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e6d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e7aa`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e0ce`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e13c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e159`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e17c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e1f5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e25d`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e320`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e3a8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e3f2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e4e2`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e5dc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e6d1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18002e7aa`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002e22e`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18002e22e`

## string_xrefs

- `0x18002dffd`: `Read (ConnectServer)`
- `0x18002e765`: `WMIService`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWbemLevel1Login::LoginUser(
        CWbemLevel1Login *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct IWbemContext *a5,
        bool a6,
        const struct _GUID *a7,
        void **a8,
        bool a9)
{
  void **v12; // r15
  unsigned __int16 *v13; // r8
  struct CCoreServices *Instance; // rax
  CCoreServices *v15; // r14
  unsigned int v16; // edi
  int Services3; // edi
  CClientCnt *v18; // rcx
  CWbemNamespace *v19; // rdi
  unsigned __int16 *v20; // rbx
  char IsOffline; // al
  unsigned int SystemDefaultLocale; // ebx
  unsigned int UserAccess; // ebx
  CWbemNamespace *v24; // rax
  CMemoryLog *v26; // rax
  bool v27; // zf
  CMemoryLog *v28; // rax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  HRESULT v32; // eax
  void *v33; // rbx
  int v34; // r15d
  CMemoryLog *v35; // rax
  CMemoryLog *v36; // rax
  CClientCnt *v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // r9
  CMemoryLog *MemLogObject; // rax
  CMemoryLog *v41; // rax
  void *v42; // rcx
  int v43; // r15d
  CMemoryLog *v44; // rax
  CMemoryLog *v45; // rax
  CMemoryLog *v46; // rax
  int v47; // ebx
  unsigned __int16 *v48; // r8
  CMemoryLog *v49; // rax
  bool v50; // [rsp+28h] [rbp-F8h]
  CWbemNamespace *v51; // [rsp+A0h] [rbp-80h] BYREF
  unsigned int v52; // [rsp+A8h] [rbp-78h]
  void *ppInterface; // [rsp+B0h] [rbp-70h] BYREF
  struct CCoreServices *v54; // [rsp+B8h] [rbp-68h] BYREF
  _BYTE v55[8]; // [rsp+C0h] [rbp-60h] BYREF
  void (__fastcall *v56)(__int64); // [rsp+C8h] [rbp-58h]
  __int64 v57; // [rsp+D0h] [rbp-50h]
  void *v58; // [rsp+D8h] [rbp-48h] BYREF
  unsigned __int16 *v59; // [rsp+E0h] [rbp-40h] BYREF
  struct IWbemContext *v60; // [rsp+E8h] [rbp-38h]
  void **v61; // [rsp+F8h] [rbp-28h]
  CWbemNamespace **v62; // [rsp+100h] [rbp-20h]
  unsigned __int16 v63[264]; // [rsp+110h] [rbp-10h] BYREF

  v52 = a4;
  v60 = a5;
  v12 = a8;
  v61 = a8;
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      67,
      (unsigned int)WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
      (_DWORD)a2,
      (__int64)a3);
  }
  if ( memcmp_0(&IID_IWbemServices, &IID_IWbemServices, 0x10u) )
  {
    MemLogObject = GetMemLogObject();
    SystemDefaultLocale = -2147467262;
    CMemoryLog::Write(MemLogObject, -2147467262);
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SystemDefaultLocale;
    }
    v38 = 68;
    v39 = 2147500034LL;
    goto LABEL_69;
  }
  if ( !a8 )
  {
    v41 = GetMemLogObject();
    SystemDefaultLocale = -2147467261;
    CMemoryLog::Write(v41, -2147467261);
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SystemDefaultLocale;
    }
    v38 = 69;
    v39 = 2147500035LL;
    goto LABEL_69;
  }
  *a8 = 0;
  v59 = 0;
  if ( a3 && *a3 )
  {
    v13 = 0;
    v59 = a3;
    goto LABEL_7;
  }
  SystemDefaultLocale = GetSystemDefaultLocale(&v59);
  if ( (SystemDefaultLocale & 0x80000000) != 0 )
  {
    v36 = GetMemLogObject();
    CMemoryLog::Write(v36, SystemDefaultLocale);
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CClientCnt *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return SystemDefaultLocale;
    }
    v38 = 70;
    v39 = SystemDefaultLocale;
LABEL_69:
    WPP_SF_d(*((_QWORD *)v37 + 2), v38, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, v39);
    return SystemDefaultLocale;
  }
  v13 = v59;
LABEL_7:
  MakeGuard<int (*)(void *),unsigned short *>(v55, CMUILocale::_Free, v13);
  Instance = CCoreServices::CreateInstance();
  v15 = Instance;
  if ( !Instance )
  {
    v31 = GetMemLogObject();
    SystemDefaultLocale = -2147217402;
    CMemoryLog::Write(v31, -2147217402);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749894LL);
    }
    v27 = v55[0] == 0;
    goto LABEL_37;
  }
  v54 = Instance;
  v16 = (!a9 + 1) << 17;
  v51 = 0;
  v62 = &v51;
  if ( (v16 & 0x20000) == 0 )
  {
    AcquireSRWLockShared((PSRWLOCK)this + 10);
    Services3 = CWbemNamespace::UniversalConnect(
                  0,
                  v60,
                  a2,
                  0,
                  *((const unsigned __int16 **)this + 3),
                  0,
                  0,
                  v52,
                  v16,
                  0,
                  0,
                  (v16 >> 18) & 1,
                  0,
                  *((const unsigned __int16 **)this + 6),
                  *((const unsigned __int16 **)this + 7),
                  *((_DWORD *)this + 16),
                  *((_QWORD *)this + 9),
                  &IID_IWbemServices,
                  (void **)&v51);
    if ( Services3 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, Services3);
    }
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        513,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        (unsigned int)Services3);
      v18 = WPP_GLOBAL_Control;
    }
    if ( Services3 < 0 )
    {
      v28 = GetMemLogObject();
      CMemoryLog::Write(v28, Services3);
      v18 = WPP_GLOBAL_Control;
    }
    if ( v18 != (CClientCnt *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 && *((_BYTE *)v18 + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)v18 + 2), 45, WPP_28a6391408553a99477eaaaeeaa95c37_Traceguids, (unsigned int)Services3);
    ReleaseSRWLockShared((PSRWLOCK)this + 10);
    goto LABEL_18;
  }
  ppInterface = 0;
  v32 = CoGetCallContext(&IID_IServerSecurity, &ppInterface);
  v33 = ppInterface;
  v58 = ppInterface;
  v34 = 0;
  if ( v32 != -2147417833 )
    v34 = v32;
  if ( v34 < 0 )
  {
    v35 = GetMemLogObject();
    CMemoryLog::Write(v35, v34);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
        (unsigned int)v34);
    }
    if ( v33 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v33 + 16LL))(v33);
    v58 = 0;
    if ( v51 )
      (*(void (__fastcall **)(CWbemNamespace *))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    (*(void (__fastcall **)(CCoreServices *))(*(_QWORD *)v15 + 16LL))(v15);
    v54 = 0;
    if ( !v55[0] )
      v56(v57);
    return (unsigned int)v34;
  }
  v42 = ppInterface;
  if ( ppInterface )
  {
    v43 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 48LL))(ppInterface);
    v42 = ppInterface;
  }
  else
  {
    v43 = 0;
  }
  if ( v42 )
  {
    if ( v43 )
    {
      SystemDefaultLocale = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v42 + 40LL))(v42);
      if ( (SystemDefaultLocale & 0x80000000) != 0 )
      {
        v44 = GetMemLogObject();
        CMemoryLog::Write(v44, SystemDefaultLocale);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            73,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            SystemDefaultLocale);
        }
LABEL_98:
        CReleaseMe::release((CReleaseMe *)&v58);
LABEL_70:
        if ( v51 )
          (*(void (__fastcall **)(CWbemNamespace *))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
        CReleaseMe::release((CReleaseMe *)&v54);
        ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>::~ScopeGuardImpl1<int (*)(AUTHZ_AUDIT_EVENT_HANDLE__ *),AUTHZ_AUDIT_EVENT_HANDLE__ *>((__int64)v55);
        return SystemDefaultLocale;
      }
    }
  }
  AcquireSRWLockShared((PSRWLOCK)this + 10);
  Services3 = CCoreServices::GetServices3(
                v15,
                a2,
                *((const unsigned __int16 **)this + 3),
                v60,
                v52,
                0,
                0,
                v16,
                *((const unsigned __int16 **)this + 6),
                *((const unsigned __int16 **)this + 7),
                *((_DWORD *)this + 16),
                *((_QWORD *)this + 9),
                &IID_IWbemServices,
                (void **)&v51);
  ReleaseSRWLockShared((PSRWLOCK)this + 10);
  if ( v43 )
  {
    if ( ppInterface )
    {
      SystemDefaultLocale = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppInterface + 32LL))(ppInterface);
      if ( (SystemDefaultLocale & 0x80000000) != 0 )
      {
        v45 = GetMemLogObject();
        CMemoryLog::Write(v45, SystemDefaultLocale);
        if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            74,
            WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
            SystemDefaultLocale);
        }
        goto LABEL_98;
      }
    }
  }
  CReleaseMe::release((CReleaseMe *)&v58);
  v12 = v61;
LABEL_18:
  if ( Services3 >= 0 )
  {
    v19 = v51;
    v20 = v59;
    IsOffline = CWbemInstallObject::IsOffline();
    SystemDefaultLocale = CMUILocaleList::Initialize((CWbemNamespace *)((char *)v19 + 176), v20, IsOffline);
    if ( (SystemDefaultLocale & 0x80000000) != 0 )
    {
      v46 = GetMemLogObject();
      CMemoryLog::Write(v46, SystemDefaultLocale);
    }
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        936,
        WPP_feb511234a3c3e685382ece5e11c7a60_Traceguids,
        SystemDefaultLocale);
    }
    if ( (SystemDefaultLocale & 0x80000000) == 0 )
    {
      UserAccess = CWbemNamespace::GetUserAccess(v19);
      CWbemNamespace::InnerAllowedWithSD(
        v19,
        (CWbemNamespace *)((char *)v19 + 216),
        1u,
        L"Read (ConnectServer)",
        0,
        v50,
        0);
      if ( (UserAccess & 1) != 0 )
      {
        *((_DWORD *)v19 + 26) = UserAccess;
        v24 = v51;
        v51 = 0;
        *v12 = v24;
        if ( v51 )
          (*(void (__fastcall **)(CWbemNamespace *))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
        (*(void (__fastcall **)(CCoreServices *))(*(_QWORD *)v15 + 16LL))(v15);
        v54 = 0;
        if ( !v55[0] )
          v56(v57);
        return 0;
      }
      v47 = StringCchPrintfW(v63, 0x104u, L"%s : %s", L"connect to namespace", *((_QWORD *)v19 + 12));
      AcquireSRWLockShared((PSRWLOCK)this + 10);
      v48 = v63;
      if ( v47 )
        v48 = L"connect to namespace";
      SystemDefaultLocale = -2147217405;
      CPublishWMIOperationEvent::PublishClientRequestFailure(
        &psz,
        *((unsigned __int16 **)this + 6),
        *((unsigned __int16 **)this + 3),
        *((_DWORD *)this + 16),
        L"WMIService",
        v48,
        -2147217405,
        L"the user was not granted appropriate permission on the namespace.");
      ReleaseSRWLockShared((PSRWLOCK)this + 10);
      Sleep(0x1388u);
      v49 = GetMemLogObject();
      CMemoryLog::Write(v49, -2147217405);
      if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids, 2147749891LL);
      }
      goto LABEL_70;
    }
    v26 = GetMemLogObject();
    CMemoryLog::Write(v26, SystemDefaultLocale);
    if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        76,
        WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
        SystemDefaultLocale);
    }
    if ( v51 )
      (*(void (__fastcall **)(CWbemNamespace *))(*(_QWORD *)v51 + 16LL))(v51);
    v51 = 0;
    (*(void (__fastcall **)(CCoreServices *))(*(_QWORD *)v15 + 16LL))(v15);
    v54 = 0;
    v27 = v55[0] == 0;
LABEL_37:
    if ( v27 )
      v56(v57);
    return SystemDefaultLocale;
  }
  if ( Services3 == -2147217405 )
    Sleep(0x1388u);
  v30 = GetMemLogObject();
  CMemoryLog::Write(v30, Services3);
  if ( WPP_GLOBAL_Control != (CClientCnt *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      75,
      WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids,
      (unsigned int)Services3);
  }
  if ( v51 )
    (*(void (__fastcall **)(CWbemNamespace *))(*(_QWORD *)v51 + 16LL))(v51);
  v51 = 0;
  (*(void (__fastcall **)(CCoreServices *))(*(_QWORD *)v15 + 16LL))(v15);
  v54 = 0;
  if ( !v55[0] )
    v56(v57);
  return (unsigned int)Services3;
}

```

## disassembly

```asm
0x18002dda4  push    rbp
0x18002dda6  push    rbx
0x18002dda7  push    rdi
0x18002dda8  push    r12
0x18002ddaa  push    r13
0x18002ddac  push    r14
0x18002ddae  push    r15
0x18002ddb0  lea     rbp, [rsp-210h]
0x18002ddb8  sub     rsp, 330h
0x18002ddbf  mov     rax, cs:__security_cookie
0x18002ddc6  xor     rax, rsp
0x18002ddc9  mov     [rbp+240h+var_40], rax
0x18002ddd0  mov     [rbp+240h+var_2B8], r9d
0x18002ddd4  mov     rbx, r8
0x18002ddd7  mov     r12, rdx
0x18002ddda  mov     r13, rcx
0x18002dddd  mov     rax, [rbp+240h+arg_20]
0x18002dde4  mov     [rbp+240h+var_278], rax
0x18002dde8  mov     r15, [rbp+240h+arg_38]
0x18002ddef  mov     [rbp+240h+var_268], r15
0x18002ddf3  xor     edi, edi
0x18002ddf5  lea     r14, WPP_GLOBAL_Control
0x18002ddfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002de03  cmp     rcx, r14
0x18002de06  jnz     loc_18002E08C
0x18002de0c  mov     r8d, 10h; Size
0x18002de12  lea     rax, IID_IWbemServices
0x18002de19  mov     rdx, rax; Buf2
0x18002de1c  mov     rcx, rax; Buf1
0x18002de1f  call    memcmp_0
0x18002de24  test    eax, eax
0x18002de26  jnz     loc_18002E398
0x18002de2c  test    r15, r15
0x18002de2f  jz      loc_18002E3E2
0x18002de35  mov     [r15], rdi
0x18002de38  mov     [rbp+240h+var_280], rdi
0x18002de3c  test    rbx, rbx
0x18002de3f  jz      loc_18002E302
0x18002de45  cmp     [rbx], di
0x18002de48  jz      loc_18002E302
0x18002de4e  mov     r8, rdi
0x18002de51  mov     [rbp+240h+var_280], rbx
0x18002de55  mov     rdx, cs:__imp_?_Free@CMUILocale@@SAHPEAX@Z; CMUILocale::_Free(void *)
0x18002de5c  lea     rcx, [rbp+240h+var_2A0]
0x18002de60  call    ??$MakeGuard@P6AHPEAX@ZPEAG@@YA?AV?$ScopeGuardImpl1@P6AHPEAX@ZPEAG@@P6AHPEAX@ZPEAG@Z; MakeGuard<int (*)(void *),ushort *>(int (*)(void *),ushort *)
0x18002de65  nop
0x18002de66  call    ?CreateInstance@CCoreServices@@SAPEAV1@XZ; CCoreServices::CreateInstance(void)
0x18002de6b  mov     r14, rax
0x18002de6e  test    rax, rax
0x18002de71  jz      loc_18002E1E5
0x18002de77  mov     [rbp+240h+var_2A8], rax
0x18002de7b  movzx   edi, [rbp+240h+arg_40]
0x18002de82  xor     edi, 1
0x18002de85  inc     edi
0x18002de87  shl     edi, 11h
0x18002de8a  mov     [rbp+240h+var_2C0], 0
0x18002de92  lea     rax, [rbp+240h+var_2C0]
0x18002de96  mov     [rbp+240h+var_260], rax
0x18002de9a  bt      edi, 11h
0x18002de9e  jb      loc_18002E21B
0x18002dea4  lea     rcx, [r13+50h]; SRWLock
0x18002dea8  call    cs:__imp_AcquireSRWLockShared
0x18002deae  mov     ecx, edi
0x18002deb0  shr     ecx, 12h
0x18002deb3  and     ecx, 1
0x18002deb6  lea     rax, [rbp+240h+var_2C0]
0x18002deba  mov     [rsp+360h+var_2D0], rax; void **
0x18002dec2  lea     rax, IID_IWbemServices
0x18002dec9  mov     [rsp+360h+var_2D8], rax; struct _GUID *
0x18002ded1  mov     rax, [r13+48h]
0x18002ded5  mov     [rsp+360h+var_2E0], rax; unsigned __int64
0x18002dedd  mov     eax, [r13+40h]
0x18002dee1  mov     [rsp+360h+var_2E8], eax; unsigned int
0x18002dee5  mov     rax, [r13+38h]
0x18002dee9  mov     [rsp+360h+var_2F0], rax; unsigned __int16 *
0x18002deee  mov     rax, [r13+30h]
0x18002def2  mov     [rsp+360h+var_2F8], rax; unsigned __int16 *
0x18002def7  xor     edx, edx
0x18002def9  mov     dword ptr [rsp+360h+var_300], edx; int
0x18002defd  mov     dword ptr [rsp+360h+var_308], ecx; int
0x18002df01  mov     [rsp+360h+var_310], edx; unsigned int
0x18002df05  mov     dword ptr [rsp+360h+var_318], edx; unsigned int
0x18002df09  mov     dword ptr [rsp+360h+var_320], edi; unsigned int
0x18002df0d  mov     eax, [rbp+240h+var_2B8]
0x18002df10  mov     [rsp+360h+var_328], eax; unsigned int
0x18002df14  mov     [rsp+360h+var_330], rdx; struct _IWmiUserHandle *
0x18002df19  mov     [rsp+360h+var_338], rdx; bool
0x18002df1e  mov     rax, [r13+18h]
0x18002df22  mov     [rsp+360h+var_340], rax; unsigned __int16 *
0x18002df27  xor     r9d, r9d; unsigned __int16 *
0x18002df2a  mov     r8, r12; unsigned __int16 *
0x18002df2d  mov     rdx, [rbp+240h+var_278]; struct IWbemContext *
0x18002df31  xor     ecx, ecx; struct CWbemNamespace *
0x18002df33  call    ?UniversalConnect@CWbemNamespace@@SAJPEAV1@PEAUIWbemContext@@PEBG22PEAU_IWmiCallSec@@PEAU_IWmiUserHandle@@KKKKHH22K_KAEBU_GUID@@PEAPEAX@Z; CWbemNamespace::UniversalConnect(CWbemNamespace *,IWbemContext *,ushort const *,ushort const *,ushort const *,_IWmiCallSec *,_IWmiUserHandle *,ulong,ulong,ulong,ulong,int,int,ushort const *,ushort const *,ulong,unsigned __int64,_GUID const &,void * *)
0x18002df38  mov     edi, eax
0x18002df3a  xor     r12d, r12d
0x18002df3d  test    eax, eax
0x18002df3f  js      loc_18002E14E
0x18002df45  mov     rcx, cs:WPP_GLOBAL_Control
0x18002df4c  lea     rax, WPP_GLOBAL_Control
0x18002df53  cmp     rcx, rax
0x18002df56  jz      short loc_18002DF62
0x18002df58  test    byte ptr [rcx+1Ch], 1
0x18002df5c  jnz     loc_18002E63A
0x18002df62  test    edi, edi
0x18002df64  js      loc_18002E131
0x18002df6a  lea     rax, WPP_GLOBAL_Control
0x18002df71  cmp     rcx, rax
0x18002df74  jz      short loc_18002DF80
0x18002df76  test    byte ptr [rcx+1Ch], 1
0x18002df7a  jnz     loc_18002E668
0x18002df80  lea     rcx, [r13+50h]; SRWLock
0x18002df84  call    cs:__imp_ReleaseSRWLockShared
0x18002df8a  test    edi, edi
0x18002df8c  js      loc_18002E164
0x18002df92  mov     rdi, [rbp+240h+var_2C0]
0x18002df96  mov     rbx, [rbp+240h+var_280]
0x18002df9a  call    cs:__imp_?IsOffline@CWbemInstallObject@@SA_NXZ; CWbemInstallObject::IsOffline(void)
0x18002dfa0  mov     r8b, al
0x18002dfa3  lea     rcx, [rdi+0B0h]
0x18002dfaa  mov     rdx, rbx
0x18002dfad  call    cs:__imp_?Initialize@CMUILocaleList@@QEAAJPEAG_N@Z; CMUILocaleList::Initialize(ushort *,bool)
0x18002dfb3  mov     ebx, eax
0x18002dfb5  test    eax, eax
0x18002dfb7  js      loc_18002E6C6
0x18002dfbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dfc4  lea     rax, WPP_GLOBAL_Control
0x18002dfcb  cmp     rcx, rax
0x18002dfce  jz      short loc_18002DFDA
0x18002dfd0  test    byte ptr [rcx+1Ch], 1
0x18002dfd4  jnz     loc_18002E2DB
0x18002dfda  test    ebx, ebx
0x18002dfdc  js      loc_18002E0C2
0x18002dfe2  mov     rcx, rdi; this
0x18002dfe5  call    ?GetUserAccess@CWbemNamespace@@QEAAKXZ; CWbemNamespace::GetUserAccess(void)
0x18002dfea  mov     ebx, eax
0x18002dfec  lea     rdx, [rdi+0D8h]; struct CNtSecurityDescriptor *
0x18002dff3  mov     byte ptr [rsp+360h+var_330], r12b; bool
0x18002dff8  mov     [rsp+360h+var_340], r12; unsigned __int16 *
0x18002dffd  lea     r9, aReadConnectser; "Read (ConnectServer)"
0x18002e004  mov     r8d, 1; unsigned int
0x18002e00a  mov     rcx, rdi; this
0x18002e00d  call    ?InnerAllowedWithSD@CWbemNamespace@@QEAA_NPEAVCNtSecurityDescriptor@@KPEBG1_N2@Z; CWbemNamespace::InnerAllowedWithSD(CNtSecurityDescriptor *,ulong,ushort const *,ushort const *,bool,bool)
0x18002e012  test    bl, 1
0x18002e015  jz      loc_18002E70D
0x18002e01b  mov     [rdi+68h], ebx
0x18002e01e  mov     rax, [rbp+240h+var_2C0]
0x18002e022  mov     [rbp+240h+var_2C0], r12
0x18002e026  mov     [r15], rax
0x18002e029  mov     rcx, [rbp+240h+var_2C0]
0x18002e02d  test    rcx, rcx
0x18002e030  jz      short loc_18002E03E
0x18002e032  mov     rax, [rcx]
0x18002e035  mov     rax, [rax+10h]
0x18002e039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e03e  mov     [rbp+240h+var_2C0], r12
0x18002e042  mov     rax, [r14]
0x18002e045  mov     rcx, r14
0x18002e048  mov     rax, [rax+10h]
0x18002e04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e051  mov     [rbp+240h+var_2A8], r12
0x18002e055  cmp     [rbp+240h+var_2A0], r12b
0x18002e059  jnz     short loc_18002E068
0x18002e05b  mov     rcx, [rbp+240h+var_290]
0x18002e05f  mov     rax, [rbp+240h+var_298]
0x18002e063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e068  xor     eax, eax
0x18002e06a  mov     rcx, [rbp+240h+var_40]
0x18002e071  xor     rcx, rsp; StackCookie
0x18002e074  call    __security_check_cookie
0x18002e079  add     rsp, 330h
0x18002e080  pop     r15
0x18002e082  pop     r14
0x18002e084  pop     r13
0x18002e086  pop     r12
0x18002e088  pop     rdi
0x18002e089  pop     rbx
0x18002e08a  pop     rbp
0x18002e08b  retn
0x18002e08c  test    byte ptr [rcx+1Ch], 1
0x18002e090  jz      loc_18002DE0C
0x18002e096  cmp     byte ptr [rcx+19h], 5
0x18002e09a  jb      loc_18002DE0C
0x18002e0a0  mov     edx, 43h ; 'C'
0x18002e0a5  mov     [rsp+360h+var_340], rbx
0x18002e0aa  mov     r9, r12
0x18002e0ad  lea     r8, WPP_85e451853fbe3bdcca694ddf3290172d_Traceguids
0x18002e0b4  mov     rcx, [rcx+10h]
0x18002e0b8  call    WPP_SF_SS
0x18002e0bd  jmp     loc_18002DE0C
0x18002e0c2  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e0c8  nop
0x18002e0c9  mov     edx, ebx
0x18002e0cb  mov     rcx, rax
0x18002e0ce  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e0db  lea     rax, WPP_GLOBAL_Control
0x18002e0e2  cmp     rcx, rax
0x18002e0e5  jnz     loc_18002E6DC
0x18002e0eb  mov     rcx, [rbp+240h+var_2C0]
0x18002e0ef  test    rcx, rcx
0x18002e0f2  jz      short loc_18002E100
0x18002e0f4  mov     rax, [rcx]
0x18002e0f7  mov     rax, [rax+10h]
0x18002e0fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e100  mov     [rbp+240h+var_2C0], r12
0x18002e104  mov     rax, [r14]
0x18002e107  mov     rcx, r14
0x18002e10a  mov     rax, [rax+10h]
0x18002e10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e113  mov     [rbp+240h+var_2A8], r12
0x18002e117  cmp     [rbp+240h+var_2A0], r12b
0x18002e11b  jnz     short loc_18002E12A
0x18002e11d  mov     rcx, [rbp+240h+var_290]
0x18002e121  mov     rax, [rbp+240h+var_298]
0x18002e125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e12a  mov     eax, ebx
0x18002e12c  jmp     loc_18002E06A
0x18002e131  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e137  mov     edx, edi
0x18002e139  mov     rcx, rax
0x18002e13c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e142  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e149  jmp     loc_18002DF6A
0x18002e14e  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e154  mov     edx, edi
0x18002e156  mov     rcx, rax
0x18002e159  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e15f  jmp     loc_18002DF45
0x18002e164  mov     ebx, 80041003h
0x18002e169  cmp     edi, ebx
0x18002e16b  jz      loc_18002E68F
0x18002e171  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e177  mov     edx, edi
0x18002e179  mov     rcx, rax
0x18002e17c  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e182  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e189  lea     rax, WPP_GLOBAL_Control
0x18002e190  cmp     rcx, rax
0x18002e193  jz      short loc_18002E19F
0x18002e195  test    byte ptr [rcx+1Ch], 1
0x18002e199  jnz     loc_18002E69F
0x18002e19f  mov     rcx, [rbp+240h+var_2C0]
0x18002e1a3  test    rcx, rcx
0x18002e1a6  jz      short loc_18002E1B4
0x18002e1a8  mov     rax, [rcx]
0x18002e1ab  mov     rax, [rax+10h]
0x18002e1af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1b4  mov     [rbp+240h+var_2C0], r12
0x18002e1b8  mov     rax, [r14]
0x18002e1bb  mov     rcx, r14
0x18002e1be  mov     rax, [rax+10h]
0x18002e1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1c7  mov     [rbp+240h+var_2A8], r12
0x18002e1cb  cmp     [rbp+240h+var_2A0], r12b
0x18002e1cf  jnz     short loc_18002E1DE
0x18002e1d1  mov     rcx, [rbp+240h+var_290]
0x18002e1d5  mov     rax, [rbp+240h+var_298]
0x18002e1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e1de  mov     eax, edi
0x18002e1e0  jmp     loc_18002E06A
0x18002e1e5  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e1eb  mov     ebx, 80041006h
0x18002e1f0  mov     edx, ebx
0x18002e1f2  mov     rcx, rax
0x18002e1f5  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e1fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e202  lea     rax, WPP_GLOBAL_Control
0x18002e209  cmp     rcx, rax
0x18002e20c  jnz     loc_18002E435
0x18002e212  cmp     [rbp+240h+var_2A0], dil
0x18002e216  jmp     loc_18002E11B
0x18002e21b  mov     [rbp+240h+ppInterface], 0
0x18002e223  lea     rdx, [rbp+240h+ppInterface]; ppInterface
0x18002e227  lea     rcx, IID_IServerSecurity; riid
0x18002e22e  call    cs:__imp_CoGetCallContext
0x18002e234  mov     rbx, [rbp+240h+ppInterface]
0x18002e238  mov     [rbp+240h+var_288], rbx
0x18002e23c  xor     r15d, r15d
0x18002e23f  cmp     eax, 80010117h
0x18002e244  cmovnz  r15d, eax
0x18002e248  test    r15d, r15d
0x18002e24b  jns     loc_18002E49A
0x18002e251  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18002e257  mov     edx, r15d
0x18002e25a  mov     rcx, rax
0x18002e25d  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18002e263  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e26a  lea     rax, WPP_GLOBAL_Control
0x18002e271  cmp     rcx, rax
0x18002e274  jnz     loc_18002E469
0x18002e27a  xor     edi, edi
0x18002e27c  test    rbx, rbx
0x18002e27f  jz      short loc_18002E290
0x18002e281  mov     rax, [rbx]
0x18002e284  mov     rcx, rbx
0x18002e287  mov     rax, [rax+10h]
0x18002e28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e290  mov     [rbp+240h+var_288], rdi
0x18002e294  mov     rcx, [rbp+240h+var_2C0]
  ... truncated ...
```
