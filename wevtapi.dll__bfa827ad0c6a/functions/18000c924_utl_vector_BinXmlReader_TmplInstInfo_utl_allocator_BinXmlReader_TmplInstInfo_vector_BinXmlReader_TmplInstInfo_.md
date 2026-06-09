# utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::~vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(void)

- ea: `0x18000c924`
- end: `0x18000c929`
- name: `??1?$vector@UTmplInstInfo@BinXmlReader@@V?$allocator@UTmplInstInfo@BinXmlReader@@@utl@@@utl@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800390b8`
- `0x1800390d0`
- `0x1800390f0`
- `0x180039480`
- `0x1800394a0`
- `0x180039636`
- `0x180039eaa`
- `0x18003a0c3`
- `0x18003a773`
- `0x18003ad7c`
- `0x18003af68`

## callees

- `0x18000a4b4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall utl::vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>::~vector<BinXmlReader::TmplInstInfo,utl::allocator<BinXmlReader::TmplInstInfo>>(
        __int64 a1)
{
  return utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(a1);
}

```

## disassembly

```asm
0x18000c924  jmp     ?_Uninit@?$vector@Utag_EvtRpcVariant@@V?$allocator@Utag_EvtRpcVariant@@@utl@@@utl@@AEAAXXZ; utl::vector<tag_EvtRpcVariant,utl::allocator<tag_EvtRpcVariant>>::_Uninit(void)
```
