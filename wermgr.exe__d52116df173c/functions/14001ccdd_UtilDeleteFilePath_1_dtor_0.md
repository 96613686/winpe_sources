# _UtilDeleteFilePath_::_1_::dtor$0

- ea: `0x14001ccdd`
- end: `0x14001cce9`
- name: `_UtilDeleteFilePath_::_1_::dtor$0`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400049d0`

## pseudocode

```c
int __fastcall UtilDeleteFilePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)(a2 + 128));
}

```

## disassembly

```asm
0x14001ccdd  lea     rcx, [rdx+80h]
0x14001cce4  jmp     ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
```
