# HTTP2IISTransportChannel::PostDirectReceiveComplete(void)

- ea: `0x180010900`
- end: `0x18001090f`
- name: `?PostDirectReceiveComplete@HTTP2IISTransportChannel@@MEAAJXZ`
- size: `15`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001e91c`

## pseudocode

```c
__int64 __fastcall HTTP2IISTransportChannel::PostDirectReceiveComplete(PVOID pv)
{
  return RPC_THREAD_POOL::TrySubmitWork((PTP_SIMPLE_CALLBACK)HTTP2IISDirectReceive, pv);
}

```

## disassembly

```asm
0x180010900  mov     rdx, rcx; pv
0x180010903  lea     rcx, ?HTTP2IISDirectReceive@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001090a  jmp     ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
```
