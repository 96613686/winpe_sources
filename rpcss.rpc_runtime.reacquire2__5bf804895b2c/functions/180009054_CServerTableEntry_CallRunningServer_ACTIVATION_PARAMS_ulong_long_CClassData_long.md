# CServerTableEntry::CallRunningServer(ACTIVATION_PARAMS *,ulong,long,CClassData *,long *)

- ea: `0x180009054`
- end: `0x180009d71`
- name: `?CallRunningServer@CServerTableEntry@@QEAAHPEAUACTIVATION_PARAMS@@KJPEAVCClassData@@PEAJ@Z`
- size: `3357`
- prototype: `int(CServerTableEntry *__hidden this, struct ACTIVATION_PARAMS *, unsigned int, int, struct CClassData *, int *)`
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800065e4`

## callees

- `0x1800065a4`
- `0x18000902c`
- `0x180009054`
- `0x18000b398`
- `0x180013b18`
- `0x180017880`
- `0x180018d24`
- `0x180018d8c`
- `0x18001a374`
- `0x1800210f8`
- `0x180022ddc`
- `0x180023dc4`
- `0x180025088`
- `0x18002d440`
- `0x1800306dc`
- `0x180034260`
- `0x18004056c`
- `0x180046930`
- `0x180046994`
- `0x180050fd0`
- `0x1800522a0`
- `0x18005232c`
- `0x180059760`
- `0x180060bbc`
- `0x180061fc0`
- `0x180062c04`
- `0x180064120`
- `0x180066584`
- `0x1800748b0`
- `0x180077f10`
- `0x1800806a4`
- `0x180087cd0`
- `0x1800902a4`
- `0x180090910`
- `0x180091a10`
- `0x180095c0c`
- `0x1800a4c08`
- `0x1800a6b6c`
- `0x1800a7b14`
- `0x1800b7ac0`
- `0x1800baa94`
- `0x1800fc8a0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009d51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a44`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009a44`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800099d9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800099d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009835`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180009835`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800098da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180009768`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800098da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009a76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009c3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009174`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009241`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009878`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009a76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180009c3e`

## string_xrefs

- `0x1800094ad`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x18000951e`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180009995`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x1800099f2`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180009ae6`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180009c6b`: `onecore\com\combase\rpcss\olescm\class.cxx`
- `0x180009adb`: `Removing server entry. CLSID:%ls, PID: %#x, image: %ls`
- `0x180009c72`: `The specified console handles will be ignored since the activation bound to a running server. CLSID:%ws ACID:%ws`

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
  int PerAppBrokerMatchToken; // eax
  CServerTableEntry *v32; // rbx
  CSharedLock *v33; // r13
  int v34; // eax
  unsigned int *v35; // rdi
  CServerTableEntry *v36; // rbx
  unsigned int v37; // r13d
  int inited; // eax
  int v39; // eax
  struct _SECURITY_DESCRIPTOR *v40; // rdi
  __int64 v41; // rax
  void (__fastcall *v42)(CServerTableEntry *, HSTRING *); // rbx
  BOOL v43; // ebx
  int *v44; // r9
  void *v45; // rcx
  LPWSTR v46; // r13
  __int64 v47; // rax
  const WCHAR *v48; // rdi
  CGuidStr *v49; // rax
  unsigned int v50; // r11^4
  int v51; // r9d
  __int64 v52; // rdx
  void *LaunchedProcessHandleUnsafe; // rax
  const char *v54; // r9
  CProcess *v55; // rcx
  int ProcessHandle; // eax
  int v57; // ebx
  __int64 v58; // rax
  __int64 v59; // rbx
  unsigned int v60; // edi
  const char *v61; // rax
  const char *v62; // rax
  CServerTableEntry *v63; // rbx
  CSharedLock *v64; // rdi
  _QWORD *i; // rax
  int v66; // ebx
  CSurrogateList *v67; // rcx
  unsigned int v68; // ebx
  CGuidStr *v70; // rax
  int v71; // r9d
  __int64 v72; // r11
  char v73; // al
  signed int v74; // eax
  int v75; // edx
  unsigned int v76; // r8d
  signed int v77; // eax
  int v78; // edx
  unsigned int v79; // r8d
  signed int LastError; // eax
  int v81; // edx
  unsigned int v82; // r8d
  int v83; // [rsp+20h] [rbp-120h]
  char *v84; // [rsp+28h] [rbp-118h]
  unsigned int v85[2]; // [rsp+30h] [rbp-110h]
  unsigned int v86[2]; // [rsp+40h] [rbp-100h]
  struct CToken *v87; // [rsp+48h] [rbp-F8h]
  struct CClassData *v88; // [rsp+50h] [rbp-F0h]
  unsigned __int8 v89; // [rsp+C0h] [rbp-80h] BYREF
  unsigned __int8 v90[7]; // [rsp+C1h] [rbp-7Fh] BYREF
  HANDLE hObject; // [rsp+C8h] [rbp-78h] BYREF
  int v92; // [rsp+D0h] [rbp-70h]
  unsigned int v93; // [rsp+D4h] [rbp-6Ch] BYREF
  unsigned int v94; // [rsp+D8h] [rbp-68h]
  unsigned int v95; // [rsp+DCh] [rbp-64h]
  bool v96[4]; // [rsp+E0h] [rbp-60h]
  int v97; // [rsp+E4h] [rbp-5Ch]
  unsigned int v98; // [rsp+E8h] [rbp-58h]
  int v99; // [rsp+ECh] [rbp-54h]
  CServerTableEntry *v100; // [rsp+F0h] [rbp-50h]
  int *v101; // [rsp+F8h] [rbp-48h]
  void **v102; // [rsp+100h] [rbp-40h] BYREF
  void *v103; // [rsp+108h] [rbp-38h] BYREF
  int v104; // [rsp+110h] [rbp-30h]
  int v105; // [rsp+114h] [rbp-2Ch]
  LPWSTR StringSid; // [rsp+118h] [rbp-28h] BYREF
  HSTRING string; // [rsp+120h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+128h] [rbp-18h]
  int v109; // [rsp+130h] [rbp-10h]
  int v110; // [rsp+134h] [rbp-Ch]
  unsigned __int64 v111; // [rsp+138h] [rbp-8h]
  __int64 v112; // [rsp+140h] [rbp+0h]
  __int64 v113; // [rsp+148h] [rbp+8h]
  __int64 v114; // [rsp+150h] [rbp+10h]
  struct CToken *v115; // [rsp+158h] [rbp+18h]
  OLECHAR sz[40]; // [rsp+160h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+B8h]

  v100 = this;
  v8 = *((_QWORD *)a2 + 43);
  v99 = a4;
  v101 = a6;
  hObject = 0;
  v93 = 0;
  ActivationFlags = ActivationPropertiesIn::GetActivationFlags((ActivationPropertiesIn *)(v8 + 568), &v93);
  *a6 = ActivationFlags;
  if ( ActivationFlags >= 0 )
  {
    v105 = 0;
    v98 = 0;
    matched = ConvertActivationFlagsToMatchFlags(v93);
    v11 = *((_QWORD *)a2 + 1);
    v12 = matched;
    if ( v11 )
      NativeArchitecture = *(_WORD *)(v11 + 428);
    else
      NativeArchitecture = GetNativeArchitecture();
    LOBYTE(v6) = 0;
    v104 = NativeArchitecture;
    *(_DWORD *)v96 = v6;
    StringRawBuffer = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
    {
      v93 = CClassData::AppIDFlags((CClassData *)a5);
      v16 = v12 | v15 & (v93 >> 3) | (32 * (v14 & v93)) | (v93 >> 3) & 0x1000 | (8 * (v93 & 0x80 | (4 * (v93 & 2))));
      if ( *((_BYTE *)a5 + 172) )
        StringRawBuffer = WindowsGetStringRawBuffer(a5[17], 0);
      else
        LOWORD(v16) = v16 | 0x800;
      v89 = 0;
      v90[0] = 0;
      CClassData::GetContextAndSubcontext((struct CClassData *)a5, &v89, v90);
      if ( v89 == 3 )
        *(_DWORD *)v96 = v90[0] == 4;
    }
    else
    {
      LOWORD(v16) = v12;
      if ( !a5 )
      {
        v93 = 0;
        v97 = 0;
        v92 = -1;
LABEL_22:
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
          || a5 )
        {
          v94 = *((_DWORD *)a5 + 33);
        }
        else
        {
          v94 = 4;
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
            LODWORD(v88) = v94;
            LODWORD(v87) = *((_DWORD *)a2 + 104);
            v86[0] = *((_DWORD *)a2 + 32);
            v83 = v21;
            v22 = CServerTableEntry::LookupServer(
                    v100,
                    *((_QWORD *)a2 + 2),
                    *((unsigned __int8 *)a2 + 188),
                    *((unsigned int *)a2 + 48));
            v23 = hObject;
            v24 = v22;
          }
          else
          {
            v25 = *((_QWORD *)a2 + 67);
            v113 = *((_QWORD *)a2 + 68);
            v111 = *((_QWORD *)a2 + 63);
            v109 = *((_DWORD *)a2 + 31);
            v110 = *((_DWORD *)a2 + 30);
            LODWORD(StringSid) = *((_DWORD *)a2 + 104);
            v95 = *((_DWORD *)a2 + 32);
            v26 = *((_QWORD *)a2 + 1);
            v114 = v25;
            if ( v26 )
              v112 = *(_QWORD *)(v26 + 32);
            else
              v112 = 0;
            v27 = (struct CToken *)*((_QWORD *)a2 + 2);
            v28 = *((_DWORD *)a2 + 48);
            v29 = *((unsigned __int8 *)a2 + 188);
            v115 = v27;
            LODWORD(hObject) = v28;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl) )
              MicrosoftTelemetryAssertTriggeredNoArgs(v30);
            v23 = 0;
            if ( (unsigned int)CServerTableEntry::IsSuspended(v100) )
            {
              v24 = 1;
              goto LABEL_58;
            }
            v103 = 0;
            v102 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
            if ( (v16 & 0x200) == 0 )
              goto LABEL_47;
            if ( v25 )
            {
              v24 = -2147418113;
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x696,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)0x8000FFFFLL,
                v83);
              v102 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
              if ( !v103 )
                goto LABEL_58;
              if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v102) )
              {
                LastError = GetLastError();
                if ( LastError > 0 )
                  LastError = (unsigned __int16)LastError | 0x80070000;
                Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v81, v82);
                JUMPOUT(0x180009D70LL);
              }
              goto LABEL_42;
            }
            PerAppBrokerMatchToken = CServerTableEntry::GetPerAppBrokerMatchToken(v27, v95, v111, v96[0], &v103);
            v24 = PerAppBrokerMatchToken;
            if ( PerAppBrokerMatchToken < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x69F,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)PerAppBrokerMatchToken,
                v83);
              v102 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
              if ( v103 )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v102) )
                {
                  v77 = GetLastError();
                  if ( v77 > 0 )
                    v77 = (unsigned __int16)v77 | 0x80070000;
                  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v77, v78, v79);
                  __debugbreak();
                }
LABEL_42:
                v103 = 0;
              }
            }
            else
            {
LABEL_47:
              v32 = v100;
              v33 = (CServerTableEntry *)((char *)v100 + 88);
              CSharedLock::LockShared((LPCRITICAL_SECTION)((char *)v100 + 88));
              v23 = (_QWORD *)((*((_QWORD *)v32 + 9) - 16LL) & -(__int64)(*((_QWORD *)v32 + 9) != 0));
              if ( v23 )
              {
                while ( 1 )
                {
                  LODWORD(v88) = v110;
                  LODWORD(v87) = v94;
                  v86[0] = (unsigned int)StringSid;
                  v83 = v112;
                  v34 = CServerListEntry::Match(v23, v115, v29, (unsigned int)hObject);
                  v24 = v34;
                  if ( !v34 )
                    break;
                  if ( v34 >= 0 )
                  {
                    v23 = (_QWORD *)((v23[2] - 16LL) & -(__int64)(v23[2] != 0));
                    if ( v23 )
                      continue;
                  }
                  goto LABEL_54;
                }
                (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
              }
              else
              {
                v24 = 1;
LABEL_54:
                v23 = 0;
              }
              CSharedLock::UnlockShared(v33);
              v102 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
              if ( v103 )
              {
                if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(&v102) )
                {
                  v74 = GetLastError();
                  if ( v74 > 0 )
                    v74 = (unsigned __int16)v74 | 0x80070000;
                  Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v74, v75, v76);
                  __debugbreak();
                }
                v103 = 0;
              }
            }
          }
LABEL_58:
          v35 = (unsigned int *)v101;
          *v101 = v24;
          if ( v24 < 0 )
            return 1;
          if ( v24 )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
              || a5 )
            {
              v73 = *((_BYTE *)a5 + 80);
              if ( v73 == 2 || v73 == 8 )
              {
                if ( IsServiceStopping(a2, (struct CClassData *)a5) )
                  *v35 = -2146959352;
              }
            }
            return 0;
          }
          v36 = v100;
          v37 = 1;
          *v35 = 0;
          if ( (*(_DWORD *)(v23[12] + 92LL) & 0x40) != 0 )
          {
            inited = CServerTableEntry::WaitForInitCompleted(
                       v36,
                       (struct CServerListEntry *)v23,
                       (struct CClassData *)a5);
            *v35 = inited;
            if ( inited < 0 )
              v37 = inited != -2146959352;
          }
          v39 = CProcess::ActivateProcessIfNeeded(v23[12], v94);
          *v35 = v39;
          if ( v39 < 0 )
            v37 = 1;
          if ( gfCheckActivationSecurity )
          {
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
              || (v40 = 0, a5) )
            {
              v40 = CClassData::LaunchPermission((CClassData *)a5);
            }
            v41 = *(_QWORD *)v36;
            string = 0;
            v42 = *(void (__fastcall **)(CServerTableEntry *, HSTRING *))(v41 + 32);
            WindowsDeleteString(0);
            string = 0;
            v42(v100, &string);
            v43 = 0;
            if ( !(unsigned int)LaunchOrActivationAllowed(
                                  *(void **)a2,
                                  (WCHAR *)string,
                                  v40,
                                  *((unsigned __int8 *)a2 + 188),
                                  *((unsigned __int8 *)a2 + 189),
                                  0,
                                  *((_DWORD *)a2 + 32),
                                  *((struct CToken **)a2 + 2),
                                  *((_DWORD *)a2 + 29),
                                  *(struct CToken **)(v23[12] + 24LL),
                                  (struct CClassData *)a5) )
            {
              v44 = v101;
              *v101 = -2147024891;
              if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
              {
                v45 = (void *)(*((_QWORD *)a2 + 2) + 156LL);
                LODWORD(hObject) = *v44;
                StringSid = 0;
                ConvertSidToStringSidW(v45, &StringSid);
                v46 = (LPWSTR)&Class;
                if ( StringSid )
                  v46 = StringSid;
                v47 = *((_QWORD *)a2 + 1);
                if ( v47 )
                  v48 = *(const WCHAR **)(v47 + 384);
                else
                  v48 = &Class;
                WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
                v49 = CGuidStr::CGuidStr((CGuidStr *)sz, (const struct _GUID *)((char *)a2 + 60));
                LODWORD(v88) = (_DWORD)hObject;
                v87 = (struct CToken *)v46;
                *(_QWORD *)v86 = v48;
                v85[1] = v50;
                HIDWORD(v84) = HIDWORD(v49);
                ComTraceMessageT<unsigned short *,unsigned short const *,unsigned long,unsigned short const *,unsigned short *,long>(
                  (_DWORD)hObject,
                  (unsigned int)"CServerTableEntry::CallRunningServer",
                  2352,
                  v51);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
                v43 = 0;
              }
              v37 = 1;
            }
            WindowsDeleteString(string);
            v35 = (unsigned int *)v101;
            string = 0;
          }
          else
          {
            v43 = 0;
          }
          v95 = 0;
          if ( (*v35 & 0x80000000) == 0 )
          {
            hObject = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl'::`2'::impl)
              || a5 )
            {
              *v35 = CClassData::GetActivationActivityIfNeeded(
                       a5,
                       *(_QWORD *)(*(_QWORD *)(v23[12] + 24LL) + 72LL),
                       &hObject);
            }
            if ( (*v35 & 0x80000000) != 0 )
            {
              v37 = 1;
            }
            else
            {
              v95 = 1;
              v37 = CServerListEntry::CallServer(
                      (CServerListEntry *)v23,
                      a2,
                      gfIssueActivationRpcAtIdentify | v93 & 4,
                      v35);
            }
            if ( hObject )
              ActivationActivity::DestroyActivationActivity((struct ActivationActivity *)hObject);
          }
          if ( !v37 )
          {
            if ( *v35 != -2147417851 )
              goto LABEL_97;
            v52 = v23[12];
            *(_QWORD *)v85 = *(_QWORD *)(v52 + 384);
            LODWORD(v84) = *(_DWORD *)(v52 + 88);
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x965,
              (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
              (const char *)0x80010105LL,
              (int)"Terminating server process (PID: %#x, image: %ls) due to server exception",
              v84);
            LaunchedProcessHandleUnsafe = CProcess::GetLaunchedProcessHandleUnsafe((CProcess *)v23[12]);
            if ( LaunchedProcessHandleUnsafe )
            {
              v43 = TerminateProcess(LaunchedProcessHandleUnsafe, 0);
              if ( !v43 )
                wil::details::in1diag3::_Log_GetLastError(
                  retaddr,
                  (void *)0x96B,
                  (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                  v54);
            }
            _InterlockedIncrement((volatile signed __int32 *)v23 + 36);
            if ( !v43 )
            {
LABEL_97:
              if ( *v35 != -2146959352 )
              {
                v55 = (CProcess *)v23[12];
                hObject = 0;
                ProcessHandle = CProcess::GetProcessHandle(v55, 0x100000u, &hObject);
                if ( ProcessHandle < 0 )
                {
                  if ( ProcessHandle != -2147024809 )
                  {
LABEL_103:
                    if ( *(_WORD *)v35 == 1722 )
                      v37 = 1;
                    goto LABEL_114;
                  }
                }
                else
                {
                  v57 = IsProcessTerminated(hObject);
                  CloseHandle(hObject);
                  if ( !v57 )
                    goto LABEL_103;
                }
              }
            }
            v58 = v23[12];
            v59 = *(_QWORD *)(v58 + 384);
            v60 = *(_DWORD *)(v58 + 88);
            if ( *((_BYTE *)a2 + 432) )
            {
              v61 = (const char *)WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
              v85[0] = v60;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x97F,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)*v101,
                (int)"Removing server entry. ACID:%ls, PID: %#x, image: %ls",
                v61,
                *(_QWORD *)v85,
                v59,
                *(_QWORD *)v86,
                v87,
                v88);
            }
            else
            {
              v62 = (const char *)GuidString::GuidString(sz, (GUID *)((char *)a2 + 60));
              v85[0] = v60;
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x984,
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (const char *)(unsigned int)*v101,
                (int)"Removing server entry. CLSID:%ls, PID: %#x, image: %ls",
                v62,
                *(_QWORD *)v85,
                v59,
                *(_QWORD *)v86,
                v87,
                v88);
            }
            v63 = v100;
            v64 = (CServerTableEntry *)((char *)v100 + 88);
            CSharedLock::LockExclusive((CServerTableEntry *)((char *)v100 + 88));
            for ( i = (_QWORD *)*((_QWORD *)v63 + 9); ; i = (_QWORD *)*i )
            {
              if ( !i )
              {
                v66 = 0;
                goto LABEL_111;
              }
              if ( i == v23 + 2 )
                break;
            }
            v66 = 1;
            CListBase<1,1>::Remove();
LABEL_111:
            CSharedLock::UnlockExclusive(v64);
            CSurrogateList::RemoveMatchingEntry(v67, (struct CServerListEntry *)v23);
            if ( v66 )
            {
              CProcess::RemoveClassReg((CProcess *)v23[12], *((_DWORD *)v23 + 33));
              (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
            }
            v35 = (unsigned int *)v101;
          }
LABEL_114:
          if ( v95 )
          {
            if ( v105 == *((_DWORD *)v23 + 33) )
            {
              v68 = v98 + 1;
            }
            else
            {
              v105 = *((_DWORD *)v23 + 33);
              v68 = 0;
            }
            v98 = v68;
          }
          else
          {
            v68 = v98;
          }
          if ( v99 )
          {
            _InterlockedExchange((volatile __int32 *)v23 + 34, 0);
            (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
            return v37;
          }
          (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
          hObject = 0;
          if ( v37 )
          {
            if ( (*v35 & 0x80000000) == 0
              && (((*((_QWORD *)a2 + 73) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
               || ((*((_QWORD *)a2 + 74) + 1LL) & 0xFFFFFFFFFFFFFFFEuLL) != 0
               || (unsigned __int64)(*((_QWORD *)a2 + 75) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL)
              && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1)) )
            {
              WindowsGetStringRawBuffer(*((HSTRING *)a2 + 55), 0);
              v70 = CGuidStr::CGuidStr((CGuidStr *)sz, (const struct _GUID *)((char *)a2 + 60));
              ComTraceMessageT<unsigned short *,unsigned short const *>(
                (unsigned int)"onecore\\com\\combase\\rpcss\\olescm\\class.cxx",
                (unsigned int)"CServerTableEntry::CallRunningServer",
                2510,
                v71,
                (__int64)L"The specified console handles will be ignored since the activation bound to a running server. C"
                          "LSID:%ws ACID:%ws",
                v70,
                v72);
            }
            return 1;
          }
          if ( v68 > gdwMaxActivationRetriesPerServer )
            return 1;
        }
      }
      v93 = CClassData::AppIDFlags((CClassData *)a5);
      v16 = v12 | v19 & (v93 >> 3) | (32 * (v18 & v93)) | (v93 >> 3) & 0x1000 | (8 * (v93 & 0x80 | (4 * (v93 & 2))));
      if ( *((_BYTE *)a5 + 172) )
        StringRawBuffer = WindowsGetStringRawBuffer(a5[17], 0);
      else
        LOWORD(v16) = v16 | 0x800;
      v90[0] = 0;
      v89 = 0;
      CClassData::GetContextAndSubcontext((struct CClassData *)a5, v90, &v89);
      if ( v90[0] == 3 )
        v96[0] = v89 == 4;
    }
    v17 = a5[11];
    if ( v17 )
      v92 = *((_DWORD *)v17 + 19);
    else
      v92 = -1;
    v97 = *((_DWORD *)a5 + 47);
    goto LABEL_22;
  }
  return 0;
}

```

## disassembly

```asm
0x180009054  mov     [rsp-8+arg_10], rbx
0x180009059  push    rbp
0x18000905a  push    rsi
0x18000905b  push    rdi
0x18000905c  push    r12
0x18000905e  push    r13
0x180009060  push    r14
0x180009062  push    r15
0x180009064  lea     rbp, [rsp-80h]
0x180009069  sub     rsp, 1C0h
0x180009070  mov     rax, cs:__security_cookie
0x180009077  xor     rax, rsp
0x18000907a  mov     [rbp+0B0h+var_40], rax
0x18000907e  mov     rdi, [rbp+0B0h+arg_28]
0x180009085  mov     r15, rdx
0x180009088  mov     r14, [rbp+0B0h+arg_20]
0x18000908f  xor     r13d, r13d
0x180009092  mov     [rbp+0B0h+var_100], rcx
0x180009096  mov     rcx, [rdx+158h]
0x18000909d  lea     rdx, [rbp+0B0h+var_11C]; unsigned int *
0x1800090a1  add     rcx, 238h; this
0x1800090a8  mov     [rbp+0B0h+var_104], r9d
0x1800090ac  mov     [rbp+0B0h+var_F8], rdi
0x1800090b0  mov     [rbp+0B0h+hObject], r13
0x1800090b4  mov     [rbp+0B0h+var_11C], r13d
0x1800090b8  call    ?GetActivationFlags@ActivationPropertiesIn@@UEAAJPEAK@Z; ActivationPropertiesIn::GetActivationFlags(ulong *)
0x1800090bd  mov     [rdi], eax
0x1800090bf  test    eax, eax
0x1800090c1  js      loc_180009CD8
0x1800090c7  mov     ecx, [rbp+0B0h+var_11C]; unsigned int
0x1800090ca  mov     [rbp+0B0h+var_DC], r13d
0x1800090ce  mov     [rbp+0B0h+var_108], r13d
0x1800090d2  call    ?ConvertActivationFlagsToMatchFlags@@YAKK@Z; ConvertActivationFlagsToMatchFlags(ulong)
0x1800090d7  mov     rcx, [r15+8]
0x1800090db  mov     ebx, eax
0x1800090dd  test    rcx, rcx
0x1800090e0  jz      short loc_1800090EB
0x1800090e2  movzx   eax, word ptr [rcx+1ACh]
0x1800090e9  jmp     short loc_1800090F0
0x1800090eb  call    ?GetNativeArchitecture@@YAGXZ; GetNativeArchitecture(void)
0x1800090f0  movzx   eax, ax
0x1800090f3  mov     r12b, r13b
0x1800090f6  mov     [rbp+0B0h+var_E0], eax
0x1800090f9  mov     dword ptr [rbp+0B0h+var_110], r12d
0x1800090fd  mov     [rbp+0B0h+var_C8], r13
0x180009101  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180009108  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x18000910d  mov     edx, 1
0x180009112  mov     r8d, 200h
0x180009118  test    al, al
0x18000911a  jz      loc_1800091E4
0x180009120  mov     rcx, r14; this
0x180009123  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x180009128  mov     edi, eax
0x18000912a  mov     [rbp+0B0h+var_11C], eax
0x18000912d  mov     esi, eax
0x18000912f  mov     ecx, eax
0x180009131  and     esi, 2
0x180009134  and     ecx, 80h
0x18000913a  shl     esi, 2
0x18000913d  or      esi, ecx
0x18000913f  mov     ecx, eax
0x180009141  shl     esi, 3
0x180009144  and     eax, edx
0x180009146  shl     eax, 5
0x180009149  shr     ecx, 3
0x18000914c  and     ecx, 1000h
0x180009152  or      esi, ecx
0x180009154  or      esi, eax
0x180009156  mov     eax, edi
0x180009158  shr     eax, 3
0x18000915b  and     eax, r8d
0x18000915e  or      esi, eax
0x180009160  or      esi, ebx
0x180009162  cmp     [r14+0ACh], r13b
0x180009169  jz      short loc_180009186
0x18000916b  mov     rcx, [r14+88h]; string
0x180009172  xor     edx, edx; length
0x180009174  call    cs:__imp_WindowsGetStringRawBuffer
0x18000917b  nop     dword ptr [rax+rax+00h]
0x180009180  mov     [rbp+0B0h+var_C8], rax
0x180009184  jmp     short loc_18000918A
0x180009186  bts     esi, 0Bh
0x18000918a  lea     r8, [rbp+0B0h+var_12F]; unsigned __int8 *
0x18000918e  mov     [rbp+0B0h+var_130], r13b
0x180009192  lea     rdx, [rbp+0B0h+var_130]; unsigned __int8 *
0x180009196  mov     [rbp+0B0h+var_12F], r13b
0x18000919a  mov     rcx, r14; this
0x18000919d  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x1800091a2  cmp     [rbp+0B0h+var_130], 3
0x1800091a6  jnz     short loc_1800091BD
0x1800091a8  cmp     [rbp+0B0h+var_12F], 4
0x1800091ac  mov     ecx, 1
0x1800091b1  movzx   r12d, r12b
0x1800091b5  cmovz   r12d, ecx
0x1800091b9  mov     dword ptr [rbp+0B0h+var_110], r12d
0x1800091bd  mov     rax, [r14+58h]
0x1800091c1  test    rax, rax
0x1800091c4  jz      short loc_1800091CE
0x1800091c6  mov     eax, [rax+4Ch]
0x1800091c9  mov     [rbp+0B0h+var_120], eax
0x1800091cc  jmp     short loc_1800091D5
0x1800091ce  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x1800091d5  mov     edi, [r14+0BCh]
0x1800091dc  mov     [rbp+0B0h+var_10C], edi
0x1800091df  jmp     loc_1800092A0
0x1800091e4  mov     esi, ebx
0x1800091e6  test    r14, r14
0x1800091e9  jz      loc_180009291
0x1800091ef  mov     rcx, r14; this
0x1800091f2  call    ?AppIDFlags@CClassData@@QEAAKXZ; CClassData::AppIDFlags(void)
0x1800091f7  mov     edi, eax
0x1800091f9  mov     [rbp+0B0h+var_11C], eax
0x1800091fc  mov     esi, eax
0x1800091fe  and     eax, 80h
0x180009203  and     esi, 2
0x180009206  shl     esi, 2
0x180009209  or      esi, eax
0x18000920b  mov     eax, edi
0x18000920d  shr     eax, 3
0x180009210  and     eax, 1000h
0x180009215  shl     esi, 3
0x180009218  or      esi, eax
0x18000921a  mov     eax, edi
0x18000921c  and     eax, edx
0x18000921e  shl     eax, 5
0x180009221  or      esi, eax
0x180009223  mov     eax, edi
0x180009225  shr     eax, 3
0x180009228  and     eax, r8d
0x18000922b  or      esi, eax
0x18000922d  or      esi, ebx
0x18000922f  cmp     [r14+0ACh], r13b
0x180009236  jz      short loc_180009253
0x180009238  mov     rcx, [r14+88h]; string
0x18000923f  xor     edx, edx; length
0x180009241  call    cs:__imp_WindowsGetStringRawBuffer
0x180009248  nop     dword ptr [rax+rax+00h]
0x18000924d  mov     [rbp+0B0h+var_C8], rax
0x180009251  jmp     short loc_180009257
0x180009253  bts     esi, 0Bh
0x180009257  lea     r8, [rbp+0B0h+var_130]; unsigned __int8 *
0x18000925b  mov     [rbp+0B0h+var_12F], r13b
0x18000925f  lea     rdx, [rbp+0B0h+var_12F]; unsigned __int8 *
0x180009263  mov     [rbp+0B0h+var_130], r13b
0x180009267  mov     rcx, r14; this
0x18000926a  call    ?GetContextAndSubcontext@CClassData@@SAXPEAV1@PEAE1@Z; CClassData::GetContextAndSubcontext(CClassData *,uchar *,uchar *)
0x18000926f  cmp     [rbp+0B0h+var_12F], 3
0x180009273  jnz     loc_1800091BD
0x180009279  cmp     [rbp+0B0h+var_130], 4
0x18000927d  mov     ecx, 1
0x180009282  movzx   eax, r12b
0x180009286  cmovz   eax, ecx
0x180009289  mov     [rbp+0B0h+var_110], al
0x18000928c  jmp     loc_1800091BD
0x180009291  mov     [rbp+0B0h+var_11C], r13d
0x180009295  mov     [rbp+0B0h+var_10C], r13d
0x180009299  mov     [rbp+0B0h+var_120], 0FFFFFFFFh
0x1800092a0  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800092a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800092ac  test    al, al
0x1800092ae  jnz     short loc_1800092BE
0x1800092b0  test    r14, r14
0x1800092b3  jnz     short loc_1800092BE
0x1800092b5  mov     [rbp+0B0h+var_118], 4
0x1800092bc  jmp     short loc_1800092C8
0x1800092be  mov     eax, [r14+84h]
0x1800092c5  mov     [rbp+0B0h+var_118], eax
0x1800092c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x1800092cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x1800092d4  test    al, al
0x1800092d6  jz      loc_1800093E1
0x1800092dc  mov     rax, [r15+8]
0x1800092e0  mov     rdx, [r15+1C8h]
0x1800092e7  mov     r9, [r15+220h]
0x1800092ee  mov     r10, [r15+218h]
0x1800092f5  mov     r11, [r15+1F8h]
0x1800092fc  mov     ebx, [r15+7Ch]
0x180009300  mov     edi, [r15+78h]
0x180009304  mov     r12d, [r15+1A0h]
0x18000930b  mov     r13d, [r15+80h]
0x180009312  test    rax, rax
0x180009315  jz      short loc_18000931D
0x180009317  mov     rcx, [rax+20h]
0x18000931b  jmp     short loc_18000931F
0x18000931d  xor     ecx, ecx
0x18000931f  movzx   r8d, byte ptr [r15+0BCh]
0x180009327  lea     rax, [rbp+0B0h+hObject]
0x18000932b  mov     [rsp+1F0h+var_138], rax
0x180009333  mov     eax, dword ptr [rbp+0B0h+var_110]
0x180009336  mov     [rsp+1F0h+var_140], rdx
0x18000933e  mov     rdx, [r15+10h]
0x180009342  mov     byte ptr [rsp+1F0h+var_148], al
0x180009349  mov     eax, [rbp+0B0h+var_10C]
0x18000934c  mov     [rsp+1F0h+var_150], eax
0x180009353  mov     eax, [rbp+0B0h+var_E0]
0x180009356  mov     [rsp+1F0h+var_158], eax
0x18000935d  mov     rax, [rbp+0B0h+var_C8]
0x180009361  mov     [rsp+1F0h+var_160], rax
0x180009369  lea     rax, [r15+208h]
0x180009370  mov     [rsp+1F0h+var_168], r9
0x180009378  mov     r9d, [r15+0C0h]
0x18000937f  mov     [rsp+1F0h+var_170], r10
0x180009387  mov     [rsp+1F0h+var_178], rax
0x18000938c  lea     rax, [r15+1F0h]
0x180009393  mov     [rsp+1F0h+var_180], r11
0x180009398  mov     [rsp+1F0h+var_188], rax
0x18000939d  mov     eax, [rbp+0B0h+var_118]
0x1800093a0  mov     dword ptr [rsp+1F0h+var_190], ebx
0x1800093a4  mov     [rsp+1F0h+var_198], edi
0x1800093a8  mov     dword ptr [rsp+1F0h+var_1A0], eax
0x1800093ac  mov     eax, [rbp+0B0h+var_104]
0x1800093af  mov     dword ptr [rsp+1F0h+var_1A8], r12d
0x1800093b4  mov     [rsp+1F0h+var_1B0], r13d
0x1800093b9  mov     dword ptr [rsp+1F0h+var_1B8], eax
0x1800093bd  mov     eax, [rbp+0B0h+var_120]
0x1800093c0  mov     [rsp+1F0h+var_1C0], eax
0x1800093c4  mov     dword ptr [rsp+1F0h+var_1C8], esi
0x1800093c8  mov     [rsp+1F0h+var_1D0], rcx
0x1800093cd  mov     rcx, [rbp+0B0h+var_100]
0x1800093d1  call    ?LookupServer@CServerTableEntry@@QEAAJPEAVCToken@@HHPEAGKW4ServerProtectionLevel@@JJKW4_PSM_ACTIVATE_BACKGROUND_TYPE@@KKPEA_K_KAEBU_GUID@@0PEAUtagBLOB@@PEBGKK_N8PEAPEAVCServerListEntry@@@Z; CServerTableEntry::LookupServer(CToken *,int,int,ushort *,ulong,ServerProtectionLevel,long,long,ulong,_PSM_ACTIVATE_BACKGROUND_TYPE,ulong,ulong,unsigned __int64 *,unsigned __int64,_GUID const &,CToken *,tagBLOB *,ushort const *,ulong,ulong,bool,ushort const *,CServerListEntry * *)
0x1800093d6  mov     r12, [rbp+0B0h+hObject]
0x1800093da  mov     ebx, eax
0x1800093dc  jmp     loc_1800096BD
0x1800093e1  mov     rax, [r15+220h]
0x1800093e8  mov     r13, [r15+218h]
0x1800093ef  mov     [rbp+0B0h+var_A8], rax
0x1800093f3  mov     rax, [r15+1F8h]
0x1800093fa  mov     [rbp+0B0h+var_B8], rax
0x1800093fe  mov     eax, [r15+7Ch]
0x180009402  mov     [rbp+0B0h+var_C0], eax
0x180009405  mov     eax, [r15+78h]
0x180009409  mov     [rbp+0B0h+var_BC], eax
0x18000940c  mov     eax, [r15+1A0h]
0x180009413  mov     dword ptr [rbp+0B0h+StringSid], eax
0x180009416  mov     eax, [r15+80h]
0x18000941d  mov     [rbp+0B0h+var_114], eax
0x180009420  mov     rax, [r15+8]
0x180009424  mov     [rbp+0B0h+var_A0], r13
0x180009428  test    rax, rax
0x18000942b  jz      short loc_180009437
0x18000942d  mov     rbx, [rax+20h]
0x180009431  mov     [rbp+0B0h+var_B0], rbx
0x180009435  jmp     short loc_18000943F
0x180009437  mov     [rbp+0B0h+var_B0], 0
0x18000943f  mov     rbx, [r15+10h]
0x180009443  mov     eax, [r15+0C0h]
0x18000944a  movzx   edi, byte ptr [r15+0BCh]
0x180009452  mov     [rbp+0B0h+var_98], rbx
0x180009456  mov     dword ptr [rbp+0B0h+hObject], eax
0x180009459  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport> `wil::Feature<__WilFeatureTraits_Feature_PackagedComElevationSupport>::GetImpl(void)'::`2'::impl
0x180009460  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PackagedComElevationSupport@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PackagedComElevationSupport>::__private_IsEnabled(void)
0x180009465  test    al, al
0x180009467  jz      short loc_18000946E
0x180009469  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000946e  mov     rcx, [rbp+0B0h+var_100]; this
0x180009472  xor     r12d, r12d
0x180009475  call    ?IsSuspended@CServerTableEntry@@QEAAHXZ; CServerTableEntry::IsSuspended(void)
0x18000947a  test    eax, eax
0x18000947c  jz      short loc_180009488
0x18000947e  lea     ebx, [r12+1]
0x180009483  jmp     loc_1800096BD
0x180009488  mov     [rbp+0B0h+var_E8], r12
0x18000948c  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180009493  mov     [rbp+0B0h+var_F0], rax
0x180009497  bt      esi, 9
0x18000949b  jnb     loc_18000955A
0x1800094a1  test    r13, r13
0x1800094a4  jz      short loc_1800094F5
0x1800094a6  mov     rcx, [rbp+0B8h]; this
0x1800094ad  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x1800094b4  mov     ebx, 8000FFFFh
0x1800094b9  mov     edx, 696h; void *
0x1800094be  mov     r9d, ebx; char *
0x1800094c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094c6  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800094cd  mov     [rbp+0B0h+var_F0], rax
0x1800094d1  cmp     [rbp+0B0h+var_E8], r12
0x1800094d5  jz      loc_1800096BD
0x1800094db  lea     rcx, [rbp+0B0h+var_F0]
0x1800094df  call    ?InternalClose@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::InternalClose(void)
0x1800094e4  test    al, al
0x1800094e6  jz      loc_180009D51
0x1800094ec  mov     [rbp+0B0h+var_E8], r12
0x1800094f0  jmp     loc_1800096BD
0x1800094f5  mov     r9b, [rbp+0B0h+var_110]; bool
0x1800094f9  lea     rax, [rbp+0B0h+var_E8]
0x1800094fd  mov     r8, [rbp+0B0h+var_B8]; unsigned __int64
0x180009501  mov     rcx, rbx; this
0x180009504  mov     edx, [rbp+0B0h+var_114]; unsigned int
0x180009507  mov     [rsp+1F0h+var_1D0], rax; int
0x18000950c  call    ?GetPerAppBrokerMatchToken@CServerTableEntry@@SAJPEAVCToken@@K_K_NPEAPEAX@Z; CServerTableEntry::GetPerAppBrokerMatchToken(CToken *,ulong,unsigned __int64,bool,void * *)
0x180009511  mov     ebx, eax
0x180009513  test    eax, eax
0x180009515  jns     short loc_18000955A
0x180009517  mov     rcx, [rbp+0B8h]; this
0x18000951e  lea     r8, aOnecoreComComb_6; "onecore\\com\\combase\\rpcss\\olescm\\c"...
0x180009525  mov     r9d, eax; char *
0x180009528  mov     edx, 69Fh; void *
0x18000952d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
