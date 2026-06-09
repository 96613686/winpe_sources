# _SrSmapiCreateReplica_::_1_::dtor$0

- ea: `0x18002a88b`
- end: `0x18002a897`
- name: `_SrSmapiCreateReplica_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a9c`

## pseudocode

```c
void __fastcall SrSmapiCreateReplica_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWMIContext::~CWMIContext((CWMIContext *)(a2 + 304));
}

```

## disassembly

```asm
0x18002a88b  lea     rcx, [rdx+130h]; this
0x18002a892  jmp     ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
```
