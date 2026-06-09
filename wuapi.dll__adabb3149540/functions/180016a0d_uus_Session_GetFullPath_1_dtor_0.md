# _uus::Session::GetFullPath_::_1_::dtor$0

- ea: `0x180016a0d`
- end: `0x180016a19`
- name: `_uus::Session::GetFullPath_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000634c`

## pseudocode

```c
void __fastcall uus::Session::GetFullPath_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::filesystem::path::~path((std::filesystem::path *)(a2 + 112));
}

```

## disassembly

```asm
0x180016a0d  lea     rcx, [rdx+70h]; this
0x180016a14  jmp     ??1path@filesystem@std@@QEAA@XZ; std::filesystem::path::~path(void)
```
