# SubscriptionConfigWriter::~SubscriptionConfigWriter(void)

- ea: `0x1800154cc`
- end: `0x1800154eb`
- name: `??1SubscriptionConfigWriter@@UEAA@XZ`
- size: `31`
- prototype: `void __fastcall(SubscriptionConfigWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800155b0`

## callees

- `0x180003be8`
- `0x18001dbd4`

## pseudocode

```c
void __fastcall SubscriptionConfigWriter::~SubscriptionConfigWriter(SubscriptionConfigWriter *this)
{
  SubscriptionReadData::~SubscriptionReadData((SubscriptionConfigWriter *)((char *)this + 24));
  ConfigBase::~ConfigBase(this);
}

```

## disassembly

```asm
0x1800154cc  push    rbx
0x1800154ce  sub     rsp, 20h
0x1800154d2  mov     rbx, rcx
0x1800154d5  add     rcx, 18h; this
0x1800154d9  call    ??1SubscriptionReadData@@QEAA@XZ; SubscriptionReadData::~SubscriptionReadData(void)
0x1800154de  mov     rcx, rbx; this
0x1800154e1  add     rsp, 20h
0x1800154e5  pop     rbx
0x1800154e6  jmp     ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
```
