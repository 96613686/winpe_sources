# _DataCollectorCreate_::_1_::dtor$1

- ea: `0x14001cdc7`
- end: `0x14001cdd3`
- name: `_DataCollectorCreate_::_1_::dtor$1`
- size: `12`
- prototype: `BOOL __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140004a74`

## pseudocode

```c
BOOL __fastcall DataCollectorCreate_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return __1__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6AHPEBX_Z1_UnmapViewOfFile__YAH0_ZPEAX_tlx___tlx___utl__QEAA_XZ((const void **)(a2 + 168));
}

```

## disassembly

```asm
0x14001cdc7  lea     rcx, [rdx+0A8h]
0x14001cdce  jmp     ??1?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6AHPEBX@Z1?UnmapViewOfFile@@YAH0@ZPEAX@tlx@@@tlx@@@utl@@QEAA@XZ
```
