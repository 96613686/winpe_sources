# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CdsValue::Value,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<CdsValue::Value>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CdsValue::Value,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<CdsValue::Value>>::CNode * &)

- ea: `0x14002e110`
- end: `0x14002e1e3`
- name: `?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@W4Value@CdsValue@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@W4Value@CdsValue@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z`
- size: `211`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400995b8`

## callees

- `0x14002e110`
- `0x1400396dc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002e1d0`
- `KERNEL32!CompareStringW` at `0x14002e1d0`
- `USER32!CharUpperW` at `0x14002e13d`
- `USER32!CharUpperW` at `0x14002e13d`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,enum CdsValue::Value,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<enum CdsValue::Value>>::GetNode(
        __int64 a1,
        const WCHAR *a2,
        unsigned int *a3,
        unsigned int *a4,
        _QWORD *a5)
{
  WCHAR v8; // ax
  unsigned int v9; // ebx
  WCHAR *v10; // rsi
  int v11; // ecx
  unsigned int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v16; // rsi
  __int64 v17; // rbx

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v8 = *a2;
  v9 = 0;
  if ( *a2 )
  {
    v10 = (WCHAR *)a2;
    do
    {
      ++v10;
      v11 = (unsigned __int16)CharUpperW((LPWSTR)v8);
      v8 = *v10;
      v9 = v11 + 33 * v9;
    }
    while ( *v10 );
  }
  HIDWORD(v14) = 0;
  *a4 = v9;
  v12 = v9;
  v13 = CdsValues::s_cdsNameToAtomMap;
  LODWORD(v14) = v12 % dword_1400C03F0;
  *a3 = v12 % dword_1400C03F0;
  if ( v13 )
  {
    v16 = 0;
    v17 = *(_QWORD *)(v13 + 8 * v14);
    *a5 = 0;
    while ( v17 )
    {
      if ( *(_DWORD *)(v17 + 24) == *a4 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)v17, -1, a2, -1) == 2 )
      {
        *a5 = v16;
        return v17;
      }
      v16 = v17;
      v17 = *(_QWORD *)(v17 + 16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002e110  push    rbx
0x14002e112  push    rbp
0x14002e113  push    rsi
0x14002e114  push    rdi
0x14002e115  push    r14
0x14002e117  push    r15
0x14002e119  sub     rsp, 38h
0x14002e11d  xor     ebp, ebp
0x14002e11f  mov     r15, r9
0x14002e122  mov     r14, r8
0x14002e125  mov     rdi, rdx
0x14002e128  test    rdx, rdx
0x14002e12b  jz      short loc_14002E182
0x14002e12d  movzx   eax, word ptr [rdx]
0x14002e130  mov     ebx, ebp
0x14002e132  test    ax, ax
0x14002e135  jz      short loc_14002E157
0x14002e137  mov     rsi, rdx
0x14002e13a  movzx   ecx, ax; lpsz
0x14002e13d  call    cs:__imp_CharUpperW
0x14002e143  imul    ebx, 21h ; '!'
0x14002e146  lea     rsi, [rsi+2]
0x14002e14a  movzx   ecx, ax
0x14002e14d  movzx   eax, word ptr [rsi]
0x14002e150  add     ebx, ecx
0x14002e152  test    ax, ax
0x14002e155  jnz     short loc_14002E13A
0x14002e157  xor     edx, edx
0x14002e159  mov     [r15], ebx
0x14002e15c  mov     eax, ebx
0x14002e15e  mov     rbx, qword ptr cs:?s_cdsNameToAtomMap@CdsValues@@0V?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@W4Value@CdsValue@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@W4Value@CdsValue@@@2@@ATL@@A; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CdsValue::Value,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<CdsValue::Value>> CdsValues::s_cdsNameToAtomMap
0x14002e165  div     cs:dword_1400C03F0
0x14002e16b  mov     [r14], edx
0x14002e16e  test    rbx, rbx
0x14002e171  jnz     short loc_14002E18D
0x14002e173  xor     eax, eax
0x14002e175  add     rsp, 38h
0x14002e179  pop     r15
0x14002e17b  pop     r14
0x14002e17d  pop     rdi
0x14002e17e  pop     rsi
0x14002e17f  pop     rbp
0x14002e180  pop     rbx
0x14002e181  retn
0x14002e182  mov     ecx, 80004005h; int
0x14002e187  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002e18d  mov     r14, [rsp+68h+arg_20]
0x14002e195  mov     rsi, rbp
0x14002e198  mov     rbx, [rbx+rdx*8]
0x14002e19c  mov     [r14], rbp
0x14002e19f  test    rbx, rbx
0x14002e1a2  jz      short loc_14002E173
0x14002e1a4  mov     eax, [r15]
0x14002e1a7  cmp     [rbx+18h], eax
0x14002e1aa  jz      short loc_14002E1B5
0x14002e1ac  mov     rsi, rbx
0x14002e1af  mov     rbx, [rbx+10h]
0x14002e1b3  jmp     short loc_14002E19F
0x14002e1b5  mov     r8, [rbx]; lpString1
0x14002e1b8  or      r9d, 0FFFFFFFFh; cchCount1
0x14002e1bc  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x14002e1c4  mov     [rsp+68h+lpString2], rdi; lpString2
0x14002e1c9  lea     edx, [r9+2]; dwCmpFlags
0x14002e1cd  lea     ecx, [rdx+7Eh]; Locale
0x14002e1d0  call    cs:__imp_CompareStringW
0x14002e1d6  cmp     eax, 2
0x14002e1d9  jnz     short loc_14002E1AC
0x14002e1db  mov     [r14], rsi
0x14002e1de  mov     rax, rbx
0x14002e1e1  jmp     short loc_14002E175
```
