# _SrSmapiDeleteReplicationGroup_::_1_::dtor$0

- ea: `0x18002a8f7`
- end: `0x18002a903`
- name: `_SrSmapiDeleteReplicationGroup_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a9c`

## pseudocode

```c
void __fastcall SrSmapiDeleteReplicationGroup_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWMIContext::~CWMIContext((CWMIContext *)(a2 + 144));
}

```

## disassembly

```asm
0x18002a8f7  lea     rcx, [rdx+90h]; this
0x18002a8fe  jmp     ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
```
