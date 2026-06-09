# UtcClearTimerConfiguration

- ea: `0x180002730`
- end: `0x180002794`
- name: `UtcClearTimerConfiguration`
- size: `100`
- prototype: `CLIENT_CALL_RETURN __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002560`
- `0x180002730`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000276e`
- `RPCRT4!NdrClientCall3` at `0x18000276e`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall UtcClearTimerConfiguration(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a1 )
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180005790, 0xFu, 0, a1, a2);
  wil::details::in1diag3::Return_Hr(retaddr, (void *)0x73, a3, a4, v5);
  return (CLIENT_CALL_RETURN)2147942487LL;
}

```

## disassembly

```asm
0x180002730  sub     rsp, 48h
0x180002734  test    rcx, rcx
0x180002737  jnz     short loc_18000274F
0x180002739  mov     rcx, [rsp+48h]; this
0x18000273e  mov     edx, 73h ; 's'; void *
0x180002743  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002748  mov     eax, 80070057h
0x18000274d  jmp     short loc_18000278F
0x18000274f  mov     [rsp+48h+arg_10], 0
0x180002758  mov     qword ptr [rsp+48h+var_28], rdx
0x18000275d  mov     r9, rcx
0x180002760  xor     r8d, r8d; pReturnValue
0x180002763  lea     edx, [r8+0Fh]; nProcNum
0x180002767  lea     rcx, stru_180005790; pProxyInfo
0x18000276e  call    cs:__imp_NdrClientCall3
0x180002774  mov     [rsp+48h+arg_10], rax
0x180002779  mov     [rsp+48h+var_18], eax
0x18000277d  jmp     short loc_18000278F
0x18000277f  test    eax, eax
0x180002781  jle     short loc_18000278B
0x180002783  movzx   eax, ax
0x180002786  or      eax, 80070000h
0x18000278b  mov     [rsp+48h+var_18], eax
0x18000278f  add     rsp, 48h
0x180002793  retn
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
