# UtcGetTimerConfiguration

- ea: `0x180002b20`
- end: `0x180002b8e`
- name: `UtcGetTimerConfiguration`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002560`
- `0x180002b20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002b68`
- `RPCRT4!NdrClientCall3` at `0x180002b68`
- `RPCRT4!RpcExceptionFilter` at `0x180003094`
- `RPCRT4!RpcExceptionFilter` at `0x180003094`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall UtcGetTimerConfiguration(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( a1 )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180005790, 0x11u, 0, a1, a2, a3, a4);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6B, a3, a4, v5);
  return (CLIENT_CALL_RETURN)2147942487LL;
}

```

## disassembly

```asm
0x180002b20  sub     rsp, 58h
0x180002b24  test    rcx, rcx
0x180002b27  jnz     short loc_180002B3F
0x180002b29  mov     rcx, [rsp+58h]; this
0x180002b2e  mov     edx, 6Bh ; 'k'; void *
0x180002b33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002b38  mov     eax, 80070057h
0x180002b3d  jmp     short loc_180002B89
0x180002b3f  mov     [rsp+58h+var_10], 0
0x180002b48  mov     [rsp+58h+var_28], r9
0x180002b4d  mov     [rsp+58h+var_30], r8
0x180002b52  mov     [rsp+58h+var_38], rdx
0x180002b57  mov     r9, rcx
0x180002b5a  xor     r8d, r8d; pReturnValue
0x180002b5d  lea     edx, [r8+11h]; nProcNum
0x180002b61  lea     rcx, stru_180005790; pProxyInfo
0x180002b68  call    cs:__imp_NdrClientCall3
0x180002b6e  mov     [rsp+58h+var_10], rax
0x180002b73  mov     [rsp+58h+var_18], eax
0x180002b77  jmp     short loc_180002B89
0x180002b79  test    eax, eax
0x180002b7b  jle     short loc_180002B85
0x180002b7d  movzx   eax, ax
0x180002b80  or      eax, 80070000h
0x180002b85  mov     [rsp+58h+var_18], eax
0x180002b89  add     rsp, 58h
0x180002b8d  retn
0x180003086  push    rbp
0x180003088  sub     rsp, 40h
0x18000308c  mov     rbp, rdx
0x18000308f  mov     rcx, [rcx]
0x180003092  mov     ecx, [rcx]; ExceptionCode
0x180003094  call    cs:__imp_RpcExceptionFilter
0x18000309a  nop
0x18000309b  add     rsp, 40h
0x18000309f  pop     rbp
0x1800030a0  retn
```
