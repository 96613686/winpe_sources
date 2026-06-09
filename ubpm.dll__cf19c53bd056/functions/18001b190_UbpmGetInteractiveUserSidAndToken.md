# UbpmGetInteractiveUserSidAndToken

- ea: `0x18001b190`
- end: `0x18001bb1a`
- name: `UbpmGetInteractiveUserSidAndToken`
- size: `2442`
- prototype: `__int64 __usercall@<rax>(PSID pSid2@<rcx>, PSID SidToCheck@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800189f4`
- `0x180019fb0`
- `0x18001a8a8`
- `0x18001acb0`

## callees

- `0x180019d90`
- `0x18001b190`
- `0x18001bb20`
- `0x180030cec`
- `0x18003226c`
- `0x180032450`
- `0x1800325e0`
- `0x180032e38`
- `0x18003d810`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001b534`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001b534`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001b25c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001b5ea`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001b68e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001b25c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001b5ea`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18001b68e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001b54e`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18001b54e`
- `ntdll!NtDuplicateToken` at `0x18001b7b1`
- `ntdll!NtDuplicateToken` at `0x18001b7b1`
- `ntdll!NtQueryInformationToken` at `0x18001b4c8`
- `ntdll!NtQueryInformationToken` at `0x18001b508`
- `ntdll!NtQueryInformationToken` at `0x18001b64c`
- `ntdll!NtQueryInformationToken` at `0x18001b87c`
- `ntdll!NtQueryInformationToken` at `0x18001b4c8`
- `ntdll!NtQueryInformationToken` at `0x18001b508`
- `ntdll!NtQueryInformationToken` at `0x18001b64c`
- `ntdll!NtQueryInformationToken` at `0x18001b87c`
- `ntdll!RtlIsMultiSessionSku` at `0x18001b445`
- `ntdll!RtlIsMultiSessionSku` at `0x18001b445`
- `ntdll!RtlFreeHeap` at `0x18001b311`
- `ntdll!RtlFreeHeap` at `0x18001b34e`
- `ntdll!RtlFreeHeap` at `0x18001b3e0`
- `ntdll!RtlFreeHeap` at `0x18001b311`
- `ntdll!RtlFreeHeap` at `0x18001b34e`
- `ntdll!RtlFreeHeap` at `0x18001b3e0`
- `ntdll!RtlAllocateHeap` at `0x18001b2a1`
- `ntdll!RtlAllocateHeap` at `0x18001b2a1`
- `ntdll!RtlNtStatusToDosError` at `0x18001b65c`
- `ntdll!RtlNtStatusToDosError` at `0x18001b888`
- `ntdll!RtlNtStatusToDosError` at `0x18001b65c`
- `ntdll!RtlNtStatusToDosError` at `0x18001b888`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001babf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b966`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b9ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ba98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001babf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b9c4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b9c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b38b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b39b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b7d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba13`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b38b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b39b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b6eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b7d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba00`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ba13`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001b901`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18001b901`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001bb0f`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18001bb0f`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18001b95c`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18001b95c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18001b273`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18001b273`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18001b5fd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18001b5fd`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18001b37c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18001b37c`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001b823`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18001b823`

## pseudocode

```c
__int64 __fastcall UbpmGetInteractiveUserSidAndToken(PSID pSid2, PSID SidToCheck, int a3, _QWORD *a4, unsigned int *a5)
{
  DWORD v5; // ebx
  _QWORD *Heap; // rsi
  int v9; // eax
  int v10; // edi
  DWORD v11; // eax
  _QWORD *v12; // rcx
  DWORD SessionId; // r8d
  ULONG UserToken; // eax
  HANDLE v16; // rdi
  int v17; // eax
  HANDLE v18; // rax
  HANDLE v19; // rcx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  unsigned int i; // r14d
  __int64 v26; // rdi
  int v27; // eax
  int v28; // eax
  ULONG v29; // eax
  DWORD LastError; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  WTS_CONNECTSTATE_CLASS State; // eax
  DWORD ReturnLength; // [rsp+28h] [rbp-E0h]
  DWORD pCount[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v37; // [rsp+48h] [rbp-C0h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+50h] [rbp-B8h] BYREF
  ULONG v39[2]; // [rsp+58h] [rbp-B0h] BYREF
  PVOID P; // [rsp+60h] [rbp-A8h]
  HANDLE NewTokenHandle; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v42; // [rsp+70h] [rbp-98h] BYREF
  int TokenInformation; // [rsp+78h] [rbp-90h] BYREF
  int v44; // [rsp+7Ch] [rbp-8Ch] BYREF
  WINBOOL IsMember; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-80h] BYREF
  __int128 *v47; // [rsp+90h] [rbp-78h] BYREF
  ULONG v48; // [rsp+98h] [rbp-70h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-50h]
  _QWORD *v52; // [rsp+C0h] [rbp-48h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v54; // [rsp+F8h] [rbp-10h] BYREF

  v5 = 0;
  Heap = 0;
  *a5 = 0;
  *a4 = 0;
  v52 = a4;
  LODWORD(v37) = a3;
  v47 = 0;
  ppSessionInfo = 0;
  TokenHandle = 0;
  hObject = 0;
  NewTokenHandle = 0;
  P = 0;
  v50 = 0;
  v51 = 0;
  v54 = 0;
  pCount[1] = 0;
  pCount[0] = 0;
  v42 = 0;
  IsMember = 0;
  v48 = 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    if ( (!pSid2 || !qword_18004CE70 || !EqualSid(pSid2, qword_18004CE70))
      && (!SidToCheck || !qword_18004CE78 || !EqualSid(SidToCheck, qword_18004CE78)) )
    {
      v9 = UMgrEnumerateSessionUsers(&pCount[1], &v47);
      if ( v9 >= 0 )
      {
        v10 = v37;
LABEL_9:
        v11 = pCount[1];
        goto LABEL_10;
      }
      v5 = (unsigned __int16)v9;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = 46;
      v22 = (unsigned __int16)v9;
LABEL_131:
      WPP_SF_d(v12[2], v21, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, v22);
      goto LABEL_14;
    }
    v20 = UMgrQueryDefaultAccountToken(&TokenHandle);
    if ( v20 == -2147023584 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_14;
      v21 = 42;
      v22 = 2147943712LL;
      goto LABEL_131;
    }
    if ( v20 < 0 )
    {
      v5 = (unsigned __int16)v20;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = 43;
      v22 = (unsigned int)v20;
      goto LABEL_131;
    }
    v27 = UMgrQueryUserContext(TokenHandle, &v42);
    if ( v27 < 0 )
    {
      v5 = (unsigned __int16)v27;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = 44;
      v22 = (unsigned __int16)v27;
      goto LABEL_131;
    }
    v28 = NtQueryInformationToken(TokenHandle, TokenSessionId, pCount, 4u, &v48);
    if ( v28 < 0 )
    {
      v29 = RtlNtStatusToDosError(v28);
      v5 = v29;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = 45;
      v22 = v29;
      goto LABEL_131;
    }
    v10 = v37;
    v47 = &v54;
    *(_QWORD *)&v54 = v42;
    DWORD2(v54) = pCount[0];
  }
  else
  {
    v10 = v37;
    if ( (_DWORD)v37 == -1 )
    {
      if ( (unsigned __int8)IsWTSEnumerateSessionsWPresent() )
      {
        if ( WTSEnumerateSessionsW(0, 0, 1u, &ppSessionInfo, &pCount[1]) )
          goto LABEL_9;
        LastError = GetLastError();
        v5 = LastError;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_14;
        v21 = 47;
        v22 = LastError;
        goto LABEL_131;
      }
      ppSessionInfo = (PWTS_SESSION_INFOW)&v50;
      if ( (unsigned __int8)IsQueryActiveSessionPresent() )
      {
        if ( !(unsigned int)QueryActiveSession(ppSessionInfo) )
        {
          v31 = GetLastError();
          v5 = v31;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_14;
          v21 = 48;
          v22 = v31;
          goto LABEL_131;
        }
      }
      else
      {
        ppSessionInfo->SessionId = NtCurrentPeb()->SessionId;
      }
      ppSessionInfo->State = WTSActive;
    }
    else
    {
      LODWORD(v50) = v37;
      ppSessionInfo = (PWTS_SESSION_INFOW)&v50;
      LODWORD(v51) = 0;
    }
  }
  v11 = 1;
  pCount[1] = 1;
LABEL_10:
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 32 * v11);
  if ( !Heap )
  {
    SetLastError(8u);
    v32 = GetLastError();
    v5 = v32;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v21 = 49;
    v22 = v32;
    goto LABEL_131;
  }
  while ( v5 < pCount[1] )
  {
    if ( P )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
    P = 0;
    if ( TokenHandle )
    {
      CloseHandle(TokenHandle);
      TokenHandle = 0;
    }
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( NewTokenHandle )
    {
      CloseHandle(NewTokenHandle);
      NewTokenHandle = 0;
    }
    if ( v47 )
    {
      SessionId = DWORD2(v47[v5]);
      pCount[0] = SessionId;
      v42 = *(_QWORD *)&v47[v5];
    }
    else
    {
      if ( !ppSessionInfo )
      {
        v5 = 1359;
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v21 = 50;
          v22 = 1359;
          goto LABEL_131;
        }
        goto LABEL_14;
      }
      SessionId = ppSessionInfo[v5].SessionId;
      pCount[0] = SessionId;
      v42 = 0;
      State = ppSessionInfo[v5].State;
      if ( State && State != WTSDisconnected )
        goto LABEL_57;
    }
    if ( v10 != -1 && SessionId != v10 || (unsigned __int8)RtlIsMultiSessionSku() && !pCount[0] )
      goto LABEL_57;
    UserToken = UbpmGetUserToken(pCount[0], ReturnLength);
    if ( UserToken )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 51;
        goto LABEL_123;
      }
      goto LABEL_57;
    }
    if ( !SidToCheck )
      goto LABEL_55;
    v16 = TokenHandle;
    v39[0] = 0;
    v44 = 0;
    TokenInformation = 0;
    ExistingTokenHandle = 0;
    NewTokenHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v17 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, v39);
    if ( v17 < 0 )
    {
LABEL_67:
      UserToken = RtlNtStatusToDosError(v17);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 52;
LABEL_123:
        WPP_SF_dd(v23[2], v24, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, pCount[0], UserToken);
        goto LABEL_57;
      }
      goto LABEL_57;
    }
    if ( TokenInformation == 2 )
      goto LABEL_85;
    if ( TokenInformation != 1 )
    {
      v17 = NtQueryInformationToken(v16, TokenLinkedToken, &ExistingTokenHandle, 8u, v39);
      if ( v17 < 0 )
        goto LABEL_67;
      v18 = ExistingTokenHandle;
      NewTokenHandle = ExistingTokenHandle;
      goto LABEL_50;
    }
    v17 = NtQueryInformationToken(v16, TokenElevation, &v44, 4u, v39);
    if ( v17 < 0 )
      goto LABEL_67;
    if ( v44 )
    {
LABEL_85:
      ObjectAttributes.Length = 48;
      memset(&ObjectAttributes.RootDirectory, 0, 20);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v17 = NtDuplicateToken(v16, 0, &ObjectAttributes, 0, TokenPrimary, &NewTokenHandle);
      if ( v17 < 0 )
        goto LABEL_67;
    }
    v18 = NewTokenHandle;
LABEL_50:
    v19 = TokenHandle;
    if ( v18 )
      v19 = v18;
    if ( DuplicateToken(v19, SecurityImpersonation, &hObject) )
    {
      if ( CheckTokenMembership(hObject, SidToCheck, &IsMember) )
      {
        if ( !IsMember )
          goto LABEL_57;
LABEL_55:
        if ( !pSid2 || EqualSid(P, pSid2) )
        {
          Heap[4 * *a5] = P;
          Heap[4 * *a5 + 1] = TokenHandle;
          LODWORD(Heap[4 * *a5 + 2]) = pCount[0];
          Heap[4 * (*a5)++ + 3] = v42;
          TokenHandle = 0;
          P = 0;
        }
        goto LABEL_57;
      }
      UserToken = GetLastError();
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 54;
        goto LABEL_123;
      }
    }
    else
    {
      UserToken = GetLastError();
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 53;
        goto LABEL_123;
      }
    }
LABEL_57:
    v10 = v37;
    ++v5;
  }
  v5 = 0;
  *v52 = Heap;
  Heap = 0;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
  {
    v22 = *a5;
    v21 = 55;
    goto LABEL_131;
  }
LABEL_14:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v5 )
  {
    for ( i = 0; i < *a5; ++i )
    {
      v26 = 4LL * i;
      CloseHandle((HANDLE)Heap[v26 + 1]);
      UBPM_MIDL_user_free(Heap[v26]);
    }
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( ppSessionInfo && ppSessionInfo != (PWTS_SESSION_INFOW)&v50 )
    WTSFreeMemory(ppSessionInfo);
  if ( v47 && v47 != &v54 )
    UMgrFreeSessionUsers();
  if ( hObject )
    CloseHandle(hObject);
  if ( NewTokenHandle )
    CloseHandle(NewTokenHandle);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v5;
}

```

## disassembly

```asm
0x18001b190  mov     r11, rsp
0x18001b193  push    rbp
0x18001b194  push    rbx
0x18001b195  lea     rbp, [r11-48h]
0x18001b199  sub     rsp, 138h
0x18001b1a0  mov     rax, cs:__security_cookie
0x18001b1a7  xor     rax, rsp
0x18001b1aa  mov     [rbp+40h+var_40], rax
0x18001b1ae  xor     ebx, ebx
0x18001b1b0  mov     [r11+18h], rsi
0x18001b1b4  mov     [r11-18h], rdi
0x18001b1b8  xorps   xmm0, xmm0
0x18001b1bb  mov     [r11-20h], r12
0x18001b1bf  xor     eax, eax
0x18001b1c1  mov     r12, [rbp+40h+arg_20]
0x18001b1c5  mov     esi, ebx
0x18001b1c7  mov     [r11-28h], r13
0x18001b1cb  mov     r13, rcx
0x18001b1ce  mov     [r11-30h], r14
0x18001b1d2  mov     r14, rdx
0x18001b1d5  mov     [r11-38h], r15
0x18001b1d9  mov     [r12], ebx
0x18001b1dd  mov     [r9], rbx
0x18001b1e0  mov     [rbp+40h+var_88], r9
0x18001b1e4  mov     dword ptr [rsp+140h+var_100], r8d
0x18001b1e9  mov     [rbp+40h+var_B8], rbx
0x18001b1ed  mov     [rsp+140h+ppSessionInfo], rbx
0x18001b1f2  mov     [rsp+140h+TokenHandle], rbx
0x18001b1f7  mov     [rbp+40h+hObject], rbx
0x18001b1fb  mov     [rsp+140h+var_E0], rbx
0x18001b200  mov     [rsp+140h+P], rbx
0x18001b205  movups  [rbp+40h+var_A0], xmm0
0x18001b209  mov     [rbp+40h+var_90], rax
0x18001b20d  movups  [rbp+40h+var_50], xmm0
0x18001b211  mov     [rsp+140h+pCount+4], ebx
0x18001b215  mov     [rsp+140h+pCount], ebx
0x18001b219  mov     qword ptr [rsp+140h+var_D8], rbx
0x18001b21e  mov     [rsp+140h+IsMember], ebx
0x18001b222  mov     [rbp+40h+var_B0], ebx
0x18001b225  call    IsUMgrEnumerateSessionUsersPresent
0x18001b22a  test    al, al
0x18001b22c  jz      loc_18001B708
0x18001b232  call    IsUMgrEnumerateSessionUsersPresent
0x18001b237  test    al, al
0x18001b239  jz      loc_18001B708
0x18001b23f  test    r13, r13
0x18001b242  jnz     loc_18001B5D7
0x18001b248  test    r14, r14
0x18001b24b  jz      short loc_18001B26A
0x18001b24d  mov     rdx, cs:qword_18004CE78; pSid2
0x18001b254  test    rdx, rdx
0x18001b257  jz      short loc_18001B26A
0x18001b259  mov     rcx, r14; pSid1
0x18001b25c  call    cs:__imp_EqualSid
0x18001b262  test    eax, eax
0x18001b264  jnz     loc_18001B5F8
0x18001b26a  lea     rdx, [rbp+40h+var_B8]
0x18001b26e  lea     rcx, [rsp+140h+pCount+4]
0x18001b273  call    cs:__imp_UMgrEnumerateSessionUsers
0x18001b279  test    eax, eax
0x18001b27b  js      loc_18001B6A1
0x18001b281  mov     edi, dword ptr [rsp+140h+var_100]
0x18001b285  mov     eax, [rsp+140h+pCount+4]
0x18001b289  mov     rcx, gs:60h
0x18001b292  mov     edx, 8; Flags
0x18001b297  shl     eax, 5
0x18001b29a  mov     r8d, eax; Size
0x18001b29d  mov     rcx, [rcx+30h]; HeapHandle
0x18001b2a1  call    cs:__imp_RtlAllocateHeap
0x18001b2a7  mov     rsi, rax
0x18001b2aa  test    rax, rax
0x18001b2ad  jz      loc_18001B9BF
0x18001b2b3  lea     r15, WPP_GLOBAL_Control
0x18001b2ba  cmp     ebx, [rsp+140h+pCount+4]
0x18001b2be  jb      loc_18001B3C7
0x18001b2c4  mov     rax, [rbp+40h+var_88]
0x18001b2c8  xor     ebx, ebx
0x18001b2ca  mov     [rax], rsi
0x18001b2cd  xor     esi, esi
0x18001b2cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b2d6  cmp     rcx, r15
0x18001b2d9  jz      short loc_18001B2E8
0x18001b2db  test    dword ptr [rcx+1Ch], 100h
0x18001b2e2  jnz     loc_18001BAE1
0x18001b2e8  mov     r8, [rsp+140h+P]; P
0x18001b2ed  mov     r15, [rsp+140h+var_30]
0x18001b2f5  mov     r13, [rsp+140h+var_20]
0x18001b2fd  test    r8, r8
0x18001b300  jz      short loc_18001B317
0x18001b302  mov     rcx, gs:60h
0x18001b30b  xor     edx, edx; Flags
0x18001b30d  mov     rcx, [rcx+30h]; HeapHandle
0x18001b311  call    cs:__imp_RtlFreeHeap
0x18001b317  test    ebx, ebx
0x18001b319  jnz     loc_18001B6D2
0x18001b31f  mov     r14, [rsp+140h+var_28]
0x18001b327  mov     r12, [rsp+140h+var_18]
0x18001b32f  mov     rdi, [rsp+130h]
0x18001b337  test    rsi, rsi
0x18001b33a  jz      short loc_18001B354
0x18001b33c  mov     rcx, gs:60h
0x18001b345  mov     r8, rsi; P
0x18001b348  xor     edx, edx; Flags
0x18001b34a  mov     rcx, [rcx+30h]; HeapHandle
0x18001b34e  call    cs:__imp_RtlFreeHeap
0x18001b354  mov     rdx, [rsp+140h+ppSessionInfo]
0x18001b359  mov     rsi, [rsp+140h+arg_10]
0x18001b361  test    rdx, rdx
0x18001b364  jnz     loc_18001BAFF
0x18001b36a  mov     rcx, [rbp+40h+var_B8]
0x18001b36e  test    rcx, rcx
0x18001b371  jz      short loc_18001B382
0x18001b373  lea     rax, [rbp+40h+var_50]
0x18001b377  cmp     rcx, rax
0x18001b37a  jz      short loc_18001B382
0x18001b37c  call    cs:__imp_UMgrFreeSessionUsers
0x18001b382  mov     rcx, [rbp+40h+hObject]; hObject
0x18001b386  test    rcx, rcx
0x18001b389  jz      short loc_18001B391
0x18001b38b  call    cs:__imp_CloseHandle
0x18001b391  mov     rcx, [rsp+140h+var_E0]; hObject
0x18001b396  test    rcx, rcx
0x18001b399  jz      short loc_18001B3A1
0x18001b39b  call    cs:__imp_CloseHandle
0x18001b3a1  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x18001b3a6  test    rcx, rcx
0x18001b3a9  jnz     loc_18001B732
0x18001b3af  mov     eax, ebx
0x18001b3b1  mov     rcx, [rbp+40h+var_40]
0x18001b3b5  xor     rcx, rsp; StackCookie
0x18001b3b8  call    __security_check_cookie
0x18001b3bd  add     rsp, 138h
0x18001b3c4  pop     rbx
0x18001b3c5  pop     rbp
0x18001b3c6  retn
0x18001b3c7  mov     r8, [rsp+140h+P]; P
0x18001b3cc  test    r8, r8
0x18001b3cf  jz      short loc_18001B3E6
0x18001b3d1  mov     rcx, gs:60h
0x18001b3da  xor     edx, edx; Flags
0x18001b3dc  mov     rcx, [rcx+30h]; HeapHandle
0x18001b3e0  call    cs:__imp_RtlFreeHeap
0x18001b3e6  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x18001b3eb  xor     r9d, r9d
0x18001b3ee  mov     [rsp+140h+P], r9
0x18001b3f3  test    rcx, rcx
0x18001b3f6  jnz     loc_18001BA00
0x18001b3fc  mov     rcx, [rbp+40h+hObject]; hObject
0x18001b400  test    rcx, rcx
0x18001b403  jnz     loc_18001B7D2
0x18001b409  mov     rcx, [rsp+140h+var_E0]; hObject
0x18001b40e  test    rcx, rcx
0x18001b411  jnz     loc_18001BA13
0x18001b417  mov     rcx, [rbp+40h+var_B8]
0x18001b41b  test    rcx, rcx
0x18001b41e  jz      loc_18001B73D
0x18001b424  mov     eax, ebx
0x18001b426  add     rax, rax
0x18001b429  mov     r8d, [rcx+rax*8+8]
0x18001b42e  mov     [rsp+140h+pCount], r8d
0x18001b433  mov     rax, [rcx+rax*8]
0x18001b437  mov     qword ptr [rsp+140h+var_D8], rax
0x18001b43c  cmp     edi, 0FFFFFFFFh
0x18001b43f  jnz     loc_18001B5CC
0x18001b445  call    cs:__imp_RtlIsMultiSessionSku
0x18001b44b  mov     ecx, [rsp+140h+pCount]; SessionId
0x18001b44f  test    al, al
0x18001b451  jz      short loc_18001B45B
0x18001b453  test    ecx, ecx
0x18001b455  jz      loc_18001B5C1
0x18001b45b  mov     rdx, qword ptr [rsp+140h+var_D8]
0x18001b460  lea     r9, [rsp+140h+P]
0x18001b465  lea     r8, [rsp+140h+TokenHandle]
0x18001b46a  call    UbpmGetUserToken
0x18001b46f  test    eax, eax
0x18001b471  jnz     loc_18001BA54
0x18001b477  test    r14, r14
0x18001b47a  jz      loc_18001B563
0x18001b480  mov     rdi, [rsp+140h+TokenHandle]
0x18001b485  lea     r8, [rsp+140h+TokenInformation]; TokenInformation
0x18001b48a  xor     eax, eax
0x18001b48c  xorps   xmm0, xmm0
0x18001b48f  mov     [rsp+140h+var_F0], eax
0x18001b493  mov     r9d, 4; TokenInformationLength
0x18001b499  mov     [rsp+140h+var_CC], eax
0x18001b49d  mov     edx, 12h; TokenInformationClass
0x18001b4a2  mov     [rsp+140h+TokenInformation], eax
0x18001b4a6  mov     rcx, rdi; TokenHandle
0x18001b4a9  mov     [rbp+40h+ExistingTokenHandle], rax
0x18001b4ad  mov     [rsp+140h+var_E0], rax
0x18001b4b2  lea     rax, [rsp+140h+var_F0]
0x18001b4b7  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18001b4bc  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18001b4c0  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18001b4c4  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001b4c8  call    cs:__imp_NtQueryInformationToken
0x18001b4ce  test    eax, eax
0x18001b4d0  js      loc_18001B65A
0x18001b4d6  mov     eax, [rsp+140h+TokenInformation]
0x18001b4da  cmp     eax, 2
0x18001b4dd  jz      loc_18001B777
0x18001b4e3  cmp     eax, 1
0x18001b4e6  mov     rcx, rdi; TokenHandle
0x18001b4e9  lea     rax, [rsp+140h+var_F0]
0x18001b4ee  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18001b4f3  jz      loc_18001B63C
0x18001b4f9  mov     r9d, 8; TokenInformationLength
0x18001b4ff  lea     r8, [rbp+40h+ExistingTokenHandle]; TokenInformation
0x18001b503  mov     edx, 13h; TokenInformationClass
0x18001b508  call    cs:__imp_NtQueryInformationToken
0x18001b50e  test    eax, eax
0x18001b510  js      loc_18001B65A
0x18001b516  mov     rax, [rbp+40h+ExistingTokenHandle]
0x18001b51a  mov     [rsp+140h+var_E0], rax
0x18001b51f  mov     rcx, [rsp+140h+TokenHandle]
0x18001b524  lea     r8, [rbp+40h+hObject]; DuplicateTokenHandle
0x18001b528  test    rax, rax
0x18001b52b  mov     edx, 2; ImpersonationLevel
0x18001b530  cmovnz  rcx, rax; ExistingTokenHandle
0x18001b534  call    cs:__imp_DuplicateToken
0x18001b53a  test    eax, eax
0x18001b53c  jz      loc_18001BA98
0x18001b542  mov     rcx, [rbp+40h+hObject]; TokenHandle
0x18001b546  lea     r8, [rsp+140h+IsMember]; IsMember
0x18001b54b  mov     rdx, r14; SidToCheck
0x18001b54e  call    cs:__imp_CheckTokenMembership
0x18001b554  test    eax, eax
0x18001b556  jz      loc_18001BABF
0x18001b55c  cmp     [rsp+140h+IsMember], 0
0x18001b561  jz      short loc_18001B5C1
0x18001b563  test    r13, r13
0x18001b566  jnz     loc_18001B686
0x18001b56c  mov     ecx, [r12]
0x18001b570  mov     rax, [rsp+140h+P]
0x18001b575  shl     rcx, 5
0x18001b579  mov     [rcx+rsi], rax
0x18001b57d  mov     rax, [rsp+140h+TokenHandle]
0x18001b582  mov     ecx, [r12]
0x18001b586  shl     rcx, 5
0x18001b58a  mov     [rcx+rsi+8], rax
0x18001b58f  mov     ecx, [r12]
0x18001b593  mov     eax, [rsp+140h+pCount]
0x18001b597  shl     rcx, 5
0x18001b59b  mov     [rcx+rsi+10h], eax
0x18001b59f  mov     ecx, [r12]
0x18001b5a3  mov     rax, qword ptr [rsp+140h+var_D8]
0x18001b5a8  shl     rcx, 5
0x18001b5ac  mov     [rcx+rsi+18h], rax
0x18001b5b1  inc     dword ptr [r12]
0x18001b5b5  xor     eax, eax
0x18001b5b7  mov     [rsp+140h+TokenHandle], rax
0x18001b5bc  mov     [rsp+140h+P], rax
0x18001b5c1  mov     edi, dword ptr [rsp+140h+var_100]
0x18001b5c5  inc     ebx
0x18001b5c7  jmp     loc_18001B2BA
0x18001b5cc  cmp     r8d, edi
0x18001b5cf  jz      loc_18001B445
0x18001b5d5  jmp     short loc_18001B5C1
0x18001b5d7  mov     rdx, cs:qword_18004CE70; pSid2
0x18001b5de  test    rdx, rdx
0x18001b5e1  jz      loc_18001B248
0x18001b5e7  mov     rcx, r13; pSid1
0x18001b5ea  call    cs:__imp_EqualSid
0x18001b5f0  test    eax, eax
0x18001b5f2  jz      loc_18001B248
0x18001b5f8  lea     rcx, [rsp+140h+TokenHandle]
0x18001b5fd  call    cs:__imp_UMgrQueryDefaultAccountToken
0x18001b603  cmp     eax, 80070520h
0x18001b608  jnz     loc_18001B7E4
0x18001b60e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b615  lea     r15, WPP_GLOBAL_Control
0x18001b61c  cmp     rcx, r15
0x18001b61f  jz      loc_18001B2E8
0x18001b625  test    byte ptr [rcx+1Ch], 2
0x18001b629  jz      loc_18001B2E8
0x18001b62f  mov     edx, 2Ah ; '*'
0x18001b634  mov     r9d, eax
0x18001b637  jmp     loc_18001BAEA
0x18001b63c  mov     r9d, 4; TokenInformationLength
0x18001b642  lea     r8, [rsp+140h+var_CC]; TokenInformation
0x18001b647  mov     edx, 14h; TokenInformationClass
0x18001b64c  call    cs:__imp_NtQueryInformationToken
0x18001b652  test    eax, eax
0x18001b654  jns     loc_18001B7C1
0x18001b65a  mov     ecx, eax; Status
0x18001b65c  call    cs:__imp_RtlNtStatusToDosError
0x18001b662  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b669  cmp     rcx, r15
0x18001b66c  jz      loc_18001B5C1
0x18001b672  test    byte ptr [rcx+1Ch], 2
0x18001b676  jz      loc_18001B5C1
0x18001b67c  mov     edx, 34h ; '4'
0x18001b681  jmp     loc_18001BA7A
0x18001b686  mov     rcx, [rsp+140h+P]; pSid1
0x18001b68b  mov     rdx, r13; pSid2
0x18001b68e  call    cs:__imp_EqualSid
0x18001b694  test    eax, eax
0x18001b696  jnz     loc_18001B56C
0x18001b69c  jmp     loc_18001B5C1
0x18001b6a1  movzx   ebx, ax
  ... truncated ...
```
