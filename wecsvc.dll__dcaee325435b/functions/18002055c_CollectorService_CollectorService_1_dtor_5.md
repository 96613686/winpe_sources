# _CollectorService::CollectorService_::_1_::dtor$5

- ea: `0x18002055c`
- end: `0x18002056c`
- name: `_CollectorService::CollectorService_::_1_::dtor$5`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180003b5c`

## pseudocode

```c
void __fastcall CollectorService::CollectorService_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  wmi::AutoHandle::~AutoHandle((wmi::AutoHandle *)(*(_QWORD *)(a2 + 160) + 112LL));
}

```

## disassembly

```asm
0x18002055c  mov     rcx, [rdx+0A0h]
0x180020563  add     rcx, 70h ; 'p'; this
0x180020567  jmp     ??1AutoHandle@wmi@@QEAA@XZ; wmi::AutoHandle::~AutoHandle(void)
```
