# ATL::CComAggObject<CRecoExt>::AddRef(void)

- ea: `0x180001c20`
- end: `0x180001c29`
- name: `?AddRef@?$CComAggObject@VCRecoExt@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001b80`

## callees

- `0x180002f48`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CRecoExt>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x180001c20  add     rcx, 8; volatile int *
0x180001c24  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
