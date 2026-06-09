# _RPCReleaseClientContext(void *,void * *)

- ea: `0x18000521c`
- end: `0x18000526b`
- name: `?_RPCReleaseClientContext@@YAXPEAXPEAPEAX@Z`
- size: `79`
- prototype: `void __fastcall(void *, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004938`
- `0x180005db4`

## callees

- `0x18000521c`
- `0x18000cdf0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000523f`
- `RPCRT4!NdrClientCall3` at `0x18000523f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001adc6`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001adc6`

## string_xrefs

- `0x180005254`: `onecore\ds\security\gina\profile\userenv\dll\profrpc.cpp`

## pseudocode

```c
void __fastcall _RPCReleaseClientContext(void *a1, void **a2)
{
  NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, a1, a2);
}

```

## disassembly

```asm
0x18000521c  sub     rsp, 38h
0x180005220  mov     [rsp+38h+arg_10], 0
0x180005229  mov     [rsp+38h+var_18], rdx
0x18000522e  mov     r9, rcx
0x180005231  xor     r8d, r8d; pReturnValue
0x180005234  lea     edx, [r8+1]; nProcNum
0x180005238  lea     rcx, pProxyInfo; pProxyInfo
0x18000523f  call    cs:__imp_NdrClientCall3
0x180005245  mov     [rsp+38h+arg_10], rax
0x18000524a  jmp     short loc_180005266
0x18000524c  mov     r9d, eax; char *
0x18000524f  mov     rcx, [rsp+38h]; this
0x180005254  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\gina\\profile\\u"...
0x18000525b  mov     edx, 0A4h; void *
0x180005260  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180005265  nop
0x180005266  add     rsp, 38h
0x18000526a  retn
0x18001adb8  push    rbp
0x18001adba  sub     rsp, 30h
0x18001adbe  mov     rbp, rdx
0x18001adc1  mov     rcx, [rcx]
0x18001adc4  mov     ecx, [rcx]; ExceptionCode
0x18001adc6  call    cs:__imp_I_RpcExceptionFilter
0x18001adcc  nop
0x18001adcd  add     rsp, 30h
0x18001add1  pop     rbp
0x18001add2  retn
```
