# _mi::MiApplication::CreateSession_0__::_1_::dtor$0

- ea: `0x18002a465`
- end: `0x18002a471`
- name: `_mi::MiApplication::CreateSession_0__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005a70`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_0__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(a2 + 48);
}

```

## disassembly

```asm
0x18002a465  lea     rcx, [rdx+30h]
0x18002a46c  jmp     ??1?$shared_ptr@$$CBVMiSession@mi@@@std@@QEAA@XZ; std::shared_ptr<mi::MiSession const>::~shared_ptr<mi::MiSession const>(void)
```
