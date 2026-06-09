# UtcUpdateTimerConfiguration

- ea: `0x180002e40`
- end: `0x180002ed6`
- name: `UtcUpdateTimerConfiguration`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callees

- `0x180002590`
- `0x180002e40`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002ea6`
- `RPCRT4!NdrClientCall3` at `0x180002ea6`
- `RPCRT4!RpcExceptionFilter` at `0x18000317c`
- `RPCRT4!RpcExceptionFilter` at `0x18000317c`

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
0x180002e40  sub     rsp, 78h
0x180002e44  test    rcx, rcx
0x180002e47  jnz     short loc_180002E5F
0x180002e49  mov     rcx, [rsp+78h]; this
0x180002e4e  mov     edx, 61h ; 'a'; void *
0x180002e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e58  mov     eax, 80070057h
0x180002e5d  jmp     short loc_180002ED0
0x180002e5f  mov     [rsp+78h+arg_18], 0
0x180002e6b  movups  xmm0, xmmword ptr [r8]
0x180002e6f  movaps  [rsp+78h+var_38], xmm0
0x180002e74  movups  xmm1, xmmword ptr [r8+10h]
0x180002e79  movaps  [rsp+78h+var_28], xmm1
0x180002e7e  mov     eax, [r8+20h]
0x180002e82  mov     [rsp+78h+var_18], eax
0x180002e86  lea     rax, [rsp+78h+var_38]
0x180002e8b  mov     [rsp+78h+var_50], rax
0x180002e90  mov     [rsp+78h+var_58], rdx
0x180002e95  mov     r9, rcx
0x180002e98  xor     r8d, r8d; pReturnValue
0x180002e9b  lea     edx, [r8+0Eh]; nProcNum
0x180002e9f  lea     rcx, stru_180005790; pProxyInfo
0x180002ea6  call    cs:__imp_NdrClientCall3
0x180002ead  nop     dword ptr [rax+rax+00h]
0x180002eb2  mov     [rsp+78h+arg_18], rax
0x180002eba  mov     [rsp+78h+var_48], eax
0x180002ebe  jmp     short loc_180002ED0
0x180002ec0  test    eax, eax
0x180002ec2  jle     short loc_180002ECC
0x180002ec4  movzx   eax, ax
0x180002ec7  or      eax, 80070000h
0x180002ecc  mov     [rsp+78h+var_48], eax
0x180002ed0  add     rsp, 78h
0x180002ed4  retn
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
