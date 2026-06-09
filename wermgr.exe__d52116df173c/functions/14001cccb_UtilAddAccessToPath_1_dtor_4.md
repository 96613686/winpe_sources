# _UtilAddAccessToPath_::_1_::dtor$4

- ea: `0x14001cccb`
- end: `0x14001ccd7`
- name: `_UtilAddAccessToPath_::_1_::dtor$4`
- size: `12`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400049d0`

## pseudocode

```c
int __fastcall UtilAddAccessToPath_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)(a2 + 216));
}

```

## disassembly

```asm
0x14001cccb  lea     rcx, [rdx+0D8h]
0x14001ccd2  jmp     ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
```
