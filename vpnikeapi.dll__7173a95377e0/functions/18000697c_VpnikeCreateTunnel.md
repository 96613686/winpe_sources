# VpnikeCreateTunnel

- ea: `0x18000697c`
- end: `0x1800069a9`
- name: `VpnikeCreateTunnel`
- size: `45`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002b70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000699e`
- `RPCRT4!NdrClientCall3` at `0x18000699e`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall VpnikeCreateTunnel(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18000697c  sub     rsp, 48h
0x180006980  mov     [rsp+48h+var_18], r9
0x180006985  mov     r9, rcx
0x180006988  mov     [rsp+48h+var_20], r8
0x18000698d  lea     rcx, pProxyInfo; pProxyInfo
0x180006994  mov     [rsp+48h+var_28], rdx
0x180006999  xor     r8d, r8d; pReturnValue
0x18000699c  xor     edx, edx; nProcNum
0x18000699e  call    cs:__imp_NdrClientCall3
0x1800069a4  add     rsp, 48h
0x1800069a8  retn
```
