# WcnRpcSecurityCheckAccess

- ea: `0x180039228`
- end: `0x1800394bd`
- name: `WcnRpcSecurityCheckAccess`
- size: `661`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE ClientBinding, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039090`
- `0x180039690`

## callees

- `0x180004fb8`
- `0x180005014`
- `0x180005088`
- `0x180039228`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039387`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039387`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x18003946f`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x18003946f`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x1800392fb`
- `RPCRT4!RpcGetAuthorizationContextForClient` at `0x1800392fb`
- `AUTHZ!AuthzAccessCheck` at `0x18003937d`
- `AUTHZ!AuthzAccessCheck` at `0x18003937d`

## pseudocode

```c
__int64 __fastcall WcnRpcSecurityCheckAccess(
        RPC_BINDING_HANDLE ClientBinding,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  const char *Indent; // rax
  __int64 v5; // r10
  DWORD AuthorizationContextForClient; // ebx
  _BYTE *v7; // r10
  unsigned int v8; // eax
  __int64 v9; // r10
  unsigned int v10; // eax
  __int64 v11; // r10
  _BYTE *v12; // r10
  unsigned int v13; // eax
  __int64 v14; // r10
  const char *v15; // rax
  __int64 v16; // r10
  __int64 v17; // rdx
  const char *v18; // rax
  __int64 v19; // r10
  PVOID pAuthzClientContext; // [rsp+50h] [rbp-19h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [rsp+58h] [rbp-11h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+78h] [rbp+Fh] BYREF
  int v24; // [rsp+E0h] [rbp+77h] BYREF
  int v25; // [rsp+E8h] [rbp+7Fh] BYREF

  pAuthzClientContext = 0;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v24;
  *(_QWORD *)&pRequest.DesiredAccess = 0x2000000;
  pReply.Error = (PDWORD)&v25;
  memset(&pRequest.PrincipalSelfSid, 0, 32);
  v24 = 0;
  v25 = 0;
  *(_QWORD *)&pReply.ResultListLength = 1;
  pReply.SaclEvaluationResults = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v5 + 16), 55, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, Indent);
  }
  AuthorizationContextForClient = RpcGetAuthorizationContextForClient(
                                    ClientBinding,
                                    0,
                                    0,
                                    0,
                                    0,
                                    0,
                                    0,
                                    &pAuthzClientContext);
  if ( !AuthorizationContextForClient )
  {
    if ( !AuthzAccessCheck(
            1u,
            (AUTHZ_CLIENT_CONTEXT_HANDLE)pAuthzClientContext,
            &pRequest,
            0,
            pSecurityDescriptor,
            0,
            0,
            &pReply,
            0) )
    {
      AuthorizationContextForClient = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = (unsigned int)GetIndent(0);
        WPP_SF_sd(
          *(_QWORD *)(v11 + 16),
          57,
          (unsigned int)WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids,
          v10,
          AuthorizationContextForClient);
      }
      goto LABEL_23;
    }
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v13 = (unsigned int)GetIndent(0);
      WPP_SF_sld(
        *(_QWORD *)(v14 + 16),
        58,
        (unsigned int)WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids,
        v13,
        *pReply.GrantedAccessMask,
        *pReply.Error);
      v12 = WPP_GLOBAL_Control;
    }
    if ( (*pReply.GrantedAccessMask & 0x20000) != 0 )
    {
      AuthorizationContextForClient = 0;
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || v12[25] < 5u )
        goto LABEL_23;
      v15 = GetIndent(0);
      v17 = 59;
    }
    else
    {
      AuthorizationContextForClient = 5;
      if ( v12 == (_BYTE *)&WPP_GLOBAL_Control || v12[25] < 3u )
        goto LABEL_23;
      v15 = GetIndent(0);
      v17 = 60;
    }
    WPP_SF_s(*(_QWORD *)(v16 + 16), v17, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, v15);
LABEL_23:
    RpcFreeAuthorizationContext(&pAuthzClientContext);
    goto LABEL_24;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return AuthorizationContextForClient;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v8 = (unsigned int)GetIndent(0);
    WPP_SF_sd(
      *(_QWORD *)(v9 + 16),
      56,
      (unsigned int)WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids,
      v8,
      AuthorizationContextForClient);
LABEL_24:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (_BYTE *)&WPP_GLOBAL_Control && v7[25] >= 6u )
  {
    v18 = GetIndent(-1);
    WPP_SF_s(*(_QWORD *)(v19 + 16), 61, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids, v18);
  }
  return AuthorizationContextForClient;
}

```

## disassembly

```asm
0x180039228  mov     [rsp-8+arg_0], rbx
0x18003922d  push    rbp
0x18003922e  push    rsi
0x18003922f  push    rdi
0x180039230  push    r12
0x180039232  push    r15
0x180039234  lea     rbp, [rsp-37h]
0x180039239  sub     rsp, 0A0h
0x180039240  lea     rax, [rbp+57h+arg_10]
0x180039244  mov     [rbp+57h+var_70], 0
0x18003924c  mov     [rbp+57h+pReply.GrantedAccessMask], rax
0x180039250  xorps   xmm0, xmm0
0x180039253  lea     rax, [rbp+57h+arg_18]
0x180039257  mov     qword ptr [rbp+57h+pRequest.DesiredAccess], 2000000h
0x18003925f  mov     [rbp+57h+pReply.Error], rax
0x180039263  mov     rdi, rdx
0x180039266  mov     rsi, rcx
0x180039269  mov     qword ptr [rbp+57h+pRequest.ObjectTypeListLength], 0
0x180039271  movdqu  xmmword ptr [rbp+57h+pRequest.PrincipalSelfSid], xmm0
0x180039276  mov     [rbp+57h+pRequest.OptionalArguments], 0
0x18003927e  xor     ebx, ebx
0x180039280  mov     [rbp+57h+arg_10], 0
0x180039287  mov     [rbp+57h+arg_18], 0
0x18003928e  mov     qword ptr [rbp+57h+pReply.ResultListLength], 1
0x180039296  mov     [rbp+57h+pReply.SaclEvaluationResults], 0
0x18003929e  mov     r10, cs:WPP_GLOBAL_Control
0x1800392a5  lea     r15, WPP_GLOBAL_Control
0x1800392ac  lea     r12, WPP_3caf818283943d0c809de850cf5bb0ac_Traceguids
0x1800392b3  cmp     r10, r15
0x1800392b6  jz      short loc_1800392D9
0x1800392b8  cmp     byte ptr [r10+19h], 6
0x1800392bd  jb      short loc_1800392D9
0x1800392bf  lea     ecx, [rbx+1]; int
0x1800392c2  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800392c7  mov     rcx, [r10+10h]
0x1800392cb  lea     edx, [rbx+37h]
0x1800392ce  mov     r9, rax
0x1800392d1  mov     r8, r12
0x1800392d4  call    WPP_SF_s
0x1800392d9  lea     rax, [rbp+57h+var_70]
0x1800392dd  xor     r9d, r9d; pExpirationTime
0x1800392e0  mov     [rsp+0C0h+pAuthzClientContext], rax; pAuthzClientContext
0x1800392e5  xor     r8d, r8d; Reserved1
0x1800392e8  mov     [rsp+0C0h+Reserved4], rbx; Reserved4
0x1800392ed  xor     edx, edx; ImpersonateOnReturn
0x1800392ef  mov     [rsp+0C0h+Reserved3], ebx; Reserved3
0x1800392f3  mov     rcx, rsi; ClientBinding
0x1800392f6  mov     qword ptr [rsp+0C0h+Reserved2.LowPart], rbx; Reserved2
0x1800392fb  call    cs:__imp_RpcGetAuthorizationContextForClient
0x180039301  mov     ebx, eax
0x180039303  test    eax, eax
0x180039305  jz      short loc_180039346
0x180039307  mov     r10, cs:WPP_GLOBAL_Control
0x18003930e  cmp     r10, r15
0x180039311  jz      loc_1800394A4
0x180039317  cmp     byte ptr [r10+19h], 2
0x18003931c  jb      loc_18003947C
0x180039322  xor     ecx, ecx; int
0x180039324  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180039329  mov     rcx, [r10+10h]
0x18003932d  mov     edx, 38h ; '8'
0x180039332  mov     r9, rax
0x180039335  mov     [rsp+0C0h+Reserved2.LowPart], ebx
0x180039339  mov     r8, r12
0x18003933c  call    WPP_SF_sd
0x180039341  jmp     loc_180039475
0x180039346  mov     rdx, [rbp+57h+var_70]; hAuthzClientContext
0x18003934a  lea     rax, [rbp+57h+pReply]
0x18003934e  mov     [rsp+0C0h+phAccessCheckResults], 0; phAccessCheckResults
0x180039357  lea     r8, [rbp+57h+pRequest]; pRequest
0x18003935b  mov     [rsp+0C0h+pAuthzClientContext], rax; pReply
0x180039360  xor     r9d, r9d; hAuditEvent
0x180039363  mov     dword ptr [rsp+0C0h+Reserved4], 0; OptionalSecurityDescriptorCount
0x18003936b  mov     qword ptr [rsp+0C0h+Reserved3], 0; OptionalSecurityDescriptorArray
0x180039374  mov     qword ptr [rsp+0C0h+Reserved2.LowPart], rdi; pSecurityDescriptor
0x180039379  lea     ecx, [r9+1]; Flags
0x18003937d  call    cs:__imp_AuthzAccessCheck
0x180039383  test    eax, eax
0x180039385  jnz     short loc_1800393CE
0x180039387  call    cs:__imp_GetLastError
0x18003938d  mov     ebx, eax
0x18003938f  mov     r10, cs:WPP_GLOBAL_Control
0x180039396  cmp     r10, r15
0x180039399  jz      loc_18003946B
0x18003939f  cmp     byte ptr [r10+19h], 2
0x1800393a4  jb      loc_18003946B
0x1800393aa  xor     ecx, ecx; int
0x1800393ac  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800393b1  mov     rcx, [r10+10h]
0x1800393b5  mov     edx, 39h ; '9'
0x1800393ba  mov     r9, rax
0x1800393bd  mov     [rsp+0C0h+Reserved2.LowPart], ebx
0x1800393c1  mov     r8, r12
0x1800393c4  call    WPP_SF_sd
0x1800393c9  jmp     loc_18003946B
0x1800393ce  mov     r10, cs:WPP_GLOBAL_Control
0x1800393d5  cmp     r10, r15
0x1800393d8  jz      short loc_18003941B
0x1800393da  cmp     byte ptr [r10+19h], 5
0x1800393df  jb      short loc_18003941B
0x1800393e1  xor     ecx, ecx; int
0x1800393e3  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x1800393e8  mov     r8, [rbp+57h+pReply.Error]
0x1800393ec  mov     edx, 3Ah ; ':'
0x1800393f1  mov     rcx, [r10+10h]
0x1800393f5  mov     r9d, [r8]
0x1800393f8  mov     r8, [rbp+57h+pReply.GrantedAccessMask]
0x1800393fc  mov     [rsp+0C0h+Reserved3], r9d
0x180039401  mov     r9d, [r8]
0x180039404  mov     r8, r12
0x180039407  mov     [rsp+0C0h+Reserved2.LowPart], r9d
0x18003940c  mov     r9, rax
0x18003940f  call    WPP_SF_sld
0x180039414  mov     r10, cs:WPP_GLOBAL_Control
0x18003941b  mov     rax, [rbp+57h+pReply.GrantedAccessMask]
0x18003941f  test    dword ptr [rax], 20000h
0x180039425  jz      short loc_180039441
0x180039427  xor     ebx, ebx
0x180039429  cmp     r10, r15
0x18003942c  jz      short loc_18003946B
0x18003942e  cmp     byte ptr [r10+19h], 5
0x180039433  jb      short loc_18003946B
0x180039435  xor     ecx, ecx; int
0x180039437  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18003943c  lea     edx, [rbx+3Bh]
0x18003943f  jmp     short loc_18003945C
0x180039441  mov     ebx, 5
0x180039446  cmp     r10, r15
0x180039449  jz      short loc_18003946B
0x18003944b  cmp     byte ptr [r10+19h], 3
0x180039450  jb      short loc_18003946B
0x180039452  xor     ecx, ecx; int
0x180039454  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180039459  lea     edx, [rbx+37h]
0x18003945c  mov     rcx, [r10+10h]
0x180039460  mov     r9, rax
0x180039463  mov     r8, r12
0x180039466  call    WPP_SF_s
0x18003946b  lea     rcx, [rbp+57h+var_70]; pAuthzClientContext
0x18003946f  call    cs:__imp_RpcFreeAuthorizationContext
0x180039475  mov     r10, cs:WPP_GLOBAL_Control
0x18003947c  cmp     r10, r15
0x18003947f  jz      short loc_1800394A4
0x180039481  cmp     byte ptr [r10+19h], 6
0x180039486  jb      short loc_1800394A4
0x180039488  or      ecx, 0FFFFFFFFh; int
0x18003948b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x180039490  mov     rcx, [r10+10h]
0x180039494  mov     edx, 3Dh ; '='
0x180039499  mov     r9, rax
0x18003949c  mov     r8, r12
0x18003949f  call    WPP_SF_s
0x1800394a4  mov     eax, ebx
0x1800394a6  mov     rbx, [rsp+0C0h+arg_0]
0x1800394ae  add     rsp, 0A0h
0x1800394b5  pop     r15
0x1800394b7  pop     r12
0x1800394b9  pop     rdi
0x1800394ba  pop     rsi
0x1800394bb  pop     rbp
0x1800394bc  retn
```
