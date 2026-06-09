# RpcSecurityCallback(void * *,void *)

- ea: `0x180021910`
- end: `0x1800219b5`
- name: `?RpcSecurityCallback@@YAJPEAPEAXPEAX@Z`
- size: `165`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18001fb14`
- `0x180021320`
- `0x180021910`

## import_xrefs

- `RPCRT4!RpcBindingInqAuthClientA` at `0x180021963`
- `RPCRT4!RpcBindingInqAuthClientA` at `0x180021963`
- `RPCRT4!RpcRevertToSelf` at `0x180021991`
- `RPCRT4!RpcRevertToSelf` at `0x1800219ad`
- `RPCRT4!RpcRevertToSelf` at `0x180021991`
- `RPCRT4!RpcRevertToSelf` at `0x1800219ad`
- `RPCRT4!RpcImpersonateClient` at `0x18002197c`
- `RPCRT4!RpcImpersonateClient` at `0x18002197c`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180021933`
- `RPCRT4!I_RpcBindingInqTransportType` at `0x180021933`

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
0x180021910  mov     rax, rsp
0x180021913  push    rbx
0x180021914  sub     rsp, 40h
0x180021918  lea     rdx, [rax+18h]; Type
0x18002191c  mov     dword ptr [rax+18h], 0
0x180021923  xor     ecx, ecx; Binding
0x180021925  mov     dword ptr [rax+20h], 0
0x18002192c  mov     dword ptr [rax-18h], 0
0x180021933  call    cs:__imp_I_RpcBindingInqTransportType
0x180021939  test    eax, eax
0x18002193b  jnz     short loc_180021997
0x18002193d  cmp     [rsp+48h+arg_10], 4
0x180021942  jnz     short loc_180021997
0x180021944  lea     rax, [rsp+48h+var_18]
0x180021949  mov     [rsp+48h+AuthzSvc], 0; AuthzSvc
0x180021952  lea     r9, [rsp+48h+AuthnLevel]; AuthnLevel
0x180021957  mov     [rsp+48h+AuthnSvc], rax; AuthnSvc
0x18002195c  xor     r8d, r8d; ServerPrincName
0x18002195f  xor     edx, edx; Privs
0x180021961  xor     ecx, ecx; ClientBinding
0x180021963  call    cs:__imp_RpcBindingInqAuthClientA
0x180021969  test    eax, eax
0x18002196b  jnz     short loc_180021997
0x18002196d  cmp     [rsp+48h+AuthnLevel], 6
0x180021972  jnz     short loc_180021997
0x180021974  cmp     [rsp+48h+var_18], eax
0x180021978  jz      short loc_180021997
0x18002197a  xor     ecx, ecx; BindingHandle
0x18002197c  call    cs:__imp_RpcImpersonateClient
0x180021982  mov     ebx, eax
0x180021984  test    eax, eax
0x180021986  jnz     short loc_180021997
0x180021988  call    ?IsAuthenticatedUser@@YAHXZ; IsAuthenticatedUser(void)
0x18002198d  test    eax, eax
0x18002198f  jnz     short loc_1800219A4
0x180021991  call    cs:__imp_RpcRevertToSelf
0x180021997  mov     ebx, 5
0x18002199c  mov     eax, ebx
0x18002199e  add     rsp, 40h
0x1800219a2  pop     rbx
0x1800219a3  retn
0x1800219a4  call    ?IsAnonymousUser@@YAHXZ; IsAnonymousUser(void)
0x1800219a9  test    eax, eax
0x1800219ab  jnz     short loc_180021991
0x1800219ad  call    cs:__imp_RpcRevertToSelf
0x1800219b3  jmp     short loc_18002199C
```
