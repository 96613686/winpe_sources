# _ComTaskHost::ComTaskHost_::_1_::dtor$3

- ea: `0x14000aea0`
- end: `0x14000aeb0`
- name: `_ComTaskHost::ComTaskHost_::_1_::dtor$3`
- size: `16`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006e90`

## pseudocode

```c
void __fastcall ComTaskHost::ComTaskHost_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  InterlockedAutoHandle::~InterlockedAutoHandle((InterlockedAutoHandle *)(*(_QWORD *)(a2 + 96) + 80LL));
}

```

## disassembly

```asm
0x14000aea0  mov     rcx, [rdx+60h]
0x14000aea7  add     rcx, 50h ; 'P'; this
0x14000aeab  jmp     ??1InterlockedAutoHandle@@QEAA@XZ; InterlockedAutoHandle::~InterlockedAutoHandle(void)
```
