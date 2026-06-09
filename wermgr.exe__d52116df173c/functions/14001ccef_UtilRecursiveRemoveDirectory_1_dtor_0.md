# _UtilRecursiveRemoveDirectory_::_1_::dtor$0

- ea: `0x14001ccef`
- end: `0x14001ccfb`
- name: `_UtilRecursiveRemoveDirectory_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x1400049f4`

## pseudocode

```c
__int64 __fastcall UtilRecursiveRemoveDirectory_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(a2 + 112);
}

```

## disassembly

```asm
0x14001ccef  lea     rcx, [rdx+70h]
0x14001ccf6  jmp     ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
```
