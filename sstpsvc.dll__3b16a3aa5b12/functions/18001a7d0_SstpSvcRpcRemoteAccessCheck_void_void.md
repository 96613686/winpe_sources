# SstpSvcRpcRemoteAccessCheck(void * *,void *)

- ea: `0x18001a7d0`
- end: `0x18001a7fd`
- name: `?SstpSvcRpcRemoteAccessCheck@@YAJPEAPEAXPEAX@Z`
- size: `45`
- prototype: `RPC_STATUS __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18001a7d0`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001a7e3`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x18001a7e3`

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
0x18001a7d0  sub     rsp, 28h
0x18001a7d4  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x18001a7d9  mov     [rsp+28h+ClientLocalFlag], 0
0x18001a7e1  xor     ecx, ecx; BindingHandle
0x18001a7e3  call    cs:__imp_I_RpcBindingIsClientLocal
0x18001a7e9  test    eax, eax
0x18001a7eb  jnz     short loc_18001A7F3
0x18001a7ed  cmp     [rsp+28h+ClientLocalFlag], eax
0x18001a7f1  jnz     short loc_18001A7F8
0x18001a7f3  mov     eax, 5
0x18001a7f8  add     rsp, 28h
0x18001a7fc  retn
```
