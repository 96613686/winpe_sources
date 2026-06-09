# HTTP2WinHttpTransportChannel::PostDirectReceiveComplete(void)

- ea: `0x180010920`
- end: `0x18001092f`
- name: `?PostDirectReceiveComplete@HTTP2WinHttpTransportChannel@@EEAAJXZ`
- size: `15`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001e91c`

## pseudocode

```c
__int64 __fastcall HTTP2WinHttpTransportChannel::PostDirectReceiveComplete(PVOID pv)
{
  return RPC_THREAD_POOL::TrySubmitWork(HTTP2WinHttpDirectReceive, pv);
}

```

## disassembly

```asm
0x180010920  mov     rdx, rcx; pv
0x180010923  lea     rcx, ?HTTP2WinHttpDirectReceive@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z; pfns
0x18001092a  jmp     ?TrySubmitWork@RPC_THREAD_POOL@@SAJP6AXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z1@Z; RPC_THREAD_POOL::TrySubmitWork(void (*)(_TP_CALLBACK_INSTANCE *,void *),void *)
```
