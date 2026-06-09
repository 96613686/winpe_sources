# UtcTenantUpdateDailyUploadQuota

- ea: `0x180002d00`
- end: `0x180002d76`
- name: `UtcTenantUpdateDailyUploadQuota`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180002560`
- `0x180002d00`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002d50`
- `RPCRT4!NdrClientCall3` at `0x180002d50`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall UtcTenantUpdateDailyUploadQuota(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  int v5; // eax
  int v6; // [rsp+20h] [rbp-28h]
  int v7; // [rsp+28h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a1 )
  {
    v5 = -1;
    if ( a3 != -1 )
      v5 = a3 << 20;
    v7 = v5;
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, a1, a2, v7);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xBB, a3, a4, v6);
    return (CLIENT_CALL_RETURN)2147942487LL;
  }
}

```

## disassembly

```asm
0x180002d00  sub     rsp, 48h
0x180002d04  test    rcx, rcx
0x180002d07  jnz     short loc_180002D1F
0x180002d09  mov     rcx, [rsp+48h]; this
0x180002d0e  mov     edx, 0BBh; void *
0x180002d13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002d18  mov     eax, 80070057h
0x180002d1d  jmp     short loc_180002D71
0x180002d1f  or      eax, 0FFFFFFFFh
0x180002d22  cmp     r8d, eax
0x180002d25  jz      short loc_180002D2D
0x180002d27  mov     eax, r8d
0x180002d2a  shl     eax, 14h
0x180002d2d  mov     [rsp+48h+arg_18], 0
0x180002d36  mov     [rsp+48h+var_20], eax
0x180002d3a  mov     [rsp+48h+var_28], rdx
0x180002d3f  mov     r9, rcx
0x180002d42  xor     r8d, r8d; pReturnValue
0x180002d45  lea     edx, [r8+2]; nProcNum
0x180002d49  lea     rcx, pProxyInfo; pProxyInfo
0x180002d50  call    cs:__imp_NdrClientCall3
0x180002d56  mov     [rsp+48h+arg_18], rax
0x180002d5b  mov     [rsp+48h+var_18], eax
0x180002d5f  jmp     short loc_180002D71
0x180002d61  test    eax, eax
0x180002d63  jle     short loc_180002D6D
0x180002d65  movzx   eax, ax
0x180002d68  or      eax, 80070000h
0x180002d6d  mov     [rsp+48h+var_18], eax
0x180002d71  add     rsp, 48h
0x180002d75  retn
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
