# GetClientTokenSessionId

- ea: `0x180014468`
- end: `0x18001449f`
- name: `GetClientTokenSessionId`
- size: `55`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800121f0`

## callees

- `0x1800143e0`
- `0x180014468`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180014470`
- `RPCRT4!RpcImpersonateClient` at `0x180014470`
- `RPCRT4!RpcRevertToSelf` at `0x180014495`
- `RPCRT4!RpcRevertToSelf` at `0x180014495`
- `RPCRT4!RpcRevertToSelf` at `0x18001928e`

## pseudocode

```c
__int64 GetClientTokenSessionId()
{
  RPC_STATUS v0; // eax
  unsigned int ClientLogonId; // ebx

  v0 = RpcImpersonateClient(0);
  if ( v0 == 1725 )
    return 0;
  if ( v0 )
    return 0xFFFFFFFFLL;
  ClientLogonId = GetClientLogonId();
  RpcRevertToSelf();
  return ClientLogonId;
}

```

## disassembly

```asm
0x180014468  push    rbx
0x18001446a  sub     rsp, 20h
0x18001446e  xor     ecx, ecx; BindingHandle
0x180014470  call    cs:__imp_RpcImpersonateClient
0x180014476  cmp     eax, 6BDh
0x18001447b  jnz     short loc_180014485
0x18001447d  xor     eax, eax
0x18001447f  add     rsp, 20h
0x180014483  pop     rbx
0x180014484  retn
0x180014485  test    eax, eax
0x180014487  jz      short loc_18001448E
0x180014489  or      eax, 0FFFFFFFFh
0x18001448c  jmp     short loc_18001447F
0x18001448e  call    GetClientLogonId
0x180014493  mov     ebx, eax
0x180014495  call    cs:__imp_RpcRevertToSelf
0x18001449b  mov     eax, ebx
0x18001449d  jmp     short loc_18001447F
0x180019280  push    rbp
0x180019282  sub     rsp, 20h
0x180019286  mov     rbp, rdx
0x180019289  add     rsp, 20h
0x18001928d  pop     rbp
0x18001928e  jmp     cs:__imp_RpcRevertToSelf
```
