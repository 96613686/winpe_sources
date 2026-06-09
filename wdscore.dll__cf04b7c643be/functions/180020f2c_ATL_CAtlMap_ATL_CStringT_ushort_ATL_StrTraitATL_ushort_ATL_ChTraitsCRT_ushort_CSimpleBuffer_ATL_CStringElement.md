# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CreateNode(ushort const *,uint,uint)

- ea: `0x180020f2c`
- end: `0x180020f7a`
- name: `?CreateNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z`
- size: `78`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180021a64`
- `0x1800223a4`

## callees

- `0x180020e70`
- `0x180020f2c`
- `0x180021294`
- `0x18002153c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::CreateNode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int v5; // esi

  v5 = a3;
  if ( !*(_QWORD *)a1 )
  {
    LOBYTE(a3) = 1;
    if ( !(unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::InitHashTable(
                             a1,
                             *(unsigned int *)(a1 + 16),
                             a3) )
      ATL::AtlThrowImpl(-2147024882);
  }
  return ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::NewNode(
           a1,
           a2,
           v5,
           a4);
}

```

## disassembly

```asm
0x180020f2c  push    rbx
0x180020f2e  push    rbp
0x180020f2f  push    rsi
0x180020f30  push    rdi
0x180020f31  sub     rsp, 28h
0x180020f35  cmp     qword ptr [rcx], 0
0x180020f39  mov     edi, r9d
0x180020f3c  mov     esi, r8d
0x180020f3f  mov     rbp, rdx
0x180020f42  mov     rbx, rcx
0x180020f45  jnz     short loc_180020F61
0x180020f47  mov     edx, [rcx+10h]
0x180020f4a  mov     r8b, 1
0x180020f4d  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::InitHashTable(uint,bool)
0x180020f52  test    al, al
0x180020f54  jnz     short loc_180020F61
0x180020f56  mov     ecx, 8007000Eh; int
0x180020f5b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020f61  mov     r9d, edi
0x180020f64  mov     r8d, esi
0x180020f67  mov     rdx, rbp
0x180020f6a  mov     rcx, rbx
0x180020f6d  add     rsp, 28h
0x180020f71  pop     rdi
0x180020f72  pop     rsi
0x180020f73  pop     rbp
0x180020f74  pop     rbx
0x180020f75  jmp     ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::NewNode(ushort const *,uint,uint)
```
