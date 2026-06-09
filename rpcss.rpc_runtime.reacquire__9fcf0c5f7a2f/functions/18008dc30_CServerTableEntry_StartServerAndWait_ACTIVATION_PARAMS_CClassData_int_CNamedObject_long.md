# CServerTableEntry::StartServerAndWait(ACTIVATION_PARAMS *,CClassData *,int,CNamedObject *,long *)

- ea: `0x18008dc30`
- end: `0x18008e545`
- name: `?StartServerAndWait@CServerTableEntry@@QEAAJPEAUACTIVATION_PARAMS@@PEAVCClassData@@HPEAVCNamedObject@@PEAJ@Z`
- size: `2325`
- prototype: `__int64 __usercall@<rax>(CServerTableEntry *__hidden this@<rcx>, struct ACTIVATION_PARAMS *@<rdx>, struct CClassData *@<r8>, int@<r9d>, struct CNamedObject *, int *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800065e4`

## callees

- `0x180003194`
- `0x18000902c`
- `0x18000fe7c`
- `0x1800189d0`
- `0x18001a374`
- `0x18001ee90`
- `0x1800210f8`
- `0x180025088`
- `0x18002c408`
- `0x18002ea40`
- `0x180034260`
- `0x1800486cc`
- `0x18004e554`
- `0x1800516c0`
- `0x18005ac00`
- `0x180061ec0`
- `0x18006313c`
- `0x1800648b4`
- `0x1800686c0`
- `0x18006920c`
- `0x18006b8f0`
- `0x18006c680`
- `0x18006d118`
- `0x18006e72c`
- `0x180077f10`
- `0x1800839e0`
- `0x18008dc30`
- `0x1800b7ac0`
- `0x1800fba30`
- `0x1800fbd7c`
- `0x180100958`
- `0x180100c50`
- `0x180114010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x18008e14a`
- `RPCRT4!UuidCreate` at `0x18008e14a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008de07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008dff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e20a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e516`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008de07`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008dff0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e20a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18008e516`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008e0e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008e0e2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e24c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e24c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008dd3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18008dd3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008dd81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008def0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e34b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008dd81`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008def0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e047`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008e34b`

## string_xrefs

- `0x18008dddb`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008df28`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008dfbd`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008e192`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008e4b5`: `onecore\com\combase\rpcss\olescm\class.cxx`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::StartServerAndWait(
        CServerTableEntry *this,
        struct ACTIVATION_PARAMS *a2,
        HSTRING *a3,
        int a4,
        struct CNamedObject *a5,
        int *a6)
{
  int *v6; // r12
  struct CNamedObject *v7; // rbx
  __int64 v11; // rcx
  void *v12; // rcx
  struct tagBLOB *v13; // rdx
  void *v14; // rcx
  int v15; // ecx
  int v16; // r9d
  void *v17; // r8
  __int64 v19; // rcx
  __int64 v20; // rax
  const WCHAR *v21; // rbx
  int v22; // esi
  CGuidStr *v23; // rax
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  __int64 v28; // r11
  void *v29; // r8
  ComBlob *v30; // rcx
  int v31; // r15d
  HANDLE *v32; // r13
  HSTRING v33; // rax
  __int64 v34; // rbx
  int v35; // r12d
  PCWSTR StringRawBuffer; // r9
  HSTRING v37; // rax
  int v38; // edx
  __int64 v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  CSurrogateListEntry *v42; // rbx
  __int64 v43; // rcx
  CActivationStateList *v44; // rcx
  char v45; // al
  int Dll; // eax
  unsigned int v47; // edx
  int started; // ebx
  unsigned int v49; // edx
  CActivationState *v50; // rcx
  void *v51; // r8
  CActivationState *v52; // rcx
  void *v53; // r8
  CActivationState *v54; // rcx
  __int64 v55; // rax
  int v56; // ecx
  WCHAR *v57; // rax
  HSTRING v58; // rcx
  __int64 v59; // rcx
  int v60; // r9d
  const wchar_t *v61; // rax
  CGuidStr *v62; // rcx
  int v63; // [rsp+20h] [rbp-E0h]
  int v64; // [rsp+20h] [rbp-E0h]
  int v65; // [rsp+20h] [rbp-E0h]
  char *v66; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  CSurrogateListEntry *v69; // [rsp+78h] [rbp-88h] BYREF
  int v70; // [rsp+80h] [rbp-80h] BYREF
  int v71[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CNamedObject *v72; // [rsp+90h] [rbp-70h] BYREF
  int v73; // [rsp+98h] [rbp-68h] BYREF
  int v74; // [rsp+9Ch] [rbp-64h] BYREF
  CGuidStr *v75; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID *p_lpMem; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v77; // [rsp+B0h] [rbp-50h] BYREF
  char v78; // [rsp+B8h] [rbp-48h]
  _BYTE v79[80]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v6 = a6;
  v7 = a5;
  lpMem = 0;
  v70 = a4;
  *a6 = 0;
  v11 = *((_QWORD *)a2 + 2);
  v72 = a5;
  *(_QWORD *)v71 = a6;
  p_lpMem = &lpMem;
  v12 = *(void **)(v11 + 72);
  v77 = 0;
  v78 = 1;
  GetPackageNameFromToken(v12, &v77);
  wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void MIDL_user_free(void *)>>>(&p_lpMem);
  if ( !(unsigned int)CClassData::LaunchOrActivationAllowed(
                        (CClassData *)a3,
                        *(void **)a2,
                        *((unsigned __int8 *)a2 + 188),
                        *((unsigned __int8 *)a2 + 189),
                        1,
                        *((_DWORD *)a2 + 32),
                        *((struct CToken **)a2 + 2),
                        *((_DWORD *)a2 + 29),
                        0) )
  {
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v14 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
      StringSid = 0;
      ConvertSidToStringSidW(v14, &StringSid);
      WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
      CGuidStr::CGuidStr((CGuidStr *)v79, (const struct _GUID *)((char *)a2 + 60));
      ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
        v15,
        (unsigned int)"CServerTableEntry::StartServerAndWait",
        2553,
        v16);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9FA,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)0x80070005LL,
      v63);
    v17 = lpMem;
    lpMem = 0;
    if ( v17 )
      HeapFree(g_hHeap, 0, v17);
    return 2147942405LL;
  }
  v19 = *((_QWORD *)a2 + 43);
  if ( v19 )
  {
    LODWORD(v66) = 1;
    v69 = 0;
    if ( (int)ActivationPropertiesIn::GetClassInfoW(
                (ActivationPropertiesIn *)(v19 + 568),
                &GUID_000001e2_0000_0000_c000_000000000046,
                (void **)&v69) >= 0 )
    {
      StringSid = 0;
      if ( (*(int (__fastcall **)(CSurrogateListEntry *, GUID *, LPWSTR *))(*(_QWORD *)v69 + 48LL))(
             v69,
             &GUID_7a0ddd93_7198_4e15_bbd7_427c77b6907a,
             &StringSid) >= 0
        && (*(int (__fastcall **)(LPWSTR, _QWORD, char **))(*(_QWORD *)StringSid + 24LL))(StringSid, 0, &v66) >= 0
        && !(_DWORD)v66 )
      {
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v20 = *((_QWORD *)a2 + 1);
          if ( v20 )
          {
            v21 = *(const WCHAR **)(v20 + 384);
            v22 = *(_DWORD *)(v20 + 88);
          }
          else
          {
            v21 = &Class;
            v22 = 0;
          }
          WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
          v23 = CGuidStr::CGuidStr((CGuidStr *)v79, (const struct _GUID *)((char *)a2 + 60));
          ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,long>(
            v25,
            v24,
            v26,
            v27,
            v63,
            (__int64)v23,
            v28,
            v22,
            (__int64)v21);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA13,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)0x8007000ELL,
          v63);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&StringSid);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v69);
        v29 = lpMem;
        lpMem = 0;
        goto LABEL_30;
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&StringSid);
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v69);
  }
  *((_DWORD *)this + 4) = 0;
  v30 = (ComBlob *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v30 )
    ComBlob::DeleteBlob(v30, v13);
  *(GUID *)((char *)this + 56) = GUID_NULL;
  do
    v31 = _InterlockedIncrement(&dword_180158DA0);
  while ( !v31 );
  v32 = (HANDLE *)ServerProcessLaunchCompletedEvent(v31);
  if ( !v32 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2C,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)0x8007000ELL,
      v63);
    *((_DWORD *)this + 3) = 0;
    v29 = lpMem;
    lpMem = 0;
LABEL_30:
    if ( v29 )
      HeapFree(g_hHeap, 0, v29);
    return 2147942414LL;
  }
  if ( *((_BYTE *)a3 + 80) == 3 )
  {
    v33 = a3[11];
    v69 = 0;
    v34 = ((unsigned __int64)v33 + 118) & -(__int64)(v33 != 0);
    if ( v34 )
    {
      if ( *((_BYTE *)a3 + 172) )
      {
        v35 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(a3[17], 0);
      }
      else
      {
        StringRawBuffer = 0;
        v35 = 2048;
      }
      v37 = a3[11];
      if ( v37 )
        v38 = *((_DWORD *)v37 + 19);
      else
        v38 = -1;
      v39 = *((_QWORD *)a2 + 1);
      if ( v39 )
        v40 = *(_QWORD *)(v39 + 32);
      else
        v40 = 0;
      v41 = CSurrogateList::Lookup(
              v40,
              *((_QWORD *)a2 + 2),
              *((unsigned __int8 *)a2 + 188),
              *((unsigned int *)a2 + 48),
              v40,
              v34,
              StringRawBuffer,
              v35,
              v38);
      wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
        &v69,
        v41);
      v42 = v69;
      if ( v69 )
      {
        v43 = *(_QWORD *)(*((_QWORD *)v69 + 5) + 96LL);
        *((_QWORD *)this + 4) = v43;
        _InterlockedIncrement((volatile signed __int32 *)(v43 + 16));
        SetEvent(v32[3]);
        v6 = *(int **)v71;
        *((_DWORD *)this + 3) = v31;
        *(_QWORD *)v71 = 0;
        *v6 = v31;
        LODWORD(v66) = *(_DWORD *)(*((_QWORD *)this + 4) + 88LL);
        wil::make_unique_nothrow<CActivationState,_GUID &,unsigned long,unsigned long &,std::nullptr_t>(
          (unsigned int)&StringSid,
          (_DWORD)a2 + 60,
          (unsigned int)&v66,
          (_DWORD)a2 + 240,
          (__int64)v71);
        if ( StringSid )
          CActivationStateList::Insert(v44, (struct CActivationState *)StringSid);
        UuidCreate((UUID *)(*((_QWORD *)a2 + 20) + 24LL));
        LODWORD(v66) = 0;
        v45 = CClassData::AppIDFlags((CClassData *)a3);
        Dll = CSurrogateListEntry::LoadDll(v42, a2, gfIssueActivationRpcAtIdentify | v45 & 4, (int *)&v66);
        started = (int)v66;
        if ( (int)v66 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA7B,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)(unsigned int)v66,
            v64);
          v50 = (CActivationState *)StringSid;
          if ( StringSid )
          {
            CActivationStateList::Remove((CActivationStateList *)StringSid, (struct CActivationState *)StringSid);
            v50 = (CActivationState *)StringSid;
          }
          StringSid = 0;
          if ( v50 )
            CActivationState::`scalar deleting destructor'(v50, v49);
          ReleaseProcess(*((struct CProcess **)this + 4));
          *((_QWORD *)this + 4) = 0;
          wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
            &v69,
            0);
          CNamedObject::Release((CNamedObject *)v32);
          *((_DWORD *)this + 3) = 0;
          v51 = lpMem;
          lpMem = 0;
          goto LABEL_53;
        }
        if ( Dll )
        {
          ClearOrpcThat(*((struct tagORPCTHAT **)a2 + 21));
          ClearLocalThat(*((struct __MIDL_XmitDefs_0011 **)a2 + 22));
          if ( !WaitForSingleObject(*((HANDLE *)v72 + 3), 0x7530u) )
          {
            v52 = (CActivationState *)StringSid;
            if ( StringSid )
            {
              CActivationStateList::Remove((CActivationStateList *)StringSid, (struct CActivationState *)StringSid);
              v52 = (CActivationState *)StringSid;
            }
            StringSid = 0;
            if ( v52 )
              CActivationState::`scalar deleting destructor'(v52, v47);
            ReleaseProcess(*((struct CProcess **)this + 4));
            *((_QWORD *)this + 4) = 0;
            wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
              &v69,
              0);
            CNamedObject::Release((CNamedObject *)v32);
            *((_DWORD *)this + 3) = 0;
            v53 = lpMem;
            lpMem = 0;
            goto LABEL_84;
          }
        }
        v54 = (CActivationState *)StringSid;
        if ( StringSid )
        {
          CActivationStateList::Remove((CActivationStateList *)StringSid, (struct CActivationState *)StringSid);
          v54 = (CActivationState *)StringSid;
        }
        StringSid = 0;
        if ( v54 )
          CActivationState::`scalar deleting destructor'(v54, v47);
        ReleaseProcess(*((struct CProcess **)this + 4));
        *((_QWORD *)this + 4) = 0;
      }
      else
      {
        v6 = *(int **)v71;
      }
    }
    wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
      &v69,
      0);
    v7 = v72;
  }
  if ( (unsigned int)dword_1801574B8 > 5 )
  {
    v72 = (struct CNamedObject *)lpMem;
    *(_QWORD *)v71 = *((_QWORD *)a2 + 69);
    v55 = *((_QWORD *)a2 + 1);
    if ( v55 )
      v56 = *(_DWORD *)(v55 + 88);
    else
      v56 = 0;
    LODWORD(v66) = v56;
    v57 = (WCHAR *)CClassData::ExecutionPackageName((CClassData *)a3);
    v58 = (HSTRING)*((_QWORD *)a2 + 55);
    StringSid = v57;
    v69 = (CSurrogateListEntry *)WindowsGetStringRawBuffer(v58, 0);
    v75 = CGuidStr::CGuidStr((CGuidStr *)v79, (const struct _GUID *)((char *)a2 + 60));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v59,
      &dword_18014876C,
      (char *)a2 + 560);
  }
  v73 = 0;
  v74 = 0;
  started = CServerTableEntry::StartServerAndWaitImpl(
              this,
              a2,
              (struct CClassData *)a3,
              v70,
              v7,
              (WCHAR *)v32,
              v31,
              v6,
              &v74,
              &v73);
  if ( (unsigned int)dword_1801574B8 > 5 )
  {
    v61 = (const wchar_t *)*((_QWORD *)a2 + 72);
    v62 = (CGuidStr *)*((_QWORD *)a2 + 69);
    v75 = v62;
    if ( !v61 )
    {
      if ( CClassData::AppUserModelID((CClassData *)a3) )
        v61 = CClassData::AppUserModelID((CClassData *)a3);
      else
        v61 = L"null";
    }
    v72 = (struct CNamedObject *)v61;
    v70 = v73;
    LODWORD(v69) = v74;
    LODWORD(StringSid) = *((_DWORD *)this + 4);
    LODWORD(v66) = started;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (_DWORD)v62,
      (unsigned int)byte_1801486F1,
      (_DWORD)a2 + 560,
      v60,
      (__int64)&StringSid,
      (__int64)&v69,
      (__int64)&v66,
      (__int64)&v70,
      (__int64)&v72,
      (__int64)&v75);
  }
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC2,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)(unsigned int)started,
      v65);
    CNamedObject::Release((CNamedObject *)v32);
    *((_DWORD *)this + 3) = 0;
    v51 = lpMem;
    lpMem = 0;
LABEL_53:
    if ( v51 )
      HeapFree(g_hHeap, 0, v51);
    return (unsigned int)started;
  }
  CNamedObject::Release((CNamedObject *)v32);
  *((_DWORD *)this + 3) = 0;
  v53 = lpMem;
  lpMem = 0;
LABEL_84:
  if ( v53 )
    HeapFree(g_hHeap, 0, v53);
  return 0;
}

```

## disassembly

```asm
0x18008dc30  push    rbp
0x18008dc32  push    rbx
0x18008dc33  push    rsi
0x18008dc34  push    rdi
0x18008dc35  push    r12
0x18008dc37  push    r13
0x18008dc39  push    r14
0x18008dc3b  push    r15
0x18008dc3d  lea     rbp, [rsp-28h]
0x18008dc42  sub     rsp, 128h
0x18008dc49  mov     rax, cs:__security_cookie
0x18008dc50  xor     rax, rsp
0x18008dc53  mov     [rbp+60h+var_50], rax
0x18008dc57  mov     r12, [rbp+60h+arg_28]
0x18008dc5e  lea     rax, [rsp+160h+lpMem]
0x18008dc63  mov     rbx, [rbp+60h+arg_20]
0x18008dc6a  xor     r15d, r15d
0x18008dc6d  mov     rsi, rcx
0x18008dc70  mov     [rsp+160h+lpMem], r15
0x18008dc75  mov     rdi, rdx
0x18008dc78  mov     [rbp+60h+var_E0], r9d
0x18008dc7c  mov     [r12], r15d
0x18008dc80  mov     r14, r8
0x18008dc83  mov     rcx, [rdx+10h]
0x18008dc87  lea     r13d, [r15+1]
0x18008dc8b  lea     rdx, [rbp+60h+var_B0]; unsigned __int16 **
0x18008dc8f  mov     [rbp+60h+var_D0], rbx
0x18008dc93  mov     qword ptr [rbp+60h+var_D8], r12
0x18008dc97  mov     [rbp+60h+var_B8], rax
0x18008dc9b  mov     rcx, [rcx+48h]; void *
0x18008dc9f  mov     [rbp+60h+var_B0], r15
0x18008dca3  mov     [rbp+60h+var_A8], r13b
0x18008dca7  call    ?GetPackageNameFromToken@@YAJPEAXPEAPEAG@Z; GetPackageNameFromToken(void *,ushort * *)
0x18008dcac  lea     rcx, [rbp+60h+var_B8]
0x18008dcb0  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x18008dcb5  mov     eax, [rdi+74h]
0x18008dcb8  mov     rcx, r14; this
0x18008dcbb  movzx   r9d, byte ptr [rdi+0BDh]; int
0x18008dcc3  movzx   r8d, byte ptr [rdi+0BCh]; int
0x18008dccb  mov     rdx, [rdi]; void *
0x18008dcce  mov     [rsp+160h+var_120], r15; struct CToken *
0x18008dcd3  mov     dword ptr [rsp+160h+var_128], eax; unsigned int
0x18008dcd7  mov     rax, [rdi+10h]
0x18008dcdb  mov     [rsp+160h+var_130], rax; struct CToken *
0x18008dce0  mov     eax, [rdi+80h]
0x18008dce6  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x18008dcea  mov     dword ptr [rsp+160h+var_140], r13d; int
0x18008dcef  call    ?LaunchOrActivationAllowed@CClassData@@QEAAHPEAXHHHKPEAVCToken@@K1@Z; CClassData::LaunchOrActivationAllowed(void *,int,int,int,ulong,CToken *,ulong,CToken *)
0x18008dcf4  test    eax, eax
0x18008dcf6  jnz     loc_18008DE1B
0x18008dcfc  mov     eax, cs:dword_1801574B8
0x18008dd02  mov     r12d, 80070005h
0x18008dd08  test    eax, eax
0x18008dd0a  jnz     short loc_18008DD28
0x18008dd0c  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18008dd13  jz      loc_18008DDD7
0x18008dd19  xor     ecx, ecx
0x18008dd1b  call    IsWppLevelEnabled
0x18008dd20  test    al, al
0x18008dd22  jz      loc_18008DDD7
0x18008dd28  mov     rcx, [rdi+10h]
0x18008dd2c  lea     rdx, [rsp+160h+StringSid]; StringSid
0x18008dd31  add     rcx, 9Ch; Sid
0x18008dd38  mov     [rsp+160h+StringSid], r15
0x18008dd3d  call    cs:__imp_ConvertSidToStringSidW
0x18008dd44  nop     dword ptr [rax+rax+00h]
0x18008dd49  mov     rax, [rsp+160h+StringSid]
0x18008dd4e  lea     rbx, Class
0x18008dd55  test    rax, rax
0x18008dd58  mov     rsi, rbx
0x18008dd5b  cmovnz  rsi, rax
0x18008dd5f  mov     rax, [rdi+8]
0x18008dd63  test    rax, rax
0x18008dd66  jz      short loc_18008DD75
0x18008dd68  mov     rbx, [rax+180h]
0x18008dd6f  mov     r14d, [rax+58h]
0x18008dd73  jmp     short loc_18008DD78
0x18008dd75  mov     r14d, r15d
0x18008dd78  mov     rcx, [rdi+1B8h]; string
0x18008dd7f  xor     edx, edx; length
0x18008dd81  call    cs:__imp_WindowsGetStringRawBuffer
0x18008dd88  nop     dword ptr [rax+rax+00h]
0x18008dd8d  lea     rdx, [rdi+3Ch]; struct _GUID *
0x18008dd91  mov     r11, rax
0x18008dd94  lea     rcx, [rbp+60h+var_A0]; this
0x18008dd98  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18008dd9d  mov     [rsp+160h+var_110], r12d
0x18008dda2  lea     rdx, aCservertableen_0; "CServerTableEntry::StartServerAndWait"
0x18008dda9  mov     [rsp+160h+var_118], rsi
0x18008ddae  mov     r8d, 9F9h
0x18008ddb4  mov     [rsp+160h+var_120], rbx
0x18008ddb9  mov     dword ptr [rsp+160h+var_128], r14d
0x18008ddbe  mov     [rsp+160h+var_130], r11
0x18008ddc3  mov     [rsp+160h+var_138], rax
0x18008ddc8  call    ??$ComTraceMessageT@PEAGPEBGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K23J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,ushort *,long)
0x18008ddcd  lea     rcx, [rsp+160h+StringSid]
0x18008ddd2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18008ddd7  mov     rcx, [rbp+68h]; this
0x18008dddb  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18008dde2  mov     r9d, r12d; char *
0x18008dde5  mov     edx, 9FAh; void *
0x18008ddea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ddef  mov     r8, [rsp+160h+lpMem]; lpMem
0x18008ddf4  mov     [rsp+160h+lpMem], r15
0x18008ddf9  test    r8, r8
0x18008ddfc  jz      short loc_18008DE13
0x18008ddfe  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008de05  xor     edx, edx; dwFlags
0x18008de07  call    cs:__imp_HeapFree
0x18008de0e  nop     dword ptr [rax+rax+00h]
0x18008de13  mov     eax, r12d
0x18008de16  jmp     loc_18008E524
0x18008de1b  mov     rcx, [rdi+158h]
0x18008de22  test    rcx, rcx
0x18008de25  jz      loc_18008DF76
0x18008de2b  add     rcx, 238h; this
0x18008de32  mov     dword ptr [rsp+160h+var_100], r13d
0x18008de37  lea     r8, [rsp+160h+var_E8]; void **
0x18008de3c  mov     [rsp+160h+var_E8], r15
0x18008de41  lea     rdx, _GUID_000001e2_0000_0000_c000_000000000046; struct _GUID *
0x18008de48  call    ?GetClassInfoW@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::GetClassInfoW(_GUID const &,void * *)
0x18008de4d  test    eax, eax
0x18008de4f  js      loc_18008DF6C
0x18008de55  mov     rcx, [rsp+160h+var_E8]
0x18008de5a  lea     r8, [rsp+160h+StringSid]
0x18008de5f  mov     [rsp+160h+StringSid], r15
0x18008de64  lea     rdx, _GUID_7a0ddd93_7198_4e15_bbd7_427c77b6907a
0x18008de6b  mov     rax, [rcx]
0x18008de6e  mov     rax, [rax+30h]
0x18008de72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de77  test    eax, eax
0x18008de79  js      loc_18008DF62
0x18008de7f  mov     rcx, [rsp+160h+StringSid]
0x18008de84  lea     r8, [rsp+160h+var_100]
0x18008de89  xor     edx, edx
0x18008de8b  mov     rax, [rcx]
0x18008de8e  mov     rax, [rax+18h]
0x18008de92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008de97  test    eax, eax
0x18008de99  js      loc_18008DF62
0x18008de9f  cmp     dword ptr [rsp+160h+var_100], r15d
0x18008dea4  jnz     loc_18008DF62
0x18008deaa  mov     eax, cs:dword_1801574B8
0x18008deb0  test    eax, eax
0x18008deb2  jnz     short loc_18008DEC8
0x18008deb4  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x18008debb  jz      short loc_18008DF24
0x18008debd  xor     ecx, ecx
0x18008debf  call    IsWppLevelEnabled
0x18008dec4  test    al, al
0x18008dec6  jz      short loc_18008DF24
0x18008dec8  mov     rax, [rdi+8]
0x18008decc  test    rax, rax
0x18008decf  jz      short loc_18008DEDD
0x18008ded1  mov     rbx, [rax+180h]
0x18008ded8  mov     esi, [rax+58h]
0x18008dedb  jmp     short loc_18008DEE7
0x18008dedd  lea     rbx, Class
0x18008dee4  mov     esi, r15d
0x18008dee7  mov     rcx, [rdi+1B8h]; string
0x18008deee  xor     edx, edx; length
0x18008def0  call    cs:__imp_WindowsGetStringRawBuffer
0x18008def7  nop     dword ptr [rax+rax+00h]
0x18008defc  lea     rdx, [rdi+3Ch]; struct _GUID *
0x18008df00  mov     r11, rax
0x18008df03  lea     rcx, [rbp+60h+var_A0]; this
0x18008df07  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18008df0c  mov     [rsp+160h+var_120], rbx
0x18008df11  mov     dword ptr [rsp+160h+var_128], esi
0x18008df15  mov     [rsp+160h+var_130], r11
0x18008df1a  mov     [rsp+160h+var_138], rax
0x18008df1f  call    ??$ComTraceMessageT@PEAGPEBGKPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K2J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,long)
0x18008df24  mov     rcx, [rbp+68h]; this
0x18008df28  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18008df2f  mov     r9d, 8007000Eh; char *
0x18008df35  mov     edx, 0A13h; void *
0x18008df3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008df3f  lea     rcx, [rsp+160h+StringSid]
0x18008df44  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18008df49  lea     rcx, [rsp+160h+var_E8]
0x18008df4e  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18008df53  mov     r8, [rsp+160h+lpMem]
0x18008df58  mov     [rsp+160h+lpMem], r15
0x18008df5d  jmp     loc_18008DFE2
0x18008df62  lea     rcx, [rsp+160h+StringSid]
0x18008df67  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18008df6c  lea     rcx, [rsp+160h+var_E8]
0x18008df71  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18008df76  mov     [rsi+10h], r15d
0x18008df7a  mov     rcx, [rsi+30h]; this
0x18008df7e  mov     [rsi+30h], r15
0x18008df82  test    rcx, rcx
0x18008df85  jz      short loc_18008DF8C
0x18008df87  call    ?DeleteBlob@ComBlob@@YAXPEAUtagBLOB@@@Z; ComBlob::DeleteBlob(tagBLOB *)
0x18008df8c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18008df93  movdqu  xmmword ptr [rsi+38h], xmm0
0x18008df98  mov     r15d, r13d
0x18008df9b  lock xadd cs:dword_180158DA0, r15d
0x18008dfa4  add     r15d, r13d
0x18008dfa7  jz      short loc_18008DF98
0x18008dfa9  mov     ecx, r15d; int
0x18008dfac  call    ?ServerProcessLaunchCompletedEvent@@YAPEAVCNamedObject@@J@Z; ServerProcessLaunchCompletedEvent(long)
0x18008dfb1  mov     r13, rax
0x18008dfb4  test    rax, rax
0x18008dfb7  jnz     short loc_18008E006
0x18008dfb9  mov     rcx, [rbp+68h]; this
0x18008dfbd  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18008dfc4  mov     r9d, 8007000Eh; char *
0x18008dfca  mov     edx, 0A2Ch; void *
0x18008dfcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008dfd4  mov     [rsi+0Ch], r13d
0x18008dfd8  mov     r8, [rsp+160h+lpMem]; lpMem
0x18008dfdd  mov     [rsp+160h+lpMem], r13
0x18008dfe2  test    r8, r8
0x18008dfe5  jz      short loc_18008DFFC
0x18008dfe7  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18008dfee  xor     edx, edx; dwFlags
0x18008dff0  call    cs:__imp_HeapFree
0x18008dff7  nop     dword ptr [rax+rax+00h]
0x18008dffc  mov     eax, 8007000Eh
0x18008e001  jmp     loc_18008E524
0x18008e006  cmp     byte ptr [r14+50h], 3
0x18008e00b  jnz     loc_18008E2FE
0x18008e011  mov     rax, [r14+58h]
0x18008e015  mov     [rsp+160h+var_E8], 0
0x18008e01e  lea     rcx, [rax+76h]
0x18008e022  neg     rax
0x18008e025  sbb     rbx, rbx
0x18008e028  and     rbx, rcx
0x18008e02b  jz      loc_18008E2EE
0x18008e031  cmp     byte ptr [r14+0ACh], 0
0x18008e039  jz      short loc_18008E058
0x18008e03b  mov     rcx, [r14+88h]; string
0x18008e042  xor     r12d, r12d
0x18008e045  xor     edx, edx; length
0x18008e047  call    cs:__imp_WindowsGetStringRawBuffer
0x18008e04e  nop     dword ptr [rax+rax+00h]
0x18008e053  mov     r9, rax
0x18008e056  jmp     short loc_18008E061
0x18008e058  xor     r9d, r9d
0x18008e05b  mov     r12d, 800h
0x18008e061  mov     rax, [r14+58h]
0x18008e065  test    rax, rax
0x18008e068  jz      short loc_18008E06F
0x18008e06a  mov     edx, [rax+4Ch]
0x18008e06d  jmp     short loc_18008E072
0x18008e06f  or      edx, 0FFFFFFFFh
0x18008e072  mov     rax, [rdi+8]
0x18008e076  test    rax, rax
0x18008e079  jz      short loc_18008E081
0x18008e07b  mov     rcx, [rax+20h]
0x18008e07f  jmp     short loc_18008E083
0x18008e081  xor     ecx, ecx
0x18008e083  movzx   r8d, byte ptr [rdi+0BCh]
0x18008e08b  mov     dword ptr [rsp+160h+var_120], edx
0x18008e08f  mov     rdx, [rdi+10h]
0x18008e093  mov     dword ptr [rsp+160h+var_128], r12d
0x18008e098  mov     [rsp+160h+var_130], r9
0x18008e09d  mov     r9d, [rdi+0C0h]
0x18008e0a4  mov     [rsp+160h+var_138], rbx
0x18008e0a9  mov     [rsp+160h+var_140], rcx
0x18008e0ae  call    ?Lookup@CSurrogateList@@QEAAPEAVCSurrogateListEntry@@PEAVCToken@@HHPEAG1PEBGKW4ServerProtectionLevel@@@Z; CSurrogateList::Lookup(CToken *,int,int,ushort *,ushort *,ushort const *,ulong,ServerProtectionLevel)
0x18008e0b3  mov     rdx, rax
0x18008e0b6  lea     rcx, [rsp+160h+var_E8]
0x18008e0bb  call    ?reset@?$unique_ptr@VCProcess@@U?$function_deleter@P6AXPEAVCProcess@@@Z$1?ReleaseProcessReference@ResourceMetricAnalysis@@CAX0@Z@wil@@@wistd@@QEAAXPEAVCProcess@@@Z; wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(CProcess *)
0x18008e0c0  mov     rbx, [rsp+160h+var_E8]
0x18008e0c5  test    rbx, rbx
0x18008e0c8  jz      loc_18008E2EA
0x18008e0ce  mov     rax, [rbx+28h]
0x18008e0d2  mov     rcx, [rax+60h]
0x18008e0d6  mov     [rsi+20h], rcx
0x18008e0da  lock inc dword ptr [rcx+10h]
0x18008e0de  mov     rcx, [r13+18h]; hEvent
0x18008e0e2  call    cs:__imp_SetEvent
0x18008e0e9  nop     dword ptr [rax+rax+00h]
0x18008e0ee  mov     r12, qword ptr [rbp+60h+var_D8]
0x18008e0f2  lea     r9, [rdi+0F0h]
0x18008e0f9  mov     [rsi+0Ch], r15d
0x18008e0fd  lea     rdx, [rdi+3Ch]
0x18008e101  lea     r8, [rsp+160h+var_100]
0x18008e106  mov     qword ptr [rbp+60h+var_D8], 0
0x18008e10e  mov     [r12], r15d
0x18008e112  mov     rax, [rsi+20h]
0x18008e116  mov     ecx, [rax+58h]
0x18008e119  lea     rax, [rbp+60h+var_D8]
0x18008e11d  mov     dword ptr [rsp+160h+var_100], ecx
0x18008e121  lea     rcx, [rsp+160h+StringSid]
0x18008e126  mov     [rsp+160h+var_140], rax; int
0x18008e12b  call    ??$make_unique_nothrow@VCActivationState@@AEAU_GUID@@KAEAK$$T@wil@@YA?AV?$unique_ptr@VCActivationState@@U?$default_delete@VCActivationState@@@wistd@@@wistd@@AEAU_GUID@@$$QEAKAEAK$$QEA$$T@Z
0x18008e130  mov     rdx, [rsp+160h+StringSid]; struct CActivationState *
0x18008e135  test    rdx, rdx
0x18008e138  jz      short loc_18008E13F
0x18008e13a  call    ?Insert@CActivationStateList@@QEAAXPEAVCActivationState@@@Z; CActivationStateList::Insert(CActivationState *)
0x18008e13f  mov     rcx, [rdi+0A0h]
0x18008e146  add     rcx, 18h; Uuid
0x18008e14a  call    cs:__imp_UuidCreate
0x18008e151  nop     dword ptr [rax+rax+00h]
0x18008e156  mov     rcx, r14; this
0x18008e159  mov     dword ptr [rsp+160h+var_100], 0
0x18008e161  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
  ... truncated ...
```
