# _CollectorService::CollectorService_::_1_::dtor$3

- ea: `0x180020530`
- end: `0x180020540`
- name: `_CollectorService::CollectorService_::_1_::dtor$3`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003c48`

## pseudocode

```c
void __fastcall CollectorService::CollectorService_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  wmi::CritSec::~CritSec((LPCRITICAL_SECTION)(*(_QWORD *)(a2 + 160) + 24LL));
}

```

## disassembly

```asm
0x180020530  mov     rcx, [rdx+0A0h]
0x180020537  add     rcx, 18h; lpCriticalSection
0x18002053b  jmp     ??1CritSec@wmi@@QEAA@XZ; wmi::CritSec::~CritSec(void)
```
