# PowerRegisterLegacyEventNotification

- ea: `0x140025830`
- end: `0x140025910`
- name: `PowerRegisterLegacyEventNotification`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140024ab0`

## callees

- `0x140025830`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x140025894`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x140025894`
- `RPCRT4!RpcStringBindingComposeW` at `0x14002587b`
- `RPCRT4!RpcStringBindingComposeW` at `0x14002587b`
- `RPCRT4!I_RpcExceptionFilter` at `0x140092c21`
- `RPCRT4!I_RpcExceptionFilter` at `0x140092c21`
- `RPCRT4!NdrClientCall3` at `0x1400258c9`
- `RPCRT4!NdrClientCall3` at `0x1400258c9`
- `RPCRT4!RpcBindingFree` at `0x1400258fe`
- `RPCRT4!RpcBindingFree` at `0x1400258fe`
- `RPCRT4!RpcStringFreeW` at `0x1400258eb`
- `RPCRT4!RpcStringFreeW` at `0x1400258eb`

## string_xrefs

- `0x14002585d`: `Security=Impersonation Dynamic True`

## pseudocode

```c
__int64 __fastcall PowerRegisterLegacyEventNotification(__int64 a1, __int64 a2, int a3)
{
  unsigned int v6; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v9; // [rsp+48h] [rbp-30h]
  RPC_WSTR StringBinding; // [rsp+98h] [rbp+20h] BYREF

  StringBinding = 0;
  Binding = (RPC_BINDING_HANDLE)-1LL;
  v6 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         (RPC_WSTR)L"umpo",
         L"Security=Impersonation Dynamic True",
         &StringBinding);
  if ( !v6 )
  {
    v6 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    if ( !v6 )
    {
      v9.Simple = 0;
      v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x19u, 0, Binding, a1, a2, a3).Pointer;
    }
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  if ( Binding != (RPC_BINDING_HANDLE)-1LL )
    RpcBindingFree(&Binding);
  return v6;
}

```

## disassembly

```asm
0x140025830  mov     r11, rsp
0x140025833  push    rbx
0x140025834  push    rsi
0x140025835  push    rdi
0x140025836  push    r14
0x140025838  sub     rsp, 58h
0x14002583c  mov     edi, r8d
0x14002583f  mov     rsi, rdx
0x140025842  mov     r14, rcx
0x140025845  mov     qword ptr [r11+20h], 0
0x14002584d  mov     qword ptr [r11-38h], 0FFFFFFFFFFFFFFFFh
0x140025855  lea     rax, [r11+20h]
0x140025859  mov     [r11-50h], rax
0x14002585d  lea     rax, aSecurityImpers; "Security=Impersonation Dynamic True"
0x140025864  mov     [r11-58h], rax
0x140025868  lea     r9, aUmpo; "umpo"
0x14002586f  xor     r8d, r8d; NetworkAddr
0x140025872  lea     rdx, ProtSeq; "ncalrpc"
0x140025879  xor     ecx, ecx; ObjUuid
0x14002587b  call    cs:__imp_RpcStringBindingComposeW
0x140025881  mov     ebx, eax
0x140025883  test    eax, eax
0x140025885  jnz     short loc_1400258D8
0x140025887  lea     rdx, [rsp+78h+Binding]; Binding
0x14002588c  mov     rcx, [rsp+78h+StringBinding]; StringBinding
0x140025894  call    cs:__imp_RpcBindingFromStringBindingW
0x14002589a  mov     ebx, eax
0x14002589c  test    eax, eax
0x14002589e  jnz     short loc_1400258D8
0x1400258a0  mov     [rsp+78h+var_30], 0
0x1400258a9  mov     [rsp+78h+var_48], edi
0x1400258ad  mov     [rsp+78h+var_50], rsi
0x1400258b2  mov     [rsp+78h+var_58], r14
0x1400258b7  mov     r9, [rsp+78h+Binding]
0x1400258bc  xor     r8d, r8d; pReturnValue
0x1400258bf  lea     edx, [rax+19h]; nProcNum
0x1400258c2  lea     rcx, pProxyInfo; pProxyInfo
0x1400258c9  call    cs:__imp_NdrClientCall3
0x1400258cf  mov     [rsp+78h+var_30], rax
0x1400258d4  jmp     short loc_1400258D8
0x1400258d6  mov     ebx, eax
0x1400258d8  cmp     [rsp+78h+StringBinding], 0
0x1400258e1  jz      short loc_1400258F1
0x1400258e3  lea     rcx, [rsp+78h+StringBinding]; String
0x1400258eb  call    cs:__imp_RpcStringFreeW
0x1400258f1  cmp     [rsp+78h+Binding], 0FFFFFFFFFFFFFFFFh
0x1400258f7  jz      short loc_140025904
0x1400258f9  lea     rcx, [rsp+78h+Binding]; Binding
0x1400258fe  call    cs:__imp_RpcBindingFree
0x140025904  mov     eax, ebx
0x140025906  add     rsp, 58h
0x14002590a  pop     r14
0x14002590c  pop     rdi
0x14002590d  pop     rsi
0x14002590e  pop     rbx
0x14002590f  retn
0x140092c13  push    rbp
0x140092c15  sub     rsp, 40h
0x140092c19  mov     rbp, rdx
0x140092c1c  mov     rcx, [rcx]
0x140092c1f  mov     ecx, [rcx]; ExceptionCode
0x140092c21  call    cs:__imp_I_RpcExceptionFilter
0x140092c27  nop
0x140092c28  add     rsp, 40h
0x140092c2c  pop     rbp
0x140092c2d  retn
```
