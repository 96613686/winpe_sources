# RpcpUnbindRpc

- ea: `0x180001050`
- end: `0x180001070`
- name: `RpcpUnbindRpc`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b3b4`
- `0x180013060`
- `0x180013490`
- `0x1800142a0`

## callees

- `0x180001050`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180001063`
- `RPCRT4!RpcBindingFree` at `0x180001063`

## pseudocode

```c
__int64 __fastcall RpcpUnbindRpc(void *a1)
{
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  Binding = a1;
  if ( a1 )
    RpcBindingFree(&Binding);
  return 0;
}

```

## disassembly

```asm
0x180001050  mov     [rsp+Binding], rcx
0x180001055  sub     rsp, 28h
0x180001059  test    rcx, rcx
0x18000105c  jz      short loc_180001069
0x18000105e  lea     rcx, [rsp+28h+Binding]; Binding
0x180001063  call    cs:__imp_RpcBindingFree
0x180001069  xor     eax, eax
0x18000106b  add     rsp, 28h
0x18000106f  retn
```
