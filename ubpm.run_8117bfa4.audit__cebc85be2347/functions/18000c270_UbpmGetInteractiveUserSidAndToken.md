# UbpmGetInteractiveUserSidAndToken

- ea: `0x18000c270`
- end: `0x18000ccd9`
- name: `UbpmGetInteractiveUserSidAndToken`
- size: `2665`
- prototype: `__int64 __usercall@<rax>(PSID pSid2@<rcx>, PSID SidToCheck@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000aff0`
- `0x18000b938`
- `0x18000bd60`
- `0x18000e5b0`

## callees

- `0x18000c270`
- `0x18000fbf0`
- `0x180015120`
- `0x180032f78`
- `0x1800345cc`
- `0x1800347b0`
- `0x180034940`
- `0x1800351ec`
- `0x180040260`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000c65d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000c65d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c33c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c71f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c7db`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c33c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c71f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000c7db`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c67d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x18000c67d`
- `ntdll!NtDuplicateToken` at `0x18000c910`
- `ntdll!NtDuplicateToken` at `0x18000c910`
- `ntdll!NtQueryInformationToken` at `0x18000c5e5`
- `ntdll!NtQueryInformationToken` at `0x18000c62b`
- `ntdll!NtQueryInformationToken` at `0x18000c78d`
- `ntdll!NtQueryInformationToken` at `0x18000c9ed`
- `ntdll!NtQueryInformationToken` at `0x18000c5e5`
- `ntdll!NtQueryInformationToken` at `0x18000c62b`
- `ntdll!NtQueryInformationToken` at `0x18000c78d`
- `ntdll!NtQueryInformationToken` at `0x18000c9ed`
- `ntdll!RtlIsMultiSessionSku` at `0x18000c55c`
- `ntdll!RtlIsMultiSessionSku` at `0x18000c55c`
- `ntdll!RtlFreeHeap` at `0x18000c403`
- `ntdll!RtlFreeHeap` at `0x18000c446`
- `ntdll!RtlFreeHeap` at `0x18000c4f1`
- `ntdll!RtlFreeHeap` at `0x18000c403`
- `ntdll!RtlFreeHeap` at `0x18000c446`
- `ntdll!RtlFreeHeap` at `0x18000c4f1`
- `ntdll!RtlAllocateHeap` at `0x18000c38d`
- `ntdll!RtlAllocateHeap` at `0x18000c38d`
- `ntdll!RtlNtStatusToDosError` at `0x18000c7a3`
- `ntdll!RtlNtStatusToDosError` at `0x18000c9ff`
- `ntdll!RtlNtStatusToDosError` at `0x18000c7a3`
- `ntdll!RtlNtStatusToDosError` at `0x18000c9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000caf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ca92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000caf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cc72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c48f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c83e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c48f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c4a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c83e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c88b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000c937`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cba1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000cbba`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18000ca7e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateSessionsW` at `0x18000ca7e`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000ccc8`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000ccc8`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18000cae5`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x18000cae5`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18000c359`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrEnumerateSessionUsers` at `0x18000c359`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18000c738`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryDefaultAccountToken` at `0x18000c738`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18000c47a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrFreeSessionUsers` at `0x18000c47a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000c98e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18000c98e`

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
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // eax
  int v31; // eax
  ULONG v32; // eax
  DWORD LastError; // eax
  DWORD v34; // eax
  DWORD v35; // eax
  WTS_CONNECTSTATE_CLASS State; // eax
  DWORD ReturnLength; // [rsp+28h] [rbp-E0h]
  DWORD pCount[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE TokenHandle; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+48h] [rbp-C0h]
  PWTS_SESSION_INFOW ppSessionInfo; // [rsp+50h] [rbp-B8h] BYREF
  ULONG v42[2]; // [rsp+58h] [rbp-B0h] BYREF
  PVOID P; // [rsp+60h] [rbp-A8h]
  HANDLE NewTokenHandle; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v45; // [rsp+70h] [rbp-98h] BYREF
  int TokenInformation; // [rsp+78h] [rbp-90h] BYREF
  int v47; // [rsp+7Ch] [rbp-8Ch] BYREF
  WINBOOL IsMember; // [rsp+80h] [rbp-88h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-80h] BYREF
  __int128 *v50; // [rsp+90h] [rbp-78h] BYREF
  ULONG v51; // [rsp+98h] [rbp-70h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v53; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-50h]
  _QWORD *v55; // [rsp+C0h] [rbp-48h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v57; // [rsp+F8h] [rbp-10h] BYREF

  v5 = 0;
  Heap = 0;
  *a5 = 0;
  *a4 = 0;
  v55 = a4;
  LODWORD(v40) = a3;
  v50 = 0;
  ppSessionInfo = 0;
  TokenHandle = 0;
  hObject = 0;
  NewTokenHandle = 0;
  P = 0;
  v53 = 0;
  v54 = 0;
  v57 = 0;
  pCount[1] = 0;
  pCount[0] = 0;
  v45 = 0;
  IsMember = 0;
  v51 = 0;
  if ( (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() && (unsigned __int8)IsUMgrEnumerateSessionUsersPresent() )
  {
    if ( (!pSid2 || !qword_18004FF70 || !EqualSid(pSid2, qword_18004FF70))
      && (!SidToCheck || !qword_18004FF78 || !EqualSid(SidToCheck, qword_18004FF78)) )
    {
      v9 = UMgrEnumerateSessionUsers(&pCount[1], &v50);
      if ( v9 >= 0 )
      {
        v10 = v40;
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
    v30 = UMgrQueryUserContext(TokenHandle, &v45);
    if ( v30 < 0 )
    {
      v5 = (unsigned __int16)v30;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = 44;
      v22 = (unsigned __int16)v30;
      goto LABEL_131;
    }
    v31 = NtQueryInformationToken(TokenHandle, TokenSessionId, pCount, 4u, &v51);
    if ( v31 < 0 )
    {
      v32 = RtlNtStatusToDosError(v31);
      v5 = v32;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_14;
      v21 = 45;
      v22 = v32;
      goto LABEL_131;
    }
    v10 = v40;
    v50 = &v57;
    *(_QWORD *)&v57 = v45;
    DWORD2(v57) = pCount[0];
  }
  else
  {
    v10 = v40;
    if ( (_DWORD)v40 == -1 )
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
      ppSessionInfo = (PWTS_SESSION_INFOW)&v53;
      if ( (unsigned __int8)IsQueryActiveSessionPresent() )
      {
        if ( !(unsigned int)QueryActiveSession(ppSessionInfo) )
        {
          v34 = GetLastError();
          v5 = v34;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_14;
          v21 = 48;
          v22 = v34;
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
      LODWORD(v53) = v40;
      ppSessionInfo = (PWTS_SESSION_INFOW)&v53;
      LODWORD(v54) = 0;
    }
  }
  v11 = 1;
  pCount[1] = 1;
LABEL_10:
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 32 * v11);
  if ( !Heap )
  {
    SetLastError(8u);
    v35 = GetLastError();
    v5 = v35;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_14;
    v21 = 49;
    v22 = v35;
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
    if ( v50 )
    {
      SessionId = DWORD2(v50[v5]);
      pCount[0] = SessionId;
      v45 = *(_QWORD *)&v50[v5];
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
      v45 = 0;
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
    v42[0] = 0;
    v47 = 0;
    TokenInformation = 0;
    ExistingTokenHandle = 0;
    NewTokenHandle = 0;
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v17 = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, v42);
    if ( v17 < 0 )
    {
LABEL_67:
      UserToken = RtlNtStatusToDosError(v17);
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v24 = 52;
LABEL_123:
        ReturnLength = UserToken;
        WPP_SF_dd(v23[2], v24, WPP_134408c016563692a0776b6ad2359b4f_Traceguids, pCount[0]);
        goto LABEL_57;
      }
      goto LABEL_57;
    }
    if ( TokenInformation == 2 )
      goto LABEL_85;
    if ( TokenInformation != 1 )
    {
      v17 = NtQueryInformationToken(v16, TokenLinkedToken, &ExistingTokenHandle, 8u, v42);
      if ( v17 < 0 )
        goto LABEL_67;
      v18 = ExistingTokenHandle;
      NewTokenHandle = ExistingTokenHandle;
      goto LABEL_50;
    }
    v17 = NtQueryInformationToken(v16, TokenElevation, &v47, 4u, v42);
    if ( v17 < 0 )
      goto LABEL_67;
    if ( v47 )
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
          Heap[4 * (*a5)++ + 3] = v45;
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
    v10 = v40;
    ++v5;
  }
  v5 = 0;
  *v55 = Heap;
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
      UBPM_MIDL_user_free(Heap[v26], v27, v28, v29);
    }
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( ppSessionInfo && ppSessionInfo != (PWTS_SESSION_INFOW)&v53 )
    WTSFreeMemory(ppSessionInfo);
  if ( v50 && v50 != &v57 )
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
0x18000c270  mov     r11, rsp
0x18000c273  push    rbp
0x18000c274  push    rbx
0x18000c275  lea     rbp, [r11-48h]
0x18000c279  sub     rsp, 138h
0x18000c280  mov     rax, cs:__security_cookie
0x18000c287  xor     rax, rsp
0x18000c28a  mov     [rbp+40h+var_40], rax
0x18000c28e  xor     ebx, ebx
0x18000c290  mov     [r11+18h], rsi
0x18000c294  mov     [r11-18h], rdi
0x18000c298  xorps   xmm0, xmm0
0x18000c29b  mov     [r11-20h], r12
0x18000c29f  xor     eax, eax
0x18000c2a1  mov     r12, [rbp+40h+arg_20]
0x18000c2a5  mov     esi, ebx
0x18000c2a7  mov     [r11-28h], r13
0x18000c2ab  mov     r13, rcx
0x18000c2ae  mov     [r11-30h], r14
0x18000c2b2  mov     r14, rdx
0x18000c2b5  mov     [r11-38h], r15
0x18000c2b9  mov     [r12], ebx
0x18000c2bd  mov     [r9], rbx
0x18000c2c0  mov     [rbp+40h+var_88], r9
0x18000c2c4  mov     dword ptr [rsp+140h+var_100], r8d
0x18000c2c9  mov     [rbp+40h+var_B8], rbx
0x18000c2cd  mov     [rsp+140h+ppSessionInfo], rbx
0x18000c2d2  mov     [rsp+140h+TokenHandle], rbx
0x18000c2d7  mov     [rbp+40h+hObject], rbx
0x18000c2db  mov     [rsp+140h+var_E0], rbx
0x18000c2e0  mov     [rsp+140h+P], rbx
0x18000c2e5  movups  [rbp+40h+var_A0], xmm0
0x18000c2e9  mov     [rbp+40h+var_90], rax
0x18000c2ed  movups  [rbp+40h+var_50], xmm0
0x18000c2f1  mov     [rsp+140h+pCount+4], ebx
0x18000c2f5  mov     [rsp+140h+pCount], ebx
0x18000c2f9  mov     qword ptr [rsp+140h+var_D8], rbx
0x18000c2fe  mov     [rsp+140h+IsMember], ebx
0x18000c302  mov     [rbp+40h+var_B0], ebx
0x18000c305  call    IsUMgrEnumerateSessionUsersPresent
0x18000c30a  test    al, al
0x18000c30c  jz      loc_18000C861
0x18000c312  call    IsUMgrEnumerateSessionUsersPresent
0x18000c317  test    al, al
0x18000c319  jz      loc_18000C861
0x18000c31f  test    r13, r13
0x18000c322  jnz     loc_18000C70C
0x18000c328  test    r14, r14
0x18000c32b  jz      short loc_18000C350
0x18000c32d  mov     rdx, cs:qword_18004FF78; pSid2
0x18000c334  test    rdx, rdx
0x18000c337  jz      short loc_18000C350
0x18000c339  mov     rcx, r14; pSid1
0x18000c33c  call    cs:__imp_EqualSid
0x18000c343  nop     dword ptr [rax+rax+00h]
0x18000c348  test    eax, eax
0x18000c34a  jnz     loc_18000C733
0x18000c350  lea     rdx, [rbp+40h+var_B8]
0x18000c354  lea     rcx, [rsp+140h+pCount+4]
0x18000c359  call    cs:__imp_UMgrEnumerateSessionUsers
0x18000c360  nop     dword ptr [rax+rax+00h]
0x18000c365  test    eax, eax
0x18000c367  js      loc_18000C7F4
0x18000c36d  mov     edi, dword ptr [rsp+140h+var_100]
0x18000c371  mov     eax, [rsp+140h+pCount+4]
0x18000c375  mov     rcx, gs:60h
0x18000c37e  mov     edx, 8; Flags
0x18000c383  shl     eax, 5
0x18000c386  mov     r8d, eax; Size
0x18000c389  mov     rcx, [rcx+30h]; HeapHandle
0x18000c38d  call    cs:__imp_RtlAllocateHeap
0x18000c394  nop     dword ptr [rax+rax+00h]
0x18000c399  mov     rsi, rax
0x18000c39c  test    rax, rax
0x18000c39f  jz      loc_18000CB54
0x18000c3a5  lea     r15, WPP_GLOBAL_Control
0x18000c3ac  cmp     ebx, [rsp+140h+pCount+4]
0x18000c3b0  jb      loc_18000C4D8
0x18000c3b6  mov     rax, [rbp+40h+var_88]
0x18000c3ba  xor     ebx, ebx
0x18000c3bc  mov     [rax], rsi
0x18000c3bf  xor     esi, esi
0x18000c3c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3c8  cmp     rcx, r15
0x18000c3cb  jz      short loc_18000C3DA
0x18000c3cd  test    dword ptr [rcx+1Ch], 100h
0x18000c3d4  jnz     loc_18000CC9A
0x18000c3da  mov     r8, [rsp+140h+P]; P
0x18000c3df  mov     r15, [rsp+140h+var_30]
0x18000c3e7  mov     r13, [rsp+140h+var_20]
0x18000c3ef  test    r8, r8
0x18000c3f2  jz      short loc_18000C40F
0x18000c3f4  mov     rcx, gs:60h
0x18000c3fd  xor     edx, edx; Flags
0x18000c3ff  mov     rcx, [rcx+30h]; HeapHandle
0x18000c403  call    cs:__imp_RtlFreeHeap
0x18000c40a  nop     dword ptr [rax+rax+00h]
0x18000c40f  test    ebx, ebx
0x18000c411  jnz     loc_18000C825
0x18000c417  mov     r14, [rsp+140h+var_28]
0x18000c41f  mov     r12, [rsp+140h+var_18]
0x18000c427  mov     rdi, [rsp+130h]
0x18000c42f  test    rsi, rsi
0x18000c432  jz      short loc_18000C452
0x18000c434  mov     rcx, gs:60h
0x18000c43d  mov     r8, rsi; P
0x18000c440  xor     edx, edx; Flags
0x18000c442  mov     rcx, [rcx+30h]; HeapHandle
0x18000c446  call    cs:__imp_RtlFreeHeap
0x18000c44d  nop     dword ptr [rax+rax+00h]
0x18000c452  mov     rdx, [rsp+140h+ppSessionInfo]
0x18000c457  mov     rsi, [rsp+140h+arg_10]
0x18000c45f  test    rdx, rdx
0x18000c462  jnz     loc_18000CCB8
0x18000c468  mov     rcx, [rbp+40h+var_B8]
0x18000c46c  test    rcx, rcx
0x18000c46f  jz      short loc_18000C486
0x18000c471  lea     rax, [rbp+40h+var_50]
0x18000c475  cmp     rcx, rax
0x18000c478  jz      short loc_18000C486
0x18000c47a  call    cs:__imp_UMgrFreeSessionUsers
0x18000c481  nop     dword ptr [rax+rax+00h]
0x18000c486  mov     rcx, [rbp+40h+hObject]; hObject
0x18000c48a  test    rcx, rcx
0x18000c48d  jz      short loc_18000C49B
0x18000c48f  call    cs:__imp_CloseHandle
0x18000c496  nop     dword ptr [rax+rax+00h]
0x18000c49b  mov     rcx, [rsp+140h+var_E0]; hObject
0x18000c4a0  test    rcx, rcx
0x18000c4a3  jz      short loc_18000C4B1
0x18000c4a5  call    cs:__imp_CloseHandle
0x18000c4ac  nop     dword ptr [rax+rax+00h]
0x18000c4b1  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x18000c4b6  test    rcx, rcx
0x18000c4b9  jnz     loc_18000C88B
0x18000c4bf  mov     eax, ebx
0x18000c4c1  mov     rcx, [rbp+40h+var_40]
0x18000c4c5  xor     rcx, rsp; StackCookie
0x18000c4c8  call    __security_check_cookie
0x18000c4cd  add     rsp, 138h
0x18000c4d4  pop     rbx
0x18000c4d5  pop     rbp
0x18000c4d6  retn
0x18000c4d8  mov     r8, [rsp+140h+P]; P
0x18000c4dd  test    r8, r8
0x18000c4e0  jz      short loc_18000C4FD
0x18000c4e2  mov     rcx, gs:60h
0x18000c4eb  xor     edx, edx; Flags
0x18000c4ed  mov     rcx, [rcx+30h]; HeapHandle
0x18000c4f1  call    cs:__imp_RtlFreeHeap
0x18000c4f8  nop     dword ptr [rax+rax+00h]
0x18000c4fd  mov     rcx, [rsp+140h+TokenHandle]; hObject
0x18000c502  xor     r9d, r9d
0x18000c505  mov     [rsp+140h+P], r9
0x18000c50a  test    rcx, rcx
0x18000c50d  jnz     loc_18000CBA1
0x18000c513  mov     rcx, [rbp+40h+hObject]; hObject
0x18000c517  test    rcx, rcx
0x18000c51a  jnz     loc_18000C937
0x18000c520  mov     rcx, [rsp+140h+var_E0]; hObject
0x18000c525  test    rcx, rcx
0x18000c528  jnz     loc_18000CBBA
0x18000c52e  mov     rcx, [rbp+40h+var_B8]
0x18000c532  test    rcx, rcx
0x18000c535  jz      loc_18000C89C
0x18000c53b  mov     eax, ebx
0x18000c53d  add     rax, rax
0x18000c540  mov     r8d, [rcx+rax*8+8]
0x18000c545  mov     [rsp+140h+pCount], r8d
0x18000c54a  mov     rax, [rcx+rax*8]
0x18000c54e  mov     qword ptr [rsp+140h+var_D8], rax
0x18000c553  cmp     edi, 0FFFFFFFFh
0x18000c556  jnz     loc_18000C701
0x18000c55c  call    cs:__imp_RtlIsMultiSessionSku
0x18000c563  nop     dword ptr [rax+rax+00h]
0x18000c568  mov     ecx, [rsp+140h+pCount]; SessionId
0x18000c56c  test    al, al
0x18000c56e  jz      short loc_18000C578
0x18000c570  test    ecx, ecx
0x18000c572  jz      loc_18000C6F6
0x18000c578  mov     rdx, qword ptr [rsp+140h+var_D8]
0x18000c57d  lea     r9, [rsp+140h+P]
0x18000c582  lea     r8, [rsp+140h+TokenHandle]
0x18000c587  call    UbpmGetUserToken
0x18000c58c  test    eax, eax
0x18000c58e  jnz     loc_18000CC01
0x18000c594  test    r14, r14
0x18000c597  jz      loc_18000C698
0x18000c59d  mov     rdi, [rsp+140h+TokenHandle]
0x18000c5a2  lea     r8, [rsp+140h+TokenInformation]; TokenInformation
0x18000c5a7  xor     eax, eax
0x18000c5a9  xorps   xmm0, xmm0
0x18000c5ac  mov     [rsp+140h+var_F0], eax
0x18000c5b0  mov     r9d, 4; TokenInformationLength
0x18000c5b6  mov     [rsp+140h+var_CC], eax
0x18000c5ba  mov     edx, 12h; TokenInformationClass
0x18000c5bf  mov     [rsp+140h+TokenInformation], eax
0x18000c5c3  mov     rcx, rdi; TokenHandle
0x18000c5c6  mov     [rbp+40h+ExistingTokenHandle], rax
0x18000c5ca  mov     [rsp+140h+var_E0], rax
0x18000c5cf  lea     rax, [rsp+140h+var_F0]
0x18000c5d4  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18000c5d9  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x18000c5dd  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x18000c5e1  movups  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000c5e5  call    cs:__imp_NtQueryInformationToken
0x18000c5ec  nop     dword ptr [rax+rax+00h]
0x18000c5f1  test    eax, eax
0x18000c5f3  js      loc_18000C7A1
0x18000c5f9  mov     eax, [rsp+140h+TokenInformation]
0x18000c5fd  cmp     eax, 2
0x18000c600  jz      loc_18000C8D6
0x18000c606  cmp     eax, 1
0x18000c609  mov     rcx, rdi; TokenHandle
0x18000c60c  lea     rax, [rsp+140h+var_F0]
0x18000c611  mov     [rsp+140h+ReturnLength], rax; ReturnLength
0x18000c616  jz      loc_18000C77D
0x18000c61c  mov     r9d, 8; TokenInformationLength
0x18000c622  lea     r8, [rbp+40h+ExistingTokenHandle]; TokenInformation
0x18000c626  mov     edx, 13h; TokenInformationClass
0x18000c62b  call    cs:__imp_NtQueryInformationToken
0x18000c632  nop     dword ptr [rax+rax+00h]
0x18000c637  test    eax, eax
0x18000c639  js      loc_18000C7A1
0x18000c63f  mov     rax, [rbp+40h+ExistingTokenHandle]
0x18000c643  mov     [rsp+140h+var_E0], rax
0x18000c648  mov     rcx, [rsp+140h+TokenHandle]
0x18000c64d  lea     r8, [rbp+40h+hObject]; DuplicateTokenHandle
0x18000c651  test    rax, rax
0x18000c654  mov     edx, 2; ImpersonationLevel
0x18000c659  cmovnz  rcx, rax; ExistingTokenHandle
0x18000c65d  call    cs:__imp_DuplicateToken
0x18000c664  nop     dword ptr [rax+rax+00h]
0x18000c669  test    eax, eax
0x18000c66b  jz      loc_18000CC45
0x18000c671  mov     rcx, [rbp+40h+hObject]; TokenHandle
0x18000c675  lea     r8, [rsp+140h+IsMember]; IsMember
0x18000c67a  mov     rdx, r14; SidToCheck
0x18000c67d  call    cs:__imp_CheckTokenMembership
0x18000c684  nop     dword ptr [rax+rax+00h]
0x18000c689  test    eax, eax
0x18000c68b  jz      loc_18000CC72
0x18000c691  cmp     [rsp+140h+IsMember], 0
0x18000c696  jz      short loc_18000C6F6
0x18000c698  test    r13, r13
0x18000c69b  jnz     loc_18000C7D3
0x18000c6a1  mov     ecx, [r12]
0x18000c6a5  mov     rax, [rsp+140h+P]
0x18000c6aa  shl     rcx, 5
0x18000c6ae  mov     [rcx+rsi], rax
0x18000c6b2  mov     rax, [rsp+140h+TokenHandle]
0x18000c6b7  mov     ecx, [r12]
0x18000c6bb  shl     rcx, 5
0x18000c6bf  mov     [rcx+rsi+8], rax
0x18000c6c4  mov     ecx, [r12]
0x18000c6c8  mov     eax, [rsp+140h+pCount]
0x18000c6cc  shl     rcx, 5
0x18000c6d0  mov     [rcx+rsi+10h], eax
0x18000c6d4  mov     ecx, [r12]
0x18000c6d8  mov     rax, qword ptr [rsp+140h+var_D8]
0x18000c6dd  shl     rcx, 5
0x18000c6e1  mov     [rcx+rsi+18h], rax
0x18000c6e6  inc     dword ptr [r12]
0x18000c6ea  xor     eax, eax
0x18000c6ec  mov     [rsp+140h+TokenHandle], rax
0x18000c6f1  mov     [rsp+140h+P], rax
0x18000c6f6  mov     edi, dword ptr [rsp+140h+var_100]
0x18000c6fa  inc     ebx
0x18000c6fc  jmp     loc_18000C3AC
0x18000c701  cmp     r8d, edi
0x18000c704  jz      loc_18000C55C
0x18000c70a  jmp     short loc_18000C6F6
0x18000c70c  mov     rdx, cs:qword_18004FF70; pSid2
0x18000c713  test    rdx, rdx
0x18000c716  jz      loc_18000C328
0x18000c71c  mov     rcx, r13; pSid1
0x18000c71f  call    cs:__imp_EqualSid
0x18000c726  nop     dword ptr [rax+rax+00h]
0x18000c72b  test    eax, eax
0x18000c72d  jz      loc_18000C328
0x18000c733  lea     rcx, [rsp+140h+TokenHandle]
0x18000c738  call    cs:__imp_UMgrQueryDefaultAccountToken
0x18000c73f  nop     dword ptr [rax+rax+00h]
0x18000c744  cmp     eax, 80070520h
0x18000c749  jnz     loc_18000C94F
0x18000c74f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c756  lea     r15, WPP_GLOBAL_Control
0x18000c75d  cmp     rcx, r15
0x18000c760  jz      loc_18000C3DA
0x18000c766  test    byte ptr [rcx+1Ch], 2
0x18000c76a  jz      loc_18000C3DA
0x18000c770  mov     edx, 2Ah ; '*'
0x18000c775  mov     r9d, eax
0x18000c778  jmp     loc_18000CCA3
0x18000c77d  mov     r9d, 4; TokenInformationLength
0x18000c783  lea     r8, [rsp+140h+var_CC]; TokenInformation
0x18000c788  mov     edx, 14h; TokenInformationClass
0x18000c78d  call    cs:__imp_NtQueryInformationToken
0x18000c794  nop     dword ptr [rax+rax+00h]
0x18000c799  test    eax, eax
  ... truncated ...
```
