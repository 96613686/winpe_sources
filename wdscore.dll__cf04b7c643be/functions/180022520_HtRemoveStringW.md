# HtRemoveStringW

- ea: `0x180022520`
- end: `0x1800225dc`
- name: `HtRemoveStringW`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180006770`

## callees

- `0x180020bbc`
- `0x1800210ec`
- `0x1800214d8`
- `0x180021930`
- `0x180021a08`
- `0x180022520`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HtRemoveStringW(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 Node; // rax
  unsigned int v5; // ebx
  _QWORD v6[2]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v7; // [rsp+40h] [rbp-18h] BYREF
  int v8; // [rsp+60h] [rbp+8h] BYREF
  int v9; // [rsp+70h] [rbp+18h] BYREF
  __int64 v10; // [rsp+78h] [rbp+20h] BYREF

  v6[1] = -2;
  if ( !a1 )
    return 0;
  if ( !a2 )
    return 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v10);
  try
  {
    if ( !*(_DWORD *)(a1 + 80) )
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v10);
    v9 = 0;
    v8 = 0;
    v6[0] = 0;
    Node = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::GetNode(
             (int)a1 + 8,
             v10,
             (unsigned int)&v9,
             (unsigned int)&v8,
             (__int64)v6);
    if ( Node )
    {
      ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,ATL::CElementTraits<CSimpleBuffer>>::RemoveNode(
        a1 + 8,
        Node,
        v6[0]);
      v5 = 1;
    }
    else
    {
      v5 = 0;
    }
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    result = v5;
  }
  catch ( ATL::CAtlException v7 )
  {
    ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180022520  push    rbx
0x180022522  sub     rsp, 50h
0x180022526  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x18002252f  mov     rbx, rcx
0x180022532  test    rcx, rcx
0x180022535  jz      short loc_180022567
0x180022537  test    rdx, rdx
0x18002253a  jz      short loc_180022567
0x18002253c  lea     rcx, [rsp+58h+arg_18]
0x180022541  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180022546  nop
0x180022547  cmp     dword ptr [rbx+50h], 0
0x18002254b  jnz     short loc_180022570
0x18002254d  lea     rcx, [rsp+58h+arg_18]
0x180022552  call    ?MakeLower@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x180022557  jmp     short loc_180022570
0x180022559  mov     rcx, [rsp+58h+arg_18]
0x18002255e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180022562  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180022567  xor     eax, eax
0x180022569  add     rsp, 50h
0x18002256d  pop     rbx
0x18002256e  retn
0x180022570  mov     [rsp+58h+arg_10], 0
0x180022578  mov     [rsp+58h+arg_0], 0
0x180022580  mov     [rsp+58h+var_28], 0
0x180022589  lea     rax, [rsp+58h+var_28]
0x18002258e  mov     [rsp+58h+var_38], rax
0x180022593  lea     r9, [rsp+58h+arg_0]
0x180022598  lea     r8, [rsp+58h+arg_10]
0x18002259d  mov     rdx, [rsp+58h+arg_18]
0x1800225a2  lea     rcx, [rbx+8]
0x1800225a6  call    ?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode * &)
0x1800225ab  test    rax, rax
0x1800225ae  jnz     short loc_1800225B4
0x1800225b0  xor     ebx, ebx
0x1800225b2  jmp     short loc_1800225CA
0x1800225b4  mov     r8, [rsp+58h+var_28]
0x1800225b9  mov     rdx, rax
0x1800225bc  lea     rcx, [rbx+8]
0x1800225c0  call    ?RemoveNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCSimpleBuffer@@V?$CStringElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@V?$CElementTraits@VCSimpleBuffer@@@2@@ATL@@AEAAXPEAVCNode@12@0@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::RemoveNode(ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode *,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CSimpleBuffer,ATL::CStringElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,ATL::CElementTraits<CSimpleBuffer>>::CNode *)
0x1800225c5  mov     ebx, 1
0x1800225ca  mov     rcx, [rsp+58h+arg_18]
0x1800225cf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800225d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800225d8  mov     eax, ebx
0x1800225da  jmp     short loc_180022569
```
