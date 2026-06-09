# LsarOpenPolicy3

- ea: `0x180014808`
- end: `0x18001486d`
- name: `LsarOpenPolicy3`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180016f78`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180014862`
- `RPCRT4!NdrClientCall3` at `0x180014862`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall LsarOpenPolicy3(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v9; // [rsp+28h] [rbp-40h]
  int v10; // [rsp+30h] [rbp-38h]

  v10 = 1;
  v9 = 1;
  return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x82u, 0, a1, a2, v9, v10, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x180014808  mov     r11, rsp
0x18001480b  sub     rsp, 68h
0x18001480f  mov     rax, [rsp+68h+arg_38]
0x180014817  mov     r9, rcx
0x18001481a  mov     [r11-18h], rax
0x18001481e  lea     rcx, pProxyInfo; pProxyInfo
0x180014825  mov     rax, [rsp+68h+arg_30]
0x18001482d  xor     r8d, r8d; pReturnValue
0x180014830  mov     [r11-20h], rax
0x180014834  mov     rax, [rsp+68h+arg_28]
0x18001483c  mov     [r11-28h], rax
0x180014840  mov     rax, [rsp+68h+arg_20]
0x180014848  mov     [r11-30h], rax
0x18001484c  mov     eax, 1
0x180014851  mov     [rsp+68h+var_38], eax
0x180014855  mov     [rsp+68h+var_40], eax
0x180014859  mov     [r11-48h], rdx
0x18001485d  mov     edx, 82h; nProcNum
0x180014862  call    cs:__imp_NdrClientCall3
0x180014868  add     rsp, 68h
0x18001486c  retn
```
