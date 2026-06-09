# _CommandImpl::RunCommand_::_1_::dtor$0

- ea: `0x180015880`
- end: `0x18001588c`
- name: `_CommandImpl::RunCommand_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000d1cc`

## pseudocode

```c
void __fastcall CommandImpl::RunCommand_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Telemetry4UpdateCli::RunCmd::~RunCmd((Telemetry4UpdateCli::RunCmd *)(a2 + 96));
}

```

## disassembly

```asm
0x180015880  lea     rcx, [rdx+60h]; this
0x180015887  jmp     ??1RunCmd@Telemetry4UpdateCli@@QEAA@XZ; Telemetry4UpdateCli::RunCmd::~RunCmd(void)
```
