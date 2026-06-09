# _DataCollectorCreate_::_1_::dtor$6

- ea: `0x14001ce21`
- end: `0x14001ce2d`
- name: `_DataCollectorCreate_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400049d0`

## pseudocode

```c
__int64 __fastcall DataCollectorCreate_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(a2 + 176);
}

```

## disassembly

```asm
0x14001ce21  lea     rcx, [rdx+0B0h]
0x14001ce28  jmp     ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
```
