# UtcUpdateTimerConfiguration

- ea: `0x180002d80`
- end: `0x180002e0f`
- name: `UtcUpdateTimerConfiguration`
- size: `143`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180002560`
- `0x180002d80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002de6`
- `RPCRT4!NdrClientCall3` at `0x180002de6`
- `RPCRT4!RpcExceptionFilter` at `0x1800030b6`
- `RPCRT4!RpcExceptionFilter` at `0x1800030b6`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall UtcUpdateTimerConfiguration(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-58h]
  _OWORD v6[2]; // [rsp+40h] [rbp-38h] BYREF
  int v7; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( a1 )
  {
    v6[0] = *(_OWORD *)a3;
    v6[1] = *(_OWORD *)(a3 + 16);
    v7 = *(_DWORD *)(a3 + 32);
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180005790, 0xEu, 0, a1, a2, v6);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x61, a3, a4, v5);
    return (CLIENT_CALL_RETURN)2147942487LL;
  }
}

```

## disassembly

```asm
0x180002d80  sub     rsp, 78h
0x180002d84  test    rcx, rcx
0x180002d87  jnz     short loc_180002D9F
0x180002d89  mov     rcx, [rsp+78h]; this
0x180002d8e  mov     edx, 61h ; 'a'; void *
0x180002d93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d98  mov     eax, 80070057h
0x180002d9d  jmp     short loc_180002E0A
0x180002d9f  mov     [rsp+78h+arg_18], 0
0x180002dab  movups  xmm0, xmmword ptr [r8]
0x180002daf  movaps  [rsp+78h+var_38], xmm0
0x180002db4  movups  xmm1, xmmword ptr [r8+10h]
0x180002db9  movaps  [rsp+78h+var_28], xmm1
0x180002dbe  mov     eax, [r8+20h]
0x180002dc2  mov     [rsp+78h+var_18], eax
0x180002dc6  lea     rax, [rsp+78h+var_38]
0x180002dcb  mov     [rsp+78h+var_50], rax
0x180002dd0  mov     [rsp+78h+var_58], rdx
0x180002dd5  mov     r9, rcx
0x180002dd8  xor     r8d, r8d; pReturnValue
0x180002ddb  lea     edx, [r8+0Eh]; nProcNum
0x180002ddf  lea     rcx, stru_180005790; pProxyInfo
0x180002de6  call    cs:__imp_NdrClientCall3
0x180002dec  mov     [rsp+78h+arg_18], rax
0x180002df4  mov     [rsp+78h+var_48], eax
0x180002df8  jmp     short loc_180002E0A
0x180002dfa  test    eax, eax
0x180002dfc  jle     short loc_180002E06
0x180002dfe  movzx   eax, ax
0x180002e01  or      eax, 80070000h
0x180002e06  mov     [rsp+78h+var_48], eax
0x180002e0a  add     rsp, 78h
0x180002e0e  retn
0x1800030a8  push    rbp
0x1800030aa  sub     rsp, 30h
0x1800030ae  mov     rbp, rdx
0x1800030b1  mov     rcx, [rcx]
0x1800030b4  mov     ecx, [rcx]; ExceptionCode
0x1800030b6  call    cs:__imp_RpcExceptionFilter
0x1800030bc  nop
0x1800030bd  add     rsp, 30h
0x1800030c1  pop     rbp
0x1800030c2  retn
```
