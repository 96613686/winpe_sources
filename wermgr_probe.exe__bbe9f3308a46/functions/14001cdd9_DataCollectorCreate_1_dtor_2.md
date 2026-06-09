# _DataCollectorCreate_::_1_::dtor$2

- ea: `0x14001cdd9`
- end: `0x14001cde5`
- name: `_DataCollectorCreate_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400049d0`

## pseudocode

```c
__int64 __fastcall DataCollectorCreate_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(a2 + 88);
}

```

## disassembly

```asm
0x14001cdd9  lea     rcx, [rdx+58h]
0x14001cde0  jmp     ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
```
