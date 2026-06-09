# VpnikeRemoveTs

- ea: `0x180006bc8`
- end: `0x180006bf2`
- name: `VpnikeRemoveTs`
- size: `42`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b30`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180006be7`
- `RPCRT4!NdrClientCall3` at `0x180006be7`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall VpnikeRemoveTs(__int64 a1, __int64 a2, __int64 a3)
{
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xAu, 0, a1, a2, a3);
}

```

## disassembly

```asm
0x180006bc8  sub     rsp, 38h
0x180006bcc  mov     [rsp+38h+var_10], r8
0x180006bd1  mov     r9, rcx
0x180006bd4  xor     r8d, r8d; pReturnValue
0x180006bd7  mov     [rsp+38h+var_18], rdx
0x180006bdc  lea     rcx, pProxyInfo; pProxyInfo
0x180006be3  lea     edx, [r8+0Ah]; nProcNum
0x180006be7  call    cs:__imp_NdrClientCall3
0x180006bed  add     rsp, 38h
0x180006bf1  retn
```
