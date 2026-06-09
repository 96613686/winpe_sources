# _SrSmapiCreateReplicationGroup_::_1_::dtor$0

- ea: `0x18002aecd`
- end: `0x18002aed9`
- name: `_SrSmapiCreateReplicationGroup_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005a9c`

## pseudocode

```c
void __fastcall SrSmapiCreateReplicationGroup_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CWMIContext::~CWMIContext((CWMIContext *)(a2 + 288));
}

```

## disassembly

```asm
0x18002aecd  lea     rcx, [rdx+120h]; this
0x18002aed4  jmp     ??1CWMIContext@@UEAA@XZ; CWMIContext::~CWMIContext(void)
```
