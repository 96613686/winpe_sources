# ATL::CComObject<CPreflistFolder>::AddRef(void)

- ea: `0x1800041f0`
- end: `0x1800041f9`
- name: `?AddRef@?$CComObject@VCPreflistFolder@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004200`
- `0x180004210`
- `0x180004220`
- `0x180004230`
- `0x180004240`
- `0x180004250`
- `0x180004260`
- `0x180004270`

## callees

- `0x18000b93c`

## pseudocode

```c
unsigned int __fastcall ATL::CComObject<CPreflistFolder>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 80));
}

```

## disassembly

```asm
0x1800041f0  add     rcx, 50h ; 'P'; volatile int *
0x1800041f4  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
