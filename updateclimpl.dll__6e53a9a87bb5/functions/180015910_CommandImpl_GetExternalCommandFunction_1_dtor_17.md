# _CommandImpl::GetExternalCommandFunction_::_1_::dtor$17

- ea: `0x180015910`
- end: `0x18001591c`
- name: `_CommandImpl::GetExternalCommandFunction_::_1_::dtor$17`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c1e4`

## pseudocode

```c
void __fastcall CommandImpl::GetExternalCommandFunction_::_1_::dtor_17(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path(a2 + 96);
}

```

## disassembly

```asm
0x180015910  lea     rcx, [rdx+60h]; this
0x180015917  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
