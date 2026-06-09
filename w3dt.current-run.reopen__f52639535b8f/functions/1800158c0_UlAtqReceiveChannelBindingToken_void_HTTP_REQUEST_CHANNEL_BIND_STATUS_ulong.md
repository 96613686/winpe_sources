# UlAtqReceiveChannelBindingToken(void *,_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)

- ea: `0x1800158c0`
- end: `0x1800158c5`
- name: `?UlAtqReceiveChannelBindingToken@@YAJPEAXPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z`
- size: `5`
- prototype: `__int64 __fastcall(void *, struct _HTTP_REQUEST_CHANNEL_BIND_STATUS *, unsigned int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180014e9c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall UlAtqReceiveChannelBindingToken(
        UL_NATIVE_REQUEST *this,
        struct _HTTP_SSL_CLIENT_CERT_INFO *a2,
        unsigned int *a3)
{
  return UL_NATIVE_REQUEST::ReceiveChannelBindingToken(this, a2, a3);
}

```

## disassembly

```asm
0x1800158c0  jmp     ?ReceiveChannelBindingToken@UL_NATIVE_REQUEST@@QEAAJPEAU_HTTP_REQUEST_CHANNEL_BIND_STATUS@@PEAK@Z; UL_NATIVE_REQUEST::ReceiveChannelBindingToken(_HTTP_REQUEST_CHANNEL_BIND_STATUS *,ulong *)
```
