# _UtilRecursiveRemoveDirectory_::_1_::dtor$0

- ea: `0x180017426`
- end: `0x180017432`
- name: `_UtilRecursiveRemoveDirectory_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000f690`

## pseudocode

```c
__int64 __fastcall UtilRecursiveRemoveDirectory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(a2 + 80);
}

```

## disassembly

```asm
0x180017426  lea     rcx, [rdx+50h]
0x18001742d  jmp     ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
```
