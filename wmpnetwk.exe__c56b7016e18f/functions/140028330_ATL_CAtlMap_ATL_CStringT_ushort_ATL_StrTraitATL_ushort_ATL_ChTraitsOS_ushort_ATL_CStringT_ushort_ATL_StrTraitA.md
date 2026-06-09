# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::CNode * &)

- ea: `0x140028330`
- end: `0x140028428`
- name: `?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140079e5c`

## callees

- `0x140028330`
- `0x1400396dc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x140028415`
- `KERNEL32!CompareStringW` at `0x140028415`
- `USER32!CharUpperW` at `0x14002836a`
- `USER32!CharUpperW` at `0x14002836a`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::GetNode(
        __int64 a1,
        const WCHAR *a2,
        int *a3,
        unsigned int *a4,
        _QWORD *a5)
{
  WCHAR v9; // ax
  unsigned int v10; // edi
  WCHAR *v11; // rbx
  int v12; // ecx
  __int64 v13; // rdi
  __int64 i; // rbx

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v9 = *a2;
  v10 = 0;
  if ( *a2 )
  {
    v11 = (WCHAR *)a2;
    do
    {
      ++v11;
      v12 = (unsigned __int16)CharUpperW((LPWSTR)v9);
      v9 = *v11;
      v10 = v12 + 33 * v10;
    }
    while ( *v11 );
  }
  *a4 = v10;
  *a3 = v10 % *(_DWORD *)(a1 + 16);
  if ( *(_QWORD *)a1 )
  {
    v13 = 0;
    *a5 = 0;
    for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)*a3); i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 24) == *a4 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, a2, -1) == 2 )
      {
        *a5 = v13;
        return i;
      }
      v13 = i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140028330  mov     [rsp+arg_18], rbp
0x140028335  push    r12
0x140028337  push    r14
0x140028339  push    r15
0x14002833b  sub     rsp, 30h
0x14002833f  mov     r12, r9
0x140028342  mov     rbp, r8
0x140028345  mov     r14, rdx
0x140028348  mov     r15, rcx
0x14002834b  test    rdx, rdx
0x14002834e  jz      short loc_1400283C9
0x140028350  movzx   eax, word ptr [rdx]
0x140028353  mov     [rsp+48h+arg_0], rbx
0x140028358  mov     [rsp+48h+arg_10], rdi
0x14002835d  xor     edi, edi
0x14002835f  test    ax, ax
0x140028362  jz      short loc_140028384
0x140028364  mov     rbx, rdx
0x140028367  movzx   ecx, ax; lpsz
0x14002836a  call    cs:__imp_CharUpperW
0x140028370  imul    edi, 21h ; '!'
0x140028373  lea     rbx, [rbx+2]
0x140028377  movzx   ecx, ax
0x14002837a  movzx   eax, word ptr [rbx]
0x14002837d  add     edi, ecx
0x14002837f  test    ax, ax
0x140028382  jnz     short loc_140028367
0x140028384  mov     [r12], edi
0x140028388  xor     edx, edx
0x14002838a  mov     eax, edi
0x14002838c  mov     [rsp+48h+arg_8], rsi
0x140028391  div     dword ptr [r15+10h]
0x140028395  mov     [rbp+0], edx
0x140028398  cmp     qword ptr [r15], 0
0x14002839c  jz      short loc_1400283D4
0x14002839e  mov     rsi, [rsp+48h+arg_20]
0x1400283a3  xor     edi, edi
0x1400283a5  mov     [rsi], rdi
0x1400283a8  mov     ecx, [rbp+0]
0x1400283ab  mov     rax, [r15]
0x1400283ae  mov     rbx, [rax+rcx*8]
0x1400283b2  test    rbx, rbx
0x1400283b5  jz      short loc_1400283D4
0x1400283b7  mov     eax, [r12]
0x1400283bb  cmp     [rbx+18h], eax
0x1400283be  jz      short loc_1400283F5
0x1400283c0  mov     rdi, rbx
0x1400283c3  mov     rbx, [rbx+10h]
0x1400283c7  jmp     short loc_1400283B2
0x1400283c9  mov     ecx, 80004005h; int
0x1400283ce  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400283d4  xor     eax, eax
0x1400283d6  mov     rsi, [rsp+48h+arg_8]
0x1400283db  mov     rbx, [rsp+48h+arg_0]
0x1400283e0  mov     rdi, [rsp+48h+arg_10]
0x1400283e5  mov     rbp, [rsp+48h+arg_18]
0x1400283ea  add     rsp, 30h
0x1400283ee  pop     r15
0x1400283f0  pop     r14
0x1400283f2  pop     r12
0x1400283f4  retn
0x1400283f5  mov     r8, [rbx]; lpString1
0x1400283f8  mov     r9d, 0FFFFFFFFh; cchCount1
0x1400283fe  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x140028406  mov     edx, 1; dwCmpFlags
0x14002840b  mov     ecx, 7Fh; Locale
0x140028410  mov     [rsp+48h+lpString2], r14; lpString2
0x140028415  call    cs:__imp_CompareStringW
0x14002841b  cmp     eax, 2
0x14002841e  jnz     short loc_1400283C0
0x140028420  mov     [rsi], rdi
0x140028423  mov     rax, rbx
0x140028426  jmp     short loc_1400283D6
```
