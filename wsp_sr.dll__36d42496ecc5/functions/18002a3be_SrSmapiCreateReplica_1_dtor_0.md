# _SrSmapiCreateReplica_::_1_::dtor$0

- ea: `0x18002a3be`
- end: `0x18002a3ca`
- name: `_SrSmapiCreateReplica_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a5c`

## pseudocode

```c
void __fastcall SrSmapiCreateReplica_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWMIContext::~CWMIContext((CWMIContext *)(a2 + 304));
}

```

## disassembly

```asm
0x18002a3be  lea     rcx, [rdx+130h]; this
0x18002a3c5  jmp     ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
```
