# VpnikeUpdateTunnel

- ea: `0x180006c28`
- end: `0x180006c52`
- name: `VpnikeUpdateTunnel`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x1800060c0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006c47`
- `RPCRT4!NdrClientCall3` at `0x180006c47`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall VpnikeUpdateTunnel(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180006c28  sub     rsp, 38h
0x180006c2c  mov     [rsp+38h+var_10], r8
0x180006c31  mov     r9, rcx
0x180006c34  xor     r8d, r8d; pReturnValue
0x180006c37  mov     [rsp+38h+var_18], rdx
0x180006c3c  lea     rcx, pProxyInfo; pProxyInfo
0x180006c43  lea     edx, [r8+1]; nProcNum
0x180006c47  call    cs:__imp_NdrClientCall3
0x180006c4d  add     rsp, 38h
0x180006c51  retn
```
