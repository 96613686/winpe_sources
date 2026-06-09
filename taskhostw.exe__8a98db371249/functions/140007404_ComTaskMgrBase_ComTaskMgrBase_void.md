# ComTaskMgrBase::~ComTaskMgrBase(void)

- ea: `0x140007404`
- end: `0x14000740f`
- name: `??1ComTaskMgrBase@@MEAA@XZ`
- size: `11`
- prototype: `void __fastcall(ComTaskMgrBase *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000aee0`

## pseudocode

```c
void __fastcall ComTaskMgrBase::~ComTaskMgrBase(ComTaskMgrBase *this)
{
  *(_QWORD *)this = &ComTaskMgrBase::`vftable';
}

```

## disassembly

```asm
0x140007404  lea     rax, ??_7ComTaskMgrBase@@6B@; const ComTaskMgrBase::`vftable'
0x14000740b  mov     [rcx], rax
0x14000740e  retn
```
