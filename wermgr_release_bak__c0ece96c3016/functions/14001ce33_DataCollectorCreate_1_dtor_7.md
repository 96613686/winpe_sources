# _DataCollectorCreate_::_1_::dtor$7

- ea: `0x14001ce33`
- end: `0x14001ce3f`
- name: `_DataCollectorCreate_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004a74`

## pseudocode

```c
BOOL __fastcall DataCollectorCreate_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  return __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6AHPEBX_Z1_UnmapViewOfFile__YAH0_ZPEAX_tlx___tlx___utl__QEAA_XZ((const void **)(a2 + 184));
}

```

## disassembly

```asm
0x14001ce33  lea     rcx, [rdx+0B8h]
0x14001ce3a  jmp     ??1?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
```
