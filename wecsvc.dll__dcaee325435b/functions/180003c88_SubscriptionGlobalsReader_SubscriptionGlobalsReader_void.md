# SubscriptionGlobalsReader::~SubscriptionGlobalsReader(void)

- ea: `0x180003c88`
- end: `0x180003c8d`
- name: `??1SubscriptionGlobalsReader@@UEAA@XZ`
- size: `5`
- prototype: `void __fastcall(SubscriptionGlobalsReader *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002064a`
- `0x1800206ec`
- `0x18002078e`
- `0x18002099f`
- `0x180020e14`
- `0x180020ebb`
- `0x180022358`
- `0x18002237c`

## callees

- `0x180003be8`

## pseudocode

```c
// attributes: thunk
void __fastcall SubscriptionGlobalsReader::~SubscriptionGlobalsReader(SubscriptionGlobalsReader *this)
{
  ConfigBase::~ConfigBase(this);
}

```

## disassembly

```asm
0x180003c88  jmp     ??1ConfigBase@@UEAA@XZ; ConfigBase::~ConfigBase(void)
```
