# _CommandImpl::GetExternalCommandFunction_::_1_::dtor$2

- ea: `0x1800158da`
- end: `0x1800158e6`
- name: `_CommandImpl::GetExternalCommandFunction_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000c1e4`

## pseudocode

```c
void __fastcall CommandImpl::GetExternalCommandFunction_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path(a2 + 144);
}

```

## disassembly

```asm
0x1800158da  lea     rcx, [rdx+90h]; this
0x1800158e1  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
