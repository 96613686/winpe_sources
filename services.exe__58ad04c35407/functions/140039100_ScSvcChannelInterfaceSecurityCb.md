# ScSvcChannelInterfaceSecurityCb

- ea: `0x140039100`
- end: `0x1400393f4`
- name: `ScSvcChannelInterfaceSecurityCb`
- size: `756`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x140004c58`
- `0x140013b0c`
- `0x140020e68`
- `0x140039100`
- `0x140041bc4`
- `0x14004401c`
- `0x1400575b0`
- `0x140092060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400392c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003932d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039200`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400392c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003932d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140039377`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400391f6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400391f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400391e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400391e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400393cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400393cb`
- `RPCRT4!RpcImpersonateClient` at `0x1400391c8`
- `RPCRT4!RpcImpersonateClient` at `0x1400391c8`
- `RPCRT4!RpcRevertToSelf` at `0x140039208`
- `RPCRT4!RpcRevertToSelf` at `0x140039252`
- `RPCRT4!RpcRevertToSelf` at `0x140039208`
- `RPCRT4!RpcRevertToSelf` at `0x140039252`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x140039154`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x140039154`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400392b9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140039323`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14003936d`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1400392b9`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x140039323`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x14003936d`

## pseudocode

```c
__int64 __fastcall ScSvcChannelInterfaceSecurityCb(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  DWORD LastError; // ebx
  RPC_STATUS v4; // eax
  HANDLE CurrentThread; // rax
  unsigned int v6; // esi
  PRPC_ASYNC_STATE v7; // rcx
  __int64 v8; // rdx
  void *v9; // rcx
  WINBOOL IsMember; // [rsp+24h] [rbp-45h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-41h] BYREF
  _DWORD RpcCallAttributes[32]; // [rsp+30h] [rbp-39h] BYREF

  memset(&RpcCallAttributes[1], 0, 0x74u);
  TokenHandle = 0;
  IsMember = 0;
  RpcCallAttributes[0] = 3;
  LastError = RpcServerInqCallAttributesW(Context, RpcCallAttributes);
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 133, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, LastError);
    goto LABEL_42;
  }
  if ( RpcCallAttributes[14] != 3 || RpcCallAttributes[12] || RpcCallAttributes[10] != 6 || RpcCallAttributes[11] != 10 )
    goto LABEL_41;
  v4 = RpcImpersonateClient(0);
  LastError = v4;
  if ( v4 )
  {
    ScLogImpersonateFailureEvent(v4);
    goto LABEL_42;
  }
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v6 = RpcRevertToSelf();
  }
  else
  {
    LastError = GetLastError();
    v6 = RpcRevertToSelf();
    if ( LastError )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_42;
      v8 = 134;
      goto LABEL_16;
    }
  }
  if ( !v6 )
  {
    if ( !CheckTokenMembership(TokenHandle, ServiceLogonSid, &IsMember) )
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_42;
      v8 = 136;
      goto LABEL_16;
    }
    v9 = TokenHandle;
    if ( IsMember == 1 )
    {
LABEL_28:
      ScCheckServiceLogonSid(v9);
      LastError = 0;
      goto LABEL_42;
    }
    if ( !CheckTokenMembership(TokenHandle, LocalSystemSid, &IsMember) )
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_42;
      v8 = 137;
      goto LABEL_16;
    }
    v9 = TokenHandle;
    if ( IsMember == 1 )
      goto LABEL_28;
    if ( !CheckTokenMembership(TokenHandle, AllRestrictedServicesSid, &IsMember) )
    {
      LastError = GetLastError();
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        goto LABEL_42;
      v8 = 138;
LABEL_16:
      WPP_SF_d(v7->StubInfo, v8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, LastError);
      goto LABEL_42;
    }
    v9 = TokenHandle;
    if ( IsMember == 1 )
      goto LABEL_28;
    if ( (unsigned int)ScCheckForUserServiceClaim(TokenHandle) )
    {
      LastError = 0;
      goto LABEL_42;
    }
LABEL_41:
    LastError = 5;
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 135, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids, v6);
  ScLogEvent(5u, L"RpcRevertToSelf", v6);
  LastError = v6;
LABEL_42:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x140039100  mov     [rsp-8+arg_0], rbx
0x140039105  mov     [rsp-8+arg_10], rsi
0x14003910a  push    rbp
0x14003910b  lea     rbp, [rsp-57h]
0x140039110  sub     rsp, 0C0h
0x140039117  mov     rax, cs:__security_cookie
0x14003911e  xor     rax, rsp
0x140039121  mov     [rbp+57h+var_10], rax
0x140039125  mov     rbx, rdx
0x140039128  lea     rcx, [rbp+57h+var_8C]; void *
0x14003912c  xor     edx, edx; Val
0x14003912e  lea     r8d, [rdx+74h]; Size
0x140039132  call    memset
0x140039137  lea     rdx, [rbp+57h+RpcCallAttributes]; RpcCallAttributes
0x14003913b  mov     [rbp+57h+TokenHandle], 0
0x140039143  mov     rcx, rbx; ClientBinding
0x140039146  mov     [rbp+57h+IsMember], 0
0x14003914d  mov     [rbp+57h+RpcCallAttributes], 3
0x140039154  call    cs:__imp_RpcServerInqCallAttributesW
0x14003915a  mov     ebx, eax
0x14003915c  test    eax, eax
0x14003915e  jz      short loc_14003919E
0x140039160  mov     rcx, cs:WPP_GLOBAL_Control
0x140039167  lea     rax, WPP_GLOBAL_Control
0x14003916e  cmp     rcx, rax
0x140039171  jz      loc_1400393C2
0x140039177  test    byte ptr [rcx+1Ch], 1
0x14003917b  jz      loc_1400393C2
0x140039181  mov     rcx, [rcx+10h]
0x140039185  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x14003918c  mov     edx, 85h
0x140039191  mov     r9d, ebx
0x140039194  call    WPP_SF_d
0x140039199  jmp     loc_1400393C2
0x14003919e  cmp     [rbp+57h+var_58], 3
0x1400391a2  jnz     loc_1400393BD
0x1400391a8  cmp     [rbp+57h+var_60], 0
0x1400391ac  jnz     loc_1400393BD
0x1400391b2  cmp     [rbp+57h+var_68], 6
0x1400391b6  jnz     loc_1400393BD
0x1400391bc  cmp     [rbp+57h+var_64], 0Ah
0x1400391c0  jnz     loc_1400393BD
0x1400391c6  xor     ecx, ecx; BindingHandle
0x1400391c8  call    cs:__imp_RpcImpersonateClient
0x1400391ce  mov     ebx, eax
0x1400391d0  test    eax, eax
0x1400391d2  jz      short loc_1400391E0
0x1400391d4  mov     ecx, eax; int
0x1400391d6  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x1400391db  jmp     loc_1400393C2
0x1400391e0  call    cs:__imp_GetCurrentThread
0x1400391e6  mov     edx, 8; DesiredAccess
0x1400391eb  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1400391ef  mov     rcx, rax; ThreadHandle
0x1400391f2  lea     r8d, [rdx-7]; OpenAsSelf
0x1400391f6  call    cs:__imp_OpenThreadToken
0x1400391fc  test    eax, eax
0x1400391fe  jnz     short loc_140039252
0x140039200  call    cs:__imp_GetLastError
0x140039206  mov     ebx, eax
0x140039208  call    cs:__imp_RpcRevertToSelf
0x14003920e  mov     esi, eax
0x140039210  test    ebx, ebx
0x140039212  jz      short loc_14003925A
0x140039214  mov     rcx, cs:WPP_GLOBAL_Control
0x14003921b  lea     rax, WPP_GLOBAL_Control
0x140039222  cmp     rcx, rax
0x140039225  jz      loc_1400393C2
0x14003922b  test    byte ptr [rcx+1Ch], 1
0x14003922f  jz      loc_1400393C2
0x140039235  mov     edx, 86h
0x14003923a  mov     rcx, [rcx+10h]
0x14003923e  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140039245  mov     r9d, ebx
0x140039248  call    WPP_SF_d
0x14003924d  jmp     loc_1400393C2
0x140039252  call    cs:__imp_RpcRevertToSelf
0x140039258  mov     esi, eax
0x14003925a  test    esi, esi
0x14003925c  jz      short loc_1400392AA
0x14003925e  mov     rcx, cs:WPP_GLOBAL_Control
0x140039265  lea     rax, WPP_GLOBAL_Control
0x14003926c  cmp     rcx, rax
0x14003926f  jz      short loc_14003928F
0x140039271  test    byte ptr [rcx+1Ch], 1
0x140039275  jz      short loc_14003928F
0x140039277  mov     rcx, [rcx+10h]
0x14003927b  lea     r8, WPP_a8d36da9c4e335f01a31191f807fb9a3_Traceguids
0x140039282  mov     edx, 87h
0x140039287  mov     r9d, esi
0x14003928a  call    WPP_SF_d
0x14003928f  mov     r8d, esi
0x140039292  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140039299  mov     ecx, 5; unsigned int
0x14003929e  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x1400392a3  mov     ebx, esi
0x1400392a5  jmp     loc_1400393C2
0x1400392aa  mov     rdx, cs:ServiceLogonSid; SidToCheck
0x1400392b1  lea     r8, [rbp+57h+IsMember]; IsMember
0x1400392b5  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400392b9  call    cs:__imp_CheckTokenMembership
0x1400392bf  test    eax, eax
0x1400392c1  jnz     short loc_1400392F6
0x1400392c3  call    cs:__imp_GetLastError
0x1400392c9  mov     ebx, eax
0x1400392cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400392d2  lea     rax, WPP_GLOBAL_Control
0x1400392d9  cmp     rcx, rax
0x1400392dc  jz      loc_1400393C2
0x1400392e2  test    byte ptr [rcx+1Ch], 1
0x1400392e6  jz      loc_1400393C2
0x1400392ec  mov     edx, 88h
0x1400392f1  jmp     loc_14003923A
0x1400392f6  cmp     [rbp+57h+IsMember], 1
0x1400392fa  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400392fe  jnz     short loc_140039318
0x140039300  lea     rdx, [rbp+57h+var_A0]
0x140039304  mov     [rbp+57h+var_A0], 0
0x14003930b  call    ScCheckServiceLogonSid
0x140039310  mov     ebx, [rbp+57h+var_A0]
0x140039313  jmp     loc_1400393C2
0x140039318  mov     rdx, cs:LocalSystemSid; SidToCheck
0x14003931f  lea     r8, [rbp+57h+IsMember]; IsMember
0x140039323  call    cs:__imp_CheckTokenMembership
0x140039329  test    eax, eax
0x14003932b  jnz     short loc_140039358
0x14003932d  call    cs:__imp_GetLastError
0x140039333  mov     ebx, eax
0x140039335  mov     rcx, cs:WPP_GLOBAL_Control
0x14003933c  lea     rax, WPP_GLOBAL_Control
0x140039343  cmp     rcx, rax
0x140039346  jz      short loc_1400393C2
0x140039348  test    byte ptr [rcx+1Ch], 1
0x14003934c  jz      short loc_1400393C2
0x14003934e  mov     edx, 89h
0x140039353  jmp     loc_14003923A
0x140039358  cmp     [rbp+57h+IsMember], 1
0x14003935c  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140039360  jz      short loc_140039300
0x140039362  mov     rdx, cs:AllRestrictedServicesSid; SidToCheck
0x140039369  lea     r8, [rbp+57h+IsMember]; IsMember
0x14003936d  call    cs:__imp_CheckTokenMembership
0x140039373  test    eax, eax
0x140039375  jnz     short loc_1400393A2
0x140039377  call    cs:__imp_GetLastError
0x14003937d  mov     ebx, eax
0x14003937f  mov     rcx, cs:WPP_GLOBAL_Control
0x140039386  lea     rax, WPP_GLOBAL_Control
0x14003938d  cmp     rcx, rax
0x140039390  jz      short loc_1400393C2
0x140039392  test    byte ptr [rcx+1Ch], 1
0x140039396  jz      short loc_1400393C2
0x140039398  mov     edx, 8Ah
0x14003939d  jmp     loc_14003923A
0x1400393a2  cmp     [rbp+57h+IsMember], 1
0x1400393a6  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400393aa  jz      loc_140039300
0x1400393b0  call    ?ScCheckForUserServiceClaim@@YAHPEAX@Z; ScCheckForUserServiceClaim(void *)
0x1400393b5  test    eax, eax
0x1400393b7  jz      short loc_1400393BD
0x1400393b9  xor     ebx, ebx
0x1400393bb  jmp     short loc_1400393C2
0x1400393bd  mov     ebx, 5
0x1400393c2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x1400393c6  test    rcx, rcx
0x1400393c9  jz      short loc_1400393D1
0x1400393cb  call    cs:__imp_CloseHandle
0x1400393d1  mov     eax, ebx
0x1400393d3  mov     rcx, [rbp+57h+var_10]
0x1400393d7  xor     rcx, rsp; StackCookie
0x1400393da  call    __security_check_cookie
0x1400393df  lea     r11, [rsp+0C0h+var_s0]
0x1400393e7  mov     rbx, [r11+10h]
0x1400393eb  mov     rsi, [r11+20h]
0x1400393ef  mov     rsp, r11
0x1400393f2  pop     rbp
0x1400393f3  retn
```
