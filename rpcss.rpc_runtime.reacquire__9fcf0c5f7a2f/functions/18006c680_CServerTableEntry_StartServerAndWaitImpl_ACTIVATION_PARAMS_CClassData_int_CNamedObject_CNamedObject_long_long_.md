# CServerTableEntry::StartServerAndWaitImpl(ACTIVATION_PARAMS *,CClassData *,int,CNamedObject *,CNamedObject *,long,long *,int *,long *)

- ea: `0x18006c680`
- end: `0x18006d03d`
- name: `?StartServerAndWaitImpl@CServerTableEntry@@AEAAJPEAUACTIVATION_PARAMS@@PEAVCClassData@@HPEAVCNamedObject@@2JPEAJPEAH3@Z`
- size: `2493`
- prototype: `int(CServerTableEntry *__hidden this, struct ACTIVATION_PARAMS *, struct CClassData *, int, struct CNamedObject *, struct CNamedObject *, int, int *, int *, int *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008dc30`

## callees

- `0x18001a374`
- `0x1800210f8`
- `0x180022ddc`
- `0x180023dc4`
- `0x180024590`
- `0x180025088`
- `0x18002c408`
- `0x1800307c0`
- `0x180034260`
- `0x180046758`
- `0x180046930`
- `0x180046994`
- `0x18005126c`
- `0x180051484`
- `0x180051900`
- `0x1800522a0`
- `0x18005ac00`
- `0x18006313c`
- `0x180069324`
- `0x18006c680`
- `0x180074428`
- `0x180074ee4`
- `0x180077f10`
- `0x18007f234`
- `0x180080470`
- `0x1800830a8`
- `0x180085a80`
- `0x180088ec8`
- `0x18009e160`
- `0x1800a5144`
- `0x1800a75d0`
- `0x1800a7b34`
- `0x1800b7ac0`
- `0x1800fb9a0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c9ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ca84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ccd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c9ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ca84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cab8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ccd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006cd8c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006cb2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006cb2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c7bd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c850`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c7bd`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c850`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cc44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ccaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ce72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cf7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cc44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ccaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006ce72`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006cf7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c95e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cee8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cf28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c894`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006c95e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cee8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006cf28`

## string_xrefs

- `0x18006c769`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006c934`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006c9c7`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006ca57`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006cba9`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006cc22`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006cc8d`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006cd5d`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006ce50`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18006cf5a`: `onecore\com\combase\rpcss\olescm\class.cxx`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::StartServerAndWaitImpl(
        CServerTableEntry *this,
        struct ACTIVATION_PARAMS *a2,
        struct CClassData *a3,
        int a4,
        struct CNamedObject *a5,
        WCHAR *a6,
        int a7,
        int *a8,
        int *a9,
        int *a10)
{
  int v10; // ebx
  int *v11; // r12
  char v15; // al
  ActivationPropertiesIn *v16; // rcx
  int ActivationFlags; // eax
  int v18; // r15d
  void *v19; // rcx
  void *v20; // rcx
  int v21; // ecx
  int v22; // r9d
  __int64 v23; // rdx
  int v24; // r15d
  int v25; // eax
  struct tagBLOB **v26; // r8
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // r9d
  void *v31; // rcx
  HANDLE *v32; // rbx
  int v33; // eax
  unsigned int v34; // r12d
  __int128 v36; // xmm0
  ComBlob *v37; // rcx
  BOOL v38; // r12d
  CActivationStateList *v39; // rcx
  struct ActivationActivity *v40; // r15
  int ActivationActivityIfNeeded; // eax
  unsigned int v42; // edx
  CActivationState *v43; // rcx
  int v44; // eax
  int v45; // r15d
  __int64 v46; // rcx
  void (__fastcall *v47)(CServerTableEntry *, LPWSTR *); // rbx
  const unsigned __int16 *v48; // rax
  void *v49; // rcx
  int v50; // eax
  void *v51; // rcx
  signed int v52; // eax
  unsigned int v53; // edx
  signed int v54; // r14d
  __int64 v55; // rax
  void (__fastcall *v56)(CServerTableEntry *, LPWSTR *); // rbx
  unsigned __int64 v57; // rdx
  unsigned __int8 v58; // cl
  __int64 v59; // rax
  const WCHAR *v60; // rbx
  int v61; // edi
  PCWSTR StringRawBuffer; // rax
  int v63; // edx
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  unsigned int v67; // edx
  CActivationState *v68; // rcx
  CActivationState *v69; // rcx
  int v70; // [rsp+20h] [rbp-E0h]
  int v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  struct CActivationState *v76; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v77; // [rsp+70h] [rbp-90h] BYREF
  int *v78; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp-80h] BYREF
  struct CNamedObject *v80; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v81[2]; // [rsp+90h] [rbp-70h] BYREF
  char v82; // [rsp+A0h] [rbp-60h]
  int *v83; // [rsp+A8h] [rbp-58h]
  PCWSTR v84; // [rsp+B0h] [rbp-50h] BYREF
  char *v85; // [rsp+B8h] [rbp-48h] BYREF
  struct tagBLOB v86; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v87[80]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v10 = 0;
  v11 = a10;
  v80 = a5;
  StringSid = a6;
  v81[1] = &v78;
  *a10 = 0;
  v15 = *((_BYTE *)a3 + 80);
  v78 = a8;
  v83 = a10;
  hObject = 0;
  v81[0] = this;
  if ( v15 == 2 || v15 == 8 )
  {
    if ( a4
      && (v44 = CServerTableEntry::WaitForServiceStopped(this, a3, *((struct CToken **)a2 + 2)), v45 = v44, v44 < 0) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAF8,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)v44,
        v70);
      v46 = *(_QWORD *)this;
      StringSid = 0;
      v47 = *(void (__fastcall **)(CServerTableEntry *, LPWSTR *))(v46 + 32);
      WindowsDeleteString(0);
      StringSid = 0;
      v47(this, &StringSid);
      v48 = CClassData::Service(a3);
      LogServiceStopError((HSTRING)StringSid, *((_DWORD *)a2 + 29), *((struct CToken **)a2 + 2), v48);
      BreakOnServerExecFailureIfRequested();
      v10 = -2146959355;
      *a10 = v45;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB02,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)0x80080005LL,
        v73);
      WindowsDeleteString((HSTRING)StringSid);
      StringSid = 0;
      if ( *((_QWORD *)this + 3) )
      {
        CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
        v49 = (void *)*((_QWORD *)this + 3);
        if ( v49 )
        {
          CloseHandle(v49);
          *((_QWORD *)this + 3) = 0;
        }
        CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
      }
      if ( *((_DWORD *)this + 3) )
        *v78 = 0;
    }
    else
    {
      v24 = (_DWORD)this + 16;
      v50 = (*(__int64 (__fastcall **)(struct CClassData *, struct ACTIVATION_PARAMS *, char *))(*(_QWORD *)a3 + 72LL))(
              a3,
              a2,
              (char *)this + 16);
      if ( v50 != -2147023840 )
        v10 = v50;
      v38 = v50 == -2147023840;
      if ( v10 >= 0 )
        goto LABEL_44;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0C,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)v10,
        v70);
      if ( *((_QWORD *)this + 3) )
      {
        CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
        v51 = (void *)*((_QWORD *)this + 3);
        if ( v51 )
        {
          CloseHandle(v51);
          *((_QWORD *)this + 3) = 0;
        }
        CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
      }
      if ( *((_DWORD *)this + 3) )
        *v78 = 0;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    return (unsigned int)v10;
  }
  *((_DWORD *)this + 3) = a7;
  *a8 = a7;
  if ( !(unsigned int)CClassData::HasRunAs(a3) && !(unsigned int)CClassData::HasActivateAsPackage(a3) )
  {
    v16 = (ActivationPropertiesIn *)(*((_QWORD *)a2 + 43) + 568LL);
    v77 = 0;
    ActivationFlags = ActivationPropertiesIn::GetActivationFlags(v16, &v77);
    v18 = ActivationFlags;
    if ( ActivationFlags < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB26,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)ActivationFlags,
        v70);
      goto LABEL_7;
    }
    if ( (v77 & 2) != 0 )
    {
LABEL_7:
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v19 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
        StringSid = 0;
        ConvertSidToStringSidW(v19, &StringSid);
        WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
        CGuidStr::CGuidStr((CGuidStr *)v87, (const struct _GUID *)((char *)a2 + 60));
        ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
          v29,
          (unsigned int)"CServerTableEntry::StartServerAndWaitImpl",
          2858,
          v30);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        v11 = v83;
      }
      *v11 = v18;
      v23 = 2860;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)0x80070005LL,
        v70);
      if ( *((_QWORD *)this + 3) )
      {
        CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
        v31 = (void *)*((_QWORD *)this + 3);
        if ( v31 )
        {
          CloseHandle(v31);
          *((_QWORD *)this + 3) = 0;
        }
        CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
      }
      if ( *((_DWORD *)this + 3) )
        *v78 = 0;
      v10 = -2147024891;
      goto LABEL_107;
    }
    if ( *((_DWORD *)a2 + 8) )
    {
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v20 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
        StringSid = 0;
        ConvertSidToStringSidW(v20, &StringSid);
        WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
        CGuidStr::CGuidStr((CGuidStr *)v87, (const struct _GUID *)((char *)a2 + 60));
        ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
          v21,
          (unsigned int)"CServerTableEntry::StartServerAndWaitImpl",
          2868,
          v22);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      }
      v23 = 2869;
      goto LABEL_23;
    }
    v24 = (_DWORD)this + 16;
    v71 = (_DWORD)this + 16;
    v25 = (*(__int64 (__fastcall **)(struct CClassData *, struct ACTIVATION_PARAMS *, char *, HANDLE *))(*(_QWORD *)a3 + 56LL))(
            a3,
            a2,
            (char *)this + 24,
            &hObject);
    v10 = v25;
    if ( v25 < 0 )
    {
      v27 = (unsigned int)v25;
      v28 = 2876;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)v27,
        v71);
      v82 = 0;
LABEL_21:
      lambda_b15df0fea7fedc2ab86f4cd588ad762e_::operator()(v81);
LABEL_107:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return (unsigned int)v10;
    }
    goto LABEL_40;
  }
  v32 = (HANDLE *)((char *)this + 24);
  v24 = (_DWORD)this + 16;
  v71 = (_DWORD)this + 16;
  v33 = (*(__int64 (__fastcall **)(struct CClassData *, struct ACTIVATION_PARAMS *, char *, HANDLE *))(*(_QWORD *)a3 + 64LL))(
          a3,
          a2,
          (char *)this + 24,
          &hObject);
  v34 = v33;
  if ( v33 >= 0 )
  {
LABEL_40:
    if ( *((_QWORD *)a2 + 68) )
    {
      v36 = *(_OWORD *)((char *)a2 + 520);
      *(_QWORD *)&v86.cbSize = 0;
      v85 = (char *)this + 48;
      *(_OWORD *)((char *)this + 56) = v36;
      v37 = (ComBlob *)*((_QWORD *)a2 + 68);
      LOBYTE(v86.pBlobData) = 1;
      v10 = ComBlob::DuplicateBlob(v37, &v86, v26);
      wil::details::out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&void ComBlob::DeleteBlob(tagBLOB *)>>>::~out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&void ComBlob::DeleteBlob(tagBLOB *)>>>(&v85);
      if ( v10 < 0 )
      {
        v27 = (unsigned int)v10;
        v28 = 2883;
        goto LABEL_20;
      }
    }
    v38 = 0;
    SetEvent(*((HANDLE *)StringSid + 3));
LABEL_44:
    StringSid = 0;
    wil::make_unique_nothrow<CActivationState,_GUID &,unsigned long &,unsigned long &,std::nullptr_t>(
      (unsigned int)&v76,
      (_DWORD)a2 + 60,
      v24,
      (_DWORD)a2 + 240,
      (__int64)&StringSid);
    if ( v76 )
      CActivationStateList::Insert(v39, v76);
    v40 = 0;
    StringSid = 0;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      ActivationActivityIfNeeded = CClassData::GetActivationActivityIfNeeded(a3, hObject, &StringSid);
      v10 = ActivationActivityIfNeeded;
      if ( ActivationActivityIfNeeded < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB59,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)(unsigned int)ActivationActivityIfNeeded,
          v72);
        if ( StringSid )
          ActivationActivity::DestroyActivationActivity((struct ActivationActivity *)StringSid);
        v43 = v76;
        if ( v76 )
        {
          CActivationStateList::Remove(v76, v76);
          v43 = v76;
        }
        v76 = 0;
        if ( v43 )
          CActivationState::`scalar deleting destructor'(v43, v42);
        v82 = 0;
        goto LABEL_21;
      }
      v40 = (struct ActivationActivity *)StringSid;
    }
    if ( *((_BYTE *)a3 + 80) != 2 )
    {
      if ( *((_BYTE *)a3 + 80) == 6 || *((_BYTE *)a3 + 80) == 7 )
      {
        v52 = CServerTableEntry::WaitForDllhostServer(this, a3, *((void **)v80 + 3), a2, *v78, *a9);
        goto LABEL_82;
      }
      if ( *((_BYTE *)a3 + 80) != 8 )
      {
        v52 = CServerTableEntry::WaitForLocalServer(this, *((void **)v80 + 3), a3, *a9);
LABEL_82:
        v77 = v52;
        v54 = v52;
        if ( v52 >= 0 )
        {
          if ( v40 )
            ActivationActivity::DestroyActivationActivity(v40);
          v69 = v76;
          if ( v76 )
          {
            CActivationStateList::Remove(v76, v76);
            v69 = v76;
          }
          v76 = 0;
          if ( v69 )
            CActivationState::`scalar deleting destructor'(v69, v53);
          v82 = 0;
          lambda_b15df0fea7fedc2ab86f4cd588ad762e_::operator()(v81);
          v10 = 0;
          goto LABEL_107;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB78,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)(unsigned int)v52,
          v72);
        v55 = *(_QWORD *)this;
        StringSid = 0;
        v56 = *(void (__fastcall **)(CServerTableEntry *, LPWSTR *))(v55 + 32);
        WindowsDeleteString(0);
        StringSid = 0;
        v56(this, &StringSid);
        LogRegisterTimeout((HSTRING)StringSid, *((_DWORD *)a2 + 29), *((struct CToken **)a2 + 2));
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          v59 = *((_QWORD *)a2 + 1);
          if ( v59 )
          {
            v60 = *(const WCHAR **)(v59 + 384);
            v61 = *(_DWORD *)(v59 + 88);
          }
          else
          {
            v60 = &Class;
            v61 = 0;
          }
          StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)StringSid, 0);
          ComTraceMessageT<unsigned short const *,unsigned long,unsigned short const *,long>(
            v64,
            v63,
            v65,
            v66,
            v74,
            (__int64)StringRawBuffer,
            v61,
            (__int64)v60);
        }
        v10 = -2146959355;
        if ( *((_QWORD *)a2 + 69) && AAMTraceProvider::IsEnabled(v58, v57) )
        {
          LODWORD(v80) = -2146959355;
          v84 = WindowsGetStringRawBuffer((HSTRING)StringSid, 0);
          AAMTraceProvider::AAMCOMWaitForServerFailed<unsigned short const *,unsigned __int64 &,long,long &>(
            &v84,
            (char *)a2 + 552,
            &v80,
            &v77);
        }
        BreakOnServerExecFailureIfRequested();
        *v83 = v54;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8B,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)0x80080005LL,
          v74);
        WindowsDeleteString((HSTRING)StringSid);
        StringSid = 0;
        if ( v40 )
          ActivationActivity::DestroyActivationActivity(v40);
        v68 = v76;
        if ( v76 )
        {
          CActivationStateList::Remove(v76, v76);
          v68 = v76;
        }
        v76 = 0;
        if ( v68 )
          CActivationState::`scalar deleting destructor'(v68, v67);
        v82 = 0;
        goto LABEL_21;
      }
    }
    v52 = CServerTableEntry::WaitForService(this, a3, *((struct CToken **)a2 + 2), *((void **)v80 + 3), v38);
    goto LABEL_82;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB1E,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
    (const char *)(unsigned int)v33,
    v71);
  if ( *v32 )
  {
    CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
    if ( *v32 )
    {
      CloseHandle(*v32);
      *v32 = 0;
    }
    CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
  }
  if ( *((_DWORD *)this + 3) )
    *v78 = 0;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v34;
}

```

## disassembly

```asm
0x18006c680  mov     [rsp-8+arg_18], rbx
0x18006c685  push    rbp
0x18006c686  push    rsi
0x18006c687  push    rdi
0x18006c688  push    r12
0x18006c68a  push    r13
0x18006c68c  push    r14
0x18006c68e  push    r15
0x18006c690  lea     rbp, [rsp-30h]
0x18006c695  sub     rsp, 130h
0x18006c69c  mov     rax, cs:__security_cookie
0x18006c6a3  xor     rax, rsp
0x18006c6a6  mov     [rbp+60h+var_40], rax
0x18006c6aa  mov     rax, [rbp+60h+arg_20]
0x18006c6b1  xor     ebx, ebx
0x18006c6b3  mov     r12, [rbp+60h+arg_48]
0x18006c6ba  mov     rdi, rcx
0x18006c6bd  mov     rcx, [rbp+60h+arg_38]
0x18006c6c4  mov     r14, r8
0x18006c6c7  mov     r13, [rbp+60h+arg_40]
0x18006c6ce  mov     rsi, rdx
0x18006c6d1  mov     [rbp+60h+var_D8], rax
0x18006c6d5  mov     rax, [rbp+60h+arg_28]
0x18006c6dc  mov     [rsp+160h+StringSid], rax
0x18006c6e1  lea     rax, [rsp+160h+var_E8]
0x18006c6e6  mov     [rbp+60h+var_C8], rax
0x18006c6ea  mov     [r12], ebx
0x18006c6ee  mov     al, [r8+50h]
0x18006c6f2  mov     [rsp+160h+var_E8], rcx
0x18006c6f7  mov     [rbp+60h+var_B8], r12
0x18006c6fb  mov     [rbp+60h+hObject], rbx
0x18006c6ff  mov     [rbp+60h+var_D0], rdi
0x18006c703  cmp     al, 2
0x18006c705  jz      loc_18006CBFB
0x18006c70b  cmp     al, 8
0x18006c70d  jz      loc_18006CBFB
0x18006c713  mov     eax, [rbp+60h+arg_30]
0x18006c719  mov     [rdi+0Ch], eax
0x18006c71c  mov     [rcx], eax
0x18006c71e  mov     rcx, r8; this
0x18006c721  call    ?HasRunAs@CClassData@@QEAAHXZ; CClassData::HasRunAs(void)
0x18006c726  test    eax, eax
0x18006c728  jnz     loc_18006CA21
0x18006c72e  mov     rcx, r14; this
0x18006c731  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18006c736  test    eax, eax
0x18006c738  jnz     loc_18006CA21
0x18006c73e  mov     rcx, [rsi+158h]
0x18006c745  lea     rdx, [rsp+160h+var_F0]; unsigned int *
0x18006c74a  add     rcx, 238h; this
0x18006c751  mov     [rsp+160h+var_F0], ebx
0x18006c755  call    ?GetActivationFlags@ActivationPropertiesIn@@UEAAJPEAK@Z; ActivationPropertiesIn::GetActivationFlags(ulong *)
0x18006c75a  mov     r15d, eax
0x18006c75d  test    eax, eax
0x18006c75f  jns     loc_18006C7FC
0x18006c765  mov     rcx, [rbp+68h]; this
0x18006c769  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18006c770  mov     r9d, eax; char *
0x18006c773  mov     edx, 0B26h; void *
0x18006c778  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006c77d  mov     eax, cs:dword_1801574B8
0x18006c783  mov     r14d, 80070005h
0x18006c789  test    eax, eax
0x18006c78b  jnz     short loc_18006C7A8
0x18006c78d  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18006c793  jz      loc_18006C9BA
0x18006c799  xor     ecx, ecx
0x18006c79b  call    IsWppLevelEnabled
0x18006c7a0  test    al, al
0x18006c7a2  jz      loc_18006C9BA
0x18006c7a8  mov     rcx, [rsi+10h]
0x18006c7ac  lea     rdx, [rsp+160h+StringSid]; StringSid
0x18006c7b1  add     rcx, 9Ch; Sid
0x18006c7b8  mov     [rsp+160h+StringSid], rbx
0x18006c7bd  call    cs:__imp_ConvertSidToStringSidW
0x18006c7c4  nop     dword ptr [rax+rax+00h]
0x18006c7c9  mov     rax, [rsp+160h+StringSid]
0x18006c7ce  lea     rbx, Class
0x18006c7d5  test    rax, rax
0x18006c7d8  mov     r12, rbx
0x18006c7db  cmovnz  r12, rax
0x18006c7df  mov     rax, [rsi+8]
0x18006c7e3  test    rax, rax
0x18006c7e6  jz      loc_18006C952
0x18006c7ec  mov     rbx, [rax+180h]
0x18006c7f3  mov     r13d, [rax+58h]
0x18006c7f7  jmp     loc_18006C955
0x18006c7fc  test    byte ptr [rsp+160h+var_F0], 2
0x18006c801  jnz     loc_18006C77D
0x18006c807  cmp     [rsi+20h], ebx
0x18006c80a  jz      loc_18006C8F6
0x18006c810  mov     eax, cs:dword_1801574B8
0x18006c816  mov     r14d, 80070005h
0x18006c81c  test    eax, eax
0x18006c81e  jnz     short loc_18006C83B
0x18006c820  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18006c826  jz      loc_18006C8EC
0x18006c82c  xor     ecx, ecx
0x18006c82e  call    IsWppLevelEnabled
0x18006c833  test    al, al
0x18006c835  jz      loc_18006C8EC
0x18006c83b  mov     rcx, [rsi+10h]
0x18006c83f  lea     rdx, [rsp+160h+StringSid]; StringSid
0x18006c844  add     rcx, 9Ch; Sid
0x18006c84b  mov     [rsp+160h+StringSid], rbx
0x18006c850  call    cs:__imp_ConvertSidToStringSidW
0x18006c857  nop     dword ptr [rax+rax+00h]
0x18006c85c  mov     rax, [rsp+160h+StringSid]
0x18006c861  lea     rbx, Class
0x18006c868  test    rax, rax
0x18006c86b  mov     r15, rbx
0x18006c86e  cmovnz  r15, rax
0x18006c872  mov     rax, [rsi+8]
0x18006c876  test    rax, rax
0x18006c879  jz      short loc_18006C888
0x18006c87b  mov     rbx, [rax+180h]
0x18006c882  mov     r12d, [rax+58h]
0x18006c886  jmp     short loc_18006C88B
0x18006c888  xor     r12d, r12d
0x18006c88b  mov     rcx, [rsi+1B8h]; string
0x18006c892  xor     edx, edx; length
0x18006c894  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c89b  nop     dword ptr [rax+rax+00h]
0x18006c8a0  lea     rdx, [rsi+3Ch]; struct _GUID *
0x18006c8a4  mov     r11, rax
0x18006c8a7  lea     rcx, [rbp+60h+var_90]; this
0x18006c8ab  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18006c8b0  mov     [rsp+160h+var_110], r14d
0x18006c8b5  lea     rdx, aCservertableen_3; "CServerTableEntry::StartServerAndWaitIm"...
0x18006c8bc  mov     [rsp+160h+var_118], r15
0x18006c8c1  mov     r8d, 0B34h
0x18006c8c7  mov     [rsp+160h+var_120], rbx
0x18006c8cc  mov     dword ptr [rsp+160h+var_128], r12d
0x18006c8d1  mov     [rsp+160h+var_130], r11
0x18006c8d6  mov     qword ptr [rsp+160h+var_138], rax
0x18006c8db  call    ??$ComTraceMessageT@PEAGPEBGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K23J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,ushort *,long)
0x18006c8e0  lea     rcx, [rsp+160h+StringSid]
0x18006c8e5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c8ea  xor     ebx, ebx
0x18006c8ec  mov     edx, 0B35h
0x18006c8f1  jmp     loc_18006C9C3
0x18006c8f6  mov     rax, [r14]
0x18006c8f9  lea     r15, [rdi+10h]
0x18006c8fd  lea     r8, [rdi+18h]
0x18006c901  mov     qword ptr [rsp+160h+var_138], r13
0x18006c906  lea     r9, [rbp+60h+hObject]
0x18006c90a  mov     qword ptr [rsp+160h+var_140], r15; int
0x18006c90f  mov     rdx, rsi
0x18006c912  mov     rcx, r14
0x18006c915  mov     rax, [rax+38h]
0x18006c919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c91e  mov     ebx, eax
0x18006c920  test    eax, eax
0x18006c922  jns     loc_18006CACC
0x18006c928  mov     r9d, eax; char *
0x18006c92b  mov     edx, 0B3Ch; void *
0x18006c930  mov     rcx, [rbp+68h]; this
0x18006c934  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18006c93b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c940  mov     [rbp+60h+var_C0], 0
0x18006c944  lea     rcx, [rbp+60h+var_D0]
0x18006c948  call    _lambda_b15df0fea7fedc2ab86f4cd588ad762e___operator__
0x18006c94d  jmp     loc_18006D00A
0x18006c952  xor     r13d, r13d
0x18006c955  mov     rcx, [rsi+1B8h]; string
0x18006c95c  xor     edx, edx; length
0x18006c95e  call    cs:__imp_WindowsGetStringRawBuffer
0x18006c965  nop     dword ptr [rax+rax+00h]
0x18006c96a  lea     rdx, [rsi+3Ch]; struct _GUID *
0x18006c96e  mov     r11, rax
0x18006c971  lea     rcx, [rbp+60h+var_90]; this
0x18006c975  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18006c97a  mov     [rsp+160h+var_110], r14d
0x18006c97f  lea     rdx, aCservertableen_3; "CServerTableEntry::StartServerAndWaitIm"...
0x18006c986  mov     [rsp+160h+var_118], r12
0x18006c98b  mov     r8d, 0B2Ah
0x18006c991  mov     [rsp+160h+var_120], rbx
0x18006c996  mov     dword ptr [rsp+160h+var_128], r13d
0x18006c99b  mov     [rsp+160h+var_130], r11
0x18006c9a0  mov     qword ptr [rsp+160h+var_138], rax
0x18006c9a5  call    ??$ComTraceMessageT@PEAGPEBGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K23J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,ushort *,long)
0x18006c9aa  lea     rcx, [rsp+160h+StringSid]
0x18006c9af  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18006c9b4  mov     r12, [rbp+60h+var_B8]
0x18006c9b8  xor     ebx, ebx
0x18006c9ba  mov     [r12], r15d
0x18006c9be  mov     edx, 0B2Ch; void *
0x18006c9c3  mov     rcx, [rbp+68h]; this
0x18006c9c7  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18006c9ce  mov     r9d, r14d; char *
0x18006c9d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006c9d6  cmp     [rdi+18h], rbx
0x18006c9da  jz      short loc_18006CA0D
0x18006c9dc  lea     rcx, [rdi+58h]; lpCriticalSection
0x18006c9e0  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x18006c9e5  mov     rcx, [rdi+18h]; hObject
0x18006c9e9  test    rcx, rcx
0x18006c9ec  jz      short loc_18006CA02
0x18006c9ee  call    cs:__imp_CloseHandle
0x18006c9f5  nop     dword ptr [rax+rax+00h]
0x18006c9fa  mov     qword ptr [rdi+18h], 0
0x18006ca02  lea     rcx, [rdi+58h]; this
0x18006ca06  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x18006ca0b  xor     ebx, ebx
0x18006ca0d  cmp     [rdi+0Ch], ebx
0x18006ca10  jz      short loc_18006CA19
0x18006ca12  mov     rax, [rsp+160h+var_E8]
0x18006ca17  mov     [rax], ebx
0x18006ca19  mov     ebx, r14d
0x18006ca1c  jmp     loc_18006D00A
0x18006ca21  mov     rax, [r14]
0x18006ca24  lea     rbx, [rdi+18h]
0x18006ca28  lea     r15, [rdi+10h]
0x18006ca2c  mov     qword ptr [rsp+160h+var_138], r13
0x18006ca31  lea     r9, [rbp+60h+hObject]
0x18006ca35  mov     qword ptr [rsp+160h+var_140], r15; int
0x18006ca3a  mov     r8, rbx
0x18006ca3d  mov     rdx, rsi
0x18006ca40  mov     rax, [rax+40h]
0x18006ca44  mov     rcx, r14
0x18006ca47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ca4c  mov     r12d, eax
0x18006ca4f  test    eax, eax
0x18006ca51  jns     short loc_18006CACC
0x18006ca53  mov     rcx, [rbp+68h]; this
0x18006ca57  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x18006ca5e  mov     r9d, eax; char *
0x18006ca61  mov     edx, 0B1Eh; void *
0x18006ca66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006ca6b  xor     r14d, r14d
0x18006ca6e  cmp     [rbx], r14
0x18006ca71  jz      short loc_18006CA9C
0x18006ca73  lea     rcx, [rdi+58h]; lpCriticalSection
0x18006ca77  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x18006ca7c  mov     rcx, [rbx]; hObject
0x18006ca7f  test    rcx, rcx
0x18006ca82  jz      short loc_18006CA93
0x18006ca84  call    cs:__imp_CloseHandle
0x18006ca8b  nop     dword ptr [rax+rax+00h]
0x18006ca90  mov     [rbx], r14
0x18006ca93  lea     rcx, [rdi+58h]; this
0x18006ca97  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x18006ca9c  cmp     [rdi+0Ch], r14d
0x18006caa0  jz      short loc_18006CAAA
0x18006caa2  mov     rax, [rsp+160h+var_E8]
0x18006caa7  mov     [rax], r14d
0x18006caaa  mov     rcx, [rbp+60h+hObject]; hObject
0x18006caae  lea     rax, [rcx-1]
0x18006cab2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006cab6  ja      short loc_18006CAC4
0x18006cab8  call    cs:__imp_CloseHandle
0x18006cabf  nop     dword ptr [rax+rax+00h]
0x18006cac4  mov     eax, r12d
0x18006cac7  jmp     loc_18006D015
0x18006cacc  cmp     qword ptr [rsi+220h], 0
0x18006cad4  jz      short loc_18006CB22
0x18006cad6  movups  xmm0, xmmword ptr [rsi+208h]
0x18006cadd  lea     rax, [rdi+30h]
0x18006cae1  mov     qword ptr [rbp+60h+var_A0.cbSize], 0
0x18006cae9  lea     rdx, [rbp+60h+var_A0]; struct tagBLOB *
0x18006caed  mov     [rbp+60h+var_A8], rax
0x18006caf1  movdqu  xmmword ptr [rdi+38h], xmm0
0x18006caf6  mov     rcx, [rsi+220h]; this
0x18006cafd  mov     byte ptr [rbp+60h+var_A0.pBlobData], 1
0x18006cb01  call    ?DuplicateBlob@ComBlob@@YAJPEAUtagBLOB@@PEAPEAU2@@Z; ComBlob::DuplicateBlob(tagBLOB *,tagBLOB * *)
0x18006cb06  lea     rcx, [rbp+60h+var_A8]
0x18006cb0a  mov     ebx, eax
0x18006cb0c  call    ??1?$out_param_t@V?$unique_ptr@UtagBLOB@@U?$function_deleter@P6AXPEAUtagBLOB@@@Z$1?DeleteBlob@ComBlob@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&ComBlob::DeleteBlob(tagBLOB *)>>>::~out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&ComBlob::DeleteBlob(tagBLOB *)>>>(void)
0x18006cb11  test    ebx, ebx
0x18006cb13  jns     short loc_18006CB22
0x18006cb15  mov     r9d, ebx
0x18006cb18  mov     edx, 0B43h
0x18006cb1d  jmp     loc_18006C930
0x18006cb22  mov     rcx, [rsp+160h+StringSid]
0x18006cb27  xor     r12d, r12d
0x18006cb2a  mov     rcx, [rcx+18h]; hEvent
0x18006cb2e  call    cs:__imp_SetEvent
0x18006cb35  nop     dword ptr [rax+rax+00h]
0x18006cb3a  lea     rax, [rsp+160h+StringSid]
0x18006cb3f  mov     [rsp+160h+StringSid], 0
0x18006cb48  lea     r9, [rsi+0F0h]
0x18006cb4f  mov     qword ptr [rsp+160h+var_140], rax; int
0x18006cb54  lea     rdx, [rsi+3Ch]
0x18006cb58  mov     r8, r15
0x18006cb5b  lea     rcx, [rsp+160h+var_F8]
0x18006cb60  call    ??$make_unique_nothrow@VCActivationState@@AEAU_GUID@@AEAKAEAK$$T@wil@@YA?AV?$unique_ptr@VCActivationState@@U?$default_delete@VCActivationState@@@wistd@@@wistd@@AEAU_GUID@@AEAK1$$QEA$$T@Z
0x18006cb65  mov     rdx, [rsp+160h+var_F8]; struct CActivationState *
0x18006cb6a  test    rdx, rdx
0x18006cb6d  jz      short loc_18006CB74
0x18006cb6f  call    ?Insert@CActivationStateList@@QEAAXPEAVCActivationState@@@Z; CActivationStateList::Insert(CActivationState *)
0x18006cb74  mov     rdx, [rbp+60h+hObject]
0x18006cb78  xor     r15d, r15d
0x18006cb7b  mov     [rsp+160h+StringSid], r15
0x18006cb80  lea     rax, [rdx-1]
0x18006cb84  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18006cb88  ja      loc_18006CDC1
0x18006cb8e  lea     r8, [rsp+160h+StringSid]
0x18006cb93  mov     rcx, r14
0x18006cb96  call    ?GetActivationActivityIfNeeded@CClassData@@QEAAJPEAXAEAV?$unique_ptr@VActivationActivity@@U?$function_deleter@P6AXPEAVActivationActivity@@@Z$1?DestroyActivationActivity@1@SAX0@Z@wil@@@wistd@@@Z; CClassData::GetActivationActivityIfNeeded(void *,wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&ActivationActivity::DestroyActivationActivity(ActivationActivity *)>> &)
0x18006cb9b  mov     ebx, eax
  ... truncated ...
```
