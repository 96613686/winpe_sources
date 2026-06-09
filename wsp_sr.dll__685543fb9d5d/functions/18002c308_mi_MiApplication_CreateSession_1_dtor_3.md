# _mi::MiApplication::CreateSession_::_1_::dtor$3

- ea: `0x18002c308`
- end: `0x18002c314`
- name: `_mi::MiApplication::CreateSession_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180028160`

## pseudocode

```c
void __fastcall mi::MiApplication::CreateSession_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  mi::MiDestinationOptions::~MiDestinationOptions((mi::MiDestinationOptions *)(a2 + 64));
}

```

## disassembly

```asm
0x18002c308  lea     rcx, [rdx+40h]; this
0x18002c30f  jmp     ??1MiDestinationOptions@mi@@QEAA@XZ; mi::MiDestinationOptions::~MiDestinationOptions(void)
```
