# WTSQuerySessionInformationW

- ea: `0x180002d20`
- end: `0x1800037b0`
- name: `WTSQuerySessionInformationW`
- size: `2704`
- prototype: `BOOL __stdcall(HANDLE hServer, DWORD SessionId, WTS_INFO_CLASS WTSInfoClass, LPWSTR *ppBuffer, DWORD *pBytesReturned)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002780`
- `0x180002b40`

## callees

- `0x180002d20`
- `0x180004090`
- `0x1800041d0`
- `0x180004240`
- `0x180004850`
- `0x180005230`
- `0x180008300`
- `0x180008660`
- `0x180008acc`
- `0x18001558e`
- `0x1800155c0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x180003418`
- `msvcrt!_wcsupr` at `0x180003418`
- `msvcrt!swscanf` at `0x180003434`
- `msvcrt!swscanf` at `0x180003487`
- `msvcrt!swscanf` at `0x180003434`
- `msvcrt!swscanf` at `0x180003487`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800030fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003146`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003603`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036bd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180002e84`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800030fb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003121`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003146`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800031c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003603`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800036bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e4c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e4c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000313b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e61`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e6a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002e7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000313b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002ef4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002f33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000301d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800030b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000310e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800034fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000366c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e02`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002e9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002ef4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002f33`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000301d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800030b8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000310e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800032e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800034fb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003569`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000366c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800034eb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800034eb`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800031b2`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800031ee`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800031b2`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x1800031ee`
- `WINSTA!WinStationIsSessionRemoteable` at `0x18000309d`
- `WINSTA!WinStationIsSessionRemoteable` at `0x18000309d`
- `WINSTA!WinStationQueryInformationW` at `0x180002e36`
- `WINSTA!WinStationQueryInformationW` at `0x180002f66`
- `WINSTA!WinStationQueryInformationW` at `0x18000318d`
- `WINSTA!WinStationQueryInformationW` at `0x180002e36`
- `WINSTA!WinStationQueryInformationW` at `0x180002f66`
- `WINSTA!WinStationQueryInformationW` at `0x18000318d`
- `WINSTA!WinStationGetDeviceId` at `0x1800035dc`
- `WINSTA!WinStationGetDeviceId` at `0x1800035dc`
- `WINSTA!WinStationQuerySessionVirtualIP` at `0x180002fa1`
- `WINSTA!WinStationQuerySessionVirtualIP` at `0x180002fa1`

## pseudocode

```c
BOOL __stdcall WTSQuerySessionInformationW(
        HANDLE hServer,
        DWORD SessionId,
        WTS_INFO_CLASS WTSInfoClass,
        LPWSTR *ppBuffer,
        DWORD *pBytesReturned)
{
  __int64 v5; // r12
  __int64 v6; // r13
  __int64 v7; // r15
  DWORD v8; // esi
  char *v10; // r13
  char *v11; // r15
  __int64 v12; // rdi
  unsigned int v13; // r12d
  char *v14; // rax
  int v15; // r8d
  void *v16; // rsi
  void *v17; // r14
  DWORD LastError; // ebx
  BOOL result; // eax
  char *v20; // rax
  void *v21; // rcx
  size_t v22; // rdx
  char v23; // al
  HLOCAL v24; // rax
  DWORD v25; // ecx
  WCHAR *v26; // rax
  char v27; // al
  _DWORD *v28; // rsi
  void *v29; // rcx
  void *v30; // rcx
  WCHAR *v31; // rax
  __int128 v32; // xmm0
  __int64 v33; // xmm1_8
  LPWSTR v34; // rax
  int v35; // eax
  const wchar_t *v36; // rsi
  WCHAR *v37; // rax
  __int128 v38; // xmm0
  LPWSTR v39; // rax
  int v40; // edi
  int v41; // esi
  int v42; // r12d
  WCHAR *v43; // rax
  LPWSTR v44; // rcx
  WCHAR *v45; // rax
  __int128 v46; // xmm0
  char *v47; // [rsp+48h] [rbp-81h]
  HLOCAL v48; // [rsp+50h] [rbp-79h]
  char v49[4]; // [rsp+58h] [rbp-71h] BYREF
  int v50; // [rsp+5Ch] [rbp-6Dh] BYREF
  HANDLE v51; // [rsp+60h] [rbp-69h]
  _BYTE v52[24]; // [rsp+68h] [rbp-61h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-49h]
  __int128 v54; // [rsp+88h] [rbp-41h] BYREF
  __m128i v55; // [rsp+98h] [rbp-31h]
  CHAR MultiByteStr[16]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v57; // [rsp+B8h] [rbp-11h]
  __int128 v58; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v59; // [rsp+D0h] [rbp+7h] BYREF
  __int64 v60; // [rsp+E8h] [rbp+1Fh]
  __int64 v61; // [rsp+F0h] [rbp+27h]
  __int64 v62; // [rsp+F8h] [rbp+2Fh]

  LODWORD(v59) = WTSInfoClass;
  v51 = hServer;
  v8 = SessionId;
  v57 = 0;
  v49[0] = 0;
  v50 = 0;
  *(_OWORD *)MultiByteStr = 0;
  v54 = 0;
  v55 = 0;
  v58 = 0;
  if ( ppBuffer && pBytesReturned )
  {
    v62 = v5;
    v61 = v6;
    v60 = v7;
    switch ( WTSInfoClass )
    {
      case WTSIdleTime:
      case WTSLogonTime:
      case WTSIncomingBytes:
      case WTSOutgoingBytes:
      case WTSIncomingFrames:
      case WTSOutgoingFrames:
LABEL_29:
        v25 = 50;
LABEL_30:
        SetLastError(v25);
        return 0;
      default:
        v10 = 0;
        v47 = 0;
        v11 = 0;
        v48 = 0;
        v12 = 0;
        hMem = 0;
        v13 = 4;
        switch ( WTSInfoClass )
        {
          case WTSInitialProgram:
          case WTSApplicationName:
          case WTSWorkingDirectory:
          case WTSOEMId:
          case WTSConfigInfo:
            v14 = (char *)LocalAlloc(0x40u, 0xA68u);
            v47 = v14;
            if ( !v14 )
              return 0;
            if ( (unsigned __int8)WinStationQueryInformationW(v51, v8, 1, v14, 2664, &v50) )
              goto LABEL_47;
LABEL_7:
            v16 = v47;
            goto LABEL_8;
          case WTSSessionId:
            v20 = (char *)LocalAlloc(0x40u, 0x4C0u);
            v10 = v20;
            if ( !v20 )
              return 0;
            if ( v8 == -1 )
              v8 = NtCurrentPeb()->SessionId;
            *((_DWORD *)v20 + 18) = v8;
            v50 = 4;
LABEL_14:
            v21 = v10 + 72;
            goto LABEL_15;
          case WTSUserName:
          case WTSWinStationName:
          case WTSDomainName:
          case WTSConnectState:
          case WTSSessionInfo:
            v10 = (char *)LocalAlloc(0x40u, 0x4C0u);
            if ( !v10 )
              return 0;
            v23 = WinStationQueryInformationW(v51, v8, 8, v10, 1216, &v50);
            goto LABEL_46;
          case WTSClientBuildNumber:
          case WTSClientName:
          case WTSClientDirectory:
          case WTSClientProductId:
          case WTSClientHardwareId:
          case WTSClientAddress:
          case WTSClientDisplay:
          case WTSClientProtocolType:
          case WTSClientInfo:
            v11 = (char *)LocalAlloc(0x40u, 0x8F8u);
            if ( !v11 )
              return 0;
            v23 = WinStationQueryInformationW(v51, v8, 6, v11, 2296, &v50);
            goto LABEL_46;
          case WTSSessionInfoEx:
            v24 = LocalAlloc(0x40u, 0x4C8u);
            v48 = v24;
            if ( !v24 )
              return 0;
            if ( (unsigned __int8)WinStationQueryInformationW(v51, v8, 40, v24, 1224, &v50) )
            {
LABEL_22:
              v17 = v48;
              v16 = v47;
              LODWORD(v12) = CollectSessionInfoEx(v48, ppBuffer, pBytesReturned);
            }
            else
            {
              v17 = v48;
              v16 = 0;
            }
            goto LABEL_9;
          case WTSValidationInfo:
            goto LABEL_29;
          case WTSSessionAddressV4:
            if ( !(unsigned __int8)WinStationQuerySessionVirtualIP(hServer, SessionId, 2, &v54) )
              goto LABEL_39;
LABEL_24:
            memset(v52, 0, sizeof(v52));
            *(_DWORD *)v52 = (unsigned __int16)v54;
            if ( (unsigned __int16)v54 == 2 )
            {
              *(_DWORD *)&v52[6] = DWORD2(v54);
            }
            else if ( (unsigned __int16)v54 == 23 )
            {
              *(_WORD *)&v52[22] = 0;
              *(_DWORD *)&v52[6] = HIDWORD(v54);
              *(_QWORD *)&v52[10] = v55.m128i_i64[0];
              *(_DWORD *)&v52[18] = _mm_cvtsi128_si32(_mm_srli_si128(v55, 8));
            }
            v31 = (WCHAR *)LocalAlloc(0x40u, 0x18u);
            *ppBuffer = v31;
            if ( !v31 )
              goto LABEL_17;
            v32 = *(_OWORD *)v52;
            LODWORD(v12) = 1;
            v16 = v47;
            v33 = *(_QWORD *)&v52[16];
            *pBytesReturned = 24;
            v34 = *ppBuffer;
            v17 = 0;
            *(_OWORD *)v34 = v32;
            *((_QWORD *)v34 + 2) = v33;
            goto LABEL_9;
          case WTSIsRemoteSession:
            if ( !(unsigned __int8)WinStationIsSessionRemoteable(hServer, SessionId, v49) )
              goto LABEL_39;
            v50 = 1;
LABEL_34:
            v26 = (WCHAR *)LocalAlloc(0x40u, 1u);
            *ppBuffer = v26;
            if ( v26 )
            {
              v27 = v49[0];
              LODWORD(v12) = 1;
              *pBytesReturned = 1;
              *(_BYTE *)*ppBuffer = v27;
            }
            v16 = v47;
            v17 = 0;
            goto LABEL_9;
          case WTSSessionAddressV4|WTSWorkingDirectory:
            v23 = WinStationQueryInformationW(hServer, SessionId, 42, &v58, 16, &v50);
LABEL_46:
            if ( !v23 )
              goto LABEL_39;
LABEL_47:
            switch ( v15 )
            {
              case 0:
                if ( v8 == (unsigned int)RtlGetCurrentServiceSessionId() )
                  goto LABEL_49;
                v16 = v47;
                v29 = v47 + 754;
                goto LABEL_51;
              case 1:
                if ( v8 == (unsigned int)RtlGetCurrentServiceSessionId() )
                {
LABEL_49:
                  SetLastError(0x57u);
                  goto LABEL_7;
                }
                v16 = v47;
                v29 = v47 + 1494;
LABEL_51:
                v17 = 0;
                LODWORD(v12) = CopyStringW(v29);
                break;
              case 2:
                v16 = v47;
                v29 = v47 + 240;
                goto LABEL_51;
              case 3:
                v16 = v47;
                v17 = 0;
                LODWORD(v12) = CopyStringA(v47 + 2660, ppBuffer, pBytesReturned);
                goto LABEL_9;
              case 4:
                goto LABEL_14;
              case 5:
                v30 = v10 + 1160;
                goto LABEL_58;
              case 6:
                v30 = v10 + 4;
                goto LABEL_58;
              case 7:
                v30 = v10 + 1124;
                goto LABEL_58;
              case 8:
                v16 = v47;
                LODWORD(v12) = CopyData(v10, 4u);
                v17 = 0;
                goto LABEL_9;
              case 9:
                v21 = v11 + 2012;
                goto LABEL_15;
              case 10:
                v30 = v11 + 4;
                goto LABEL_58;
              case 11:
                v30 = v11 + 1350;
LABEL_58:
                v16 = v47;
                LODWORD(v12) = CopyStringW(v30);
                v17 = 0;
                goto LABEL_9;
              case 12:
                v21 = v11 + 2020;
                v22 = 2;
                goto LABEL_16;
              case 13:
                v21 = v11 + 2016;
                goto LABEL_15;
              case 14:
                v35 = *((_DWORD *)v11 + 298);
                *(_DWORD *)MultiByteStr = v35;
                if ( v35 )
                {
                  switch ( v35 )
                  {
                    case 2:
                      v59 = 0;
                      swscanf(
                        (const wchar_t *const)v11 + 598,
                        L"%hu.%hu.%hu.%hu",
                        &v59,
                        (char *)&v59 + 2,
                        (char *)&v59 + 4,
                        (char *)&v59 + 6);
                      MultiByteStr[6] = v59;
                      MultiByteStr[7] = BYTE2(v59);
                      MultiByteStr[8] = BYTE4(v59);
                      MultiByteStr[9] = BYTE6(v59);
                      break;
                    case 6:
                      v36 = (const wchar_t *)(v11 + 1196);
                      LOWORD(v59) = 0;
                      _wcsupr((wchar_t *)v11 + 598);
                      do
                      {
                        if ( *v36 == 58 )
                        {
                          ++v36;
                          LODWORD(v12) = v12 - 1;
                        }
                        else
                        {
                          swscanf(v36, L"%2hX", &v59);
                          v36 += 2;
                          MultiByteStr[v12 + 4] = v59;
                        }
                        v12 = (unsigned int)(v12 + 1);
                      }
                      while ( (unsigned int)v12 < 0xA );
                      break;
                    case 23:
                      MultiByteStr[6] = v11[1197];
                      MultiByteStr[7] = v11[1196];
                      MultiByteStr[8] = v11[1199];
                      MultiByteStr[9] = v11[1198];
                      MultiByteStr[10] = v11[1201];
                      MultiByteStr[11] = v11[1200];
                      MultiByteStr[12] = v11[1203];
                      MultiByteStr[13] = v11[1202];
                      MultiByteStr[14] = v11[1205];
                      MultiByteStr[15] = v11[1204];
                      LOBYTE(v57) = v11[1207];
                      BYTE1(v57) = v11[1206];
                      BYTE2(v57) = v11[1209];
                      BYTE3(v57) = v11[1208];
                      BYTE4(v57) = v11[1211];
                      BYTE5(v57) = v11[1210];
                      break;
                  }
                }
                else
                {
                  if ( *((_WORD *)v11 + 628) )
                    *((_WORD *)v11 + 628) = 0;
                  WideCharToMultiByte(0, 0, (LPCWCH)v11 + 598, -1, &MultiByteStr[4], 20, 0, 0);
                }
                v37 = (WCHAR *)LocalAlloc(0x40u, 0x18u);
                *ppBuffer = v37;
                if ( !v37 )
                  goto LABEL_85;
                v38 = *(_OWORD *)MultiByteStr;
                v16 = v47;
                LODWORD(v12) = 1;
                *pBytesReturned = 24;
                v39 = *ppBuffer;
                v17 = 0;
                *(_OWORD *)v39 = v38;
                *((_QWORD *)v39 + 2) = v57;
                goto LABEL_9;
              case 15:
                v40 = *((unsigned __int16 *)v11 + 629);
                v41 = *((unsigned __int16 *)v11 + 630);
                v42 = *((unsigned __int16 *)v11 + 631);
                v43 = (WCHAR *)LocalAlloc(0x40u, 0xCu);
                *ppBuffer = v43;
                if ( v43 )
                {
                  *pBytesReturned = 12;
                  v44 = *ppBuffer;
                  v17 = 0;
                  *(_DWORD *)v44 = v40;
                  LODWORD(v12) = 1;
                  *((_DWORD *)v44 + 1) = v41;
                  v16 = v47;
                  *((_DWORD *)v44 + 2) = v42;
                }
                else
                {
LABEL_85:
                  v16 = v47;
                  LODWORD(v12) = 0;
                  v17 = 0;
                }
                goto LABEL_9;
              case 16:
                v21 = v11 + 1264;
                v22 = 2;
                goto LABEL_16;
              case 17:
              case 18:
              case 19:
              case 20:
              case 21:
              case 22:
              case 27:
                goto LABEL_7;
              case 23:
                LODWORD(v12) = CollectClientInfo(v11, ppBuffer, pBytesReturned);
                if ( !(_DWORD)v12 || (unsigned __int8)WinStationGetDeviceId(v51, v8, *ppBuffer + 890, 261) )
                  goto LABEL_17;
                memset_0(*ppBuffer + 890, 0, 0x20Au);
                SetLastError(0);
                v16 = v47;
                v17 = 0;
                goto LABEL_9;
              case 24:
                v16 = v47;
                LODWORD(v12) = CollectSessionInfo(v10, ppBuffer, pBytesReturned);
                v17 = 0;
                goto LABEL_9;
              case 25:
                goto LABEL_22;
              case 26:
                v16 = v47;
                v17 = 0;
                LODWORD(v12) = CollectConfigInfo(v47, ppBuffer, pBytesReturned);
                goto LABEL_9;
              case 28:
                goto LABEL_24;
              case 29:
                goto LABEL_34;
              case 30:
                v45 = (WCHAR *)LocalAlloc(0x40u, 0x10u);
                *ppBuffer = v45;
                if ( !v45 )
                  goto LABEL_17;
                v46 = v58;
                v16 = v47;
                LODWORD(v12) = 1;
                *pBytesReturned = 16;
                v17 = 0;
                *(_OWORD *)*ppBuffer = v46;
                goto LABEL_9;
              case 31:
                v13 = v50;
                v21 = 0;
                goto LABEL_15;
              default:
                goto LABEL_99;
            }
            goto LABEL_9;
          case WTSIsRemoteSession|WTSWorkingDirectory:
            hMem = 0;
            if ( !(unsigned int)Feature_RailV2ServerBuildSupported__private_IsEnabledDeviceUsageNoInline() )
            {
              SetLastError(2u);
LABEL_39:
              v16 = 0;
              goto LABEL_8;
            }
            v28 = LocalAlloc(0, 4u);
            if ( !v28 )
            {
              SetLastError(0xEu);
              v16 = 0;
LABEL_8:
              v17 = 0;
              goto LABEL_9;
            }
            if ( !(unsigned int)Feature_RailV2ServerBuildSupported__private_IsEnabledDeviceUsageNoInline() )
            {
              LocalFree(v28);
              SetLastError(0x54Fu);
              v16 = 0;
              goto LABEL_8;
            }
            *v28 = 59083637;
            hMem = v28;
            v21 = v28;
            v50 = 4;
LABEL_15:
            v22 = v13;
LABEL_16:
            LODWORD(v12) = CopyData(v21, v22);
LABEL_17:
            v16 = v47;
            v17 = 0;
LABEL_9:
            LastError = GetLastError();
            LocalFree(hMem);
            LocalFree(v16);
            LocalFree(v10);
            LocalFree(v11);
            LocalFree(v17);
            SetLastError(LastError);
            result = v12;
            break;
          default:
LABEL_99:
            v25 = 87;
            goto LABEL_30;
        }
        break;
    }
  }
  else
  {
    SetLastError(0x6F8u);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180002d20  mov     r11, rsp
0x180002d23  push    rbp
0x180002d24  push    rbx
0x180002d25  push    rsi
0x180002d26  push    r14
0x180002d28  lea     rbp, [r11-57h]
0x180002d2c  sub     rsp, 0F8h
0x180002d33  mov     rax, cs:__security_cookie
0x180002d3a  xor     rax, rsp
0x180002d3d  mov     [rbp+4Fh+var_40], rax
0x180002d41  mov     r14, [rbp+4Fh+pBytesReturned]
0x180002d45  xor     eax, eax
0x180002d47  xorps   xmm0, xmm0
0x180002d4a  mov     dword ptr [rbp+4Fh+var_48], r8d
0x180002d4e  xorps   xmm1, xmm1
0x180002d51  mov     [rbp+4Fh+var_B8], rcx
0x180002d55  mov     esi, edx
0x180002d57  mov     [rbp+4Fh+var_60], rax
0x180002d5b  xor     edx, edx
0x180002d5d  mov     [rbp+4Fh+var_C0], al
0x180002d60  mov     [rbp+4Fh+var_BC], edx
0x180002d63  mov     rbx, r9
0x180002d66  mov     r10, rcx
0x180002d69  movups  xmmword ptr [rbp+4Fh+MultiByteStr], xmm0
0x180002d6d  movups  [rbp+4Fh+var_90], xmm1
0x180002d71  movups  [rbp+4Fh+var_80], xmm1
0x180002d75  movups  [rbp+4Fh+var_58], xmm0
0x180002d79  test    r9, r9
0x180002d7c  jz      loc_1800036B8
0x180002d82  test    r14, r14
0x180002d85  jz      loc_1800036B8
0x180002d8b  mov     [r11+18h], rdi
0x180002d8f  lea     eax, [r8-11h]; switch 6 cases
0x180002d93  mov     [r11-28h], r12
0x180002d97  lea     r9, __ImageBase
0x180002d9e  mov     [r11-30h], r13
0x180002da2  mov     [r11-38h], r15
0x180002da6  cmp     eax, 5
0x180002da9  ja      short def_180002DB8; jumptable 0000000180002DB8 default case
0x180002dab  cdqe
0x180002dad  mov     ecx, ds:(jpt_180002DB8 - 180000000h)[r9+rax*4]
0x180002db5  add     rcx, r9
0x180002db8  jmp     rcx; switch jump
0x180002dba  cmp     r8d, 1Fh; jumptable 0000000180002DB8 default case
0x180002dbe  ja      def_180002DF6; jumptable 0000000180002DF6 default case, cases 17-22
0x180002dc4  movsxd  rax, r8d
0x180002dc7  mov     r13, rdx
0x180002dca  mov     [rsp+40h], rdx
0x180002dcf  mov     r15, rdx
0x180002dd2  mov     [rbp+4Fh+var_C8], rdx
0x180002dd6  mov     edi, edx
0x180002dd8  mov     [rbp+4Fh+hMem], rdx
0x180002ddc  mov     r12d, 4
0x180002de2  movzx   eax, ds:(byte_180003710 - 180000000h)[r9+rax]
0x180002deb  mov     ecx, ds:(jpt_180002DF6 - 180000000h)[r9+rax*4]
0x180002df3  add     rcx, r9
0x180002df6  jmp     rcx; switch jump
0x180002df8  mov     edx, 0A68h; jumptable 0000000180002DF6 cases 0-3,26
0x180002dfd  mov     ecx, 40h ; '@'; uFlags
0x180002e02  call    cs:__imp_LocalAlloc
0x180002e08  mov     [rsp+40h], rax
0x180002e0d  test    rax, rax
0x180002e10  jz      loc_180003059
0x180002e16  lea     rcx, [rbp+4Fh+var_BC]
0x180002e1a  mov     r9, rax
0x180002e1d  mov     qword ptr [rsp+110h+cbMultiByte], rcx
0x180002e22  mov     r8d, 1
0x180002e28  mov     rcx, [rbp+4Fh+var_B8]
0x180002e2c  mov     edx, esi
0x180002e2e  mov     dword ptr [rsp+110h+lpMultiByteStr], 0A68h
0x180002e36  call    cs:__imp_WinStationQueryInformationW
0x180002e3c  test    al, al
0x180002e3e  jnz     loc_18000319B
0x180002e44  mov     rsi, [rsp+40h]; jumptable 00000001800031B0 cases 17-22,27
0x180002e49  mov     r14, rdi
0x180002e4c  call    cs:__imp_GetLastError
0x180002e52  mov     rcx, [rbp+4Fh+hMem]; hMem
0x180002e56  mov     ebx, eax
0x180002e58  call    cs:__imp_LocalFree
0x180002e5e  mov     rcx, rsi; hMem
0x180002e61  call    cs:__imp_LocalFree
0x180002e67  mov     rcx, r13; hMem
0x180002e6a  call    cs:__imp_LocalFree
0x180002e70  mov     rcx, r15; hMem
0x180002e73  call    cs:__imp_LocalFree
0x180002e79  mov     rcx, r14; hMem
0x180002e7c  call    cs:__imp_LocalFree
0x180002e82  mov     ecx, ebx; dwErrCode
0x180002e84  call    cs:__imp_SetLastError
0x180002e8a  mov     eax, edi
0x180002e8c  jmp     loc_18000305B
0x180002e91  mov     edx, 4C0h; jumptable 0000000180002DF6 case 4
0x180002e96  mov     ecx, 40h ; '@'; uFlags
0x180002e9b  call    cs:__imp_LocalAlloc
0x180002ea1  mov     r13, rax
0x180002ea4  test    rax, rax
0x180002ea7  jz      loc_180003059
0x180002ead  cmp     esi, 0FFFFFFFFh
0x180002eb0  jnz     short loc_180002EC1
0x180002eb2  mov     rcx, gs:60h
0x180002ebb  mov     esi, [rcx+2C0h]
0x180002ec1  mov     [rax+48h], esi
0x180002ec4  mov     [rbp+4Fh+var_BC], r12d
0x180002ec8  lea     rcx, [r13+48h]; jumptable 00000001800031B0 case 4
0x180002ecc  mov     edx, r12d; Size
0x180002ecf  mov     r9, r14
0x180002ed2  mov     r8, rbx
0x180002ed5  call    _CopyData
0x180002eda  mov     edi, eax
0x180002edc  mov     rsi, [rsp+40h]
0x180002ee1  mov     r14, [rbp+4Fh+var_C8]
0x180002ee5  jmp     loc_180002E4C
0x180002eea  mov     edx, 4C0h; jumptable 0000000180002DF6 cases 5-8,24
0x180002eef  mov     ecx, 40h ; '@'; uFlags
0x180002ef4  call    cs:__imp_LocalAlloc
0x180002efa  mov     r13, rax
0x180002efd  test    rax, rax
0x180002f00  jz      loc_180003059
0x180002f06  mov     rcx, [rbp+4Fh+var_B8]
0x180002f0a  lea     rax, [rbp+4Fh+var_BC]
0x180002f0e  mov     qword ptr [rsp+110h+cbMultiByte], rax
0x180002f13  mov     r9, r13
0x180002f16  mov     dword ptr [rsp+110h+lpMultiByteStr], 4C0h
0x180002f1e  mov     r8d, 8
0x180002f24  jmp     loc_18000318B
0x180002f29  mov     edx, 4C8h; jumptable 0000000180002DF6 case 25
0x180002f2e  mov     ecx, 40h ; '@'; uFlags
0x180002f33  call    cs:__imp_LocalAlloc
0x180002f39  mov     [rbp+4Fh+var_C8], rax
0x180002f3d  test    rax, rax
0x180002f40  jz      loc_180003059
0x180002f46  mov     rcx, [rbp+4Fh+var_B8]
0x180002f4a  lea     rdx, [rbp+4Fh+var_BC]
0x180002f4e  mov     qword ptr [rsp+110h+cbMultiByte], rdx
0x180002f53  mov     r9, rax
0x180002f56  mov     edx, esi
0x180002f58  mov     dword ptr [rsp+110h+lpMultiByteStr], 4C8h
0x180002f60  mov     r8d, 28h ; '('
0x180002f66  call    cs:__imp_WinStationQueryInformationW
0x180002f6c  test    al, al
0x180002f6e  jz      loc_1800036A2
0x180002f74  mov     r8, r14; jumptable 00000001800031B0 case 25
0x180002f77  mov     rdx, rbx
0x180002f7a  mov     r14, [rbp+4Fh+var_C8]
0x180002f7e  mov     rcx, r14
0x180002f81  call    CollectSessionInfoEx
0x180002f86  mov     rsi, [rsp+40h]
0x180002f8b  mov     edi, eax
0x180002f8d  jmp     loc_180002E4C
0x180002f92  mov     r8d, 2; jumptable 0000000180002DF6 case 28
0x180002f98  lea     r9, [rbp+4Fh+var_90]
0x180002f9c  mov     edx, esi
0x180002f9e  mov     rcx, r10
0x180002fa1  call    cs:__imp_WinStationQuerySessionVirtualIP
0x180002fa7  test    al, al
0x180002fa9  jz      loc_180003101
0x180002faf  xor     eax, eax; jumptable 00000001800031B0 case 28
0x180002fb1  xorps   xmm0, xmm0
0x180002fb4  mov     [rbp+4Fh+var_A0], rax
0x180002fb8  movzx   eax, word ptr [rbp+4Fh+var_90]
0x180002fbc  movups  [rbp+4Fh+var_B0], xmm0
0x180002fc0  mov     dword ptr [rbp+4Fh+var_B0], eax
0x180002fc3  cmp     eax, 2
0x180002fc6  jz      loc_1800032C0
0x180002fcc  cmp     eax, 17h
0x180002fcf  jnz     loc_1800032DC
0x180002fd5  movups  [rbp+4Fh+var_B0+6], xmm0
0x180002fd9  xor     eax, eax
0x180002fdb  movups  xmm0, [rbp+4Fh+var_80]
0x180002fdf  mov     word ptr [rbp+4Fh+var_A0+6], ax
0x180002fe3  movzx   eax, byte ptr [rbp+4Fh+var_90+0Ch]
0x180002fe7  mov     byte ptr [rbp+4Fh+var_B0+6], al
0x180002fea  movzx   eax, byte ptr [rbp+4Fh+var_90+0Dh]
0x180002fee  mov     byte ptr [rbp+4Fh+var_B0+7], al
0x180002ff1  movzx   eax, byte ptr [rbp+4Fh+var_90+0Eh]
0x180002ff5  mov     byte ptr [rbp+4Fh+var_B0+8], al
0x180002ff8  movzx   eax, byte ptr [rbp+4Fh+var_90+0Fh]
0x180002ffc  movsd   qword ptr [rbp+4Fh+var_B0+0Ah], xmm0
0x180003001  psrldq  xmm0, 8
0x180003006  mov     byte ptr [rbp+4Fh+var_B0+9], al
0x180003009  movd    dword ptr [rbp+4Fh+var_A0+2], xmm0
0x18000300e  jmp     loc_1800032DC
0x180003013  mov     edx, 8F8h; jumptable 0000000180002DF6 cases 9-16,23
0x180003018  mov     ecx, 40h ; '@'; uFlags
0x18000301d  call    cs:__imp_LocalAlloc
0x180003023  mov     r15, rax
0x180003026  test    rax, rax
0x180003029  jz      short loc_180003059
0x18000302b  mov     rcx, [rbp+4Fh+var_B8]
0x18000302f  lea     rax, [rbp+4Fh+var_BC]
0x180003033  mov     qword ptr [rsp+110h+cbMultiByte], rax
0x180003038  mov     r9, r15
0x18000303b  mov     dword ptr [rsp+110h+lpMultiByteStr], 8F8h
0x180003043  mov     r8d, 6
0x180003049  jmp     loc_18000318B
0x18000304e  mov     ecx, 32h ; '2'; jumptable 0000000180002DB8 cases 17-22
0x180003053  call    cs:__imp_SetLastError
0x180003059  xor     eax, eax
0x18000305b  mov     r13, [rsp+110h+var_28]
0x180003063  mov     r12, [rsp+110h+var_20]
0x18000306b  mov     rdi, [rsp+110h+arg_10]
0x180003073  mov     r15, [rsp+110h+var_30]
0x18000307b  mov     rcx, [rbp+4Fh+var_40]
0x18000307f  xor     rcx, rsp; StackCookie
0x180003082  call    __security_check_cookie
0x180003087  add     rsp, 0F8h
0x18000308e  pop     r14
0x180003090  pop     rsi
0x180003091  pop     rbx
0x180003092  pop     rbp
0x180003093  retn
0x180003094  lea     r8, [rbp+4Fh+var_C0]; jumptable 0000000180002DF6 case 29
0x180003098  mov     edx, esi
0x18000309a  mov     rcx, r10
0x18000309d  call    cs:__imp_WinStationIsSessionRemoteable
0x1800030a3  test    al, al
0x1800030a5  jz      short loc_180003101
0x1800030a7  mov     [rbp+4Fh+var_BC], 1
0x1800030ae  mov     edx, 1; jumptable 00000001800031B0 case 29
0x1800030b3  mov     ecx, 40h ; '@'; uFlags
0x1800030b8  call    cs:__imp_LocalAlloc
0x1800030be  mov     [rbx], rax
0x1800030c1  test    rax, rax
0x1800030c4  jz      short loc_1800030DB
0x1800030c6  movzx   eax, [rbp+4Fh+var_C0]
0x1800030ca  mov     edi, 1
0x1800030cf  mov     dword ptr [r14], 1
0x1800030d6  mov     rcx, [rbx]
0x1800030d9  mov     [rcx], al
0x1800030db  mov     rsi, [rsp+40h]
0x1800030e0  mov     r14, [rbp+4Fh+var_C8]
0x1800030e4  jmp     loc_180002E4C
0x1800030e9  mov     [rbp+4Fh+hMem], rdx; jumptable 0000000180002DF6 case 31
0x1800030ed  call    Feature_RailV2ServerBuildSupported__private_IsEnabledDeviceUsageNoInline
0x1800030f2  test    eax, eax
0x1800030f4  jnz     short loc_180003109
0x1800030f6  mov     ecx, 2; dwErrCode
0x1800030fb  call    cs:__imp_SetLastError
0x180003101  mov     rsi, rdi
0x180003104  jmp     loc_180002E49
0x180003109  mov     rdx, r12; uBytes
0x18000310c  xor     ecx, ecx; uFlags
0x18000310e  call    cs:__imp_LocalAlloc
0x180003114  mov     rsi, rax
0x180003117  test    rax, rax
0x18000311a  jnz     short loc_18000312F
0x18000311c  mov     ecx, 0Eh; dwErrCode
0x180003121  call    cs:__imp_SetLastError
0x180003127  mov     rsi, rdi
0x18000312a  jmp     loc_180002E49
0x18000312f  call    Feature_RailV2ServerBuildSupported__private_IsEnabledDeviceUsageNoInline
0x180003134  test    eax, eax
0x180003136  jnz     short loc_180003154
0x180003138  mov     rcx, rsi; hMem
0x18000313b  call    cs:__imp_LocalFree
0x180003141  mov     ecx, 54Fh; dwErrCode
0x180003146  call    cs:__imp_SetLastError
0x18000314c  mov     rsi, rdi
0x18000314f  jmp     loc_180002E49
0x180003154  mov     rax, rsi
0x180003157  mov     dword ptr [rsi], 3858B75h
0x18000315d  mov     [rbp+4Fh+hMem], rax
0x180003161  mov     rcx, rax
0x180003164  mov     [rbp+4Fh+var_BC], r12d
0x180003168  jmp     loc_180002ECC
0x18000316d  lea     rax, [rbp+4Fh+var_BC]; jumptable 0000000180002DF6 case 30
0x180003171  mov     r8d, 2Ah ; '*'
0x180003177  mov     qword ptr [rsp+110h+cbMultiByte], rax
0x18000317c  lea     r9, [rbp+4Fh+var_58]
0x180003180  mov     dword ptr [rsp+110h+lpMultiByteStr], 10h
0x180003188  mov     rcx, r10
0x18000318b  mov     edx, esi
0x18000318d  call    cs:__imp_WinStationQueryInformationW
0x180003193  test    al, al
0x180003195  jz      loc_180003101
0x18000319b  movsxd  rax, dword ptr [rbp+4Fh+var_48]
0x18000319f  lea     rdx, __ImageBase
0x1800031a6  mov     ecx, ds:(jpt_1800031B0 - 180000000h)[rdx+rax*4]; switch 32 cases
0x1800031ad  add     rcx, rdx
0x1800031b0  jmp     rcx; switch jump
0x1800031b2  call    cs:__imp_RtlGetCurrentServiceSessionId; jumptable 00000001800031B0 case 0
0x1800031b8  cmp     esi, eax
0x1800031ba  jnz     short loc_1800031CC
0x1800031bc  mov     ecx, 57h ; 'W'; dwErrCode
0x1800031c1  call    cs:__imp_SetLastError
0x1800031c7  jmp     loc_180002E44; jumptable 00000001800031B0 cases 17-22,27
0x1800031cc  mov     rsi, [rsp+40h]
0x1800031d1  lea     rcx, [rsi+2F2h]; Src
0x1800031d8  mov     r8, r14
0x1800031db  mov     rdx, rbx
0x1800031de  call    _CopyStringW
0x1800031e3  mov     r14, [rbp+4Fh+var_C8]
0x1800031e7  mov     edi, eax
0x1800031e9  jmp     loc_180002E4C
0x1800031ee  call    cs:__imp_RtlGetCurrentServiceSessionId; jumptable 00000001800031B0 case 1
0x1800031f4  cmp     esi, eax
0x1800031f6  jz      short loc_1800031BC
0x1800031f8  mov     rsi, [rsp+40h]
0x1800031fd  lea     rcx, [rsi+5D6h]
0x180003204  jmp     short loc_1800031D8
  ... truncated ...
```
