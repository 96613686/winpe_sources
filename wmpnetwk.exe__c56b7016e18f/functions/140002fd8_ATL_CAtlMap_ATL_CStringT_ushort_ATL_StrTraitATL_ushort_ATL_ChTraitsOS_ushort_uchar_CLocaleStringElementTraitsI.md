# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,uchar,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<uchar>>::SetAt(ushort const *,uchar)

- ea: `0x140002fd8`
- end: `0x1400030e0`
- name: `?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@EV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@E@2@@ATL@@QEAAPEAU__POSITION@@PEBGE@Z`
- size: `264`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140004160`
- `0x140007388`
- `0x14002629c`

## callees

- `0x140002fd8`
- `0x140008e0c`
- `0x14000dfd8`
- `0x1400396dc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14000306a`
- `KERNEL32!CompareStringW` at `0x14000306a`
- `USER32!CharUpperW` at `0x140003011`
- `USER32!CharUpperW` at `0x140003011`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned char,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned char>>::SetAt(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3)
{
  unsigned int v5; // r14d
  WCHAR v6; // ax
  const WCHAR *v7; // rbx
  unsigned int v8; // r15d
  __int64 i; // rbx

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v5 = 0;
  v6 = *a2;
  if ( *a2 )
  {
    v7 = a2;
    do
    {
      v5 = (unsigned __int16)CharUpperW((LPWSTR)v6) + 33 * v5;
      v6 = *++v7;
    }
    while ( *v7 );
  }
  v8 = v5 % *(_DWORD *)(a1 + 16);
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v5 % *(_DWORD *)(a1 + 16))); i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 24) == v5 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, a2, -1) == 2 )
      {
        *(_BYTE *)(i + 8) = 0;
        return i;
      }
    }
  }
  if ( !*(_QWORD *)a1 )
  {
    LOBYTE(a3) = 1;
    if ( !(unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::InitHashTable(
                             a1,
                             *(unsigned int *)(a1 + 16),
                             a3) )
      ATL::AtlThrowImpl(-2147024882);
  }
  i = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned long,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned long>>::NewNode(
        a1,
        a2,
        v8,
        v5);
  *(_BYTE *)(i + 8) = 0;
  return i;
}

```

## disassembly

```asm
0x140002fd8  mov     [rsp+arg_10], rbx
0x140002fdd  mov     [rsp+arg_0], rcx
0x140002fe2  push    rsi
0x140002fe3  push    rdi
0x140002fe4  push    r12
0x140002fe6  push    r14
0x140002fe8  push    r15
0x140002fea  sub     rsp, 30h
0x140002fee  mov     rsi, rdx
0x140002ff1  mov     rdi, rcx
0x140002ff4  xor     r12d, r12d
0x140002ff7  test    rdx, rdx
0x140002ffa  jz      loc_14000308E
0x140003000  mov     r14d, r12d
0x140003003  movzx   eax, word ptr [rdx]
0x140003006  test    ax, ax
0x140003009  jz      short loc_14000302D
0x14000300b  mov     rbx, rdx
0x14000300e  movzx   ecx, ax; lpsz
0x140003011  call    cs:__imp_CharUpperW
0x140003017  movzx   ecx, ax
0x14000301a  imul    r14d, 21h ; '!'
0x14000301e  add     r14d, ecx
0x140003021  lea     rbx, [rbx+2]
0x140003025  movzx   eax, word ptr [rbx]
0x140003028  test    ax, ax
0x14000302b  jnz     short loc_14000300E
0x14000302d  xor     edx, edx
0x14000302f  mov     eax, r14d
0x140003032  div     dword ptr [rdi+10h]
0x140003035  mov     r15d, edx
0x140003038  mov     rbx, [rdi]
0x14000303b  test    rbx, rbx
0x14000303e  jz      short loc_14000309F
0x140003040  mov     rbx, [rbx+rdx*8]
0x140003044  test    rbx, rbx
0x140003047  jz      short loc_14000309F
0x140003049  cmp     [rbx+18h], r14d
0x14000304d  jnz     short loc_140003099
0x14000304f  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x140003057  mov     [rsp+58h+lpString2], rsi; lpString2
0x14000305c  or      r9d, 0FFFFFFFFh; cchCount1
0x140003060  mov     r8, [rbx]; lpString1
0x140003063  lea     edx, [r9+2]; dwCmpFlags
0x140003067  lea     ecx, [rdx+7Eh]; Locale
0x14000306a  call    cs:__imp_CompareStringW
0x140003070  cmp     eax, 2
0x140003073  jnz     short loc_140003099
0x140003075  mov     [rbx+8], r12b
0x140003079  mov     rax, rbx
0x14000307c  mov     rbx, [rsp+58h+arg_10]
0x140003081  add     rsp, 30h
0x140003085  pop     r15
0x140003087  pop     r14
0x140003089  pop     r12
0x14000308b  pop     rdi
0x14000308c  pop     rsi
0x14000308d  retn
0x14000308e  mov     ecx, 80004005h; int
0x140003093  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140003099  mov     rbx, [rbx+10h]
0x14000309d  jmp     short loc_140003044
0x14000309f  cmp     [rdi], r12
0x1400030a2  jz      short loc_1400030C3
0x1400030a4  mov     r9d, r14d
0x1400030a7  mov     r8d, r15d
0x1400030aa  mov     rdx, rsi
0x1400030ad  mov     rcx, rdi
0x1400030b0  call    ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@K@2@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ulong,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ulong>>::NewNode(ushort const *,uint,uint)
0x1400030b5  mov     rbx, rax
0x1400030b8  mov     [rsp+58h+arg_8], rax
0x1400030bd  mov     [rax+8], r12b
0x1400030c1  jmp     short loc_140003079
0x1400030c3  mov     r8b, 1
0x1400030c6  mov     edx, [rdi+10h]
0x1400030c9  mov     rcx, rdi
0x1400030cc  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::InitHashTable(uint,bool)
0x1400030d1  test    al, al
0x1400030d3  jnz     short loc_1400030A4
0x1400030d5  mov     ecx, 8007000Eh; int
0x1400030da  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
