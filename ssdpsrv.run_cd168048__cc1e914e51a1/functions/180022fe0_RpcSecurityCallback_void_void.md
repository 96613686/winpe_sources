# RpcSecurityCallback(void * *,void *)

- ea: `0x180022fe0`
- end: `0x1800230a4`
- name: `?RpcSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `196`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800211e8`
- `0x180022b00`
- `0x180022fe0`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientA` at `0x180023039`
- `RPCRT4!RpcBindingInqAuthClientA` at `0x180023039`
- `RPCRT4!RpcRevertToSelf` at `0x180023073`
- `RPCRT4!RpcRevertToSelf` at `0x180023096`
- `RPCRT4!RpcRevertToSelf` at `0x180023073`
- `RPCRT4!RpcRevertToSelf` at `0x180023096`
- `RPCRT4!RpcImpersonateClient` at `0x180023058`
- `RPCRT4!RpcImpersonateClient` at `0x180023058`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180023003`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180023003`

## pseudocode

```c
__int64 __fastcall RpcSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  unsigned int v2; // ebx
  unsigned int AuthnSvc[6]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v5; // [rsp+60h] [rbp+18h] BYREF
  unsigned int AuthnLevel; // [rsp+68h] [rbp+20h] BYREF

  v5 = 0;
  AuthnLevel = 0;
  AuthnSvc[0] = 0;
  if ( !I_RpcBindingInqTransportType(0, &v5)
    && v5 == 4
    && !RpcBindingInqAuthClientA(0, 0, 0, &AuthnLevel, AuthnSvc, 0)
    && AuthnLevel == 6 )
  {
    if ( AuthnSvc[0] )
    {
      v2 = RpcImpersonateClient(0);
      if ( !v2 )
      {
        if ( (unsigned int)IsAuthenticatedUser() && !(unsigned int)IsAnonymousUser() )
        {
          RpcRevertToSelf();
          return v2;
        }
        RpcRevertToSelf();
      }
    }
  }
  return 5;
}

```

## disassembly

```asm
0x180022fe0  mov     rax, rsp
0x180022fe3  push    rbx
0x180022fe4  sub     rsp, 40h
0x180022fe8  lea     rdx, [rax+18h]; Type
0x180022fec  mov     dword ptr [rax+18h], 0
0x180022ff3  xor     ecx, ecx; Binding
0x180022ff5  mov     dword ptr [rax+20h], 0
0x180022ffc  mov     dword ptr [rax-18h], 0
0x180023003  call    cs:__imp_I_RpcBindingInqTransportType
0x18002300a  nop     dword ptr [rax+rax+00h]
0x18002300f  test    eax, eax
0x180023011  jnz     short loc_18002307F
0x180023013  cmp     [rsp+48h+arg_10], 4
0x180023018  jnz     short loc_18002307F
0x18002301a  lea     rax, [rsp+48h+var_18]
0x18002301f  mov     [rsp+48h+AuthzSvc], 0; AuthzSvc
0x180023028  lea     r9, [rsp+48h+AuthnLevel]; AuthnLevel
0x18002302d  mov     [rsp+48h+AuthnSvc], rax; AuthnSvc
0x180023032  xor     r8d, r8d; ServerPrincName
0x180023035  xor     edx, edx; Privs
0x180023037  xor     ecx, ecx; ClientBinding
0x180023039  call    cs:__imp_RpcBindingInqAuthClientA
0x180023040  nop     dword ptr [rax+rax+00h]
0x180023045  test    eax, eax
0x180023047  jnz     short loc_18002307F
0x180023049  cmp     [rsp+48h+AuthnLevel], 6
0x18002304e  jnz     short loc_18002307F
0x180023050  cmp     [rsp+48h+var_18], eax
0x180023054  jz      short loc_18002307F
0x180023056  xor     ecx, ecx; BindingHandle
0x180023058  call    cs:__imp_RpcImpersonateClient
0x18002305f  nop     dword ptr [rax+rax+00h]
0x180023064  mov     ebx, eax
0x180023066  test    eax, eax
0x180023068  jnz     short loc_18002307F
0x18002306a  call    ?IsAuthenticatedUser@@YAHXZ; IsAuthenticatedUser(void)
0x18002306f  test    eax, eax
0x180023071  jnz     short loc_18002308D
0x180023073  call    cs:__imp_RpcRevertToSelf
0x18002307a  nop     dword ptr [rax+rax+00h]
0x18002307f  mov     ebx, 5
0x180023084  mov     eax, ebx
0x180023086  add     rsp, 40h
0x18002308a  pop     rbx
0x18002308b  retn
0x18002308d  call    ?IsAnonymousUser@@YAHXZ; IsAnonymousUser(void)
0x180023092  test    eax, eax
0x180023094  jnz     short loc_180023073
0x180023096  call    cs:__imp_RpcRevertToSelf
0x18002309d  nop     dword ptr [rax+rax+00h]
0x1800230a2  jmp     short loc_180023084
```
