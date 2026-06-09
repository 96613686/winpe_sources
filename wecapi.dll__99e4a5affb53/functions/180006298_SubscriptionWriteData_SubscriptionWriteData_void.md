# SubscriptionWriteData::~SubscriptionWriteData(void)

- ea: `0x180006298`
- end: `0x18000629d`
- name: `??1SubscriptionWriteData@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(SubscriptionWriteData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c490`

## callees

- `0x18000a3e0`

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
0x180006298  jmp     ??1SubscriptionReadData@@QEAA@XZ; SubscriptionReadData::~SubscriptionReadData(void)
```
