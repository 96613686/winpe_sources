# _LOG_WRITER::UpdateConfigHelper_::_1_::dtor$1

- ea: `0x18000f00a`
- end: `0x18000f016`
- name: `_LOG_WRITER::UpdateConfigHelper_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, registry_config, installer_update`

## callees

- `0x180001048`

## pseudocode

```c
void __fastcall LOG_WRITER::UpdateConfigHelper_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 88));
}

```

## disassembly

```asm
0x18000f00a  mov     rcx, [rdx+58h]; Block
0x18000f011  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
