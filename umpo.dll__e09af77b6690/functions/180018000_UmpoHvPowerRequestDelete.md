# UmpoHvPowerRequestDelete

- ea: `0x180018000`
- end: `0x180018049`
- name: `UmpoHvPowerRequestDelete`
- size: `73`
- prototype: `CLIENT_CALL_RETURN()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b39c`

## callees

- `0x180018000`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001802f`
- `RPCRT4!NdrClientCall3` at `0x18001802f`

## pseudocode

```c
CLIENT_CALL_RETURN UmpoHvPowerRequestDelete()
{
  CLIENT_CALL_RETURN result; // rax

  result.Simple = 50;
  if ( UmpoHvRpcPowerRequestClientHandle )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0);
  return result;
}

```

## disassembly

```asm
0x180018000  sub     rsp, 48h
0x180018004  mov     eax, 32h ; '2'
0x180018009  mov     r9, cs:UmpoHvRpcPowerRequestClientHandle
0x180018010  test    r9, r9
0x180018013  jz      short loc_180018044
0x180018015  mov     [rsp+48h+arg_8], 0
0x18001801e  mov     [rsp+48h+var_28], ecx
0x180018022  xor     r8d, r8d; pReturnValue
0x180018025  lea     edx, [rax-30h]; nProcNum
0x180018028  lea     rcx, pProxyInfo; pProxyInfo
0x18001802f  call    cs:__imp_NdrClientCall3
0x180018035  mov     [rsp+48h+arg_8], rax
0x18001803a  mov     [rsp+48h+var_18], eax
0x18001803e  jmp     short loc_180018044
0x180018040  mov     [rsp+48h+var_18], eax
0x180018044  add     rsp, 48h
0x180018048  retn
```
