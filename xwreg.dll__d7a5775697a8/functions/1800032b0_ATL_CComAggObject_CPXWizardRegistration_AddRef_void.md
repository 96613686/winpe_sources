# ATL::CComAggObject<CPXWizardRegistration>::AddRef(void)

- ea: `0x1800032b0`
- end: `0x1800032b9`
- name: `?AddRef@?$CComAggObject@VCPXWizardRegistration@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180005e2c`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CPXWizardRegistration>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x1800032b0  add     rcx, 8; volatile int *
0x1800032b4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
