# Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(void)

- ea: `0x18003ef60`
- end: `0x18003f41c`
- name: `?GetMostPreferredLoggedOnSessionToken@CallerToken@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ`
- size: `1212`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180021e80`
- `0x180055614`
- `0x180057520`

## callees

- `0x180007660`
- `0x18000856c`
- `0x180011840`
- `0x180011944`
- `0x180011a38`
- `0x180011b50`
- `0x1800209fc`
- `0x180023a18`
- `0x18003ef60`
- `0x18003f424`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f1d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f2d6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f05e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f1ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f2e9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f05e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f1ea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003f2e9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f1ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f1e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f2e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f1ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f1e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f2e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003f360`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18003f32e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18003f32e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18003f299`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18003f299`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003f301`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18003f301`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18003f224`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18003f224`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18003f072`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18003f1fe`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18003f072`
- `ext-ms-win-session-usertoken-l1-1-0!QueryUserToken` at `0x18003f1fe`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18003efe8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsExW` at `0x18003efe8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18003f196`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18003f1c2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18003f196`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18003f1c2`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18003f0b6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18003f11e`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18003f0b6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationQueryInformationW` at `0x18003f11e`

## string_xrefs

- `0x18003f3a3`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\callertoken.cpp`
- `0x18003f3b8`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\callertoken.cpp`
- `0x18003f3c9`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\callertoken.cpp`
- `0x18003f3de`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\callertoken.cpp`
- `0x18003f3f5`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\callertoken.cpp`
- `0x18003f409`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\callertoken.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
HANDLE *__fastcall Windows::CallerToken::GetMostPreferredLoggedOnSessionToken(HANDLE *a1)
{
  char *v2; // rdi
  int v3; // r12d
  const char *v4; // r9
  DWORD v5; // r8d
  PWTS_SESSION_INFO_1W v6; // r14
  int v7; // r15d
  struct _WTS_SESSION_INFO_1W *v8; // r13
  DWORD v9; // ebx
  DWORD SessionId; // ebx
  DWORD v11; // ebx
  HANDLE v13; // r14
  DWORD v14; // ebx
  const char *v15; // r9
  const char *v16; // r9
  int v17; // eax
  DWORD LastError; // ebx
  int v19; // eax
  int pCount; // [rsp+20h] [rbp-558h]
  HANDLE v21; // [rsp+30h] [rbp-548h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-540h] BYREF
  int v23; // [rsp+3Ch] [rbp-53Ch] BYREF
  DWORD NumberOfEntries; // [rsp+40h] [rbp-538h] BYREF
  PWTS_SESSION_INFO_1W ppSessionInfo; // [rsp+48h] [rbp-530h] BYREF
  DWORD pLevel; // [rsp+50h] [rbp-528h] BYREF
  int v27; // [rsp+54h] [rbp-524h] BYREF
  int v28; // [rsp+58h] [rbp-520h] BYREF
  HANDLE hObject; // [rsp+60h] [rbp-518h]
  HANDLE *v30; // [rsp+68h] [rbp-510h]
  _BYTE v31[12]; // [rsp+70h] [rbp-508h] BYREF
  int v32; // [rsp+7Ch] [rbp-4FCh]
  int v33; // [rsp+80h] [rbp-4F8h]
  wil::details::in1diag3 *retaddr; // [rsp+578h] [rbp+0h]

  v30 = a1;
  v2 = 0;
  v21 = 0;
  if ( !(unsigned __int8)IsQueryActiveSessionPresent() )
  {
    if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
    {
      v23 = 0;
      ppSessionInfo = 0;
      v17 = UMgrEnumerateSessionUsers(&v23, &ppSessionInfo);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\callertoken.cpp",
          (const char *)(unsigned int)v17,
          pCount);
      if ( v23 != 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBD,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\callertoken.cpp",
          (const char *)0x8000FFFFLL,
          pCount);
      if ( (char *)v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        LastError = GetLastError();
        CloseHandle(v21);
        SetLastError(LastError);
      }
      v21 = 0;
      v19 = UMgrQueryUserToken(*(_QWORD *)&ppSessionInfo->ExecEnvId, &v21);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBF,
          (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\callertoken.cpp",
          (const char *)(unsigned int)v19,
          pCount);
      *a1 = v21;
      v21 = 0;
      if ( ppSessionInfo )
      {
        UMgrFreeSessionUsers();
        v2 = (char *)v21;
      }
      if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(v2);
      return a1;
    }
    else
    {
      if ( (char *)v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v21);
      *a1 = 0;
      return a1;
    }
  }
  v3 = -1;
  v22 = -1;
  if ( !(unsigned __int8)IsWTSEnumerateSessionsWPresent() )
  {
    if ( !(unsigned __int8)IsQueryActiveSessionPresent() )
    {
      *a1 = 0;
      if ( (char *)v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(v21);
      return a1;
    }
    if ( !(unsigned int)QueryActiveSession(&v22) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\callertoken.cpp",
        v16);
LABEL_37:
    v13 = v21;
    if ( (char *)v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v14 = GetLastError();
      CloseHandle(v13);
      SetLastError(v14);
    }
    v21 = 0;
    if ( !(unsigned int)QueryUserToken(v22, &v21) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\callertoken.cpp",
        v15);
    *a1 = v21;
    return a1;
  }
  NumberOfEntries = 0;
  pLevel = 1;
  ppSessionInfo = 0;
  if ( !WTSEnumerateSessionsExW(0, &pLevel, 0, &ppSessionInfo, &NumberOfEntries) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\callertoken.cpp",
      v4);
  v5 = NumberOfEntries;
  v6 = ppSessionInfo;
  if ( !ppSessionInfo && NumberOfEntries )
    gsl::details::terminate(retaddr);
  v7 = -1;
  v8 = &ppSessionInfo[NumberOfEntries];
  if ( ppSessionInfo == v8 )
    goto LABEL_28;
  while ( 1 )
  {
    if ( !v6->SessionId )
      goto LABEL_24;
    hObject = v21;
    if ( (char *)v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v9 = GetLastError();
      CloseHandle(hObject);
      SetLastError(v9);
    }
    v21 = 0;
    if ( !(unsigned int)QueryUserToken(v6->SessionId, &v21) )
      goto LABEL_24;
    SessionId = v6->SessionId;
    if ( !(unsigned __int8)IsWinStationQueryInformationWPresent() )
      break;
    v27 = 0;
    v23 = 0;
    if ( !(unsigned __int8)WinStationQueryInformationW(0, SessionId, 39, &v23, 4, &v27) || v23 != 5 && v23 != 6 )
      break;
    if ( v7 != -1 )
      break;
    v7 = v6->SessionId;
LABEL_24:
    if ( ++v6 == v8 )
      goto LABEL_27;
  }
  v11 = v6->SessionId;
  if ( !(unsigned __int8)IsWinStationQueryInformationWPresent()
    || (v28 = 0, memset_0(v31, 0, 0x4C8u), !(unsigned __int8)WinStationQueryInformationW(0, v11, 40, v31, 1224, &v28))
    || v32
    || v33 != 1
    || v22 != -1 )
  {
    if ( v3 == -1 )
      v3 = v6->SessionId;
    goto LABEL_24;
  }
  v22 = v6->SessionId;
LABEL_27:
  v6 = ppSessionInfo;
  v5 = NumberOfEntries;
LABEL_28:
  if ( v22 != -1 )
  {
LABEL_36:
    WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, v6, v5);
    goto LABEL_37;
  }
  if ( v3 != -1 )
  {
    v22 = v3;
    goto LABEL_36;
  }
  if ( v7 != -1 )
  {
    v22 = v7;
    goto LABEL_36;
  }
  *a1 = 0;
  WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, v6, v5);
  if ( (char *)v21 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(v21);
  return a1;
}

```

## disassembly

```asm
0x18003ef60  mov     [rsp+arg_8], rbx
0x18003ef65  mov     [rsp+arg_10], rsi
0x18003ef6a  push    rdi
0x18003ef6b  push    r12
0x18003ef6d  push    r13
0x18003ef6f  push    r14
0x18003ef71  push    r15
0x18003ef73  sub     rsp, 550h
0x18003ef7a  mov     rax, cs:__security_cookie
0x18003ef81  xor     rax, rsp
0x18003ef84  mov     [rsp+578h+var_38], rax
0x18003ef8c  mov     rsi, rcx
0x18003ef8f  mov     [rsp+578h+var_510], rcx
0x18003ef94  xor     edi, edi
0x18003ef96  mov     [rsp+578h+var_548], rdi
0x18003ef9b  call    IsQueryActiveSessionPresent
0x18003efa0  test    al, al
0x18003efa2  jz      loc_18003F26C
0x18003efa8  or      r12d, 0FFFFFFFFh
0x18003efac  mov     [rsp+578h+var_540], r12d
0x18003efb1  call    IsWTSEnumerateSessionsWPresent
0x18003efb6  test    al, al
0x18003efb8  jz      loc_18003F216
0x18003efbe  mov     [rsp+578h+NumberOfEntries], edi
0x18003efc2  mov     [rsp+578h+pLevel], 1
0x18003efca  mov     [rsp+578h+ppSessionInfo], rdi
0x18003efcf  lea     rax, [rsp+578h+NumberOfEntries]
0x18003efd4  mov     [rsp+578h+pCount], rax; pCount
0x18003efd9  lea     r9, [rsp+578h+ppSessionInfo]; ppSessionInfo
0x18003efde  xor     r8d, r8d; Filter
0x18003efe1  lea     rdx, [rsp+578h+pLevel]; pLevel
0x18003efe6  xor     ecx, ecx; hServer
0x18003efe8  call    cs:__imp_WTSEnumerateSessionsExW
0x18003efee  mov     rcx, [rsp+578h]; this
0x18003eff6  test    eax, eax
0x18003eff8  jz      loc_18003F3A3
0x18003effe  mov     r8d, [rsp+578h+NumberOfEntries]
0x18003f003  mov     eax, r8d
0x18003f006  mov     r14, [rsp+578h+ppSessionInfo]
0x18003f00b  test    r14, r14
0x18003f00e  jnz     short loc_18003F019
0x18003f010  test    r8d, r8d
0x18003f013  jnz     loc_18003F3B2
0x18003f019  mov     r15d, r12d
0x18003f01c  imul    r13, rax, 38h ; '8'
0x18003f020  add     r13, r14
0x18003f023  cmp     r14, r13
0x18003f026  jz      loc_18003F16A
0x18003f02c  cmp     [r14+8], edi
0x18003f030  jz      loc_18003F149
0x18003f036  mov     rax, [rsp+578h+var_548]
0x18003f03b  mov     [rsp+578h+hObject], rax
0x18003f040  dec     rax
0x18003f043  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f047  ja      short loc_18003F064
0x18003f049  call    cs:__imp_GetLastError
0x18003f04f  mov     ebx, eax
0x18003f051  mov     rcx, [rsp+578h+hObject]; hObject
0x18003f056  call    cs:__imp_CloseHandle
0x18003f05c  mov     ecx, ebx; dwErrCode
0x18003f05e  call    cs:__imp_SetLastError
0x18003f064  mov     [rsp+578h+var_548], rdi
0x18003f069  lea     rdx, [rsp+578h+var_548]
0x18003f06e  mov     ecx, [r14+8]
0x18003f072  call    cs:__imp_QueryUserToken
0x18003f078  test    eax, eax
0x18003f07a  jz      loc_18003F149
0x18003f080  mov     ebx, [r14+8]
0x18003f084  call    IsWinStationQueryInformationWPresent
0x18003f089  test    al, al
0x18003f08b  jz      short loc_18003F0DA
0x18003f08d  mov     [rsp+578h+var_524], edi
0x18003f091  mov     [rsp+578h+var_53C], edi
0x18003f095  lea     rax, [rsp+578h+var_524]
0x18003f09a  mov     [rsp+578h+var_550], rax
0x18003f09f  mov     dword ptr [rsp+578h+pCount], 4
0x18003f0a7  lea     r9, [rsp+578h+var_53C]
0x18003f0ac  mov     r8d, 27h ; '''
0x18003f0b2  mov     edx, ebx
0x18003f0b4  xor     ecx, ecx
0x18003f0b6  call    cs:__imp_WinStationQueryInformationW
0x18003f0bc  test    al, al
0x18003f0be  jz      short loc_18003F0DA
0x18003f0c0  mov     ecx, [rsp+578h+var_53C]
0x18003f0c4  sub     ecx, 5
0x18003f0c7  jz      short loc_18003F0CE
0x18003f0c9  cmp     ecx, 1
0x18003f0cc  jnz     short loc_18003F0DA
0x18003f0ce  cmp     r15d, 0FFFFFFFFh
0x18003f0d2  jnz     short loc_18003F0DA
0x18003f0d4  mov     r15d, [r14+8]
0x18003f0d8  jmp     short loc_18003F149
0x18003f0da  mov     ebx, [r14+8]
0x18003f0de  call    IsWinStationQueryInformationWPresent
0x18003f0e3  test    al, al
0x18003f0e5  jz      short loc_18003F13F
0x18003f0e7  mov     [rsp+578h+var_520], edi
0x18003f0eb  xor     edx, edx; Val
0x18003f0ed  mov     r8d, 4C8h; Size
0x18003f0f3  lea     rcx, [rsp+578h+var_508]; void *
0x18003f0f8  call    memset_0
0x18003f0fd  lea     rax, [rsp+578h+var_520]
0x18003f102  mov     [rsp+578h+var_550], rax
0x18003f107  mov     dword ptr [rsp+578h+pCount], 4C8h
0x18003f10f  lea     r9, [rsp+578h+var_508]
0x18003f114  mov     r8d, 28h ; '('
0x18003f11a  mov     edx, ebx
0x18003f11c  xor     ecx, ecx
0x18003f11e  call    cs:__imp_WinStationQueryInformationW
0x18003f124  test    al, al
0x18003f126  jz      short loc_18003F13F
0x18003f128  cmp     [rsp+578h+var_4FC], edi
0x18003f12c  jnz     short loc_18003F13F
0x18003f12e  cmp     [rsp+578h+var_4F8], 1
0x18003f136  jnz     short loc_18003F13F
0x18003f138  cmp     [rsp+578h+var_540], 0FFFFFFFFh
0x18003f13d  jz      short loc_18003F158
0x18003f13f  cmp     r12d, 0FFFFFFFFh
0x18003f143  jnz     short loc_18003F149
0x18003f145  mov     r12d, [r14+8]
0x18003f149  add     r14, 38h ; '8'
0x18003f14d  cmp     r14, r13
0x18003f150  jnz     loc_18003F02C
0x18003f156  jmp     short loc_18003F160
0x18003f158  mov     eax, [r14+8]
0x18003f15c  mov     [rsp+578h+var_540], eax
0x18003f160  mov     r14, [rsp+578h+ppSessionInfo]
0x18003f165  mov     r8d, [rsp+578h+NumberOfEntries]; NumberOfEntries
0x18003f16a  or      eax, 0FFFFFFFFh
0x18003f16d  cmp     [rsp+578h+var_540], eax
0x18003f171  jnz     short loc_18003F1BA
0x18003f173  cmp     r12d, eax
0x18003f176  jz      short loc_18003F17F
0x18003f178  mov     [rsp+578h+var_540], r12d
0x18003f17d  jmp     short loc_18003F1BA
0x18003f17f  cmp     r15d, eax
0x18003f182  jz      short loc_18003F18B
0x18003f184  mov     [rsp+578h+var_540], r15d
0x18003f189  jmp     short loc_18003F1BA
0x18003f18b  mov     [rsi], rdi
0x18003f18e  mov     rdx, r14; pMemory
0x18003f191  mov     ecx, 2; WTSTypeClass
0x18003f196  call    cs:__imp_WTSFreeMemoryExW
0x18003f19c  nop
0x18003f19d  mov     rcx, [rsp+578h+var_548]; hObject
0x18003f1a2  lea     rdx, [rcx-1]
0x18003f1a6  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003f1aa  ja      short loc_18003F1B2
0x18003f1ac  call    cs:__imp_CloseHandle
0x18003f1b2  mov     rax, rsi
0x18003f1b5  jmp     loc_18003F376
0x18003f1ba  mov     rdx, r14; pMemory
0x18003f1bd  mov     ecx, 2; WTSTypeClass
0x18003f1c2  call    cs:__imp_WTSFreeMemoryExW
0x18003f1c8  mov     r14, [rsp+578h+var_548]
0x18003f1cd  lea     rax, [r14-1]
0x18003f1d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f1d5  ja      short loc_18003F1F0
0x18003f1d7  call    cs:__imp_GetLastError
0x18003f1dd  mov     ebx, eax
0x18003f1df  mov     rcx, r14; hObject
0x18003f1e2  call    cs:__imp_CloseHandle
0x18003f1e8  mov     ecx, ebx; dwErrCode
0x18003f1ea  call    cs:__imp_SetLastError
0x18003f1f0  mov     [rsp+578h+var_548], rdi
0x18003f1f5  lea     rdx, [rsp+578h+var_548]
0x18003f1fa  mov     ecx, [rsp+578h+var_540]
0x18003f1fe  call    cs:__imp_QueryUserToken
0x18003f204  mov     rcx, [rsp+578h]; this
0x18003f20c  test    eax, eax
0x18003f20e  jz      loc_18003F3B8
0x18003f214  jmp     short loc_18003F23C
0x18003f216  call    IsQueryActiveSessionPresent
0x18003f21b  test    al, al
0x18003f21d  jz      short loc_18003F24C
0x18003f21f  lea     rcx, [rsp+578h+var_540]
0x18003f224  call    cs:__imp_QueryActiveSession
0x18003f22a  mov     rcx, [rsp+578h]; this
0x18003f232  test    eax, eax
0x18003f234  jz      loc_18003F3C9
0x18003f23a  jmp     short loc_18003F1C8
0x18003f23c  mov     rax, [rsp+578h+var_548]
0x18003f241  mov     [rsi], rax
0x18003f244  mov     rax, rsi
0x18003f247  jmp     loc_18003F376
0x18003f24c  mov     [rsi], rdi
0x18003f24f  mov     rcx, [rsp+578h+var_548]; hObject
0x18003f254  lea     rax, [rcx-1]
0x18003f258  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f25c  ja      short loc_18003F264
0x18003f25e  call    cs:__imp_CloseHandle
0x18003f264  mov     rax, rsi
0x18003f267  jmp     loc_18003F376
0x18003f26c  call    IsUMgrEnumerateSessionUsersPresent
0x18003f271  test    al, al
0x18003f273  jz      loc_18003F351
0x18003f279  call    IsUMgrEnumerateSessionUsersPresent
0x18003f27e  test    al, al
0x18003f280  jz      loc_18003F351
0x18003f286  mov     [rsp+578h+var_53C], edi
0x18003f28a  mov     [rsp+578h+ppSessionInfo], rdi
0x18003f28f  lea     rdx, [rsp+578h+ppSessionInfo]
0x18003f294  lea     rcx, [rsp+578h+var_53C]
0x18003f299  call    cs:__imp_UMgrEnumerateSessionUsers
0x18003f29f  mov     rcx, [rsp+578h]; this
0x18003f2a7  test    eax, eax
0x18003f2a9  js      loc_18003F3DB
0x18003f2af  cmp     [rsp+578h+var_53C], 1
0x18003f2b4  setnz   al
0x18003f2b7  mov     rcx, [rsp+578h]; this
0x18003f2bf  test    al, al
0x18003f2c1  jnz     loc_18003F3EF
0x18003f2c7  mov     r14, [rsp+578h+var_548]
0x18003f2cc  lea     rax, [r14-1]
0x18003f2d0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f2d4  ja      short loc_18003F2EF
0x18003f2d6  call    cs:__imp_GetLastError
0x18003f2dc  mov     ebx, eax
0x18003f2de  mov     rcx, r14; hObject
0x18003f2e1  call    cs:__imp_CloseHandle
0x18003f2e7  mov     ecx, ebx; dwErrCode
0x18003f2e9  call    cs:__imp_SetLastError
0x18003f2ef  mov     [rsp+578h+var_548], rdi
0x18003f2f4  lea     rdx, [rsp+578h+var_548]
0x18003f2f9  mov     rcx, [rsp+578h+ppSessionInfo]
0x18003f2fe  mov     rcx, [rcx]
0x18003f301  call    cs:__imp_UMgrQueryUserToken
0x18003f307  mov     rcx, [rsp+578h]; this
0x18003f30f  test    eax, eax
0x18003f311  js      loc_18003F406
0x18003f317  mov     rax, [rsp+578h+var_548]
0x18003f31c  mov     [rsi], rax
0x18003f31f  mov     [rsp+578h+var_548], rdi
0x18003f324  mov     rcx, [rsp+578h+ppSessionInfo]
0x18003f329  test    rcx, rcx
0x18003f32c  jz      short loc_18003F339
0x18003f32e  call    cs:__imp_UMgrFreeSessionUsers
0x18003f334  mov     rdi, [rsp+578h+var_548]
0x18003f339  lea     rax, [rdi-1]
0x18003f33d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f341  ja      short loc_18003F34C
0x18003f343  mov     rcx, rdi; hObject
0x18003f346  call    cs:__imp_CloseHandle
0x18003f34c  mov     rax, rsi
0x18003f34f  jmp     short loc_18003F376
0x18003f351  mov     rcx, [rsp+578h+var_548]; hObject
0x18003f356  lea     rax, [rcx-1]
0x18003f35a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003f35e  ja      short loc_18003F367
0x18003f360  call    cs:__imp_CloseHandle
0x18003f366  nop
0x18003f367  jmp     short loc_18003F370
0x18003f369  xor     edi, edi
0x18003f36b  mov     rsi, [rsp+578h+var_510]
0x18003f370  mov     [rsi], rdi
0x18003f373  mov     rax, rsi
0x18003f376  mov     rcx, [rsp+578h+var_38]
0x18003f37e  xor     rcx, rsp; StackCookie
0x18003f381  call    __security_check_cookie
0x18003f386  lea     r11, [rsp+578h+var_28]
0x18003f38e  mov     rbx, [r11+38h]
0x18003f392  mov     rsi, [r11+40h]
0x18003f396  mov     rsp, r11
0x18003f399  pop     r15
0x18003f39b  pop     r14
0x18003f39d  pop     r13
0x18003f39f  pop     r12
0x18003f3a1  pop     rdi
0x18003f3a2  retn
0x18003f3a3  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f3aa  lea     edx, [rdi+62h]; void *
0x18003f3ad  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003f3b2  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
0x18003f3b8  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f3bf  mov     edx, 0AFh; void *
0x18003f3c4  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003f3c9  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f3d0  mov     edx, 0A7h; void *
0x18003f3d5  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18003f3db  mov     r9d, eax; char *
0x18003f3de  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f3e5  mov     edx, 0B7h; void *
0x18003f3ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f3ef  mov     r9d, 8000FFFFh; char *
0x18003f3f5  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f3fc  mov     edx, 0BDh; void *
0x18003f401  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003f406  mov     r9d, eax; char *
0x18003f409  lea     r8, aOnecoreEnduser_10; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18003f410  mov     edx, 0BFh; void *
0x18003f415  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
