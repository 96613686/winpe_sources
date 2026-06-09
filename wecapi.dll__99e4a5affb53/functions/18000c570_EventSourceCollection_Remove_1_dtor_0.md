# _EventSourceCollection::Remove_::_1_::dtor$0

- ea: `0x18000c570`
- end: `0x18000c57c`
- name: `_EventSourceCollection::Remove_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800032c8`

## pseudocode

```c
__int64 __fastcall EventSourceCollection::Remove_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wmi::AutoRef<Object>::~AutoRef<Object>(a2 + 112);
}

```

## disassembly

```asm
0x18000c570  lea     rcx, [rdx+70h]
0x18000c577  jmp     ??1?$AutoRef@VObject@@@wmi@@QEAA@XZ; wmi::AutoRef<Object>::~AutoRef<Object>(void)
```
