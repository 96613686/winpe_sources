# WLGeneric_FindDestinationSession_Unlock_Execute(_StateMachineCallContext *)

- ea: `0x140070920`
- end: `0x1400710e1`
- name: `?WLGeneric_FindDestinationSession_Unlock_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `1985`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400057f4`
- `0x140016f30`
- `0x140032414`
- `0x140032550`
- `0x1400333b0`
- `0x140037b00`
- `0x14003bfec`
- `0x140041c34`
- `0x14004327c`
- `0x140044830`
- `0x14004d9f4`
- `0x14004df08`
- `0x140053720`
- `0x1400544e0`
- `0x140056348`
- `0x140070920`
- `0x1400899b8`
- `0x14008b96c`
- `0x14009b620`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070c75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070cec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140071044`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070e16`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070e16`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140070cbf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140070cbf`
- `RPCRT4!I_RpcMapWin32Status` at `0x140070f45`
- `RPCRT4!I_RpcMapWin32Status` at `0x140070f45`
- `SspiCli!LsaCallAuthenticationPackage` at `0x140070da0`
- `SspiCli!LsaCallAuthenticationPackage` at `0x140070da0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationConnectAndLockDesktop` at `0x140070ba0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationConnectAndLockDesktop` at `0x140070ba0`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140070c48`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x140070c48`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x140071023`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSDisconnectSession` at `0x140071023`
- `WTSAPI32!WTSConnectSessionW` at `0x140070a07`
- `WTSAPI32!WTSConnectSessionW` at `0x140070a07`

## string_xrefs

- `0x140071000`: `clientcore\ds\security\umstartup\winlogon\core\logon.cxx`

## pseudocode

```c
unsigned int __fastcall WLGeneric_FindDestinationSession_Unlock_Execute(
        struct _StateMachineCallContext *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v4; // r15d
  CGlobalStore **v5; // r14
  CUser *v6; // rcx
  ULONG *v7; // rdx
  ULONG v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  DWORD LastError; // eax
  DWORD NegotiatePackage; // eax
  CUser *v13; // rcx
  __int64 v14; // rdx
  _WORD *v15; // rcx
  DWORD v16; // eax
  DWORD v17; // eax
  NTSTATUS v18; // eax
  CGlobalStore *v19; // rdx
  __int64 v20; // rcx
  RPC_STATUS updated; // eax
  CGlobalStore *v22; // rbx
  int IsBoundToConsole; // eax
  int v24; // eax
  __int64 v25; // r9
  DWORD v26; // eax
  int ReturnLength; // [rsp+20h] [rbp-1B8h]
  int ProtocolStatus; // [rsp+50h] [rbp-188h] BYREF
  int v30; // [rsp+54h] [rbp-184h] BYREF
  DWORD v31; // [rsp+58h] [rbp-180h] BYREF
  ULONG AuthenticationPackage; // [rsp+5Ch] [rbp-17Ch] BYREF
  ULONG ReturnBufferLength; // [rsp+60h] [rbp-178h] BYREF
  HANDLE LsaHandle; // [rsp+68h] [rbp-170h] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+70h] [rbp-168h] BYREF
  __int128 v36; // [rsp+78h] [rbp-160h] BYREF
  HANDLE TokenHandle; // [rsp+88h] [rbp-150h]
  __int128 v38; // [rsp+90h] [rbp-148h] BYREF
  __int128 v39; // [rsp+A0h] [rbp-138h]
  _BYTE v40[64]; // [rsp+B0h] [rbp-128h]
  _OWORD v41[6]; // [rsp+F0h] [rbp-E8h] BYREF
  _BYTE ProtocolSubmitBuffer[24]; // [rsp+150h] [rbp-88h] BYREF
  int TokenInformation; // [rsp+168h] [rbp-70h] BYREF
  __int128 v44; // [rsp+16Ch] [rbp-6Ch]
  __int128 v45; // [rsp+17Ch] [rbp-5Ch]
  __int128 v46; // [rsp+18Ch] [rbp-4Ch]
  int v47; // [rsp+19Ch] [rbp-3Ch]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v4 = 0;
  v5 = (CGlobalStore **)*((_QWORD *)a1 + 1);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, a4);
    v6 = WPP_GLOBAL_Control;
  }
  v7 = (ULONG *)v5[2];
  v8 = v7[72];
  if ( v8 == -1 )
  {
    v4 = 87;
    if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    {
      v9 = 142;
LABEL_10:
      WPP_SF_(*((_QWORD *)v6 + 2), v9, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, a4);
      goto LABEL_79;
    }
    goto LABEL_79;
  }
  v10 = v7[94];
  if ( !(_DWORD)v10 )
  {
    if ( !WTSConnectSessionW(v8, v7[22], (PWSTR)&pPassword, 0) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, LastError);
      }
      goto LABEL_79;
    }
    goto LABEL_17;
  }
  if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
    WPP_SF_d(*((_QWORD *)v6 + 2), 144, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v10);
  CSession::ResetAutoLock(v5[2], 2, v8);
  if ( (unsigned __int8)IsWinStationConnectAndLockDesktopPresent() )
  {
    v15 = (_WORD *)*((_QWORD *)*v5 + 15);
    if ( v15 )
      SetCredentialContextReg(v15);
    if ( !(unsigned __int8)WinStationConnectAndLockDesktop(0, v8) )
    {
      v16 = GetLastError();
      v4 = v16;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v16);
      }
      CleanupCredentialContextReg();
      goto LABEL_79;
    }
LABEL_17:
    WLEventWrite(&WLDiagEvt_UnlockSuccess_Stop);
    ProtocolStatus = 0;
    AuthenticationPackage = 0;
    ReturnBufferLength = 0;
    v31 = 0;
    ProtocolReturnBuffer = 0;
    LsaHandle = 0;
    TokenInformation = 0;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    v36 = 0;
    TokenHandle = 0;
    memset(ProtocolSubmitBuffer, 0, sizeof(ProtocolSubmitBuffer));
    NegotiatePackage = CGlobalStore::GetLsaHandle(*v5, &LsaHandle);
    if ( NegotiatePackage )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_66;
      }
      v14 = 147;
    }
    else
    {
      NegotiatePackage = CGlobalStore::GetNegotiatePackage(*v5, &AuthenticationPackage);
      if ( NegotiatePackage )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_66;
        }
        v14 = 148;
      }
      else
      {
        if ( (unsigned __int8)WinStationQueryInformationW(0, v8, 14, &v36, 24, &v31) )
        {
          if ( GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v31) )
          {
            *(_OWORD *)ProtocolSubmitBuffer = 0;
            *(_QWORD *)&ProtocolSubmitBuffer[16] = 0x400000000LL;
            *(_DWORD *)ProtocolSubmitBuffer = 1026;
            *(_QWORD *)&ProtocolSubmitBuffer[4] = *((_QWORD *)v5[5] + 16);
            *(_QWORD *)&ProtocolSubmitBuffer[12] = *(_QWORD *)((char *)&v44 + 4);
            v18 = LsaCallAuthenticationPackage(
                    LsaHandle,
                    AuthenticationPackage,
                    ProtocolSubmitBuffer,
                    0x18u,
                    &ProtocolReturnBuffer,
                    &ReturnBufferLength,
                    &ProtocolStatus);
            if ( v18 < 0 || ProtocolStatus < 0 )
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_DD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  151,
                  WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                  (unsigned int)v18,
                  ProtocolStatus);
              }
            }
            else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                152,
                WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                (unsigned int)v18);
            }
          }
          else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = GetLastError();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v17);
          }
          CloseHandle(TokenHandle);
          goto LABEL_66;
        }
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
LABEL_66:
          LODWORD(v38) = 0;
          memset_0((char *)&v38 + 4, 0, 0x5Cu);
          v30 = 0;
          v19 = v5[5];
          v20 = *((_QWORD *)v19 + 30);
          *(_QWORD *)&v38 = *(_QWORD *)(v20 + 16);
          *((_QWORD *)&v38 + 1) = *(_QWORD *)(v20 + 32);
          v39 = *(_OWORD *)(v20 + 40);
          *(_DWORD *)&v40[56] = *(_DWORD *)(v20 + 152);
          *(_QWORD *)v40 = *(_QWORD *)((char *)v19 + 252);
          *(_OWORD *)&v40[8] = *((_OWORD *)v19 + 11);
          *(_OWORD *)&v40[24] = *((_OWORD *)v19 + 12);
          *(_OWORD *)&v40[40] = *((_OWORD *)v19 + 13);
          v41[0] = v38;
          v41[1] = v39;
          v41[2] = *(_OWORD *)v40;
          v41[3] = *(_OWORD *)&v40[16];
          v41[4] = *(_OWORD *)&v40[32];
          v41[5] = *(_OWORD *)&v40[48];
          updated = WmsgSendReconnectionUpdateMessage(v8, v41, &v30);
          if ( updated )
            v30 = I_RpcMapWin32Status(updated);
          if ( v30 >= 0 )
          {
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                154,
                WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                (unsigned int)v30);
            }
          }
          else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                 && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              153,
              WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
              (unsigned int)v30);
          }
          v22 = *v5;
          IsBoundToConsole = CSession::IsBoundToConsole(v5[2]);
          v24 = CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity(
                  (RTL_SRWLOCK *)v22,
                  *((_DWORD *)v5[2] + 22),
                  1,
                  1,
                  IsBoundToConsole == 0,
                  0,
                  0,
                  0,
                  0);
          if ( v24 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xE84,
              (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\logon.cxx",
              (const char *)(unsigned int)v24,
              ReturnLength);
          goto LABEL_79;
        }
        NegotiatePackage = GetLastError();
        v14 = 149;
        v13 = WPP_GLOBAL_Control;
      }
    }
    WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, NegotiatePackage);
    goto LABEL_66;
  }
  v4 = 5;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = 145;
    goto LABEL_10;
  }
LABEL_79:
  if ( v4 )
  {
    if ( !WTSDisconnectSession(0, 0xFFFFFFFF, 0) )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v26 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v26);
      }
      *((_DWORD *)v5[1] + 23) = 0;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v25);
      }
    }
    WLEventWrite(&WLDiagEvt_UnlockFailure_Stop);
  }
  CGlobalStore::FreeCredentialContext(*v5, 0);
  return WlStateMachineSetSignal(0, 0);
}

```

## disassembly

```asm
0x140070920  mov     [rsp+arg_8], rbx
0x140070925  mov     [rsp+arg_10], rsi
0x14007092a  push    rdi
0x14007092b  push    r12
0x14007092d  push    r13
0x14007092f  push    r14
0x140070931  push    r15
0x140070933  sub     rsp, 1B0h
0x14007093a  mov     rax, cs:__security_cookie
0x140070941  xor     rax, rsp
0x140070944  mov     [rsp+1D8h+var_38], rax
0x14007094c  xor     r12d, r12d
0x14007094f  mov     r15d, r12d
0x140070952  mov     r14, [rcx+8]
0x140070956  lea     r13, WPP_GLOBAL_Control
0x14007095d  mov     rcx, cs:WPP_GLOBAL_Control
0x140070964  cmp     rcx, r13
0x140070967  jz      short loc_140070999
0x140070969  test    dword ptr [rcx+1Ch], 100h
0x140070970  jz      short loc_140070999
0x140070972  lea     rsi, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x140070979  cmp     byte ptr [rcx+19h], 4
0x14007097d  jb      short loc_1400709A0
0x14007097f  mov     edx, 8Dh
0x140070984  mov     r8, rsi
0x140070987  mov     rcx, [rcx+10h]
0x14007098b  call    WPP_SF_
0x140070990  mov     rcx, cs:WPP_GLOBAL_Control
0x140070997  jmp     short loc_1400709A0
0x140070999  lea     rsi, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x1400709a0  mov     rdx, [r14+10h]
0x1400709a4  mov     ebx, [rdx+120h]
0x1400709aa  cmp     ebx, 0FFFFFFFFh
0x1400709ad  jnz     short loc_1400709EB
0x1400709af  mov     r15d, 57h ; 'W'
0x1400709b5  mov     edi, 1000h
0x1400709ba  cmp     rcx, r13
0x1400709bd  jz      loc_140071012
0x1400709c3  test    [rcx+1Ch], edi
0x1400709c6  jz      loc_140071012
0x1400709cc  cmp     byte ptr [rcx+19h], 2
0x1400709d0  jb      loc_140071012
0x1400709d6  lea     edx, [r15+37h]
0x1400709da  mov     r8, rsi
0x1400709dd  mov     rcx, [rcx+10h]
0x1400709e1  call    WPP_SF_
0x1400709e6  jmp     loc_140071012
0x1400709eb  mov     r9d, [rdx+178h]; bWait
0x1400709f2  test    r9d, r9d
0x1400709f5  jnz     loc_140070B18
0x1400709fb  lea     r8, pPassword; pPassword
0x140070a02  mov     edx, [rdx+58h]; TargetLogonId
0x140070a05  mov     ecx, ebx; LogonId
0x140070a07  call    cs:__imp_WTSConnectSessionW
0x140070a0d  test    eax, eax
0x140070a0f  jnz     short loc_140070A5B
0x140070a11  call    cs:__imp_GetLastError
0x140070a17  mov     r15d, eax
0x140070a1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140070a21  mov     edi, 1000h
0x140070a26  cmp     rcx, r13
0x140070a29  jz      loc_140071012
0x140070a2f  test    [rcx+1Ch], edi
0x140070a32  jz      loc_140071012
0x140070a38  cmp     byte ptr [rcx+19h], 2
0x140070a3c  jb      loc_140071012
0x140070a42  mov     edx, 8Fh
0x140070a47  mov     r9d, eax
0x140070a4a  mov     r8, rsi
0x140070a4d  mov     rcx, [rcx+10h]
0x140070a51  call    WPP_SF_d
0x140070a56  jmp     loc_140071012
0x140070a5b  mov     edi, 1000h
0x140070a60  lea     rcx, WLDiagEvt_UnlockSuccess_Stop; struct _EVENT_DESCRIPTOR *
0x140070a67  call    ?WLEventWrite@@YAXAEBU_EVENT_DESCRIPTOR@@@Z; WLEventWrite(_EVENT_DESCRIPTOR const &)
0x140070a6c  mov     [rsp+1D8h+var_188], r12d
0x140070a71  mov     [rsp+1D8h+AuthenticationPackage], r12d
0x140070a76  mov     [rsp+1D8h+var_178], r12d
0x140070a7b  mov     [rsp+1D8h+var_180], r12d
0x140070a80  mov     [rsp+1D8h+ProtocolReturnBuffer], r12
0x140070a85  mov     [rsp+1D8h+LsaHandle], r12
0x140070a8a  mov     [rsp+1D8h+TokenInformation], r12d
0x140070a92  xorps   xmm0, xmm0
0x140070a95  xor     eax, eax
0x140070a97  movups  [rsp+1D8h+var_6C], xmm0
0x140070a9f  movups  [rsp+1D8h+var_5C], xmm0
0x140070aa7  movups  [rsp+1D8h+var_4C], xmm0
0x140070aaf  mov     [rsp+1D8h+var_3C], eax
0x140070ab6  movups  [rsp+1D8h+var_160], xmm0
0x140070abb  mov     [rsp+1D8h+TokenHandle], rax
0x140070ac3  xorps   xmm1, xmm1
0x140070ac6  movups  [rsp+1D8h+ProtocolSubmitBuffer], xmm1
0x140070ace  mov     [rsp+1D8h+var_78], rax
0x140070ad6  lea     rdx, [rsp+1D8h+LsaHandle]; void **
0x140070adb  mov     rcx, [r14]; this
0x140070ade  call    ?GetLsaHandle@CGlobalStore@@QEAAKPEAPEAX@Z; CGlobalStore::GetLsaHandle(void * *)
0x140070ae3  test    eax, eax
0x140070ae5  jz      loc_140070BEC
0x140070aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x140070af2  cmp     rcx, r13
0x140070af5  jz      loc_140070E1C
0x140070afb  test    [rcx+1Ch], edi
0x140070afe  jz      loc_140070E1C
0x140070b04  cmp     byte ptr [rcx+19h], 2
0x140070b08  jb      loc_140070E1C
0x140070b0e  mov     edx, 93h
0x140070b13  jmp     loc_140070C87
0x140070b18  mov     edi, 1000h
0x140070b1d  cmp     rcx, r13
0x140070b20  jz      short loc_140070B3E
0x140070b22  test    [rcx+1Ch], edi
0x140070b25  jz      short loc_140070B3E
0x140070b27  cmp     byte ptr [rcx+19h], 4
0x140070b2b  jb      short loc_140070B3E
0x140070b2d  mov     edx, 90h
0x140070b32  mov     r8, rsi
0x140070b35  mov     rcx, [rcx+10h]
0x140070b39  call    WPP_SF_d
0x140070b3e  mov     r8d, ebx
0x140070b41  mov     edx, 2
0x140070b46  mov     rcx, [r14+10h]
0x140070b4a  call    ?ResetAutoLock@CSession@@QEAAXW4AutoLockStopReason@1@K@Z; CSession::ResetAutoLock(CSession::AutoLockStopReason,ulong)
0x140070b4f  call    IsWinStationConnectAndLockDesktopPresent
0x140070b54  test    al, al
0x140070b56  jnz     short loc_140070B8B
0x140070b58  mov     r15d, 5
0x140070b5e  mov     rcx, cs:WPP_GLOBAL_Control
0x140070b65  cmp     rcx, r13
0x140070b68  jz      loc_140071012
0x140070b6e  test    [rcx+1Ch], edi
0x140070b71  jz      loc_140071012
0x140070b77  cmp     byte ptr [rcx+19h], 2
0x140070b7b  jb      loc_140071012
0x140070b81  mov     edx, 91h
0x140070b86  jmp     loc_1400709DA
0x140070b8b  mov     rax, [r14]
0x140070b8e  mov     rcx, [rax+78h]; lpData
0x140070b92  test    rcx, rcx
0x140070b95  jz      short loc_140070B9C
0x140070b97  call    ?SetCredentialContextReg@@YAXPEBG@Z; SetCredentialContextReg(ushort const *)
0x140070b9c  mov     edx, ebx
0x140070b9e  xor     ecx, ecx
0x140070ba0  call    cs:__imp_WinStationConnectAndLockDesktop
0x140070ba6  test    al, al
0x140070ba8  jnz     loc_140070A60
0x140070bae  call    cs:__imp_GetLastError
0x140070bb4  mov     r15d, eax
0x140070bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x140070bbe  cmp     rcx, r13
0x140070bc1  jz      short loc_140070BE2
0x140070bc3  test    [rcx+1Ch], edi
0x140070bc6  jz      short loc_140070BE2
0x140070bc8  cmp     byte ptr [rcx+19h], 2
0x140070bcc  jb      short loc_140070BE2
0x140070bce  mov     edx, 92h
0x140070bd3  mov     r9d, eax
0x140070bd6  mov     r8, rsi
0x140070bd9  mov     rcx, [rcx+10h]
0x140070bdd  call    WPP_SF_d
0x140070be2  call    ?CleanupCredentialContextReg@@YAXXZ; CleanupCredentialContextReg(void)
0x140070be7  jmp     loc_140071012
0x140070bec  lea     rdx, [rsp+1D8h+AuthenticationPackage]; unsigned int *
0x140070bf1  mov     rcx, [r14]; this
0x140070bf4  call    ?GetNegotiatePackage@CGlobalStore@@QEAAKPEAK@Z; CGlobalStore::GetNegotiatePackage(ulong *)
0x140070bf9  test    eax, eax
0x140070bfb  jz      short loc_140070C27
0x140070bfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140070c04  cmp     rcx, r13
0x140070c07  jz      loc_140070E1C
0x140070c0d  test    [rcx+1Ch], edi
0x140070c10  jz      loc_140070E1C
0x140070c16  cmp     byte ptr [rcx+19h], 2
0x140070c1a  jb      loc_140070E1C
0x140070c20  mov     edx, 94h
0x140070c25  jmp     short loc_140070C87
0x140070c27  lea     rax, [rsp+1D8h+var_180]
0x140070c2c  mov     [rsp+1D8h+ReturnBufferLength], rax
0x140070c31  mov     dword ptr [rsp+1D8h+ReturnLength], 18h
0x140070c39  lea     r9, [rsp+1D8h+var_160]
0x140070c3e  mov     r8d, 0Eh
0x140070c44  mov     edx, ebx
0x140070c46  xor     ecx, ecx
0x140070c48  call    cs:__imp_WinStationQueryInformationW
0x140070c4e  test    al, al
0x140070c50  jnz     short loc_140070C9B
0x140070c52  mov     rax, cs:WPP_GLOBAL_Control
0x140070c59  cmp     rax, r13
0x140070c5c  jz      loc_140070E1C
0x140070c62  test    [rax+1Ch], edi
0x140070c65  jz      loc_140070E1C
0x140070c6b  cmp     byte ptr [rax+19h], 2
0x140070c6f  jb      loc_140070E1C
0x140070c75  call    cs:__imp_GetLastError
0x140070c7b  mov     edx, 95h
0x140070c80  mov     rcx, cs:WPP_GLOBAL_Control
0x140070c87  mov     r9d, eax
0x140070c8a  mov     r8, rsi
0x140070c8d  mov     rcx, [rcx+10h]
0x140070c91  call    WPP_SF_d
0x140070c96  jmp     loc_140070E1C
0x140070c9b  lea     rax, [rsp+1D8h+var_180]
0x140070ca0  mov     [rsp+1D8h+ReturnLength], rax; ReturnLength
0x140070ca5  mov     r9d, 38h ; '8'; TokenInformationLength
0x140070cab  lea     r8, [rsp+1D8h+TokenInformation]; TokenInformation
0x140070cb3  lea     edx, [r9-2Eh]; TokenInformationClass
0x140070cb7  mov     rcx, [rsp+1D8h+TokenHandle]; TokenHandle
0x140070cbf  call    cs:__imp_GetTokenInformation
0x140070cc5  test    eax, eax
0x140070cc7  jnz     short loc_140070D12
0x140070cc9  mov     rax, cs:WPP_GLOBAL_Control
0x140070cd0  cmp     rax, r13
0x140070cd3  jz      loc_140070E0E
0x140070cd9  test    [rax+1Ch], edi
0x140070cdc  jz      loc_140070E0E
0x140070ce2  cmp     byte ptr [rax+19h], 2
0x140070ce6  jb      loc_140070E0E
0x140070cec  call    cs:__imp_GetLastError
0x140070cf2  mov     edx, 96h
0x140070cf7  mov     r9d, eax
0x140070cfa  mov     r8, rsi
0x140070cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140070d04  mov     rcx, [rcx+10h]
0x140070d08  call    WPP_SF_d
0x140070d0d  jmp     loc_140070E0E
0x140070d12  xorps   xmm0, xmm0
0x140070d15  xor     eax, eax
0x140070d17  movups  [rsp+1D8h+ProtocolSubmitBuffer], xmm0
0x140070d1f  mov     [rsp+1D8h+var_78], rax
0x140070d27  mov     dword ptr [rsp+1D8h+ProtocolSubmitBuffer], 402h
0x140070d32  mov     dword ptr [rsp+1D8h+var_78+4], 4
0x140070d3d  mov     rcx, [r14+28h]
0x140070d41  mov     eax, [rcx+80h]
0x140070d47  mov     dword ptr [rsp+1D8h+ProtocolSubmitBuffer+4], eax
0x140070d4e  mov     eax, [rcx+84h]
0x140070d54  mov     dword ptr [rsp+1D8h+ProtocolSubmitBuffer+8], eax
0x140070d5b  mov     rax, qword ptr [rsp+1D8h+var_6C+4]
0x140070d63  mov     qword ptr [rsp+1D8h+ProtocolSubmitBuffer+0Ch], rax
0x140070d6b  lea     rax, [rsp+1D8h+var_188]
0x140070d70  mov     [rsp+1D8h+ProtocolStatus], rax; ProtocolStatus
0x140070d75  lea     rax, [rsp+1D8h+var_178]
0x140070d7a  mov     [rsp+1D8h+ReturnBufferLength], rax; ReturnBufferLength
0x140070d7f  lea     rax, [rsp+1D8h+ProtocolReturnBuffer]
0x140070d84  mov     [rsp+1D8h+ReturnLength], rax; ProtocolReturnBuffer
0x140070d89  mov     r9d, 18h; SubmitBufferLength
0x140070d8f  lea     r8, [rsp+1D8h+ProtocolSubmitBuffer]; ProtocolSubmitBuffer
0x140070d97  mov     edx, [rsp+1D8h+AuthenticationPackage]; AuthenticationPackage
0x140070d9b  mov     rcx, [rsp+1D8h+LsaHandle]; LsaHandle
0x140070da0  call    cs:__imp_LsaCallAuthenticationPackage
0x140070da6  mov     r9d, eax
0x140070da9  test    eax, eax
0x140070dab  js      short loc_140070DDE
0x140070dad  cmp     [rsp+1D8h+var_188], r12d
0x140070db2  jl      short loc_140070DDE
0x140070db4  mov     rcx, cs:WPP_GLOBAL_Control
0x140070dbb  cmp     rcx, r13
0x140070dbe  jz      short loc_140070E0E
0x140070dc0  test    [rcx+1Ch], edi
0x140070dc3  jz      short loc_140070E0E
0x140070dc5  cmp     byte ptr [rcx+19h], 4
0x140070dc9  jb      short loc_140070E0E
0x140070dcb  mov     edx, 98h
0x140070dd0  mov     r8, rsi
0x140070dd3  mov     rcx, [rcx+10h]
0x140070dd7  call    WPP_SF_
0x140070ddc  jmp     short loc_140070E0E
0x140070dde  mov     rcx, cs:WPP_GLOBAL_Control
0x140070de5  cmp     rcx, r13
0x140070de8  jz      short loc_140070E0E
0x140070dea  test    [rcx+1Ch], edi
0x140070ded  jz      short loc_140070E0E
0x140070def  cmp     byte ptr [rcx+19h], 2
0x140070df3  jb      short loc_140070E0E
0x140070df5  mov     edx, 97h
0x140070dfa  mov     eax, [rsp+1D8h+var_188]
0x140070dfe  mov     dword ptr [rsp+1D8h+ReturnLength], eax
0x140070e02  mov     r8, rsi
0x140070e05  mov     rcx, [rcx+10h]
0x140070e09  call    WPP_SF_DD
0x140070e0e  mov     rcx, [rsp+1D8h+TokenHandle]; hObject
0x140070e16  call    cs:__imp_CloseHandle
0x140070e1c  mov     dword ptr [rsp+1D8h+var_148], r12d
0x140070e24  xor     edx, edx; Val
0x140070e26  lea     r8d, [rdx+5Ch]; Size
0x140070e2a  lea     rcx, [rsp+1D8h+var_148+4]; void *
0x140070e32  call    memset_0
0x140070e37  mov     [rsp+1D8h+var_184], r12d
0x140070e3c  mov     rdx, [r14+28h]
0x140070e40  mov     rcx, [rdx+0F0h]
0x140070e47  mov     rax, [rcx+10h]
0x140070e4b  mov     qword ptr [rsp+1D8h+var_148], rax
0x140070e53  mov     rax, [rcx+20h]
0x140070e57  mov     qword ptr [rsp+1D8h+var_148+8], rax
0x140070e5f  mov     rax, [rcx+28h]
0x140070e63  mov     qword ptr [rsp+1D8h+var_138], rax
0x140070e6b  mov     rax, [rcx+30h]
0x140070e6f  mov     qword ptr [rsp+1D8h+var_138+8], rax
0x140070e77  mov     eax, [rcx+98h]
0x140070e7d  mov     [rsp+1D8h+var_F0], eax
0x140070e84  mov     eax, [rdx+0FCh]
0x140070e8a  mov     dword ptr [rsp+1D8h+var_128], eax
  ... truncated ...
```
