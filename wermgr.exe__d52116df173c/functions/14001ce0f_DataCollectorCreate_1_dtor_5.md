# _DataCollectorCreate_::_1_::dtor$5

- ea: `0x14001ce0f`
- end: `0x14001ce1b`
- name: `_DataCollectorCreate_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140016270`

## pseudocode

```c
__int64 __fastcall DataCollectorCreate_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::handle_traits<IStream *,void (*)(IStream *),&void MstmFree(IStream *),0>>::~unique_any<tlx::handle_traits<IStream *,void (*)(IStream *),&void MstmFree(IStream *),0>>(a2 + 120);
}

```

## disassembly

```asm
0x14001ce0f  lea     rcx, [rdx+78h]
0x14001ce16  jmp     ??1?$unique_any@U?$handle_traits@PEAUIStream@@P6AXPEAU1@@Z$1?MstmFree@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<IStream *,void (*)(IStream *),&MstmFree(IStream *),0>>::~unique_any<tlx::handle_traits<IStream *,void (*)(IStream *),&MstmFree(IStream *),0>>(void)
```
