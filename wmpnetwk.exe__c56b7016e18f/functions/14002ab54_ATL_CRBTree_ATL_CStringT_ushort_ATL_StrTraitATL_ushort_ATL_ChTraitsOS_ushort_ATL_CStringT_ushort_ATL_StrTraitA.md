# ATL::CRBTree<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::Find(ushort const *)

- ea: `0x14002ab54`
- end: `0x14002ac53`
- name: `?Find@?$CRBTree@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@IEBAPEAVCNode@12@PEBG@Z`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400786b0`

## callees

- `0x14002ab54`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002ab90`
- `KERNEL32!CompareStringW` at `0x14002abe2`
- `KERNEL32!CompareStringW` at `0x14002ab90`
- `KERNEL32!CompareStringW` at `0x14002abe2`

## pseudocode

```c
__int64 __fastcall ATL::CRBTree<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Find(
        __int64 *a1,
        const WCHAR *a2)
{
  __int64 v2; // rbx
  __int64 v5; // rdi
  int v6; // eax
  __int64 v7; // rbx
  __int64 v9; // rax
  __int64 v10; // rcx
  char v11; // cl

  v2 = *a1;
  v5 = 0;
  while ( v2 != a1[5] )
  {
    if ( v5 )
      goto LABEL_7;
    v6 = CompareStringW(0x7Fu, 1u, a2, -1, *(PCNZWCH *)v2, -1);
    if ( v6 == 1 )
    {
      v2 = *(_QWORD *)(v2 + 24);
    }
    else if ( v6 == 3 )
    {
      v2 = *(_QWORD *)(v2 + 32);
    }
    else
    {
      v5 = v2;
    }
  }
  if ( !v5 )
    return 0;
  while ( 1 )
  {
LABEL_7:
    v7 = *(_QWORD *)(v5 + 24);
    if ( v7 == a1[5] )
    {
      v9 = *(_QWORD *)(v5 + 40);
      v10 = v5;
      while ( v9 != a1[5] )
      {
        if ( v10 != *(_QWORD *)(v9 + 24) )
        {
          v11 = 0;
          goto LABEL_17;
        }
        v10 = v9;
        v9 = *(_QWORD *)(v9 + 40);
      }
      v11 = 1;
LABEL_17:
      v7 = 0;
      if ( !v11 )
        v7 = v9;
    }
    else if ( v7 )
    {
      while ( *(_QWORD *)(v7 + 32) != a1[5] )
        v7 = *(_QWORD *)(v7 + 32);
    }
    if ( !v7 || CompareStringW(0x7Fu, 1u, a2, -1, *(PCNZWCH *)v7, -1) != 2 )
      return v5;
    v5 = v7;
  }
}

```

## disassembly

```asm
0x14002ab54  push    rbx
0x14002ab56  push    rbp
0x14002ab57  push    rsi
0x14002ab58  push    rdi
0x14002ab59  sub     rsp, 38h
0x14002ab5d  mov     rbx, [rcx]
0x14002ab60  mov     rbp, rdx
0x14002ab63  mov     rsi, rcx
0x14002ab66  xor     edi, edi
0x14002ab68  cmp     rbx, [rsi+28h]
0x14002ab6c  jz      short loc_14002ABA7
0x14002ab6e  test    rdi, rdi
0x14002ab71  jnz     short loc_14002ABB0
0x14002ab73  mov     rax, [rbx]
0x14002ab76  lea     edx, [rdi+1]; dwCmpFlags
0x14002ab79  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14002ab81  lea     ecx, [rdi+7Fh]; Locale
0x14002ab84  or      r9d, 0FFFFFFFFh; cchCount1
0x14002ab88  mov     [rsp+58h+lpString2], rax; lpString2
0x14002ab8d  mov     r8, rbp; lpString1
0x14002ab90  call    cs:__imp_CompareStringW
0x14002ab96  mov     ecx, eax
0x14002ab98  sub     ecx, 1
0x14002ab9b  jnz     loc_14002AC39
0x14002aba1  mov     rbx, [rbx+18h]
0x14002aba5  jmp     short loc_14002AB68
0x14002aba7  test    rdi, rdi
0x14002abaa  jz      loc_14002AC4F
0x14002abb0  mov     rbx, [rdi+18h]
0x14002abb4  cmp     rbx, [rsi+28h]
0x14002abb8  jz      short loc_14002ABFE
0x14002abba  test    rbx, rbx
0x14002abbd  jnz     short loc_14002AC2A
0x14002abbf  test    rbx, rbx
0x14002abc2  jz      short loc_14002ABF2
0x14002abc4  mov     rax, [rbx]
0x14002abc7  or      r9d, 0FFFFFFFFh; cchCount1
0x14002abcb  mov     [rsp+58h+cchCount2], 0FFFFFFFFh; cchCount2
0x14002abd3  mov     r8, rbp; lpString1
0x14002abd6  mov     [rsp+58h+lpString2], rax; lpString2
0x14002abdb  lea     edx, [r9+2]; dwCmpFlags
0x14002abdf  lea     ecx, [rdx+7Eh]; Locale
0x14002abe2  call    cs:__imp_CompareStringW
0x14002abe8  cmp     eax, 2
0x14002abeb  jnz     short loc_14002ABF2
0x14002abed  mov     rdi, rbx
0x14002abf0  jmp     short loc_14002ABB0
0x14002abf2  mov     rax, rdi
0x14002abf5  add     rsp, 38h
0x14002abf9  pop     rdi
0x14002abfa  pop     rsi
0x14002abfb  pop     rbp
0x14002abfc  pop     rbx
0x14002abfd  retn
0x14002abfe  mov     rax, [rdi+28h]
0x14002ac02  mov     rcx, rdi
0x14002ac05  cmp     rax, [rsi+28h]
0x14002ac09  jz      short loc_14002AC26
0x14002ac0b  cmp     rcx, [rax+18h]
0x14002ac0f  jz      short loc_14002AC1D
0x14002ac11  xor     cl, cl
0x14002ac13  xor     ebx, ebx
0x14002ac15  test    cl, cl
0x14002ac17  cmovz   rbx, rax
0x14002ac1b  jmp     short loc_14002ABBF
0x14002ac1d  mov     rcx, rax
0x14002ac20  mov     rax, [rax+28h]
0x14002ac24  jmp     short loc_14002AC05
0x14002ac26  mov     cl, 1
0x14002ac28  jmp     short loc_14002AC13
0x14002ac2a  mov     rax, [rbx+20h]
0x14002ac2e  cmp     rax, [rsi+28h]
0x14002ac32  jz      short loc_14002ABBF
0x14002ac34  mov     rbx, rax
0x14002ac37  jmp     short loc_14002AC2A
0x14002ac39  cmp     ecx, 2
0x14002ac3c  jz      short loc_14002AC46
0x14002ac3e  mov     rdi, rbx
0x14002ac41  jmp     loc_14002AB68
0x14002ac46  mov     rbx, [rbx+20h]
0x14002ac4a  jmp     loc_14002AB68
0x14002ac4f  xor     eax, eax
0x14002ac51  jmp     short loc_14002ABF5
```
