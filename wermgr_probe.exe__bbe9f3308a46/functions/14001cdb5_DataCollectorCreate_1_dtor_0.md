# _DataCollectorCreate_::_1_::dtor$0

- ea: `0x14001cdb5`
- end: `0x14001cdc1`
- name: `_DataCollectorCreate_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400049d0`

## pseudocode

```c
__int64 __fastcall DataCollectorCreate_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(a2 + 80);
}

```

## disassembly

```asm
0x14001cdb5  lea     rcx, [rdx+50h]
0x14001cdbc  jmp     ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
```
