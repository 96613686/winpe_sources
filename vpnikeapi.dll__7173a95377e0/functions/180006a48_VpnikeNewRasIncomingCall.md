# VpnikeNewRasIncomingCall

- ea: `0x180006a48`
- end: `0x180006a72`
- name: `VpnikeNewRasIncomingCall`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800044a0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006a67`
- `RPCRT4!NdrClientCall3` at `0x180006a67`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall VpnikeNewRasIncomingCall(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180006a48  sub     rsp, 38h
0x180006a4c  mov     [rsp+38h+var_10], r8
0x180006a51  mov     r9, rcx
0x180006a54  xor     r8d, r8d; pReturnValue
0x180006a57  mov     [rsp+38h+var_18], rdx
0x180006a5c  lea     rcx, pProxyInfo; pProxyInfo
0x180006a63  lea     edx, [r8+6]; nProcNum
0x180006a67  call    cs:__imp_NdrClientCall3
0x180006a6d  add     rsp, 38h
0x180006a71  retn
```
