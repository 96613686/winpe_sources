# SrvClientCertificatesAccessCheckComplete

- ea: `0x1400484c0`
- end: `0x140048517`
- name: `SrvClientCertificatesAccessCheckComplete`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400484c0`
- `0x14004a268`
- `0x14004adf0`

## import_xrefs

- `msrpc!RpcAsyncCompleteCall` at `0x1400484dc`
- `msrpc!RpcAsyncCompleteCall` at `0x1400484dc`

## pseudocode

```c
void __fastcall SrvClientCertificatesAccessCheckComplete(struct _RPC_ASYNC_STATE *a1, __int64 a2, int a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int Reply; // [rsp+40h] [rbp+18h] BYREF

  if ( !a3 )
  {
    Reply = 0;
    v4 = RpcAsyncCompleteCall(a1, &Reply);
    v5 = v4;
    if ( v4 == 259 )
      __int2c();
    RfsRpcBindingEndRpcCall(&SrvIdSegRpcBinding, v4);
    SrvNetQuicClientCertificatesAccessCheckComplete(v5, a1);
  }
}

```

## disassembly

```asm
0x1400484c0  test    r8d, r8d
0x1400484c3  jnz     short locret_140048515
0x1400484c5  mov     [rsp+arg_0], rbx
0x1400484ca  push    rdi
0x1400484cb  sub     rsp, 20h
0x1400484cf  lea     rdx, [rsp+28h+Reply]; Reply
0x1400484d4  mov     [rsp+28h+Reply], r8d
0x1400484d9  mov     rdi, rcx
0x1400484dc  call    cs:__imp_RpcAsyncCompleteCall
0x1400484e3  nop     dword ptr [rax+rax+00h]
0x1400484e8  mov     ebx, eax
0x1400484ea  cmp     eax, 103h
0x1400484ef  jnz     short loc_1400484F3
0x1400484f1  int     2Ch; Windows NT - assertion failure
0x1400484f3  mov     edx, ebx
0x1400484f5  lea     rcx, SrvIdSegRpcBinding
0x1400484fc  call    RfsRpcBindingEndRpcCall
0x140048501  mov     rdx, rdi
0x140048504  mov     ecx, ebx
0x140048506  call    SrvNetQuicClientCertificatesAccessCheckComplete
0x14004850b  mov     rbx, [rsp+28h+arg_0]
0x140048510  add     rsp, 20h
0x140048514  pop     rdi
0x140048515  retn
```
