# SourceInitiatedSubscription::Activate(ushort const *,SubscriptionReadData const &)

- ea: `0x180009a10`
- end: `0x18000a932`
- name: `?Activate@SourceInitiatedSubscription@@UEAAXPEBGAEBVSubscriptionReadData@@@Z`
- size: `3874`
- prototype: `void __fastcall(SourceInitiatedSubscription *this, unsigned __int16 *, const struct SubscriptionReadData *)`
- caller_count: `0`
- callee_count: `48`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000195c`
- `0x1800024b0`
- `0x180002510`
- `0x1800032dc`
- `0x1800034f0`
- `0x180003810`
- `0x180003a50`
- `0x180003cc8`
- `0x180003d48`
- `0x18000526c`
- `0x1800062d4`
- `0x1800064e0`
- `0x18000669c`
- `0x18000676c`
- `0x1800069f0`
- `0x1800075c8`
- `0x180007f98`
- `0x180009a10`
- `0x18000bbec`
- `0x18000d0f0`
- `0x18000d468`
- `0x18000db1c`
- `0x18000dc4c`
- `0x180010058`
- `0x1800103b8`
- `0x180010b60`
- `0x180010c38`
- `0x1800113b4`
- `0x18001141c`
- `0x180011618`
- `0x18001dd2c`
- `0x18001dd6c`
- `0x18001ddac`
- `0x18001dec4`
- `0x18001df04`
- `0x18001df44`
- `0x18001e08c`
- `0x18001e0cc`
- `0x18001e10c`
- `0x18001e14c`
- `0x18001e18c`
- `0x18001e1cc`
- `0x18001e20c`
- `0x18001e660`
- `0x18001e734`
- `0x18001f000`
- `0x18001fe50`
- `0x180023010`

## import_xrefs

- `msvcrt!_ultow` at `0x180009fab`
- `msvcrt!_ultow` at `0x180009fab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a8be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009a57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009beb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009beb`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180009f2f`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x180009f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000a3a5`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a3fa`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000a3fa`
- `WsmSvc!WSManCreatePushSubscription` at `0x18000a543`
- `WsmSvc!WSManCreatePushSubscription` at `0x18000a543`
- `WsmSvc!WSManCloseObjectHandle` at `0x18000a702`
- `WsmSvc!WSManCloseObjectHandle` at `0x18000a814`
- `WsmSvc!WSManCreateSessionInternal` at `0x180009e54`
- `WsmSvc!WSManCreateSessionInternal` at `0x180009e54`

## string_xrefs

- `0x18000a7dc`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000a893`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`
- `0x18000a906`: `admin\wmi\events\forwarding\collector\service\submgr.cpp`

## pseudocode

```c
void __fastcall SourceInitiatedSubscription::Activate(
        SourceInitiatedSubscription *this,
        unsigned __int16 *a2,
        const struct SubscriptionReadData *a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // r13
  _QWORD *v8; // r12
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdx
  _QWORD *v12; // r9
  _WORD *v13; // rcx
  __int64 v14; // rcx
  _QWORD *v15; // r9
  _QWORD *v16; // r8
  _QWORD *v17; // rax
  unsigned int v18; // edx
  _QWORD *v19; // r8
  const unsigned __int16 *v20; // rdi
  const unsigned __int16 *v21; // rdx
  _QWORD *v22; // rax
  _QWORD *v23; // rax
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  const WCHAR *v27; // rcx
  _QWORD *v28; // rax
  _QWORD *v29; // rax
  _WORD *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // r8
  PVOID *v44; // r10
  unsigned int Id; // eax
  __int64 v46; // r10
  __int64 v47; // rdx
  int v48; // r8d
  unsigned int v49; // ebx
  __int64 v50; // r8
  unsigned int v51; // ebx
  DWORD LastError; // ebx
  int v53; // eax
  SourceInitiatedSubscription *v54; // rdx
  Subscription *v55; // rdx
  const unsigned __int16 *v56; // rax
  unsigned int v57; // r8d
  const unsigned __int16 *v58; // r9
  int v59; // [rsp+20h] [rbp-578h]
  unsigned int Value[2]; // [rsp+50h] [rbp-548h] BYREF
  bool v61; // [rsp+58h] [rbp-540h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp-538h] BYREF
  void *v63[2]; // [rsp+68h] [rbp-530h] BYREF
  __int64 v64; // [rsp+78h] [rbp-520h]
  __int128 v65; // [rsp+80h] [rbp-518h] BYREF
  __int64 v66; // [rsp+90h] [rbp-508h]
  SourceInitiatedSubscription *v67; // [rsp+98h] [rbp-500h]
  __int128 v68; // [rsp+A0h] [rbp-4F8h] BYREF
  __int64 v69; // [rsp+B0h] [rbp-4E8h]
  _BYTE v70[8]; // [rsp+B8h] [rbp-4E0h] BYREF
  HLOCAL (__stdcall *v71)(HLOCAL); // [rsp+C0h] [rbp-4D8h]
  __int64 v72; // [rsp+C8h] [rbp-4D0h]
  __int128 v73; // [rsp+D0h] [rbp-4C8h] BYREF
  __int128 v74; // [rsp+E0h] [rbp-4B8h]
  PSECURITY_DESCRIPTOR v75; // [rsp+F0h] [rbp-4A8h]
  char v76[8]; // [rsp+F8h] [rbp-4A0h] BYREF
  SourceInitiatedSubscription *v77; // [rsp+100h] [rbp-498h]
  void (__fastcall *v78)(SourceInitiatedSubscription *__hidden); // [rsp+108h] [rbp-490h]
  _QWORD *v79; // [rsp+110h] [rbp-488h] BYREF
  _QWORD *v80; // [rsp+118h] [rbp-480h]
  int v81; // [rsp+120h] [rbp-478h]
  int v82; // [rsp+124h] [rbp-474h]
  __int128 *v83; // [rsp+128h] [rbp-470h]
  void (__fastcall *v84)(const struct _WSMAN_EVENTS_RESULT *, const struct WSMAN_SENDER_DETAILS_INTERNAL *, struct WSMAN_DELIVERY *, struct SubscriptionCallbackContext *); // [rsp+130h] [rbp-468h]
  struct WSMAN_OBJECT *(__fastcall *v85)(const struct WSMAN_SENDER_DETAILS_INTERNAL *, _QWORD *); // [rsp+138h] [rbp-460h]
  char *v86; // [rsp+140h] [rbp-458h]
  _QWORD v87[2]; // [rsp+150h] [rbp-448h] BYREF
  __int128 v88; // [rsp+160h] [rbp-438h]
  __int64 v89; // [rsp+170h] [rbp-428h]
  __int64 v90; // [rsp+178h] [rbp-420h]
  int v91; // [rsp+180h] [rbp-418h]
  int v92; // [rsp+184h] [rbp-414h]
  void *v93; // [rsp+188h] [rbp-410h]
  __int64 v94; // [rsp+190h] [rbp-408h]
  __int128 v95; // [rsp+1A0h] [rbp-3F8h] BYREF
  __int64 v96; // [rsp+1B0h] [rbp-3E8h]
  char *v97; // [rsp+1B8h] [rbp-3E0h]
  wmi::Exception *v98; // [rsp+1C0h] [rbp-3D8h] BYREF
  _BYTE v99[24]; // [rsp+1C8h] [rbp-3D0h] BYREF
  _BYTE v100[24]; // [rsp+1E0h] [rbp-3B8h] BYREF
  _BYTE v101[24]; // [rsp+1F8h] [rbp-3A0h] BYREF
  unsigned __int64 v102; // [rsp+210h] [rbp-388h]
  __int64 v103; // [rsp+218h] [rbp-380h]
  _BYTE v104[56]; // [rsp+260h] [rbp-338h] BYREF
  _BYTE v105[56]; // [rsp+298h] [rbp-300h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+2D0h] [rbp-2C8h] BYREF
  __int128 v107; // [rsp+308h] [rbp-290h] BYREF
  __int128 v108; // [rsp+318h] [rbp-280h]
  _BYTE v109[24]; // [rsp+328h] [rbp-270h] BYREF
  _QWORD v110[2]; // [rsp+340h] [rbp-258h] BYREF
  __int64 v111; // [rsp+350h] [rbp-248h]
  unsigned __int64 v112; // [rsp+358h] [rbp-240h]
  _QWORD v113[3]; // [rsp+360h] [rbp-238h] BYREF
  unsigned __int64 v114; // [rsp+378h] [rbp-220h]
  _QWORD v115[2]; // [rsp+380h] [rbp-218h] BYREF
  __int64 v116; // [rsp+390h] [rbp-208h]
  unsigned __int64 v117; // [rsp+398h] [rbp-200h]
  _QWORD v118[2]; // [rsp+3A0h] [rbp-1F8h] BYREF
  __int64 v119; // [rsp+3B0h] [rbp-1E8h]
  unsigned __int64 v120; // [rsp+3B8h] [rbp-1E0h]
  _WORD v121[8]; // [rsp+3C0h] [rbp-1D8h] BYREF
  __int64 v122; // [rsp+3D0h] [rbp-1C8h]
  __int64 v123; // [rsp+3D8h] [rbp-1C0h]
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+3E0h] [rbp-1B8h] BYREF
  __int64 v125; // [rsp+3F0h] [rbp-1A8h]
  unsigned __int64 v126; // [rsp+3F8h] [rbp-1A0h]
  _QWORD v127[2]; // [rsp+400h] [rbp-198h] BYREF
  __int64 v128; // [rsp+410h] [rbp-188h]
  unsigned __int64 v129; // [rsp+418h] [rbp-180h]
  _QWORD v130[2]; // [rsp+420h] [rbp-178h] BYREF
  __int64 v131; // [rsp+430h] [rbp-168h]
  unsigned __int64 v132; // [rsp+438h] [rbp-160h]
  _QWORD v133[2]; // [rsp+440h] [rbp-158h] BYREF
  __int64 v134; // [rsp+450h] [rbp-148h]
  unsigned __int64 v135; // [rsp+458h] [rbp-140h]
  _QWORD v136[2]; // [rsp+460h] [rbp-138h] BYREF
  __int64 v137; // [rsp+470h] [rbp-128h]
  unsigned __int64 v138; // [rsp+478h] [rbp-120h]
  _QWORD v139[2]; // [rsp+480h] [rbp-118h] BYREF
  __int64 v140; // [rsp+490h] [rbp-108h]
  unsigned __int64 v141; // [rsp+498h] [rbp-100h]
  _SYSTEMTIME SystemTime; // [rsp+4A0h] [rbp-F8h] BYREF
  _WORD v143[8]; // [rsp+4B0h] [rbp-E8h] BYREF
  __int64 v144; // [rsp+4C0h] [rbp-D8h]
  __int64 v145; // [rsp+4C8h] [rbp-D0h]
  wchar_t Buffer[64]; // [rsp+4D0h] [rbp-C8h] BYREF

  SecurityDescriptor = a2;
  v67 = this;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  v97 = (char *)this + 16;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  _EventSources::_EventSources((_EventSources *)v100);
  SubscriptionReadData::GetEventSources(a3, (struct _EventSources *)v100);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear((char *)this + 296);
  v6 = 0;
  v7 = v102;
  if ( v102 )
  {
    do
    {
      v8 = (_QWORD *)(v103 + 32 * v6);
      if ( v8[3] >= 8u )
        v8 = (_QWORD *)*v8;
      v9 = std::vector<bool>::operator[](v101, &SystemTime, v6);
      if ( ((1 << *(_QWORD *)(v9 + 8)) & **(_DWORD **)v9) == 0 )
      {
        std::wstring::wstring(v121, v8);
        LOBYTE(v59) = byte_18002F7B8;
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(
          (char *)this + 296,
          v63,
          v10,
          v121,
          v59);
        LOBYTE(v11) = 1;
        std::wstring::_Tidy(v121, v11, 0);
        v7 = v102;
      }
      ++v6;
    }
    while ( v6 < v7 );
    v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  }
  if ( SecurityDescriptor )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v12 = (_QWORD *)((char *)this + 56);
      if ( *((_QWORD *)this + 10) >= 8u )
        v12 = (_QWORD *)*v12;
      WPP_SF_SS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        69,
        (int)&WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
        (int)v12,
        (__int64)SecurityDescriptor);
    }
  }
  else if ( *((_BYTE *)this + 96) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 70);
    }
  }
  else
  {
    *((_DWORD *)this + 57) = 0;
    if ( *((_QWORD *)this + 32) < 8u )
      v13 = (_WORD *)((char *)this + 232);
    else
      v13 = (_WORD *)*((_QWORD *)this + 29);
    *((_QWORD *)this + 31) = 0;
    *v13 = 0;
    v76[0] = 0;
    v77 = this;
    v78 = SourceInitiatedSubscription::InternalDeactivate;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 71);
    }
    v120 = 7;
    v119 = 0;
    LOWORD(v118[0]) = 0;
    v117 = 7;
    v116 = 0;
    LOWORD(v115[0]) = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      SubscriptionReadData::GetLogFile(a3, v115);
      SubscriptionReadData::GetPublisherName(a3, v118);
      v14 = v119;
      if ( !v119 && !v116 )
      {
        std::wstring::assign(v115, L"ForwardedEvents");
        v14 = v119;
      }
      if ( v14 )
      {
        v15 = v118;
        if ( v120 >= 8 )
          v15 = (_QWORD *)v118[0];
      }
      else
      {
        v15 = 0;
      }
      if ( v116 )
      {
        v16 = v115;
        if ( v117 >= 8 )
          v16 = (_QWORD *)v115[0];
      }
      else
      {
        v16 = 0;
      }
      *(_QWORD *)Value = (*(__int64 (__fastcall **)(_QWORD, void **, _QWORD *, _QWORD *))(**(_QWORD **)(*((_QWORD *)this + 13) + 128LL)
                                                                                        + 8LL))(
                           *(_QWORD *)(*((_QWORD *)this + 13) + 128LL),
                           v63,
                           v16,
                           v15);
      wmi::AutoRef<AbstractEventProcessor>::Release((char *)this + 112);
      v17 = *(_QWORD **)Value;
      *((_QWORD *)this + 14) = **(_QWORD **)Value;
      *v17 = 0;
      wmi::AutoRef<AbstractEventProcessor>::Release(v63);
      v145 = 7;
      v144 = 0;
      v143[0] = 0;
      SubscriptionReadData::GetLocale(a3, v143);
      v95 = 0;
      v96 = 0;
      InitWSManConnectionOptions(v143, &v95);
      v68 = 0;
      v69 = 0;
      if ( !(unsigned int)WSManCreateSessionInternal(0, 0, 0, 0, &v95, &v68, (char *)this + 208, 0) )
      {
        if ( v69 )
        {
          wmi::MakeGuard<int (*)(WSMAN_OBJECT *),WSMAN_OBJECT *>(v70, WSManCloseObjectHandle);
          if ( DWORD2(v68) )
            DecodeWSManObject(v50, (__int64)this + 232);
          wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v70);
        }
        v51 = DWORD2(v68);
        if ( !DWORD2(v68) )
          v51 = 1287;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v51);
        }
        wmi::GenericException::GenericException(
          (wmi::GenericException *)v104,
          v51,
          "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
          2788);
        throw (wmi::GenericException *)v104;
      }
      if ( v144 )
        SetWSManSessionOptionsLocales(*((WSMAN_SESSION_HANDLE *)this + 26));
      v114 = 7;
      v113[2] = 0;
      LOWORD(v113[0]) = 0;
      SubscriptionReadData::GetURI(a3, v113);
      v123 = 7;
      v122 = 0;
      v121[0] = 0;
      SubscriptionReadData::GetDialect(a3, v121);
      v141 = 7;
      v140 = 0;
      LOWORD(v139[0]) = 0;
      SubscriptionReadData::GetQuery(a3, v139);
      *((_QWORD *)this + 11) = 0;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, v18, (struct _FILETIME *)this + 11);
      SystemTime = 0;
      FileTimeToSystemTime((const FILETIME *)this + 11, &SystemTime);
      v112 = 7;
      v111 = 0;
      LOWORD(v110[0]) = 0;
      SubscriptionReadData::GetTransportName(a3, v110);
      if ( v111 )
      {
        Value[0] = 0;
        ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0xCu, Value);
        if ( Value[0] )
        {
          Value[0] = 0;
          ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0xCu, Value);
          _ultow(Value[0], Buffer, 10);
          std::wstring::append(v110, L":");
          std::wstring::append(v110, Buffer);
        }
      }
      v138 = 7;
      v137 = 0;
      LOWORD(v136[0]) = 0;
      SubscriptionReadData::GetHostName(a3, v136);
      v135 = 7;
      v134 = 0;
      LOWORD(v133[0]) = 0;
      SubscriptionReadData::GetAllowedIssuerCAs(a3, v133);
      v132 = 7;
      v131 = 0;
      LOWORD(v130[0]) = 0;
      SubscriptionReadData::GetAllowedSubjects(a3, v130);
      v129 = 7;
      v128 = 0;
      LOWORD(v127[0]) = 0;
      SubscriptionReadData::GetDeniedSubjects(a3, v127);
      v126 = 7;
      v125 = 0;
      LOWORD(StringSecurityDescriptor[0]) = 0;
      SubscriptionReadData::GetAllowedSourceDomainComputers(a3, StringSecurityDescriptor);
      *(_OWORD *)v63 = 0;
      v64 = 0;
      Value[0] = 2;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0x12u, Value);
      v19 = v113;
      if ( v114 >= 8 )
        LODWORD(v19) = v113[0];
      v20 = (const unsigned __int16 *)((char *)this + 56);
      if ( *((_QWORD *)this + 10) < 8u )
        LODWORD(v21) = (_DWORD)this + 56;
      else
        v21 = *(const unsigned __int16 **)v20;
      GetWSManSubscribeOptions((int)v63, (int)v21, (int)v19, 905, Value[0], 0);
      v61 = 0;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0x19u, &v61);
      *((_BYTE *)this + 224) = v61;
      v87[0] = 72;
      v22 = v113;
      if ( v114 >= 8 )
        v22 = (_QWORD *)v113[0];
      v87[1] = v22;
      v88 = 0;
      v89 = 0;
      v90 = 0;
      v91 = -1431655765 * (((char *)v63[1] - (char *)v63[0]) >> 3);
      v92 = 0;
      v93 = v63[0];
      v94 = 0;
      v107 = 0;
      v108 = 0;
      memset(v109, 0, sizeof(v109));
      DWORD2(v108) = -1;
      Value[0] = -1;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0xEu, Value);
      HIDWORD(v108) = Value[0];
      Value[0] = 15000;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0xFu, Value);
      *(_DWORD *)v109 = Value[0];
      *(_QWORD *)&v107 = GetDialect(v121, v113);
      if ( v140 )
      {
        v23 = v139;
        if ( v141 >= 8 )
          v23 = (_QWORD *)v139[0];
        *((_QWORD *)&v107 + 1) = v23;
      }
      else
      {
        *((_QWORD *)&v107 + 1) = 0;
      }
      *(_SYSTEMTIME *)&v109[4] = SystemTime;
      Value[0] = 900000;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0x10u, Value);
      *(_DWORD *)&v109[20] = Value[0];
      Value[0] = 900000;
      ReadMetadataProp(*(const struct tag_EcRpcMetadataPropertyList **)a3, 0x10u, Value);
      *((_DWORD *)this + 66) = Value[0];
      v73 = 0;
      v74 = 0;
      v75 = 0;
      LODWORD(v73) = 2;
      if ( v134 )
      {
        v24 = v133;
        if ( v135 >= 8 )
          v24 = (_QWORD *)v133[0];
        *((_QWORD *)&v73 + 1) = v24;
      }
      if ( v131 )
      {
        v25 = v130;
        if ( v132 >= 8 )
          v25 = (_QWORD *)v130[0];
        *(_QWORD *)&v74 = v25;
      }
      if ( v128 )
      {
        v26 = v127;
        if ( v129 >= 8 )
          v26 = (_QWORD *)v127[0];
        *((_QWORD *)&v74 + 1) = v26;
      }
      SecurityDescriptor = 0;
      v70[0] = 0;
      v71 = LocalFree;
      v72 = 0;
      if ( v125 )
      {
        Value[0] = 0;
        v27 = (const WCHAR *)StringSecurityDescriptor;
        if ( v126 >= 8 )
          v27 = StringSecurityDescriptor[0];
        if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v27, 1u, &SecurityDescriptor, Value) )
        {
          LastError = GetLastError();
          if ( !LastError )
            LastError = 1287;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              73,
              &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids,
              LastError);
          }
          wmi::GenericException::GenericException(
            (wmi::GenericException *)v105,
            LastError,
            "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
            2905);
          throw (wmi::GenericException *)v105;
        }
        v75 = SecurityDescriptor;
      }
      v79 = 0;
      v80 = 0;
      if ( v137 )
      {
        v28 = v136;
        if ( v138 >= 8 )
          v28 = (_QWORD *)v136[0];
        v79 = v28;
      }
      if ( v111 )
      {
        v29 = v110;
        if ( v112 >= 8 )
          v29 = (_QWORD *)v110[0];
        v80 = v29;
      }
      v83 = &v73;
      v84 = Subscription::EventsCallback;
      v85 = SourceInitiatedSubscription::BookmarkCallback;
      *((_DWORD *)this + 68) = 0;
      *((_QWORD *)this + 35) = this;
      *((_QWORD *)this + 36) = 0;
      v86 = (char *)this + 272;
      v81 = 60;
      v82 = 5;
      v65 = 0;
      v66 = 0;
      if ( (unsigned int)WSManCreatePushSubscription(
                           *((_QWORD *)this + 26),
                           905,
                           0xFFFFFFFFLL,
                           v87,
                           &v107,
                           &v79,
                           &v65,
                           (char *)this + 216,
                           0) != 1 )
      {
        if ( v66 )
        {
          wmi::MakeGuard<int (*)(WSMAN_OBJECT *),WSMAN_OBJECT *>(v99, WSManCloseObjectHandle);
          if ( DWORD2(v65) )
            DecodeWSManObject(v43, (__int64)this + 232);
          wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v99);
        }
        v44 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          if ( !(unsigned __int8)std::wstring::empty((char *)this + 232) )
            std::wstring::c_str((char *)this + 232);
          Id = (unsigned int)Subscription::GetId(this);
          WPP_SF_SDS(*(_QWORD *)(v46 + 16), DWORD2(v65), v48, Id, SBYTE8(v65), v47);
          v44 = (PVOID *)WPP_GLOBAL_Control;
        }
        v49 = DWORD2(v65);
        if ( !DWORD2(v65) )
          v49 = 1287;
        if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 0x10) != 0 && *((_BYTE *)v44 + 25) >= 2u )
          WPP_SF_D(v44[2], 76, &WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids, v49);
        wmi::GenericException::GenericException(
          (wmi::GenericException *)pExceptionObject,
          v49,
          "admin\\wmi\\events\\forwarding\\collector\\service\\submgr.cpp",
          2975);
        throw (wmi::GenericException *)pExceptionObject;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 74);
      }
      v76[0] = 1;
      *((_BYTE *)this + 96) = 1;
      if ( *((_QWORD *)this + 42) < 8u )
        v30 = (_WORD *)((char *)this + 312);
      else
        v30 = (_WORD *)*((_QWORD *)this + 39);
      *((_QWORD *)this + 41) = 0;
      *v30 = 0;
      wmi::ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>::~ScopeGuardImpl1<void (*)(std::vector<std::vector<unsigned short>> *),std::vector<std::vector<unsigned short>> *>(v70);
      if ( v63[0] )
        operator delete(v63[0]);
      LOBYTE(v31) = 1;
      std::wstring::_Tidy(StringSecurityDescriptor, v31, 0);
      LOBYTE(v32) = 1;
      std::wstring::_Tidy(v127, v32, 0);
      LOBYTE(v33) = 1;
      std::wstring::_Tidy(v130, v33, 0);
      LOBYTE(v34) = 1;
      std::wstring::_Tidy(v133, v34, 0);
      LOBYTE(v35) = 1;
      std::wstring::_Tidy(v136, v35, 0);
      LOBYTE(v36) = 1;
      std::wstring::_Tidy(v110, v36, 0);
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(v139, v37, 0);
      LOBYTE(v38) = 1;
      std::wstring::_Tidy(v121, v38, 0);
      LOBYTE(v39) = 1;
      std::wstring::_Tidy(v113, v39, 0);
      LOBYTE(v40) = 1;
      std::wstring::_Tidy(v143, v40, 0);
      LOBYTE(v41) = 1;
      std::wstring::_Tidy(v115, v41, 0);
      LOBYTE(v42) = 1;
      std::wstring::_Tidy(v118, v42, 0);
      __1__ObjScopeGuardImpl0_VSourceInitiatedSubscription__P81_EAAXX_E_wmi__QEAA_XZ(v76);
      if ( *((_QWORD *)this + 10) >= 8u )
        v20 = *(const unsigned __int16 **)v20;
      WriteSavedRunTimeStatus(v20, 0, 0, &word_180026AD8, 0, 1);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &wmi::Exception `RTTI Type Descriptor', &v98) )
      {
        v53 = (**(__int64 (__fastcall ***)(wmi::Exception *))v98)(v98);
        v54 = v67;
        *((_DWORD *)v67 + 57) = v53;
        if ( !(unsigned __int8)std::wstring::empty((char *)v54 + 232) )
          std::wstring::c_str((char *)v55 + 232);
        v56 = Subscription::GetId(v55);
        WriteSavedRunTimeStatus(v56, 0, v57, v58, 0, 1);
        throw;
      }
    }
  }
  _EventSources::~_EventSources((_EventSources *)v100);
  LeaveCriticalSection(v5);
}

```

## disassembly

```asm
0x180009a10  push    rbx
0x180009a12  push    rsi
0x180009a13  push    rdi
0x180009a14  push    r12
0x180009a16  push    r13
0x180009a18  push    r14
0x180009a1a  push    r15
0x180009a1c  sub     rsp, 560h
0x180009a23  mov     rax, cs:__security_cookie
0x180009a2a  xor     rax, rsp
0x180009a2d  mov     [rsp+598h+var_48], rax
0x180009a35  mov     rsi, r8
0x180009a38  mov     [rsp+598h+SecurityDescriptor], rdx
0x180009a3d  mov     r14, rcx
0x180009a40  mov     [rsp+598h+var_500], rcx
0x180009a48  lea     rbx, [rcx+10h]
0x180009a4c  mov     [rsp+598h+var_3E0], rbx
0x180009a54  mov     rcx, rbx; lpCriticalSection
0x180009a57  call    cs:__imp_EnterCriticalSection
0x180009a5d  nop
0x180009a5e  lea     rcx, [rsp+598h+var_3B8]; this
0x180009a66  call    ??0_EventSources@@QEAA@XZ; _EventSources::_EventSources(void)
0x180009a6b  nop
0x180009a6c  lea     rdx, [rsp+598h+var_3B8]; struct _EventSources *
0x180009a74  mov     rcx, rsi; this
0x180009a77  call    ?GetEventSources@SubscriptionReadData@@QEBAXAEAU_EventSources@@@Z; SubscriptionReadData::GetEventSources(_EventSources &)
0x180009a7c  lea     rcx, [r14+128h]
0x180009a83  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x180009a88  xor     edi, edi
0x180009a8a  mov     r13, [rsp+598h+var_388]
0x180009a92  lea     r15d, [rdi+8]
0x180009a96  test    r13, r13
0x180009a99  jz      loc_180009B45
0x180009a9f  mov     r12, rdi
0x180009aa2  shl     r12, 5
0x180009aa6  add     r12, [rsp+598h+var_380]
0x180009aae  cmp     [r12+18h], r15
0x180009ab3  jb      short loc_180009AB9
0x180009ab5  mov     r12, [r12]
0x180009ab9  mov     r8, rdi
0x180009abc  lea     rdx, [rsp+598h+SystemTime]
0x180009ac4  lea     rcx, [rsp+598h+var_3A0]
0x180009acc  call    ??A?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@1@_K@Z; std::vector<bool>::operator[](unsigned __int64)
0x180009ad1  mov     rcx, [rax+8]
0x180009ad5  mov     r8d, 1
0x180009adb  shl     r8d, cl
0x180009ade  mov     rax, [rax]
0x180009ae1  test    [rax], r8d
0x180009ae4  jnz     short loc_180009B35
0x180009ae6  mov     rdx, r12
0x180009ae9  lea     rcx, [rsp+598h+var_1D8]
0x180009af1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180009af6  nop
0x180009af7  mov     al, cs:byte_18002F7B8
0x180009afd  mov     byte ptr [rsp+598h+var_578], al
0x180009b01  lea     r9, [rsp+598h+var_1D8]
0x180009b09  lea     rdx, [rsp+598h+var_530]
0x180009b0e  lea     rcx, [r14+128h]
0x180009b15  call    ??$_Insert_nohint@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@_N$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Insert_nohint<std::wstring,std::_Nil>(bool,std::wstring &&,std::_Nil)
0x180009b1a  nop
0x180009b1b  xor     r8d, r8d
0x180009b1e  mov     dl, 1
0x180009b20  lea     rcx, [rsp+598h+var_1D8]
0x180009b28  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180009b2d  mov     r13, [rsp+598h+var_388]
0x180009b35  inc     rdi
0x180009b38  cmp     rdi, r13
0x180009b3b  jb      loc_180009A9F
0x180009b41  lea     rbx, [r14+10h]
0x180009b45  mov     rax, [rsp+598h+SecurityDescriptor]
0x180009b4a  xor     edi, edi
0x180009b4c  test    rax, rax
0x180009b4f  jz      short loc_180009B99
0x180009b51  lea     r12, WPP_GLOBAL_Control
0x180009b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b5f  cmp     rcx, r12
0x180009b62  jz      short loc_180009BDA
0x180009b64  test    byte ptr [rcx+1Ch], 10h
0x180009b68  jz      short loc_180009BDA
0x180009b6a  cmp     byte ptr [rcx+19h], 4
0x180009b6e  jb      short loc_180009BDA
0x180009b70  lea     r9, [r14+38h]
0x180009b74  cmp     [r9+18h], r15
0x180009b78  jb      short loc_180009B7D
0x180009b7a  mov     r9, [r9]
0x180009b7d  mov     edx, 45h ; 'E'
0x180009b82  mov     [rsp+598h+var_578], rax
0x180009b87  lea     r8, WPP_311dc52e399f3c6238c54a9ac88e2061_Traceguids
0x180009b8e  mov     rcx, [rcx+10h]
0x180009b92  call    WPP_SF_SS
0x180009b97  jmp     short loc_180009BDA
0x180009b99  cmp     [r14+60h], dil
0x180009b9d  jz      short loc_180009C14
0x180009b9f  lea     r12, WPP_GLOBAL_Control
0x180009ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180009bad  cmp     rcx, r12
0x180009bb0  jz      short loc_180009BDA
0x180009bb2  test    byte ptr [rcx+1Ch], 10h
0x180009bb6  jz      short loc_180009BDA
0x180009bb8  cmp     byte ptr [rcx+19h], 4
0x180009bbc  jb      short loc_180009BDA
0x180009bbe  lea     r9, [r14+38h]
0x180009bc2  cmp     [r9+18h], r15
0x180009bc6  jb      short loc_180009BCB
0x180009bc8  mov     r9, [r9]
0x180009bcb  mov     edx, 46h ; 'F'
0x180009bd0  mov     rcx, [rcx+10h]
0x180009bd4  call    WPP_SF_S
0x180009bd9  nop
0x180009bda  lea     rcx, [rsp+598h+var_3B8]; this
0x180009be2  call    ??1_EventSources@@QEAA@XZ; _EventSources::~_EventSources(void)
0x180009be7  nop
0x180009be8  mov     rcx, rbx; lpCriticalSection
0x180009beb  call    cs:__imp_LeaveCriticalSection
0x180009bf1  mov     rcx, [rsp+598h+var_48]
0x180009bf9  xor     rcx, rsp; StackCookie
0x180009bfc  call    __security_check_cookie
0x180009c01  add     rsp, 560h
0x180009c08  pop     r15
0x180009c0a  pop     r14
0x180009c0c  pop     r13
0x180009c0e  pop     r12
0x180009c10  pop     rdi
0x180009c11  pop     rsi
0x180009c12  pop     rbx
0x180009c13  retn
0x180009c14  mov     [r14+0E4h], edi
0x180009c1b  lea     r13, [r14+0E8h]
0x180009c22  cmp     [r13+18h], r15
0x180009c26  jb      short loc_180009C2E
0x180009c28  mov     rcx, [r13+0]
0x180009c2c  jmp     short loc_180009C31
0x180009c2e  mov     rcx, r13
0x180009c31  mov     [r13+10h], rdi
0x180009c35  mov     [rcx], di
0x180009c38  mov     [rsp+598h+var_4A0], dil
0x180009c40  mov     [rsp+598h+var_498], r14
0x180009c48  lea     rax, ?InternalDeactivate@SourceInitiatedSubscription@@AEAAXXZ; SourceInitiatedSubscription::InternalDeactivate(void)
0x180009c4f  mov     [rsp+598h+var_490], rax
0x180009c57  lea     r12, WPP_GLOBAL_Control
0x180009c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c65  cmp     rcx, r12
0x180009c68  jz      short loc_180009C91
0x180009c6a  test    byte ptr [rcx+1Ch], 10h
0x180009c6e  jz      short loc_180009C91
0x180009c70  cmp     byte ptr [rcx+19h], 4
0x180009c74  jb      short loc_180009C91
0x180009c76  lea     r9, [r14+38h]
0x180009c7a  cmp     [r9+18h], r15
0x180009c7e  jb      short loc_180009C83
0x180009c80  mov     r9, [r9]
0x180009c83  mov     edx, 47h ; 'G'
0x180009c88  mov     rcx, [rcx+10h]
0x180009c8c  call    WPP_SF_S
0x180009c91  mov     ecx, 7
0x180009c96  mov     [rsp+598h+var_1E0], rcx
0x180009c9e  mov     [rsp+598h+var_1E8], rdi
0x180009ca6  mov     word ptr [rsp+598h+var_1F8], di
0x180009cae  mov     [rsp+598h+var_200], rcx
0x180009cb6  mov     [rsp+598h+var_208], rdi
0x180009cbe  mov     word ptr [rsp+598h+var_218], di
0x180009cc6  lea     rdx, [rsp+598h+var_218]
0x180009cce  mov     rcx, rsi
0x180009cd1  call    ?GetLogFile@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetLogFile(std::wstring &)
0x180009cd6  lea     rdx, [rsp+598h+var_1F8]
0x180009cde  mov     rcx, rsi
0x180009ce1  call    ?GetPublisherName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetPublisherName(std::wstring &)
0x180009ce6  mov     rcx, [rsp+598h+var_1E8]
0x180009cee  test    rcx, rcx
0x180009cf1  jnz     short loc_180009D19
0x180009cf3  cmp     [rsp+598h+var_208], rdi
0x180009cfb  jnz     short loc_180009D19
0x180009cfd  lea     rdx, aForwardedevent; "ForwardedEvents"
0x180009d04  lea     rcx, [rsp+598h+var_218]
0x180009d0c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180009d11  mov     rcx, [rsp+598h+var_1E8]
0x180009d19  mov     rax, [r14+68h]
0x180009d1d  mov     r10, [rax+80h]
0x180009d24  mov     rax, [r10]
0x180009d27  test    rcx, rcx
0x180009d2a  jnz     short loc_180009D31
0x180009d2c  mov     r9, rdi
0x180009d2f  jmp     short loc_180009D4A
0x180009d31  lea     r9, [rsp+598h+var_1F8]
0x180009d39  cmp     [rsp+598h+var_1E0], r15
0x180009d41  cmovnb  r9, [rsp+598h+var_1F8]
0x180009d4a  cmp     [rsp+598h+var_208], rdi
0x180009d52  jnz     short loc_180009D59
0x180009d54  mov     r8, rdi
0x180009d57  jmp     short loc_180009D72
0x180009d59  lea     r8, [rsp+598h+var_218]
0x180009d61  cmp     [rsp+598h+var_200], r15
0x180009d69  cmovnb  r8, [rsp+598h+var_218]
0x180009d72  lea     rdx, [rsp+598h+var_530]
0x180009d77  mov     rcx, r10
0x180009d7a  mov     rax, [rax+8]
0x180009d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d83  mov     qword ptr [rsp+598h+Value], rax
0x180009d88  lea     rcx, [r14+70h]
0x180009d8c  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180009d91  mov     rax, qword ptr [rsp+598h+Value]
0x180009d96  mov     rcx, [rax]
0x180009d99  mov     [r14+70h], rcx
0x180009d9d  mov     qword ptr [rax], 0
0x180009da4  lea     rcx, [rsp+598h+var_530]
0x180009da9  call    ?Release@?$AutoRef@VAbstractEventProcessor@@@wmi@@QEAAXXZ; wmi::AutoRef<AbstractEventProcessor>::Release(void)
0x180009dae  mov     [rsp+598h+var_D0], 7
0x180009dba  mov     [rsp+598h+var_D8], 0
0x180009dc6  xor     eax, eax
0x180009dc8  mov     [rsp+598h+var_E8], ax
0x180009dd0  lea     rdx, [rsp+598h+var_E8]
0x180009dd8  mov     rcx, rsi
0x180009ddb  call    ?GetLocale@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetLocale(std::wstring &)
0x180009de0  xorps   xmm0, xmm0
0x180009de3  xor     eax, eax
0x180009de5  movups  [rsp+598h+var_3F8], xmm0
0x180009ded  mov     [rsp+598h+var_3E8], rax
0x180009df5  lea     rdx, [rsp+598h+var_3F8]
0x180009dfd  lea     rcx, [rsp+598h+var_E8]
0x180009e05  call    ?InitWSManConnectionOptions@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_WSMAN_CONNECTION_OPTIONS@@@Z; InitWSManConnectionOptions(std::wstring &,_WSMAN_CONNECTION_OPTIONS &)
0x180009e0a  xorps   xmm0, xmm0
0x180009e0d  xor     eax, eax
0x180009e0f  movups  [rsp+598h+var_4F8], xmm0
0x180009e17  mov     [rsp+598h+var_4E8], rax
0x180009e1f  lea     rdi, [r14+0D0h]
0x180009e26  mov     [rsp+598h+var_560], rax
0x180009e2b  mov     [rsp+598h+var_568], rdi
0x180009e30  lea     rax, [rsp+598h+var_4F8]
0x180009e38  mov     qword ptr [rsp+598h+var_570], rax
0x180009e3d  lea     rax, [rsp+598h+var_3F8]
0x180009e45  mov     [rsp+598h+var_578], rax
0x180009e4a  xor     r9d, r9d
0x180009e4d  xor     r8d, r8d
0x180009e50  xor     edx, edx
0x180009e52  xor     ecx, ecx
0x180009e54  call    cs:__imp_WSManCreateSessionInternal
0x180009e5a  test    eax, eax
0x180009e5c  jz      loc_18000A807
0x180009e62  cmp     [rsp+598h+var_D8], 0
0x180009e6b  jz      short loc_180009E7D
0x180009e6d  lea     rdx, [rsp+598h+var_E8]
0x180009e75  mov     rcx, [rdi]; session
0x180009e78  call    ?SetWSManSessionOptionsLocales@@YAXPEAUWSMAN_SESSION@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SetWSManSessionOptionsLocales(WSMAN_SESSION *,std::wstring &)
0x180009e7d  mov     [rsp+598h+var_220], 7
0x180009e89  xor     edi, edi
0x180009e8b  mov     [rsp+598h+var_228], rdi
0x180009e93  mov     word ptr [rsp+598h+var_238], di
0x180009e9b  lea     rdx, [rsp+598h+var_238]
0x180009ea3  mov     rcx, rsi
0x180009ea6  call    ?GetURI@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetURI(std::wstring &)
0x180009eab  mov     [rsp+598h+var_1C0], 7
0x180009eb7  mov     [rsp+598h+var_1C8], rdi
0x180009ebf  mov     [rsp+598h+var_1D8], di
0x180009ec7  lea     rdx, [rsp+598h+var_1D8]
0x180009ecf  mov     rcx, rsi
0x180009ed2  call    ?GetDialect@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetDialect(std::wstring &)
0x180009ed7  mov     [rsp+598h+var_100], 7
0x180009ee3  mov     [rsp+598h+var_108], rdi
0x180009eeb  mov     word ptr [rsp+598h+var_118], di
0x180009ef3  lea     rdx, [rsp+598h+var_118]
0x180009efb  mov     rcx, rsi
0x180009efe  call    ?GetQuery@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetQuery(std::wstring &)
0x180009f03  lea     rdi, [r14+58h]
0x180009f07  mov     qword ptr [rdi], 0
0x180009f0e  mov     r8, rdi; struct _FILETIME *
0x180009f11  mov     rcx, [rsi]; struct tag_EcRpcMetadataPropertyList *
0x180009f14  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAU_FILETIME@@@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,_FILETIME &)
0x180009f19  xorps   xmm0, xmm0
0x180009f1c  movups  xmmword ptr [rsp+598h+SystemTime.wYear], xmm0
0x180009f24  lea     rdx, [rsp+598h+SystemTime]; lpSystemTime
0x180009f2c  mov     rcx, rdi; lpFileTime
0x180009f2f  call    cs:__imp_FileTimeToSystemTime
0x180009f35  mov     [rsp+598h+var_240], 7
0x180009f41  xor     edi, edi
0x180009f43  mov     [rsp+598h+var_248], rdi
0x180009f4b  mov     word ptr [rsp+598h+var_258], di
0x180009f53  lea     rdx, [rsp+598h+var_258]
0x180009f5b  mov     rcx, rsi
0x180009f5e  call    ?GetTransportName@SubscriptionReadData@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SubscriptionReadData::GetTransportName(std::wstring &)
0x180009f63  cmp     [rsp+598h+var_248], rdi
0x180009f6b  jz      short loc_180009FDA
0x180009f6d  mov     [rsp+598h+Value], edi
0x180009f71  lea     r8, [rsp+598h+Value]; unsigned int *
0x180009f76  lea     edx, [rdi+0Ch]; unsigned int
0x180009f79  mov     rcx, [rsi]; struct tag_EcRpcMetadataPropertyList *
0x180009f7c  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180009f81  cmp     [rsp+598h+Value], edi
0x180009f85  jz      short loc_180009FDA
0x180009f87  mov     [rsp+598h+Value], edi
0x180009f8b  lea     r8, [rsp+598h+Value]; unsigned int *
0x180009f90  lea     edx, [rdi+0Ch]; unsigned int
0x180009f93  mov     rcx, [rsi]; struct tag_EcRpcMetadataPropertyList *
0x180009f96  call    ?ReadMetadataProp@@YA_NAEBUtag_EcRpcMetadataPropertyList@@KAEAK@Z; ReadMetadataProp(tag_EcRpcMetadataPropertyList const &,ulong,ulong &)
0x180009f9b  lea     r8d, [rdi+0Ah]; Radix
0x180009f9f  lea     rdx, [rsp+598h+Buffer]; Buffer
0x180009fa7  mov     ecx, [rsp+598h+Value]; Value
0x180009fab  call    cs:__imp__ultow
0x180009fb1  lea     rdx, asc_1800275D8; ":"
0x180009fb8  lea     rcx, [rsp+598h+var_258]
0x180009fc0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
  ... truncated ...
```
