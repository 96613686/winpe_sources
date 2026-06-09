# TimeRestrictions::Private::SendScreenTimeExceptionRequest(DateTime,DateTime)

- ea: `0x14009415c`
- end: `0x140095165`
- name: `?SendScreenTimeExceptionRequest@Private@TimeRestrictions@@YAXVDateTime@@0@Z`
- size: `4105`
- prototype: ``
- caller_count: `1`
- callee_count: `48`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400957d0`

## callees

- `0x140005530`
- `0x140005554`
- `0x1400057f0`
- `0x140006314`
- `0x140006338`
- `0x140008904`
- `0x140009858`
- `0x14000b588`
- `0x14000b744`
- `0x14000ccac`
- `0x140010e18`
- `0x14001c478`
- `0x14001f654`
- `0x1400231d4`
- `0x14002a754`
- `0x14002c2e4`
- `0x14002f3a0`
- `0x14002fe20`
- `0x140035800`
- `0x140047e78`
- `0x14005bc7c`
- `0x140060764`
- `0x140060aac`
- `0x140060f58`
- `0x140069070`
- `0x140069748`
- `0x14006d0c4`
- `0x14006e1f0`
- `0x1400740c4`
- `0x140074158`
- `0x140076328`
- `0x14007a800`
- `0x14007b98c`
- `0x14007bb94`
- `0x14007c2a0`
- `0x14007ed8c`
- `0x14007ef58`
- `0x14007f210`
- `0x14007f478`
- `0x140093190`
- `0x1400934fc`
- `0x14009380c`
- `0x140093adc`
- `0x14009415c`
- `0x140095540`
- `0x1400959b4`
- `0x14009b894`
- `0x1400a8010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140094d9c`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x140094d9c`

## string_xrefs

- `0x1400947e3`: `FamilyServiceAuthTarget`
- `0x14009421b`: `EnforcementFrontDoorServiceServer`
- `0x1400947c6`: `family.microsoft.com`
- `0x1400941fe`: `clientfd.family.microsoft.com`
- `0x140094c20`: `Sending extension request to: `

## pseudocode

```c
// Hidden C++ exception states: #wind=46
__int64 __fastcall TimeRestrictions::Private::SendScreenTimeExceptionRequest(Private *a1, Private *a2)
{
  TraceLoggingCorrelationVector *v4; // rax
  volatile signed __int64 *v5; // r12
  __int64 v6; // r8
  _QWORD *v7; // rax
  void (__fastcall ***v8)(_QWORD, __int64); // rcx
  char *v9; // rdi
  __int64 (__fastcall *v10)(char *, __int64 *, __int128 *); // rbx
  __int64 v11; // rax
  __int64 v12; // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  char *v14; // rdi
  __int64 (__fastcall *v15)(char *, __int64 *, __int128 *); // rbx
  _QWORD *v16; // rax
  void (__fastcall ***v17)(_QWORD, __int64); // rcx
  Private::Format *v18; // rbx
  Private::Format *v19; // rbx
  Private::Format *v20; // rbx
  __int128 *v21; // rdx
  const unsigned __int16 *p_Src; // rdx
  __int64 v23; // rdx
  int v24; // ecx
  __int128 *v25; // r9
  __int128 *DeviceTicket; // rax
  __int64 *v27; // rbx
  int v28; // r8d
  char **v29; // rax
  char **v30; // r9
  __int64 **v31; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  char *v34; // rdi
  __int64 (__fastcall *v35)(char *, _QWORD *, __int128 *); // rbx
  __int64 v36; // rax
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64, __int64); // rbx
  __int64 v39; // rdx
  void (__fastcall ***v40)(_QWORD, __int64); // rcx
  char *v41; // rdi
  __int64 (__fastcall *v42)(char *, _QWORD *, __int128 *); // rbx
  __int64 v43; // rax
  __int64 v44; // rdi
  void (__fastcall *v45)(__int64, __int64); // rbx
  __int64 v46; // rdx
  void (__fastcall ***v47)(_QWORD, __int64); // rcx
  __int64 v48; // rdx
  __int64 v49; // r8
  int *v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  char **v53; // rax
  __int64 v54; // rax
  __int64 v55; // rdx
  _QWORD *v56; // rdx
  Private::Format *v57; // rcx
  Private::Format *v58; // rax
  __int64 v59; // rax
  char *v60; // rcx
  char *v61; // rcx
  volatile signed __int32 *v62; // rbx
  unsigned int v64; // eax
  unsigned int v65; // r8d
  unsigned int v66; // eax
  unsigned int v67; // r8d
  Private::Format *v68; // rax
  __int64 v69; // rax
  int v70; // [rsp+20h] [rbp-4C8h]
  _QWORD v71[2]; // [rsp+50h] [rbp-498h] BYREF
  __int64 v72; // [rsp+60h] [rbp-488h] BYREF
  char *v73; // [rsp+68h] [rbp-480h] BYREF
  char *v74; // [rsp+70h] [rbp-478h] BYREF
  __int64 v75; // [rsp+78h] [rbp-470h] BYREF
  volatile signed __int64 *v76; // [rsp+80h] [rbp-468h]
  Private *v77; // [rsp+88h] [rbp-460h]
  Private *v78; // [rsp+90h] [rbp-458h]
  _QWORD v79[3]; // [rsp+98h] [rbp-450h] BYREF
  __int64 v80; // [rsp+B0h] [rbp-438h] BYREF
  Private *v81; // [rsp+C0h] [rbp-428h]
  _QWORD v82[7]; // [rsp+D0h] [rbp-418h] BYREF
  _QWORD *v83; // [rsp+108h] [rbp-3E0h]
  _QWORD v84[3]; // [rsp+110h] [rbp-3D8h] BYREF
  volatile signed __int32 *v85; // [rsp+128h] [rbp-3C0h]
  void **v86; // [rsp+140h] [rbp-3A8h]
  _BYTE pExceptionObject[40]; // [rsp+148h] [rbp-3A0h] BYREF
  _BYTE v88[40]; // [rsp+170h] [rbp-378h] BYREF
  _BYTE v89[40]; // [rsp+198h] [rbp-350h] BYREF
  _BYTE v90[160]; // [rsp+1C0h] [rbp-328h] BYREF
  __int128 Src; // [rsp+260h] [rbp-288h] BYREF
  __int64 v92; // [rsp+270h] [rbp-278h]
  unsigned __int64 v93; // [rsp+278h] [rbp-270h]
  __int128 v94; // [rsp+280h] [rbp-268h] BYREF
  __int64 v95; // [rsp+290h] [rbp-258h]
  __int64 v96; // [rsp+298h] [rbp-250h]
  __int128 v97; // [rsp+2A0h] [rbp-248h] BYREF
  __int128 v98; // [rsp+2B0h] [rbp-238h]
  __int128 v99[2]; // [rsp+2C8h] [rbp-220h] BYREF
  __int128 v100; // [rsp+2F0h] [rbp-1F8h] BYREF
  __int64 v101; // [rsp+300h] [rbp-1E8h]
  unsigned __int64 v102; // [rsp+308h] [rbp-1E0h]
  char *v103; // [rsp+310h] [rbp-1D8h] BYREF
  char *v104[3]; // [rsp+318h] [rbp-1D0h] BYREF
  char **v105; // [rsp+330h] [rbp-1B8h] BYREF
  _BYTE v106[16]; // [rsp+338h] [rbp-1B0h] BYREF
  unsigned __int64 v107; // [rsp+348h] [rbp-1A0h]
  int v108[2]; // [rsp+350h] [rbp-198h] BYREF
  __int64 v109; // [rsp+360h] [rbp-188h]
  unsigned __int64 v110; // [rsp+368h] [rbp-180h]
  __int128 v111; // [rsp+370h] [rbp-178h] BYREF
  __int64 v112; // [rsp+380h] [rbp-168h]
  __int64 v113; // [rsp+388h] [rbp-160h]
  char *v114[2]; // [rsp+390h] [rbp-158h] BYREF
  __int64 v115; // [rsp+3A0h] [rbp-148h]
  unsigned __int64 v116; // [rsp+3A8h] [rbp-140h]
  __int128 v117; // [rsp+3B0h] [rbp-138h] BYREF
  __int64 v118; // [rsp+3C0h] [rbp-128h]
  __int64 v119; // [rsp+3C8h] [rbp-120h]
  _BYTE v120[16]; // [rsp+3D0h] [rbp-118h] BYREF
  _DWORD *v121; // [rsp+3E0h] [rbp-108h]
  char **v122; // [rsp+410h] [rbp-D8h]
  char v123[144]; // [rsp+420h] [rbp-C8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+0h]

  v78 = a2;
  v77 = a1;
  v81 = a1;
  v71[0] = a2;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&v117,
    L"/windows/wpccore/api/v1.0/users/me/screentime/exceptionRequest",
    0x3Eu);
  v94 = 0;
  v95 = 0;
  v96 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v94, L"clientfd.family.microsoft.com", 0x1Du);
  RegistryHelper::ReadRegOrDefault(v114, L"EnforcementFrontDoorServiceServer", &v94);
  std::wstring::~wstring((char **)&v94);
  v4 = (TraceLoggingCorrelationVector *)operator new(0x90u);
  v5 = (volatile signed __int64 *)TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(v4);
  v76 = v5;
  v79[2] = v5;
  memset_0(v123, 0, 0x81u);
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v5,
    _InterlockedExchangeAdd64(v5 + 17, 0),
    v123);
  v100 = 0;
  v101 = 0;
  v102 = 0;
  v6 = -1;
  do
    ++v6;
  while ( v123[v6] );
  std::string::_Construct<1,char const *>(&v100, v123);
  RegistryT<256>::RegistryT<256>(
    v84,
    -2147483647,
    (int)L"Software\\Microsoft\\Windows\\CurrentVersion\\Parental Controls");
  v94 = 0;
  v95 = 0;
  v96 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v94, L"Overrides", 9u);
  v7 = (_QWORD *)RegistryT<256>::Get(v84, &v72, &v94);
  (*(void (__fastcall **)(_QWORD, char **))(*(_QWORD *)*v7 + 48LL))(*v7, &v74);
  if ( v72 )
  {
    v8 = (void (__fastcall ***)(_QWORD, __int64))(v72 + *(int *)(*(_QWORD *)(v72 + 8) + 4LL) + 8LL);
    (**v8)(v8, 1);
  }
  std::wstring::~wstring((char **)&v94);
  v9 = v74;
  v10 = **(__int64 (__fastcall ***)(char *, __int64 *, __int128 *))v74;
  v94 = 0;
  v95 = 0;
  v96 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v94, L"FakeSendRequestError", 0x14u);
  v11 = v10(v9, &v80, &v94);
  v12 = *(_QWORD *)v11 + 8LL + *(int *)(*(_QWORD *)(*(_QWORD *)v11 + 8LL) + 4LL);
  (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 16LL))(v12, &v97);
  if ( v80 )
  {
    v13 = (void (__fastcall ***)(_QWORD, __int64))(v80 + *(int *)(*(_QWORD *)(v80 + 8) + 4LL) + 8LL);
    (**v13)(v13, 1);
  }
  std::wstring::~wstring((char **)&v94);
  if ( *((_QWORD *)&v97 + 1) && **((_DWORD **)&v97 + 1) )
  {
    v14 = v74;
    v15 = **(__int64 (__fastcall ***)(char *, __int64 *, __int128 *))v74;
    Src = 0;
    v92 = 0;
    v93 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"FakeSendRequestError", 0x14u);
    v16 = (_QWORD *)v15(v14, &v75, &Src);
    (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v16 + 8LL))(*v16, 0);
    if ( v75 )
    {
      v17 = (void (__fastcall ***)(_QWORD, __int64))(v75 + *(int *)(*(_QWORD *)(v75 + 8) + 4LL) + 8LL);
      (**v17)(v17, 1);
    }
    std::wstring::~wstring((char **)&Src);
    if ( !*((_QWORD *)&v97 + 1) )
    {
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
      throw (ErrorCodeException *)pExceptionObject;
    }
    switch ( **((_DWORD **)&v97 + 1) )
    {
      case 1:
        MSATokenBroker::GetSimulatedTicketFailure(v90, 1);
        throw (MSATokenBroker::TicketFailureException *)v90;
      case 2:
        MSATokenBroker::GetSimulatedTicketFailure(v89, 2);
        throw (MSATokenBroker::TicketFailureException *)v89;
      case 3:
        MSATokenBroker::GetSimulatedTicketFailure(v88, 3);
        throw (MSATokenBroker::TicketFailureException *)v88;
      case 4:
        v64 = wil::verify_hresult<long>(2147954407LL);
        wil::details::in1diag3::Throw_Hr(retaddr, (void *)0xB3, v65, (const char *)v64, v70);
    }
  }
  Src = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    (char **)&Src,
    L"RequestException - LockTime:{0}, RequestedTime:{1}, cv:{2}",
    0x3Au);
  v18 = (Private::Format *)StringAlgo::FormatString(v99, &Src);
  DateTime::ToDebugString(a1, &v97, 1);
  v19 = (Private::Format *)Private::Format::operator%<std::wstring>(v18);
  DateTime::ToDebugString(a2, &v94, 1);
  v20 = (Private::Format *)Private::Format::operator%<std::wstring>(v19);
  v21 = &v100;
  if ( v102 > 0xF )
    v21 = (__int128 *)v100;
  StringAlgo::ToUnicode(&Src, v21);
  p_Src = (const unsigned __int16 *)&Src;
  if ( v93 > 7 )
    p_Src = (const unsigned __int16 *)Src;
  Private::Format::Replace(v20, p_Src);
  std::wstring::~wstring((char **)&Src);
  wpc::UI::Logging::MonitorUILogger::LogMessage(v20);
  std::wstring::~wstring((char **)&v94);
  std::wstring::~wstring((char **)&v97);
  std::wstring::~wstring((char **)v99);
  v23 = wpc::MicrosoftAccount::AuthScope::CreateForEnforcementFrontDoorService(&v94);
  MSATokenBroker::GetCurrentUsersTicket(v120, v23);
  std::wstring::~wstring((char **)&v94);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    if ( v122 )
    {
      stdext::call__wpc::MicrosoftAccount::UserTicketResult::Serialize_::_2_::_lambda_1__const__std::tuple_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_______(&Src);
    }
    else
    {
      if ( !v121 )
        Choice<std::tuple<std::wstring>,std::tuple<enum wpc::MicrosoftAccount::TicketFailure,long,unsigned long>>::_Match<2,Optional<wpc::MicrosoftAccount::UserTicketResult>>();
      wpc::MicrosoftAccount::UserTicketResult::Serialize_::_2_::_lambda_2_::operator()(
        v24,
        (unsigned int)&Src,
        v121[2],
        v121[1],
        *v121);
    }
    v25 = &Src;
    if ( v93 > 7 )
      v25 = (__int128 *)Src;
    WPP_SF_S(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 17, &WPP_a962fa5ad48435823699fbe85b3baeb7_Traceguids, v25);
    std::wstring::~wstring((char **)&Src);
  }
  v111 = 0;
  v112 = 0;
  v113 = 7;
  LOWORD(v111) = 0;
  if ( !v122 )
    Choice_std::tuple_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::tuple_enum_wpc::MicrosoftAccount::TicketFailure_long_unsigned_long___::_Match_1_void__lambda_1ae2b98fdf03ea2f9cad865cc7ceac59___(v120);
  std::wstring::operator=(&v111, v122);
  v94 = 0;
  v95 = 0;
  v96 = 7;
  LOWORD(v94) = 0;
  try
  {
    Src = 0;
    v92 = 0;
    v93 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"family.microsoft.com", 0x14u);
    RegistryHelper::ReadRegOrDefault(&v97, L"FamilyServiceAuthTarget", &Src);
    std::wstring::~wstring((char **)&Src);
    DeviceTicket = MSATokenBroker::GetDeviceTicket(v99, &v97);
    std::wstring::operator=(&v94, DeviceTicket);
    std::wstring::~wstring((char **)v99);
    std::wstring::~wstring((char **)&v97);
  }
  catch ( ... )
  {
    LODWORD(v72) = ErrorCodeFromCaughtException();
    Src = 0;
    v92 = 0;
    v93 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"GetDeviceTicket failed with {0}", 0x1Fu);
    v68 = (Private::Format *)StringAlgo::FormatString(v99, &Src);
    v69 = Private::Format::operator%<long>(v68);
    wpc::UI::Logging::MonitorUILogger::LogMessage(v69);
    std::wstring::~wstring((char **)v99);
    v5 = v76;
    v77 = v81;
    v78 = (Private *)v71[0];
  }
  TimeRestrictions::Private::CreateHeaders(v79, &v111, &v94, &v100);
  v27 = *(__int64 **)v79[0];
  while ( !*((_BYTE *)v27 + 25) )
  {
    std::wstring::wstring((__int64)&v103, (__int64)(v27 + 4));
    std::wstring::wstring((__int64)&v105, (__int64)(v27 + 8));
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      v29 = (char **)&v105;
      if ( v107 > 7 )
        v29 = v105;
      v30 = &v103;
      if ( v104[2] > (char *)7 )
        LODWORD(v30) = (_DWORD)v103;
      WPP_SF_SS(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v28, (_DWORD)v30, (__int64)v29);
    }
    std::wstring::~wstring((char **)&v105);
    std::wstring::~wstring(&v103);
    v31 = (__int64 **)v27[2];
    if ( *((_BYTE *)v31 + 25) )
    {
      for ( i = (__int64 *)v27[1]; !*((_BYTE *)i + 25) && v27 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v27 = i;
      v27 = i;
    }
    else
    {
      v27 = (__int64 *)v27[2];
      for ( j = *v31; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        v27 = j;
    }
  }
  JsonStorage::Create(&v73);
  v34 = v73;
  v35 = **(__int64 (__fastcall ***)(char *, _QWORD *, __int128 *))v73;
  Src = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"lockTime", 8u);
  v36 = v35(v34, v71, &Src);
  v37 = *(_QWORD *)v36;
  v38 = *(void (__fastcall **)(__int64, __int64))(**(_QWORD **)v36 + 32LL);
  v39 = DateTime::ToDateTimeOffsetString(v77);
  v38(v37, v39);
  std::wstring::~wstring((char **)v99);
  if ( v71[0] )
  {
    v40 = (void (__fastcall ***)(_QWORD, __int64))(v71[0] + *(int *)(*(_QWORD *)(v71[0] + 8LL) + 4LL) + 8LL);
    (**v40)(v40, 1);
  }
  std::wstring::~wstring((char **)&Src);
  v41 = v73;
  v42 = **(__int64 (__fastcall ***)(char *, _QWORD *, __int128 *))v73;
  Src = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"requestedTime", 0xDu);
  v43 = v42(v41, v71, &Src);
  v44 = *(_QWORD *)v43;
  v45 = *(void (__fastcall **)(__int64, __int64))(**(_QWORD **)v43 + 32LL);
  v46 = DateTime::ToDateTimeOffsetString(v78);
  v45(v44, v46);
  std::wstring::~wstring((char **)v99);
  if ( v71[0] )
  {
    v47 = (void (__fastcall ***)(_QWORD, __int64))(v71[0] + *(int *)(*(_QWORD *)(v71[0] + 8LL) + 4LL) + 8LL);
    (**v47)(v47, 1);
  }
  std::wstring::~wstring((char **)&Src);
  (*(void (__fastcall **)(char *, int *))(*(_QWORD *)v73 + 24LL))(v73, v108);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v109) < 0xE )
    std::_Xlen_string();
  v50 = v108;
  if ( v110 > 7 )
    v50 = *(int **)v108;
  std::wstring::wstring(&Src, v48, v49, L"Request body: ", 14, v50, v109);
  wpc::UI::Logging::MonitorUILogger::LogMessage(&Src);
  std::wstring::~wstring((char **)&Src);
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v115) < 0x1E )
    std::_Xlen_string();
  v53 = v114;
  if ( v116 > 7 )
    v53 = (char **)v114[0];
  std::wstring::wstring(&Src, v51, v52, L"Sending extension request to: ", 30, v53, v115);
  v54 = std::wstring::append(&Src);
  v97 = 0;
  v98 = 0u;
  v97 = *(_OWORD *)v54;
  v98 = *(_OWORD *)(v54 + 16);
  *(_QWORD *)(v54 + 16) = 0;
  *(_QWORD *)(v54 + 24) = 7;
  *(_WORD *)v54 = 0;
  wpc::UI::Logging::MonitorUILogger::LogMessage(&v97);
  std::wstring::~wstring((char **)&v97);
  std::wstring::~wstring((char **)&Src);
  v82[0] = &std::_Func_impl_no_alloc<_lambda_000970f6e2f70b9137488875e0c2887b_,void,unsigned long,std::map<std::wstring,std::wstring> const &>::`vftable';
  v83 = v82;
  v71[0] = v82;
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(&v97, v79);
  Src = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"POST", 4u);
  SendRequest(&v103, v55, v114, &v117);
  std::wstring::~wstring((char **)&Src);
  LODWORD(v72) = (_DWORD)v103;
  if ( !v83 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(_QWORD *, __int64 *, _BYTE *))(*v83 + 16LL))(v83, &v72, v106);
  LODWORD(v99[0]) = (_DWORD)v103;
  std::wstring::wstring((__int64)v99 + 8, (__int64)v104);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v106);
  std::wstring::~wstring(v104);
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v97);
  if ( v83 )
  {
    v56 = v82;
    LOBYTE(v56) = v83 != v82;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v83 + 32LL))(v83, v56);
    v83 = 0;
  }
  Src = 0;
  v92 = 0;
  v93 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&Src, L"Request response: {0}, {1}", 0x1Au);
  v57 = (Private::Format *)StringAlgo::FormatString(&v97, &Src);
  v58 = (Private::Format *)Private::Format::operator%<unsigned long>(v57);
  v59 = Private::Format::operator%<std::wstring>(v58);
  wpc::UI::Logging::MonitorUILogger::LogMessage(v59);
  std::wstring::~wstring((char **)&v97);
  if ( LODWORD(v99[0]) != 200
    && LODWORD(v99[0]) != 201
    && LODWORD(v99[0]) != 202
    && LODWORD(v99[0]) != 203
    && LODWORD(v99[0]) != 204
    && LODWORD(v99[0]) != 304 )
  {
    v66 = wil::verify_hresult<long>(v99[0] & 0x3FF | 0x80F81C00);
    wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x102, v67, (const char *)v66, (int)v108);
  }
  std::wstring::~wstring((char **)v99 + 1);
  std::wstring::~wstring((char **)v108);
  if ( v73 )
  {
    v60 = &v73[*(int *)(*((_QWORD *)v73 + 1) + 4LL) + 8];
    (**(void (__fastcall ***)(char *, __int64))v60)(v60, 1);
  }
  std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v79);
  std::wstring::~wstring((char **)&v94);
  std::wstring::~wstring((char **)&v111);
  if ( v122 )
  {
    std::wstring::~wstring(v122);
    v122 = 0;
  }
  if ( v121 )
    v121 = 0;
  if ( v74 )
  {
    v61 = &v74[*(int *)(*((_QWORD *)v74 + 1) + 4LL) + 8];
    (**(void (__fastcall ***)(char *, __int64))v61)(v61, 1);
  }
  v62 = v85;
  if ( v85 )
  {
    if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
      if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
    }
  }
  v86 = &IConstHierarchicalStorage::`vftable';
  std::string::~string((char **)&v100);
  if ( v5 )
    operator delete((void *)v5, 0x90u);
  std::wstring::~wstring(v114);
  return std::wstring::~wstring((char **)&v117);
}

```

## disassembly

```asm
0x14009415c  mov     r11, rsp
0x14009415f  mov     [r11+18h], rbx
0x140094163  mov     [r11+20h], rsi
0x140094167  push    rdi
0x140094168  push    r12
0x14009416a  push    r13
0x14009416c  push    r14
0x14009416e  push    r15
0x140094170  sub     rsp, 4C0h
0x140094177  mov     rax, cs:__security_cookie
0x14009417e  xor     rax, rsp
0x140094181  mov     [rsp+4E8h+var_38], rax
0x140094189  mov     r13, rdx
0x14009418c  mov     [rsp+4E8h+var_458], rdx
0x140094194  mov     r15, rcx
0x140094197  mov     [rsp+4E8h+var_460], rcx
0x14009419f  mov     [rsp+4E8h+var_428], rcx
0x1400941a7  mov     [rsp+4E8h+var_498], rdx
0x1400941ac  xor     esi, esi
0x1400941ae  xorps   xmm0, xmm0
0x1400941b1  movups  [rsp+4E8h+var_138], xmm0
0x1400941b9  mov     [r11-128h], rsi
0x1400941c0  mov     [r11-120h], rsi
0x1400941c7  lea     r8d, [rsi+3Eh]
0x1400941cb  lea     rdx, aWindowsWpccore; "/windows/wpccore/api/v1.0/users/me/scre"...
0x1400941d2  lea     rcx, [r11-138h]
0x1400941d9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400941de  nop
0x1400941df  xorps   xmm0, xmm0
0x1400941e2  movups  [rsp+4E8h+var_268], xmm0
0x1400941ea  mov     [rsp+4E8h+var_258], rsi
0x1400941f2  mov     [rsp+4E8h+var_250], rsi
0x1400941fa  lea     r8d, [rsi+1Dh]
0x1400941fe  lea     rdx, aClientfdFamily; "clientfd.family.microsoft.com"
0x140094205  lea     rcx, [rsp+4E8h+var_268]
0x14009420d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140094212  nop
0x140094213  lea     r8, [rsp+4E8h+var_268]
0x14009421b  lea     rdx, aEnforcementfro; "EnforcementFrontDoorServiceServer"
0x140094222  lea     rcx, [rsp+4E8h+var_158]
0x14009422a  call    ?ReadRegOrDefault@RegistryHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBV23@@Z; RegistryHelper::ReadRegOrDefault(ushort const *,std::wstring const &)
0x14009422f  nop
0x140094230  lea     rcx, [rsp+4E8h+var_268]
0x140094238  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009423d  nop
0x14009423e  mov     ecx, 90h; Size
0x140094243  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140094248  mov     [rsp+4E8h+var_468], rax
0x140094250  mov     rcx, rax; this
0x140094253  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x140094258  mov     r12, rax
0x14009425b  mov     [rsp+4E8h+var_468], rax
0x140094263  mov     [rsp+4E8h+var_440], rax
0x14009426b  xor     edx, edx; Val
0x14009426d  mov     r8d, 81h; Size
0x140094273  lea     rcx, [rsp+4E8h+var_C8]; void *
0x14009427b  call    memset_0
0x140094280  mov     edx, esi
0x140094282  lock xadd [r12+88h], rdx; unsigned __int64
0x14009428c  lea     r8, [rsp+4E8h+var_C8]; char *
0x140094294  mov     rcx, r12; this
0x140094297  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x14009429c  xorps   xmm0, xmm0
0x14009429f  movups  [rsp+4E8h+var_1F8], xmm0
0x1400942a7  mov     [rsp+4E8h+var_1E8], rsi
0x1400942af  mov     [rsp+4E8h+var_1E0], rsi
0x1400942b7  lea     rax, [rsp+4E8h+var_C8]
0x1400942bf  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400942c3  inc     r8
0x1400942c6  cmp     [rax+r8], sil
0x1400942ca  jnz     short loc_1400942C3
0x1400942cc  lea     rdx, [rsp+4E8h+var_C8]
0x1400942d4  lea     rcx, [rsp+4E8h+var_1F8]
0x1400942dc  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1400942e1  nop
0x1400942e2  lea     r8, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400942e9  mov     rdx, 0FFFFFFFF80000001h
0x1400942f0  lea     rcx, [rsp+4E8h+var_3D8]
0x1400942f8  call    ??0?$RegistryT@$0BAA@@@QEAA@PEAUHKEY__@@PEBG_NPEAU_SECURITY_ATTRIBUTES@@@Z; RegistryT<256>::RegistryT<256>(HKEY__ *,ushort const *,bool,_SECURITY_ATTRIBUTES *)
0x1400942fd  nop
0x1400942fe  xorps   xmm0, xmm0
0x140094301  movups  [rsp+4E8h+var_268], xmm0
0x140094309  mov     [rsp+4E8h+var_258], rsi
0x140094311  mov     [rsp+4E8h+var_250], rsi
0x140094319  mov     r8d, 9
0x14009431f  lea     rdx, aOverrides; "Overrides"
0x140094326  lea     rcx, [rsp+4E8h+var_268]
0x14009432e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140094333  nop
0x140094334  lea     r8, [rsp+4E8h+var_268]
0x14009433c  lea     rdx, [rsp+4E8h+var_488]
0x140094341  lea     rcx, [rsp+4E8h+var_3D8]
0x140094349  call    ?Get@?$RegistryT@$0BAA@@@UEAA?AV?$unique_ref@UIStorageValue@@U?$default_delete@UIStorageValue@@@std@@@stdext@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; RegistryT<256>::Get(std::wstring const &)
0x14009434e  nop
0x14009434f  mov     rcx, [rax]
0x140094352  mov     rax, [rcx]
0x140094355  lea     rdx, [rsp+4E8h+var_478]
0x14009435a  mov     rax, [rax+30h]
0x14009435e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094363  nop
0x140094364  mov     rdx, [rsp+4E8h+var_488]
0x140094369  mov     r14d, 1
0x14009436f  test    rdx, rdx
0x140094372  jz      short loc_140094392
0x140094374  mov     rax, [rdx+8]
0x140094378  movsxd  rcx, dword ptr [rax+4]
0x14009437c  add     rcx, 8
0x140094380  add     rcx, rdx
0x140094383  mov     rax, [rcx]
0x140094386  mov     edx, r14d
0x140094389  mov     rax, [rax]
0x14009438c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094391  nop
0x140094392  lea     rcx, [rsp+4E8h+var_268]
0x14009439a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009439f  mov     rdi, [rsp+4E8h+var_478]
0x1400943a4  mov     rax, [rdi]
0x1400943a7  mov     rbx, [rax]
0x1400943aa  xorps   xmm0, xmm0
0x1400943ad  movups  [rsp+4E8h+var_268], xmm0
0x1400943b5  mov     [rsp+4E8h+var_258], rsi
0x1400943bd  mov     [rsp+4E8h+var_250], rsi
0x1400943c5  mov     r8d, 14h
0x1400943cb  lea     rdx, aFakesendreques; "FakeSendRequestError"
0x1400943d2  lea     rcx, [rsp+4E8h+var_268]
0x1400943da  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400943df  nop
0x1400943e0  lea     r8, [rsp+4E8h+var_268]
0x1400943e8  lea     rdx, [rsp+4E8h+var_438]
0x1400943f0  mov     rcx, rdi
0x1400943f3  mov     rax, rbx
0x1400943f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400943fb  nop
0x1400943fc  mov     rdx, [rax]
0x1400943ff  mov     rax, [rdx+8]
0x140094403  movsxd  rcx, dword ptr [rax+4]
0x140094407  add     rdx, 8
0x14009440b  add     rcx, rdx
0x14009440e  mov     rax, [rcx]
0x140094411  lea     rdx, [rsp+4E8h+var_248]
0x140094419  mov     rax, [rax+10h]
0x14009441d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094422  nop
0x140094423  mov     rdx, [rsp+4E8h+var_438]
0x14009442b  test    rdx, rdx
0x14009442e  jz      short loc_14009444E
0x140094430  mov     rax, [rdx+8]
0x140094434  movsxd  rcx, dword ptr [rax+4]
0x140094438  add     rcx, 8
0x14009443c  add     rcx, rdx
0x14009443f  mov     rax, [rcx]
0x140094442  mov     edx, r14d
0x140094445  mov     rax, [rax]
0x140094448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009444d  nop
0x14009444e  lea     rcx, [rsp+4E8h+var_268]
0x140094456  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009445b  mov     rax, qword ptr [rsp+4E8h+var_248+8]
0x140094463  test    rax, rax
0x140094466  jz      loc_14009454C
0x14009446c  cmp     [rax], esi
0x14009446e  jz      loc_14009454C
0x140094474  mov     rdi, [rsp+4E8h+var_478]
0x140094479  mov     rax, [rdi]
0x14009447c  mov     rbx, [rax]
0x14009447f  xorps   xmm0, xmm0
0x140094482  movups  [rsp+4E8h+Src], xmm0
0x14009448a  mov     [rsp+4E8h+var_278], rsi
0x140094492  mov     [rsp+4E8h+var_270], rsi
0x14009449a  mov     r8d, 14h
0x1400944a0  lea     rdx, aFakesendreques; "FakeSendRequestError"
0x1400944a7  lea     rcx, [rsp+4E8h+Src]
0x1400944af  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1400944b4  nop
0x1400944b5  lea     r8, [rsp+4E8h+Src]
0x1400944bd  lea     rdx, [rsp+4E8h+var_470]
0x1400944c2  mov     rcx, rdi
0x1400944c5  mov     rax, rbx
0x1400944c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400944cd  nop
0x1400944ce  mov     rcx, [rax]
0x1400944d1  mov     rax, [rcx]
0x1400944d4  xor     edx, edx
0x1400944d6  mov     rax, [rax+8]
0x1400944da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400944df  nop
0x1400944e0  mov     rdx, [rsp+4E8h+var_470]
0x1400944e5  test    rdx, rdx
0x1400944e8  jz      short loc_140094508
0x1400944ea  mov     rax, [rdx+8]
0x1400944ee  movsxd  rcx, dword ptr [rax+4]
0x1400944f2  add     rcx, 8
0x1400944f6  add     rcx, rdx
0x1400944f9  mov     rax, [rcx]
0x1400944fc  mov     edx, r14d
0x1400944ff  mov     rax, [rax]
0x140094502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140094507  nop
0x140094508  lea     rcx, [rsp+4E8h+Src]
0x140094510  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140094515  mov     rcx, qword ptr [rsp+4E8h+var_248+8]
0x14009451d  test    rcx, rcx
0x140094520  jz      loc_140095072
0x140094526  mov     ecx, [rcx]
0x140094528  sub     ecx, 1
0x14009452b  jz      loc_140095107
0x140094531  sub     ecx, 1
0x140094534  jz      loc_1400950E0
0x14009453a  sub     ecx, 1
0x14009453d  jz      loc_1400950B9
0x140094543  cmp     ecx, 1
0x140094546  jz      loc_140095099
0x14009454c  xorps   xmm0, xmm0
0x14009454f  movups  [rsp+4E8h+Src], xmm0
0x140094557  mov     [rsp+4E8h+var_278], rsi
0x14009455f  mov     [rsp+4E8h+var_270], rsi
0x140094567  mov     r8d, 3Ah ; ':'
0x14009456d  lea     rdx, aRequestexcepti_0; "RequestException - LockTime:{0}, Reques"...
0x140094574  lea     rcx, [rsp+4E8h+Src]
0x14009457c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140094581  lea     rdx, [rsp+4E8h+Src]
0x140094589  lea     rcx, [rsp+4E8h+var_220]
0x140094591  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x140094596  mov     rbx, rax
0x140094599  mov     r8d, r14d
0x14009459c  lea     rdx, [rsp+4E8h+var_248]
0x1400945a4  mov     rcx, r15
0x1400945a7  call    ?ToDebugString@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TimeType@@@Z; DateTime::ToDebugString(TimeType)
0x1400945ac  nop
0x1400945ad  mov     rdx, rax
0x1400945b0  mov     rcx, rbx; this
0x1400945b3  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x1400945b8  mov     rbx, rax
0x1400945bb  mov     r8d, r14d
0x1400945be  lea     rdx, [rsp+4E8h+var_268]
0x1400945c6  mov     rcx, r13
0x1400945c9  call    ?ToDebugString@DateTime@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4TimeType@@@Z; DateTime::ToDebugString(TimeType)
0x1400945ce  nop
0x1400945cf  mov     rdx, rax
0x1400945d2  mov     rcx, rbx; this
0x1400945d5  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x1400945da  mov     rbx, rax
0x1400945dd  lea     rdx, [rsp+4E8h+var_1F8]
0x1400945e5  cmp     [rsp+4E8h+var_1E0], 0Fh
0x1400945ee  cmova   rdx, qword ptr [rsp+4E8h+var_1F8]
0x1400945f7  lea     rcx, [rsp+4E8h+Src]
0x1400945ff  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; StringAlgo::ToUnicode(char const *)
0x140094604  nop
0x140094605  lea     rdx, [rsp+4E8h+Src]
0x14009460d  mov     r15d, 7
0x140094613  cmp     [rsp+4E8h+var_270], r15
0x14009461b  cmova   rdx, qword ptr [rsp+4E8h+Src]; unsigned __int16 *
0x140094624  mov     rcx, rbx; this
0x140094627  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x14009462c  nop
0x14009462d  lea     rcx, [rsp+4E8h+Src]
0x140094635  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009463a  mov     rcx, rbx
0x14009463d  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x140094642  nop
0x140094643  lea     rcx, [rsp+4E8h+var_268]
0x14009464b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140094650  nop
0x140094651  lea     rcx, [rsp+4E8h+var_248]
0x140094659  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009465e  nop
0x14009465f  lea     rcx, [rsp+4E8h+var_220]
0x140094667  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14009466c  lea     rcx, [rsp+4E8h+var_268]
0x140094674  call    ?CreateForEnforcementFrontDoorService@AuthScope@MicrosoftAccount@wpc@@SA?AV123@XZ; wpc::MicrosoftAccount::AuthScope::CreateForEnforcementFrontDoorService(void)
0x140094679  nop
0x14009467a  mov     rdx, rax
0x14009467d  lea     rcx, [rsp+4E8h+var_118]
0x140094685  call    ?GetCurrentUsersTicket@MSATokenBroker@@YA?AUUserTicketResult@MicrosoftAccount@wpc@@AEBVAuthScope@34@I@Z; MSATokenBroker::GetCurrentUsersTicket(wpc::MicrosoftAccount::AuthScope const &,uint)
0x14009468a  nop
0x14009468b  lea     rcx, [rsp+4E8h+var_268]
0x140094693  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140094698  lea     r13, WPP_GLOBAL_Control
0x14009469f  mov     rax, cs:WPP_GLOBAL_Control
0x1400946a6  cmp     rax, r13
0x1400946a9  jz      loc_140094744
0x1400946af  test    byte ptr [rax+1Ch], 4
0x1400946b3  jz      loc_140094744
0x1400946b9  mov     r8, [rsp+4E8h+var_D8]
0x1400946c1  test    r8, r8
0x1400946c4  jz      short loc_1400946D5
0x1400946c6  lea     rcx, [rsp+4E8h+Src]
0x1400946ce  call    stdext__call__wpc__MicrosoftAccount__UserTicketResult__Serialize____2____lambda_1__const__std__tuple_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_______
0x1400946d3  jmp     short loc_140094702
0x1400946d5  mov     r8, [rsp+4E8h+var_108]
0x1400946dd  test    r8, r8
0x1400946e0  jz      loc_14009512C
0x1400946e6  mov     eax, [r8]
0x1400946e9  mov     [rsp+4E8h+var_4C8], eax
0x1400946ed  mov     r9d, [r8+4]
0x1400946f1  mov     r8d, [r8+8]
0x1400946f5  lea     rdx, [rsp+4E8h+Src]
0x1400946fd  call    _wpc__MicrosoftAccount__UserTicketResult__Serialize____2____lambda_2___operator__
0x140094702  lea     r9, [rsp+4E8h+Src]
0x14009470a  cmp     [rsp+4E8h+var_270], r15
  ... truncated ...
```
