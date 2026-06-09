# _CliMain::ProcessCliCommand_::_1_::dtor$1

- ea: `0x180015a66`
- end: `0x180015a72`
- name: `_CliMain::ProcessCliCommand_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008efc`

## pseudocode

```c
void __fastcall CliMain::ProcessCliCommand_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CommandImpl::~CommandImpl((CommandImpl *)(a2 + 40));
}

```

## disassembly

```asm
0x180015a66  lea     rcx, [rdx+28h]; this
0x180015a6d  jmp     ??1CommandImpl@@QEAA@XZ; CommandImpl::~CommandImpl(void)
```
