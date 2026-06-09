# _CollectorService::CollectorService_::_1_::dtor$2

- ea: `0x18002051a`
- end: `0x18002052a`
- name: `_CollectorService::CollectorService_::_1_::dtor$2`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003b0c`

## pseudocode

```c
__int64 __fastcall CollectorService::CollectorService_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::auto_ptr<AbstractEventReporter>::~auto_ptr<AbstractEventReporter>(*(_QWORD *)(a2 + 160) + 16LL);
}

```

## disassembly

```asm
0x18002051a  mov     rcx, [rdx+0A0h]
0x180020521  add     rcx, 10h
0x180020525  jmp     ??1?$auto_ptr@VAbstractEventReporter@@@std@@QEAA@XZ; std::auto_ptr<AbstractEventReporter>::~auto_ptr<AbstractEventReporter>(void)
```
