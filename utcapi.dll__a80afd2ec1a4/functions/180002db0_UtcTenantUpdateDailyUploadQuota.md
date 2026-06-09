# UtcTenantUpdateDailyUploadQuota

- ea: `0x180002db0`
- end: `0x180002e2d`
- name: `UtcTenantUpdateDailyUploadQuota`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180002590`
- `0x180002db0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002e00`
- `RPCRT4!NdrClientCall3` at `0x180002e00`

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
0x180002db0  sub     rsp, 48h
0x180002db4  test    rcx, rcx
0x180002db7  jnz     short loc_180002DCF
0x180002db9  mov     rcx, [rsp+48h]; this
0x180002dbe  mov     edx, 0BBh; void *
0x180002dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002dc8  mov     eax, 80070057h
0x180002dcd  jmp     short loc_180002E27
0x180002dcf  or      eax, 0FFFFFFFFh
0x180002dd2  cmp     r8d, eax
0x180002dd5  jz      short loc_180002DDD
0x180002dd7  mov     eax, r8d
0x180002dda  shl     eax, 14h
0x180002ddd  mov     [rsp+48h+arg_18], 0
0x180002de6  mov     [rsp+48h+var_20], eax
0x180002dea  mov     [rsp+48h+var_28], rdx
0x180002def  mov     r9, rcx
0x180002df2  xor     r8d, r8d; pReturnValue
0x180002df5  lea     edx, [r8+2]; nProcNum
0x180002df9  lea     rcx, pProxyInfo; pProxyInfo
0x180002e00  call    cs:__imp_NdrClientCall3
0x180002e07  nop     dword ptr [rax+rax+00h]
0x180002e0c  mov     [rsp+48h+arg_18], rax
0x180002e11  mov     [rsp+48h+var_18], eax
0x180002e15  jmp     short loc_180002E27
0x180002e17  test    eax, eax
0x180002e19  jle     short loc_180002E23
0x180002e1b  movzx   eax, ax
0x180002e1e  or      eax, 80070000h
0x180002e23  mov     [rsp+48h+var_18], eax
0x180002e27  add     rsp, 48h
0x180002e2b  retn
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
