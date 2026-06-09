# CReportManager::TransportCallback(TRANSPORT_CALLBACK_PARAM *,TRANSPORT_CALLBACK_DATA *)

- ea: `0x1800180d8`
- end: `0x180018b1d`
- name: `?TransportCallback@CReportManager@@QEAAJPEAUTRANSPORT_CALLBACK_PARAM@@PEAUTRANSPORT_CALLBACK_DATA@@@Z`
- size: `2629`
- prototype: `__int64 __fastcall(CReportManager *__hidden this, struct TRANSPORT_CALLBACK_PARAM *, struct TRANSPORT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800180c0`

## callees

- `0x180004bd4`
- `0x180004c64`
- `0x180009490`
- `0x18000ad98`
- `0x18000cf50`
- `0x18000db80`
- `0x1800180d8`
- `0x180018e90`
- `0x180020680`
- `0x18002b5d4`
- `0x18002dea4`
- `0x18002f750`
- `0x18002f8bc`
- `0x1800317b4`
- `0x1800334f8`
- `0x180036c60`
- `0x18003cef0`
- `0x18003de9c`
- `0x18004373c`
- `0x180043804`
- `0x180044080`
- `0x1800479ac`
- `0x180048ce0`
- `0x180048db4`
- `0x18004d2d4`
- `0x18004e964`
- `0x18005446c`
- `0x180054514`
- `0x18006cb20`
- `0x18007543c`
- `0x18007d814`
- `0x18007e5f4`
- `0x18007e678`
- `0x18007e6d8`
- `0x18007e918`
- `0x18007eecc`
- `0x18007efc4`
- `0x180082cec`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018246`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180018246`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018623`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018623`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadComplete` at `0x18001897a`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadComplete` at `0x18001897a`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadProgress` at `0x180018879`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadProgress` at `0x180018879`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadStart` at `0x1800181d8`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadStart` at `0x1800181d8`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventFinish` at `0x18001860a`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventFinish` at `0x18001860a`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventBegin` at `0x1800187ec`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventBegin` at `0x1800187ec`

## pseudocode

```c
__int64 __fastcall CReportManager::TransportCallback(CReport **this, struct TRANSPORT_CALLBACK_PARAM *a2, HANDLE *a3)
{
  __int64 v6; // r9
  unsigned int WatsonCab; // r15d
  wchar_t *v8; // rcx
  CReport *v9; // rcx
  int v10; // ebx
  unsigned int v11; // r8d
  CReport *v12; // rax
  CReport *v13; // rax
  CReport *v14; // rax
  CReport *v15; // rax
  int v16; // ecx
  int v17; // eax
  int v18; // ebx
  wchar_t *v19; // rcx
  __int64 v20; // rdx
  wchar_t *v21; // rcx
  CReport *v22; // r14
  int UniqueIdentifier; // eax
  CReport *v24; // rax
  wchar_t *v25; // rcx
  __int64 v26; // rdx
  _WORD *v27; // rax
  _WORD *v28; // rax
  _QWORD *v29; // rsi
  _QWORD *i; // rbx
  wchar_t *v31; // rcx
  __int64 v32; // r14
  int v33; // eax
  wchar_t *v34; // rcx
  __int64 v35; // rdx
  CReport *v36; // rcx
  _QWORD *v37; // rdi
  _QWORD *v38; // rsi
  __int64 v39; // rdx
  __int64 v40; // r8
  CReport *v41; // rdx
  int v42; // eax
  unsigned int v43; // r9d
  __int64 v44; // rdx
  unsigned int v45; // r9d
  _OWORD v47[2]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v48; // [rsp+50h] [rbp-49h] BYREF
  __m256i v49; // [rsp+60h] [rbp-39h] BYREF
  __int128 v50; // [rsp+80h] [rbp-19h] BYREF
  __m256i v51; // [rsp+90h] [rbp-9h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0, a3);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2, a3);
  if ( a2 && a3 )
  {
    v6 = *((unsigned int *)a2 + 2);
    WatsonCab = 0;
    if ( (_DWORD)v6 == 5 )
    {
      if ( this[13] )
      {
        v36 = this[3];
        v37 = (_QWORD *)((char *)a2 + 24);
        v38 = (_QWORD *)((char *)a2 + 16);
        (*(void (__fastcall **)(CReport *, __int64, _QWORD, _QWORD))(*(_QWORD *)v36 + 24LL))(v36, 4, *v38, *v37);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
          WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), v39, v40, *v38, *v37);
      }
      else
      {
        v37 = (_QWORD *)((char *)a2 + 24);
        v38 = (_QWORD *)((char *)a2 + 16);
      }
      if ( (unsigned __int8)((__int64 (*)(void))IsXerTransportEventUploadCompletePresent)() )
        XerTransportEventUploadProgress(*v38, *v37);
      return WatsonCab;
    }
    if ( (int)v6 <= 5 )
    {
      if ( (_DWORD)v6 )
      {
        if ( (_DWORD)v6 != 1 )
        {
          if ( (_DWORD)v6 != 2 )
          {
            if ( (_DWORD)v6 == 3 )
            {
              if ( (unsigned int)CReport::IsSecondaryDataEnabled(this[1]) )
              {
                (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], 2);
                GetTickCount();
                CReportManager::AddTracingFile((CReportManager *)this);
                v9 = this[1];
                v10 = *((_DWORD *)v9 + 12947);
                if ( (unsigned int)CReport::IsSecondLevelDataThrottled(v9, v10 != 3) )
                {
                  *((_DWORD *)this + 34) = 0;
                  *((_DWORD *)a2 + 6) = 3;
                }
                else
                {
                  WatsonCab = CReportManager::AddSecondLevelData(
                                (CReportManager *)this,
                                *((const struct CDataRequest **)a2 + 2));
                  if ( (WatsonCab & 0x80000000) == 0 )
                  {
                    v11 = 0;
                    if ( v10 == 3 )
                      v11 = 0x1000000;
                    if ( CReport::GetNumFilesByFlags(this[1], 0x10000u, v11) )
                    {
                      if ( !(unsigned int)CReportManager::CalcDefaultSecondLevelPromptResult((CReportManager *)this) )
                        *((_DWORD *)this + 34) = (*(__int64 (__fastcall **)(CReport *))(*(_QWORD *)this[3] + 32LL))(this[3]);
                      if ( *((_DWORD *)this + 34) == 1
                        && !(unsigned int)CReport::GetUploadShouldBypassPowerThrottling(this[1])
                        && (unsigned int)WerpIsOnBattery() )
                      {
                        v12 = this[1];
                        *((_DWORD *)this + 34) = 3;
                        *((_DWORD *)v12 + 1490) |= 0x4000u;
                      }
                      if ( *((_DWORD *)this + 34) == 1 )
                      {
                        if ( !(unsigned int)CReport::GetUploadShouldBypassNetworkCostThrottling(this[1])
                          && (unsigned int)UtilIsNetworkRestricted() )
                        {
                          v13 = this[1];
                          *((_DWORD *)this + 34) = 3;
                          *((_DWORD *)v13 + 1490) |= 0x8000u;
                        }
                        if ( *((_DWORD *)this + 34) == 1 )
                        {
                          if ( (unsigned int)CReport::ContainsConfidentialFiles(this[1]) )
                          {
                            v14 = this[1];
                            *((_DWORD *)this + 34) = 3;
                            *((_DWORD *)v14 + 1490) |= 0x10000u;
                          }
                          if ( *((_DWORD *)this + 34) == 1 )
                          {
                            if ( CRegSetting::GetDwordData((CReport *)((char *)this[1] + 51680)) )
                            {
                              *((_DWORD *)this + 34) = 3;
                              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
                                && (WPP_GLOBAL_Control[14] & 4) != 0 )
                              {
                                WPP_SF_(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  167,
                                  WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
                              }
                              *((_DWORD *)this[1] + 1490) |= 0x8000u;
                            }
                            if ( *((_DWORD *)this + 34) == 1
                              && (unsigned int)CReportManager::ExternalCallbackSecondLevelResponse(this, 1) )
                            {
                              v15 = this[1];
                              *((_DWORD *)this + 34) = 3;
                              *((_DWORD *)v15 + 1490) |= 0x800000u;
                            }
                          }
                        }
                      }
                      v16 = *((_DWORD *)this + 34);
                      if ( v16 == 1 )
                        *((_DWORD *)a2 + 6) = 0;
                      else
                        *((_DWORD *)a2 + 6) = (v16 != 3) + 1;
                    }
                  }
                }
              }
              else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
              }
              v17 = *((_DWORD *)this + 34);
              v47[0] = 0;
              LODWORD(v47[0]) = 24;
              DWORD2(v47[0]) = v17;
              CReportManager::ExternalCallbackUI((CReportManager *)this, (struct _WER_UI_CALLBACK_INPUT *)v47);
              if ( *((_DWORD *)this + 41) != 7 )
              {
                v18 = *((_DWORD *)this[1] + 1654);
                if ( (v18 & 1) != 0 )
                  CReportManager::ExternalCallbackDocRecoveryNotification((CReportManager *)this);
                if ( (v18 & 2) != 0 )
                  CReportManager::ExternalCallbackRestartNotification((CReportManager *)this);
              }
              return WatsonCab;
            }
            if ( (_DWORD)v6 == 4 )
            {
              *((_DWORD *)this[1] + 1656) = 6;
              (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], 4);
              v8 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                WPP_SF_q(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  168,
                  WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
                  *((_QWORD *)a2 + 2));
              a3[2] = (HANDLE)*((_QWORD *)a2 + 2);
              if ( (unsigned __int8)IsXerTransportEventUploadCompletePresent(v8) )
                XerTransportEventUploadStart(*((_QWORD *)a2 + 2));
              return WatsonCab;
            }
LABEL_121:
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids, v6);
            return WatsonCab;
          }
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            return WatsonCab;
          v20 = 165;
LABEL_62:
          WPP_SF_(*((_QWORD *)v19 + 2), v20, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
          return WatsonCab;
        }
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
        v22 = this[1];
        *((_DWORD *)this + 28) = *((_DWORD *)a2 + 4);
        if ( !(unsigned __int8)IsXerProgressCallbackPresent(v21) )
        {
LABEL_81:
          SetEvent(a3[1]);
          (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], 5);
          v27 = (_WORD *)*((_QWORD *)v22 + 1);
          if ( v27 && *v27 || (v28 = (_WORD *)*((_QWORD *)v22 + 14)) != 0 && *v28 )
            *((_DWORD *)this + 30) = CReportManager::ExternalCallbackResponseReceived(
                                       (CReportManager *)this,
                                       (CReport *)((char *)v22 + 8));
          v29 = (_QWORD *)((char *)v22 + 368);
          if ( (_QWORD *)*v29 != v29 )
          {
            CReportManager::ExternalCallbackControlRequestBegin((CReportManager *)this);
            for ( i = (_QWORD *)*v29; i != v29; i = (_QWORD *)*i )
              CReportManager::ExternalCallbackControlRequest(
                (CReportManager *)this,
                (const wchar_t *)i[2],
                (const wchar_t *)i[6]);
            CReportManager::ExternalCallbackControlRequestEnd((CReportManager *)this);
          }
          return WatsonCab;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
        UniqueIdentifier = CReport::GetUniqueIdentifier(this[1], v47);
        WatsonCab = UniqueIdentifier;
        if ( UniqueIdentifier < 0
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            162,
            WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
            (unsigned int)UniqueIdentifier);
        }
        v24 = this[1];
        memset(&v49.m256i_u64[1], 0, 24);
        v48 = *((unsigned __int64 *)v24 + 70);
        v49.m256i_i64[0] = *(_QWORD *)&v47[0];
        if ( CReportManager::IsXboxVmCrashDump((CReportManager *)this, &v48) )
        {
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_80;
          v26 = 163;
        }
        else
        {
          if ( !CReportManager::IsXboxGameCoreHeapDump((CReportManager *)this, &v48) )
            goto LABEL_80;
          v25 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_80;
          v26 = 164;
        }
        WPP_SF_(*((_QWORD *)v25 + 2), v26, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
LABEL_80:
        v49.m256i_i32[5] = *((_DWORD *)this + 28);
        v49.m256i_i64[3] = *((_QWORD *)v22 + 32);
        v50 = v48;
        v51 = v49;
        XerTransportEventFinish(&v50);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
        goto LABEL_81;
      }
      CReportManager::ExternalCallbackUploadBegin((CReportManager *)this);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
      if ( !(unsigned __int8)IsXerProgressCallbackPresent(v31) )
        return WatsonCab;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v47);
      v32 = *((_QWORD *)a2 + 2);
      v33 = CReport::GetUniqueIdentifier(v32, v47);
      WatsonCab = v33;
      if ( v33 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          158,
          WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
          (unsigned int)v33);
      *(_QWORD *)&v48 = *(_QWORD *)(v32 + 560);
      *((_QWORD *)&v48 + 1) = *(_QWORD *)a2;
      *(_OWORD *)v49.m256i_i8 = *(unsigned __int64 *)&v47[0];
      *(__int64 *)((char *)&v49.m256i_i64[2] + 1) = 0;
      *(__int32 *)((char *)&v49.m256i_i32[6] + 1) = 0;
      *(__int16 *)((char *)&v49.m256i_i16[14] + 1) = 0;
      v49.m256i_i8[31] = 0;
      v49.m256i_i8[16] = 0;
      if ( CReportManager::IsXboxVmCrashDump((CReportManager *)this, &v48) )
      {
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_108;
        v35 = 159;
      }
      else
      {
        if ( !CReportManager::IsXboxGameCoreHeapDump((CReportManager *)this, &v48) )
          goto LABEL_108;
        v34 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_108;
        v35 = 160;
      }
      WPP_SF_(*((_QWORD *)v34 + 2), v35, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
LABEL_108:
      v50 = v48;
      v51 = v49;
      XerTransportEventBegin(&v50);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v47);
      return WatsonCab;
    }
    switch ( (_DWORD)v6 )
    {
      case 6:
        if ( (*((_DWORD *)this[1] + 1654) & 0x40000000) != 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            return WatsonCab;
          v20 = 171;
          goto LABEL_62;
        }
        if ( (unsigned __int8)IsXerTransportEventUploadCompletePresent((unsigned int)(v6 - 6))
          && !(unsigned int)CReport::IsSecondaryDataEnabled(this[1]) )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
          *((_DWORD *)this[1] + 1490) |= 0x800u;
          return WatsonCab;
        }
        if ( *((_DWORD *)this + 34) != 1 && *((_DWORD *)this[1] + 1468) != 4 )
        {
          *((_QWORD *)a2 + 2) = 0;
          return WatsonCab;
        }
        v44 = 1;
        if ( *((_DWORD *)this[1] + 1468) != 4 )
          v44 = 3;
        (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], v44);
        CReportManager::ExternalCallbackCabProgress((CReportManager *)this, 0, 0, v45);
        WatsonCab = CReportManager::CreateWatsonCab((CReportManager *)this, *((_DWORD *)a2 + 6));
        if ( (WatsonCab & 0x80000000) != 0 )
        {
          *((_DWORD *)this + 29) = -2147024865;
          return WatsonCab;
        }
        break;
      case 7:
        (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], 3);
        return WatsonCab;
      case 8:
        CReportManager::CabCompressCallback((CReportManager *)this, *((_QWORD *)a2 + 2), *((_QWORD *)a2 + 3));
        return WatsonCab;
      case 9:
        *((_DWORD *)this + 29) = *((_DWORD *)a2 + 4);
        if ( (unsigned __int8)IsXerTransportEventUploadCompletePresent((unsigned int)(v6 - 9)) )
          XerTransportEventUploadComplete(*((unsigned int *)this + 29));
        return WatsonCab;
      case 0xA:
        v41 = this[13];
        this[13] = 0;
        if ( v41 )
          utl::default_delete<CReportCabStream>::operator()();
        CReportManager::ExternalCallbackCabProgress((CReportManager *)this, 0, 0, v6);
        v42 = CReportManager::CreateWatsonCab((CReportManager *)this, *((_DWORD *)a2 + 6));
        WatsonCab = v42;
        if ( v42 < 0 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              170,
              WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids,
              (unsigned int)v42);
          goto LABEL_151;
        }
        break;
      default:
        goto LABEL_121;
    }
    *((_QWORD *)a2 + 2) = this[13];
LABEL_151:
    CReportManager::ExternalCallbackCabProgress((CReportManager *)this, 1, 1u, v43);
    return WatsonCab;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800180d8  push    rbp
0x1800180da  push    rbx
0x1800180db  push    rsi
0x1800180dc  push    rdi
0x1800180dd  push    r12
0x1800180df  push    r13
0x1800180e1  push    r14
0x1800180e3  push    r15
0x1800180e5  lea     rbp, [rsp-1Fh]
0x1800180ea  sub     rsp, 0B8h
0x1800180f1  xor     r12d, r12d
0x1800180f4  mov     r13, r8
0x1800180f7  mov     rsi, rdx
0x1800180fa  mov     rdi, rcx
0x1800180fd  test    rdx, rdx
0x180018100  jnz     short loc_180018107
0x180018102  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018107  test    r13, r13
0x18001810a  jnz     short loc_180018111
0x18001810c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018111  test    rsi, rsi
0x180018114  jz      loc_180018AD5
0x18001811a  test    r13, r13
0x18001811d  jz      loc_180018AD5
0x180018123  mov     r9d, [rsi+8]
0x180018127  mov     r15d, r12d
0x18001812a  cmp     r9d, 5
0x18001812e  jz      loc_180018806
0x180018134  jg      loc_18001888A
0x18001813a  mov     ecx, r9d
0x18001813d  test    r9d, r9d
0x180018140  jz      loc_1800186B0
0x180018146  sub     ecx, 1
0x180018149  jz      loc_1800184CA
0x18001814f  sub     ecx, 1
0x180018152  jz      loc_18001848F
0x180018158  sub     ecx, 1
0x18001815b  jz      loc_1800181E9
0x180018161  cmp     ecx, 1
0x180018164  jnz     loc_1800188B6
0x18001816a  mov     rax, [rdi+8]
0x18001816e  mov     edx, 4
0x180018173  mov     dword ptr [rax+19E0h], 6
0x18001817d  mov     rcx, [rdi+18h]
0x180018181  mov     rax, [rcx]
0x180018184  mov     rax, [rax+10h]
0x180018188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001818d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018194  lea     rbx, WPP_GLOBAL_Control
0x18001819b  cmp     rcx, rbx
0x18001819e  jz      short loc_1800181BF
0x1800181a0  test    byte ptr [rcx+1Ch], 4
0x1800181a4  jz      short loc_1800181BF
0x1800181a6  mov     r9, [rsi+10h]
0x1800181aa  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x1800181b1  mov     rcx, [rcx+10h]
0x1800181b5  mov     edx, 0A8h
0x1800181ba  call    WPP_SF_q
0x1800181bf  mov     rax, [rsi+10h]
0x1800181c3  mov     [r13+10h], rax
0x1800181c7  call    IsXerTransportEventUploadCompletePresent
0x1800181cc  test    al, al
0x1800181ce  jz      loc_180018AD0
0x1800181d4  mov     rcx, [rsi+10h]
0x1800181d8  call    cs:__imp_XerTransportEventUploadStart
0x1800181df  nop     dword ptr [rax+rax+00h]
0x1800181e4  jmp     loc_180018AD0
0x1800181e9  mov     rcx, [rdi+8]; this
0x1800181ed  call    ?IsSecondaryDataEnabled@CReport@@QEBAHXZ; CReport::IsSecondaryDataEnabled(void)
0x1800181f2  test    eax, eax
0x1800181f4  jnz     short loc_180018231
0x1800181f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181fd  lea     rbx, WPP_GLOBAL_Control
0x180018204  cmp     rcx, rbx
0x180018207  jz      loc_180018431
0x18001820d  test    byte ptr [rcx+1Ch], 4
0x180018211  jz      loc_180018431
0x180018217  mov     rcx, [rcx+10h]
0x18001821b  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180018222  mov     edx, 0A6h
0x180018227  call    WPP_SF_
0x18001822c  jmp     loc_180018431
0x180018231  mov     rcx, [rdi+18h]
0x180018235  mov     edx, 2
0x18001823a  mov     rax, [rcx]
0x18001823d  mov     rax, [rax+10h]
0x180018241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018246  call    cs:__imp_GetTickCount
0x18001824d  nop     dword ptr [rax+rax+00h]
0x180018252  mov     rcx, rdi; this
0x180018255  call    ?AddTracingFile@CReportManager@@AEAAJXZ; CReportManager::AddTracingFile(void)
0x18001825a  mov     rcx, [rdi+8]; this
0x18001825e  mov     edx, r12d
0x180018261  mov     r14d, 3
0x180018267  mov     ebx, [rcx+0CA4Ch]
0x18001826d  cmp     ebx, r14d
0x180018270  setnz   dl; int
0x180018273  call    ?IsSecondLevelDataThrottled@CReport@@QEAAHH@Z; CReport::IsSecondLevelDataThrottled(int)
0x180018278  test    eax, eax
0x18001827a  jz      short loc_18001828C
0x18001827c  mov     [rdi+88h], r12d
0x180018283  mov     [rsi+18h], r14d
0x180018287  jmp     loc_180018431
0x18001828c  mov     rdx, [rsi+10h]; struct CDataRequest *
0x180018290  mov     rcx, rdi; this
0x180018293  call    ?AddSecondLevelData@CReportManager@@AEAAJPEBVCDataRequest@@@Z; CReportManager::AddSecondLevelData(CDataRequest const *)
0x180018298  mov     r15d, eax
0x18001829b  test    eax, eax
0x18001829d  js      loc_180018431
0x1800182a3  mov     rcx, [rdi+8]; this
0x1800182a7  cmp     ebx, r14d
0x1800182aa  mov     r8d, r12d
0x1800182ad  mov     eax, 1000000h
0x1800182b2  mov     ebx, 10000h
0x1800182b7  cmovz   r8d, eax; unsigned int
0x1800182bb  mov     edx, ebx; unsigned int
0x1800182bd  call    ?GetNumFilesByFlags@CReport@@QEAAKKK@Z; CReport::GetNumFilesByFlags(ulong,ulong)
0x1800182c2  test    eax, eax
0x1800182c4  jz      loc_180018431
0x1800182ca  mov     rcx, rdi; this
0x1800182cd  call    ?CalcDefaultSecondLevelPromptResult@CReportManager@@AEAAHXZ; CReportManager::CalcDefaultSecondLevelPromptResult(void)
0x1800182d2  test    eax, eax
0x1800182d4  jnz     short loc_1800182EC
0x1800182d6  mov     rcx, [rdi+18h]
0x1800182da  mov     rax, [rcx]
0x1800182dd  mov     rax, [rax+20h]
0x1800182e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e6  mov     [rdi+88h], eax
0x1800182ec  cmp     dword ptr [rdi+88h], 1
0x1800182f3  jnz     short loc_18001831E
0x1800182f5  mov     rcx, [rdi+8]; this
0x1800182f9  call    ?GetUploadShouldBypassPowerThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassPowerThrottling(void)
0x1800182fe  test    eax, eax
0x180018300  jnz     short loc_18001831E
0x180018302  call    WerpIsOnBattery
0x180018307  test    eax, eax
0x180018309  jz      short loc_18001831E
0x18001830b  mov     rax, [rdi+8]
0x18001830f  mov     [rdi+88h], r14d
0x180018316  bts     dword ptr [rax+1748h], 0Eh
0x18001831e  cmp     dword ptr [rdi+88h], 1
0x180018325  mov     r13d, 8000h
0x18001832b  jnz     loc_180018412
0x180018331  mov     rcx, [rdi+8]; this
0x180018335  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x18001833a  test    eax, eax
0x18001833c  jnz     short loc_180018359
0x18001833e  call    ?UtilIsNetworkRestricted@@YAHXZ; UtilIsNetworkRestricted(void)
0x180018343  test    eax, eax
0x180018345  jz      short loc_180018359
0x180018347  mov     rax, [rdi+8]
0x18001834b  mov     [rdi+88h], r14d
0x180018352  or      [rax+1748h], r13d
0x180018359  cmp     dword ptr [rdi+88h], 1
0x180018360  jnz     loc_180018412
0x180018366  mov     rcx, [rdi+8]; this
0x18001836a  call    ?ContainsConfidentialFiles@CReport@@QEAAHXZ; CReport::ContainsConfidentialFiles(void)
0x18001836f  test    eax, eax
0x180018371  jz      short loc_180018384
0x180018373  mov     rax, [rdi+8]
0x180018377  mov     [rdi+88h], r14d
0x18001837e  or      [rax+1748h], ebx
0x180018384  cmp     dword ptr [rdi+88h], 1
0x18001838b  jnz     loc_180018412
0x180018391  mov     rcx, [rdi+8]
0x180018395  add     rcx, 0C9E0h; this
0x18001839c  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x1800183a1  test    eax, eax
0x1800183a3  jz      short loc_1800183E5
0x1800183a5  mov     [rdi+88h], r14d
0x1800183ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183b3  lea     rbx, WPP_GLOBAL_Control
0x1800183ba  cmp     rcx, rbx
0x1800183bd  jz      short loc_1800183DA
0x1800183bf  test    byte ptr [rcx+1Ch], 4
0x1800183c3  jz      short loc_1800183DA
0x1800183c5  mov     rcx, [rcx+10h]
0x1800183c9  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x1800183d0  mov     edx, 0A7h
0x1800183d5  call    WPP_SF_
0x1800183da  mov     rax, [rdi+8]
0x1800183de  or      [rax+1748h], r13d
0x1800183e5  cmp     dword ptr [rdi+88h], 1
0x1800183ec  jnz     short loc_180018412
0x1800183ee  mov     edx, 1
0x1800183f3  mov     rcx, rdi
0x1800183f6  call    ?ExternalCallbackSecondLevelResponse@CReportManager@@AEAAHW4SECONDLEVEL_SELECTION@@@Z; CReportManager::ExternalCallbackSecondLevelResponse(SECONDLEVEL_SELECTION)
0x1800183fb  test    eax, eax
0x1800183fd  jz      short loc_180018412
0x1800183ff  mov     rax, [rdi+8]
0x180018403  mov     [rdi+88h], r14d
0x18001840a  bts     dword ptr [rax+1748h], 17h
0x180018412  mov     ecx, [rdi+88h]
0x180018418  cmp     ecx, 1
0x18001841b  jnz     short loc_180018423
0x18001841d  mov     [rsi+18h], r12d
0x180018421  jmp     short loc_180018431
0x180018423  cmp     ecx, r14d
0x180018426  mov     eax, r12d
0x180018429  setnz   al
0x18001842c  inc     eax
0x18001842e  mov     [rsi+18h], eax
0x180018431  mov     eax, [rdi+88h]
0x180018437  lea     rdx, [rbp+57h+var_C0]; struct _WER_UI_CALLBACK_INPUT *
0x18001843b  xorps   xmm0, xmm0
0x18001843e  mov     rcx, rdi; this
0x180018441  movdqa  [rbp+57h+var_C0], xmm0
0x180018446  mov     dword ptr [rbp+57h+var_C0], 18h
0x18001844d  mov     dword ptr [rbp+57h+var_C0+8], eax
0x180018450  call    ?ExternalCallbackUI@CReportManager@@QEAAHPEAU_WER_UI_CALLBACK_INPUT@@@Z; CReportManager::ExternalCallbackUI(_WER_UI_CALLBACK_INPUT *)
0x180018455  cmp     dword ptr [rdi+0A4h], 7
0x18001845c  jz      loc_180018AD0
0x180018462  mov     rax, [rdi+8]
0x180018466  mov     ebx, [rax+19D8h]
0x18001846c  test    bl, 1
0x18001846f  jz      short loc_180018479
0x180018471  mov     rcx, rdi; this
0x180018474  call    ?ExternalCallbackDocRecoveryNotification@CReportManager@@AEAAHXZ; CReportManager::ExternalCallbackDocRecoveryNotification(void)
0x180018479  test    bl, 2
0x18001847c  jz      loc_180018AD0
0x180018482  mov     rcx, rdi; this
0x180018485  call    ?ExternalCallbackRestartNotification@CReportManager@@AEAAHXZ; CReportManager::ExternalCallbackRestartNotification(void)
0x18001848a  jmp     loc_180018AD0
0x18001848f  mov     rcx, cs:WPP_GLOBAL_Control
0x180018496  lea     rbx, WPP_GLOBAL_Control
0x18001849d  cmp     rcx, rbx
0x1800184a0  jz      loc_180018AD0
0x1800184a6  test    byte ptr [rcx+1Ch], 4
0x1800184aa  jz      loc_180018AD0
0x1800184b0  mov     edx, 0A5h
0x1800184b5  mov     rcx, [rcx+10h]
0x1800184b9  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x1800184c0  call    WPP_SF_
0x1800184c5  jmp     loc_180018AD0
0x1800184ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184d1  lea     rbx, WPP_GLOBAL_Control
0x1800184d8  cmp     rcx, rbx
0x1800184db  jz      short loc_1800184F8
0x1800184dd  test    byte ptr [rcx+1Ch], 4
0x1800184e1  jz      short loc_1800184F8
0x1800184e3  mov     rcx, [rcx+10h]
0x1800184e7  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x1800184ee  mov     edx, 0A1h
0x1800184f3  call    WPP_SF_
0x1800184f8  mov     eax, [rsi+10h]
0x1800184fb  mov     r14, [rdi+8]
0x1800184ff  mov     [rdi+70h], eax
0x180018502  call    IsXerProgressCallbackPresent
0x180018507  test    al, al
0x180018509  jz      loc_18001861F
0x18001850f  lea     rcx, [rbp+57h+var_C0]; void *
0x180018513  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180018518  mov     rcx, [rdi+8]
0x18001851c  lea     rdx, [rbp+57h+var_C0]
0x180018520  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180018525  mov     r15d, eax
0x180018528  test    eax, eax
0x18001852a  jns     short loc_180018556
0x18001852c  mov     rcx, cs:WPP_GLOBAL_Control
0x180018533  cmp     rcx, rbx
0x180018536  jz      short loc_180018556
0x180018538  test    byte ptr [rcx+1Ch], 1
0x18001853c  jz      short loc_180018556
0x18001853e  mov     rcx, [rcx+10h]
0x180018542  lea     r8, WPP_6ad42813e292370fdbddf61f29a0acf4_Traceguids
0x180018549  mov     edx, 0A2h
0x18001854e  mov     r9d, eax
0x180018551  call    WPP_SF_d
0x180018556  mov     rax, [rdi+8]
0x18001855a  lea     rdx, [rbp+57h+var_A0]; void *
0x18001855e  xorps   xmm0, xmm0
0x180018561  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180018565  movdqu  [rbp+57h+var_90+8], xmm0
0x18001856a  mov     qword ptr [rbp+57h+var_80+8], r12
0x18001856e  mov     rcx, [rax+230h]
0x180018575  mov     rax, qword ptr [rbp+57h+var_C0]
0x180018579  mov     qword ptr [rbp+57h+var_A0], rcx
0x18001857d  mov     rcx, rdi; this
0x180018580  mov     qword ptr [rbp+57h+var_90], rax
0x180018584  call    ?IsXboxVmCrashDump@CReportManager@@QEAAEPEAX@Z; CReportManager::IsXboxVmCrashDump(void *)
0x180018589  test    al, al
0x18001858b  jz      short loc_1800185A6
0x18001858d  mov     rcx, cs:WPP_GLOBAL_Control
0x180018594  cmp     rcx, rbx
0x180018597  jz      short loc_1800185DD
0x180018599  test    byte ptr [rcx+1Ch], 4
0x18001859d  jz      short loc_1800185DD
0x18001859f  mov     edx, 0A3h
0x1800185a4  jmp     short loc_1800185CD
0x1800185a6  lea     rdx, [rbp+57h+var_A0]; void *
0x1800185aa  mov     rcx, rdi; this
0x1800185ad  call    ?IsXboxGameCoreHeapDump@CReportManager@@QEAAEPEAX@Z; CReportManager::IsXboxGameCoreHeapDump(void *)
0x1800185b2  test    al, al
0x1800185b4  jz      short loc_1800185DD
0x1800185b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800185bd  cmp     rcx, rbx
0x1800185c0  jz      short loc_1800185DD
0x1800185c2  test    byte ptr [rcx+1Ch], 4
0x1800185c6  jz      short loc_1800185DD
0x1800185c8  mov     edx, 0A4h
  ... truncated ...
```
