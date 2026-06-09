# SstpSvcRpcRemoteAccessCheck(void * *,void *)

- ea: `0x18001bd00`
- end: `0x18001bd34`
- name: `?SstpSvcRpcRemoteAccessCheck@@YAJPEAPEAXPEAX@Z`
- size: `52`
- prototype: `RPC_IF_CALLBACK_FN`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001bd00`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001bd13`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001bd13`

## pseudocode

```c
RPC_STATUS __fastcall SstpSvcRpcRemoteAccessCheck(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  RPC_STATUS result; // eax
  unsigned int ClientLocalFlag; // [rsp+40h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  result = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( result || !ClientLocalFlag )
    return 5;
  return result;
}

```

## disassembly

```asm
0x18001bd00  sub     rsp, 28h
0x18001bd04  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x18001bd09  mov     [rsp+28h+ClientLocalFlag], 0
0x18001bd11  xor     ecx, ecx; BindingHandle
0x18001bd13  call    cs:__imp_I_RpcBindingIsClientLocal
0x18001bd1a  nop     dword ptr [rax+rax+00h]
0x18001bd1f  test    eax, eax
0x18001bd21  jnz     short loc_18001BD29
0x18001bd23  cmp     [rsp+28h+ClientLocalFlag], eax
0x18001bd27  jnz     short loc_18001BD2E
0x18001bd29  mov     eax, 5
0x18001bd2e  add     rsp, 28h
0x18001bd32  retn
```
