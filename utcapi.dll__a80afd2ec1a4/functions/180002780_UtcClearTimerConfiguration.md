# UtcClearTimerConfiguration

- ea: `0x180002780`
- end: `0x1800027eb`
- name: `UtcClearTimerConfiguration`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002590`
- `0x180002780`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800027be`
- `RPCRT4!NdrClientCall3` at `0x1800027be`

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
0x180002780  sub     rsp, 48h
0x180002784  test    rcx, rcx
0x180002787  jnz     short loc_18000279F
0x180002789  mov     rcx, [rsp+48h]; this
0x18000278e  mov     edx, 73h ; 's'; void *
0x180002793  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002798  mov     eax, 80070057h
0x18000279d  jmp     short loc_1800027E5
0x18000279f  mov     [rsp+48h+arg_10], 0
0x1800027a8  mov     qword ptr [rsp+48h+var_28], rdx
0x1800027ad  mov     r9, rcx
0x1800027b0  xor     r8d, r8d; pReturnValue
0x1800027b3  lea     edx, [r8+0Fh]; nProcNum
0x1800027b7  lea     rcx, stru_180005790; pProxyInfo
0x1800027be  call    cs:__imp_NdrClientCall3
0x1800027c5  nop     dword ptr [rax+rax+00h]
0x1800027ca  mov     [rsp+48h+arg_10], rax
0x1800027cf  mov     [rsp+48h+var_18], eax
0x1800027d3  jmp     short loc_1800027E5
0x1800027d5  test    eax, eax
0x1800027d7  jle     short loc_1800027E1
0x1800027d9  movzx   eax, ax
0x1800027dc  or      eax, 80070000h
0x1800027e1  mov     [rsp+48h+var_18], eax
0x1800027e5  add     rsp, 48h
0x1800027e9  retn
0x18000316e  push    rbp
0x180003170  sub     rsp, 30h
0x180003174  mov     rbp, rdx
0x180003177  mov     rcx, [rcx]
0x18000317a  mov     ecx, [rcx]; ExceptionCode
0x18000317c  call    cs:__imp_RpcExceptionFilter
0x180003183  nop     dword ptr [rax+rax+00h]
0x180003188  nop
0x180003189  add     rsp, 30h
0x18000318d  pop     rbp
0x18000318e  retn
```
