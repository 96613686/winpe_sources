# _UpdateDevnode_::_1_::dtor$0

- ea: `0x1800150ce`
- end: `0x1800150da`
- name: `_UpdateDevnode_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800111e0`

## pseudocode

```c
void __fastcall UpdateDevnode_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)(a2 + 72));
}

```

## disassembly

```asm
0x1800150ce  lea     rcx, [rdx+48h]; this
0x1800150d5  jmp     ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
```
