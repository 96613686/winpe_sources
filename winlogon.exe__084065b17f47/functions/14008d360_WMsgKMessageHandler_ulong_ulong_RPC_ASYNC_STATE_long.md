# WMsgKMessageHandler(ulong,ulong,_RPC_ASYNC_STATE *,long *)

- ea: `0x14008d360`
- end: `0x14008e0db`
- name: `?WMsgKMessageHandler@@YAHKKPEAU_RPC_ASYNC_STATE@@PEAJ@Z`
- size: `3451`
- prototype: `__int64 __fastcall(unsigned int, unsigned int, struct _RPC_ASYNC_STATE *, int *)`
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400057f4`
- `0x140005840`
- `0x140016f30`
- `0x14002ba10`
- `0x14002bc20`
- `0x140030590`
- `0x1400333b0`
- `0x140037b00`
- `0x14003b254`
- `0x14003c318`
- `0x14003f818`
- `0x140041c34`
- `0x140043504`
- `0x14004b708`
- `0x14004ec2c`
- `0x14004effc`
- `0x140056bd8`
- `0x140059380`
- `0x140083ee0`
- `0x140084044`
- `0x14008d360`
- `0x14008e0f0`
- `0x14008ed54`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008d871`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008d871`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x14008e0a7`
- `ext-ms-win-ntuser-private-l1-1-1!LockWindowStation` at `0x14008e0a7`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x14008e096`
- `ext-ms-win-ntuser-private-l1-1-1!UnlockWindowStation` at `0x14008e096`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x14008db33`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x14008dd27`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x14008de70`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x14008db33`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x14008dd27`
- `ext-ms-win-composition-init-l1-1-0!DwmpCreateSessionProcess` at `0x14008de70`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x14008dac3`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x14008dfcf`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x14008dac3`
- `ext-ms-win-composition-init-l1-1-0!DwmpTerminateSessionProcess` at `0x14008dfcf`

## string_xrefs

- `0x14008dd19`: `DwmpCreateSessionProcess`
- `0x14008dd36`: `DwmpCreateSessionProcess`
- `0x14008de62`: `DwmpCreateSessionProcess`
- `0x14008de7f`: `DwmpCreateSessionProcess`

## pseudocode

```c
__int64 __fastcall WMsgKMessageHandler(unsigned int a1, unsigned int a2, struct _RPC_ASYNC_STATE *a3, int *a4)
{
  unsigned __int64 v5; // rbx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  struct _StateMachineSignalData *v10; // rdx
  unsigned int v11; // edx
  CSession *v12; // rcx
  __int64 v13; // r9
  unsigned int v14; // edi
  CUser *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  __int64 v19; // r9
  CUser *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  CUser *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // r9
  const struct _EVENT_DESCRIPTOR *v27; // rcx
  __int64 v28; // r9
  int v29; // esi
  __int64 v30; // r9
  int v31; // ebx
  __int64 v32; // r9
  int v33; // ebx
  __int128 v34; // [rsp+30h] [rbp-20h] BYREF
  __int64 v35; // [rsp+40h] [rbp-10h]
  int v36; // [rsp+90h] [rbp+40h] BYREF
  int SessionProcess; // [rsp+A8h] [rbp+58h] BYREF

  v5 = a2;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_llq(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, a3, a1, a2, a3);
  }
  v8 = 1029;
  *a4 = 0;
  if ( a1 <= 0x405 )
  {
    if ( a1 != 1029 )
    {
      if ( a1 != 1 )
      {
        switch ( a1 )
        {
          case 0x100u:
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
            }
            *a4 = 0;
            return 1;
          case 0x400u:
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                71,
                WPP_9372b429430230a2303f99774b8cd740_Traceguids,
                (unsigned int)v5);
            }
            if ( ((*((_DWORD *)qword_1400D2550 + 37) - 1) & 0xFFFFFFFD) != 0
              && (!(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
               || *((_DWORD *)qword_1400D2550 + 37) != 4) )
            {
              v14 = 2;
              if ( (unsigned int)CSession::IsBoundToConsole(qword_1400D2550) )
                v14 = v5;
              if ( v14 == 3 )
              {
                if ( !(unsigned int)IsLockScreenSlideshowAutoLockDisabled((struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext)
                  && qword_1400D2560 )
                {
                  WMsgDisplayOffHandler(1);
                }
              }
              else
              {
                WlInactivityTimeoutHandler((struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext, v14);
              }
            }
            return 1;
          case 0x401u:
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                72,
                WPP_9372b429430230a2303f99774b8cd740_Traceguids,
                (unsigned int)v5);
            }
            if ( (unsigned int)AsyncLogoffSupportIsLogoffInProgress() )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v13);
              }
            }
            else if ( (unsigned int)CSession::IsShellRequiredInSession(v12) )
            {
              RecordBlackboxInfo(L"ShellRestart", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
              WlStateMachineSetSignal(0xAu, 0);
            }
            else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                73,
                WPP_9372b429430230a2303f99774b8cd740_Traceguids,
                *((unsigned int *)qword_1400D2550 + 22));
            }
            if ( (_DWORD)v5 )
              CloseHandle((HANDLE)v5);
            return 1;
          case 0x402u:
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 69, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
            }
            v11 = v5;
            goto LABEL_40;
        }
        if ( a1 != 1027 )
        {
          if ( a1 == 1028 )
          {
            switch ( (_DWORD)v5 )
            {
              case 4:
                v34 = 0;
                v35 = 0;
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                *((_QWORD *)&v34 + 1) = 0x200000000LL;
                v9 = 44;
                goto LABEL_20;
              case 5:
                v34 = 0;
                v35 = 0;
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                WLEventWrite(&WLEvt_HotKeyLockDesktopInvoked_Info);
                v9 = 13;
                DWORD2(v34) = 1;
                goto LABEL_20;
              case 0xF:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                CTraceCollector::HandleTraceCollectorHotKey(qword_1400D2558, &xGlobalContext);
                return 1;
              case 6:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -1;
                break;
              case 7:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -3;
                break;
              case 8:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -4;
                break;
              case 9:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -5;
                break;
              case 0xB:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -7;
                break;
              case 0:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                if ( (unsigned int)(*((_DWORD *)qword_1400D2550 + 37) - 1) <= 2
                  || (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl'::`2'::impl)
                  && *((_DWORD *)qword_1400D2550 + 37) == 4 )
                {
                  return 1;
                }
                v10 = 0;
                v9 = 3;
                goto LABEL_21;
              case 0xC:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -8;
                break;
              case 0xD:
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 67, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                v11 = -9;
                break;
              default:
                if ( (_DWORD)v5 == 14
                  && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
                }
                return 1;
            }
LABEL_40:
            WlAccessibilityOnWin32KMessage((struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext, v11);
            return 1;
          }
          goto LABEL_141;
        }
      }
      v8 = a1;
    }
    return WMsgMessageHandler(v8, v5, a3, a4);
  }
  switch ( a1 )
  {
    case 0x407u:
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_9372b429430230a2303f99774b8cd740_Traceguids, a4);
      }
      UnlockWindowStation(*((_QWORD *)qword_1400D2550 + 12));
      LockWindowStation(*((_QWORD *)qword_1400D2550 + 12));
      WlAccessibilityOnDesktopSwitch((struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext, 1);
      return 1;
    case 0x409u:
      LaunchUmfdHostWithVirtualAccount();
      return 1;
    case 0x40Au:
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          75,
          WPP_9372b429430230a2303f99774b8cd740_Traceguids,
          (unsigned int)v5);
      }
      if ( (unsigned int)CSession::IsDwmRequiredInSession(qword_1400D2550) )
      {
        if ( !qword_1400D30C8 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v32);
          }
          if ( !(unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
            return 1;
          WLEventWrite(&WLEvt_DwmpTerminateSessionProcess_Start);
          RecordBlackboxInfo(L"DwmpTerminateSessionProcess", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
          v36 = DwmpTerminateSessionProcess(1);
          v33 = v36;
          RecordBlackboxInfo(L"DwmpTerminateSessionProcess", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
          if ( v33 < 0
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              78,
              WPP_9372b429430230a2303f99774b8cd740_Traceguids,
              (unsigned int)v33);
          }
          WinlogonProvider::DwmpTerminateSessionProcess<long &>(&v36);
          v27 = &WLEvt_DwmpTerminateSessionProcess_Stop;
          goto LABEL_176;
        }
        DWORD2(v34) = 0;
LABEL_259:
        HIDWORD(v34) = 1;
        goto LABEL_260;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 1;
      }
      v21 = 76;
      goto LABEL_245;
    case 0x40Bu:
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          WPP_9372b429430230a2303f99774b8cd740_Traceguids,
          (unsigned int)v5);
      }
      if ( (unsigned int)CSession::IsDwmRequiredInSession(qword_1400D2550) )
      {
        if ( !qword_1400D30C8 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v30);
          }
          if ( !(unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
            return 1;
          WLEventWrite(&WLEvt_DwmpCreateSessionProcess_Start);
          RecordBlackboxInfo(L"DwmpCreateSessionProcess", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
          SessionProcess = DwmpCreateSessionProcess(0);
          v31 = SessionProcess;
          RecordBlackboxInfo(L"DwmpCreateSessionProcess", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
          if ( v31 >= 0 )
            goto LABEL_174;
          v24 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_174;
          }
          v25 = 82;
          v26 = (unsigned int)v31;
LABEL_173:
          WPP_SF_d(*((_QWORD *)v24 + 2), v25, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v26);
LABEL_174:
          LOBYTE(v36) = 0;
LABEL_175:
          WinlogonProvider::DwmpCreateSessionProcess<bool,long &>(&v36, &SessionProcess);
          v27 = &WLEvt_DwmpCreateSessionProcess_Stop;
LABEL_176:
          WLEventWrite(v27);
          return 1;
        }
        *((_QWORD *)&v34 + 1) = 1;
        goto LABEL_260;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 1;
      }
      v21 = 80;
LABEL_245:
      WPP_SF_d(
        *((_QWORD *)v20 + 2),
        v21,
        WPP_9372b429430230a2303f99774b8cd740_Traceguids,
        *((unsigned int *)qword_1400D2550 + 22));
      return 1;
    case 0x40Cu:
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          83,
          WPP_9372b429430230a2303f99774b8cd740_Traceguids,
          (unsigned int)v5);
      }
      if ( (unsigned int)CSession::IsDwmRequiredInSession(qword_1400D2550) )
      {
        if ( !qword_1400D30C8 )
        {
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v28);
          }
          if ( !(unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
            return 1;
          WLEventWrite(&WLEvt_DwmpCreateSessionProcess_Start);
          RecordBlackboxInfo(L"DwmpCreateSessionProcess", 1, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
          SessionProcess = DwmpCreateSessionProcess((unsigned int)v5);
          v29 = SessionProcess;
          RecordBlackboxInfo(L"DwmpCreateSessionProcess", 0, (struct _WLSM_GLOBAL_CONTEXT *)&xGlobalContext);
          if ( v29 < 0
            && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              86,
              WPP_9372b429430230a2303f99774b8cd740_Traceguids,
              (unsigned int)v29);
          }
          LOBYTE(v36) = (_DWORD)v5 != 0;
          goto LABEL_175;
        }
        DWORD2(v34) = 1;
        HIDWORD(v34) = v5;
        goto LABEL_260;
      }
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 1;
      }
      v21 = 84;
      goto LABEL_245;
  }
  if ( a1 != 1037 )
  {
    if ( a1 != 1038 )
    {
LABEL_141:
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      {
        return 1;
      }
      v17 = 96;
      v18 = a1;
      goto LABEL_145;
    }
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        WPP_9372b429430230a2303f99774b8cd740_Traceguids,
        (unsigned int)v5);
    }
    if ( !(unsigned int)CSession::IsDwmRequiredInSession(qword_1400D2550) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
        return 1;
      }
      v21 = 92;
      goto LABEL_245;
    }
    if ( !qword_1400D30C8 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v19);
      }
      if ( (unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
      {
        WLEventWrite(&WLEvt_DwmpTerminateSessionProcess_Start);
        v22 = DwmpTerminateSessionProcess(1);
        v36 = v22;
        if ( v22 < 0
          && WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            94,
            WPP_9372b429430230a2303f99774b8cd740_Traceguids,
            (unsigned int)v22);
        }
        WinlogonProvider::DwmpTerminateSessionProcess<long &>(&v36);
        WLEventWrite(&WLEvt_DwmpTerminateSessionProcess_Stop);
      }
      if ( !(unsigned __int8)IsDwmpStartWinlogonMouseThreadPresent() )
        return 1;
      WLEventWrite(&WLEvt_DwmpCreateSessionProcess_Start);
      v23 = DwmpCreateSessionProcess(0);
      SessionProcess = v23;
      if ( v23 >= 0 )
        goto LABEL_174;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_174;
      }
      v25 = 95;
      v26 = (unsigned int)v23;
      goto LABEL_173;
    }
    DWORD2(v34) = 3;
    goto LABEL_259;
  }
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 87, WPP_9372b429430230a2303f99774b8cd740_Traceguids, (unsigned int)v5);
  }
  if ( !(unsigned int)CSession::IsDwmRequiredInSession(qword_1400D2550) )
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      return 1;
    }
    v21 = 88;
    goto LABEL_245;
  }
  if ( !qword_1400D30C8 )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      return 1;
    }
    v17 = 89;
    v18 = (unsigned int)v5;
LABEL_145:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_9372b429430230a2303f99774b8cd740_Traceguids, v18);
    return 1;
  }
  *((_QWORD *)&v34 + 1) = 2;
LABEL_260:
  *(_QWORD *)&v34 = 0;
  v9 = 11;
  v35 = 0;
LABEL_20:
  v10 = (struct _StateMachineSignalData *)&v34;
LABEL_21:
  WlStateMachineSetSignal(v9, v10);
  return 1;
}

```

## disassembly

```asm
0x14008d360  mov     [rsp-38h+arg_8], rbx
0x14008d365  push    rbp
0x14008d366  push    rsi
0x14008d367  push    rdi
0x14008d368  push    r12
0x14008d36a  push    r13
0x14008d36c  push    r14
0x14008d36e  push    r15
0x14008d370  mov     rbp, rsp
0x14008d373  sub     rsp, 50h
0x14008d377  mov     rdi, r9
0x14008d37a  mov     ebx, edx
0x14008d37c  mov     r14, r8
0x14008d37f  mov     esi, ecx
0x14008d381  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d388  lea     r12, WPP_GLOBAL_Control
0x14008d38f  mov     edx, 5
0x14008d394  lea     r13d, [rdx+3Bh]
0x14008d398  cmp     rcx, r12
0x14008d39b  jz      short loc_14008D3C5
0x14008d39d  test    [rcx+1Ch], r13b
0x14008d3a1  jz      short loc_14008D3C5
0x14008d3a3  cmp     [rcx+19h], dl
0x14008d3a6  jb      short loc_14008D3C5
0x14008d3a8  mov     rcx, [rcx+10h]
0x14008d3ac  lea     edx, [r13-0Bh]
0x14008d3b0  mov     [rsp+50h+var_28], r8
0x14008d3b5  mov     r9d, esi
0x14008d3b8  mov     [rsp+50h+var_30], ebx
0x14008d3bc  call    WPP_SF_llq
0x14008d3c1  lea     edx, [r13-3Bh]
0x14008d3c5  xor     r15d, r15d
0x14008d3c8  mov     ecx, 405h
0x14008d3cd  mov     [rdi], r15d
0x14008d3d0  cmp     esi, ecx
0x14008d3d2  ja      loc_14008D980
0x14008d3d8  jz      loc_14008D96E
0x14008d3de  mov     eax, esi
0x14008d3e0  sub     eax, 1
0x14008d3e3  jz      loc_14008D96C
0x14008d3e9  sub     eax, 0FFh
0x14008d3ee  jz      loc_14008D938
0x14008d3f4  sub     eax, 300h
0x14008d3f9  jz      loc_14008D87C
0x14008d3ff  sub     eax, 1
0x14008d402  jz      loc_14008D79A
0x14008d408  sub     eax, 1
0x14008d40b  jz      loc_14008D767
0x14008d411  sub     eax, 1
0x14008d414  jz      loc_14008D96C
0x14008d41a  cmp     eax, 1
0x14008d41d  jnz     loc_14008D9C3
0x14008d423  cmp     ebx, 4
0x14008d426  jnz     short loc_14008D47C
0x14008d428  xorps   xmm0, xmm0
0x14008d42b  xor     eax, eax
0x14008d42d  movups  [rbp+var_20], xmm0
0x14008d431  mov     [rbp+var_10], rax
0x14008d435  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d43c  cmp     rcx, r12
0x14008d43f  jz      short loc_14008D45F
0x14008d441  test    [rcx+1Ch], r13b
0x14008d445  jz      short loc_14008D45F
0x14008d447  cmp     [rcx+19h], dl
0x14008d44a  jb      short loc_14008D45F
0x14008d44c  mov     rcx, [rcx+10h]
0x14008d450  lea     edx, [rbx+35h]
0x14008d453  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d45a  call    WPP_SF_
0x14008d45f  mov     edi, 2
0x14008d464  mov     dword ptr [rbp+var_20+8], r15d
0x14008d468  mov     dword ptr [rbp+var_20+0Ch], edi
0x14008d46b  lea     ecx, [rdi+2Ah]; unsigned int
0x14008d46e  lea     rdx, [rbp+var_20]; struct _StateMachineSignalData *
0x14008d472  call    ?WlStateMachineSetSignal@@YAKKPEAU_StateMachineSignalData@@@Z; WlStateMachineSetSignal(ulong,_StateMachineSignalData *)
0x14008d477  jmp     loc_14008E0BE
0x14008d47c  cmp     ebx, edx
0x14008d47e  jnz     short loc_14008D4D1
0x14008d480  xorps   xmm0, xmm0
0x14008d483  xor     eax, eax
0x14008d485  movups  [rbp+var_20], xmm0
0x14008d489  mov     [rbp+var_10], rax
0x14008d48d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d494  cmp     rcx, r12
0x14008d497  jz      short loc_14008D4B7
0x14008d499  test    [rcx+1Ch], r13b
0x14008d49d  jz      short loc_14008D4B7
0x14008d49f  cmp     [rcx+19h], dl
0x14008d4a2  jb      short loc_14008D4B7
0x14008d4a4  mov     rcx, [rcx+10h]
0x14008d4a8  lea     edx, [rax+3Ah]
0x14008d4ab  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d4b2  call    WPP_SF_
0x14008d4b7  lea     rcx, WLEvt_HotKeyLockDesktopInvoked_Info; struct _EVENT_DESCRIPTOR *
0x14008d4be  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x14008d4c3  mov     ecx, 0Dh
0x14008d4c8  mov     dword ptr [rbp+var_20+8], 1
0x14008d4cf  jmp     short loc_14008D46E
0x14008d4d1  cmp     ebx, 0Fh
0x14008d4d4  jnz     short loc_14008D518
0x14008d4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d4dd  cmp     rcx, r12
0x14008d4e0  jz      short loc_14008D500
0x14008d4e2  test    [rcx+1Ch], r13b
0x14008d4e6  jz      short loc_14008D500
0x14008d4e8  cmp     [rcx+19h], dl
0x14008d4eb  jb      short loc_14008D500
0x14008d4ed  mov     rcx, [rcx+10h]
0x14008d4f1  lea     edx, [rbx+2Ch]
0x14008d4f4  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d4fb  call    WPP_SF_
0x14008d500  mov     rcx, cs:qword_1400D2558; this
0x14008d507  lea     rdx, ?xGlobalContext@@3U_WLSM_GLOBAL_CONTEXT@@A; void *
0x14008d50e  call    ?HandleTraceCollectorHotKey@CTraceCollector@@QEAAXPEAX@Z; CTraceCollector::HandleTraceCollectorHotKey(void *)
0x14008d513  jmp     loc_14008E0BE
0x14008d518  cmp     ebx, 6
0x14008d51b  jnz     short loc_14008D55B
0x14008d51d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d524  cmp     rcx, r12
0x14008d527  jz      short loc_14008D547
0x14008d529  test    [rcx+1Ch], r13b
0x14008d52d  jz      short loc_14008D547
0x14008d52f  cmp     [rcx+19h], dl
0x14008d532  jb      short loc_14008D547
0x14008d534  mov     rcx, [rcx+10h]
0x14008d538  lea     edx, [rbx+36h]
0x14008d53b  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d542  call    WPP_SF_
0x14008d547  or      edx, 0FFFFFFFFh; unsigned int
0x14008d54a  lea     rcx, ?xGlobalContext@@3U_WLSM_GLOBAL_CONTEXT@@A; struct _WLSM_GLOBAL_CONTEXT *
0x14008d551  call    ?WlAccessibilityOnWin32KMessage@@YAHPEAU_WLSM_GLOBAL_CONTEXT@@K@Z; WlAccessibilityOnWin32KMessage(_WLSM_GLOBAL_CONTEXT *,ulong)
0x14008d556  jmp     loc_14008E0BE
0x14008d55b  cmp     ebx, 7
0x14008d55e  jnz     short loc_14008D591
0x14008d560  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d567  cmp     rcx, r12
0x14008d56a  jz      short loc_14008D58A
0x14008d56c  test    [rcx+1Ch], r13b
0x14008d570  jz      short loc_14008D58A
0x14008d572  cmp     [rcx+19h], dl
0x14008d575  jb      short loc_14008D58A
0x14008d577  mov     rcx, [rcx+10h]
0x14008d57b  lea     edx, [rbx+36h]
0x14008d57e  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d585  call    WPP_SF_
0x14008d58a  mov     edx, 0FFFFFFFDh
0x14008d58f  jmp     short loc_14008D54A
0x14008d591  cmp     ebx, 8
0x14008d594  jnz     short loc_14008D5C7
0x14008d596  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d59d  cmp     rcx, r12
0x14008d5a0  jz      short loc_14008D5C0
0x14008d5a2  test    [rcx+1Ch], r13b
0x14008d5a6  jz      short loc_14008D5C0
0x14008d5a8  cmp     [rcx+19h], dl
0x14008d5ab  jb      short loc_14008D5C0
0x14008d5ad  mov     rcx, [rcx+10h]
0x14008d5b1  lea     edx, [rbx+36h]
0x14008d5b4  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d5bb  call    WPP_SF_
0x14008d5c0  mov     edx, 0FFFFFFFCh
0x14008d5c5  jmp     short loc_14008D54A
0x14008d5c7  cmp     ebx, 9
0x14008d5ca  jnz     short loc_14008D600
0x14008d5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d5d3  cmp     rcx, r12
0x14008d5d6  jz      short loc_14008D5F6
0x14008d5d8  test    [rcx+1Ch], r13b
0x14008d5dc  jz      short loc_14008D5F6
0x14008d5de  cmp     [rcx+19h], dl
0x14008d5e1  jb      short loc_14008D5F6
0x14008d5e3  mov     rcx, [rcx+10h]
0x14008d5e7  lea     edx, [rbx+36h]
0x14008d5ea  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d5f1  call    WPP_SF_
0x14008d5f6  mov     edx, 0FFFFFFFBh
0x14008d5fb  jmp     loc_14008D54A
0x14008d600  cmp     ebx, 0Bh
0x14008d603  jnz     short loc_14008D639
0x14008d605  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d60c  cmp     rcx, r12
0x14008d60f  jz      short loc_14008D62F
0x14008d611  test    [rcx+1Ch], r13b
0x14008d615  jz      short loc_14008D62F
0x14008d617  cmp     [rcx+19h], dl
0x14008d61a  jb      short loc_14008D62F
0x14008d61c  mov     rcx, [rcx+10h]
0x14008d620  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d627  mov     edx, r13d
0x14008d62a  call    WPP_SF_
0x14008d62f  mov     edx, 0FFFFFFF9h
0x14008d634  jmp     loc_14008D54A
0x14008d639  test    ebx, ebx
0x14008d63b  jnz     short loc_14008D6B1
0x14008d63d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d644  cmp     rcx, r12
0x14008d647  jz      short loc_14008D667
0x14008d649  test    [rcx+1Ch], r13b
0x14008d64d  jz      short loc_14008D667
0x14008d64f  cmp     [rcx+19h], dl
0x14008d652  jb      short loc_14008D667
0x14008d654  mov     rcx, [rcx+10h]
0x14008d658  lea     edx, [rbx+41h]
0x14008d65b  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d662  call    WPP_SF_
0x14008d667  mov     rax, cs:qword_1400D2550
0x14008d66e  mov     edi, 2
0x14008d673  mov     ecx, [rax+94h]
0x14008d679  dec     ecx
0x14008d67b  cmp     ecx, edi
0x14008d67d  jbe     loc_14008E0BE
0x14008d683  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID56916126@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126> `wil::Feature<__WilFeatureTraits_Feature_ID56916126>::GetImpl(void)'::`2'::impl
0x14008d68a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56916126@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56916126>::__private_IsEnabled(void)
0x14008d68f  test    al, al
0x14008d691  jz      short loc_14008D6A7
0x14008d693  mov     rax, cs:qword_1400D2550
0x14008d69a  cmp     dword ptr [rax+94h], 4
0x14008d6a1  jz      loc_14008E0BE
0x14008d6a7  xor     edx, edx
0x14008d6a9  lea     ecx, [rdx+3]
0x14008d6ac  jmp     loc_14008D472
0x14008d6b1  cmp     ebx, 0Ch
0x14008d6b4  jnz     short loc_14008D6EA
0x14008d6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d6bd  cmp     rcx, r12
0x14008d6c0  jz      short loc_14008D6E0
0x14008d6c2  test    [rcx+1Ch], r13b
0x14008d6c6  jz      short loc_14008D6E0
0x14008d6c8  cmp     [rcx+19h], dl
0x14008d6cb  jb      short loc_14008D6E0
0x14008d6cd  mov     rcx, [rcx+10h]
0x14008d6d1  lea     edx, [rbx+36h]
0x14008d6d4  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d6db  call    WPP_SF_
0x14008d6e0  mov     edx, 0FFFFFFF8h
0x14008d6e5  jmp     loc_14008D54A
0x14008d6ea  cmp     ebx, 0Dh
0x14008d6ed  jnz     short loc_14008D723
0x14008d6ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d6f6  cmp     rcx, r12
0x14008d6f9  jz      short loc_14008D719
0x14008d6fb  test    [rcx+1Ch], r13b
0x14008d6ff  jz      short loc_14008D719
0x14008d701  cmp     [rcx+19h], dl
0x14008d704  jb      short loc_14008D719
0x14008d706  mov     rcx, [rcx+10h]
0x14008d70a  lea     edx, [rbx+36h]
0x14008d70d  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d714  call    WPP_SF_
0x14008d719  mov     edx, 0FFFFFFF7h
0x14008d71e  jmp     loc_14008D54A
0x14008d723  cmp     ebx, 0Eh
0x14008d726  jnz     loc_14008E0BE
0x14008d72c  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d733  cmp     rcx, r12
0x14008d736  jz      loc_14008E0BE
0x14008d73c  test    [rcx+1Ch], r13b
0x14008d740  jz      loc_14008E0BE
0x14008d746  cmp     [rcx+19h], dl
0x14008d749  jb      loc_14008E0BE
0x14008d74f  mov     rcx, [rcx+10h]
0x14008d753  lea     edx, [rbx+36h]
0x14008d756  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d75d  call    WPP_SF_
0x14008d762  jmp     loc_14008E0BE
0x14008d767  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d76e  cmp     rcx, r12
0x14008d771  jz      short loc_14008D793
0x14008d773  test    [rcx+1Ch], r13b
0x14008d777  jz      short loc_14008D793
0x14008d779  cmp     [rcx+19h], dl
0x14008d77c  jb      short loc_14008D793
0x14008d77e  mov     rcx, [rcx+10h]
0x14008d782  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d789  mov     edx, 45h ; 'E'
0x14008d78e  call    WPP_SF_
0x14008d793  mov     edx, ebx
0x14008d795  jmp     loc_14008D54A
0x14008d79a  mov     rcx, cs:WPP_GLOBAL_Control
0x14008d7a1  cmp     rcx, r12
0x14008d7a4  jz      short loc_14008D7C9
0x14008d7a6  test    [rcx+1Ch], r13b
0x14008d7aa  jz      short loc_14008D7C9
0x14008d7ac  cmp     [rcx+19h], dl
0x14008d7af  jb      short loc_14008D7C9
0x14008d7b1  mov     rcx, [rcx+10h]
0x14008d7b5  lea     r8, WPP_9372b429430230a2303f99774b8cd740_Traceguids
0x14008d7bc  mov     edx, 48h ; 'H'
0x14008d7c1  mov     r9d, ebx
0x14008d7c4  call    WPP_SF_d
0x14008d7c9  call    ?AsyncLogoffSupportIsLogoffInProgress@@YAHXZ; AsyncLogoffSupportIsLogoffInProgress(void)
0x14008d7ce  test    eax, eax
0x14008d7d0  jnz     short loc_14008D839
0x14008d7d2  call    ?IsShellRequiredInSession@CSession@@QEAAHXZ; CSession::IsShellRequiredInSession(void)
0x14008d7d7  test    eax, eax
0x14008d7d9  jz      short loc_14008D7FF
0x14008d7db  lea     r8, ?xGlobalContext@@3U_WLSM_GLOBAL_CONTEXT@@A; struct _WLSM_GLOBAL_CONTEXT *
0x14008d7e2  mov     edx, 1; int
0x14008d7e7  lea     rcx, aShellrestart; "ShellRestart"
0x14008d7ee  call    ?RecordBlackboxInfo@@YAXPEBGHPEAU_WLSM_GLOBAL_CONTEXT@@@Z; RecordBlackboxInfo(ushort const *,int,_WLSM_GLOBAL_CONTEXT *)
  ... truncated ...
```
