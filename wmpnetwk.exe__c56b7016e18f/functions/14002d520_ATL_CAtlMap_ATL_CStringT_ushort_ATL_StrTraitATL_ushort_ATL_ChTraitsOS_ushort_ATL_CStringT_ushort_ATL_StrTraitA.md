# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::SetAt(ushort const *,ushort const *)

- ea: `0x14002d520`
- end: `0x14002d6de`
- name: `?SetAt@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@QEAAPEAU__POSITION@@PEBG0@Z`
- size: `446`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400457ac`
- `0x140062960`
- `0x140062b78`
- `0x140062f88`

## callees

- `0x140007020`
- `0x140008e0c`
- `0x14000c780`
- `0x140015230`
- `0x140019590`
- `0x14002d520`
- `0x1400392b4`
- `0x1400396dc`
- `0x140046c32`
- `0x14009ad10`
- `0x14009ad1c`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002d5d1`
- `KERNEL32!CompareStringW` at `0x14002d5d1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d655`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002d655`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::SetAt(
        __int64 a1,
        const WCHAR *a2,
        char *a3)
{
  __int64 v6; // r8
  unsigned int v7; // r15d
  unsigned int v8; // ebx
  __int64 v9; // rdi
  __int64 v10; // rbx
  _QWORD *v11; // rsi
  _BYTE *v12; // r15
  unsigned __int64 v13; // r13
  __int64 v14; // r14
  unsigned __int64 v15; // rdx
  _BYTE *v16; // rcx
  unsigned int v18; // [rsp+78h] [rbp+20h]

  v7 = CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>::Hash(a2);
  v8 = v7 % *(_DWORD *)(a1 + 16);
  v18 = v8;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v7 % *(_DWORD *)(a1 + 16)));
    v10 = -1;
    while ( 1 )
    {
      if ( !v9 )
      {
        v8 = v18;
        goto LABEL_7;
      }
      if ( *(_DWORD *)(v9 + 24) == v7 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)v9, -1, a2, -1) == 2 )
        break;
      v9 = *(_QWORD *)(v9 + 16);
    }
    v11 = (_QWORD *)(v9 + 8);
    if ( !a3 )
      goto LABEL_20;
    do
      ++v10;
    while ( *(_WORD *)&a3[2 * v10] );
    if ( !(_DWORD)v10 )
    {
LABEL_20:
      ATL::CSimpleStringT<unsigned short,0>::Empty(v9 + 8);
      return v9;
    }
    v12 = (_BYTE *)*v11;
    v13 = *(unsigned int *)(*v11 - 16LL);
    if ( (int)((*(_DWORD *)(*v11 - 12LL) - v10) | (1 - *(_DWORD *)(*v11 - 8LL))) < 0 )
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(v9 + 8, (unsigned int)v10);
    v14 = 2LL * (int)v10;
    if ( !v14 )
      goto LABEL_22;
    v15 = (a3 - v12) >> 1;
    v16 = (_BYTE *)*v11;
    if ( v15 <= v13 )
    {
      if ( v16 )
      {
        v15 = (unsigned __int64)&v16[2 * v15];
        if ( v15 )
        {
          memmove_0(v16, (const void *)v15, 2LL * (int)v10);
LABEL_22:
          if ( (int)v10 < 0 || (int)v10 > *(_DWORD *)(*v11 - 12LL) )
            ATL::AtlThrowImpl(-2147024809);
          *(_DWORD *)(*v11 - 16LL) = v10;
          *(_WORD *)(v14 + *v11) = 0;
          return v9;
        }
      }
    }
    else if ( v16 )
    {
      memcpy_0(v16, a3, 2LL * (int)v10);
      goto LABEL_22;
    }
    *(_DWORD *)_o__errno(v16, v15, v6) = 22;
    invalid_parameter_noinfo();
    goto LABEL_22;
  }
LABEL_7:
  if ( !*(_QWORD *)a1 )
  {
    LOBYTE(v6) = 1;
    if ( !(unsigned __int8)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::InitHashTable(
                             a1,
                             *(unsigned int *)(a1 + 16),
                             v6) )
      ATL::AtlThrowImpl(-2147024882);
  }
  v9 = ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::NewNode(
         a1,
         a2,
         v8,
         v7);
  ATL::CSimpleStringT<unsigned short,0>::SetString(v9 + 8, a3);
  return v9;
}

```

## disassembly

```asm
0x14002d520  mov     [rsp+arg_8], rbx
0x14002d525  mov     [rsp+arg_10], rsi
0x14002d52a  mov     [rsp+arg_0], rcx
0x14002d52f  push    rdi
0x14002d530  push    r12
0x14002d532  push    r13
0x14002d534  push    r14
0x14002d536  push    r15
0x14002d538  sub     rsp, 30h
0x14002d53c  mov     r12, r8
0x14002d53f  mov     r13, rdx
0x14002d542  mov     rsi, rcx
0x14002d545  mov     rcx, rdx
0x14002d548  call    ?Hash@?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@SAKPEBG@Z; CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>::Hash(ushort const *)
0x14002d54d  mov     r15d, eax
0x14002d550  xor     edx, edx
0x14002d552  div     dword ptr [rsi+10h]
0x14002d555  mov     ebx, edx
0x14002d557  mov     dword ptr [rsp+58h+arg_18], ebx
0x14002d55b  mov     rdi, [rsi]
0x14002d55e  xor     eax, eax
0x14002d560  lea     r14d, [rax+1]
0x14002d564  test    rdi, rdi
0x14002d567  jz      short loc_14002D586
0x14002d569  mov     rdi, [rdi+rdx*8]
0x14002d56d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14002d571  test    rdi, rdi
0x14002d574  jz      short loc_14002D582
0x14002d576  cmp     [rdi+18h], r15d
0x14002d57a  jz      short loc_14002D5BA
0x14002d57c  mov     rdi, [rdi+10h]
0x14002d580  jmp     short loc_14002D571
0x14002d582  mov     ebx, dword ptr [rsp+58h+arg_18]
0x14002d586  cmp     [rsi], rax
0x14002d589  jz      loc_14002D6BD
0x14002d58f  mov     r9d, r15d
0x14002d592  mov     r8d, ebx
0x14002d595  mov     rdx, r13
0x14002d598  mov     rcx, rsi
0x14002d59b  call    ?NewNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@AEAAPEAVCNode@12@PEBGII@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::NewNode(ushort const *,uint,uint)
0x14002d5a0  mov     rdi, rax
0x14002d5a3  mov     [rsp+58h+arg_18], rax
0x14002d5a8  lea     rcx, [rax+8]
0x14002d5ac  mov     rdx, r12
0x14002d5af  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x14002d5b4  nop
0x14002d5b5  jmp     loc_14002D67F
0x14002d5ba  mov     [rsp+58h+cchCount2], ebx; cchCount2
0x14002d5be  mov     [rsp+58h+lpString2], r13; lpString2
0x14002d5c3  mov     r9d, ebx; cchCount1
0x14002d5c6  mov     r8, [rdi]; lpString1
0x14002d5c9  mov     edx, r14d; dwCmpFlags
0x14002d5cc  mov     ecx, 7Fh; Locale
0x14002d5d1  call    cs:__imp_CompareStringW
0x14002d5d7  cmp     eax, 2
0x14002d5da  jnz     short loc_14002D644
0x14002d5dc  lea     rsi, [rdi+8]
0x14002d5e0  xor     eax, eax
0x14002d5e2  test    r12, r12
0x14002d5e5  jz      short loc_14002D64B
0x14002d5e7  inc     rbx
0x14002d5ea  cmp     [r12+rbx*2], ax
0x14002d5ef  jnz     short loc_14002D5E7
0x14002d5f1  test    ebx, ebx
0x14002d5f3  jz      short loc_14002D64B
0x14002d5f5  mov     r15, [rsi]
0x14002d5f8  mov     r13d, [r15-10h]
0x14002d5fc  sub     r14d, [r15-8]
0x14002d600  mov     eax, [r15-0Ch]
0x14002d604  sub     eax, ebx
0x14002d606  or      r14d, eax
0x14002d609  jge     short loc_14002D615
0x14002d60b  mov     edx, ebx
0x14002d60d  mov     rcx, rsi
0x14002d610  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x14002d615  movsxd  rax, ebx
0x14002d618  lea     r14, [rax+rax]
0x14002d61c  test    r14, r14
0x14002d61f  jz      short loc_14002D666
0x14002d621  mov     rdx, r12
0x14002d624  sub     rdx, r15
0x14002d627  sar     rdx, 1
0x14002d62a  mov     rcx, [rsi]; void *
0x14002d62d  cmp     rdx, r13
0x14002d630  jbe     short loc_14002D69A
0x14002d632  test    rcx, rcx
0x14002d635  jz      short loc_14002D655
0x14002d637  mov     r8, r14; Size
0x14002d63a  mov     rdx, r12; Src
0x14002d63d  call    memcpy_0
0x14002d642  jmp     short loc_14002D666
0x14002d644  xor     eax, eax
0x14002d646  jmp     loc_14002D57C
0x14002d64b  mov     rcx, rsi
0x14002d64e  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x14002d653  jmp     short loc_14002D67F
0x14002d655  call    cs:__imp__o__errno
0x14002d65b  mov     dword ptr [rax], 16h
0x14002d661  call    _invalid_parameter_noinfo
0x14002d666  test    ebx, ebx
0x14002d668  js      short loc_14002D6B2
0x14002d66a  mov     rax, [rsi]
0x14002d66d  cmp     ebx, [rax-0Ch]
0x14002d670  jg      short loc_14002D6B2
0x14002d672  mov     [rax-10h], ebx
0x14002d675  mov     rcx, [rsi]
0x14002d678  xor     eax, eax
0x14002d67a  mov     [r14+rcx], ax
0x14002d67f  mov     rax, rdi
0x14002d682  mov     rbx, [rsp+58h+arg_8]
0x14002d687  mov     rsi, [rsp+58h+arg_10]
0x14002d68c  add     rsp, 30h
0x14002d690  pop     r15
0x14002d692  pop     r14
0x14002d694  pop     r13
0x14002d696  pop     r12
0x14002d698  pop     rdi
0x14002d699  retn
0x14002d69a  test    rcx, rcx
0x14002d69d  jz      short loc_14002D655
0x14002d69f  lea     rdx, [rcx+rdx*2]; Src
0x14002d6a3  test    rdx, rdx
0x14002d6a6  jz      short loc_14002D655
0x14002d6a8  mov     r8, r14; Size
0x14002d6ab  call    memmove_0
0x14002d6b0  jmp     short loc_14002D666
0x14002d6b2  mov     ecx, 80070057h; int
0x14002d6b7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002d6bd  mov     r8b, r14b
0x14002d6c0  mov     edx, [rsi+10h]
0x14002d6c3  mov     rcx, rsi
0x14002d6c6  call    ?InitHashTable@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@QEAA_NI_N@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::InitHashTable(uint,bool)
0x14002d6cb  test    al, al
0x14002d6cd  jnz     loc_14002D58F
0x14002d6d3  mov     ecx, 8007000Eh; int
0x14002d6d8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
