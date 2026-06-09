# _CPath::GetDirectorySizeRecursive_::_1_::dtor$0

- ea: `0x14001cf43`
- end: `0x14001cf4f`
- name: `_CPath::GetDirectorySizeRecursive_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400049f4`

## pseudocode

```c
__int64 __fastcall CPath::GetDirectorySizeRecursive_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(a2 + 144);
}

```

## disassembly

```asm
0x14001cf43  lea     rcx, [rdx+90h]
0x14001cf4a  jmp     ??1?$unique_any@Ufind_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::find_handle_traits>::~unique_any<tlx::find_handle_traits>(void)
```
