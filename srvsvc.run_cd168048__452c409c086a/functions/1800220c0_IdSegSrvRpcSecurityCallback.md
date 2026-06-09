# IdSegSrvRpcSecurityCallback

- ea: `0x1800220c0`
- end: `0x18002236e`
- name: `IdSegSrvRpcSecurityCallback`
- size: `686`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001deb0`
- `0x180020dc0`
- `0x180020de8`
- `0x1800220c0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800222aa`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800222aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022294`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800222b4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002225a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002225a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022244`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022244`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002231d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002231d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800221bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800221bd`
- `RPCRT4!RpcStringBindingParseW` at `0x180022165`
- `RPCRT4!RpcStringBindingParseW` at `0x180022165`
- `RPCRT4!RpcStringFreeW` at `0x1800222fe`
- `RPCRT4!RpcStringFreeW` at `0x18002230e`
- `RPCRT4!RpcStringFreeW` at `0x1800222fe`
- `RPCRT4!RpcStringFreeW` at `0x18002230e`
- `RPCRT4!RpcImpersonateClient` at `0x18002220a`
- `RPCRT4!RpcImpersonateClient` at `0x18002220a`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002212d`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18002212d`
- `RPCRT4!RpcBindingFree` at `0x1800222ee`
- `RPCRT4!RpcBindingFree` at `0x1800222ee`
- `RPCRT4!RpcRevertToSelf` at `0x180022262`
- `RPCRT4!RpcRevertToSelf` at `0x180022262`
- `RPCRT4!RpcBindingServerFromClient` at `0x180022113`
- `RPCRT4!RpcBindingServerFromClient` at `0x180022113`

## pseudocode

```c
__int64 __fastcall IdSegSrvRpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  DWORD LastError; // ebx
  DWORD v4; // eax
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  HANDLE CurrentThread; // rax
  BOOL v8; // edi
  WINBOOL IsMember; // [rsp+30h] [rbp-48h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-40h] BYREF
  RPC_WSTR Protseq; // [rsp+40h] [rbp-38h] BYREF
  RPC_BINDING_HANDLE ServerBinding; // [rsp+48h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-28h] BYREF
  _DWORD SidToCheck[4]; // [rsp+58h] [rbp-20h] BYREF

  IsMember = 1;
  ServerBinding = 0;
  StringBinding = 0;
  Protseq = 0;
  TokenHandle = 0;
  SidToCheck[0] = 257;
  SidToCheck[1] = 83886080;
  SidToCheck[2] = 18;
  if ( RpcBindingServerFromClient(Context, &ServerBinding) )
    return 5;
  if ( RpcBindingToStringBindingW(ServerBinding, &StringBinding) )
  {
    LastError = 5;
  }
  else
  {
    v4 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    LastError = v4;
    if ( v4 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        goto LABEL_34;
      }
      v6 = 10;
    }
    else
    {
      if ( lstrcmpW(Protseq, L"ncalrpc") )
      {
        LastError = 5;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids);
        }
        goto LABEL_34;
      }
      v4 = RpcImpersonateClient(0);
      LastError = v4;
      if ( v4 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_34;
        }
        v6 = 12;
      }
      else
      {
        CurrentThread = GetCurrentThread();
        v8 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
        v4 = RpcRevertToSelf();
        LastError = v4;
        if ( v4 )
        {
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_34;
          }
          v6 = 13;
        }
        else
        {
          if ( !v8 )
          {
            LastError = GetLastError();
            goto LABEL_34;
          }
          if ( CheckTokenMembership(TokenHandle, SidToCheck, &IsMember) )
          {
            LastError = IsMember == 0 ? 5 : 0;
            goto LABEL_34;
          }
          v4 = GetLastError();
          LastError = v4;
          v5 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
            || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            goto LABEL_34;
          }
          v6 = 14;
        }
      }
    }
    WPP_SF_d(v5[2], v6, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids, v4);
  }
LABEL_34:
  RpcBindingFree(&ServerBinding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids, LastError);
  }
  return LastError;
}

```

## disassembly

```asm
0x1800220c0  push    rbp
0x1800220c2  push    rbx
0x1800220c3  push    rsi
0x1800220c4  push    rdi
0x1800220c5  push    r12
0x1800220c7  push    r13
0x1800220c9  mov     rbp, rsp
0x1800220cc  sub     rsp, 78h
0x1800220d0  mov     rax, cs:__security_cookie
0x1800220d7  xor     rax, rsp
0x1800220da  mov     [rbp+var_10], rax
0x1800220de  xor     esi, esi
0x1800220e0  mov     [rbp+IsMember], 1
0x1800220e7  mov     rcx, rdx; ClientBinding
0x1800220ea  mov     [rbp+ServerBinding], rsi
0x1800220ee  lea     rdx, [rbp+ServerBinding]; ServerBinding
0x1800220f2  mov     [rbp+StringBinding], rsi
0x1800220f6  mov     [rbp+Protseq], rsi
0x1800220fa  mov     [rbp+TokenHandle], rsi
0x1800220fe  mov     [rbp+SidToCheck], 101h
0x180022105  mov     [rbp+var_1C], 5000000h
0x18002210c  mov     [rbp+var_18], 12h
0x180022113  call    cs:__imp_RpcBindingServerFromClient
0x180022119  test    eax, eax
0x18002211b  jz      short loc_180022125
0x18002211d  lea     eax, [rsi+5]
0x180022120  jmp     loc_180022355
0x180022125  mov     rcx, [rbp+ServerBinding]; Binding
0x180022129  lea     rdx, [rbp+StringBinding]; StringBinding
0x18002212d  call    cs:__imp_RpcBindingToStringBindingW
0x180022133  lea     r13, WPP_GLOBAL_Control
0x18002213a  mov     r12d, 400h
0x180022140  test    eax, eax
0x180022142  jz      short loc_18002214E
0x180022144  mov     ebx, 5
0x180022149  jmp     loc_1800222EA
0x18002214e  mov     rcx, [rbp+StringBinding]; StringBinding
0x180022152  lea     r8, [rbp+Protseq]; Protseq
0x180022156  mov     [rsp+78h+NetworkOptions], rsi; NetworkOptions
0x18002215b  xor     r9d, r9d; NetworkAddr
0x18002215e  xor     edx, edx; ObjUuid
0x180022160  mov     [rsp+78h+Endpoint], rsi; Endpoint
0x180022165  call    cs:__imp_RpcStringBindingParseW
0x18002216b  mov     ebx, eax
0x18002216d  test    eax, eax
0x18002216f  jz      short loc_1800221B2
0x180022171  mov     rcx, cs:WPP_GLOBAL_Control
0x180022178  cmp     rcx, r13
0x18002217b  jz      loc_1800222EA
0x180022181  test    [rcx+1Ch], r12d
0x180022185  jz      loc_1800222EA
0x18002218b  cmp     byte ptr [rcx+19h], 1
0x18002218f  jb      loc_1800222EA
0x180022195  mov     edx, 0Ah
0x18002219a  mov     rcx, [rcx+10h]
0x18002219e  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x1800221a5  mov     r9d, eax
0x1800221a8  call    WPP_SF_d
0x1800221ad  jmp     loc_1800222EA
0x1800221b2  mov     rcx, [rbp+Protseq]; lpString1
0x1800221b6  lea     rdx, String2; "ncalrpc"
0x1800221bd  call    cs:__imp_lstrcmpW
0x1800221c3  test    eax, eax
0x1800221c5  jz      short loc_180022208
0x1800221c7  mov     ebx, 5
0x1800221cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800221d3  cmp     rcx, r13
0x1800221d6  jz      loc_1800222EA
0x1800221dc  test    [rcx+1Ch], r12d
0x1800221e0  jz      loc_1800222EA
0x1800221e6  cmp     byte ptr [rcx+19h], 1
0x1800221ea  jb      loc_1800222EA
0x1800221f0  mov     rcx, [rcx+10h]
0x1800221f4  lea     edx, [rbx+6]
0x1800221f7  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x1800221fe  call    WPP_SF_
0x180022203  jmp     loc_1800222EA
0x180022208  xor     ecx, ecx; BindingHandle
0x18002220a  call    cs:__imp_RpcImpersonateClient
0x180022210  mov     ebx, eax
0x180022212  test    eax, eax
0x180022214  jz      short loc_180022244
0x180022216  mov     rcx, cs:WPP_GLOBAL_Control
0x18002221d  cmp     rcx, r13
0x180022220  jz      loc_1800222EA
0x180022226  test    [rcx+1Ch], r12d
0x18002222a  jz      loc_1800222EA
0x180022230  cmp     byte ptr [rcx+19h], 1
0x180022234  jb      loc_1800222EA
0x18002223a  mov     edx, 0Ch
0x18002223f  jmp     loc_18002219A
0x180022244  call    cs:__imp_GetCurrentThread
0x18002224a  mov     edx, 8; DesiredAccess
0x18002224f  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180022253  mov     rcx, rax; ThreadHandle
0x180022256  lea     r8d, [rdx-7]; OpenAsSelf
0x18002225a  call    cs:__imp_OpenThreadToken
0x180022260  mov     edi, eax
0x180022262  call    cs:__imp_RpcRevertToSelf
0x180022268  mov     ebx, eax
0x18002226a  test    eax, eax
0x18002226c  jz      short loc_180022290
0x18002226e  mov     rcx, cs:WPP_GLOBAL_Control
0x180022275  cmp     rcx, r13
0x180022278  jz      short loc_1800222EA
0x18002227a  test    [rcx+1Ch], r12d
0x18002227e  jz      short loc_1800222EA
0x180022280  cmp     byte ptr [rcx+19h], 1
0x180022284  jb      short loc_1800222EA
0x180022286  mov     edx, 0Dh
0x18002228b  jmp     loc_18002219A
0x180022290  test    edi, edi
0x180022292  jnz     short loc_18002229E
0x180022294  call    cs:__imp_GetLastError
0x18002229a  mov     ebx, eax
0x18002229c  jmp     short loc_1800222EA
0x18002229e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800222a2  lea     r8, [rbp+IsMember]; IsMember
0x1800222a6  lea     rdx, [rbp+SidToCheck]; SidToCheck
0x1800222aa  call    cs:__imp_CheckTokenMembership
0x1800222b0  test    eax, eax
0x1800222b2  jnz     short loc_1800222DE
0x1800222b4  call    cs:__imp_GetLastError
0x1800222ba  mov     ebx, eax
0x1800222bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800222c3  cmp     rcx, r13
0x1800222c6  jz      short loc_1800222EA
0x1800222c8  test    [rcx+1Ch], r12d
0x1800222cc  jz      short loc_1800222EA
0x1800222ce  cmp     byte ptr [rcx+19h], 1
0x1800222d2  jb      short loc_1800222EA
0x1800222d4  mov     edx, 0Eh
0x1800222d9  jmp     loc_18002219A
0x1800222de  mov     eax, [rbp+IsMember]
0x1800222e1  neg     eax
0x1800222e3  sbb     ebx, ebx
0x1800222e5  not     ebx
0x1800222e7  and     ebx, 5
0x1800222ea  lea     rcx, [rbp+ServerBinding]; Binding
0x1800222ee  call    cs:__imp_RpcBindingFree
0x1800222f4  cmp     [rbp+StringBinding], rsi
0x1800222f8  jz      short loc_180022304
0x1800222fa  lea     rcx, [rbp+StringBinding]; String
0x1800222fe  call    cs:__imp_RpcStringFreeW
0x180022304  cmp     [rbp+Protseq], rsi
0x180022308  jz      short loc_180022314
0x18002230a  lea     rcx, [rbp+Protseq]; String
0x18002230e  call    cs:__imp_RpcStringFreeW
0x180022314  mov     rcx, [rbp+TokenHandle]; hObject
0x180022318  test    rcx, rcx
0x18002231b  jz      short loc_180022323
0x18002231d  call    cs:__imp_CloseHandle
0x180022323  mov     rcx, cs:WPP_GLOBAL_Control
0x18002232a  cmp     rcx, r13
0x18002232d  jz      short loc_180022353
0x18002232f  test    [rcx+1Ch], r12d
0x180022333  jz      short loc_180022353
0x180022335  cmp     byte ptr [rcx+19h], 1
0x180022339  jb      short loc_180022353
0x18002233b  mov     rcx, [rcx+10h]
0x18002233f  lea     r8, WPP_ab6e649d781a3ca20308d30499d09a0b_Traceguids
0x180022346  mov     edx, 0Fh
0x18002234b  mov     r9d, ebx
0x18002234e  call    WPP_SF_d
0x180022353  mov     eax, ebx
0x180022355  mov     rcx, [rbp+var_10]
0x180022359  xor     rcx, rsp; StackCookie
0x18002235c  call    __security_check_cookie
0x180022361  add     rsp, 78h
0x180022365  pop     r13
0x180022367  pop     r12
0x180022369  pop     rdi
0x18002236a  pop     rsi
0x18002236b  pop     rbx
0x18002236c  pop     rbp
0x18002236d  retn
```
