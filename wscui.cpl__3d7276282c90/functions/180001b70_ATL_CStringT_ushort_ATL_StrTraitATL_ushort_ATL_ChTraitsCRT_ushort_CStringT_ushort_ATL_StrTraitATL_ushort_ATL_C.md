# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x180001b70`
- end: `0x180001b7c`
- name: `??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `12`
- prototype: `void(void *)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac0a`
- `0x18000ac2e`
- `0x18000ac5a`
- `0x18000ac6c`
- `0x18000acfa`
- `0x18000ad0c`
- `0x18000ad1e`
- `0x18000ad30`
- `0x18000ad42`
- `0x18000ad54`
- `0x18000ad66`
- `0x18000aee4`
- `0x18000af10`
- `0x18000af3c`
- `0x18000af4e`
- `0x18000af60`

## callees

- `0x180001b90`

## pseudocode

```c
void __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        _QWORD *a1)
{
  ATL::CStringData::Release((ATL::CStringData *)(*a1 - 24LL));
}

```

## disassembly

```asm
0x180001b70  mov     rcx, [rcx]
0x180001b73  sub     rcx, 18h; this
0x180001b77  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
