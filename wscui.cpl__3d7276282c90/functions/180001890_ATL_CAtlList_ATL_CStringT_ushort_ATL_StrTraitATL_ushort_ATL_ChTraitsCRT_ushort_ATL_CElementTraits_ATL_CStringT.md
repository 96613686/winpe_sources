# ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)

- ea: `0x180001890`
- end: `0x180001910`
- name: `?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180001890`
- `0x18000b330`

## callees

- `0x180001890`
- `0x180001b90`
- `0x1800044f8`
- `0x180004fe8`

## pseudocode

```c
void __fastcall ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(
        __int64 a1)
{
  _QWORD *v2; // rdi
  ATL::CAtlPlex *v4; // rcx

  while ( *(_QWORD *)(a1 + 16) )
  {
    v2 = *(_QWORD **)a1;
    if ( !*(_QWORD *)a1 )
      ATL::AtlThrowImpl(-2147467259);
    *(_QWORD *)a1 = *v2;
    ATL::CStringData::Release((ATL::CStringData *)(v2[2] - 24LL));
    *v2 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = v2;
    if ( (*(_QWORD *)(a1 + 16))-- == 1 )
      ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(a1);
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v4 = *(ATL::CAtlPlex **)(a1 + 24);
  if ( v4 )
  {
    ATL::CAtlPlex::FreeDataChain(v4);
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x180001890  mov     [rsp+arg_8], rbx
0x180001895  push    rdi
0x180001896  sub     rsp, 20h
0x18000189a  mov     rbx, rcx
0x18000189d  cmp     qword ptr [rbx+10h], 0
0x1800018a2  jbe     short loc_1800018E6
0x1800018a4  mov     rdi, [rbx]
0x1800018a7  test    rdi, rdi
0x1800018aa  jz      short loc_1800018DB
0x1800018ac  mov     rax, [rdi]
0x1800018af  mov     [rbx], rax
0x1800018b2  mov     rcx, [rdi+10h]
0x1800018b6  sub     rcx, 18h; this
0x1800018ba  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800018bf  mov     rax, [rbx+20h]
0x1800018c3  mov     [rdi], rax
0x1800018c6  mov     [rbx+20h], rdi
0x1800018ca  sub     qword ptr [rbx+10h], 1
0x1800018cf  jnz     short loc_18000189D
0x1800018d1  mov     rcx, rbx
0x1800018d4  call    ?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x1800018d9  jmp     short loc_18000189D
0x1800018db  mov     ecx, 80004005h; int
0x1800018e0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800018e6  xor     edi, edi
0x1800018e8  mov     [rbx], rdi
0x1800018eb  mov     [rbx+8], rdi
0x1800018ef  mov     [rbx+20h], rdi
0x1800018f3  mov     rcx, [rbx+18h]; this
0x1800018f7  test    rcx, rcx
0x1800018fa  jz      short loc_180001905
0x1800018fc  call    ?FreeDataChain@CAtlPlex@ATL@@QEAAXXZ; ATL::CAtlPlex::FreeDataChain(void)
0x180001901  mov     [rbx+18h], rdi
0x180001905  mov     rbx, [rsp+28h+arg_8]
0x18000190a  add     rsp, 20h
0x18000190e  pop     rdi
0x18000190f  retn
```
