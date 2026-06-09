# _mi::MiApplication::CreateSession_0__::_1_::dtor$0

- ea: `0x180029fb5`
- end: `0x180029fc1`
- name: `_mi::MiApplication::CreateSession_0__::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a30`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_0__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(a2 + 48);
}

```

## disassembly

```asm
0x180029fb5  lea     rcx, [rdx+30h]
0x180029fbc  jmp     ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
```
