# CVerifyAuthentication::VerifyAuthentication(void *)

- ea: `0x180004750`
- end: `0x1800047a0`
- name: `?VerifyAuthentication@CVerifyAuthentication@@SAXPEAX@Z`
- size: `80`
- prototype: `void __fastcall(void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003d00`
- `0x1800053b0`
- `0x18000f150`
- `0x18000f1b0`

## callees

- `0x180004750`
- `0x18000d038`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18000477b`
- `RPCRT4!RpcRevertToSelf` at `0x180004798`
- `RPCRT4!RpcRevertToSelf` at `0x18000477b`
- `RPCRT4!RpcRevertToSelf` at `0x180004798`
- `RPCRT4!RpcImpersonateClient` at `0x180004754`
- `RPCRT4!RpcImpersonateClient` at `0x180004754`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004775`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180004775`

## pseudocode

```c
void __fastcall CVerifyAuthentication::VerifyAuthentication(void *a1)
{
  WINBOOL IsMember; // [rsp+38h] [rbp+10h] BYREF

  if ( RpcImpersonateClient(a1) )
LABEL_4:
    TrkRaiseWin32Error(1244);
  IsMember = 0;
  if ( !CVerifyAuthentication::_psidAuthenticatedUsersGroup )
  {
    RpcRevertToSelf();
    goto LABEL_4;
  }
  CheckTokenMembership(0, CVerifyAuthentication::_psidAuthenticatedUsersGroup, &IsMember);
  RpcRevertToSelf();
  if ( !IsMember )
    goto LABEL_4;
}

```

## disassembly

```asm
0x180004750  sub     rsp, 28h
0x180004754  call    cs:__imp_RpcImpersonateClient
0x18000475a  test    eax, eax
0x18000475c  jnz     short loc_18000478D
0x18000475e  mov     rdx, cs:?_psidAuthenticatedUsersGroup@CVerifyAuthentication@@0PEAXEA; SidToCheck
0x180004765  mov     [rsp+28h+IsMember], eax
0x180004769  test    rdx, rdx
0x18000476c  jz      short loc_180004798
0x18000476e  lea     r8, [rsp+28h+IsMember]; IsMember
0x180004773  xor     ecx, ecx; TokenHandle
0x180004775  call    cs:__imp_CheckTokenMembership
0x18000477b  call    cs:__imp_RpcRevertToSelf
0x180004781  cmp     [rsp+28h+IsMember], 0
0x180004786  jz      short loc_18000478D
0x180004788  add     rsp, 28h
0x18000478c  retn
0x18000478d  mov     ecx, 4DCh; int
0x180004792  call    ?TrkRaiseWin32Error@@YAXJ@Z; TrkRaiseWin32Error(long)
0x180004798  call    cs:__imp_RpcRevertToSelf
0x18000479e  jmp     short loc_18000478D
```
