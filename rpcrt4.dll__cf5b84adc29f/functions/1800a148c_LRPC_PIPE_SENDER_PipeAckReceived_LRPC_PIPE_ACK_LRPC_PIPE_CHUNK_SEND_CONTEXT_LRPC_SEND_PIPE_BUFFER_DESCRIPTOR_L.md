# LRPC_PIPE_SENDER::PipeAckReceived(_LRPC_PIPE_ACK *,LRPC_PIPE_CHUNK_SEND_CONTEXT *,LRPC_SEND_PIPE_BUFFER_DESCRIPTOR * *,LRPC_SENT_PIPE_BUFFER_INFO * *,unsigned __int64 *,int *)

- ea: `0x1800a148c`
- end: `0x1800a16fc`
- name: `?PipeAckReceived@LRPC_PIPE_SENDER@@QEAAJPEAU_LRPC_PIPE_ACK@@PEAVLRPC_PIPE_CHUNK_SEND_CONTEXT@@PEAPEAVLRPC_SEND_PIPE_BUFFER_DESCRIPTOR@@PEAPEAVLRPC_SENT_PIPE_BUFFER_INFO@@PEA_KPEAH@Z`
- size: `624`
- prototype: `__int64 __fastcall(LRPC_PIPE_SENDER *__hidden this, struct _LRPC_PIPE_ACK *, struct LRPC_PIPE_CHUNK_SEND_CONTEXT *, struct LRPC_SEND_PIPE_BUFFER_DESCRIPTOR **, struct LRPC_SENT_PIPE_BUFFER_INFO **, unsigned __int64 *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800a1274`
- `0x1800ab914`

## callees

- `0x18002cab0`
- `0x18003227c`
- `0x1800a148c`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x1800a1515`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a15d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a16d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a1515`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a15d8`
- `ntdll!RtlLeaveCriticalSection` at `0x1800a16d8`
- `ntdll!RtlEnterCriticalSection` at `0x1800a1500`
- `ntdll!RtlEnterCriticalSection` at `0x1800a1500`

## pseudocode

```c

```
