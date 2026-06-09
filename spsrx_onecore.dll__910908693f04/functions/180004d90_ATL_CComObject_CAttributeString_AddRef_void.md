# ATL::CComObject<CAttributeString>::AddRef(void)

- ea: `0x180004d90`
- end: `0x180004d99`
- name: `?AddRef@?$CComObject@VCAttributeString@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f3c`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CAttributeString>::AddRef(__int64 a1)
{
  return ATL::CComMultiThreadModel::SafeIncrementReference((int *)(a1 + 8));
}

```

## disassembly

```asm
0x180004d90  add     rcx, 8; int *
0x180004d94  jmp     ?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeIncrementReference(long *)
```
