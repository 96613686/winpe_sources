# _ComTaskMgrBase::Initialize_::_1_::dtor$1

- ea: `0x14000a4ee`
- end: `0x14000a4fc`
- name: `_ComTaskMgrBase::Initialize_::_1_::dtor$1`
- size: `14`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, service_task, broker_com_uri`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000a4f5`

## pseudocode

```c
void __fastcall ComTaskMgrBase::Initialize_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 72));
}

```

## disassembly

```asm
0x14000a4ee  mov     rcx, [rdx+48h]
0x14000a4f5  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
