# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)

- ea: `0x180004838`
- end: `0x180004856`
- name: `??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005130`
- `0x18000592c`
- `0x180005cf4`
- `0x18000750c`
- `0x180009590`

## callees

- `0x1800047f8`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        __int64 a1)
{
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(a1, &ATL::g_strmgr);
  return a1;
}

```

## disassembly

```asm
0x180004838  push    rbx
0x18000483a  sub     rsp, 20h
0x18000483e  mov     rbx, rcx
0x180004841  lea     rdx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004848  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18000484d  mov     rax, rbx
0x180004850  add     rsp, 20h
0x180004854  pop     rbx
0x180004855  retn
```
