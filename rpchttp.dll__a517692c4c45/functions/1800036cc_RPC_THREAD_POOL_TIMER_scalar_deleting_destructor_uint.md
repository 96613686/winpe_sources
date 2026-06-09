# RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(uint)

- ea: `0x1800036cc`
- end: `0x1800036f0`
- name: `??_GRPC_THREAD_POOL_TIMER@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(RPC_THREAD_POOL_TIMER *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b90`
- `0x18000a880`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1800036d8`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800036d8`
- `RPCRT4!I_RpcFree` at `0x1800036e1`
- `RPCRT4!I_RpcFree` at `0x1800036e1`

## pseudocode

```c
PTP_TIMER *__fastcall RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(PTP_TIMER *this)
{
  CloseThreadpoolTimer(*this);
  I_RpcFree(this);
  return this;
}

```

## disassembly

```asm
0x1800036cc  push    rbx
0x1800036ce  sub     rsp, 20h
0x1800036d2  mov     rbx, rcx
0x1800036d5  mov     rcx, [rcx]; pti
0x1800036d8  call    cs:__imp_CloseThreadpoolTimer
0x1800036de  mov     rcx, rbx; Object
0x1800036e1  call    cs:__imp_I_RpcFree
0x1800036e7  mov     rax, rbx
0x1800036ea  add     rsp, 20h
0x1800036ee  pop     rbx
0x1800036ef  retn
```
