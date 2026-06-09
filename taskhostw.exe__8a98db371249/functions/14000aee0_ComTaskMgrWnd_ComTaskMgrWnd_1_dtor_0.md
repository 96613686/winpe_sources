# _ComTaskMgrWnd::ComTaskMgrWnd_::_1_::dtor$0

- ea: `0x14000aee0`
- end: `0x14000aeec`
- name: `_ComTaskMgrWnd::ComTaskMgrWnd_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140007404`

## pseudocode

```c
void __fastcall ComTaskMgrWnd::ComTaskMgrWnd_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ComTaskMgrBase::~ComTaskMgrBase(*(ComTaskMgrBase **)(a2 + 64));
}

```

## disassembly

```asm
0x14000aee0  mov     rcx, [rdx+40h]; this
0x14000aee7  jmp     ??1ComTaskMgrBase@@MEAA@XZ; ComTaskMgrBase::~ComTaskMgrBase(void)
```
