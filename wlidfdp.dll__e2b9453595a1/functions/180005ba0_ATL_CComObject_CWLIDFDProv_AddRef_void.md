# ATL::CComObject<CWLIDFDProv>::AddRef(void)

- ea: `0x180005ba0`
- end: `0x180005ba9`
- name: `?AddRef@?$CComObject@VCWLIDFDProv@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800086a4`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CWLIDFDProv>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x180005ba0  add     rcx, 8; volatile int *
0x180005ba4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
