# SubscriptionConfigEnumerator::~SubscriptionConfigEnumerator(void)

- ea: `0x180003c7c`
- end: `0x180003c81`
- name: `??1SubscriptionConfigEnumerator@@UEAA@XZ`
- size: `5`
- prototype: `void __fastcall(ConfigEnumerator *this, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002065c`
- `0x1800209e7`

## callees

- `0x180003c10`

## pseudocode

```c
// attributes: thunk
void __fastcall SubscriptionConfigEnumerator::~SubscriptionConfigEnumerator(ConfigEnumerator *this, __int64 a2)
{
  ConfigEnumerator::~ConfigEnumerator(this, a2);
}

```

## disassembly

```asm
0x180003c7c  jmp     ??1ConfigEnumerator@@UEAA@XZ; ConfigEnumerator::~ConfigEnumerator(void)
```
