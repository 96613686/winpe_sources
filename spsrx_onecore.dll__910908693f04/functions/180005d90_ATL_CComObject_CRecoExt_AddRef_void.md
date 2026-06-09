# ATL::CComObject<CRecoExt>::AddRef(void)

- ea: `0x180005d90`
- end: `0x180005d99`
- name: `?AddRef@?$CComObject@VCRecoExt@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800032b0`
- `0x1800032c0`
- `0x1800032d0`
- `0x1800032e0`
- `0x1800032f0`
- `0x180003300`
- `0x180003310`

## callees

- `0x180002f3c`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CRecoExt>::AddRef(__int64 a1)
{
  return ATL::CComMultiThreadModel::SafeIncrementReference((int *)(a1 + 64));
}

```

## disassembly

```asm
0x180005d90  add     rcx, 40h ; '@'; int *
0x180005d94  jmp     ?SafeIncrementReference@CComMultiThreadModel@ATL@@SAKPEAJ@Z; ATL::CComMultiThreadModel::SafeIncrementReference(long *)
```
