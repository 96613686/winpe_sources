# CWatsonTpTransport::DoUpload(void)

- ea: `0x180024840`
- end: `0x18002543e`
- name: `?DoUpload@CWatsonTpTransport@@AEAAJXZ`
- size: `3070`
- prototype: `__int64 __fastcall(CWatsonTpTransport *__hidden this)`
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18004e610`

## callees

- `0x180004c64`
- `0x180005be8`
- `0x18000cf50`
- `0x18000db80`
- `0x180020680`
- `0x180024840`
- `0x180025444`
- `0x180025470`
- `0x1800254b4`
- `0x18002eac4`
- `0x18003b7e0`
- `0x18003b974`
- `0x18003de9c`
- `0x18003e2b4`
- `0x18003fc6c`
- `0x1800412b4`
- `0x180046730`
- `0x180049fb0`
- `0x18004ab74`
- `0x18004af98`
- `0x18004cff4`
- `0x18004eb28`
- `0x18004eb78`
- `0x1800544c0`
- `0x180073e20`
- `0x18007543c`
- `0x180076ac4`
- `0x18008aa94`
- `0x18008ac10`
- `0x18008af68`
- `0x18008b110`
- `0x18008b588`
- `0x18008bd58`
- `0x18008c8a4`
- `0x18008c9f0`
- `0x18008cd48`
- `0x18008ea64`
- `0x18009341c`
- `0x180093454`
- `0x18009349c`
- `0x1800934d0`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800253ce`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024c0b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025223`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180024c0b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180025223`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024b67`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002518b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180024b67`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002518b`
- `ext-ms-win-wer-xbox-l1-2-1!XerHitRequestResponse` at `0x180024cfc`
- `ext-ms-win-wer-xbox-l1-2-1!XerHitRequestResponse` at `0x180024cfc`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CWatsonTpTransport::DoUpload(CWatsonTpTransport *this)
{
  __int64 v2; // r14
  int DeviceTicketHeader; // ebx
  int v4; // eax
  wchar_t *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  wchar_t *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r9
  BOOL v11; // r13d
  int UploadCab; // eax
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  wchar_t *v17; // rcx
  _DWORD *v18; // rbx
  int *v19; // r9
  wchar_t *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  struct CReportCabStream *v27; // r13
  void *v28; // rbx
  unsigned __int64 v29; // rax
  int v30; // eax
  wchar_t *v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r9
  int v34; // eax
  const wchar_t *v35; // rbx
  unsigned __int64 v36; // rax
  int v37; // ebx
  void *v38; // rax
  _QWORD v40[3]; // [rsp+80h] [rbp-80h] BYREF
  struct CReportCabStream *v41; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *v42; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *v43; // [rsp+A8h] [rbp-58h]
  char v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v46[32]; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID lpMem[2]; // [rsp+100h] [rbp+0h] BYREF
  char v48; // [rsp+110h] [rbp+10h] BYREF
  void **v49; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v50[24]; // [rsp+128h] [rbp+28h] BYREF
  void **v51; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v52[24]; // [rsp+148h] [rbp+48h] BYREF
  wchar_t *v53[2]; // [rsp+160h] [rbp+60h] BYREF
  char v54; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v55[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v56[848]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v57[32]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v58[912]; // [rsp+510h] [rbp+410h] BYREF
  BOOL v59; // [rsp+8B0h] [rbp+7B0h]
  __int64 v60; // [rsp+8B8h] [rbp+7B8h] BYREF
  int v61; // [rsp+8C0h] [rbp+7C0h] BYREF
  __int64 v62; // [rsp+8C8h] [rbp+7C8h] BYREF

  v2 = *((_QWORD *)this + 6);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v55);
  v51 = &CTpResponseMessage::`vftable';
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v52);
  CTpRequestMessage::CTpRequestMessage((CTpRequestMessage *)v57);
  v49 = &CTpResponseMessage::`vftable';
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v50);
  utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(v40);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v53);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v42);
  v62 = 0;
  LODWORD(v60) = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpMem);
  v61 = 2;
  v41 = 0;
  DeviceTicketHeader = CTransport::EventTransportBegin(this, (struct CReport *)v2, *((void **)this + 5));
  if ( DeviceTicketHeader < 0 )
    goto LABEL_163;
  if ( (int)MachineId::GetMachineId((__int64)v53) >= 0 )
  {
    v4 = CTpRequestMessage::SetMachineId((CTpRequestMessage *)v55, v53[0]);
    DeviceTicketHeader = v4;
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 59;
LABEL_7:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, (unsigned int)v4);
        goto LABEL_163;
      }
      goto LABEL_163;
    }
  }
  v4 = OsInformation::Copy((OsInformation *)v56, (const struct OsInformation *)(*((_QWORD *)this + 6) + 6032LL));
  DeviceTicketHeader = v4;
  if ( v4 >= 0 )
  {
    v4 = OsInformation::Copy((OsInformation *)v58, (const struct OsInformation *)(*((_QWORD *)this + 6) + 6032LL));
    DeviceTicketHeader = v4;
    if ( v4 < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v6 = 61;
        goto LABEL_7;
      }
      goto LABEL_163;
    }
    v7 = CTpRequestMessage::SetCommercialInfo(
           v55,
           *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
           *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
           *((_QWORD *)this + 6) + 51920LL);
    DeviceTicketHeader = v7;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 62;
LABEL_20:
      v10 = (unsigned int)v7;
LABEL_21:
      WPP_SF_d(*((_QWORD *)v8 + 2), v9, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, v10);
      goto LABEL_163;
    }
    v7 = CTpRequestMessage::SetCommercialInfo(
           v57,
           *(unsigned int *)(*((_QWORD *)this + 6) + 51912LL),
           *(unsigned int *)(*((_QWORD *)this + 6) + 51916LL),
           *((_QWORD *)this + 6) + 51920LL);
    DeviceTicketHeader = v7;
    if ( v7 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 63;
      goto LABEL_20;
    }
    v11 = 0;
    v59 = 0;
    CTpLogger::StartSession((CWatsonTpTransport *)((char *)this + 80), L"watson");
    if ( *((_DWORD *)this + 14) )
    {
      UploadCab = CWatsonTpTransport::LoadResumeState(this, &v42, &v62);
      DeviceTicketHeader = UploadCab;
      if ( UploadCab < 0 )
      {
        v8 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          goto LABEL_163;
        v9 = 77;
        goto LABEL_31;
      }
      if ( v42 == v43 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26);
      if ( !v62 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v25, v24, v26);
      v8 = WPP_GLOBAL_Control;
      goto LABEL_109;
    }
    UploadCab = CWatsonTpTransport::PrepareEventRequest((struct CReport *)v2, (struct CTpRequestMessage *)v55);
    DeviceTicketHeader = UploadCab;
    if ( UploadCab < 0 )
    {
      *(_DWORD *)(v2 + 5960) |= 0x60u;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 64;
LABEL_31:
      v10 = (unsigned int)UploadCab;
      goto LABEL_21;
    }
    DeviceTicketHeader = CTransport::GetDeviceTicketHeader(lpMem, *((_QWORD *)this + 5));
    if ( DeviceTicketHeader < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_163;
      v9 = 65;
LABEL_36:
      v10 = (unsigned int)DeviceTicketHeader;
      goto LABEL_21;
    }
    v13 = *(_QWORD *)(v2 + 52056);
    if ( v13 )
    {
      v11 = ImpersonateLoggedOnUser(*(HANDLE *)(v2 + 52056));
      v59 = v11;
    }
    DeviceTicketHeader = CTpTransport::DoExchange(
                           (struct CTpRequestMessage *)v55,
                           0,
                           (CTpResponseMessage *)&v51,
                           (__int64)off_1800B4818,
                           (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
                           0,
                           0,
                           v13,
                           *((void **)this + 5),
                           (CWatsonTpTransport *)((char *)this + 80),
                           (wchar_t *)L"s1event",
                           0,
                           (wchar_t *)lpMem[0],
                           0,
                           *(_DWORD *)(v2 + 52052));
    if ( v11 )
    {
      RevertToSelf();
      v59 = 0;
    }
    if ( DeviceTicketHeader < 0 )
    {
      *(_DWORD *)(v2 + 5960) |= 0x60u;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 66;
      goto LABEL_36;
    }
    v14 = CReport::AddStateParam((CReport *)v2, L"Transport.DoneStage1", L"1");
    if ( v14 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v14);
    UploadCab = CWatsonTpTransport::ParseEventResponse(
                  (CTpResponseMessage *)&v51,
                  (CResponse *)(v2 + 8),
                  (struct CDataRequest *)v40,
                  (__int64)&v62,
                  (__int64)&v60);
    DeviceTicketHeader = UploadCab;
    if ( UploadCab < 0 )
    {
      *(_DWORD *)(v2 + 5960) |= 0x60u;
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 68;
      goto LABEL_31;
    }
    if ( (unsigned __int8)IsXerHitRequestResponsePresent() )
      XerHitRequestResponse(*(_QWORD *)(v2 + 8));
    CWatsonTpTransport::SetLegacyTokensFromCollectCommand(
      (const struct CDataRequest *)v40,
      (struct CResponse *)(v2 + 8));
    if ( *(_DWORD *)(v2 + 46680) == 2 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs(v17, v15, v16);
      DeviceTicketHeader = -2147467263;
      goto LABEL_163;
    }
    v18 = (_DWORD *)(v2 + 6616);
    if ( *(_DWORD *)(v2 + 364) )
    {
      *v18 |= 0x100u;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
    }
    if ( (unsigned int)CDataRequest::IsBypassDataThrottling((CDataRequest *)v40) )
      *v18 |= 0x800u;
    if ( (_DWORD)v60 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      goto LABEL_70;
    }
    if ( *(_DWORD *)(v2 + 252) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_77;
      v21 = 72;
LABEL_76:
      WPP_SF_(*((_QWORD *)v20 + 2), v21, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
LABEL_77:
      CReport::ThrottleCurrentEvent((CReport *)v2, *(_DWORD *)(v2 + 252));
LABEL_70:
      *(_DWORD *)(v2 + 5960) |= 0x2000u;
LABEL_71:
      DeviceTicketHeader = 1769483;
      goto LABEL_163;
    }
    if ( !(-286331153 * (unsigned int)((__int64)(v40[1] - v40[0]) >> 3)) )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_162;
      v22 = 73;
      goto LABEL_161;
    }
    DeviceTicketHeader = CTransport::EventDataRequest(
                           this,
                           (struct CDataRequest *)v40,
                           *((void **)this + 5),
                           v19,
                           (enum TRANSPORT_SECONDLEVEL_USER_RESPONSE *)&v61);
    if ( DeviceTicketHeader < 0 )
      goto LABEL_163;
    v23 = CWatsonTpTransport::SaveResumeState(this, &v42, v62);
    DeviceTicketHeader = v23;
    if ( v23 < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_88;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        74,
        WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
        (unsigned int)v23);
    }
    v8 = WPP_GLOBAL_Control;
LABEL_88:
    if ( v61 == 1 )
    {
      if ( DeviceTicketHeader >= 0 || v8 == (wchar_t *)&WPP_GLOBAL_Control || (v8[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 75;
      goto LABEL_36;
    }
    if ( v61 == 3 )
    {
      if ( v8 != (wchar_t *)&WPP_GLOBAL_Control && (v8[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)v8 + 2), (unsigned int)(v61 + 73), WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      *(_DWORD *)(v2 + 5960) |= 0x1000u;
      goto LABEL_71;
    }
    if ( v61 )
    {
      DeviceTicketHeader = -2145681407;
      goto LABEL_163;
    }
LABEL_109:
    if ( v42 == v43 )
    {
      if ( v8 == (wchar_t *)&WPP_GLOBAL_Control || (v8[14] & 2) == 0 )
        goto LABEL_162;
      v22 = 78;
      goto LABEL_161;
    }
    UploadCab = CTransport::EventGetUploadCab(this, &v41, *((void **)this + 5), 0);
    DeviceTicketHeader = UploadCab;
    if ( UploadCab < 0 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_163;
      v9 = 79;
      goto LABEL_31;
    }
    v27 = v41;
    if ( !v41 )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 2) == 0 )
        goto LABEL_162;
      v22 = 86;
LABEL_161:
      WPP_SF_(*((_QWORD *)v8 + 2), v22, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
      goto LABEL_162;
    }
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v46);
    CTpResponseMessage::CTpResponseMessage((CTpResponseMessage *)v45);
    v28 = (void *)*((_QWORD *)this + 5);
    v29 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v27 + 32LL))(v27);
    v30 = CTransport::EventUploadStart(this, v29, v28);
    DeviceTicketHeader = v30;
    if ( v30 >= 0 )
    {
      v34 = CWatsonTpTransport::UploadToAzure(
              this,
              v27,
              v42,
              (const wchar_t *)lpMem[0],
              (const struct CDataRequest *)v40);
      DeviceTicketHeader = v34;
      if ( v34 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids);
        goto LABEL_124;
      }
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          81,
          WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids,
          (unsigned int)v34);
      v35 = L"zip";
      if ( !*((_DWORD *)v27 + 4) )
        v35 = L"cab";
      v36 = (*(__int64 (__fastcall **)(struct CReportCabStream *))(*(_QWORD *)v27 + 32LL))(v27);
      v30 = CWatsonTpTransport::PrepareCabUploadRequest(
              (struct CReport *)v2,
              (struct CResponse *)(v2 + 8),
              v42,
              v36,
              v35,
              (const struct CDataRequest *)v40,
              (struct CTpRequestMessage *)v57);
      DeviceTicketHeader = v30;
      if ( v30 >= 0 )
      {
        v37 = 0;
        if ( (unsigned int)CSettings::IsUploadOnFreeNetworksOnly((CSettings *)(*((_QWORD *)this + 6) + 46688LL))
          && !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(*((CReport **)this + 6)) )
        {
          v37 = 2;
        }
        v38 = *(void **)(v2 + 52056);
        v60 = (__int64)v38;
        if ( v38 )
          v59 = ImpersonateLoggedOnUser(v38);
        DeviceTicketHeader = CTpTransport::DoExchange(
                               (struct CTpRequestMessage *)v57,
                               v27,
                               (CTpResponseMessage *)&v49,
                               (__int64)off_1800B4818,
                               (struct ITpCallbacks *)(((unsigned __int64)this + 32) & -(__int64)(this != 0)),
                               v37,
                               0,
                               v60,
                               *((void **)this + 5),
                               (CWatsonTpTransport *)((char *)this + 80),
                               (wchar_t *)L"cab-upload",
                               0,
                               (wchar_t *)lpMem[0],
                               0,
                               0);
        if ( v59 )
          RevertToSelf();
        if ( DeviceTicketHeader >= 0 )
        {
          DeviceTicketHeader = CWatsonTpTransport::ParseCabUploadResponse(
                                 (struct CTpResponseMessage *)&v49,
                                 (struct CResponse *)(v2 + 8),
                                 (int *)&v60);
          CTransport::EventCabUploadComplete(this, DeviceTicketHeader);
          if ( DeviceTicketHeader >= 0 )
          {
            CWatsonTpTransport::ForgetResumeState(this);
            CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v45);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
            if ( *(_DWORD *)(v2 + 252) )
            {
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
                goto LABEL_77;
              v21 = 87;
              goto LABEL_76;
            }
LABEL_162:
            DeviceTicketHeader = 0;
            goto LABEL_163;
          }
          *(_DWORD *)(v2 + 5960) |= 0x180u;
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
          {
LABEL_124:
            CTpResponseMessage::~CTpResponseMessage((CTpResponseMessage *)v45);
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v46);
            goto LABEL_163;
          }
          v32 = 85;
        }
        else
        {
          CTransport::EventCabUploadComplete(this, DeviceTicketHeader);
          *(_DWORD *)(v2 + 5960) |= 0x180u;
          v31 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_124;
          v32 = 84;
        }
        v33 = (unsigned int)DeviceTicketHeader;
LABEL_123:
        WPP_SF_d(*((_QWORD *)v31 + 2), v32, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids, v33);
        goto LABEL_124;
      }
      *(_DWORD *)(v2 + 5960) |= 0x180u;
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_124;
      v32 = 83;
    }
    else
    {
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_124;
      v32 = 80;
    }
    v33 = (unsigned int)v30;
    goto LABEL_123;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v6 = 60;
    goto LABEL_7;
  }
LABEL_163:
  CTransport::EventTransportFinish(this, DeviceTicketHeader);
  if ( lpMem[0] != &v48 )
    HeapFree(g_hWerheap, 0, lpMem[0]);
  if ( v42 != (wchar_t *)&v44 )
    HeapFree(g_hWerheap, 0, v42);
  if ( (char *)v53[0] != &v54 )
    HeapFree(g_hWerheap, 0, v53[0]);
  utl::vector<RequestToken,utl::allocator<RequestToken>>::_Uninit(v40);
  v49 = &CTpResponseMessage::`vftable';
  utl::vector<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>,utl::allocator<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>>>::_Uninit(v50);
  v49 = &CTpMessage::`vftable';
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v57);
  v51 = &CTpResponseMessage::`vftable';
  utl::vector<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>,utl::allocator<utl::unique_ptr<CTpRequestSection,utl::default_delete<CTpRequestSection>>>>::_Uninit(v52);
  v51 = &CTpMessage::`vftable';
  CTpRequestMessage::~CTpRequestMessage((CTpRequestMessage *)v55);
  return (unsigned int)DeviceTicketHeader;
}

```

## disassembly

```asm
0x180024840  push    rbp
0x180024842  push    rbx
0x180024843  push    rsi
0x180024844  push    rdi
0x180024845  push    r12
0x180024847  push    r13
0x180024849  push    r14
0x18002484b  push    r15
0x18002484d  lea     rbp, [rsp-768h]
0x180024855  sub     rsp, 868h
0x18002485c  mov     r15, rcx
0x18002485f  mov     r14, [rcx+30h]
0x180024863  lea     rcx, [rbp+7A0h+var_720]; this
0x18002486a  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x18002486f  nop
0x180024870  lea     rsi, ??_7CTpResponseMessage@@6B@; const CTpResponseMessage::`vftable'
0x180024877  mov     [rbp+7A0h+var_760], rsi
0x18002487b  lea     rcx, [rbp+7A0h+var_758]
0x18002487f  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180024884  nop
0x180024885  lea     rcx, [rbp+7A0h+var_3B0]; this
0x18002488c  call    ??0CTpRequestMessage@@QEAA@XZ; CTpRequestMessage::CTpRequestMessage(void)
0x180024891  nop
0x180024892  mov     [rbp+7A0h+var_780], rsi
0x180024896  lea     rcx, [rbp+7A0h+var_778]
0x18002489a  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x18002489f  nop
0x1800248a0  lea     rcx, [rbp+7A0h+var_820]
0x1800248a4  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::vector<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x1800248a9  nop
0x1800248aa  lea     rcx, [rbp+7A0h+var_740]; void *
0x1800248ae  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800248b3  nop
0x1800248b4  lea     rcx, [rbp+7A0h+var_800]; void *
0x1800248b8  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800248bd  nop
0x1800248be  xor     edi, edi
0x1800248c0  mov     [rbp+7A0h+arg_18], rdi
0x1800248c7  mov     dword ptr [rbp+7A0h+arg_8], edi
0x1800248cd  lea     rcx, [rbp+7A0h+lpMem]; void *
0x1800248d1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800248d6  nop
0x1800248d7  mov     [rbp+7A0h+arg_10], 2
0x1800248e1  mov     [rbp+7A0h+var_808], rdi
0x1800248e5  mov     r8, [r15+28h]; void *
0x1800248e9  mov     rdx, r14; struct CReport *
0x1800248ec  mov     rcx, r15; this
0x1800248ef  call    ?EventTransportBegin@CTransport@@IEAAJPEAVCReport@@PEAX@Z; CTransport::EventTransportBegin(CReport *,void *)
0x1800248f4  mov     ebx, eax
0x1800248f6  test    eax, eax
0x1800248f8  js      loc_180025367
0x1800248fe  lea     rcx, [rbp+7A0h+var_740]; __int64
0x180024902  call    ?GetMachineId@MachineId@@SAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; MachineId::GetMachineId(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180024907  test    eax, eax
0x180024909  js      short loc_18002495F
0x18002490b  mov     rdx, [rbp+7A0h+var_740]; wchar_t *
0x18002490f  lea     rcx, [rbp+7A0h+var_720]; this
0x180024916  call    ?SetMachineId@CTpRequestMessage@@QEAAJPEB_W@Z; CTpRequestMessage::SetMachineId(wchar_t const *)
0x18002491b  mov     ebx, eax
0x18002491d  test    eax, eax
0x18002491f  jns     short loc_18002495F
0x180024921  lea     rdi, WPP_GLOBAL_Control
0x180024928  mov     rcx, cs:WPP_GLOBAL_Control
0x18002492f  cmp     rcx, rdi
0x180024932  jz      loc_180025367
0x180024938  test    byte ptr [rcx+1Ch], 1
0x18002493c  jz      loc_180025367
0x180024942  mov     edx, 3Bh ; ';'
0x180024947  mov     r9d, eax
0x18002494a  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180024951  mov     rcx, [rcx+10h]
0x180024955  call    WPP_SF_d
0x18002495a  jmp     loc_180025360
0x18002495f  mov     rdx, [r15+30h]
0x180024963  mov     esi, 1790h
0x180024968  add     rdx, rsi; struct OsInformation *
0x18002496b  lea     rcx, [rbp+7A0h+var_700]; this
0x180024972  call    ?Copy@OsInformation@@QEAAJAEBV1@@Z; OsInformation::Copy(OsInformation const &)
0x180024977  mov     ebx, eax
0x180024979  test    eax, eax
0x18002497b  jns     short loc_1800249A5
0x18002497d  lea     rdi, WPP_GLOBAL_Control
0x180024984  mov     rcx, cs:WPP_GLOBAL_Control
0x18002498b  cmp     rcx, rdi
0x18002498e  jz      loc_180025360
0x180024994  test    byte ptr [rcx+1Ch], 1
0x180024998  jz      loc_180025360
0x18002499e  mov     edx, 3Ch ; '<'
0x1800249a3  jmp     short loc_180024947
0x1800249a5  mov     rdx, [r15+30h]
0x1800249a9  add     rdx, rsi; struct OsInformation *
0x1800249ac  lea     rcx, [rbp+7A0h+var_390]; this
0x1800249b3  call    ?Copy@OsInformation@@QEAAJAEBV1@@Z; OsInformation::Copy(OsInformation const &)
0x1800249b8  mov     ebx, eax
0x1800249ba  test    eax, eax
0x1800249bc  jns     short loc_1800249E9
0x1800249be  lea     rdi, WPP_GLOBAL_Control
0x1800249c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800249cc  cmp     rcx, rdi
0x1800249cf  jz      loc_180025360
0x1800249d5  test    byte ptr [rcx+1Ch], 1
0x1800249d9  jz      loc_180025360
0x1800249df  mov     edx, 3Dh ; '='
0x1800249e4  jmp     loc_180024947
0x1800249e9  mov     rdx, [r15+30h]
0x1800249ed  lea     r9, [rdx+0CAD0h]
0x1800249f4  mov     r8d, [rdx+0CACCh]
0x1800249fb  mov     edx, [rdx+0CAC8h]
0x180024a01  lea     rcx, [rbp+7A0h+var_720]
0x180024a08  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180024a0d  mov     ebx, eax
0x180024a0f  test    eax, eax
0x180024a11  jns     short loc_180024A51
0x180024a13  lea     rdi, WPP_GLOBAL_Control
0x180024a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a21  cmp     rcx, rdi
0x180024a24  jz      loc_180025360
0x180024a2a  test    byte ptr [rcx+1Ch], 1
0x180024a2e  jz      loc_180025360
0x180024a34  mov     edx, 3Eh ; '>'
0x180024a39  mov     r9d, eax
0x180024a3c  lea     r8, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180024a43  mov     rcx, [rcx+10h]
0x180024a47  call    WPP_SF_d
0x180024a4c  jmp     loc_180025360
0x180024a51  mov     rdx, [r15+30h]
0x180024a55  lea     r9, [rdx+0CAD0h]
0x180024a5c  mov     r8d, [rdx+0CACCh]
0x180024a63  mov     edx, [rdx+0CAC8h]
0x180024a69  lea     rcx, [rbp+7A0h+var_3B0]
0x180024a70  call    ?SetCommercialInfo@CTpRequestMessage@@QEAAJHHAEBV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CTpRequestMessage::SetCommercialInfo(int,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> const &)
0x180024a75  mov     ebx, eax
0x180024a77  test    eax, eax
0x180024a79  jns     short loc_180024AA3
0x180024a7b  lea     rdi, WPP_GLOBAL_Control
0x180024a82  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a89  cmp     rcx, rdi
0x180024a8c  jz      loc_180025360
0x180024a92  test    byte ptr [rcx+1Ch], 1
0x180024a96  jz      loc_180025360
0x180024a9c  mov     edx, 3Fh ; '?'
0x180024aa1  jmp     short loc_180024A39
0x180024aa3  lea     r12, [r14+8]
0x180024aa7  mov     r13d, edi
0x180024aaa  mov     [rbp+7A0h+arg_0], edi
0x180024ab0  lea     rcx, [r15+50h]; this
0x180024ab4  lea     rdx, aWatson_0; "watson"
0x180024abb  call    ?StartSession@CTpLogger@@QEAAJPEB_W@Z; CTpLogger::StartSession(wchar_t const *)
0x180024ac0  lea     rdi, WPP_GLOBAL_Control
0x180024ac7  lea     rsi, WPP_83f6e81bb0ab34620bedf8523afe8501_Traceguids
0x180024ace  cmp     [r15+38h], r13d
0x180024ad2  jnz     loc_180024F2D
0x180024ad8  lea     rdx, [rbp+7A0h+var_720]; struct CTpRequestMessage *
0x180024adf  mov     rcx, r14; this
0x180024ae2  call    ?PrepareEventRequest@CWatsonTpTransport@@CAJPEAVCReport@@PEAVCTpRequestMessage@@@Z; CWatsonTpTransport::PrepareEventRequest(CReport *,CTpRequestMessage *)
0x180024ae7  mov     ebx, eax
0x180024ae9  test    eax, eax
0x180024aeb  jns     short loc_180024B1F
0x180024aed  or      dword ptr [r14+1748h], 60h
0x180024af5  mov     rcx, cs:WPP_GLOBAL_Control
0x180024afc  cmp     rcx, rdi
0x180024aff  jz      loc_180025360
0x180024b05  test    byte ptr [rcx+1Ch], 1
0x180024b09  jz      loc_180025360
0x180024b0f  mov     edx, 40h ; '@'
0x180024b14  mov     r9d, eax
0x180024b17  mov     r8, rsi
0x180024b1a  jmp     loc_180024A43
0x180024b1f  mov     rdx, [r15+28h]
0x180024b23  lea     rcx, [rbp+7A0h+lpMem]
0x180024b27  call    ?GetDeviceTicketHeader@CTransport@@KAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAX@Z; CTransport::GetDeviceTicketHeader(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,void *)
0x180024b2c  mov     ebx, eax
0x180024b2e  test    eax, eax
0x180024b30  jns     short loc_180024B58
0x180024b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b39  cmp     rcx, rdi
0x180024b3c  jz      loc_180025360
0x180024b42  mov     eax, 2
0x180024b47  test    [rcx+1Ch], al
0x180024b4a  jz      loc_180025360
0x180024b50  lea     edx, [rax+3Fh]
0x180024b53  mov     r9d, ebx
0x180024b56  jmp     short loc_180024B17
0x180024b58  mov     rbx, [r14+0CB58h]
0x180024b5f  test    rbx, rbx
0x180024b62  jz      short loc_180024B7C
0x180024b64  mov     rcx, rbx; hToken
0x180024b67  call    cs:__imp_ImpersonateLoggedOnUser
0x180024b6e  nop     dword ptr [rax+rax+00h]
0x180024b73  mov     r13d, eax
0x180024b76  mov     [rbp+7A0h+arg_0], eax
0x180024b7c  mov     r8, [rbp+7A0h+lpMem]
0x180024b80  mov     rcx, r15
0x180024b83  lea     rdx, [r15+20h]
0x180024b87  neg     rcx
0x180024b8a  sbb     r9, r9
0x180024b8d  and     r9, rdx
0x180024b90  mov     ecx, [r14+0CB54h]
0x180024b97  mov     [rsp+8A0h+var_830], ecx; int
0x180024b9b  mov     [rsp+8A0h+var_838], 0; __int64
0x180024ba4  mov     [rsp+8A0h+var_840], r8; __int64
0x180024ba9  mov     qword ptr [rsp+8A0h+var_848], 0; int
0x180024bb2  lea     rax, aS1event; "s1event"
0x180024bb9  mov     [rsp+8A0h+var_850], rax; __int64
0x180024bbe  lea     rax, [r15+50h]
0x180024bc2  mov     [rsp+8A0h+var_858], rax; __int64
0x180024bc7  mov     rax, [r15+28h]
0x180024bcb  mov     [rsp+8A0h+var_860], rax; __int64
0x180024bd0  mov     [rsp+8A0h+var_868], rbx; __int64
0x180024bd5  mov     [rsp+8A0h+var_870], 0; int
0x180024bde  mov     dword ptr [rsp+8A0h+var_878], 0; int
0x180024be6  mov     [rsp+8A0h+var_880], r9; struct ITpCallbacks *
0x180024beb  lea     r9, off_1800B4818
0x180024bf2  lea     r8, [rbp+7A0h+var_760]
0x180024bf6  xor     edx, edx
0x180024bf8  lea     rcx, [rbp+7A0h+var_720]; this
0x180024bff  call    ?DoExchange@CTpTransport@@SAJPEAVCTpRequestMessage@@PEAUIWerByteStream@@PEAVCTpResponseMessage@@PEBQ6AJPEB_WPEAV?$unique_ptr@VITpCommand@@U?$default_delete@VITpCommand@@@utl@@@utl@@@ZPEAUITpCallbacks@@K3PEAX7PEAVCTpLogger@@3PEAUISequentialStream@@3PEAUWINHTTP_TIMEOUTS@@K@Z; CTpTransport::DoExchange(CTpRequestMessage *,IWerByteStream *,CTpResponseMessage *,long (*const *)(wchar_t const *,utl::unique_ptr<ITpCommand,utl::default_delete<ITpCommand>> *),ITpCallbacks *,ulong,wchar_t const *,void *,void *,CTpLogger *,wchar_t const *,ISequentialStream *,wchar_t const *,WINHTTP_TIMEOUTS *,ulong)
0x180024c04  mov     ebx, eax
0x180024c06  test    r13d, r13d
0x180024c09  jz      short loc_180024C21
0x180024c0b  call    cs:__imp_RevertToSelf
0x180024c12  nop     dword ptr [rax+rax+00h]
0x180024c17  mov     [rbp+7A0h+arg_0], 0
0x180024c21  test    ebx, ebx
0x180024c23  jns     short loc_180024C51
0x180024c25  or      dword ptr [r14+1748h], 60h
0x180024c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c34  cmp     rcx, rdi
0x180024c37  jz      loc_180025360
0x180024c3d  test    byte ptr [rcx+1Ch], 1
0x180024c41  jz      loc_180025360
0x180024c47  mov     edx, 42h ; 'B'
0x180024c4c  jmp     loc_180024B53
0x180024c51  lea     r8, a1; "1"
0x180024c58  lea     rdx, aTransportDones; "Transport.DoneStage1"
0x180024c5f  mov     rcx, r14; this
0x180024c62  call    ?AddStateParam@CReport@@QEAAJPEB_W0@Z; CReport::AddStateParam(wchar_t const *,wchar_t const *)
0x180024c67  test    eax, eax
0x180024c69  jns     short loc_180024C91
0x180024c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c72  cmp     rcx, rdi
0x180024c75  jz      short loc_180024C91
0x180024c77  test    byte ptr [rcx+1Ch], 2
0x180024c7b  jz      short loc_180024C91
0x180024c7d  mov     edx, 43h ; 'C'
0x180024c82  mov     r9d, eax
0x180024c85  mov     r8, rsi
0x180024c88  mov     rcx, [rcx+10h]
0x180024c8c  call    WPP_SF_d
0x180024c91  lea     rax, [rbp+7A0h+arg_8]
0x180024c98  mov     [rsp+8A0h+var_878], rax; __int64
0x180024c9d  lea     rax, [rbp+7A0h+arg_18]
0x180024ca4  mov     [rsp+8A0h+var_880], rax; __int64
0x180024ca9  lea     r9, [rbp+7A0h+var_800]
0x180024cad  lea     r8, [rbp+7A0h+var_820]; struct CDataRequest *
0x180024cb1  mov     rdx, r12; CResponse *
0x180024cb4  lea     rcx, [rbp+7A0h+var_760]; this
0x180024cb8  call    ?ParseEventResponse@CWatsonTpTransport@@CAJPEAVCTpResponseMessage@@PEAVCResponse@@PEAVCDataRequest@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEA_KPEAH@Z; CWatsonTpTransport::ParseEventResponse(CTpResponseMessage *,CResponse *,CDataRequest *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,unsigned __int64 *,int *)
0x180024cbd  mov     ebx, eax
0x180024cbf  test    eax, eax
0x180024cc1  jns     short loc_180024CEF
0x180024cc3  or      dword ptr [r14+1748h], 60h
0x180024ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cd2  cmp     rcx, rdi
0x180024cd5  jz      loc_180025360
0x180024cdb  test    byte ptr [rcx+1Ch], 1
0x180024cdf  jz      loc_180025360
0x180024ce5  mov     edx, 44h ; 'D'
0x180024cea  jmp     loc_180024B14
0x180024cef  call    IsXerHitRequestResponsePresent
0x180024cf4  test    al, al
0x180024cf6  jz      short loc_180024D08
0x180024cf8  mov     rcx, [r12]
0x180024cfc  call    cs:__imp_XerHitRequestResponse
0x180024d03  nop     dword ptr [rax+rax+00h]
0x180024d08  mov     rdx, r12; struct CResponse *
0x180024d0b  lea     rcx, [rbp+7A0h+var_820]; this
0x180024d0f  call    ?SetLegacyTokensFromCollectCommand@CWatsonTpTransport@@CAXPEBVCDataRequest@@PEAVCResponse@@@Z; CWatsonTpTransport::SetLegacyTokensFromCollectCommand(CDataRequest const *,CResponse *)
0x180024d14  cmp     dword ptr [r14+0B658h], 2
0x180024d1c  jnz     short loc_180024D50
0x180024d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d25  cmp     rcx, rdi
0x180024d28  jz      short loc_180024D41
0x180024d2a  test    byte ptr [rcx+1Ch], 4
0x180024d2e  jz      short loc_180024D41
0x180024d30  mov     edx, 45h ; 'E'
0x180024d35  mov     r8, rsi
0x180024d38  mov     rcx, [rcx+10h]
0x180024d3c  call    WPP_SF_
0x180024d41  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024d46  mov     ebx, 80004001h
0x180024d4b  jmp     loc_180025360
0x180024d50  lea     rbx, [r14+19D8h]
0x180024d57  cmp     dword ptr [r12+164h], 0
0x180024d60  jz      short loc_180024D89
0x180024d62  bts     dword ptr [rbx], 8
0x180024d66  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d6d  cmp     rcx, rdi
0x180024d70  jz      short loc_180024D89
0x180024d72  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
