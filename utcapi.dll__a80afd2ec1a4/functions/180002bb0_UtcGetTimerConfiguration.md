# UtcGetTimerConfiguration

- ea: `0x180002bb0`
- end: `0x180002c25`
- name: `UtcGetTimerConfiguration`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002590`
- `0x180002bb0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002bf8`
- `RPCRT4!NdrClientCall3` at `0x180002bf8`
- `RPCRT4!RpcExceptionFilter` at `0x180003154`
- `RPCRT4!RpcExceptionFilter` at `0x180003154`

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
0x180002bb0  sub     rsp, 58h
0x180002bb4  test    rcx, rcx
0x180002bb7  jnz     short loc_180002BCF
0x180002bb9  mov     rcx, [rsp+58h]; this
0x180002bbe  mov     edx, 6Bh ; 'k'; void *
0x180002bc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002bc8  mov     eax, 80070057h
0x180002bcd  jmp     short loc_180002C1F
0x180002bcf  mov     [rsp+58h+var_10], 0
0x180002bd8  mov     [rsp+58h+var_28], r9
0x180002bdd  mov     [rsp+58h+var_30], r8
0x180002be2  mov     [rsp+58h+var_38], rdx
0x180002be7  mov     r9, rcx
0x180002bea  xor     r8d, r8d; pReturnValue
0x180002bed  lea     edx, [r8+11h]; nProcNum
0x180002bf1  lea     rcx, stru_180005790; pProxyInfo
0x180002bf8  call    cs:__imp_NdrClientCall3
0x180002bff  nop     dword ptr [rax+rax+00h]
0x180002c04  mov     [rsp+58h+var_10], rax
0x180002c09  mov     [rsp+58h+var_18], eax
0x180002c0d  jmp     short loc_180002C1F
0x180002c0f  test    eax, eax
0x180002c11  jle     short loc_180002C1B
0x180002c13  movzx   eax, ax
0x180002c16  or      eax, 80070000h
0x180002c1b  mov     [rsp+58h+var_18], eax
0x180002c1f  add     rsp, 58h
0x180002c23  retn
0x180003146  push    rbp
0x180003148  sub     rsp, 40h
0x18000314c  mov     rbp, rdx
0x18000314f  mov     rcx, [rcx]
0x180003152  mov     ecx, [rcx]; ExceptionCode
0x180003154  call    cs:__imp_RpcExceptionFilter
0x18000315b  nop     dword ptr [rax+rax+00h]
0x180003160  nop
0x180003161  add     rsp, 40h
0x180003165  pop     rbp
0x180003166  retn
```
