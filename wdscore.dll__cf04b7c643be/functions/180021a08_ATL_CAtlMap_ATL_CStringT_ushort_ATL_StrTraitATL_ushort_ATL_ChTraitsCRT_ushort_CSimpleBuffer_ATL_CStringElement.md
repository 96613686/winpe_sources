# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::RemoveNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode *,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode *)

- ea: `0x180021a08`
- end: `0x180021a5d`
- name: `?RemoveNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAXPEAVCNode@12@0@Z`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180022520`
- `0x1800294d8`

## callees

- `0x180020e70`
- `0x180021018`
- `0x180021a08`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::RemoveNode(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  if ( a3 )
    *(_QWORD *)(a3 + 32) = *(_QWORD *)(a2 + 32);
  else
    *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)(*(_DWORD *)(a2 + 40) % *(_DWORD *)(a1 + 16))) = *(_QWORD *)(a2 + 32);
  return ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::FreeNode(
           a1,
           a2);
}

```

## disassembly

```asm
0x180021a08  sub     rsp, 38h
0x180021a0c  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180021a15  mov     r9, rdx
0x180021a18  mov     r10, rcx
0x180021a1b  test    rdx, rdx
0x180021a1e  jnz     short loc_180021A2B
0x180021a20  mov     ecx, 80004005h; int
0x180021a25  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180021a2b  test    r8, r8
0x180021a2e  jnz     short loc_180021A46
0x180021a30  xor     edx, edx
0x180021a32  mov     eax, [r9+28h]
0x180021a36  div     dword ptr [rcx+10h]
0x180021a39  mov     rcx, [rcx]
0x180021a3c  mov     rax, [r9+20h]
0x180021a40  mov     [rcx+rdx*8], rax
0x180021a44  jmp     short loc_180021A4E
0x180021a46  mov     rax, [rdx+20h]
0x180021a4a  mov     [r8+20h], rax
0x180021a4e  mov     rdx, r9
0x180021a51  mov     rcx, r10
0x180021a54  add     rsp, 38h
0x180021a58  jmp     ?FreeNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::FreeNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode *)
```
