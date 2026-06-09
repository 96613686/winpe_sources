# CServerTableEntry::StartServerAndWaitImpl(ACTIVATION_PARAMS *,CClassData *,int,CNamedObject *,CNamedObject *,long,long *,int *,long *)

- ea: `0x180067898`
- end: `0x1800681a4`
- name: `?StartServerAndWaitImpl@CServerTableEntry@@AEAAJPEAUACTIVATION_PARAMS@@PEAVCClassData@@HPEAVCNamedObject@@2JPEAJPEAH3@Z`
- size: `2316`
- prototype: `int(CServerTableEntry *__hidden this, struct ACTIVATION_PARAMS *, struct CClassData *, int, struct CNamedObject *, struct CNamedObject *, int, int *, int *, int *)`
- caller_count: `1`
- callee_count: `35`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800890dc`

## callees

- `0x180003cd0`
- `0x180016160`
- `0x180022114`
- `0x180022138`
- `0x180022274`
- `0x1800262fc`
- `0x180026c54`
- `0x18002ba28`
- `0x18002d6cc`
- `0x18002e210`
- `0x18002ed28`
- `0x18002f058`
- `0x180034540`
- `0x18003e758`
- `0x18003e920`
- `0x18003e97c`
- `0x18004c8a8`
- `0x18004fdf0`
- `0x180064098`
- `0x180067898`
- `0x18006fbb0`
- `0x180070610`
- `0x180073764`
- `0x18007a9c4`
- `0x18007bb9c`
- `0x18007e40c`
- `0x1800816ec`
- `0x180084504`
- `0x180098b54`
- `0x18009fd60`
- `0x1800a2138`
- `0x1800a2590`
- `0x1800b27e0`
- `0x1800f3bcc`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067edf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067f51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067c78`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067ca5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067eaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067edf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067f51`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180067d15`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180067d15`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800679d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180067a5d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800679d4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180067a5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067e22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006802a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067e22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180067e87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006802a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068120`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067b5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006809a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800680d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067a9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067b5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006809a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800680d4`

## string_xrefs

- `0x180067980`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067b35`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067bc2`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067c4b`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067d8a`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067e00`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067e65`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180067f22`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180068008`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180068100`: `onecore\com\combase\rpcss\olescm\class.cxx`

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
  const WCHAR *v20; // rbx
  LPWSTR v21; // r12
  __int64 v22; // rax
  int v23; // r13d
  void *v24; // rcx
  const WCHAR *v25; // rbx
  LPWSTR v26; // r15
  __int64 v27; // rax
  int v28; // r12d
  CGuidStr *v29; // rax
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r11
  __int64 v33; // rdx
  int *v34; // r15
  int v35; // eax
  struct tagBLOB **v36; // r8
  unsigned __int64 v37; // r9
  __int64 v38; // rdx
  CGuidStr *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // r9
  __int64 v42; // r11
  void *v43; // rcx
  HANDLE *v44; // rbx
  int v45; // eax
  unsigned int v46; // r12d
  __int128 v48; // xmm0
  const void **v49; // rcx
  BOOL v50; // r12d
  CActivationStateList *v51; // rcx
  int ActivationActivityIfNeeded; // eax
  unsigned int v53; // edx
  CActivationState *v54; // rcx
  int v55; // eax
  int v56; // r15d
  __int64 v57; // rcx
  void (__fastcall *v58)(CServerTableEntry *, HSTRING *); // rbx
  const unsigned __int16 *v59; // rax
  void *v60; // rcx
  int v61; // eax
  void *v62; // rcx
  signed int v63; // eax
  signed int v64; // r14d
  __int64 v65; // rax
  void (__fastcall *v66)(CServerTableEntry *, HSTRING *); // rbx
  unsigned __int64 v67; // rdx
  unsigned __int8 v68; // cl
  unsigned int v69; // edx
  CActivationState *v70; // rcx
  int v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-98h] BYREF
  struct CActivationState *v78; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v79; // [rsp+78h] [rbp-88h] BYREF
  int *v80; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h] BYREF
  int v82; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v83[2]; // [rsp+98h] [rbp-68h] BYREF
  char v84; // [rsp+A8h] [rbp-58h]
  int *v85; // [rsp+B0h] [rbp-50h]
  PCWSTR StringRawBuffer; // [rsp+B8h] [rbp-48h] BYREF
  char *v87; // [rsp+C0h] [rbp-40h] BYREF
  struct tagBLOB v88; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v89[80]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  v10 = 0;
  v11 = a10;
  string = (HSTRING)a5;
  StringSid = a6;
  v83[1] = &v80;
  *a10 = 0;
  v15 = *((_BYTE *)a3 + 80);
  v80 = a8;
  v85 = a10;
  hObject = 0;
  v83[0] = this;
  if ( v15 == 2 || v15 == 8 )
  {
    if ( a4
      && (v55 = CServerTableEntry::WaitForServiceStopped(this, a3, *((struct CToken **)a2 + 2)), v56 = v55, v55 < 0) )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xAF8,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)v55,
        v71);
      v57 = *(_QWORD *)this;
      string = 0;
      v58 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v57 + 32);
      WindowsDeleteString(0);
      string = 0;
      v58(this, &string);
      v59 = CClassData::Service(a3);
      LogServiceStopError(string, *((_DWORD *)a2 + 29), *((struct CToken **)a2 + 2), v59);
      BreakOnServerExecFailureIfRequested();
      v10 = -2146959355;
      *a10 = v56;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB02,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)0x80080005LL,
        v74);
      WindowsDeleteString(string);
      string = 0;
      if ( *((_QWORD *)this + 3) )
      {
        CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
        v60 = (void *)*((_QWORD *)this + 3);
        if ( v60 )
        {
          CloseHandle(v60);
          *((_QWORD *)this + 3) = 0;
        }
        CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
      }
      if ( *((_DWORD *)this + 3) )
        *v80 = 0;
    }
    else
    {
      v34 = (int *)((char *)this + 16);
      v61 = (*(__int64 (__fastcall **)(struct CClassData *, struct ACTIVATION_PARAMS *, char *))(*(_QWORD *)a3 + 72LL))(
              a3,
              a2,
              (char *)this + 16);
      if ( v61 != -2147023840 )
        v10 = v61;
      v50 = v61 == -2147023840;
      if ( v10 >= 0 )
        goto LABEL_54;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB0C,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)v10,
        v71);
      if ( *((_QWORD *)this + 3) )
      {
        CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
        v62 = (void *)*((_QWORD *)this + 3);
        if ( v62 )
        {
          CloseHandle(v62);
          *((_QWORD *)this + 3) = 0;
        }
        CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
      }
      if ( *((_DWORD *)this + 3) )
        *v80 = 0;
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
    v79 = 0;
    ActivationFlags = ActivationPropertiesIn::GetActivationFlags(v16, &v79);
    v18 = ActivationFlags;
    if ( ActivationFlags < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xB26,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)(unsigned int)ActivationFlags,
        v71);
      goto LABEL_7;
    }
    if ( (v79 & 2) != 0 )
    {
LABEL_7:
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v19 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
        StringSid = 0;
        ConvertSidToStringSidW(v19, &StringSid);
        v20 = &Class;
        v21 = (LPWSTR)&Class;
        if ( StringSid )
          v21 = StringSid;
        v22 = *((_QWORD *)a2 + 1);
        if ( v22 )
        {
          v20 = *(const WCHAR **)(v22 + 384);
          v23 = *(_DWORD *)(v22 + 88);
        }
        else
        {
          v23 = 0;
        }
        WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
        v39 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
        ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
          v40,
          (__int64)"CServerTableEntry::StartServerAndWaitImpl",
          0xB2Au,
          v41,
          v71,
          (__int64)v39,
          v42,
          v23,
          (__int64)v20,
          (__int64)v21,
          0x80070005);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        v11 = v85;
      }
      *v11 = v18;
      v33 = 2860;
LABEL_33:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)0x80070005LL,
        v71);
      if ( *((_QWORD *)this + 3) )
      {
        CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
        v43 = (void *)*((_QWORD *)this + 3);
        if ( v43 )
        {
          CloseHandle(v43);
          *((_QWORD *)this + 3) = 0;
        }
        CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
      }
      if ( *((_DWORD *)this + 3) )
        *v80 = 0;
      v10 = -2147024891;
      goto LABEL_104;
    }
    if ( *((_DWORD *)a2 + 8) )
    {
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        v24 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
        StringSid = 0;
        ConvertSidToStringSidW(v24, &StringSid);
        v25 = &Class;
        v26 = (LPWSTR)&Class;
        if ( StringSid )
          v26 = StringSid;
        v27 = *((_QWORD *)a2 + 1);
        if ( v27 )
        {
          v25 = *(const WCHAR **)(v27 + 384);
          v28 = *(_DWORD *)(v27 + 88);
        }
        else
        {
          v28 = 0;
        }
        WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
        v29 = CGuidStr::CGuidStr((CGuidStr *)v89, (const struct _GUID *)((char *)a2 + 60));
        ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
          v30,
          (__int64)"CServerTableEntry::StartServerAndWaitImpl",
          0xB34u,
          v31,
          v71,
          (__int64)v29,
          v32,
          v28,
          (__int64)v25,
          (__int64)v26,
          0x80070005);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      }
      v33 = 2869;
      goto LABEL_33;
    }
    v34 = (int *)((char *)this + 16);
    v72 = (_DWORD)this + 16;
    v35 = (*(__int64 (__fastcall **)(struct CClassData *, struct ACTIVATION_PARAMS *, char *, HANDLE *))(*(_QWORD *)a3 + 56LL))(
            a3,
            a2,
            (char *)this + 24,
            &hObject);
    v10 = v35;
    if ( v35 < 0 )
    {
      v37 = (unsigned int)v35;
      v38 = 2876;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v38,
        (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
        (const char *)v37,
        v72);
      v84 = 0;
LABEL_29:
      lambda_b15df0fea7fedc2ab86f4cd588ad762e_::operator()(v83);
LABEL_104:
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hObject);
      return (unsigned int)v10;
    }
    goto LABEL_50;
  }
  v44 = (HANDLE *)((char *)this + 24);
  v34 = (int *)((char *)this + 16);
  v72 = (_DWORD)this + 16;
  v45 = (*(__int64 (__fastcall **)(struct CClassData *, struct ACTIVATION_PARAMS *, char *, HANDLE *))(*(_QWORD *)a3 + 64LL))(
          a3,
          a2,
          (char *)this + 24,
          &hObject);
  v46 = v45;
  if ( v45 >= 0 )
  {
LABEL_50:
    if ( *((_QWORD *)a2 + 68) )
    {
      v48 = *(_OWORD *)((char *)a2 + 520);
      *(_QWORD *)&v88.cbSize = 0;
      v87 = (char *)this + 48;
      *(_OWORD *)((char *)this + 56) = v48;
      v49 = (const void **)*((_QWORD *)a2 + 68);
      LOBYTE(v88.pBlobData) = 1;
      v10 = ComBlob::DuplicateBlob(v49, &v88, v36);
      wil::details::out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&void ComBlob::DeleteBlob(tagBLOB *)>>>::~out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&void ComBlob::DeleteBlob(tagBLOB *)>>>(&v87);
      if ( v10 < 0 )
      {
        v37 = (unsigned int)v10;
        v38 = 2883;
        goto LABEL_28;
      }
    }
    v50 = 0;
    SetEvent(*((HANDLE *)StringSid + 3));
LABEL_54:
    StringSid = 0;
    wil::make_unique_nothrow<CActivationState,_GUID &,unsigned long &,unsigned long &,std::nullptr_t>(
      &v78,
      (__int128 *)((char *)a2 + 60),
      v34,
      (int *)a2 + 60,
      (__int64 *)&StringSid);
    if ( v78 )
      CActivationStateList::Insert(v51, v78);
    StringSid = 0;
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      ActivationActivityIfNeeded = CClassData::GetActivationActivityIfNeeded(
                                     (__int64 *)a3,
                                     hObject,
                                     (__int64)&StringSid);
      v10 = ActivationActivityIfNeeded;
      if ( ActivationActivityIfNeeded < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB59,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)(unsigned int)ActivationActivityIfNeeded,
          v73);
LABEL_59:
        wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
          &StringSid,
          0);
        v54 = v78;
        if ( v78 )
        {
          CActivationStateList::Remove(v78, v78);
          v54 = v78;
        }
        v78 = 0;
        if ( v54 )
          CActivationState::`scalar deleting destructor'(v54, v53);
        v84 = 0;
        goto LABEL_29;
      }
    }
    if ( *((_BYTE *)a3 + 80) != 2 )
    {
      if ( *((_BYTE *)a3 + 80) == 6 || *((_BYTE *)a3 + 80) == 7 )
      {
        v63 = CServerTableEntry::WaitForDllhostServer(this, a3, *((void **)string + 3), a2, *v80, *a9);
        goto LABEL_90;
      }
      if ( *((_BYTE *)a3 + 80) != 8 )
      {
        v63 = CServerTableEntry::WaitForLocalServer(this, *((void **)string + 3), a3, *a9);
LABEL_90:
        v79 = v63;
        v64 = v63;
        if ( v63 >= 0 )
        {
          wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
            &StringSid,
            0);
          v70 = v78;
          if ( v78 )
          {
            CActivationStateList::Remove(v78, v78);
            v70 = v78;
          }
          v78 = 0;
          if ( v70 )
            CActivationState::`scalar deleting destructor'(v70, v69);
          v84 = 0;
          lambda_b15df0fea7fedc2ab86f4cd588ad762e_::operator()(v83);
          v10 = 0;
          goto LABEL_104;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xB78,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)(unsigned int)v63,
          v73);
        v65 = *(_QWORD *)this;
        string = 0;
        v66 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v65 + 32);
        WindowsDeleteString(0);
        string = 0;
        v66(this, &string);
        LogRegisterTimeout(string, *((_DWORD *)a2 + 29), *((struct CToken **)a2 + 2));
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          WindowsGetStringRawBuffer(string, 0);
          ComTraceMessageT<unsigned short const *,unsigned long,unsigned short const *,long>();
        }
        v10 = -2146959355;
        if ( *((_QWORD *)a2 + 69) && AAMTraceProvider::IsEnabled(v68, v67) )
        {
          v82 = -2146959355;
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          AAMTraceProvider::AAMCOMWaitForServerFailed<unsigned short const *,unsigned __int64 &,long,long &>(
            &StringRawBuffer,
            (__int64 *)a2 + 69,
            &v82,
            (int *)&v79);
        }
        BreakOnServerExecFailureIfRequested();
        *v85 = v64;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8B,
          (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
          (const char *)0x80080005LL,
          v75);
        WindowsDeleteString(string);
        string = 0;
        goto LABEL_59;
      }
    }
    v63 = CServerTableEntry::WaitForService(this, a3, *((HANDLE **)a2 + 2), *((void **)string + 3), v50);
    goto LABEL_90;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB1E,
    (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
    (const char *)(unsigned int)v45,
    v72);
  if ( *v44 )
  {
    CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)this + 88));
    if ( *v44 )
    {
      CloseHandle(*v44);
      *v44 = 0;
    }
    CSharedLock::UnlockShared((CServerTableEntry *)((char *)this + 88));
  }
  if ( *((_DWORD *)this + 3) )
    *v80 = 0;
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return v46;
}

```

## disassembly

```asm
0x180067898  mov     [rsp-8+arg_18], rbx
0x18006789d  push    rbp
0x18006789e  push    rsi
0x18006789f  push    rdi
0x1800678a0  push    r12
0x1800678a2  push    r13
0x1800678a4  push    r14
0x1800678a6  push    r15
0x1800678a8  lea     rbp, [rsp-40h]
0x1800678ad  sub     rsp, 140h
0x1800678b4  mov     rax, cs:__security_cookie
0x1800678bb  xor     rax, rsp
0x1800678be  mov     [rbp+70h+var_40], rax
0x1800678c2  mov     rax, [rbp+70h+arg_20]
0x1800678c9  xor     ebx, ebx
0x1800678cb  mov     r12, [rbp+70h+arg_48]
0x1800678d2  mov     rdi, rcx
0x1800678d5  mov     rcx, [rbp+70h+arg_38]
0x1800678dc  mov     r14, r8
0x1800678df  mov     r13, [rbp+70h+arg_40]
0x1800678e6  mov     rsi, rdx
0x1800678e9  mov     [rsp+170h+string], rax
0x1800678ee  mov     rax, [rbp+70h+arg_28]
0x1800678f5  mov     [rsp+170h+StringSid], rax
0x1800678fa  lea     rax, [rbp+70h+var_F0]
0x1800678fe  mov     [rbp+70h+var_D0], rax
0x180067902  mov     [r12], ebx
0x180067906  mov     al, [r8+50h]
0x18006790a  mov     [rbp+70h+var_F0], rcx
0x18006790e  mov     [rbp+70h+var_C0], r12
0x180067912  mov     [rbp+70h+hObject], rbx
0x180067916  mov     [rbp+70h+var_D8], rdi
0x18006791a  cmp     al, 2
0x18006791c  jz      loc_180067DD9
0x180067922  cmp     al, 8
0x180067924  jz      loc_180067DD9
0x18006792a  mov     eax, [rbp+70h+arg_30]
0x180067930  mov     [rdi+0Ch], eax
0x180067933  mov     [rcx], eax
0x180067935  mov     rcx, r8; this
0x180067938  call    ?HasRunAs@CClassData@@QEAAHXZ; CClassData::HasRunAs(void)
0x18006793d  test    eax, eax
0x18006793f  jnz     loc_180067C15
0x180067945  mov     rcx, r14; this
0x180067948  call    ?HasActivateAsPackage@CClassData@@QEBAHXZ; CClassData::HasActivateAsPackage(void)
0x18006794d  test    eax, eax
0x18006794f  jnz     loc_180067C15
0x180067955  mov     rcx, [rsi+158h]
0x18006795c  lea     rdx, [rsp+170h+var_F8]; unsigned int *
0x180067961  add     rcx, 238h; this
0x180067968  mov     [rsp+170h+var_F8], ebx
0x18006796c  call    ?GetActivationFlags@ActivationPropertiesIn@@UEAAJPEAK@Z; ActivationPropertiesIn::GetActivationFlags(ulong *)
0x180067971  mov     r15d, eax
0x180067974  test    eax, eax
0x180067976  jns     loc_180067A0D
0x18006797c  mov     rcx, [rbp+78h]; this
0x180067980  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180067987  mov     r9d, eax; char *
0x18006798a  mov     edx, 0B26h; void *
0x18006798f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180067994  mov     eax, cs:dword_18014E4B8
0x18006799a  mov     r14d, 80070005h
0x1800679a0  test    eax, eax
0x1800679a2  jnz     short loc_1800679BF
0x1800679a4  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800679aa  jz      loc_180067BB5
0x1800679b0  xor     ecx, ecx
0x1800679b2  call    IsWppLevelEnabled
0x1800679b7  test    al, al
0x1800679b9  jz      loc_180067BB5
0x1800679bf  mov     rcx, [rsi+10h]
0x1800679c3  lea     rdx, [rsp+170h+StringSid]; StringSid
0x1800679c8  add     rcx, 9Ch; Sid
0x1800679cf  mov     [rsp+170h+StringSid], rbx
0x1800679d4  call    cs:__imp_ConvertSidToStringSidW
0x1800679da  mov     rax, [rsp+170h+StringSid]
0x1800679df  lea     rbx, Class
0x1800679e6  test    rax, rax
0x1800679e9  mov     r12, rbx
0x1800679ec  cmovnz  r12, rax
0x1800679f0  mov     rax, [rsi+8]
0x1800679f4  test    rax, rax
0x1800679f7  jz      loc_180067B53
0x1800679fd  mov     rbx, [rax+180h]
0x180067a04  mov     r13d, [rax+58h]
0x180067a08  jmp     loc_180067B56
0x180067a0d  test    byte ptr [rsp+170h+var_F8], 2
0x180067a12  jnz     short loc_180067994
0x180067a14  cmp     [rsi+20h], ebx
0x180067a17  jz      loc_180067AF7
0x180067a1d  mov     eax, cs:dword_18014E4B8
0x180067a23  mov     r14d, 80070005h
0x180067a29  test    eax, eax
0x180067a2b  jnz     short loc_180067A48
0x180067a2d  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180067a33  jz      loc_180067AED
0x180067a39  xor     ecx, ecx
0x180067a3b  call    IsWppLevelEnabled
0x180067a40  test    al, al
0x180067a42  jz      loc_180067AED
0x180067a48  mov     rcx, [rsi+10h]
0x180067a4c  lea     rdx, [rsp+170h+StringSid]; StringSid
0x180067a51  add     rcx, 9Ch; Sid
0x180067a58  mov     [rsp+170h+StringSid], rbx
0x180067a5d  call    cs:__imp_ConvertSidToStringSidW
0x180067a63  mov     rax, [rsp+170h+StringSid]
0x180067a68  lea     rbx, Class
0x180067a6f  test    rax, rax
0x180067a72  mov     r15, rbx
0x180067a75  cmovnz  r15, rax
0x180067a79  mov     rax, [rsi+8]
0x180067a7d  test    rax, rax
0x180067a80  jz      short loc_180067A8F
0x180067a82  mov     rbx, [rax+180h]
0x180067a89  mov     r12d, [rax+58h]
0x180067a8d  jmp     short loc_180067A92
0x180067a8f  xor     r12d, r12d
0x180067a92  mov     rcx, [rsi+1B8h]; string
0x180067a99  xor     edx, edx; length
0x180067a9b  call    cs:__imp_WindowsGetStringRawBuffer
0x180067aa1  lea     rdx, [rsi+3Ch]; struct _GUID *
0x180067aa5  mov     r11, rax
0x180067aa8  lea     rcx, [rbp+70h+var_90]; this
0x180067aac  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180067ab1  mov     [rsp+170h+var_120], r14d
0x180067ab6  lea     rdx, aCservertableen_3; "CServerTableEntry::StartServerAndWaitIm"...
0x180067abd  mov     [rsp+170h+var_128], r15
0x180067ac2  mov     r8d, 0B34h
0x180067ac8  mov     [rsp+170h+var_130], rbx
0x180067acd  mov     dword ptr [rsp+170h+var_138], r12d
0x180067ad2  mov     [rsp+170h+var_140], r11
0x180067ad7  mov     qword ptr [rsp+170h+var_148], rax
0x180067adc  call    ??$ComTraceMessageT@PEAGPEBGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K23J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,ushort *,long)
0x180067ae1  lea     rcx, [rsp+170h+StringSid]
0x180067ae6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180067aeb  xor     ebx, ebx
0x180067aed  mov     edx, 0B35h
0x180067af2  jmp     loc_180067BBE
0x180067af7  mov     rax, [r14]
0x180067afa  lea     r15, [rdi+10h]
0x180067afe  lea     r8, [rdi+18h]
0x180067b02  mov     qword ptr [rsp+170h+var_148], r13
0x180067b07  lea     r9, [rbp+70h+hObject]
0x180067b0b  mov     qword ptr [rsp+170h+var_150], r15; int
0x180067b10  mov     rdx, rsi
0x180067b13  mov     rcx, r14
0x180067b16  mov     rax, [rax+38h]
0x180067b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067b1f  mov     ebx, eax
0x180067b21  test    eax, eax
0x180067b23  jns     loc_180067CB3
0x180067b29  mov     r9d, eax; char *
0x180067b2c  mov     edx, 0B3Ch; void *
0x180067b31  mov     rcx, [rbp+78h]; this
0x180067b35  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180067b3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067b41  mov     [rbp+70h+var_C8], 0
0x180067b45  lea     rcx, [rbp+70h+var_D8]
0x180067b49  call    _lambda_b15df0fea7fedc2ab86f4cd588ad762e___operator__
0x180067b4e  jmp     loc_180068172
0x180067b53  xor     r13d, r13d
0x180067b56  mov     rcx, [rsi+1B8h]; string
0x180067b5d  xor     edx, edx; length
0x180067b5f  call    cs:__imp_WindowsGetStringRawBuffer
0x180067b65  lea     rdx, [rsi+3Ch]; struct _GUID *
0x180067b69  mov     r11, rax
0x180067b6c  lea     rcx, [rbp+70h+var_90]; this
0x180067b70  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x180067b75  mov     [rsp+170h+var_120], r14d
0x180067b7a  lea     rdx, aCservertableen_3; "CServerTableEntry::StartServerAndWaitIm"...
0x180067b81  mov     [rsp+170h+var_128], r12
0x180067b86  mov     r8d, 0B2Ah
0x180067b8c  mov     [rsp+170h+var_130], rbx
0x180067b91  mov     dword ptr [rsp+170h+var_138], r13d
0x180067b96  mov     [rsp+170h+var_140], r11
0x180067b9b  mov     qword ptr [rsp+170h+var_148], rax
0x180067ba0  call    ??$ComTraceMessageT@PEAGPEBGKPEBGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG2K23J@Z; ComTraceMessageT<ushort *,ushort const *,ulong,ushort const *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort const *,ulong,ushort const *,ushort *,long)
0x180067ba5  lea     rcx, [rsp+170h+StringSid]
0x180067baa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180067baf  mov     r12, [rbp+70h+var_C0]
0x180067bb3  xor     ebx, ebx
0x180067bb5  mov     [r12], r15d
0x180067bb9  mov     edx, 0B2Ch; void *
0x180067bbe  mov     rcx, [rbp+78h]; this
0x180067bc2  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180067bc9  mov     r9d, r14d; char *
0x180067bcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067bd1  cmp     [rdi+18h], rbx
0x180067bd5  jz      short loc_180067C02
0x180067bd7  lea     rcx, [rdi+58h]; lpCriticalSection
0x180067bdb  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x180067be0  mov     rcx, [rdi+18h]; hObject
0x180067be4  test    rcx, rcx
0x180067be7  jz      short loc_180067BF7
0x180067be9  call    cs:__imp_CloseHandle
0x180067bef  mov     qword ptr [rdi+18h], 0
0x180067bf7  lea     rcx, [rdi+58h]; this
0x180067bfb  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x180067c00  xor     ebx, ebx
0x180067c02  cmp     [rdi+0Ch], ebx
0x180067c05  jz      short loc_180067C0D
0x180067c07  mov     rax, [rbp+70h+var_F0]
0x180067c0b  mov     [rax], ebx
0x180067c0d  mov     ebx, r14d
0x180067c10  jmp     loc_180068172
0x180067c15  mov     rax, [r14]
0x180067c18  lea     rbx, [rdi+18h]
0x180067c1c  lea     r15, [rdi+10h]
0x180067c20  mov     qword ptr [rsp+170h+var_148], r13
0x180067c25  lea     r9, [rbp+70h+hObject]
0x180067c29  mov     qword ptr [rsp+170h+var_150], r15; int
0x180067c2e  mov     r8, rbx
0x180067c31  mov     rdx, rsi
0x180067c34  mov     rax, [rax+40h]
0x180067c38  mov     rcx, r14
0x180067c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067c40  mov     r12d, eax
0x180067c43  test    eax, eax
0x180067c45  jns     short loc_180067CB3
0x180067c47  mov     rcx, [rbp+78h]; this
0x180067c4b  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180067c52  mov     r9d, eax; char *
0x180067c55  mov     edx, 0B1Eh; void *
0x180067c5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067c5f  xor     r14d, r14d
0x180067c62  cmp     [rbx], r14
0x180067c65  jz      short loc_180067C8A
0x180067c67  lea     rcx, [rdi+58h]; lpCriticalSection
0x180067c6b  call    ?LockShared@CSharedLock@@QEAAXXZ; CSharedLock::LockShared(void)
0x180067c70  mov     rcx, [rbx]; hObject
0x180067c73  test    rcx, rcx
0x180067c76  jz      short loc_180067C81
0x180067c78  call    cs:__imp_CloseHandle
0x180067c7e  mov     [rbx], r14
0x180067c81  lea     rcx, [rdi+58h]; this
0x180067c85  call    ?UnlockShared@CSharedLock@@QEAAXXZ; CSharedLock::UnlockShared(void)
0x180067c8a  cmp     [rdi+0Ch], r14d
0x180067c8e  jz      short loc_180067C97
0x180067c90  mov     rax, [rbp+70h+var_F0]
0x180067c94  mov     [rax], r14d
0x180067c97  mov     rcx, [rbp+70h+hObject]; hObject
0x180067c9b  lea     rax, [rcx-1]
0x180067c9f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067ca3  ja      short loc_180067CAB
0x180067ca5  call    cs:__imp_CloseHandle
0x180067cab  mov     eax, r12d
0x180067cae  jmp     loc_18006817D
0x180067cb3  cmp     qword ptr [rsi+220h], 0
0x180067cbb  jz      short loc_180067D09
0x180067cbd  movups  xmm0, xmmword ptr [rsi+208h]
0x180067cc4  lea     rax, [rdi+30h]
0x180067cc8  mov     qword ptr [rbp+70h+var_A8.cbSize], 0
0x180067cd0  lea     rdx, [rbp+70h+var_A8]; struct tagBLOB *
0x180067cd4  mov     [rbp+70h+var_B0], rax
0x180067cd8  movdqu  xmmword ptr [rdi+38h], xmm0
0x180067cdd  mov     rcx, [rsi+220h]; this
0x180067ce4  mov     byte ptr [rbp+70h+var_A8.pBlobData], 1
0x180067ce8  call    ?DuplicateBlob@ComBlob@@YAJPEAUtagBLOB@@PEAPEAU2@@Z; ComBlob::DuplicateBlob(tagBLOB *,tagBLOB * *)
0x180067ced  lea     rcx, [rbp+70h+var_B0]
0x180067cf1  mov     ebx, eax
0x180067cf3  call    ??1?$out_param_t@V?$unique_ptr@UtagBLOB@@U?$function_deleter@P6AXPEAUtagBLOB@@@Z$1?DeleteBlob@ComBlob@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&ComBlob::DeleteBlob(tagBLOB *)>>>::~out_param_t<wistd::unique_ptr<tagBLOB,wil::function_deleter<void (*)(tagBLOB *),&ComBlob::DeleteBlob(tagBLOB *)>>>(void)
0x180067cf8  test    ebx, ebx
0x180067cfa  jns     short loc_180067D09
0x180067cfc  mov     r9d, ebx
0x180067cff  mov     edx, 0B43h
0x180067d04  jmp     loc_180067B31
0x180067d09  mov     rcx, [rsp+170h+StringSid]
0x180067d0e  xor     r12d, r12d
0x180067d11  mov     rcx, [rcx+18h]; hEvent
0x180067d15  call    cs:__imp_SetEvent
0x180067d1b  lea     rax, [rsp+170h+StringSid]
0x180067d20  mov     [rsp+170h+StringSid], 0
0x180067d29  lea     r9, [rsi+0F0h]
0x180067d30  mov     qword ptr [rsp+170h+var_150], rax; int
0x180067d35  lea     rdx, [rsi+3Ch]
0x180067d39  mov     r8, r15
0x180067d3c  lea     rcx, [rsp+170h+var_100]
0x180067d41  call    ??$make_unique_nothrow@VCActivationState@@AEAU_GUID@@AEAKAEAK$$T@wil@@YA?AV?$unique_ptr@VCActivationState@@U?$default_delete@VCActivationState@@@wistd@@@wistd@@AEAU_GUID@@AEAK1$$QEA$$T@Z
0x180067d46  mov     rdx, [rsp+170h+var_100]; struct CActivationState *
0x180067d4b  xor     r15d, r15d
0x180067d4e  test    rdx, rdx
0x180067d51  jz      short loc_180067D58
0x180067d53  call    ?Insert@CActivationStateList@@QEAAXPEAVCActivationState@@@Z; CActivationStateList::Insert(CActivationState *)
0x180067d58  mov     rdx, [rbp+70h+hObject]
0x180067d5c  mov     [rsp+170h+StringSid], r15
0x180067d61  lea     rax, [rdx-1]
0x180067d65  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067d69  ja      loc_180067F7A
0x180067d6f  lea     r8, [rsp+170h+StringSid]
0x180067d74  mov     rcx, r14
0x180067d77  call    ?GetActivationActivityIfNeeded@CClassData@@QEAAJPEAXAEAV?$unique_ptr@VActivationActivity@@U?$function_deleter@P6AXPEAVActivationActivity@@@Z$1?DestroyActivationActivity@1@SAX0@Z@wil@@@wistd@@@Z; CClassData::GetActivationActivityIfNeeded(void *,wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&ActivationActivity::DestroyActivationActivity(ActivationActivity *)>> &)
0x180067d7c  mov     ebx, eax
0x180067d7e  test    eax, eax
0x180067d80  jns     loc_180067F7A
0x180067d86  mov     rcx, [rbp+78h]; this
0x180067d8a  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180067d91  mov     r9d, eax; char *
0x180067d94  mov     edx, 0B59h; void *
0x180067d99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180067d9e  xor     edx, edx
  ... truncated ...
```
