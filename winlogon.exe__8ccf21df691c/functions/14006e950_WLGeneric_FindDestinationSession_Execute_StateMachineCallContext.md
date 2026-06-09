# WLGeneric_FindDestinationSession_Execute(_StateMachineCallContext *)

- ea: `0x14006e950`
- end: `0x1400708b1`
- name: `?WLGeneric_FindDestinationSession_Execute@@YAKPEAU_StateMachineCallContext@@@Z`
- size: `8033`
- prototype: `unsigned int __fastcall(struct _StateMachineCallContext *)`
- caller_count: `0`
- callee_count: `47`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x14000200c`
- `0x1400020b4`
- `0x140002178`
- `0x14000223c`
- `0x1400028cc`
- `0x140002948`
- `0x1400057f4`
- `0x1400060d0`
- `0x1400064b0`
- `0x140006970`
- `0x140016850`
- `0x140016a30`
- `0x140016f30`
- `0x14001a200`
- `0x14002aae0`
- `0x14002ba10`
- `0x140032414`
- `0x140032550`
- `0x1400333b0`
- `0x140037b00`
- `0x14003bfec`
- `0x14003d7d8`
- `0x14003e630`
- `0x140041c34`
- `0x140041fa8`
- `0x14004327c`
- `0x140044830`
- `0x14004d23c`
- `0x14004d74c`
- `0x14004d9f4`
- `0x14004df08`
- `0x14004eb98`
- `0x140053720`
- `0x1400544e0`
- `0x140056348`
- `0x1400690d0`
- `0x140069380`
- `0x14006a184`
- `0x14006e950`
- `0x1400899b8`
- `0x14008b96c`
- `0x14008c9d0`
- `0x14009a6cc`
- `0x14009a770`
- `0x14009aeb0`
- `0x14009b620`
- `0x1400a1010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ebc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ff8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070014`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ebc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14006ff8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140070014`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070166`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140070166`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006ffdc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14006ffdc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140070680`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140070680`
- `RPCRT4!I_RpcMapWin32Status` at `0x14007029c`
- `RPCRT4!I_RpcMapWin32Status` at `0x14007029c`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1400700d4`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1400704b1`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1400700d4`
- `SspiCli!LsaCallAuthenticationPackage` at `0x1400704b1`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserSessionInfo` at `0x14006ebf7`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeUserSessionInfo` at `0x14006ebf7`
- `ext-ms-win-session-winsta-l1-1-0!WinStationConnectAndLockDesktop` at `0x14006eb5f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationConnectAndLockDesktop` at `0x14006eb5f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006f387`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006f87f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006fcd8`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006f387`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006f87f`
- `ext-ms-win-session-winsta-l1-1-0!WinStationReportUIResult` at `0x14006fcd8`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x14006ff57`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x14006ff57`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetAllUserSessions` at `0x14006ead6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetAllUserSessions` at `0x14006ead6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x140070557`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreeMemory` at `0x140070557`
- `ext-ms-win-session-winsta-l1-1-0!WinStationNegotiateSession` at `0x14006ec91`
- `ext-ms-win-session-winsta-l1-1-0!WinStationNegotiateSession` at `0x14006ec91`

## string_xrefs

- `0x1400706f8`: `clientcore\ds\security\umstartup\winlogon\core\logon.cxx`

## pseudocode

```c
unsigned int __fastcall WLGeneric_FindDestinationSession_Execute(struct _StateMachineCallContext *a1)
{
  unsigned __int64 v1; // rbx
  CGlobalStore **v2; // rdi
  unsigned int v3; // r12d
  int v4; // r13d
  char v5; // r14
  CUser *v6; // rcx
  __int64 v7; // r9
  CUser *v8; // rcx
  DWORD LastError; // eax
  unsigned int v10; // eax
  int v11; // r9d
  ULONG v12; // ecx
  BOOL v13; // r14d
  int v14; // r9d
  ULONG SessionId; // ecx
  int v16; // r9d
  ULONG v17; // ecx
  int v18; // r9d
  ULONG v19; // ecx
  int v20; // eax
  int v21; // r9d
  unsigned int v22; // eax
  __int64 v23; // rcx
  int v24; // r9d
  ULONG v25; // ecx
  int v26; // r9d
  ULONG v27; // ecx
  __int64 v28; // rdx
  ULONG v29; // ecx
  unsigned int v30; // eax
  int v31; // r9d
  ULONG v32; // ecx
  int v33; // eax
  int v34; // eax
  int v35; // r9d
  unsigned int v36; // eax
  int v37; // r9d
  ULONG v38; // ecx
  int v39; // r9d
  ULONG v40; // ecx
  ULONG v41; // ecx
  unsigned int v42; // eax
  int v43; // r9d
  ULONG v44; // ecx
  int IsBoundToConsole; // eax
  int v46; // r9d
  int v47; // r8d
  unsigned int v48; // eax
  int v49; // r9d
  ULONG v50; // ecx
  int v51; // r9d
  ULONG v52; // ecx
  ULONG v53; // ecx
  unsigned int v54; // eax
  int v55; // r9d
  ULONG v56; // ecx
  CUser *v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // r9
  DWORD v60; // eax
  DWORD v61; // eax
  NTSTATUS v62; // eax
  CGlobalStore *v63; // rdx
  __int64 v64; // rcx
  RPC_STATUS updated; // eax
  unsigned int NegotiatePackage; // eax
  __int64 v67; // rdx
  NTSTATUS v68; // eax
  unsigned int v69; // r15d
  unsigned __int16 *v70; // rsi
  unsigned __int16 *String; // rbx
  CUser *v72; // rcx
  int v73; // eax
  CGlobalStore *v74; // rbx
  int v75; // eax
  int v76; // eax
  unsigned __int16 *v77; // rbx
  unsigned __int16 *v78; // rsi
  int v79; // eax
  CGlobalStore *v80; // rcx
  bool v81; // al
  unsigned __int16 v82; // cx
  int ReturnLength; // [rsp+20h] [rbp-528h]
  unsigned int v85; // [rsp+50h] [rbp-4F8h] BYREF
  int v86; // [rsp+54h] [rbp-4F4h]
  char v87; // [rsp+58h] [rbp-4F0h]
  unsigned __int16 *v88; // [rsp+60h] [rbp-4E8h] BYREF
  unsigned int v89; // [rsp+68h] [rbp-4E0h] BYREF
  unsigned int v90; // [rsp+6Ch] [rbp-4DCh] BYREF
  unsigned int v91; // [rsp+70h] [rbp-4D8h] BYREF
  unsigned int *v92; // [rsp+78h] [rbp-4D0h] BYREF
  char v93; // [rsp+80h] [rbp-4C8h]
  unsigned int v94; // [rsp+84h] [rbp-4C4h] BYREF
  int ProtocolStatus; // [rsp+88h] [rbp-4C0h] BYREF
  int v96; // [rsp+8Ch] [rbp-4BCh] BYREF
  int v97; // [rsp+90h] [rbp-4B8h] BYREF
  unsigned int v98; // [rsp+94h] [rbp-4B4h] BYREF
  unsigned __int16 *v99; // [rsp+98h] [rbp-4B0h] BYREF
  __int64 v100; // [rsp+A0h] [rbp-4A8h] BYREF
  unsigned int v101; // [rsp+A8h] [rbp-4A0h] BYREF
  DWORD v102; // [rsp+ACh] [rbp-49Ch] BYREF
  ULONG AuthenticationPackage; // [rsp+B0h] [rbp-498h] BYREF
  ULONG v104; // [rsp+B4h] [rbp-494h] BYREF
  void *v105; // [rsp+B8h] [rbp-490h] BYREF
  unsigned __int16 *v106; // [rsp+C0h] [rbp-488h] BYREF
  int v107; // [rsp+C8h] [rbp-480h]
  int v108; // [rsp+CCh] [rbp-47Ch] BYREF
  unsigned int v109; // [rsp+D0h] [rbp-478h]
  ULONG ReturnBufferLength; // [rsp+D4h] [rbp-474h] BYREF
  ULONG v111; // [rsp+D8h] [rbp-470h] BYREF
  LPCVOID lpData; // [rsp+E0h] [rbp-468h] BYREF
  HANDLE LsaHandle; // [rsp+E8h] [rbp-460h] BYREF
  HANDLE v114; // [rsp+F0h] [rbp-458h] BYREF
  BOOL v115; // [rsp+F8h] [rbp-450h]
  const wchar_t *v116; // [rsp+100h] [rbp-448h] BYREF
  __int64 v117; // [rsp+108h] [rbp-440h] BYREF
  PVOID ProtocolReturnBuffer; // [rsp+110h] [rbp-438h] BYREF
  __int64 v119; // [rsp+118h] [rbp-430h] BYREF
  __int64 v120; // [rsp+120h] [rbp-428h] BYREF
  __int64 v121; // [rsp+128h] [rbp-420h] BYREF
  const wchar_t *v122; // [rsp+130h] [rbp-418h] BYREF
  __int64 v123; // [rsp+138h] [rbp-410h] BYREF
  __int64 v124; // [rsp+140h] [rbp-408h] BYREF
  __int64 v125; // [rsp+148h] [rbp-400h] BYREF
  const wchar_t *v126; // [rsp+150h] [rbp-3F8h] BYREF
  __int64 v127; // [rsp+158h] [rbp-3F0h] BYREF
  __int64 v128; // [rsp+160h] [rbp-3E8h] BYREF
  __int64 v129; // [rsp+168h] [rbp-3E0h] BYREF
  const wchar_t *v130; // [rsp+170h] [rbp-3D8h] BYREF
  __int64 v131; // [rsp+178h] [rbp-3D0h] BYREF
  unsigned __int64 v132; // [rsp+180h] [rbp-3C8h] BYREF
  const wchar_t *v133; // [rsp+188h] [rbp-3C0h] BYREF
  unsigned __int64 v134; // [rsp+190h] [rbp-3B8h] BYREF
  const wchar_t *v135; // [rsp+198h] [rbp-3B0h] BYREF
  __int64 v136; // [rsp+1A0h] [rbp-3A8h] BYREF
  __int64 v137; // [rsp+1A8h] [rbp-3A0h] BYREF
  __int64 v138; // [rsp+1B0h] [rbp-398h] BYREF
  __int64 v139; // [rsp+1B8h] [rbp-390h] BYREF
  const wchar_t *v140; // [rsp+1C0h] [rbp-388h] BYREF
  unsigned __int64 v141; // [rsp+1C8h] [rbp-380h] BYREF
  const wchar_t *v142; // [rsp+1D0h] [rbp-378h] BYREF
  __int64 v143; // [rsp+1D8h] [rbp-370h] BYREF
  __int64 v144; // [rsp+1E0h] [rbp-368h] BYREF
  __int64 v145; // [rsp+1E8h] [rbp-360h] BYREF
  const wchar_t *v146; // [rsp+1F0h] [rbp-358h] BYREF
  __int64 v147; // [rsp+1F8h] [rbp-350h] BYREF
  __int64 v148; // [rsp+200h] [rbp-348h] BYREF
  const wchar_t *v149; // [rsp+208h] [rbp-340h] BYREF
  __int64 v150; // [rsp+210h] [rbp-338h] BYREF
  const unsigned __int16 *v151; // [rsp+218h] [rbp-330h] BYREF
  __int64 v152; // [rsp+220h] [rbp-328h] BYREF
  __int64 v153; // [rsp+228h] [rbp-320h] BYREF
  __int64 v154; // [rsp+230h] [rbp-318h] BYREF
  __int64 v155; // [rsp+238h] [rbp-310h] BYREF
  __int64 v156; // [rsp+240h] [rbp-308h] BYREF
  const wchar_t *v157; // [rsp+248h] [rbp-300h] BYREF
  unsigned __int64 v158; // [rsp+250h] [rbp-2F8h] BYREF
  const wchar_t *v159; // [rsp+258h] [rbp-2F0h] BYREF
  __int64 v160; // [rsp+260h] [rbp-2E8h] BYREF
  __int64 v161; // [rsp+268h] [rbp-2E0h] BYREF
  __int64 v162; // [rsp+270h] [rbp-2D8h] BYREF
  const wchar_t *v163; // [rsp+278h] [rbp-2D0h] BYREF
  __int64 v164; // [rsp+280h] [rbp-2C8h] BYREF
  unsigned __int64 v165; // [rsp+288h] [rbp-2C0h] BYREF
  const wchar_t *v166; // [rsp+290h] [rbp-2B8h] BYREF
  unsigned __int64 v167; // [rsp+298h] [rbp-2B0h] BYREF
  const unsigned __int16 *v168; // [rsp+2A0h] [rbp-2A8h] BYREF
  __int64 v169; // [rsp+2A8h] [rbp-2A0h] BYREF
  __int64 v170; // [rsp+2B0h] [rbp-298h] BYREF
  __int64 v171; // [rsp+2B8h] [rbp-290h] BYREF
  __int64 v172; // [rsp+2C0h] [rbp-288h] BYREF
  const wchar_t *v173; // [rsp+2C8h] [rbp-280h] BYREF
  unsigned __int64 v174; // [rsp+2D0h] [rbp-278h] BYREF
  const wchar_t *v175; // [rsp+2D8h] [rbp-270h] BYREF
  __int64 v176; // [rsp+2E0h] [rbp-268h] BYREF
  __int64 v177; // [rsp+2E8h] [rbp-260h] BYREF
  __int128 v178; // [rsp+2F0h] [rbp-258h] BYREF
  __int128 v179; // [rsp+300h] [rbp-248h]
  _BYTE v180[64]; // [rsp+310h] [rbp-238h]
  __int128 v181; // [rsp+350h] [rbp-1F8h] BYREF
  __int64 v182; // [rsp+360h] [rbp-1E8h]
  __int128 v183; // [rsp+370h] [rbp-1D8h] BYREF
  __int64 v184; // [rsp+380h] [rbp-1C8h]
  __int128 v185; // [rsp+390h] [rbp-1B8h] BYREF
  __int64 v186; // [rsp+3A0h] [rbp-1A8h]
  __int128 v187; // [rsp+3B0h] [rbp-198h] BYREF
  __int64 v188; // [rsp+3C0h] [rbp-188h]
  __int128 v189; // [rsp+3D0h] [rbp-178h] BYREF
  __int64 v190; // [rsp+3E0h] [rbp-168h]
  __int128 v191; // [rsp+3F0h] [rbp-158h] BYREF
  __int64 v192; // [rsp+400h] [rbp-148h]
  _OWORD v193[6]; // [rsp+410h] [rbp-138h] BYREF
  __int128 v194; // [rsp+470h] [rbp-D8h] BYREF
  __int128 v195; // [rsp+480h] [rbp-C8h] BYREF
  HANDLE TokenHandle; // [rsp+490h] [rbp-B8h]
  _BYTE ProtocolSubmitBuffer[24]; // [rsp+498h] [rbp-B0h] BYREF
  PVOID v198[2]; // [rsp+4B0h] [rbp-98h] BYREF
  int TokenInformation; // [rsp+4C0h] [rbp-88h] BYREF
  __int128 v200; // [rsp+4C4h] [rbp-84h]
  __int128 v201; // [rsp+4D4h] [rbp-74h]
  __int128 v202; // [rsp+4E4h] [rbp-64h]
  int v203; // [rsp+4F4h] [rbp-54h]
  wil::details::in1diag3 *retaddr; // [rsp+548h] [rbp+0h]

  LODWORD(v1) = 0;
  v2 = (CGlobalStore **)*((_QWORD *)a1 + 1);
  LODWORD(v106) = 0;
  v105 = 0;
  v85 = 0;
  v91 = 0;
  v92 = 0;
  v3 = -1;
  v101 = 0;
  LODWORD(v99) = 0;
  v90 = 0;
  v89 = 0;
  v98 = 0;
  LODWORD(v88) = 1;
  v4 = 0;
  v5 = 0;
  v87 = 0;
  lpData = (LPCVOID)*((_QWORD *)*v2 + 15);
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    v6 = WPP_GLOBAL_Control;
  }
  while ( 1 )
  {
    v7 = *((unsigned int *)v2[2] + 94);
    if ( (_DWORD)v7 )
    {
      if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
        WPP_SF_d(*((_QWORD *)v6 + 2), 113, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v7);
      if ( (unsigned __int8)IsWinStationConnectAndLockDesktopPresent(v6)
        && (unsigned __int8)IsWinStationConnectAndLockDesktopPresent(v6) )
      {
        v100 = 0;
        v94 = 0;
        if ( (unsigned __int8)WinStationGetAllUserSessions(0, *((_QWORD *)v2[4] + 20), &v100, &v94) )
        {
          v8 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v94);
          }
          if ( (unsigned __int8)IsWinStationConnectAndLockDesktopPresent(v8) )
          {
            if ( lpData )
              SetCredentialContextReg(lpData);
            if ( (unsigned __int8)WinStationConnectAndLockDesktop(0, *(unsigned int *)(v100 + 4)) )
            {
              v3 = *(_DWORD *)(v100 + 4);
              v109 = v3;
              v5 = 1;
              v87 = 1;
              v93 = 1;
              CSession::ResetAutoLock(v2[2], 2, v3);
            }
            else
            {
              if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                LastError = GetLastError();
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  115,
                  WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                  LastError);
              }
              CleanupCredentialContextReg();
            }
          }
          WinStationFreeUserSessionInfo(v100, v94);
          v100 = 0;
        }
        else
        {
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
          }
        }
      }
    }
    if ( v5 )
    {
      v85 = 2;
      goto LABEL_50;
    }
    if ( !(unsigned __int8)IsWinStationConnectAndLockDesktopPresent(v6) )
    {
      LODWORD(v1) = 0;
      v86 = 0;
      v85 = 1;
      goto LABEL_46;
    }
    v10 = WinStationNegotiateSession(&v105, *((_QWORD *)v2[4] + 17), &v85, &v91, &v92, &v101);
    v1 = v10;
    v86 = v10;
    if ( v10 )
      break;
LABEL_46:
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v85);
    }
LABEL_50:
    v194 = 0;
    WLGetTSActivityId(&v194);
    if ( (unsigned int)dword_1400CF778 > 5 )
    {
      SessionId = NtCurrentPeb()->SessionId;
      v119 = SessionId;
      v120 = v85;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        SessionId,
        (unsigned int)&dword_1400BC144,
        (unsigned int)&v194,
        v14,
        (__int64)&v120,
        (__int64)&v119);
    }
    switch ( v85 )
    {
      case 1u:
        LODWORD(v1) = 0;
        v97 = 0;
        v104 = 0;
        v111 = 0;
        v198[0] = 0;
        v114 = 0;
        v195 = 0;
        TokenHandle = 0;
        NegotiatePackage = CGlobalStore::GetLsaHandle(*v2, &v114);
        v86 = NegotiatePackage;
        if ( !NegotiatePackage )
        {
          NegotiatePackage = CGlobalStore::GetNegotiatePackage(*v2, &v104);
          v86 = NegotiatePackage;
          if ( NegotiatePackage )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_216;
            }
            v67 = 120;
LABEL_199:
            WPP_SF_d(*((_QWORD *)v6 + 2), v67, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, NegotiatePackage);
          }
          else
          {
            v195 = 0;
            TokenHandle = (HANDLE)0x200000000LL;
            LODWORD(v195) = 1026;
            *(_QWORD *)((char *)&v195 + 4) = *((_QWORD *)v2[4] + 16);
            v68 = LsaCallAuthenticationPackage(v114, v104, &v195, 0x18u, v198, &v111, &v97);
            if ( v68 < 0 || v97 < 0 )
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
              {
                goto LABEL_216;
              }
              WPP_SF_DD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                121,
                WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                (unsigned int)v68);
            }
            else
            {
              v6 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
                || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
                || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
              {
                goto LABEL_216;
              }
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 122, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
            }
          }
          v6 = WPP_GLOBAL_Control;
          goto LABEL_216;
        }
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v67 = 119;
          goto LABEL_199;
        }
LABEL_216:
        v86 = 0;
LABEL_217:
        v13 = (int)v88;
        goto LABEL_218;
      case 2u:
        WLEventWrite(&WLDiagEvt_LogonCancel_Stop);
        if ( !v5 && v91 && v92 )
        {
          v3 = *v92;
          v109 = *v92;
        }
        if ( v3 != -1 )
        {
          ProtocolStatus = 0;
          AuthenticationPackage = 0;
          ReturnBufferLength = 0;
          v102 = 0;
          ProtocolReturnBuffer = 0;
          LsaHandle = 0;
          TokenInformation = 0;
          v200 = 0;
          v201 = 0;
          v202 = 0;
          v203 = 0;
          v195 = 0;
          TokenHandle = 0;
          memset(ProtocolSubmitBuffer, 0, sizeof(ProtocolSubmitBuffer));
          LODWORD(v1) = CGlobalStore::GetLsaHandle(*v2, &LsaHandle);
          v86 = v1;
          if ( (_DWORD)v1 )
          {
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v58 = 123;
              goto LABEL_155;
            }
            goto LABEL_183;
          }
          LODWORD(v1) = CGlobalStore::GetNegotiatePackage(*v2, &AuthenticationPackage);
          v86 = v1;
          if ( (_DWORD)v1 )
          {
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_183;
            }
            v58 = 124;
LABEL_155:
            v59 = (unsigned int)v1;
            goto LABEL_166;
          }
          if ( (unsigned __int8)WinStationQueryInformationW(0, v3, 14, &v195, 24, &v102) )
          {
            if ( GetTokenInformation(TokenHandle, TokenStatistics, &TokenInformation, 0x38u, &v102) )
            {
              *(_OWORD *)ProtocolSubmitBuffer = 0;
              *(_QWORD *)&ProtocolSubmitBuffer[16] = 0x400000000LL;
              *(_DWORD *)ProtocolSubmitBuffer = 1026;
              *(_QWORD *)&ProtocolSubmitBuffer[4] = *((_QWORD *)v2[4] + 16);
              *(_QWORD *)&ProtocolSubmitBuffer[12] = *(_QWORD *)((char *)&v200 + 4);
              v62 = LsaCallAuthenticationPackage(
                      LsaHandle,
                      AuthenticationPackage,
                      ProtocolSubmitBuffer,
                      0x18u,
                      &ProtocolReturnBuffer,
                      &ReturnBufferLength,
                      &ProtocolStatus);
              if ( v62 < 0 || ProtocolStatus < 0 )
              {
                if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                  && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_DD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    127,
                    WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                    (unsigned int)v62);
                }
              }
              else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                     && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
              }
            }
            else if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
                   && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v61 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v61);
            }
            CloseHandle(TokenHandle);
            goto LABEL_183;
          }
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v60 = GetLastError();
            v58 = 125;
            v59 = v60;
            v57 = WPP_GLOBAL_Control;
LABEL_166:
            WPP_SF_d(*((_QWORD *)v57 + 2), v58, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v59);
          }
LABEL_183:
          LODWORD(v178) = 0;
          memset_0((char *)&v178 + 4, 0, 0x5Cu);
          v96 = 0;
          v63 = v2[4];
          v64 = *((_QWORD *)v63 + 30);
          *(_QWORD *)&v178 = *(_QWORD *)(v64 + 16);
          *((_QWORD *)&v178 + 1) = *(_QWORD *)(v64 + 32);
          v179 = *(_OWORD *)(v64 + 40);
          *(_DWORD *)&v180[56] = *(_DWORD *)(v64 + 152);
          *(_QWORD *)v180 = *(_QWORD *)((char *)v63 + 252);
          *(_OWORD *)&v180[8] = *((_OWORD *)v63 + 11);
          *(_OWORD *)&v180[24] = *((_OWORD *)v63 + 12);
          *(_OWORD *)&v180[40] = *((_OWORD *)v63 + 13);
          v193[0] = v178;
          v193[1] = v179;
          v193[2] = *(_OWORD *)v180;
          v193[3] = *(_OWORD *)&v180[16];
          v193[4] = *(_OWORD *)&v180[32];
          v193[5] = *(_OWORD *)&v180[48];
          updated = WmsgSendReconnectionUpdateMessage(v3, v193, &v96);
          if ( updated )
            v96 = I_RpcMapWin32Status(updated);
          if ( v96 >= 0 )
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
            {
              goto LABEL_217;
            }
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 130, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
          }
          else
          {
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
              || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_217;
            }
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              129,
              WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
              (unsigned int)v96);
          }
        }
LABEL_65:
        v6 = WPP_GLOBAL_Control;
        goto LABEL_217;
      case 3u:
        IsBoundToConsole = CSession::IsBoundToConsole(v2[2]);
        v187 = 0;
        v188 = 0;
        ToSetTimeout(IsBoundToConsole != 0 ? 120000 : 30000, &v187);
        v194 = 0;
        WLGetTSActivityId(&v194);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          v162 = NtCurrentPeb()->SessionId;
          v163 = L"TSReconnectOptions";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1400CF778,
            (unsigned int)byte_1400BC10B,
            (unsigned int)&v194,
            v46,
            (__int64)&v163,
            (__int64)&v162);
        }
        RecordBlackboxInfo(L"WluiDisplayTSReconnectOptions", 1, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        v48 = WluiDisplayTSReconnectOptions(v91, (_DWORD)v92, v47, (unsigned int)&v89, (__int64)&v99);
        v1 = v48;
        v86 = v48;
        RecordBlackboxInfo(L"WluiDisplayTSReconnectOptions", 0, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        ToResetTimeout();
        v194 = 0;
        WLGetTSActivityId(&v194);
        if ( (_DWORD)v1 )
        {
          if ( (unsigned int)dword_1400CF778 > 5 )
          {
            v50 = NtCurrentPeb()->SessionId;
            v164 = v50;
            v165 = v1;
            v166 = L"TSReconnectOptions";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v50,
              (unsigned int)byte_1400BC075,
              (unsigned int)&v194,
              v49,
              (__int64)&v166,
              (__int64)&v165,
              (__int64)&v164);
          }
          v194 = 0;
          WLGetTSActivityId(&v194);
          if ( (unsigned int)dword_1400CF778 > 5 )
          {
            v167 = v1;
            v168 = L"WluiDisplayTSReconnectOptions";
            v52 = NtCurrentPeb()->SessionId;
            v169 = v52;
            v170 = 2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
              v52,
              (unsigned int)qword_1400BC0B8,
              (unsigned int)&v194,
              v51,
              (__int64)&v170,
              (__int64)&v169,
              (__int64)&v168,
              (__int64)&v167);
          }
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = 131;
            goto LABEL_83;
          }
        }
        else
        {
          if ( (unsigned int)dword_1400CF778 > 5 )
          {
            v108 = (int)v99;
            v53 = NtCurrentPeb()->SessionId;
            v171 = v53;
            v172 = v89;
            v173 = L"TSReconnectOptions";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
              v53,
              (unsigned int)byte_1400BBFCD,
              (unsigned int)&v194,
              v49,
              (__int64)&v173,
              (__int64)&v172,
              (__int64)&v171,
              (__int64)&v108);
          }
          if ( !(unsigned __int8)((__int64 (*)(void))IsWinStationConnectAndLockDesktopPresent)() )
            goto LABEL_65;
          v54 = WinStationReportUIResult(v105, v89, (unsigned int)v99);
          v1 = v54;
          v86 = v54;
          if ( !v54 )
            goto LABEL_65;
          v194 = 0;
          WLGetTSActivityId(&v194);
          if ( (unsigned int)dword_1400CF778 > 5 )
          {
            v174 = v1;
            v175 = L"WinStationReportUIResult";
            v56 = NtCurrentPeb()->SessionId;
            v176 = v56;
            v177 = 2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
              v56,
              (unsigned int)word_1400BC022,
              (unsigned int)&v194,
              v55,
              (__int64)&v177,
              (__int64)&v176,
              (__int64)&v175,
              (__int64)&v174);
          }
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = 132;
LABEL_83:
            WPP_SF_d(*((_QWORD *)v6 + 2), v28, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, (unsigned int)v1);
            v6 = WPP_GLOBAL_Control;
          }
        }
LABEL_84:
        v85 = 2;
        goto LABEL_217;
      case 4u:
        v34 = CSession::IsBoundToConsole(v2[2]);
        v185 = 0;
        v186 = 0;
        ToSetTimeout(v34 != 0 ? 120000 : 30000, &v185);
        v194 = 0;
        WLGetTSActivityId(&v194);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          v145 = NtCurrentPeb()->SessionId;
          v146 = L"TSDisconnectOptions";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1400CF778,
            (unsigned int)&dword_1400BBF94,
            (unsigned int)&v194,
            v35,
            (__int64)&v146,
            (__int64)&v145);
        }
        RecordBlackboxInfo(L"WluiDisplayTSDisconnectOptions", 1, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        v89 = 2;
        v90 = -1;
        if ( (v101 & 4) != 0 )
          v36 = WluiDisplayTSDisconnectOptionsList(v91, v92, v101, &v89, &v90);
        else
          v36 = WluiDisplayTSDisconnectOptionsMessage(v91, v92, v101, &v89, &v90);
        LODWORD(v1) = v36;
        v86 = v36;
        RecordBlackboxInfo(L"WluiDisplayTSDisconnectOptions", 0, (struct _WLSM_GLOBAL_CONTEXT *)v2);
        ToResetTimeout();
        v194 = 0;
        WLGetTSActivityId(&v194);
        if ( (_DWORD)v1 )
        {
          if ( (unsigned int)dword_1400CF778 > 5 )
          {
            v38 = NtCurrentPeb()->SessionId;
            v147 = v38;
            v148 = (unsigned int)v1;
            v149 = L"TSDisconnectOptions";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              v38,
              (unsigned int)&word_1400BBEFE,
              (unsigned int)&v194,
              v37,
              (__int64)&v149,
              (__int64)&v148,
              (__int64)&v147);
          }
          v194 = 0;
          WLGetTSActivityId(&v194);
          if ( (unsigned int)dword_1400CF778 > 5 )
          {
            v150 = (unsigned int)v1;
            v151 = L"WluiDisplayTSDisconnectOptions";
            v40 = NtCurrentPeb()->SessionId;
            v152 = v40;
            v153 = 2;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
              v40,
              (unsigned int)&word_1400BBE56,
              (unsigned int)&v194,
              v39,
              (__int64)&v153,
              (__int64)&v152,
              (__int64)&v151,
              (__int64)&v150);
          }
          v6 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v28 = 133;
            goto LABEL_83;
          }
          goto LABEL_84;
        }
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          v154 = v90;
          v41 = NtCurrentPeb()->SessionId;
          v155 = v41;
          v156 = v89;
          v157 = L"TSDisconnectOptions";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
            v41,
            (unsigned int)byte_1400BBEA9,
            (unsigned int)&v194,
            v37,
            (__int64)&v157,
            (__int64)&v156,
            (__int64)&v155,
            (__int64)&v154);
        }
        if ( (unsigned __int8)((__int64 (*)(void))IsWinStationConnectAndLockDesktopPresent)() )
        {
          v42 = WinStationReportUIResult(v105, v89, v90);
          v1 = v42;
          v86 = v42;
          if ( v42 )
          {
            v194 = 0;
            WLGetTSActivityId(&v194);
            if ( (unsigned int)dword_1400CF778 > 5 )
            {
              v158 = v1;
              v159 = L"WinStationReportUIResult";
              v44 = NtCurrentPeb()->SessionId;
              v160 = v44;
              v161 = 2;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
                v44,
                (unsigned int)word_1400BBDCA,
                (unsigned int)&v194,
                v43,
                (__int64)&v161,
                (__int64)&v160,
                (__int64)&v159,
                (__int64)&v158);
            }
            v6 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                134,
                WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
                (unsigned int)v1);
              v6 = WPP_GLOBAL_Control;
            }
            v85 = 2;
            goto LABEL_217;
          }
        }
        LODWORD(v1) = DisplayWaitDisconnectStatusMessage((struct _WLSM_GLOBAL_CONTEXT *)v2, v90);
        v86 = v1;
LABEL_123:
        v4 = 1;
        v107 = 1;
        goto LABEL_65;
      case 5u:
        v33 = CSession::IsBoundToConsole(v2[2]);
        v183 = 0;
        v184 = 0;
        ToSetTimeout(v33 != 0 ? 120000 : 30000, &v183);
        WlDisplayMessageByResourceId(0x3E8u, 0x7E4u, 0x10u, &v98, v2[4]);
        ToResetTimeout();
        v85 = 2;
        LODWORD(v1) = 0;
        v86 = 0;
        goto LABEL_65;
    }
    if ( v85 != 6 )
    {
      if ( v85 != 7 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 137, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v85);
        }
        LODWORD(v1) = 87;
        v86 = 87;
        v85 = 2;
        v194 = 0;
        WLGetTSActivityId(&v194);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          v121 = 87;
          v122 = L"Invalid action code";
          v17 = NtCurrentPeb()->SessionId;
          v123 = v17;
          v124 = 2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v17,
            (unsigned int)word_1400BBC4A,
            (unsigned int)&v194,
            v16,
            (__int64)&v124,
            (__int64)&v123,
            (__int64)&v122,
            (__int64)&v121);
        }
        goto LABEL_65;
      }
      LODWORD(v1) = HandleSessionBusyOptions((struct _WLSM_GLOBAL_CONTEXT *)v2, v105, v91, *v92);
      if ( (v1 & 0x1FFF0000) == 0x70000 )
        LODWORD(v1) = (unsigned __int16)v1;
      v86 = v1;
      if ( (_DWORD)v1 )
      {
        v194 = 0;
        WLGetTSActivityId(&v194);
        if ( (unsigned int)dword_1400CF778 > 5 )
        {
          v125 = (unsigned int)v1;
          v126 = L"HandleSessionBusyOptions";
          v19 = NtCurrentPeb()->SessionId;
          v127 = v19;
          v128 = 2;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
            v19,
            (unsigned int)byte_1400BBF41,
            (unsigned int)&v194,
            v18,
            (__int64)&v128,
            (__int64)&v127,
            (__int64)&v126,
            (__int64)&v125);
        }
        v85 = 2;
        goto LABEL_65;
      }
      goto LABEL_123;
    }
    v20 = CSession::IsBoundToConsole(v2[2]);
    v181 = 0;
    v182 = 0;
    ToSetTimeout(v20 != 0 ? 120000 : 30000, &v181);
    v194 = 0;
    WLGetTSActivityId(&v194);
    if ( (unsigned int)dword_1400CF778 > 5 )
    {
      v129 = NtCurrentPeb()->SessionId;
      v130 = L"DisconnectRefused";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1400CF778,
        (unsigned int)byte_1400BBE1D,
        (unsigned int)&v194,
        v21,
        (__int64)&v130,
        (__int64)&v129);
    }
    v22 = DisplayDisconnectRefusedMessage((struct _WLSM_GLOBAL_CONTEXT *)v2, *v92);
    v1 = v22;
    v86 = v22;
    ToResetTimeout();
    v194 = 0;
    WLGetTSActivityId(&v194);
    if ( (_DWORD)v1 )
    {
      if ( (unsigned int)dword_1400CF778 > 5 )
      {
        v25 = NtCurrentPeb()->SessionId;
        v131 = v25;
        v132 = v1;
        v133 = L"DisconnectRefused";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          v25,
          (unsigned int)&dword_1400BBD34,
          (unsigned int)&v194,
          v24,
          (__int64)&v133,
          (__int64)&v132,
          (__int64)&v131);
      }
      v194 = 0;
      WLGetTSActivityId(&v194);
      if ( (unsigned int)dword_1400CF778 > 5 )
      {
        v134 = v1;
        v135 = L"DisplayDisconnectRefusedMessage";
        v27 = NtCurrentPeb()->SessionId;
        v136 = v27;
        v137 = 2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
          v27,
          (unsigned int)&byte_1400BBD77,
          (unsigned int)&v194,
          v26,
          (__int64)&v137,
          (__int64)&v136,
          (__int64)&v135,
          (__int64)&v134);
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v28 = 135;
        goto LABEL_83;
      }
      goto LABEL_84;
    }
    if ( (unsigned int)dword_1400CF778 > 5 )
    {
      v29 = NtCurrentPeb()->SessionId;
      v138 = v29;
      v139 = 1;
      v140 = L"DisconnectRefused";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
        v29,
        (unsigned int)byte_1400BBC9D,
        (unsigned int)&v194,
        v24,
        (__int64)&v140,
        (__int64)&v139,
        (__int64)&v138);
    }
    if ( !(unsigned __int8)IsWinStationConnectAndLockDesktopPresent(v23) )
      goto LABEL_65;
    v30 = WinStationReportUIResult(v105, 1, 0xFFFFFFFFLL);
    v1 = v30;
    v86 = v30;
    if ( !v30 )
      goto LABEL_65;
    v194 = 0;
    WLGetTSActivityId(&v194);
    if ( (unsigned int)dword_1400CF778 > 5 )
    {
      v141 = v1;
      v142 = L"WinStationReportUIResult";
      v32 = NtCurrentPeb()->SessionId;
      v143 = v32;
      v144 = 2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        v32,
        (unsigned int)byte_1400BBCE1,
        (unsigned int)&v194,
        v31,
        (__int64)&v144,
        (__int64)&v143,
        (__int64)&v142,
        (__int64)&v141);
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        136,
        WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
        (unsigned int)v1);
      v6 = WPP_GLOBAL_Control;
    }
    v85 = 2;
    v13 = v1 != 995;
    LODWORD(v88) = v13;
    v115 = v13;
LABEL_218:
    if ( v92 )
    {
      WinStationFreeMemory(v92);
      v92 = 0;
      v6 = WPP_GLOBAL_Control;
    }
    if ( v85 - 1 <= 1 )
      goto LABEL_221;
    v5 = v87;
  }
  *(_OWORD *)v198 = 0;
  WLGetTSActivityId(v198);
  if ( (unsigned int)dword_1400CF778 > 5 )
  {
    lpData = (LPCVOID)v1;
    v116 = L"WinStationNegotiateSession";
    v12 = NtCurrentPeb()->SessionId;
    v117 = v12;
    *(_QWORD *)&v194 = 2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v12,
      (unsigned int)byte_1400BC17D,
      (unsigned int)v198,
      v11,
      (__int64)&v194,
      (__int64)&v117,
      (__int64)&v116,
      (__int64)&lpData);
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      117,
      WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids,
      (unsigned int)v1);
    v6 = WPP_GLOBAL_Control;
  }
  v85 = 2;
  v13 = (int)v88;
LABEL_221:
  if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v6 + 2), 138, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids, v85);
    v6 = WPP_GLOBAL_Control;
  }
  if ( v85 == 2 )
  {
    v69 = 1;
    if ( (_DWORD)v1 && v13 )
    {
      v106 = 0;
      CUser::ImpersonateUser(v2[4], 0);
      v70 = MyFormatMessage(v1);
      String = AllocAndLoadString(0x3E8u, v2[4]);
      v106 = String;
      CUser::StopImpersonating(v72);
      if ( v70 )
      {
        v73 = CSession::IsBoundToConsole(v2[2]);
        v189 = 0;
        v190 = 0;
        ToSetTimeout(v73 != 0 ? 120000 : 30000, &v189);
        WlDisplayMessage(String, v70, 0x10u, &v98);
        ToResetTimeout();
        LocalFree(v70);
      }
      if ( String )
        UHHeapFree(&v106);
    }
    if ( v3 != -1 )
    {
      v74 = *v2;
      v75 = CSession::IsBoundToConsole(v2[2]);
      v76 = CGlobalStore::StopAndDeleteGlobalTraceLoggingActivity(
              (RTL_SRWLOCK *)v74,
              *((_DWORD *)v2[2] + 22),
              1,
              1,
              v75 == 0,
              0,
              0,
              0,
              0);
      if ( v76 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xD28,
          (unsigned int)"clientcore\\ds\\security\\umstartup\\winlogon\\core\\logon.cxx",
          (const char *)(unsigned int)v76,
          ReturnLength);
    }
  }
  else if ( *((_DWORD *)v2[2] + 57) )
  {
    v88 = 0;
    v99 = 0;
    if ( v6 != (CUser *)&WPP_GLOBAL_Control && (*((_DWORD *)v6 + 7) & 0x1000) != 0 && *((_BYTE *)v6 + 25) >= 2u )
      WPP_SF_(*((_QWORD *)v6 + 2), 139, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids);
    v77 = AllocAndLoadString(0x3E8u, v2[4]);
    v88 = v77;
    v78 = AllocAndLoadString(0x7EDu, v2[4]);
    v99 = v78;
    if ( v78 )
    {
      v79 = CSession::IsBoundToConsole(v2[2]);
      v191 = 0;
      v192 = 0;
      ToSetTimeout(v79 != 0 ? 120000 : 30000, &v191);
      WlDisplayMessage(v77, v78, 0x10u, &v98);
      ToResetTimeout();
      UHHeapFree(&v99);
    }
    if ( v77 )
      UHHeapFree(&v88);
    v80 = v2[4];
    if ( v80 )
      (**(void (__fastcall ***)(CGlobalStore *, __int64))v80)(v80, 1);
    v2[4] = 0;
    AsyncLogoffSupportSetUser(0);
    v69 = 24;
  }
  else
  {
    if ( v4 )
    {
      v81 = CloudPCHelpers::IsBootToCloudModeRegistryCheck(v6);
      v82 = 7140;
      if ( !v81 )
        v82 = 1002;
      WlDisplayStatusByResourceId(v82, 4u, 0x10u, 0);
    }
    CGlobalStore::TransferCredentialContextToTarget(*v2);
    v69 = (unsigned int)v106;
  }
  CGlobalStore::FreeCredentialContext(*v2, 0);
  return WlStateMachineSetSignal(v69, 0);
}

```

## disassembly

```asm
0x14006e950  mov     rax, rsp
0x14006e953  mov     [rax+10h], rbx
0x14006e957  mov     [rax+18h], rsi
0x14006e95b  push    rdi
0x14006e95c  push    r12
0x14006e95e  push    r13
0x14006e960  push    r14
0x14006e962  push    r15
0x14006e964  sub     rsp, 520h
0x14006e96b  movaps  xmmword ptr [rax-38h], xmm6
0x14006e96f  movaps  xmmword ptr [rax-48h], xmm7
0x14006e973  mov     rax, cs:__security_cookie
0x14006e97a  xor     rax, rsp
0x14006e97d  mov     [rsp+548h+var_50], rax
0x14006e985  xor     eax, eax
0x14006e987  mov     ebx, eax
0x14006e989  mov     rdi, [rcx+8]
0x14006e98d  mov     dword ptr [rsp+548h+var_488], eax
0x14006e994  mov     [rsp+548h+var_490], rax
0x14006e99c  mov     [rsp+548h+var_4F8], eax
0x14006e9a0  mov     [rsp+548h+var_4D8], eax
0x14006e9a4  mov     [rsp+548h+var_4D0], rax
0x14006e9a9  or      r12d, 0FFFFFFFFh
0x14006e9ad  mov     [rsp+548h+var_4A0], eax
0x14006e9b4  mov     dword ptr [rsp+548h+var_4B0], eax
0x14006e9bb  mov     [rsp+548h+var_4DC], eax
0x14006e9bf  mov     [rsp+548h+var_4E0], eax
0x14006e9c3  mov     [rsp+548h+var_4B4], eax
0x14006e9ca  mov     dword ptr [rsp+548h+var_4E8], 1
0x14006e9d2  mov     r13d, eax
0x14006e9d5  mov     r14b, al
0x14006e9d8  mov     [rsp+548h+var_4F0], al
0x14006e9dc  mov     rax, [rdi]
0x14006e9df  mov     rcx, [rax+78h]
0x14006e9e3  mov     [rsp+548h+lpData], rcx
0x14006e9eb  lea     rdx, WPP_GLOBAL_Control
0x14006e9f2  mov     rcx, cs:WPP_GLOBAL_Control
0x14006e9f9  mov     r15d, 4
0x14006e9ff  cmp     rcx, rdx
0x14006ea02  jz      short loc_14006EA3A
0x14006ea04  test    dword ptr [rcx+1Ch], 100h
0x14006ea0b  jz      short loc_14006EA3A
0x14006ea0d  lea     rsi, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14006ea14  cmp     [rcx+19h], r15b
0x14006ea18  jb      short loc_14006EA41
0x14006ea1a  lea     edx, [r15+6Ch]
0x14006ea1e  mov     r8, rsi
0x14006ea21  mov     rcx, [rcx+10h]
0x14006ea25  call    WPP_SF_
0x14006ea2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ea31  lea     rdx, WPP_GLOBAL_Control
0x14006ea38  jmp     short loc_14006EA41
0x14006ea3a  lea     rsi, WPP_c5e4d7264d013ec9a3e90eef35698a72_Traceguids
0x14006ea41  jmp     short loc_14006EA4F
0x14006ea43  mov     r14b, [rsp+548h+var_4F0]
0x14006ea48  lea     rdx, WPP_GLOBAL_Control
0x14006ea4f  mov     rax, [rdi+10h]
0x14006ea53  mov     r9d, [rax+178h]
0x14006ea5a  test    r9d, r9d
0x14006ea5d  jz      loc_14006EC3E
0x14006ea63  cmp     rcx, rdx
0x14006ea66  jz      short loc_14006EA88
0x14006ea68  test    dword ptr [rcx+1Ch], 1000h
0x14006ea6f  jz      short loc_14006EA88
0x14006ea71  cmp     [rcx+19h], r15b
0x14006ea75  jb      short loc_14006EA88
0x14006ea77  mov     edx, 71h ; 'q'
0x14006ea7c  mov     r8, rsi
0x14006ea7f  mov     rcx, [rcx+10h]
0x14006ea83  call    WPP_SF_d
0x14006ea88  call    IsWinStationConnectAndLockDesktopPresent
0x14006ea8d  test    al, al
0x14006ea8f  jz      loc_14006EC3E
0x14006ea95  call    IsWinStationConnectAndLockDesktopPresent
0x14006ea9a  test    al, al
0x14006ea9c  jz      loc_14006EC3E
0x14006eaa2  mov     [rsp+548h+var_4A8], 0
0x14006eaae  mov     [rsp+548h+var_4C4], 0
0x14006eab9  mov     rdx, [rdi+20h]
0x14006eabd  lea     r9, [rsp+548h+var_4C4]
0x14006eac5  lea     r8, [rsp+548h+var_4A8]
0x14006eacd  mov     rdx, [rdx+0A0h]
0x14006ead4  xor     ecx, ecx
0x14006ead6  call    cs:__imp_WinStationGetAllUserSessions
0x14006eadc  test    al, al
0x14006eade  jz      loc_14006EC0B
0x14006eae4  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eaeb  lea     rax, WPP_GLOBAL_Control
0x14006eaf2  cmp     rcx, rax
0x14006eaf5  jz      short loc_14006EB30
0x14006eaf7  test    dword ptr [rcx+1Ch], 1000h
0x14006eafe  jz      short loc_14006EB30
0x14006eb00  cmp     [rcx+19h], r15b
0x14006eb04  jb      short loc_14006EB30
0x14006eb06  mov     edx, 72h ; 'r'
0x14006eb0b  mov     rax, [rsp+548h+var_4A8]
0x14006eb13  mov     r8d, [rax+4]
0x14006eb17  mov     dword ptr [rsp+548h+ReturnLength], r8d
0x14006eb1c  mov     r9d, [rsp+548h+var_4C4]
0x14006eb24  mov     r8, rsi
0x14006eb27  mov     rcx, [rcx+10h]
0x14006eb2b  call    WPP_SF_DD
0x14006eb30  call    IsWinStationConnectAndLockDesktopPresent
0x14006eb35  test    al, al
0x14006eb37  jz      loc_14006EBE8
0x14006eb3d  mov     rax, [rsp+548h+lpData]
0x14006eb45  test    rax, rax
0x14006eb48  jz      short loc_14006EB52
0x14006eb4a  mov     rcx, rax; lpData
0x14006eb4d  call    ?SetCredentialContextReg@@YAXPEBG@Z; SetCredentialContextReg(ushort const *)
0x14006eb52  mov     rdx, [rsp+548h+var_4A8]
0x14006eb5a  mov     edx, [rdx+4]
0x14006eb5d  xor     ecx, ecx
0x14006eb5f  call    cs:__imp_WinStationConnectAndLockDesktop
0x14006eb65  test    al, al
0x14006eb67  jz      short loc_14006EBA0
0x14006eb69  mov     rax, [rsp+548h+var_4A8]
0x14006eb71  mov     r12d, [rax+4]
0x14006eb75  mov     [rsp+548h+var_478], r12d
0x14006eb7d  mov     r14b, 1
0x14006eb80  mov     [rsp+548h+var_4F0], r14b
0x14006eb85  mov     [rsp+548h+var_4C8], r14b
0x14006eb8d  mov     r8d, r12d
0x14006eb90  mov     edx, 2
0x14006eb95  mov     rcx, [rdi+10h]
0x14006eb99  call    ?ResetAutoLock@CSession@@QEAAXW4AutoLockStopReason@1@K@Z; CSession::ResetAutoLock(CSession::AutoLockStopReason,ulong)
0x14006eb9e  jmp     short loc_14006EBE8
0x14006eba0  mov     rax, cs:WPP_GLOBAL_Control
0x14006eba7  lea     rcx, WPP_GLOBAL_Control
0x14006ebae  cmp     rax, rcx
0x14006ebb1  jz      short loc_14006EBE3
0x14006ebb3  test    dword ptr [rax+1Ch], 1000h
0x14006ebba  jz      short loc_14006EBE3
0x14006ebbc  cmp     byte ptr [rax+19h], 2
0x14006ebc0  jb      short loc_14006EBE3
0x14006ebc2  call    cs:__imp_GetLastError
0x14006ebc8  mov     edx, 73h ; 's'
0x14006ebcd  mov     r9d, eax
0x14006ebd0  mov     r8, rsi
0x14006ebd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ebda  mov     rcx, [rcx+10h]
0x14006ebde  call    WPP_SF_d
0x14006ebe3  call    ?CleanupCredentialContextReg@@YAXXZ; CleanupCredentialContextReg(void)
0x14006ebe8  mov     edx, [rsp+548h+var_4C4]
0x14006ebef  mov     rcx, [rsp+548h+var_4A8]
0x14006ebf7  call    cs:__imp_WinStationFreeUserSessionInfo
0x14006ebfd  mov     [rsp+548h+var_4A8], 0
0x14006ec09  jmp     short loc_14006EC3E
0x14006ec0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ec12  lea     rax, WPP_GLOBAL_Control
0x14006ec19  cmp     rcx, rax
0x14006ec1c  jz      short loc_14006EC3E
0x14006ec1e  test    dword ptr [rcx+1Ch], 1000h
0x14006ec25  jz      short loc_14006EC3E
0x14006ec27  cmp     [rcx+19h], r15b
0x14006ec2b  jb      short loc_14006EC3E
0x14006ec2d  mov     edx, 74h ; 't'
0x14006ec32  mov     r8, rsi
0x14006ec35  mov     rcx, [rcx+10h]
0x14006ec39  call    WPP_SF_
0x14006ec3e  test    r14b, r14b
0x14006ec41  jz      short loc_14006EC50
0x14006ec43  mov     [rsp+548h+var_4F8], 2
0x14006ec4b  jmp     loc_14006EDEB
0x14006ec50  call    IsWinStationConnectAndLockDesktopPresent
0x14006ec55  test    al, al
0x14006ec57  jz      loc_14006ED9D
0x14006ec5d  mov     rdx, [rdi+20h]
0x14006ec61  lea     rax, [rsp+548h+var_4A0]
0x14006ec69  mov     [rsp+548h+ReturnBufferLength], rax
0x14006ec6e  lea     rax, [rsp+548h+var_4D0]
0x14006ec73  mov     [rsp+548h+ReturnLength], rax
0x14006ec78  lea     r9, [rsp+548h+var_4D8]
0x14006ec7d  lea     r8, [rsp+548h+var_4F8]
0x14006ec82  mov     rdx, [rdx+88h]
0x14006ec89  lea     rcx, [rsp+548h+var_490]
0x14006ec91  call    cs:__imp_WinStationNegotiateSession
0x14006ec97  mov     ebx, eax
0x14006ec99  mov     [rsp+548h+var_4F4], ebx
0x14006ec9d  test    eax, eax
0x14006ec9f  jz      loc_14006EDAB
0x14006eca5  xorps   xmm0, xmm0
0x14006eca8  movups  xmmword ptr [rsp+548h+var_98], xmm0
0x14006ecb0  lea     rcx, [rsp+548h+var_98]
0x14006ecb8  call    WLGetTSActivityId
0x14006ecbd  mov     ecx, cs:dword_1400CF778
0x14006ecc3  cmp     ecx, 5
0x14006ecc6  jbe     loc_14006ED4E
0x14006eccc  mov     [rsp+548h+lpData], rbx
0x14006ecd4  lea     rax, aWinstationnego_0; "WinStationNegotiateSession"
0x14006ecdb  mov     [rsp+548h+var_448], rax
0x14006ece3  mov     rax, gs:60h
0x14006ecec  mov     ecx, [rax+2C0h]
0x14006ecf2  mov     [rsp+548h+var_440], rcx
0x14006ecfa  mov     qword ptr [rsp+548h+var_D8], 2
0x14006ed06  lea     rax, [rsp+548h+lpData]
0x14006ed0e  mov     [rsp+548h+var_510], rax
0x14006ed13  lea     rax, [rsp+548h+var_448]
0x14006ed1b  mov     [rsp+548h+ProtocolStatus], rax
0x14006ed20  lea     rax, [rsp+548h+var_440]
0x14006ed28  mov     [rsp+548h+ReturnBufferLength], rax
0x14006ed2d  lea     rax, [rsp+548h+var_D8]
0x14006ed35  mov     [rsp+548h+ReturnLength], rax
0x14006ed3a  lea     r8, [rsp+548h+var_98]
0x14006ed42  lea     rdx, byte_1400BC17D
0x14006ed49  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14006ed4e  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ed55  lea     rax, WPP_GLOBAL_Control
0x14006ed5c  cmp     rcx, rax
0x14006ed5f  jz      short loc_14006ED8B
0x14006ed61  test    dword ptr [rcx+1Ch], 1000h
0x14006ed68  jz      short loc_14006ED8B
0x14006ed6a  cmp     byte ptr [rcx+19h], 2
0x14006ed6e  jb      short loc_14006ED8B
0x14006ed70  mov     edx, 75h ; 'u'
0x14006ed75  mov     r9d, ebx
0x14006ed78  mov     r8, rsi
0x14006ed7b  mov     rcx, [rcx+10h]
0x14006ed7f  call    WPP_SF_d
0x14006ed84  mov     rcx, cs:WPP_GLOBAL_Control
0x14006ed8b  mov     [rsp+548h+var_4F8], 2
0x14006ed93  mov     r14d, dword ptr [rsp+548h+var_4E8]
0x14006ed98  jmp     loc_14007057C
0x14006ed9d  xor     ebx, ebx
0x14006ed9f  mov     [rsp+548h+var_4F4], ebx
0x14006eda3  mov     [rsp+548h+var_4F8], 1
0x14006edab  mov     rcx, cs:WPP_GLOBAL_Control
0x14006edb2  lea     rax, WPP_GLOBAL_Control
0x14006edb9  cmp     rcx, rax
0x14006edbc  jz      short loc_14006EDEB
0x14006edbe  test    dword ptr [rcx+1Ch], 1000h
0x14006edc5  jz      short loc_14006EDEB
0x14006edc7  cmp     [rcx+19h], r15b
0x14006edcb  jb      short loc_14006EDEB
0x14006edcd  mov     edx, 76h ; 'v'
0x14006edd2  mov     eax, [rsp+548h+var_4D8]
0x14006edd6  mov     dword ptr [rsp+548h+ReturnLength], eax
0x14006edda  mov     r9d, [rsp+548h+var_4F8]
0x14006eddf  mov     r8, rsi
0x14006ede2  mov     rcx, [rcx+10h]
0x14006ede6  call    WPP_SF_DD
0x14006edeb  xorps   xmm0, xmm0
0x14006edee  movups  [rsp+548h+var_D8], xmm0
0x14006edf6  lea     rcx, [rsp+548h+var_D8]
0x14006edfe  call    WLGetTSActivityId
0x14006ee03  mov     eax, cs:dword_1400CF778
0x14006ee09  cmp     eax, 5
0x14006ee0c  jbe     short loc_14006EE5F
0x14006ee0e  mov     rax, gs:60h
0x14006ee17  mov     ecx, [rax+2C0h]
0x14006ee1d  mov     [rsp+548h+var_430], rcx
0x14006ee25  mov     eax, [rsp+548h+var_4F8]
0x14006ee29  mov     [rsp+548h+var_428], rax
0x14006ee31  lea     rax, [rsp+548h+var_430]
0x14006ee39  mov     [rsp+548h+ReturnBufferLength], rax
0x14006ee3e  lea     rax, [rsp+548h+var_428]
0x14006ee46  mov     [rsp+548h+ReturnLength], rax
0x14006ee4b  lea     r8, [rsp+548h+var_D8]
0x14006ee53  lea     rdx, dword_1400BC144
0x14006ee5a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x14006ee5f  mov     r9d, [rsp+548h+var_4F8]
0x14006ee64  mov     eax, r9d
0x14006ee67  sub     eax, 1
0x14006ee6a  jz      loc_14007033E
0x14006ee70  sub     eax, 1
0x14006ee73  jz      loc_14006FDCD
0x14006ee79  sub     eax, 1
0x14006ee7c  jz      loc_14006F9A0
0x14006ee82  sub     eax, 1
0x14006ee85  jz      loc_14006F527
0x14006ee8b  sub     eax, 1
0x14006ee8e  jz      loc_14006F4A8
0x14006ee94  sub     eax, 1
0x14006ee97  jz      loc_14006F095
0x14006ee9d  cmp     eax, 1
0x14006eea0  jz      loc_14006EFA3
0x14006eea6  mov     rcx, cs:WPP_GLOBAL_Control
0x14006eead  lea     rax, WPP_GLOBAL_Control
0x14006eeb4  cmp     rcx, rax
0x14006eeb7  jz      short loc_14006EED9
0x14006eeb9  test    dword ptr [rcx+1Ch], 1000h
0x14006eec0  jz      short loc_14006EED9
0x14006eec2  cmp     byte ptr [rcx+19h], 2
0x14006eec6  jb      short loc_14006EED9
0x14006eec8  mov     edx, 89h
0x14006eecd  mov     r8, rsi
0x14006eed0  mov     rcx, [rcx+10h]
0x14006eed4  call    WPP_SF_d
0x14006eed9  mov     r14d, 57h ; 'W'
0x14006eedf  mov     ebx, r14d
0x14006eee2  mov     [rsp+548h+var_4F4], ebx
0x14006eee6  mov     [rsp+548h+var_4F8], 2
0x14006eeee  xorps   xmm0, xmm0
0x14006eef1  movups  [rsp+548h+var_D8], xmm0
0x14006eef9  lea     rcx, [rsp+548h+var_D8]
0x14006ef01  call    WLGetTSActivityId
0x14006ef06  mov     eax, cs:dword_1400CF778
0x14006ef0c  cmp     eax, 5
0x14006ef0f  jbe     loc_14006EF97
0x14006ef15  mov     [rsp+548h+var_420], r14
  ... truncated ...
```
