# SspirProcessSecurityContext2

- ea: `0x180018e90`
- end: `0x180018fa1`
- name: `SspirProcessSecurityContext2`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180002780`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180018f93`
- `RPCRT4!NdrClientCall3` at `0x180018f93`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall SspirProcessSecurityContext2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        __int64 a13,
        __int64 a14,
        __int64 a15,
        __int64 a16,
        __int64 a17,
        __int64 a18,
        __int64 a19,
        __int64 a20,
        __int64 a21,
        __int64 a22)
{
  return NdrClientCall3(
           (MIDL_STUBLESS_PROXY_INFO *)&sspirpc_ProxyInfo,
           0x15u,
           0,
           a1,
           a2,
           a3,
           a4,
           a5,
           a6,
           a7,
           a8,
           a9,
           a10,
           a11,
           a12,
           a13,
           a14,
           a15,
           a16,
           a17,
           a18,
           a19,
           a20,
           a21,
           a22);
}

```

## disassembly

```asm
0x180018e90  mov     r11, rsp
0x180018e93  sub     rsp, 0D8h
0x180018e9a  mov     rax, [rsp+0D8h+arg_A8]
0x180018ea2  mov     [r11-18h], rax
0x180018ea6  mov     rax, [rsp+0D8h+arg_A0]
0x180018eae  mov     [r11-20h], rax
0x180018eb2  mov     rax, [rsp+0D8h+arg_98]
0x180018eba  mov     [r11-28h], rax
0x180018ebe  mov     rax, [rsp+0D8h+arg_90]
0x180018ec6  mov     [r11-30h], rax
0x180018eca  mov     rax, [rsp+0D8h+arg_88]
0x180018ed2  mov     [r11-38h], rax
0x180018ed6  mov     rax, [rsp+0D8h+arg_80]
0x180018ede  mov     [r11-40h], rax
0x180018ee2  mov     rax, [rsp+0D8h+arg_78]
0x180018eea  mov     [r11-48h], rax
0x180018eee  mov     rax, [rsp+0D8h+arg_70]
0x180018ef6  mov     [r11-50h], rax
0x180018efa  mov     rax, [rsp+0D8h+arg_68]
0x180018f02  mov     [r11-58h], rax
0x180018f06  mov     rax, [rsp+0D8h+arg_60]
0x180018f0e  mov     [r11-60h], rax
0x180018f12  mov     rax, [rsp+0D8h+arg_58]
0x180018f1a  mov     [r11-68h], rax
0x180018f1e  mov     rax, [rsp+0D8h+arg_50]
0x180018f26  mov     [r11-70h], rax
0x180018f2a  mov     rax, [rsp+0D8h+arg_48]
0x180018f32  mov     [r11-78h], rax
0x180018f36  mov     eax, [rsp+0D8h+arg_40]
0x180018f3d  mov     [rsp+0D8h+var_80], eax
0x180018f41  mov     eax, [rsp+0D8h+arg_38]
0x180018f48  mov     [rsp+0D8h+var_88], eax
0x180018f4c  mov     rax, [rsp+0D8h+arg_30]
0x180018f54  mov     [rsp+0D8h+var_90], rax
0x180018f59  mov     rax, [rsp+0D8h+arg_28]
0x180018f61  mov     [rsp+0D8h+var_98], rax
0x180018f66  mov     rax, [rsp+0D8h+arg_20]
0x180018f6e  mov     [rsp+0D8h+var_A0], rax
0x180018f73  mov     [rsp+0D8h+var_A8], r9
0x180018f78  mov     r9, rcx
0x180018f7b  mov     [rsp+0D8h+var_B0], r8
0x180018f80  lea     rcx, ?sspirpc_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180018f87  xor     r8d, r8d; pReturnValue
0x180018f8a  mov     [rsp+0D8h+var_B8], rdx
0x180018f8f  lea     edx, [r8+15h]; nProcNum
0x180018f93  call    cs:__imp_NdrClientCall3
0x180018f99  add     rsp, 0D8h
0x180018fa0  retn
```
