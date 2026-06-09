# _SrSmapiDeleteReplicationGroup_::_1_::dtor$0

- ea: `0x18002a42a`
- end: `0x18002a436`
- name: `_SrSmapiDeleteReplicationGroup_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a5c`

## pseudocode

```c
void __fastcall SrSmapiDeleteReplicationGroup_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWMIContext::~CWMIContext((CWMIContext *)(a2 + 144));
}

```

## disassembly

```asm
0x18002a42a  lea     rcx, [rdx+90h]; this
0x18002a431  jmp     ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
```
