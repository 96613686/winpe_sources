# CServerTableEntry::CallRunningServer(ACTIVATION_PARAMS *,ulong,long,CClassData *,long *)

- ea: `0x18000866c`
- end: `0x18000934a`
- name: `?CallRunningServer@CServerTableEntry@@QEAAHPEAUACTIVATION_PARAMS@@KJPEAVCClassData@@PEAJ@Z`
- size: `3294`
- prototype: `int(CServerTableEntry *__hidden this, struct ACTIVATION_PARAMS *, unsigned int, int, struct CClassData *, int *)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180005c80`

## callees

- `0x1800030b4`
- `0x180003cd0`
- `0x180005c40`
- `0x180008648`
- `0x18000866c`
- `0x18000f1b8`
- `0x180013760`
- `0x180014b80`
- `0x180014be0`
- `0x180016160`
- `0x1800220f4`
- `0x180023230`
- `0x180026224`
- `0x18002ba28`
- `0x18002d6cc`
- `0x18002e210`
- `0x18002f058`
- `0x180031910`
- `0x180034540`
- `0x180039088`
- `0x18003e920`
- `0x18003e97c`
- `0x18004fc9c`
- `0x180053950`
- `0x180059be4`
- `0x18005c08c`
- `0x18005d8e0`
- `0x18005e4b0`
- `0x180063190`
- `0x1800700a4`
- `0x180073764`
- `0x18007ba34`
- `0x18008b7dc`
- `0x18008e98c`
- `0x18009df3c`
- `0x18009f8d0`
- `0x1800a167c`
- `0x1800a2570`
- `0x1800b27e0`
- `0x1800b5778`
- `0x1800f4a64`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008af4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008b81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008cfd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b12`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008d1b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b12`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008b9f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180008d1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009090`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000902b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18000902b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008e9c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180008e9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008f35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008dd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180008f35`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000878c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800090bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000927e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000878c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008853`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180008ed9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800090bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000927e`

## string_xrefs

- `0x180008ab9`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180008b4b`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180008fe7`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18000903e`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180009126`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800092a5`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800092ac`: `The specified console handles will be ignored since the activation bound to a running server. CLSID:%ws ACID:%ws`
- `0x18000911b`: `Removing server entry. CLSID:%ls, PID: %#x, image: %ls`

## pseudocode

```c
__int64 __fastcall CServerTableEntry::CallRunningServer(
        CServerTableEntry *this,
        struct ACTIVATION_PARAMS *a2,
        __int64 a3,
        int a4,
        HSTRING *a5,
        int *a6)
{
  int v6; // r12d
  __int64 v8; // rcx
  int ActivationFlags; // eax
  unsigned int matched; // eax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  unsigned __int16 NativeArchitecture; // ax
  int v14; // edx
  int v15; // r8d
  unsigned int v16; // esi
  HSTRING v17; // rax
  int v18; // edx
  int v19; // r8d
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // eax
  _QWORD *v23; // r12
  int v24; // ebx
  __int64 v25; // r13
  __int64 v26; // rax
  struct CToken *v27; // rbx
  int v28; // eax
  unsigned int v29; // edi
  __int64 v30; // rcx
  int LastError; // eax
  int PerAppBrokerMatchToken; // eax
  int v33; // eax
  CServerTableEntry *v34; // rbx
  CSharedLock *v35; // r13
  int v36; // eax
  int v37; // eax
  unsigned int *v38; // rdi
  CServerTableEntry *v39; // rbx
  unsigned int v40; // r13d
  int inited; // eax
  int v42; // eax
  struct _SECURITY_DESCRIPTOR *v43; // rdi
  __int64 v44; // rax
  void (__fastcall *v45)(CServerTableEntry *, HSTRING *); // rbx
  BOOL v46; // ebx
  int *v47; // r9
  void *v48; // rcx
  LPWSTR v49; // r13
  __int64 v50; // rax
  const WCHAR *v51; // rdi
  CGuidStr *v52; // rax
  unsigned int v53; // r11^4
  int v54; // r9d
  __int64 v55; // rdx
  void *LaunchedProcessHandleUnsafe; // rax
  const char *v57; // r9
  CProcess *v58; // rcx
  int ProcessHandle; // eax
  int v60; // ebx
  __int64 v61; // rax
  __int64 v62; // rbx
  unsigned int v63; // edi
  const char *v64; // rax
  const char *v65; // rax
  CServerTableEntry *v66; // rbx
  CSharedLock *v67; // rdi
  char *v68; // rcx
  _QWORD *i; // rax
  int v70; // ebx
  CSurrogateList *v71; // rcx
  unsigned int v72; // ebx
  CGuidStr *v74; // rax
  int v75; // r9d
  __int64 v76; // r11
  char v77; // al
  int v78; // [rsp+20h] [rbp-120h]
  char *v79; // [rsp+28h] [rbp-118h]
  unsigned int v80[2]; // [rsp+30h] [rbp-110h]
  unsigned int v81[2]; // [rsp+40h] [rbp-100h]
  struct CToken *v82; // [rsp+48h] [rbp-F8h]
  struct CClassData *v83; // [rsp+50h] [rbp-F0h]
  unsigned __int8 v84; // [rsp+C0h] [rbp-80h] BYREF
  unsigned __int8 v85[7]; // [rsp+C1h] [rbp-7Fh] BYREF
  HANDLE hObject; // [rsp+C8h] [rbp-78h] BYREF
  int v87; // [rsp+D0h] [rbp-70h]
  unsigned int v88; // [rsp+D4h] [rbp-6Ch] BYREF
  unsigned int v89; // [rsp+D8h] [rbp-68h]
  unsigned int v90; // [rsp+DCh] [rbp-64h]
  bool v91[4]; // [rsp+E0h] [rbp-60h]
  int v92; // [rsp+E4h] [rbp-5Ch]
  unsigned int v93; // [rsp+E8h] [rbp-58h]
  int v94; // [rsp+ECh] [rbp-54h]
  CServerTableEntry *v95; // [rsp+F0h] [rbp-50h]
  int *v96; // [rsp+F8h] [rbp-48h]
  void **v97; // [rsp+100h] [rbp-40h] BYREF
  void *v98; // [rsp+108h] [rbp-38h] BYREF
  int v99; // [rsp+110h] [rbp-30h]
  int v100; // [rsp+114h] [rbp-2Ch]
  LPWSTR StringSid; // [rsp+118h] [rbp-28h] BYREF
  HSTRING string; // [rsp+120h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+128h] [rbp-18h]
  int v104; // [rsp+130h] [rbp-10h]
  int v105; // [rsp+134h] [rbp-Ch]
  unsigned __int64 v106; // [rsp+138h] [rbp-8h]
  __int64 v107; // [rsp+140h] [rbp+0h]
  __int64 v108; // [rsp+148h] [rbp+8h]
  __int64 v109; // [rsp+150h] [rbp+10h]
  struct CToken *v110; // [rsp+158h] [rbp+18h]
  OLECHAR sz[40]; // [rsp+160h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+B8h]

  v95 = this;
  v8 = *((_QWORD *)a2 + 43);
  v94 = a4;
  v96 = a6;
  hObject = 0;
  v88 = 0;
  ActivationFlags = ActivationPropertiesIn::GetActivationFlags((ActivationPropertiesIn *)(v8 + 568), &v88);
  *a6 = ActivationFlags;
  if ( ActivationFlags >= 0 )
  {
    v100 = 0;
    v93 = 0;
    matched = ConvertActivationFlagsToMatchFlags(v88);
    v11 = *((_QWORD *)a2 + 1);
    v12 = matched;
    if ( v11 )
      NativeArchitecture = *(_WORD *)(v11 + 428);
    else
      NativeArchitecture = GetNativeArchitecture();
    LOBYTE(v6) = 0;
    v99 = NativeArchitecture;
    *(_DWORD *)v91 = v6;
    StringRawBuffer = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v88 = CClassData::AppIDFlags((CClassData *)a5);
      v16 = v12 | v15 & (v88 >> 3) | (32 * (v14 & v88)) | (v88 >> 3) & 0x1000 | (8 * (v88 & 0x80 | (4 * (v88 & 2))));
      if ( *((_BYTE *)a5 + 172) )
        StringRawBuffer = WindowsGetStringRawBuffer(a5[17], 0);
      else
        LOWORD(v16) = v16 | 0x800;
      v84 = 0;
      v85[0] = 0;
      CClassData::GetContextAndSubcontext((struct CClassData *)a5, &v84, v85);
      if ( v84 == 3 )
        *(_DWORD *)v91 = v85[0] == 4;
    }
    else
    {
      LOWORD(v16) = v12;
      if ( !a5 )
      {
        v88 = 0;
        v92 = 0;
        v87 = -1;
LABEL_22:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
          || a5 )
        {
          v89 = *((_DWORD *)a5 + 33);
        }
        else
        {
          v89 = 4;
        }
        while ( 1 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
          {
            v20 = *((_QWORD *)a2 + 1);
            if ( v20 )
              v21 = *(_QWORD *)(v20 + 32);
            else
              LODWORD(v21) = 0;
            LODWORD(v83) = v89;
            LODWORD(v82) = *((_DWORD *)a2 + 104);
            v81[0] = *((_DWORD *)a2 + 32);
            v78 = v21;
            v22 = CServerTableEntry::LookupServer(
                    v95,
                    *((_QWORD *)a2 + 2),
                    *((unsigned __int8 *)a2 + 188),
                    *((unsigned int *)a2 + 48));
            v23 = hObject;
            v24 = v22;
          }
          else
          {
            v25 = *((_QWORD *)a2 + 67);
            v108 = *((_QWORD *)a2 + 68);
            v106 = *((_QWORD *)a2 + 63);
            v104 = *((_DWORD *)a2 + 31);
            v105 = *((_DWORD *)a2 + 30);
            LODWORD(StringSid) = *((_DWORD *)a2 + 104);
            v90 = *((_DWORD *)a2 + 32);
            v26 = *((_QWORD *)a2 + 1);
            v109 = v25;
            if ( v26 )
              v107 = *(_QWORD *)(v26 + 32);
            else
              v107 = 0;
            v27 = (struct CToken *)*((_QWORD *)a2 + 2);
            v28 = *((_DWORD *)a2 + 48);
            v29 = *((unsigned __int8 *)a2 + 188);
            v110 = v27;
            LODWORD(hObject) = v28;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
              MicrosoftTelemetryAssertTriggeredNoArgs(v30);
            v23 = 0;
            if ( (unsigned int)CServerTableEntry::IsSuspended(v95) )
            {
              v24 = 1;
              goto LABEL_66;
            }
            v98 = 0;
            v97 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
            if ( (v16 & 0x200) == 0 )
              goto LABEL_52;
            if ( v25 )
            {
              v24 = -2147418113;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x696,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)0x8000FFFFLL,
                v78);
              v97 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
              if ( !v98 )
                goto LABEL_66;
              if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v97) )
              {
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
                RaiseException(LastError, 1u, 0, 0);
                __debugbreak();
              }
              goto LABEL_45;
            }
            PerAppBrokerMatchToken = CServerTableEntry::GetPerAppBrokerMatchToken(v27, v90, v106, v91[0], &v98);
            v24 = PerAppBrokerMatchToken;
            if ( PerAppBrokerMatchToken < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x69F,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)PerAppBrokerMatchToken,
                v78);
              v97 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
              if ( v98 )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v97) )
                {
                  v33 = GetLastError();
                  if ( v33 > 0 )
                    v33 = (unsigned __int16)v33 | 0x80070000;
                  RaiseException(v33, 1u, 0, 0);
                  __debugbreak();
                }
LABEL_45:
                v98 = 0;
              }
            }
            else
            {
LABEL_52:
              v34 = v95;
              v35 = (CServerTableEntry *)((char *)v95 + 88);
              CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)v95 + 88));
              v23 = (_QWORD *)((*((_QWORD *)v34 + 9) - 16LL) & -(__int64)(*((_QWORD *)v34 + 9) != 0));
              if ( v23 )
              {
                while ( 1 )
                {
                  LODWORD(v83) = v105;
                  LODWORD(v82) = v89;
                  v81[0] = (unsigned int)StringSid;
                  v78 = v107;
                  v36 = CServerListEntry::Match(v23, v110, v29, (unsigned int)hObject);
                  v24 = v36;
                  if ( !v36 )
                    break;
                  if ( v36 >= 0 )
                  {
                    v23 = (_QWORD *)((v23[2] - 16LL) & -(__int64)(v23[2] != 0));
                    if ( v23 )
                      continue;
                  }
                  goto LABEL_59;
                }
                (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
              }
              else
              {
                v24 = 1;
LABEL_59:
                v23 = 0;
              }
              CSharedLock::UnlockShared(v35);
              v97 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
              if ( v98 )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v97) )
                {
                  v37 = GetLastError();
                  if ( v37 > 0 )
                    v37 = (unsigned __int16)v37 | 0x80070000;
                  RaiseException(v37, 1u, 0, 0);
                  __debugbreak();
                }
                v98 = 0;
              }
            }
          }
LABEL_66:
          v38 = (unsigned int *)v96;
          *v96 = v24;
          if ( v24 < 0 )
            return 1;
          if ( v24 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
              || a5 )
            {
              v77 = *((_BYTE *)a5 + 80);
              if ( v77 == 2 || v77 == 8 )
              {
                if ( IsServiceStopping(a2, (struct CClassData *)a5) )
                  *v38 = -2146959352;
              }
            }
            return 0;
          }
          v39 = v95;
          v40 = 1;
          *v38 = 0;
          if ( (*(_DWORD *)(v23[12] + 92LL) & 0x40) != 0 )
          {
            inited = CServerTableEntry::WaitForInitCompleted(
                       v39,
                       (struct CServerListEntry *)v23,
                       (struct CClassData *)a5);
            *v38 = inited;
            if ( inited < 0 )
              v40 = inited != -2146959352;
          }
          v42 = CProcess::ActivateProcessIfNeeded(v23[12], v89);
          *v38 = v42;
          if ( v42 < 0 )
            v40 = 1;
          if ( gfCheckActivationSecurity )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
              || (v43 = 0, a5) )
            {
              v43 = CClassData::LaunchPermission((CClassData *)a5);
            }
            v44 = *(_QWORD *)v39;
            string = 0;
            v45 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v44 + 32);
            WindowsDeleteString(0);
            string = 0;
            v45(v95, &string);
            v46 = 0;
            if ( !(unsigned int)LaunchOrActivationAllowed(
                                  *(void **)a2,
                                  (WCHAR *)string,
                                  v43,
                                  *((unsigned __int8 *)a2 + 188),
                                  *((unsigned __int8 *)a2 + 189),
                                  0,
                                  *((_DWORD *)a2 + 32),
                                  *((struct CToken **)a2 + 2),
                                  *((_DWORD *)a2 + 29),
                                  *(struct CToken **)(v23[12] + 24LL),
                                  (struct CClassData *)a5) )
            {
              v47 = v96;
              *v96 = -2147024891;
              if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v48 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
                LODWORD(hObject) = *v47;
                StringSid = 0;
                ConvertSidToStringSidW(v48, &StringSid);
                v49 = (LPWSTR)&Class;
                if ( StringSid )
                  v49 = StringSid;
                v50 = *((_QWORD *)a2 + 1);
                if ( v50 )
                  v51 = *(const WCHAR **)(v50 + 384);
                else
                  v51 = &Class;
                WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
                v52 = CGuidStr::CGuidStr((CGuidStr *)sz, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v83) = (_DWORD)hObject;
                v82 = (struct CToken *)v49;
                *(_QWORD *)v81 = v51;
                v80[1] = v53;
                HIDWORD(v79) = HIDWORD(v52);
                ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
                  (_DWORD)hObject,
                  (unsigned int)"CServerTableEntry::CallRunningServer",
                  2352,
                  v54);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
                v46 = 0;
              }
              v40 = 1;
            }
            WindowsDeleteString(string);
            v38 = (unsigned int *)v96;
            string = 0;
          }
          else
          {
            v46 = 0;
          }
          v90 = 0;
          if ( (*v38 & 0x80000000) == 0 )
          {
            hObject = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
              || a5 )
            {
              *v38 = CClassData::GetActivationActivityIfNeeded(
                       (__int64 *)a5,
                       *(void **)(*(_QWORD *)(v23[12] + 24LL) + 72LL),
                       (__int64)&hObject);
            }
            if ( (*v38 & 0x80000000) != 0 )
            {
              v40 = 1;
            }
            else
            {
              v90 = 1;
              v40 = CServerListEntry::CallServer(
                      (CServerListEntry *)v23,
                      a2,
                      gfIssueActivationRpcAtIdentify | v88 & 4,
                      v38);
            }
            wistd::unique_ptr<ActivationActivity,wil::function_deleter<void (*)(ActivationActivity *),&public: static void ActivationActivity::DestroyActivationActivity(ActivationActivity *)>>::reset(
              &hObject,
              0);
          }
          if ( !v40 )
          {
            if ( *v38 != -2147417851 )
              goto LABEL_104;
            v55 = v23[12];
            *(_QWORD *)v80 = *(_QWORD *)(v55 + 384);
            LODWORD(v79) = *(_DWORD *)(v55 + 88);
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x965,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
              (const char *)0x80010105LL,
              (int)"Terminating server process (PID: %#x, image: %ls) due to server exception",
              v79);
            LaunchedProcessHandleUnsafe = CProcess::GetLaunchedProcessHandleUnsafe((CProcess *)v23[12]);
            if ( LaunchedProcessHandleUnsafe )
            {
              v46 = TerminateProcess(LaunchedProcessHandleUnsafe, 0);
              if ( !v46 )
                wil::details::in1diag3::_Log_GetLastError(
                  retaddr,
                  (void *)0x96B,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                  v57);
            }
            _InterlockedIncrement((volatile signed __int32 *)v23 + 36);
            if ( !v46 )
            {
LABEL_104:
              if ( *v38 != -2146959352 )
              {
                v58 = (CProcess *)v23[12];
                hObject = 0;
                ProcessHandle = CProcess::GetProcessHandle(v58, 0x100000u, &hObject);
                if ( ProcessHandle < 0 )
                {
                  if ( ProcessHandle != -2147024809 )
                  {
LABEL_110:
                    if ( *(_WORD *)v38 == 1722 )
                      v40 = 1;
                    goto LABEL_121;
                  }
                }
                else
                {
                  v60 = IsProcessTerminated(hObject);
                  CloseHandle(hObject);
                  if ( !v60 )
                    goto LABEL_110;
                }
              }
            }
            v61 = v23[12];
            v62 = *(_QWORD *)(v61 + 384);
            v63 = *(_DWORD *)(v61 + 88);
            if ( *((_BYTE *)a2 + 432) )
            {
              v64 = (const char *)WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
              v80[0] = v63;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x97F,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)*v96,
                (int)"Removing server entry. ACID:%ls, PID: %#x, image: %ls",
                v64,
                *(_QWORD *)v80,
                v62,
                *(_QWORD *)v81,
                v82,
                v83);
            }
            else
            {
              v65 = (const char *)GuidString::GuidString(sz, (GUID *)((char *)a2 + 60));
              v80[0] = v63;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x984,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)*v96,
                (int)"Removing server entry. CLSID:%ls, PID: %#x, image: %ls",
                v65,
                *(_QWORD *)v80,
                v62,
                *(_QWORD *)v81,
                v82,
                v83);
            }
            v66 = v95;
            v67 = (CServerTableEntry *)((char *)v95 + 88);
            CSharedLock::LockExclusive((CServerTableEntry *)((char *)v95 + 88));
            v68 = (char *)v66 + 72;
            for ( i = (_QWORD *)*((_QWORD *)v66 + 9); ; i = (_QWORD *)*i )
            {
              if ( !i )
              {
                v70 = 0;
                goto LABEL_118;
              }
              if ( i == v23 + 2 )
                break;
            }
            v70 = 1;
            CListBase<1,1>::Remove(v68, v23 + 2);
LABEL_118:
            CSharedLock::UnlockExclusive(v67);
            CSurrogateList::RemoveMatchingEntry(v71, (struct CServerListEntry *)v23);
            if ( v70 )
            {
              CProcess::RemoveClassReg((CProcess *)v23[12], *((_DWORD *)v23 + 33));
              (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
            }
            v38 = (unsigned int *)v96;
          }
LABEL_121:
          if ( v90 )
          {
            if ( v100 == *((_DWORD *)v23 + 33) )
            {
              v72 = v93 + 1;
            }
            else
            {
              v100 = *((_DWORD *)v23 + 33);
              v72 = 0;
            }
            v93 = v72;
          }
          else
          {
            v72 = v93;
          }
          if ( v94 )
          {
            _InterlockedExchange((volatile __int32 *)v23 + 34, 0);
            (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
            return v40;
          }
          (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          hObject = 0;
          if ( v40 )
          {
            if ( (*v38 & 0x80000000) == 0
              && (((*((_QWORD *)a2 + 73) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
               || ((*((_QWORD *)a2 + 74) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
               || (unsigned __int64)(*((_QWORD *)a2 + 75) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL)
              && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1)) )
            {
              WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
              v74 = CGuidStr::CGuidStr((CGuidStr *)sz, (const struct _GUID *)((char *)a2 + 60));
              ComTraceMessageT<unsigned short *,unsigned short const *>(
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (unsigned int)"CServerTableEntry::CallRunningServer",
                2510,
                v75,
                (__int64)L"The specified console handles will be ignored since the activation bound to a running server. C"
                          "LSID:%ws ACID:%ws",
                v74,
                v76);
            }
            return 1;
          }
          if ( v72 > gdwMaxActivationRetriesPerServer )
            return 1;
        }
      }
      v88 = CClassData::AppIDFlags((CClassData *)a5);
      v16 = v12 | v19 & (v88 >> 3) | (32 * (v18 & v88)) | (v88 >> 3) & 0x1000 | (8 * (v88 & 0x80 | (4 * (v88 & 2))));
      if ( *((_BYTE *)a5 + 172) )
        StringRawBuffer = WindowsGetStringRawBuffer(a5[17], 0);
      else
        LOWORD(v16) = v16 | 0x800;
      v85[0] = 0;
      v84 = 0;
      CClassData::GetContextAndSubcontext((struct CClassData *)a5, v85, &v84);
      if ( v85[0] == 3 )
        v91[0] = v84 == 4;
    }
    v17 = a5[11];
    if ( v17 )
      v87 = *((_DWORD *)v17 + 19);
    else
      v87 = -1;
    v92 = *((_DWORD *)a5 + 47);
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x18000866c  mov     [rsp-8+arg_10], rbx
0x180008671  push    rbp
0x180008672  push    rsi
0x180008673  push    rdi
0x180008674  push    r12
0x180008676  push    r13
0x180008678  push    r14
0x18000867a  push    r15
0x18000867c  lea     rbp, [rsp-80h]
0x180008681  sub     rsp, 1C0h
0x180008688  mov     rax, cs:__security_cookie
0x18000868f  xor     rax, rsp
0x180008692  mov     [rbp+0B0h+var_40], rax
0x180008696  mov     rdi, [rbp+0B0h+arg_28]
0x18000869d  mov     r15, rdx
0x1800086a0  mov     r14, [rbp+0B0h+arg_20]
0x1800086a7  xor     r13d, r13d
0x1800086aa  mov     [rbp+0B0h+var_100], rcx
0x1800086ae  mov     rcx, [rdx+158h]
0x1800086b5  lea     rdx, [rbp+0B0h+var_11C]; unsigned int *
0x1800086b9  add     rcx, 238h; this
0x1800086c0  mov     [rbp+0B0h+var_104], r9d
0x1800086c4  mov     [rbp+0B0h+var_F8], rdi
0x1800086c8  mov     [rbp+0B0h+hObject], r13
0x1800086cc  mov     [rbp+0B0h+var_11C], r13d
0x1800086d0  call    ?GetActivationFlags@ActivationPropertiesIn@@UEAAJPEAK@Z; ActivationPropertiesIn::GetActivationFlags(ulong *)
0x1800086d5  mov     [rdi], eax
0x1800086d7  test    eax, eax
0x1800086d9  js      loc_180009312
0x1800086df  mov     ecx, [rbp+0B0h+var_11C]; unsigned int
0x1800086e2  mov     [rbp+0B0h+var_DC], r13d
0x1800086e6  mov     [rbp+0B0h+var_108], r13d
0x1800086ea  call    ?ConvertActivationFlagsToMatchFlags@@YAKK@Z; ConvertActivationFlagsToMatchFlags(ulong)
0x1800086ef  mov     rcx, [r15+8]
0x1800086f3  mov     ebx, eax
0x1800086f5  test    rcx, rcx
0x1800086f8  jz      short loc_180008703
0x1800086fa  movzx   eax, word ptr [rcx+1ACh]
0x180008701  jmp     short loc_180008708
0x180008703  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x180008708  movzx   eax, ax
0x18000870b  mov     r12b, r13b
0x18000870e  mov     [rbp+0B0h+var_E0], eax
0x180008711  mov     dword ptr [rbp+0B0h+var_110], r12d
0x180008715  mov     [rbp+0B0h+var_C8], r13
0x180008719  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180008720  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180008725  mov     edx, 1
0x18000872a  mov     r8d, 200h
0x180008730  test    al, al
0x180008732  jz      loc_1800087F6
0x180008738  mov     rcx, r14; this
0x18000873b  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x180008740  mov     edi, eax
0x180008742  mov     [rbp+0B0h+var_11C], eax
0x180008745  mov     esi, eax
0x180008747  mov     ecx, eax
0x180008749  and     esi, 2
0x18000874c  and     ecx, 80h
0x180008752  shl     esi, 2
0x180008755  or      esi, ecx
0x180008757  mov     ecx, eax
0x180008759  shl     esi, 3
0x18000875c  and     eax, edx
0x18000875e  shl     eax, 5
0x180008761  shr     ecx, 3
0x180008764  and     ecx, 1000h
0x18000876a  or      esi, ecx
0x18000876c  or      esi, eax
0x18000876e  mov     eax, edi
0x180008770  shr     eax, 3
0x180008773  and     eax, r8d
0x180008776  or      esi, eax
0x180008778  or      esi, ebx
0x18000877a  cmp     [r14+0ACh], r13b
0x180008781  jz      short loc_180008798
0x180008783  mov     rcx, [r14+88h]; string
0x18000878a  xor     edx, edx; length
0x18000878c  call    cs:__imp_WindowsGetStringRawBuffer
0x180008792  mov     [rbp+0B0h+var_C8], rax
0x180008796  jmp     short loc_18000879C
0x180008798  bts     esi, 0Bh
0x18000879c  lea     r8, [rbp+0B0h+var_12F]; unsigned __int8 *
0x1800087a0  mov     [rbp+0B0h+var_130], r13b
0x1800087a4  lea     rdx, [rbp+0B0h+var_130]; unsigned __int8 *
0x1800087a8  mov     [rbp+0B0h+var_12F], r13b
0x1800087ac  mov     rcx, r14; this
0x1800087af  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x1800087b4  cmp     [rbp+0B0h+var_130], 3
0x1800087b8  jnz     short loc_1800087CF
0x1800087ba  cmp     [rbp+0B0h+var_12F], 4
0x1800087be  mov     eax, 1
0x1800087c3  movzx   r12d, r12b
0x1800087c7  cmovz   r12d, eax
0x1800087cb  mov     dword ptr [rbp+0B0h+var_110], r12d
0x1800087cf  mov     rax, [r14+58h]
0x1800087d3  test    rax, rax
0x1800087d6  jz      short loc_1800087E0
0x1800087d8  mov     eax, [rax+4Ch]
0x1800087db  mov     [rbp+0B0h+var_120], eax
0x1800087de  jmp     short loc_1800087E7
0x1800087e0  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x1800087e7  mov     edi, [r14+0BCh]
0x1800087ee  mov     [rbp+0B0h+var_10C], edi
0x1800087f1  jmp     loc_1800088AC
0x1800087f6  mov     esi, ebx
0x1800087f8  test    r14, r14
0x1800087fb  jz      loc_18000889D
0x180008801  mov     rcx, r14; this
0x180008804  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x180008809  mov     edi, eax
0x18000880b  mov     [rbp+0B0h+var_11C], eax
0x18000880e  mov     esi, eax
0x180008810  and     eax, 80h
0x180008815  and     esi, 2
0x180008818  shl     esi, 2
0x18000881b  or      esi, eax
0x18000881d  mov     eax, edi
0x18000881f  shr     eax, 3
0x180008822  and     eax, 1000h
0x180008827  shl     esi, 3
0x18000882a  or      esi, eax
0x18000882c  mov     eax, edi
0x18000882e  and     eax, edx
0x180008830  shl     eax, 5
0x180008833  or      esi, eax
0x180008835  mov     eax, edi
0x180008837  shr     eax, 3
0x18000883a  and     eax, r8d
0x18000883d  or      esi, eax
0x18000883f  or      esi, ebx
0x180008841  cmp     [r14+0ACh], r13b
0x180008848  jz      short loc_18000885F
0x18000884a  mov     rcx, [r14+88h]; string
0x180008851  xor     edx, edx; length
0x180008853  call    cs:__imp_WindowsGetStringRawBuffer
0x180008859  mov     [rbp+0B0h+var_C8], rax
0x18000885d  jmp     short loc_180008863
0x18000885f  bts     esi, 0Bh
0x180008863  lea     r8, [rbp+0B0h+var_130]; unsigned __int8 *
0x180008867  mov     [rbp+0B0h+var_12F], r13b
0x18000886b  lea     rdx, [rbp+0B0h+var_12F]; unsigned __int8 *
0x18000886f  mov     [rbp+0B0h+var_130], r13b
0x180008873  mov     rcx, r14; this
0x180008876  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x18000887b  cmp     [rbp+0B0h+var_12F], 3
0x18000887f  jnz     loc_1800087CF
0x180008885  cmp     [rbp+0B0h+var_130], 4
0x180008889  mov     ecx, 1
0x18000888e  movzx   eax, r12b
0x180008892  cmovz   eax, ecx
0x180008895  mov     [rbp+0B0h+var_110], al
0x180008898  jmp     loc_1800087CF
0x18000889d  mov     [rbp+0B0h+var_11C], r13d
0x1800088a1  mov     [rbp+0B0h+var_10C], r13d
0x1800088a5  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x1800088ac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800088b3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800088b8  test    al, al
0x1800088ba  jnz     short loc_1800088CA
0x1800088bc  test    r14, r14
0x1800088bf  jnz     short loc_1800088CA
0x1800088c1  mov     [rbp+0B0h+var_118], 4
0x1800088c8  jmp     short loc_1800088D4
0x1800088ca  mov     eax, [r14+84h]
0x1800088d1  mov     [rbp+0B0h+var_118], eax
0x1800088d4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800088db  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800088e0  test    al, al
0x1800088e2  jz      loc_1800089ED
0x1800088e8  mov     rax, [r15+8]
0x1800088ec  mov     rdx, [r15+1C8h]
0x1800088f3  mov     r9, [r15+220h]
0x1800088fa  mov     r10, [r15+218h]
0x180008901  mov     r11, [r15+1F8h]
0x180008908  mov     ebx, [r15+7Ch]
0x18000890c  mov     edi, [r15+78h]
0x180008910  mov     r12d, [r15+1A0h]
0x180008917  mov     r13d, [r15+80h]
0x18000891e  test    rax, rax
0x180008921  jz      short loc_180008929
0x180008923  mov     rcx, [rax+20h]
0x180008927  jmp     short loc_18000892B
0x180008929  xor     ecx, ecx
0x18000892b  movzx   r8d, byte ptr [r15+0BCh]
0x180008933  lea     rax, [rbp+0B0h+hObject]
0x180008937  mov     [rsp+1F0h+var_138], rax
0x18000893f  mov     eax, dword ptr [rbp+0B0h+var_110]
0x180008942  mov     [rsp+1F0h+var_140], rdx
0x18000894a  mov     rdx, [r15+10h]
0x18000894e  mov     byte ptr [rsp+1F0h+var_148], al
0x180008955  mov     eax, [rbp+0B0h+var_10C]
0x180008958  mov     [rsp+1F0h+var_150], eax
0x18000895f  mov     eax, [rbp+0B0h+var_E0]
0x180008962  mov     [rsp+1F0h+var_158], eax
0x180008969  mov     rax, [rbp+0B0h+var_C8]
0x18000896d  mov     [rsp+1F0h+var_160], rax
0x180008975  lea     rax, [r15+208h]
0x18000897c  mov     [rsp+1F0h+var_168], r9
0x180008984  mov     r9d, [r15+0C0h]
0x18000898b  mov     [rsp+1F0h+var_170], r10
0x180008993  mov     [rsp+1F0h+var_178], rax
0x180008998  lea     rax, [r15+1F0h]
0x18000899f  mov     [rsp+1F0h+var_180], r11
0x1800089a4  mov     [rsp+1F0h+var_188], rax
0x1800089a9  mov     eax, [rbp+0B0h+var_118]
0x1800089ac  mov     dword ptr [rsp+1F0h+var_190], ebx
0x1800089b0  mov     [rsp+1F0h+var_198], edi
0x1800089b4  mov     dword ptr [rsp+1F0h+var_1A0], eax
0x1800089b8  mov     eax, [rbp+0B0h+var_104]
0x1800089bb  mov     dword ptr [rsp+1F0h+var_1A8], r12d
0x1800089c0  mov     [rsp+1F0h+var_1B0], r13d
0x1800089c5  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x1800089c9  mov     eax, [rbp+0B0h+var_120]
0x1800089cc  mov     [rsp+1F0h+var_1C0], eax
0x1800089d0  mov     dword ptr [rsp+1F0h+var_1C8], esi
0x1800089d4  mov     [rsp+1F0h+var_1D0], rcx
0x1800089d9  mov     rcx, [rbp+0B0h+var_100]
0x1800089dd  call    ?LookupServer@CServerTableEntry@@QEAAJPEAVCToken@@HHPEAGKW4ServerProtectionLevel@@JJKW4_PSM_ACTIVATE_BACKGROUND_TYPE@@KKPEA_K_KAEBU_GUID@@0PEAUtagBLOB@@PEBGKK_N8PEAPEAVCServerListEntry@@@Z; CServerTableEntry::LookupServer(CToken *,int,int,ushort *,ulong,ServerProtectionLevel,long,long,ulong,_PSM_ACTIVATE_BACKGROUND_TYPE,ulong,ulong,unsigned __int64 *,unsigned __int64,_GUID const &,CToken *,tagBLOB *,ushort const *,ulong,ulong,bool,ushort const *,CServerListEntry * *)
0x1800089e2  mov     r12, [rbp+0B0h+hObject]
0x1800089e6  mov     ebx, eax
0x1800089e8  jmp     loc_180008D2A
0x1800089ed  mov     rax, [r15+220h]
0x1800089f4  mov     r13, [r15+218h]
0x1800089fb  mov     [rbp+0B0h+var_A8], rax
0x1800089ff  mov     rax, [r15+1F8h]
0x180008a06  mov     [rbp+0B0h+var_B8], rax
0x180008a0a  mov     eax, [r15+7Ch]
0x180008a0e  mov     [rbp+0B0h+var_C0], eax
0x180008a11  mov     eax, [r15+78h]
0x180008a15  mov     [rbp+0B0h+var_BC], eax
0x180008a18  mov     eax, [r15+1A0h]
0x180008a1f  mov     dword ptr [rbp+0B0h+StringSid], eax
0x180008a22  mov     eax, [r15+80h]
0x180008a29  mov     [rbp+0B0h+var_114], eax
0x180008a2c  mov     rax, [r15+8]
0x180008a30  mov     [rbp+0B0h+var_A0], r13
0x180008a34  test    rax, rax
0x180008a37  jz      short loc_180008A43
0x180008a39  mov     rbx, [rax+20h]
0x180008a3d  mov     [rbp+0B0h+var_B0], rbx
0x180008a41  jmp     short loc_180008A4B
0x180008a43  mov     [rbp+0B0h+var_B0], 0
0x180008a4b  mov     rbx, [r15+10h]
0x180008a4f  mov     eax, [r15+0C0h]
0x180008a56  movzx   edi, byte ptr [r15+0BCh]
0x180008a5e  mov     [rbp+0B0h+var_98], rbx
0x180008a62  mov     dword ptr [rbp+0B0h+hObject], eax
0x180008a65  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180008a6c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180008a71  test    al, al
0x180008a73  jz      short loc_180008A7A
0x180008a75  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180008a7a  mov     rcx, [rbp+0B0h+var_100]; this
0x180008a7e  xor     r12d, r12d
0x180008a81  call    ?IsSuspended@CServerTableEntry@@QEAAHXZ; CServerTableEntry::IsSuspended(void)
0x180008a86  test    eax, eax
0x180008a88  jz      short loc_180008A94
0x180008a8a  lea     ebx, [r12+1]
0x180008a8f  jmp     loc_180008D2A
0x180008a94  mov     [rbp+0B0h+var_E8], r12
0x180008a98  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180008a9f  mov     [rbp+0B0h+var_F0], rax
0x180008aa3  bt      esi, 9
0x180008aa7  jnb     loc_180008BA6
0x180008aad  test    r13, r13
0x180008ab0  jz      short loc_180008B22
0x180008ab2  mov     rcx, [rbp+0B8h]; this
0x180008ab9  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180008ac0  mov     ebx, 8000FFFFh
0x180008ac5  mov     edx, 696h; void *
0x180008aca  mov     r9d, ebx; char *
0x180008acd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ad2  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180008ad9  mov     [rbp+0B0h+var_F0], rax
0x180008add  cmp     [rbp+0B0h+var_E8], r12
0x180008ae1  jz      loc_180008D2A
0x180008ae7  lea     rcx, [rbp+0B0h+var_F0]
0x180008aeb  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x180008af0  test    al, al
0x180008af2  jnz     short loc_180008B19
0x180008af4  call    cs:__imp_GetLastError
0x180008afa  test    eax, eax
0x180008afc  jle     short loc_180008B06
0x180008afe  movzx   eax, ax
0x180008b01  or      eax, 80070000h
0x180008b06  xor     r9d, r9d; lpArguments
0x180008b09  xor     r8d, r8d; nNumberOfArguments
0x180008b0c  mov     ecx, eax; dwExceptionCode
0x180008b0e  lea     edx, [r9+1]; dwExceptionFlags
0x180008b12  call    cs:__imp_RaiseException
0x180008b18  int     3; Trap to Debugger
0x180008b19  mov     [rbp+0B0h+var_E8], r12
0x180008b1d  jmp     loc_180008D2A
0x180008b22  mov     r9b, [rbp+0B0h+var_110]; bool
0x180008b26  lea     rax, [rbp+0B0h+var_E8]
0x180008b2a  mov     r8, [rbp+0B0h+var_B8]; unsigned __int64
0x180008b2e  mov     rcx, rbx; this
0x180008b31  mov     edx, [rbp+0B0h+var_114]; unsigned int
0x180008b34  mov     [rsp+1F0h+var_1D0], rax; int
  ... truncated ...
```
