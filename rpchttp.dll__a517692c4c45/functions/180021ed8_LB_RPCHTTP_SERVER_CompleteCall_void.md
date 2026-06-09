# LB_RPCHTTP_SERVER::CompleteCall(void)

- ea: `0x180021ed8`
- end: `0x180021f76`
- name: `?CompleteCall@LB_RPCHTTP_SERVER@@AEAAJXZ`
- size: `158`
- prototype: `__int64 __fastcall(LB_RPCHTTP_SERVER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800237c8`

## callees

- `0x180021238`
- `0x180021ed8`
- `0x1800242e8`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180021f63`
- `RPCRT4!RpcBindingFree` at `0x180021f63`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021eeb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180021eeb`

## pseudocode

```c
__int64 __fastcall LB_RPCHTTP_SERVER::CompleteCall(LB_RPCHTTP_SERVER *this)
{
  unsigned int v2; // edi
  __int64 v3; // rcx

  v2 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 80), 0);
  LB_RPCHTTP_SERVER::RemoveReference(this);
  v3 = *((unsigned int *)this + 50);
  *((_DWORD *)this + 48) = 2;
  if ( v2 )
  {
    if ( (_DWORD)v3 && (Microsoft_Windows_RPC_Proxy_LBSEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v3, RpcProxyLbsServerDeparted, *((_QWORD *)this + 3));
    *((_DWORD *)this + 50) = 0;
    RpcBindingFree((RPC_BINDING_HANDLE *)this + 9);
  }
  else
  {
    if ( !(_DWORD)v3 && (Microsoft_Windows_RPC_Proxy_LBSEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v3, RpcProxyLbsServerJoined, *((_QWORD *)this + 3));
    *((_DWORD *)this + 50) = 1;
  }
  return v2;
}

```

## disassembly

```asm
0x180021ed8  mov     [rsp+arg_0], rbx
0x180021edd  push    rdi
0x180021ede  sub     rsp, 20h
0x180021ee2  mov     rbx, rcx
0x180021ee5  xor     edx, edx; Reply
0x180021ee7  add     rcx, 50h ; 'P'; pAsync
0x180021eeb  call    cs:__imp_RpcAsyncCompleteCall
0x180021ef1  mov     rcx, rbx; this
0x180021ef4  mov     edi, eax
0x180021ef6  call    ?RemoveReference@LB_RPCHTTP_SERVER@@QEAAXXZ; LB_RPCHTTP_SERVER::RemoveReference(void)
0x180021efb  mov     ecx, [rbx+0C8h]
0x180021f01  mov     dword ptr [rbx+0C0h], 2
0x180021f0b  test    edi, edi
0x180021f0d  jnz     short loc_180021F38
0x180021f0f  test    ecx, ecx
0x180021f11  jnz     short loc_180021F2C
0x180021f13  test    cs:Microsoft_Windows_RPC_Proxy_LBSEnableBits, 1
0x180021f1a  jz      short loc_180021F2C
0x180021f1c  mov     r8, [rbx+18h]
0x180021f20  lea     rdx, RpcProxyLbsServerJoined
0x180021f27  call    McTemplateU0z_EventWriteTransfer
0x180021f2c  mov     dword ptr [rbx+0C8h], 1
0x180021f36  jmp     short loc_180021F69
0x180021f38  test    ecx, ecx
0x180021f3a  jz      short loc_180021F55
0x180021f3c  test    cs:Microsoft_Windows_RPC_Proxy_LBSEnableBits, 1
0x180021f43  jz      short loc_180021F55
0x180021f45  mov     r8, [rbx+18h]
0x180021f49  lea     rdx, RpcProxyLbsServerDeparted
0x180021f50  call    McTemplateU0z_EventWriteTransfer
0x180021f55  lea     rcx, [rbx+48h]; Binding
0x180021f59  mov     dword ptr [rbx+0C8h], 0
0x180021f63  call    cs:__imp_RpcBindingFree
0x180021f69  mov     rbx, [rsp+28h+arg_0]
0x180021f6e  mov     eax, edi
0x180021f70  add     rsp, 20h
0x180021f74  pop     rdi
0x180021f75  retn
```
