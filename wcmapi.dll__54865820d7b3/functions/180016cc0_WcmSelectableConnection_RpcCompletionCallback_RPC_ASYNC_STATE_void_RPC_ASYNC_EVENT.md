# WcmSelectableConnection::RpcCompletionCallback(_RPC_ASYNC_STATE *,void *,_RPC_ASYNC_EVENT)

- ea: `0x180016cc0`
- end: `0x180016ccc`
- name: `?RpcCompletionCallback@WcmSelectableConnection@@CAXPEAU_RPC_ASYNC_STATE@@PEAXW4_RPC_ASYNC_EVENT@@@Z`
- size: `12`
- prototype: `void __fastcall(struct _RPC_ASYNC_STATE *, void *, enum _RPC_ASYNC_EVENT)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000761c`

## pseudocode

```c
void __fastcall WcmSelectableConnection::RpcCompletionCallback(
        struct _RPC_ASYNC_STATE *a1,
        void *a2,
        enum _RPC_ASYNC_EVENT a3)
{
  WcmSelectableConnection::AcquireAsyncComplete((struct _RTL_CRITICAL_SECTION *)a1->UserInfo, a1);
}

```

## disassembly

```asm
0x180016cc0  mov     rdx, rcx; struct _RPC_ASYNC_STATE *
0x180016cc3  mov     rcx, [rcx+18h]; this
0x180016cc7  jmp     ?AcquireAsyncComplete@WcmSelectableConnection@@AEAAXPEAU_RPC_ASYNC_STATE@@@Z; WcmSelectableConnection::AcquireAsyncComplete(_RPC_ASYNC_STATE *)
```
