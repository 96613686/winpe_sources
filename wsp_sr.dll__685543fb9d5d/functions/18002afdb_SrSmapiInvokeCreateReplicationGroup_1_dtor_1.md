# _SrSmapiInvokeCreateReplicationGroup_::_1_::dtor$1

- ea: `0x18002afdb`
- end: `0x18002afe7`
- name: `_SrSmapiInvokeCreateReplicationGroup_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a70`

## pseudocode

```c
void __fastcall SrSmapiInvokeCreateReplicationGroup_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(a2 + 200);
}

```

## disassembly

```asm
0x18002afdb  lea     rcx, [rdx+0C8h]
0x18002afe2  jmp     ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
```
