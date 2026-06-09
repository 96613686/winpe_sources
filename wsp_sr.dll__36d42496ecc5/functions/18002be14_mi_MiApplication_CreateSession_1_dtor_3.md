# _mi::MiApplication::CreateSession_::_1_::dtor$3

- ea: `0x18002be14`
- end: `0x18002be20`
- name: `_mi::MiApplication::CreateSession_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180027db0`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  mi::MiDestinationOptions::~MiDestinationOptions((mi::MiDestinationOptions *)(a2 + 64));
}

```

## disassembly

```asm
0x18002be14  lea     rcx, [rdx+40h]; this
0x18002be1b  jmp     ??1MiDestinationOptions@mi@@QEAA@XZ; mi::MiDestinationOptions::~MiDestinationOptions(void)
```
