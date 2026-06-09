# _SrSmapiCreateReplicationRelationship_::_1_::dtor$0

- ea: `0x18002af27`
- end: `0x18002af33`
- name: `_SrSmapiCreateReplicationRelationship_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a9c`

## pseudocode

```c
void __fastcall SrSmapiCreateReplicationRelationship_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWMIContext::~CWMIContext((CWMIContext *)(a2 + 496));
}

```

## disassembly

```asm
0x18002af27  lea     rcx, [rdx+1F0h]; this
0x18002af2e  jmp     ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
```
