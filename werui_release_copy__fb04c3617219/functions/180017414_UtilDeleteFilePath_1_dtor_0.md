# _UtilDeleteFilePath_::_1_::dtor$0

- ea: `0x180017414`
- end: `0x180017420`
- name: `_UtilDeleteFilePath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180005ddc`

## pseudocode

```c
__int64 __fastcall UtilDeleteFilePath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(a2 + 136);
}

```

## disassembly

```asm
0x180017414  lea     rcx, [rdx+88h]
0x18001741b  jmp     ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
```
