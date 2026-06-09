# CServerTableEntry::StartServerAndWait(ACTIVATION_PARAMS *,CClassData *,int,CNamedObject *,long *)

- ea: `0x1800890dc`
- end: `0x1800899a8`
- name: `?StartServerAndWait@CServerTableEntry@@QEAAJPEAUACTIVATION_PARAMS@@PEAVCClassData@@HPEAVCNamedObject@@PEAJ@Z`
- size: `2252`
- prototype: `__int64 __usercall@<rax>(CServerTableEntry *__hidden this@<rcx>, struct ACTIVATION_PARAMS *@<rdx>, struct CClassData *@<r8>, int@<r9d>, struct CNamedObject *, int *)`
- caller_count: `1`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005c80`

## callees

- `0x180003064`
- `0x180008648`
- `0x18000b710`
- `0x180014870`
- `0x180016160`
- `0x180019a3c`
- `0x180022114`
- `0x180022138`
- `0x180022274`
- `0x1800247a8`
- `0x180026a90`
- `0x18002ba28`
- `0x18002f058`
- `0x180034540`
- `0x18003d828`
- `0x18004fee4`
- `0x18005d7f4`
- `0x18005f80c`
- `0x180063b20`
- `0x180063cac`
- `0x1800653d0`
- `0x180067898`
- `0x18006821c`
- `0x1800697b0`
- `0x180073764`
- `0x18007f0b0`
- `0x1800890dc`
- `0x1800b27e0`
- `0x1800f3c5c`
- `0x1800f3f94`
- `0x1800f88d0`
- `0x1800f8bc0`
- `0x18010b010`

## import_xrefs

- `RPCRT4!UuidCreate` at `0x1800895cc`
- `RPCRT4!UuidCreate` at `0x1800895cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800892a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089484`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089980`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800892a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089484`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180089980`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008956a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18008956a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800896c2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800896c2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800891e9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800891e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008938a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800894d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800897bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180089227`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008938a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800894d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800897bb`

## string_xrefs

- `0x18008927b`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800893bc`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180089451`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008960e`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18008991f`: `onecore\com\combase\rpcss\olescm\class.cxx`

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
  const WCHAR *v15; // rbx
  LPWSTR v16; // rsi
  __int64 v17; // rax
  int v18; // r14d
  CGuidStr *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // r11
  void *v23; // r8
  __int64 v25; // rcx
  void *v26; // r8
  ComBlob *v27; // rcx
  int v28; // r15d
  HANDLE *v29; // r13
  HSTRING v30; // rax
  __int64 v31; // rbx
  int v32; // r12d
  PCWSTR StringRawBuffer; // r9
  HSTRING v34; // rax
  int v35; // edx
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  CSurrogateListEntry *v39; // rbx
  __int64 v40; // rcx
  CActivationStateList *v41; // rcx
  char v42; // al
  int Dll; // eax
  unsigned int v44; // edx
  int started; // ebx
  unsigned int v46; // edx
  CActivationState *v47; // rcx
  void *v48; // r8
  CActivationState *v49; // rcx
  void *v50; // r8
  CActivationState *v51; // rcx
  __int64 v52; // rax
  int v53; // ecx
  WCHAR *v54; // rax
  HSTRING v55; // rcx
  __int64 v56; // rcx
  int v57; // r9d
  const wchar_t *v58; // rax
  CGuidStr *v59; // rcx
  int v60; // [rsp+20h] [rbp-E0h]
  int v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+20h] [rbp-E0h]
  char *v63; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-90h] BYREF
  CSurrogateListEntry *v66; // [rsp+78h] [rbp-88h] BYREF
  int v67; // [rsp+80h] [rbp-80h] BYREF
  int v68[2]; // [rsp+88h] [rbp-78h] BYREF
  struct CNamedObject *v69; // [rsp+90h] [rbp-70h] BYREF
  int v70; // [rsp+98h] [rbp-68h] BYREF
  int v71; // [rsp+9Ch] [rbp-64h] BYREF
  CGuidStr *v72; // [rsp+A0h] [rbp-60h] BYREF
  LPVOID *p_lpMem; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int16 *v74; // [rsp+B0h] [rbp-50h] BYREF
  char v75; // [rsp+B8h] [rbp-48h]
  _BYTE v76[80]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v6 = a6;
  v7 = a5;
  lpMem = 0;
  v67 = a4;
  *a6 = 0;
  v11 = *((_QWORD *)a2 + 2);
  v69 = a5;
  *(_QWORD *)v68 = a6;
  p_lpMem = &lpMem;
  v12 = *(void **)(v11 + 72);
  v74 = 0;
  v75 = 1;
  GetPackageNameFromToken(v12, &v74);
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
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      v14 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
      StringSid = 0;
      ConvertSidToStringSidW(v14, &StringSid);
      v15 = &Class;
      v16 = (LPWSTR)&Class;
      if ( StringSid )
        v16 = StringSid;
      v17 = *((_QWORD *)a2 + 1);
      if ( v17 )
      {
        v15 = *(const WCHAR **)(v17 + 384);
        v18 = *(_DWORD *)(v17 + 88);
      }
      else
      {
        v18 = 0;
      }
      WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
      v19 = CGuidStr::CGuidStr((CGuidStr *)v76, (const struct _GUID *)((char *)a2 + 60));
      ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
        v20,
        (__int64)"CServerTableEntry::StartServerAndWait",
        0x9F9u,
        v21,
        v60,
        (__int64)v19,
        v22,
        v18,
        (__int64)v15,
        (__int64)v16,
        0x80070005);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9FA,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)0x80070005LL,
      v60);
    v23 = lpMem;
    lpMem = 0;
    if ( v23 )
      HeapFree(g_hHeap, 0, v23);
    return 2147942405LL;
  }
  v25 = *((_QWORD *)a2 + 43);
  if ( v25 )
  {
    LODWORD(v63) = 1;
    v66 = 0;
    if ( (int)ActivationPropertiesIn::GetClassInfoW(
                (ActivationPropertiesIn *)(v25 + 568),
                &GUID_000001e2_0000_0000_c000_000000000046,
                (void **)&v66) >= 0 )
    {
      StringSid = 0;
      if ( (*(int (__fastcall **)(CSurrogateListEntry *, GUID *, LPWSTR *))(*(_QWORD *)v66 + 48LL))(
             v66,
             &GUID_7a0ddd93_7198_4e15_bbd7_427c77b6907a,
             &StringSid) >= 0
        && (*(int (__fastcall **)(LPWSTR, _QWORD, char **))(*(_QWORD *)StringSid + 24LL))(StringSid, 0, &v63) >= 0
        && !(_DWORD)v63 )
      {
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
          CGuidStr::CGuidStr((CGuidStr *)v76, (const struct _GUID *)((char *)a2 + 60));
          ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,long>();
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA13,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)0x8007000ELL,
          v60);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&StringSid);
        wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v66);
        v26 = lpMem;
        lpMem = 0;
        goto LABEL_32;
      }
      wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&StringSid);
    }
    wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(&v66);
  }
  *((_DWORD *)this + 4) = 0;
  v27 = (ComBlob *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v27 )
    ComBlob::DeleteBlob(v27, v13);
  *(GUID *)((char *)this + 56) = GUID_NULL;
  do
    v28 = _InterlockedIncrement(&dword_18014FC90);
  while ( !v28 );
  v29 = (HANDLE *)ServerProcessLaunchCompletedEvent(v28);
  if ( !v29 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2C,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)0x8007000ELL,
      v60);
    *((_DWORD *)this + 3) = 0;
    v26 = lpMem;
    lpMem = 0;
LABEL_32:
    if ( v26 )
      HeapFree(g_hHeap, 0, v26);
    return 2147942414LL;
  }
  if ( *((_BYTE *)a3 + 80) == 3 )
  {
    v30 = a3[11];
    v66 = 0;
    v31 = ((unsigned __int64)v30 + 118) & -(__int64)(v30 != 0);
    if ( v31 )
    {
      if ( *((_BYTE *)a3 + 172) )
      {
        v32 = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(a3[17], 0);
      }
      else
      {
        StringRawBuffer = 0;
        v32 = 2048;
      }
      v34 = a3[11];
      if ( v34 )
        v35 = *((_DWORD *)v34 + 19);
      else
        v35 = -1;
      v36 = *((_QWORD *)a2 + 1);
      if ( v36 )
        v37 = *(_QWORD *)(v36 + 32);
      else
        v37 = 0;
      v38 = CSurrogateList::Lookup(
              v37,
              *((_QWORD *)a2 + 2),
              *((unsigned __int8 *)a2 + 188),
              *((unsigned int *)a2 + 48),
              v37,
              v31,
              StringRawBuffer,
              v32,
              v35);
      wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
        &v66,
        v38);
      v39 = v66;
      if ( v66 )
      {
        v40 = *(_QWORD *)(*((_QWORD *)v66 + 5) + 96LL);
        *((_QWORD *)this + 4) = v40;
        _InterlockedIncrement((volatile signed __int32 *)(v40 + 16));
        SetEvent(v29[3]);
        v6 = *(int **)v68;
        *((_DWORD *)this + 3) = v28;
        *(_QWORD *)v68 = 0;
        *v6 = v28;
        LODWORD(v63) = *(_DWORD *)(*((_QWORD *)this + 4) + 88LL);
        wil::make_unique_nothrow<CActivationState,_GUID &,unsigned long,unsigned long &,std::nullptr_t>(
          (CActivationState **)&StringSid,
          (struct _GUID *)((char *)a2 + 60),
          (unsigned int *)&v63,
          (unsigned int *)a2 + 60,
          (void **)v68);
        if ( StringSid )
          CActivationStateList::Insert(v41, (struct CActivationState *)StringSid);
        UuidCreate((UUID *)(*((_QWORD *)a2 + 20) + 24LL));
        LODWORD(v63) = 0;
        v42 = CClassData::AppIDFlags((CClassData *)a3);
        Dll = CSurrogateListEntry::LoadDll(v39, a2, gfIssueActivationRpcAtIdentify | v42 & 4, (int *)&v63);
        started = (int)v63;
        if ( (int)v63 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA7B,
            (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
            (const char *)(unsigned int)v63,
            v61);
          v47 = (CActivationState *)StringSid;
          if ( StringSid )
          {
            CActivationStateList::Remove((CActivationStateList *)StringSid, (struct CActivationState *)StringSid);
            v47 = (CActivationState *)StringSid;
          }
          StringSid = 0;
          if ( v47 )
            CActivationState::`scalar deleting destructor'(v47, v46);
          ReleaseProcess(*((struct CProcess **)this + 4));
          *((_QWORD *)this + 4) = 0;
          wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
            &v66,
            0);
          CNamedObject::Release((CNamedObject *)v29);
          *((_DWORD *)this + 3) = 0;
          v48 = lpMem;
          lpMem = 0;
          goto LABEL_55;
        }
        if ( Dll )
        {
          ClearOrpcThat(*((struct tagORPCTHAT **)a2 + 21));
          ClearLocalThat(*((struct __MIDL_XmitDefs_0011 **)a2 + 22));
          if ( !WaitForSingleObject(*((HANDLE *)v69 + 3), 0x7530u) )
          {
            v49 = (CActivationState *)StringSid;
            if ( StringSid )
            {
              CActivationStateList::Remove((CActivationStateList *)StringSid, (struct CActivationState *)StringSid);
              v49 = (CActivationState *)StringSid;
            }
            StringSid = 0;
            if ( v49 )
              CActivationState::`scalar deleting destructor'(v49, v44);
            ReleaseProcess(*((struct CProcess **)this + 4));
            *((_QWORD *)this + 4) = 0;
            wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
              &v66,
              0);
            CNamedObject::Release((CNamedObject *)v29);
            *((_DWORD *)this + 3) = 0;
            v50 = lpMem;
            lpMem = 0;
            goto LABEL_86;
          }
        }
        v51 = (CActivationState *)StringSid;
        if ( StringSid )
        {
          CActivationStateList::Remove((CActivationStateList *)StringSid, (struct CActivationState *)StringSid);
          v51 = (CActivationState *)StringSid;
        }
        StringSid = 0;
        if ( v51 )
          CActivationState::`scalar deleting destructor'(v51, v44);
        ReleaseProcess(*((struct CProcess **)this + 4));
        *((_QWORD *)this + 4) = 0;
      }
      else
      {
        v6 = *(int **)v68;
      }
    }
    wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&private: static void ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(
      &v66,
      0);
    v7 = v69;
  }
  if ( (unsigned int)dword_18014E4B8 > 5 )
  {
    v69 = (struct CNamedObject *)lpMem;
    *(_QWORD *)v68 = *((_QWORD *)a2 + 69);
    v52 = *((_QWORD *)a2 + 1);
    if ( v52 )
      v53 = *(_DWORD *)(v52 + 88);
    else
      v53 = 0;
    LODWORD(v63) = v53;
    v54 = (WCHAR *)CClassData::ExecutionPackageName((CClassData *)a3);
    v55 = (HSTRING)*((_QWORD *)a2 + 55);
    StringSid = v54;
    v66 = (CSurrogateListEntry *)WindowsGetStringRawBuffer(v55, 0);
    v72 = CGuidStr::CGuidStr((CGuidStr *)v76, (const struct _GUID *)((char *)a2 + 60));
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
      v56,
      byte_18013F751,
      (char *)a2 + 560);
  }
  v70 = 0;
  v71 = 0;
  started = CServerTableEntry::StartServerAndWaitImpl(
              this,
              a2,
              (struct CClassData *)a3,
              v67,
              v7,
              (WCHAR *)v29,
              v28,
              v6,
              &v71,
              &v70);
  if ( (unsigned int)dword_18014E4B8 > 5 )
  {
    v58 = (const wchar_t *)*((_QWORD *)a2 + 72);
    v59 = (CGuidStr *)*((_QWORD *)a2 + 69);
    v72 = v59;
    if ( !v58 )
    {
      if ( CClassData::AppUserModelID((CClassData *)a3) )
        v58 = CClassData::AppUserModelID((CClassData *)a3);
      else
        v58 = L"null";
    }
    v69 = (struct CNamedObject *)v58;
    v67 = v70;
    LODWORD(v66) = v71;
    LODWORD(StringSid) = *((_DWORD *)this + 4);
    LODWORD(v63) = started;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (_DWORD)v59,
      (unsigned int)byte_18013F7D3,
      (_DWORD)a2 + 560,
      v57,
      (__int64)&StringSid,
      (__int64)&v66,
      (__int64)&v63,
      (__int64)&v67,
      (__int64)&v69,
      (__int64)&v72);
  }
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC2,
      (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
      (const char *)(unsigned int)started,
      v62);
    CNamedObject::Release((CNamedObject *)v29);
    *((_DWORD *)this + 3) = 0;
    v48 = lpMem;
    lpMem = 0;
LABEL_55:
    if ( v48 )
      HeapFree(g_hHeap, 0, v48);
    return (unsigned int)started;
  }
  CNamedObject::Release((CNamedObject *)v29);
  *((_DWORD *)this + 3) = 0;
  v50 = lpMem;
  lpMem = 0;
LABEL_86:
  if ( v50 )
    HeapFree(g_hHeap, 0, v50);
  return 0;
}

```

## disassembly

```asm
0x1800890dc  push    rbp
0x1800890de  push    rbx
0x1800890df  push    rsi
0x1800890e0  push    rdi
0x1800890e1  push    r12
0x1800890e3  push    r13
0x1800890e5  push    r14
0x1800890e7  push    r15
0x1800890e9  lea     rbp, [rsp-28h]
0x1800890ee  sub     rsp, 128h
0x1800890f5  mov     rax, cs:__security_cookie
0x1800890fc  xor     rax, rsp
0x1800890ff  mov     [rbp+60h+var_50], rax
0x180089103  mov     r12, [rbp+60h+arg_28]
0x18008910a  lea     rax, [rsp+160h+lpMem]
0x18008910f  mov     rbx, [rbp+60h+arg_20]
0x180089116  xor     r15d, r15d
0x180089119  mov     rsi, rcx
0x18008911c  mov     [rsp+160h+lpMem], r15
0x180089121  mov     rdi, rdx
0x180089124  mov     [rbp+60h+var_E0], r9d
0x180089128  mov     [r12], r15d
0x18008912c  mov     r14, r8
0x18008912f  mov     rcx, [rdx+10h]
0x180089133  lea     r13d, [r15+1]
0x180089137  lea     rdx, [rbp+60h+var_B0]; unsigned __int16 **
0x18008913b  mov     [rbp+60h+var_D0], rbx
0x18008913f  mov     qword ptr [rbp+60h+var_D8], r12
0x180089143  mov     [rbp+60h+var_B8], rax
0x180089147  mov     rcx, [rcx+48h]; void *
0x18008914b  mov     [rbp+60h+var_B0], r15
0x18008914f  mov     [rbp+60h+var_A8], r13b
0x180089153  call    ?GetPackageNameFromToken@@YAJPEAXPEAPEAG@Z; GetPackageNameFromToken(void *,ushort * *)
0x180089158  lea     rcx, [rbp+60h+var_B8]
0x18008915c  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?MIDL_user_free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&MIDL_user_free(void *)>>>(void)
0x180089161  mov     eax, [rdi+74h]
0x180089164  mov     rcx, r14; this
0x180089167  movzx   r9d, byte ptr [rdi+0BDh]; int
0x18008916f  movzx   r8d, byte ptr [rdi+0BCh]; int
0x180089177  mov     rdx, [rdi]; void *
0x18008917a  mov     [rsp+160h+var_120], r15; struct CToken *
0x18008917f  mov     dword ptr [rsp+160h+var_128], eax; unsigned int
0x180089183  mov     rax, [rdi+10h]
0x180089187  mov     [rsp+160h+var_130], rax; struct CToken *
0x18008918c  mov     eax, [rdi+80h]
0x180089192  mov     dword ptr [rsp+160h+var_138], eax; unsigned int
0x180089196  mov     dword ptr [rsp+160h+var_140], r13d; int
0x18008919b  call    ?LaunchOrActivationAllowed@CClassData@@QEAAHPEAXHHHKPEAVCToken@@K1@Z; CClassData::LaunchOrActivationAllowed(void *,int,int,int,ulong,CToken *,ulong,CToken *)
0x1800891a0  test    eax, eax
0x1800891a2  jnz     loc_1800892B5
0x1800891a8  mov     eax, cs:dword_18014E4B8
0x1800891ae  mov     r12d, 80070005h
0x1800891b4  test    eax, eax
0x1800891b6  jnz     short loc_1800891D4
0x1800891b8  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x1800891bf  jz      loc_180089277
0x1800891c5  xor     ecx, ecx
0x1800891c7  call    IsWppLevelEnabled
0x1800891cc  test    al, al
0x1800891ce  jz      loc_180089277
0x1800891d4  mov     rcx, [rdi+10h]
0x1800891d8  lea     rdx, [rsp+160h+StringSid]; StringSid
0x1800891dd  add     rcx, 9Ch; Sid
0x1800891e4  mov     [rsp+160h+StringSid], r15
0x1800891e9  call    cs:__imp_ConvertSidToStringSidW
0x1800891ef  mov     rax, [rsp+160h+StringSid]
0x1800891f4  lea     rbx, Class
0x1800891fb  test    rax, rax
0x1800891fe  mov     rsi, rbx
0x180089201  cmovnz  rsi, rax
0x180089205  mov     rax, [rdi+8]
0x180089209  test    rax, rax
0x18008920c  jz      short loc_18008921B
0x18008920e  mov     rbx, [rax+180h]
0x180089215  mov     r14d, [rax+58h]
0x180089219  jmp     short loc_18008921E
0x18008921b  mov     r14d, r15d
0x18008921e  mov     rcx, [rdi+1B8h]; string
0x180089225  xor     edx, edx; length
0x180089227  call    cs:__imp_WindowsGetStringRawBuffer
0x18008922d  lea     rdx, [rdi+3Ch]; struct _GUID *
0x180089231  mov     r11, rax
0x180089234  lea     rcx, [rbp+60h+var_A0]; this
0x180089238  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18008923d  mov     [rsp+160h+var_110], r12d
0x180089242  lea     rdx, aCservertableen_0; "CServerTableEntry::StartServerAndWait"
0x180089249  mov     [rsp+160h+var_118], rsi
0x18008924e  mov     r8d, 9F9h
0x180089254  mov     [rsp+160h+var_120], rbx
0x180089259  mov     dword ptr [rsp+160h+var_128], r14d
0x18008925e  mov     [rsp+160h+var_130], r11
0x180089263  mov     [rsp+160h+var_138], rax
0x180089268  call    ??$ComTraceMessageT@PEAGPEBGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K23J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,ushort *,long)
0x18008926d  lea     rcx, [rsp+160h+StringSid]
0x180089272  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180089277  mov     rcx, [rbp+68h]; this
0x18008927b  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180089282  mov     r9d, r12d; char *
0x180089285  mov     edx, 9FAh; void *
0x18008928a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008928f  mov     r8, [rsp+160h+lpMem]; lpMem
0x180089294  mov     [rsp+160h+lpMem], r15
0x180089299  test    r8, r8
0x18008929c  jz      short loc_1800892AD
0x18008929e  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800892a5  xor     edx, edx; dwFlags
0x1800892a7  call    cs:__imp_HeapFree
0x1800892ad  mov     eax, r12d
0x1800892b0  jmp     loc_180089988
0x1800892b5  mov     rcx, [rdi+158h]
0x1800892bc  test    rcx, rcx
0x1800892bf  jz      loc_18008940A
0x1800892c5  add     rcx, 238h; this
0x1800892cc  mov     dword ptr [rsp+160h+var_100], r13d
0x1800892d1  lea     r8, [rsp+160h+var_E8]; void **
0x1800892d6  mov     [rsp+160h+var_E8], r15
0x1800892db  lea     rdx, _GUID_000001e2_0000_0000_c000_000000000046; struct _GUID *
0x1800892e2  call    ?GetClassInfoW@ActivationPropertiesIn@@UEAAJAEBU_GUID@@PEAPEAX@Z; ActivationPropertiesIn::GetClassInfoW(_GUID const &,void * *)
0x1800892e7  test    eax, eax
0x1800892e9  js      loc_180089400
0x1800892ef  mov     rcx, [rsp+160h+var_E8]
0x1800892f4  lea     r8, [rsp+160h+StringSid]
0x1800892f9  mov     [rsp+160h+StringSid], r15
0x1800892fe  lea     rdx, _GUID_7a0ddd93_7198_4e15_bbd7_427c77b6907a
0x180089305  mov     rax, [rcx]
0x180089308  mov     rax, [rax+30h]
0x18008930c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089311  test    eax, eax
0x180089313  js      loc_1800893F6
0x180089319  mov     rcx, [rsp+160h+StringSid]
0x18008931e  lea     r8, [rsp+160h+var_100]
0x180089323  xor     edx, edx
0x180089325  mov     rax, [rcx]
0x180089328  mov     rax, [rax+18h]
0x18008932c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089331  test    eax, eax
0x180089333  js      loc_1800893F6
0x180089339  cmp     dword ptr [rsp+160h+var_100], r15d
0x18008933e  jnz     loc_1800893F6
0x180089344  mov     eax, cs:dword_18014E4B8
0x18008934a  test    eax, eax
0x18008934c  jnz     short loc_180089362
0x18008934e  cmp     cs:?gfEnableTracing@@3HA, r15d; int gfEnableTracing
0x180089355  jz      short loc_1800893B8
0x180089357  xor     ecx, ecx
0x180089359  call    IsWppLevelEnabled
0x18008935e  test    al, al
0x180089360  jz      short loc_1800893B8
0x180089362  mov     rax, [rdi+8]
0x180089366  test    rax, rax
0x180089369  jz      short loc_180089377
0x18008936b  mov     rbx, [rax+180h]
0x180089372  mov     esi, [rax+58h]
0x180089375  jmp     short loc_180089381
0x180089377  lea     rbx, Class
0x18008937e  mov     esi, r15d
0x180089381  mov     rcx, [rdi+1B8h]; string
0x180089388  xor     edx, edx; length
0x18008938a  call    cs:__imp_WindowsGetStringRawBuffer
0x180089390  lea     rdx, [rdi+3Ch]; struct _GUID *
0x180089394  mov     r11, rax
0x180089397  lea     rcx, [rbp+60h+var_A0]; this
0x18008939b  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x1800893a0  mov     [rsp+160h+var_120], rbx
0x1800893a5  mov     dword ptr [rsp+160h+var_128], esi
0x1800893a9  mov     [rsp+160h+var_130], r11
0x1800893ae  mov     [rsp+160h+var_138], rax
0x1800893b3  call    ??$ComTraceMessageT@PEAGPEBGKPEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K2J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,long)
0x1800893b8  mov     rcx, [rbp+68h]; this
0x1800893bc  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800893c3  mov     r9d, 8007000Eh; char *
0x1800893c9  mov     edx, 0A13h; void *
0x1800893ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800893d3  lea     rcx, [rsp+160h+StringSid]
0x1800893d8  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800893dd  lea     rcx, [rsp+160h+var_E8]
0x1800893e2  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x1800893e7  mov     r8, [rsp+160h+lpMem]
0x1800893ec  mov     [rsp+160h+lpMem], r15
0x1800893f1  jmp     loc_180089476
0x1800893f6  lea     rcx, [rsp+160h+StringSid]
0x1800893fb  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x180089400  lea     rcx, [rsp+160h+var_E8]
0x180089405  call    ??1?$com_ptr_t@UIComWinRTActivationProperties@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>::~com_ptr_t<IComWinRTActivationProperties,wil::err_returncode_policy>(void)
0x18008940a  mov     [rsi+10h], r15d
0x18008940e  mov     rcx, [rsi+30h]; this
0x180089412  mov     [rsi+30h], r15
0x180089416  test    rcx, rcx
0x180089419  jz      short loc_180089420
0x18008941b  call    ?DeleteBlob@ComBlob@@YAXPEAUtagBLOB@@@Z; ComBlob::DeleteBlob(tagBLOB *)
0x180089420  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180089427  movdqu  xmmword ptr [rsi+38h], xmm0
0x18008942c  mov     r15d, r13d
0x18008942f  lock xadd cs:dword_18014FC90, r15d
0x180089438  add     r15d, r13d
0x18008943b  jz      short loc_18008942C
0x18008943d  mov     ecx, r15d; int
0x180089440  call    ?ServerProcessLaunchCompletedEvent@@YAPEAVCNamedObject@@J@Z; ServerProcessLaunchCompletedEvent(long)
0x180089445  mov     r13, rax
0x180089448  test    rax, rax
0x18008944b  jnz     short loc_180089494
0x18008944d  mov     rcx, [rbp+68h]; this
0x180089451  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180089458  mov     r9d, 8007000Eh; char *
0x18008945e  mov     edx, 0A2Ch; void *
0x180089463  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180089468  mov     [rsi+0Ch], r13d
0x18008946c  mov     r8, [rsp+160h+lpMem]; lpMem
0x180089471  mov     [rsp+160h+lpMem], r13
0x180089476  test    r8, r8
0x180089479  jz      short loc_18008948A
0x18008947b  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180089482  xor     edx, edx; dwFlags
0x180089484  call    cs:__imp_HeapFree
0x18008948a  mov     eax, 8007000Eh
0x18008948f  jmp     loc_180089988
0x180089494  cmp     byte ptr [r14+50h], 3
0x180089499  jnz     loc_18008976E
0x18008949f  mov     rax, [r14+58h]
0x1800894a3  mov     [rsp+160h+var_E8], 0
0x1800894ac  lea     rcx, [rax+76h]
0x1800894b0  neg     rax
0x1800894b3  sbb     rbx, rbx
0x1800894b6  and     rbx, rcx
0x1800894b9  jz      loc_18008975E
0x1800894bf  cmp     byte ptr [r14+0ACh], 0
0x1800894c7  jz      short loc_1800894E0
0x1800894c9  mov     rcx, [r14+88h]; string
0x1800894d0  xor     r12d, r12d
0x1800894d3  xor     edx, edx; length
0x1800894d5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800894db  mov     r9, rax
0x1800894de  jmp     short loc_1800894E9
0x1800894e0  xor     r9d, r9d
0x1800894e3  mov     r12d, 800h
0x1800894e9  mov     rax, [r14+58h]
0x1800894ed  test    rax, rax
0x1800894f0  jz      short loc_1800894F7
0x1800894f2  mov     edx, [rax+4Ch]
0x1800894f5  jmp     short loc_1800894FA
0x1800894f7  or      edx, 0FFFFFFFFh
0x1800894fa  mov     rax, [rdi+8]
0x1800894fe  test    rax, rax
0x180089501  jz      short loc_180089509
0x180089503  mov     rcx, [rax+20h]
0x180089507  jmp     short loc_18008950B
0x180089509  xor     ecx, ecx
0x18008950b  movzx   r8d, byte ptr [rdi+0BCh]
0x180089513  mov     dword ptr [rsp+160h+var_120], edx
0x180089517  mov     rdx, [rdi+10h]
0x18008951b  mov     dword ptr [rsp+160h+var_128], r12d
0x180089520  mov     [rsp+160h+var_130], r9
0x180089525  mov     r9d, [rdi+0C0h]
0x18008952c  mov     [rsp+160h+var_138], rbx
0x180089531  mov     [rsp+160h+var_140], rcx
0x180089536  call    ?Lookup@CSurrogateList@@QEAAPEAVCSurrogateListEntry@@PEAVCToken@@HHPEAG1PEBGKW4ServerProtectionLevel@@@Z; CSurrogateList::Lookup(CToken *,int,int,ushort *,ushort *,ushort const *,ulong,ServerProtectionLevel)
0x18008953b  mov     rdx, rax
0x18008953e  lea     rcx, [rsp+160h+var_E8]
0x180089543  call    ?reset@?$unique_ptr@VCProcess@@U?$function_deleter@P6AXPEAVCProcess@@@Z$1?ReleaseProcessReference@ResourceMetricAnalysis@@CAX0@Z@wil@@@wistd@@QEAAXPEAVCProcess@@@Z; wistd::unique_ptr<CProcess,wil::function_deleter<void (*)(CProcess *),&ResourceMetricAnalysis::ReleaseProcessReference(CProcess *)>>::reset(CProcess *)
0x180089548  mov     rbx, [rsp+160h+var_E8]
0x18008954d  test    rbx, rbx
0x180089550  jz      loc_18008975A
0x180089556  mov     rax, [rbx+28h]
0x18008955a  mov     rcx, [rax+60h]
0x18008955e  mov     [rsi+20h], rcx
0x180089562  lock inc dword ptr [rcx+10h]
0x180089566  mov     rcx, [r13+18h]; hEvent
0x18008956a  call    cs:__imp_SetEvent
0x180089570  mov     r12, qword ptr [rbp+60h+var_D8]
0x180089574  lea     r9, [rdi+0F0h]
0x18008957b  mov     [rsi+0Ch], r15d
0x18008957f  lea     rdx, [rdi+3Ch]
0x180089583  lea     r8, [rsp+160h+var_100]
0x180089588  mov     qword ptr [rbp+60h+var_D8], 0
0x180089590  mov     [r12], r15d
0x180089594  mov     rax, [rsi+20h]
0x180089598  mov     ecx, [rax+58h]
0x18008959b  lea     rax, [rbp+60h+var_D8]
0x18008959f  mov     dword ptr [rsp+160h+var_100], ecx
0x1800895a3  lea     rcx, [rsp+160h+StringSid]
0x1800895a8  mov     [rsp+160h+var_140], rax; int
0x1800895ad  call    ??$make_unique_nothrow@VCActivationState@@AEAU_GUID@@KAEAK$$T@wil@@YA?AV?$unique_ptr@VCActivationState@@U?$default_delete@VCActivationState@@@wistd@@@wistd@@AEAU_GUID@@$$QEAKAEAK$$QEA$$T@Z
0x1800895b2  mov     rdx, [rsp+160h+StringSid]; struct CActivationState *
0x1800895b7  test    rdx, rdx
0x1800895ba  jz      short loc_1800895C1
0x1800895bc  call    ?Insert@CActivationStateList@@QEAAXPEAVCActivationState@@@Z; CActivationStateList::Insert(CActivationState *)
0x1800895c1  mov     rcx, [rdi+0A0h]
0x1800895c8  add     rcx, 18h; Uuid
0x1800895cc  call    cs:__imp_UuidCreate
0x1800895d2  mov     rcx, r14; this
0x1800895d5  mov     dword ptr [rsp+160h+var_100], 0
0x1800895dd  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x1800895e2  and     eax, 4
0x1800895e5  lea     r9, [rsp+160h+var_100]; int *
0x1800895ea  or      eax, cs:?gfIssueActivationRpcAtIdentify@@3HA; int gfIssueActivationRpcAtIdentify
0x1800895f0  mov     rdx, rdi; struct ACTIVATION_PARAMS *
0x1800895f3  mov     r8d, eax; int
0x1800895f6  mov     rcx, rbx; this
0x1800895f9  call    ?LoadDll@CSurrogateListEntry@@QEAAHPEAUACTIVATION_PARAMS@@HPEAJ@Z; CSurrogateListEntry::LoadDll(ACTIVATION_PARAMS *,int,long *)
0x1800895fe  mov     ebx, dword ptr [rsp+160h+var_100]
  ... truncated ...
```
