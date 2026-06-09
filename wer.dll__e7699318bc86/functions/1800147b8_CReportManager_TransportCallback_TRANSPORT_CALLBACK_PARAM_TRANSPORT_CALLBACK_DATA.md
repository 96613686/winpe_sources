# CReportManager::TransportCallback(TRANSPORT_CALLBACK_PARAM *,TRANSPORT_CALLBACK_DATA *)

- ea: `0x1800147b8`
- end: `0x1800151d2`
- name: `?TransportCallback@CReportManager@@QEAAJPEAUTRANSPORT_CALLBACK_PARAM@@PEAUTRANSPORT_CALLBACK_DATA@@@Z`
- size: `2586`
- prototype: `__int64 __fastcall(CReport **this, struct TRANSPORT_CALLBACK_PARAM *, struct TRANSPORT_CALLBACK_DATA *)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147a0`

## callees

- `0x180004b24`
- `0x180004bb4`
- `0x180008388`
- `0x180009ad4`
- `0x18000bc10`
- `0x18000dad0`
- `0x1800147b8`
- `0x180015600`
- `0x18001fe24`
- `0x180029c50`
- `0x18002c1d0`
- `0x18002dbf4`
- `0x18002e390`
- `0x18002fc18`
- `0x180031b84`
- `0x180035054`
- `0x18003afa0`
- `0x18003bf14`
- `0x180041aac`
- `0x1800426b4`
- `0x1800429c0`
- `0x180045bdc`
- `0x180047060`
- `0x18004712c`
- `0x18004afd4`
- `0x18004c59c`
- `0x180051efc`
- `0x180051fa4`
- `0x1800699b0`
- `0x1800720ec`
- `0x18007a1c8`
- `0x18007af38`
- `0x18007afbc`
- `0x18007b01c`
- `0x18007b1d8`
- `0x18007b778`
- `0x18007b864`
- `0x18007f254`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014920`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180014920`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014cf1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180014cf1`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadComplete` at `0x180015036`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadComplete` at `0x180015036`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadProgress` at `0x180014f3b`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadProgress` at `0x180014f3b`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadStart` at `0x1800148b8`
- `ext-ms-win-wer-xbox-l1-1-3!XerTransportEventUploadStart` at `0x1800148b8`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventFinish` at `0x180014cde`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventFinish` at `0x180014cde`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventBegin` at `0x180014eb4`
- `ext-ms-win-wer-xbox-l1-2-0!XerTransportEventBegin` at `0x180014eb4`

## pseudocode

```c
__int64 __fastcall CReportManager::TransportCallback(
        CReport **this,
        struct TRANSPORT_CALLBACK_PARAM *a2,
        struct TRANSPORT_CALLBACK_DATA *a3)
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
  CReport *v21; // r14
  int UniqueIdentifier; // eax
  CReport *v23; // rax
  wchar_t *v24; // rcx
  __int64 v25; // rdx
  _WORD *v26; // rax
  _WORD *v27; // rax
  _QWORD *v28; // rsi
  _QWORD *i; // rbx
  __int64 v30; // r14
  int v31; // eax
  wchar_t *v32; // rcx
  __int64 v33; // rdx
  CReport *v34; // rcx
  _QWORD *v35; // rdi
  _QWORD *v36; // rsi
  __int64 v37; // rdx
  __int64 v38; // r8
  CReport *v39; // rdx
  int v40; // eax
  unsigned int v41; // r9d
  __int64 v42; // rdx
  unsigned int v43; // r9d
  _OWORD v45[2]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v46; // [rsp+50h] [rbp-49h] BYREF
  __m256i v47; // [rsp+60h] [rbp-39h] BYREF
  __int128 v48; // [rsp+80h] [rbp-19h] BYREF
  __m256i v49; // [rsp+90h] [rbp-9h]

  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, 0);
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs(this, a2);
  if ( a2 && a3 )
  {
    v6 = *((unsigned int *)a2 + 2);
    WatsonCab = 0;
    if ( (_DWORD)v6 == 5 )
    {
      if ( this[13] )
      {
        v34 = this[3];
        v35 = (_QWORD *)((char *)a2 + 24);
        v36 = (_QWORD *)((char *)a2 + 16);
        (*(void (__fastcall **)(CReport *, __int64, _QWORD, _QWORD))(*(_QWORD *)v34 + 24LL))(v34, 4, *v36, *v35);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 8) != 0 )
          WPP_SF_II(*((_QWORD *)WPP_GLOBAL_Control + 2), v37, v38, *v36, *v35);
      }
      else
      {
        v35 = (_QWORD *)((char *)a2 + 24);
        v36 = (_QWORD *)((char *)a2 + 16);
      }
      if ( (unsigned __int8)((__int64 (*)(void))IsXerTransportEventUploadCompletePresent)() )
        XerTransportEventUploadProgress(*v36, *v35);
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
                                  WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
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
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 166, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
              }
              v17 = *((_DWORD *)this + 34);
              v45[0] = 0;
              LODWORD(v45[0]) = 24;
              DWORD2(v45[0]) = v17;
              CReportManager::ExternalCallbackUI((CReportManager *)this, (struct _WER_UI_CALLBACK_INPUT *)v45);
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
                  WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
                  *((_QWORD *)a2 + 2));
              *((_QWORD *)a3 + 2) = *((_QWORD *)a2 + 2);
              if ( (unsigned __int8)IsXerTransportEventUploadCompletePresent(v8) )
                XerTransportEventUploadStart(*((_QWORD *)a2 + 2));
              return WatsonCab;
            }
LABEL_121:
            if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids, v6);
            return WatsonCab;
          }
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            return WatsonCab;
          v20 = 165;
LABEL_62:
          WPP_SF_(*((_QWORD *)v19 + 2), v20, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
          return WatsonCab;
        }
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 161, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
        v21 = this[1];
        *((_DWORD *)this + 28) = *((_DWORD *)a2 + 4);
        if ( !(unsigned __int8)IsXerProgressCallbackPresent() )
        {
LABEL_81:
          SetEvent(*((HANDLE *)a3 + 1));
          (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], 5);
          v26 = (_WORD *)*((_QWORD *)v21 + 1);
          if ( v26 && *v26 || (v27 = (_WORD *)*((_QWORD *)v21 + 14)) != 0 && *v27 )
            *((_DWORD *)this + 30) = CReportManager::ExternalCallbackResponseReceived(
                                       (CReportManager *)this,
                                       (CReport *)((char *)v21 + 8));
          v28 = (_QWORD *)((char *)v21 + 368);
          if ( (_QWORD *)*v28 != v28 )
          {
            CReportManager::ExternalCallbackControlRequestBegin((CReportManager *)this);
            for ( i = (_QWORD *)*v28; i != v28; i = (_QWORD *)*i )
              CReportManager::ExternalCallbackControlRequest(
                (CReportManager *)this,
                (const wchar_t *)i[2],
                (const wchar_t *)i[6]);
            CReportManager::ExternalCallbackControlRequestEnd((CReportManager *)this);
          }
          return WatsonCab;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v45);
        UniqueIdentifier = CReport::GetUniqueIdentifier(this[1], v45);
        WatsonCab = UniqueIdentifier;
        if ( UniqueIdentifier < 0
          && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            162,
            WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
            (unsigned int)UniqueIdentifier);
        }
        v23 = this[1];
        memset(&v47.m256i_u64[1], 0, 24);
        v46 = *((unsigned __int64 *)v23 + 70);
        v47.m256i_i64[0] = *(_QWORD *)&v45[0];
        if ( CReportManager::IsXboxVmCrashDump((CReportManager *)this, &v46) )
        {
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_80;
          v25 = 163;
        }
        else
        {
          if ( !CReportManager::IsXboxGameCoreHeapDump((CReportManager *)this, &v46) )
            goto LABEL_80;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_80;
          v25 = 164;
        }
        WPP_SF_(*((_QWORD *)v24 + 2), v25, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
LABEL_80:
        v47.m256i_i32[5] = *((_DWORD *)this + 28);
        v47.m256i_i64[3] = *((_QWORD *)v21 + 32);
        v48 = v46;
        v49 = v47;
        XerTransportEventFinish(&v48);
        utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v45);
        goto LABEL_81;
      }
      CReportManager::ExternalCallbackUploadBegin((CReportManager *)this);
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 157, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
      if ( !(unsigned __int8)IsXerProgressCallbackPresent() )
        return WatsonCab;
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v45);
      v30 = *((_QWORD *)a2 + 2);
      v31 = CReport::GetUniqueIdentifier(v30, v45);
      WatsonCab = v31;
      if ( v31 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          158,
          WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
          (unsigned int)v31);
      *(_QWORD *)&v46 = *(_QWORD *)(v30 + 560);
      *((_QWORD *)&v46 + 1) = *(_QWORD *)a2;
      *(_OWORD *)v47.m256i_i8 = *(unsigned __int64 *)&v45[0];
      *(__int64 *)((char *)&v47.m256i_i64[2] + 1) = 0;
      *(__int32 *)((char *)&v47.m256i_i32[6] + 1) = 0;
      *(__int16 *)((char *)&v47.m256i_i16[14] + 1) = 0;
      v47.m256i_i8[31] = 0;
      v47.m256i_i8[16] = 0;
      if ( CReportManager::IsXboxVmCrashDump((CReportManager *)this, &v46) )
      {
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_108;
        v33 = 159;
      }
      else
      {
        if ( !CReportManager::IsXboxGameCoreHeapDump((CReportManager *)this, &v46) )
          goto LABEL_108;
        v32 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_108;
        v33 = 160;
      }
      WPP_SF_(*((_QWORD *)v32 + 2), v33, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
LABEL_108:
      v48 = v46;
      v49 = v47;
      XerTransportEventBegin(&v48);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v45);
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
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
          *((_DWORD *)this[1] + 1490) |= 0x800u;
          return WatsonCab;
        }
        if ( *((_DWORD *)this + 34) != 1 && *((_DWORD *)this[1] + 1468) != 4 )
        {
          *((_QWORD *)a2 + 2) = 0;
          return WatsonCab;
        }
        v42 = 1;
        if ( *((_DWORD *)this[1] + 1468) != 4 )
          v42 = 3;
        (*(void (__fastcall **)(CReport *, __int64))(*(_QWORD *)this[3] + 16LL))(this[3], v42);
        CReportManager::ExternalCallbackCabProgress((CReportManager *)this, 0, 0, v43);
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
        v39 = this[13];
        this[13] = 0;
        if ( v39 )
          utl::default_delete<CReportCabStream>::operator()();
        CReportManager::ExternalCallbackCabProgress((CReportManager *)this, 0, 0, v6);
        v40 = CReportManager::CreateWatsonCab((CReportManager *)this, *((_DWORD *)a2 + 6));
        WatsonCab = v40;
        if ( v40 < 0 )
        {
          if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              170,
              WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids,
              (unsigned int)v40);
          goto LABEL_151;
        }
        break;
      default:
        goto LABEL_121;
    }
    *((_QWORD *)a2 + 2) = this[13];
LABEL_151:
    CReportManager::ExternalCallbackCabProgress((CReportManager *)this, 1, 1u, v41);
    return WatsonCab;
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids);
  return 2147942487LL;
}

```

## disassembly

```asm
0x1800147b8  push    rbp
0x1800147ba  push    rbx
0x1800147bb  push    rsi
0x1800147bc  push    rdi
0x1800147bd  push    r12
0x1800147bf  push    r13
0x1800147c1  push    r14
0x1800147c3  push    r15
0x1800147c5  lea     rbp, [rsp-1Fh]
0x1800147ca  sub     rsp, 0B8h
0x1800147d1  xor     r12d, r12d
0x1800147d4  mov     r13, r8
0x1800147d7  mov     rsi, rdx
0x1800147da  mov     rdi, rcx
0x1800147dd  test    rdx, rdx
0x1800147e0  jnz     short loc_1800147E7
0x1800147e2  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800147e7  test    r13, r13
0x1800147ea  jnz     short loc_1800147F1
0x1800147ec  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800147f1  test    rsi, rsi
0x1800147f4  jz      loc_18001518B
0x1800147fa  test    r13, r13
0x1800147fd  jz      loc_18001518B
0x180014803  mov     r9d, [rsi+8]
0x180014807  mov     r15d, r12d
0x18001480a  cmp     r9d, 5
0x18001480e  jz      loc_180014EC8
0x180014814  jg      loc_180014F46
0x18001481a  mov     ecx, r9d
0x18001481d  test    r9d, r9d
0x180014820  jz      loc_180014D78
0x180014826  sub     ecx, 1
0x180014829  jz      loc_180014B9E
0x18001482f  sub     ecx, 1
0x180014832  jz      loc_180014B63
0x180014838  sub     ecx, 1
0x18001483b  jz      loc_1800148C3
0x180014841  cmp     ecx, 1
0x180014844  jnz     loc_180014F72
0x18001484a  mov     rax, [rdi+8]
0x18001484e  mov     edx, 4
0x180014853  mov     dword ptr [rax+19E0h], 6
0x18001485d  mov     rcx, [rdi+18h]
0x180014861  mov     rax, [rcx]
0x180014864  mov     rax, [rax+10h]
0x180014868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001486d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014874  lea     rbx, WPP_GLOBAL_Control
0x18001487b  cmp     rcx, rbx
0x18001487e  jz      short loc_18001489F
0x180014880  test    byte ptr [rcx+1Ch], 4
0x180014884  jz      short loc_18001489F
0x180014886  mov     r9, [rsi+10h]
0x18001488a  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180014891  mov     rcx, [rcx+10h]
0x180014895  mov     edx, 0A8h
0x18001489a  call    WPP_SF_q
0x18001489f  mov     rax, [rsi+10h]
0x1800148a3  mov     [r13+10h], rax
0x1800148a7  call    IsXerTransportEventUploadCompletePresent
0x1800148ac  test    al, al
0x1800148ae  jz      loc_180015186
0x1800148b4  mov     rcx, [rsi+10h]
0x1800148b8  call    cs:__imp_XerTransportEventUploadStart
0x1800148be  jmp     loc_180015186
0x1800148c3  mov     rcx, [rdi+8]; this
0x1800148c7  call    ?IsSecondaryDataEnabled@CReport@@QEBAHXZ; CReport::IsSecondaryDataEnabled(void)
0x1800148cc  test    eax, eax
0x1800148ce  jnz     short loc_18001490B
0x1800148d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148d7  lea     rbx, WPP_GLOBAL_Control
0x1800148de  cmp     rcx, rbx
0x1800148e1  jz      loc_180014B05
0x1800148e7  test    byte ptr [rcx+1Ch], 4
0x1800148eb  jz      loc_180014B05
0x1800148f1  mov     rcx, [rcx+10h]
0x1800148f5  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x1800148fc  mov     edx, 0A6h
0x180014901  call    WPP_SF_
0x180014906  jmp     loc_180014B05
0x18001490b  mov     rcx, [rdi+18h]
0x18001490f  mov     edx, 2
0x180014914  mov     rax, [rcx]
0x180014917  mov     rax, [rax+10h]
0x18001491b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014920  call    cs:__imp_GetTickCount
0x180014926  mov     rcx, rdi; this
0x180014929  call    ?AddTracingFile@CReportManager@@AEAAJXZ; CReportManager::AddTracingFile(void)
0x18001492e  mov     rcx, [rdi+8]; this
0x180014932  mov     edx, r12d
0x180014935  mov     r14d, 3
0x18001493b  mov     ebx, [rcx+0CA4Ch]
0x180014941  cmp     ebx, r14d
0x180014944  setnz   dl; int
0x180014947  call    ?IsSecondLevelDataThrottled@CReport@@QEAAHH@Z; CReport::IsSecondLevelDataThrottled(int)
0x18001494c  test    eax, eax
0x18001494e  jz      short loc_180014960
0x180014950  mov     [rdi+88h], r12d
0x180014957  mov     [rsi+18h], r14d
0x18001495b  jmp     loc_180014B05
0x180014960  mov     rdx, [rsi+10h]; struct CDataRequest *
0x180014964  mov     rcx, rdi; this
0x180014967  call    ?AddSecondLevelData@CReportManager@@AEAAJPEBVCDataRequest@@@Z; CReportManager::AddSecondLevelData(CDataRequest const *)
0x18001496c  mov     r15d, eax
0x18001496f  test    eax, eax
0x180014971  js      loc_180014B05
0x180014977  mov     rcx, [rdi+8]; this
0x18001497b  cmp     ebx, r14d
0x18001497e  mov     r8d, r12d
0x180014981  mov     eax, 1000000h
0x180014986  mov     ebx, 10000h
0x18001498b  cmovz   r8d, eax; unsigned int
0x18001498f  mov     edx, ebx; unsigned int
0x180014991  call    ?GetNumFilesByFlags@CReport@@QEAAKKK@Z; CReport::GetNumFilesByFlags(ulong,ulong)
0x180014996  test    eax, eax
0x180014998  jz      loc_180014B05
0x18001499e  mov     rcx, rdi; this
0x1800149a1  call    ?CalcDefaultSecondLevelPromptResult@CReportManager@@AEAAHXZ; CReportManager::CalcDefaultSecondLevelPromptResult(void)
0x1800149a6  test    eax, eax
0x1800149a8  jnz     short loc_1800149C0
0x1800149aa  mov     rcx, [rdi+18h]
0x1800149ae  mov     rax, [rcx]
0x1800149b1  mov     rax, [rax+20h]
0x1800149b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149ba  mov     [rdi+88h], eax
0x1800149c0  cmp     dword ptr [rdi+88h], 1
0x1800149c7  jnz     short loc_1800149F2
0x1800149c9  mov     rcx, [rdi+8]; this
0x1800149cd  call    ?GetUploadShouldBypassPowerThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassPowerThrottling(void)
0x1800149d2  test    eax, eax
0x1800149d4  jnz     short loc_1800149F2
0x1800149d6  call    WerpIsOnBattery
0x1800149db  test    eax, eax
0x1800149dd  jz      short loc_1800149F2
0x1800149df  mov     rax, [rdi+8]
0x1800149e3  mov     [rdi+88h], r14d
0x1800149ea  bts     dword ptr [rax+1748h], 0Eh
0x1800149f2  cmp     dword ptr [rdi+88h], 1
0x1800149f9  mov     r13d, 8000h
0x1800149ff  jnz     loc_180014AE6
0x180014a05  mov     rcx, [rdi+8]; this
0x180014a09  call    ?GetUploadShouldBypassNetworkCostThrottling@CReport@@QEBAHXZ; CReport::GetUploadShouldBypassNetworkCostThrottling(void)
0x180014a0e  test    eax, eax
0x180014a10  jnz     short loc_180014A2D
0x180014a12  call    ?UtilIsNetworkRestricted@@YAHXZ; UtilIsNetworkRestricted(void)
0x180014a17  test    eax, eax
0x180014a19  jz      short loc_180014A2D
0x180014a1b  mov     rax, [rdi+8]
0x180014a1f  mov     [rdi+88h], r14d
0x180014a26  or      [rax+1748h], r13d
0x180014a2d  cmp     dword ptr [rdi+88h], 1
0x180014a34  jnz     loc_180014AE6
0x180014a3a  mov     rcx, [rdi+8]; this
0x180014a3e  call    ?ContainsConfidentialFiles@CReport@@QEAAHXZ; CReport::ContainsConfidentialFiles(void)
0x180014a43  test    eax, eax
0x180014a45  jz      short loc_180014A58
0x180014a47  mov     rax, [rdi+8]
0x180014a4b  mov     [rdi+88h], r14d
0x180014a52  or      [rax+1748h], ebx
0x180014a58  cmp     dword ptr [rdi+88h], 1
0x180014a5f  jnz     loc_180014AE6
0x180014a65  mov     rcx, [rdi+8]
0x180014a69  add     rcx, 0C9E0h; this
0x180014a70  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180014a75  test    eax, eax
0x180014a77  jz      short loc_180014AB9
0x180014a79  mov     [rdi+88h], r14d
0x180014a80  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a87  lea     rbx, WPP_GLOBAL_Control
0x180014a8e  cmp     rcx, rbx
0x180014a91  jz      short loc_180014AAE
0x180014a93  test    byte ptr [rcx+1Ch], 4
0x180014a97  jz      short loc_180014AAE
0x180014a99  mov     rcx, [rcx+10h]
0x180014a9d  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180014aa4  mov     edx, 0A7h
0x180014aa9  call    WPP_SF_
0x180014aae  mov     rax, [rdi+8]
0x180014ab2  or      [rax+1748h], r13d
0x180014ab9  cmp     dword ptr [rdi+88h], 1
0x180014ac0  jnz     short loc_180014AE6
0x180014ac2  mov     edx, 1
0x180014ac7  mov     rcx, rdi
0x180014aca  call    ?ExternalCallbackSecondLevelResponse@CReportManager@@AEAAHW4SECONDLEVEL_SELECTION@@@Z; CReportManager::ExternalCallbackSecondLevelResponse(SECONDLEVEL_SELECTION)
0x180014acf  test    eax, eax
0x180014ad1  jz      short loc_180014AE6
0x180014ad3  mov     rax, [rdi+8]
0x180014ad7  mov     [rdi+88h], r14d
0x180014ade  bts     dword ptr [rax+1748h], 17h
0x180014ae6  mov     ecx, [rdi+88h]
0x180014aec  cmp     ecx, 1
0x180014aef  jnz     short loc_180014AF7
0x180014af1  mov     [rsi+18h], r12d
0x180014af5  jmp     short loc_180014B05
0x180014af7  cmp     ecx, r14d
0x180014afa  mov     eax, r12d
0x180014afd  setnz   al
0x180014b00  inc     eax
0x180014b02  mov     [rsi+18h], eax
0x180014b05  mov     eax, [rdi+88h]
0x180014b0b  lea     rdx, [rbp+57h+var_C0]; struct _WER_UI_CALLBACK_INPUT *
0x180014b0f  xorps   xmm0, xmm0
0x180014b12  mov     rcx, rdi; this
0x180014b15  movdqa  [rbp+57h+var_C0], xmm0
0x180014b1a  mov     dword ptr [rbp+57h+var_C0], 18h
0x180014b21  mov     dword ptr [rbp+57h+var_C0+8], eax
0x180014b24  call    ?ExternalCallbackUI@CReportManager@@QEAAHPEAU_WER_UI_CALLBACK_INPUT@@@Z; CReportManager::ExternalCallbackUI(_WER_UI_CALLBACK_INPUT *)
0x180014b29  cmp     dword ptr [rdi+0A4h], 7
0x180014b30  jz      loc_180015186
0x180014b36  mov     rax, [rdi+8]
0x180014b3a  mov     ebx, [rax+19D8h]
0x180014b40  test    bl, 1
0x180014b43  jz      short loc_180014B4D
0x180014b45  mov     rcx, rdi; this
0x180014b48  call    ?ExternalCallbackDocRecoveryNotification@CReportManager@@AEAAHXZ; CReportManager::ExternalCallbackDocRecoveryNotification(void)
0x180014b4d  test    bl, 2
0x180014b50  jz      loc_180015186
0x180014b56  mov     rcx, rdi; this
0x180014b59  call    ?ExternalCallbackRestartNotification@CReportManager@@AEAAHXZ; CReportManager::ExternalCallbackRestartNotification(void)
0x180014b5e  jmp     loc_180015186
0x180014b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b6a  lea     rbx, WPP_GLOBAL_Control
0x180014b71  cmp     rcx, rbx
0x180014b74  jz      loc_180015186
0x180014b7a  test    byte ptr [rcx+1Ch], 4
0x180014b7e  jz      loc_180015186
0x180014b84  mov     edx, 0A5h
0x180014b89  mov     rcx, [rcx+10h]
0x180014b8d  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180014b94  call    WPP_SF_
0x180014b99  jmp     loc_180015186
0x180014b9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ba5  lea     rbx, WPP_GLOBAL_Control
0x180014bac  cmp     rcx, rbx
0x180014baf  jz      short loc_180014BCC
0x180014bb1  test    byte ptr [rcx+1Ch], 4
0x180014bb5  jz      short loc_180014BCC
0x180014bb7  mov     rcx, [rcx+10h]
0x180014bbb  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180014bc2  mov     edx, 0A1h
0x180014bc7  call    WPP_SF_
0x180014bcc  mov     eax, [rsi+10h]
0x180014bcf  mov     r14, [rdi+8]
0x180014bd3  mov     [rdi+70h], eax
0x180014bd6  call    IsXerProgressCallbackPresent
0x180014bdb  test    al, al
0x180014bdd  jz      loc_180014CED
0x180014be3  lea     rcx, [rbp+57h+var_C0]; void *
0x180014be7  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180014bec  mov     rcx, [rdi+8]
0x180014bf0  lea     rdx, [rbp+57h+var_C0]
0x180014bf4  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180014bf9  mov     r15d, eax
0x180014bfc  test    eax, eax
0x180014bfe  jns     short loc_180014C2A
0x180014c00  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c07  cmp     rcx, rbx
0x180014c0a  jz      short loc_180014C2A
0x180014c0c  test    byte ptr [rcx+1Ch], 1
0x180014c10  jz      short loc_180014C2A
0x180014c12  mov     rcx, [rcx+10h]
0x180014c16  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
0x180014c1d  mov     edx, 0A2h
0x180014c22  mov     r9d, eax
0x180014c25  call    WPP_SF_d
0x180014c2a  mov     rax, [rdi+8]
0x180014c2e  lea     rdx, [rbp+57h+var_A0]; void *
0x180014c32  xorps   xmm0, xmm0
0x180014c35  mov     qword ptr [rbp+57h+var_A0+8], r12
0x180014c39  movdqu  [rbp+57h+var_90+8], xmm0
0x180014c3e  mov     qword ptr [rbp+57h+var_80+8], r12
0x180014c42  mov     rcx, [rax+230h]
0x180014c49  mov     rax, qword ptr [rbp+57h+var_C0]
0x180014c4d  mov     qword ptr [rbp+57h+var_A0], rcx
0x180014c51  mov     rcx, rdi; this
0x180014c54  mov     qword ptr [rbp+57h+var_90], rax
0x180014c58  call    ?IsXboxVmCrashDump@CReportManager@@QEAAEPEAX@Z; CReportManager::IsXboxVmCrashDump(void *)
0x180014c5d  test    al, al
0x180014c5f  jz      short loc_180014C7A
0x180014c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c68  cmp     rcx, rbx
0x180014c6b  jz      short loc_180014CB1
0x180014c6d  test    byte ptr [rcx+1Ch], 4
0x180014c71  jz      short loc_180014CB1
0x180014c73  mov     edx, 0A3h
0x180014c78  jmp     short loc_180014CA1
0x180014c7a  lea     rdx, [rbp+57h+var_A0]; void *
0x180014c7e  mov     rcx, rdi; this
0x180014c81  call    ?IsXboxGameCoreHeapDump@CReportManager@@QEAAEPEAX@Z; CReportManager::IsXboxGameCoreHeapDump(void *)
0x180014c86  test    al, al
0x180014c88  jz      short loc_180014CB1
0x180014c8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180014c91  cmp     rcx, rbx
0x180014c94  jz      short loc_180014CB1
0x180014c96  test    byte ptr [rcx+1Ch], 4
0x180014c9a  jz      short loc_180014CB1
0x180014c9c  mov     edx, 0A4h
0x180014ca1  mov     rcx, [rcx+10h]
0x180014ca5  lea     r8, WPP_ae7d35e1850534237c3139c45f11bc05_Traceguids
  ... truncated ...
```
