# VpnikeCreateOptionalIDrPayload

- ea: `0x18000694c`
- end: `0x180006976`
- name: `VpnikeCreateOptionalIDrPayload`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000696b`
- `RPCRT4!NdrClientCall3` at `0x18000696b`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall VpnikeCreateOptionalIDrPayload(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x11u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x18000694c  sub     rsp, 38h
0x180006950  mov     [rsp+38h+var_10], r8
0x180006955  mov     r9, rcx
0x180006958  xor     r8d, r8d; pReturnValue
0x18000695b  mov     [rsp+38h+var_18], rdx
0x180006960  lea     rcx, pProxyInfo; pProxyInfo
0x180006967  lea     edx, [r8+11h]; nProcNum
0x18000696b  call    cs:__imp_NdrClientCall3
0x180006971  add     rsp, 38h
0x180006975  retn
```
