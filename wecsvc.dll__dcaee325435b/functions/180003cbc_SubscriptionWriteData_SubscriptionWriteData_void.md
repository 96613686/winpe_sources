# SubscriptionWriteData::~SubscriptionWriteData(void)

- ea: `0x180003cbc`
- end: `0x180003cc1`
- name: `??1SubscriptionWriteData@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(struct tag_EcRpcMetadataPropertyList **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002231e`
- `0x18002238e`

## callees

- `0x18001dbd4`

## pseudocode

```c
// attributes: thunk
void __fastcall SubscriptionWriteData::~SubscriptionWriteData(struct tag_EcRpcMetadataPropertyList **this)
{
  SubscriptionReadData::~SubscriptionReadData(this);
}

```

## disassembly

```asm
0x180003cbc  jmp     ??1SubscriptionReadData@@QEAA@XZ; SubscriptionReadData::~SubscriptionReadData(void)
```
