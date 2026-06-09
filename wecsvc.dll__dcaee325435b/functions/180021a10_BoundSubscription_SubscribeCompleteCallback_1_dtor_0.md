# _BoundSubscription::SubscribeCompleteCallback_::_1_::dtor$0

- ea: `0x180021a10`
- end: `0x180021a1c`
- name: `_BoundSubscription::SubscribeCompleteCallback_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003c58`

## pseudocode

```c
void __fastcall BoundSubscription::SubscribeCompleteCallback_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  wmi::InCritSec::~InCritSec((LPCRITICAL_SECTION *)(a2 + 88));
}

```

## disassembly

```asm
0x180021a10  lea     rcx, [rdx+58h]; this
0x180021a17  jmp     ??1InCritSec@wmi@@QEAA@XZ; wmi::InCritSec::~InCritSec(void)
```
