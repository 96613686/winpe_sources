# VpnikeCreateIDPayload

- ea: `0x18000691c`
- end: `0x180006946`
- name: `VpnikeCreateIDPayload`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800038d0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000693b`
- `RPCRT4!NdrClientCall3` at `0x18000693b`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall VpnikeCreateIDPayload(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xFu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000691c  sub     rsp, 38h
0x180006920  mov     [rsp+38h+var_10], r8
0x180006925  mov     r9, rcx
0x180006928  xor     r8d, r8d; pReturnValue
0x18000692b  mov     [rsp+38h+var_18], rdx
0x180006930  lea     rcx, pProxyInfo; pProxyInfo
0x180006937  lea     edx, [r8+0Fh]; nProcNum
0x18000693b  call    cs:__imp_NdrClientCall3
0x180006941  add     rsp, 38h
0x180006945  retn
```
