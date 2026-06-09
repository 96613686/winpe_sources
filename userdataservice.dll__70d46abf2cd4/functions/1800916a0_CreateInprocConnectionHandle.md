# CreateInprocConnectionHandle

- ea: `0x1800916a0`
- end: `0x180091884`
- name: `CreateInprocConnectionHandle`
- size: `484`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE IfSpec, RPC_BINDING_HANDLE *)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800303cc`
- `0x18007e9c8`
- `0x1800916a0`
- `0x18009188c`
- `0x1800918dc`
- `0x18009d104`
- `0x18012c7b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009173d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009178f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009173d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009178f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009170a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009170a`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180091785`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180091785`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180091720`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180091720`
- `RPCRT4!RpcBindingCreateW` at `0x1800917f7`
- `RPCRT4!RpcBindingCreateW` at `0x1800917f7`
- `RPCRT4!RpcBindingBind` at `0x18009181c`
- `RPCRT4!RpcBindingBind` at `0x18009181c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180091733`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180091733`

## string_xrefs

- `0x1800916c8`: `UnitTestUserDataModelService`

## pseudocode

```c
__int64 __fastcall CreateInprocConnectionHandle(RPC_IF_HANDLE IfSpec, RPC_BINDING_HANDLE *a2)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v6; // r8
  bool v7; // sf
  int v8; // eax
  __int64 v9; // r8
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r9
  signed int v14; // eax
  RPC_BINDING_HANDLE *v15; // rax
  RPC_STATUS v16; // eax
  RPC_STATUS v17; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+40h] [rbp-39h] BYREF
  unsigned __int16 v22[8]; // [rsp+78h] [rbp-1h] BYREF
  __int128 v23; // [rsp+88h] [rbp+Fh]
  _OWORD v24[2]; // [rsp+98h] [rbp+1Fh]

  Binding = 0;
  *(_OWORD *)v22 = *(_OWORD *)L"UnitTestUserDataModelService";
  TokenHandle = 0;
  v23 = *(_OWORD *)L"UserDataModelService";
  v24[0] = *(_OWORD *)L"ModelService";
  *(_OWORD *)((char *)v24 + 10) = *(_OWORD *)L"Service";
  CurrentThread = GetCurrentThread();
  OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle);
  if ( TokenHandle && !RevertToSelf() )
  {
    LastError = GetLastError();
    v7 = LastError < 0;
    if ( LastError > 0 )
    {
      LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = LastError < 0;
    }
    if ( v7 )
      Log_HREvent_47((unsigned int)LastError, 0, v6, 82);
  }
  v8 = RegisterDataModelEndpoint(v22);
  v10 = v8;
  if ( v8 >= 0 )
  {
    if ( !TokenHandle || SetThreadToken(0, TokenHandle) )
    {
      *(_QWORD *)&Template.Version = 1;
      Template.StringEndpoint = v22;
      *(_QWORD *)&Template.ProtocolSequence = 3;
      Template.NetworkAddress = 0;
      memset(&Template.u1, 0, 24);
      v15 = (RPC_BINDING_HANDLE *)tlx::replace<void *,void (*)(void *),&void _CloseBinder(void *),0>(&Binding);
      v16 = RpcBindingCreateW(&Template, 0, 0, v15);
      v10 = v16;
      if ( v16 )
      {
        if ( v16 > 0 )
          v10 = (unsigned __int16)v16 | 0x80070000;
        v13 = 102;
      }
      else
      {
        v17 = RpcBindingBind(0, Binding, IfSpec);
        v10 = v17;
        if ( !v17 )
        {
          v10 = 0;
          *a2 = Binding;
          Binding = 0;
          goto LABEL_25;
        }
        if ( v17 > 0 )
          v10 = (unsigned __int16)v17 | 0x80070000;
        v13 = 104;
      }
    }
    else
    {
      v14 = GetLastError();
      v10 = v14;
      if ( v14 > 0 )
        v10 = (unsigned __int16)v14 | 0x80070000;
      v13 = 90;
    }
    v11 = 0;
    v12 = v10;
  }
  else
  {
    v11 = 1;
    v12 = (unsigned int)v8;
    v13 = 86;
  }
  Log_HREvent_47(v12, v11, v9, v13);
LABEL_25:
  tlx::auto_xxx<void *,int (*)(void *),&int CloseHandle(void *),0>::_Delete(&TokenHandle);
  tlx::auto_xxx<void *,void (*)(void *),&void _CloseBinder(void *),0>::_Delete(&Binding);
  return v10;
}

```

## disassembly

```asm
0x1800916a0  mov     [rsp-8+arg_10], rbx
0x1800916a5  mov     [rsp-8+arg_18], rsi
0x1800916aa  push    rbp
0x1800916ab  push    rdi
0x1800916ac  push    r15
0x1800916ae  lea     rbp, [rsp-47h]
0x1800916b3  sub     rsp, 0C0h
0x1800916ba  mov     rax, cs:__security_cookie
0x1800916c1  xor     rax, rsp
0x1800916c4  mov     [rbp+57h+var_18], rax
0x1800916c8  movups  xmm0, xmmword ptr cs:aUnittestuserda; "UnitTestUserDataModelService"
0x1800916cf  mov     rdi, rdx
0x1800916d2  mov     rsi, rcx
0x1800916d5  movups  xmm1, xmmword ptr cs:aUnittestuserda+10h; "UserDataModelService"
0x1800916dc  mov     [rbp+57h+Binding], 0
0x1800916e4  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x1800916e8  mov     [rbp+57h+TokenHandle], 0
0x1800916f0  movups  xmm0, xmmword ptr cs:aUnittestuserda+20h; "ModelService"
0x1800916f7  movups  [rbp+57h+var_48], xmm1
0x1800916fb  movups  xmm1, xmmword ptr cs:aUnittestuserda+2Ah; "Service"
0x180091702  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x180091706  movups  xmmword ptr [rbp+57h+var_38+0Ah], xmm1
0x18009170a  call    cs:__imp_GetCurrentThread
0x180091710  mov     edx, 4; DesiredAccess
0x180091715  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180091719  mov     rcx, rax; ThreadHandle
0x18009171c  lea     r8d, [rdx-3]; OpenAsSelf
0x180091720  call    cs:__imp_OpenThreadToken
0x180091726  cmp     [rbp+57h+TokenHandle], 0
0x18009172b  mov     r15d, 80070000h
0x180091731  jz      short loc_18009175E
0x180091733  call    cs:__imp_RevertToSelf
0x180091739  test    eax, eax
0x18009173b  jnz     short loc_18009175E
0x18009173d  call    cs:__imp_GetLastError
0x180091743  test    eax, eax
0x180091745  jle     short loc_18009174F
0x180091747  movzx   eax, ax
0x18009174a  or      eax, r15d
0x18009174d  test    eax, eax
0x18009174f  jns     short loc_18009175E
0x180091751  xor     edx, edx
0x180091753  mov     ecx, eax
0x180091755  lea     r9d, [rdx+52h]
0x180091759  call    Log_HREvent_47
0x18009175e  lea     rcx, [rbp+57h+var_58]; unsigned __int16 *
0x180091762  call    ?RegisterDataModelEndpoint@@YAJPEBG@Z; RegisterDataModelEndpoint(ushort const *)
0x180091767  mov     ebx, eax
0x180091769  test    eax, eax
0x18009176b  jns     short loc_18009177A
0x18009176d  mov     edx, 1
0x180091772  mov     ecx, eax
0x180091774  lea     r9d, [rdx+55h]
0x180091778  jmp     short loc_1800917AB
0x18009177a  mov     rdx, [rbp+57h+TokenHandle]; Token
0x18009177e  test    rdx, rdx
0x180091781  jz      short loc_1800917B5
0x180091783  xor     ecx, ecx; Thread
0x180091785  call    cs:__imp_SetThreadToken
0x18009178b  test    eax, eax
0x18009178d  jnz     short loc_1800917B5
0x18009178f  call    cs:__imp_GetLastError
0x180091795  mov     ebx, eax
0x180091797  test    eax, eax
0x180091799  jle     short loc_1800917A1
0x18009179b  movzx   ebx, ax
0x18009179e  or      ebx, r15d
0x1800917a1  mov     r9d, 5Ah ; 'Z'
0x1800917a7  xor     edx, edx
0x1800917a9  mov     ecx, ebx
0x1800917ab  call    Log_HREvent_47
0x1800917b0  jmp     loc_18009184C
0x1800917b5  lea     rax, [rbp+57h+var_58]
0x1800917b9  mov     qword ptr [rbp+57h+Template.Version], 1
0x1800917c1  mov     [rbp+57h+Template.StringEndpoint], rax
0x1800917c5  lea     rcx, [rbp+57h+Binding]
0x1800917c9  xor     eax, eax
0x1800917cb  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x1800917d3  xorps   xmm0, xmm0
0x1800917d6  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x1800917da  mov     [rbp+57h+Template.NetworkAddress], 0
0x1800917e2  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x1800917e6  call    ??$replace@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@YAPEAPEAXAEAV?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@0@@Z; tlx::replace<void *,void (*)(void *),&_CloseBinder(void *),0>(tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0> &)
0x1800917eb  mov     r9, rax; Binding
0x1800917ee  lea     rcx, [rbp+57h+Template]; Template
0x1800917f2  xor     r8d, r8d; Options
0x1800917f5  xor     edx, edx; Security
0x1800917f7  call    cs:__imp_RpcBindingCreateW
0x1800917fd  mov     ebx, eax
0x1800917ff  test    eax, eax
0x180091801  jz      short loc_180091813
0x180091803  jle     short loc_18009180B
0x180091805  movzx   ebx, ax
0x180091808  or      ebx, r15d
0x18009180b  mov     r9d, 66h ; 'f'
0x180091811  jmp     short loc_1800917A7
0x180091813  mov     rdx, [rbp+57h+Binding]; Binding
0x180091817  mov     r8, rsi; IfSpec
0x18009181a  xor     ecx, ecx; pAsync
0x18009181c  call    cs:__imp_RpcBindingBind
0x180091822  mov     ebx, eax
0x180091824  test    eax, eax
0x180091826  jz      short loc_18009183B
0x180091828  jle     short loc_180091830
0x18009182a  movzx   ebx, ax
0x18009182d  or      ebx, r15d
0x180091830  mov     r9d, 68h ; 'h'
0x180091836  jmp     loc_1800917A7
0x18009183b  mov     rax, [rbp+57h+Binding]
0x18009183f  xor     ebx, ebx
0x180091841  mov     [rdi], rax
0x180091844  mov     [rbp+57h+Binding], 0
0x18009184c  lea     rcx, [rbp+57h+TokenHandle]
0x180091850  call    ?_Delete@?$auto_xxx@PEAXP6AHPEAX@Z$1?CloseHandle@@YAH0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,int (*)(void *),&CloseHandle(void *),0>::_Delete(void)
0x180091855  lea     rcx, [rbp+57h+Binding]
0x180091859  call    ?_Delete@?$auto_xxx@PEAXP6AXPEAX@Z$1?_CloseBinder@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void (*)(void *),&_CloseBinder(void *),0>::_Delete(void)
0x18009185e  mov     eax, ebx
0x180091860  mov     rcx, [rbp+57h+var_18]
0x180091864  xor     rcx, rsp; StackCookie
0x180091867  call    __security_check_cookie
0x18009186c  lea     r11, [rsp+0D0h+var_10]
0x180091874  mov     rbx, [r11+30h]
0x180091878  mov     rsi, [r11+38h]
0x18009187c  mov     rsp, r11
0x18009187f  pop     r15
0x180091881  pop     rdi
0x180091882  pop     rbp
0x180091883  retn
```
