# _SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$1_0

- ea: `0x18002ab6b`
- end: `0x18002ab77`
- name: `_SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor$1_0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a30`

## pseudocode

```c
void __fastcall SrSmapiInvokeCreateReplicationPartnership_::_1_::dtor_1_0(__int64 a1, __int64 a2)
{
  std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(a2 + 296);
}

```

## disassembly

```asm
0x18002ab6b  lea     rcx, [rdx+128h]
0x18002ab72  jmp     ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
```
