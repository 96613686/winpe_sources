# SeclSecurityCallback

- ea: `0x1800035c0`
- end: `0x1800035ee`
- name: `SeclSecurityCallback`
- size: `46`
- prototype: `RPC_STATUS __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800035c0`

## import_xrefs

- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800035d3`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800035d3`

## pseudocode

```c
RPC_STATUS __fastcall SeclSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context)
{
  RPC_STATUS result; // eax
  unsigned int ClientLocalFlag; // [rsp+40h] [rbp+18h] BYREF

  ClientLocalFlag = 0;
  result = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( !result && !ClientLocalFlag )
    return 5;
  return result;
}

```

## disassembly

```asm
0x1800035c0  sub     rsp, 28h
0x1800035c4  lea     rdx, [rsp+28h+ClientLocalFlag]; ClientLocalFlag
0x1800035c9  mov     [rsp+28h+ClientLocalFlag], 0
0x1800035d1  xor     ecx, ecx; BindingHandle
0x1800035d3  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800035d9  test    eax, eax
0x1800035db  jnz     short loc_1800035E9
0x1800035dd  cmp     [rsp+28h+ClientLocalFlag], eax
0x1800035e1  mov     ecx, 5
0x1800035e6  cmovz   eax, ecx
0x1800035e9  add     rsp, 28h
0x1800035ed  retn
```
