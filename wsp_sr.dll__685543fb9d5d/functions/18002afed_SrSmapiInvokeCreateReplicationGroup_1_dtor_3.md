# _SrSmapiInvokeCreateReplicationGroup_::_1_::dtor$3

- ea: `0x18002afed`
- end: `0x18002aff9`
- name: `_SrSmapiInvokeCreateReplicationGroup_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a70`

## pseudocode

```c
void __fastcall SrSmapiInvokeCreateReplicationGroup_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(a2 + 184);
}

```

## disassembly

```asm
0x18002afed  lea     rcx, [rdx+0B8h]
0x18002aff4  jmp     ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
```
