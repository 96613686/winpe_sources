# _RPCReleaseClientContext(void *,void * *)

- ea: `0x180005934`
- end: `0x18000598a`
- name: `?_RPCReleaseClientContext@@YAXPEAXPEAPEAX@Z`
- size: `86`
- prototype: `void __fastcall(void *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004f48`
- `0x1800065a8`

## callees

- `0x180005934`
- `0x18000da4c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180005957`
- `RPCRT4!NdrClientCall3` at `0x180005957`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001c91c`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001c91c`

## string_xrefs

- `0x180005972`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
void __fastcall _RPCReleaseClientContext(void *a1, void **a2)
{
  NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1, a2);
}

```

## disassembly

```asm
0x180005934  sub     rsp, 38h
0x180005938  mov     [rsp+38h+arg_10], 0
0x180005941  mov     [rsp+38h+var_18], rdx
0x180005946  mov     r9, rcx
0x180005949  xor     r8d, r8d; pReturnValue
0x18000594c  lea     edx, [r8+1]; nProcNum
0x180005950  lea     rcx, pProxyInfo; pProxyInfo
0x180005957  call    cs:__imp_NdrClientCall3
0x18000595e  nop     dword ptr [rax+rax+00h]
0x180005963  mov     [rsp+38h+arg_10], rax
0x180005968  jmp     short loc_180005984
0x18000596a  mov     r9d, eax; char *
0x18000596d  mov     rcx, [rsp+38h]; this
0x180005972  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x180005979  mov     edx, 0A4h; void *
0x18000597e  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180005983  nop
0x180005984  add     rsp, 38h
0x180005988  retn
0x18001c90e  push    rbp
0x18001c910  sub     rsp, 30h
0x18001c914  mov     rbp, rdx
0x18001c917  mov     rcx, [rcx]
0x18001c91a  mov     ecx, [rcx]; ExceptionCode
0x18001c91c  call    cs:__imp_I_RpcExceptionFilter
0x18001c923  nop     dword ptr [rax+rax+00h]
0x18001c928  nop
0x18001c929  add     rsp, 30h
0x18001c92d  pop     rbp
0x18001c92e  retn
```
