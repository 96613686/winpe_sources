# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<bool>>::CNode * &)

- ea: `0x140027420`
- end: `0x140027518`
- name: `?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@_NV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@_N@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400690f0`

## callees

- `0x140027420`
- `0x1400396dc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x1400274e4`
- `KERNEL32!CompareStringW` at `0x1400274e4`
- `USER32!CharUpperW` at `0x14002745a`
- `USER32!CharUpperW` at `0x14002745a`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,bool,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<bool>>::GetNode(
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
0x140027420  mov     [rsp+arg_18], rbp
0x140027425  push    r12
0x140027427  push    r14
0x140027429  push    r15
0x14002742b  sub     rsp, 30h
0x14002742f  mov     r12, r9
0x140027432  mov     rbp, r8
0x140027435  mov     r14, rdx
0x140027438  mov     r15, rcx
0x14002743b  test    rdx, rdx
0x14002743e  jz      short loc_1400274B9
0x140027440  movzx   eax, word ptr [rdx]
0x140027443  mov     [rsp+48h+arg_0], rbx
0x140027448  mov     [rsp+48h+arg_10], rdi
0x14002744d  xor     edi, edi
0x14002744f  test    ax, ax
0x140027452  jz      short loc_140027474
0x140027454  mov     rbx, rdx
0x140027457  movzx   ecx, ax; lpsz
0x14002745a  call    cs:__imp_CharUpperW
0x140027460  imul    edi, 21h ; '!'
0x140027463  lea     rbx, [rbx+2]
0x140027467  movzx   ecx, ax
0x14002746a  movzx   eax, word ptr [rbx]
0x14002746d  add     edi, ecx
0x14002746f  test    ax, ax
0x140027472  jnz     short loc_140027457
0x140027474  mov     [r12], edi
0x140027478  xor     edx, edx
0x14002747a  mov     eax, edi
0x14002747c  mov     [rsp+48h+arg_8], rsi
0x140027481  div     dword ptr [r15+10h]
0x140027485  mov     [rbp+0], edx
0x140027488  cmp     qword ptr [r15], 0
0x14002748c  jz      short loc_1400274F7
0x14002748e  mov     rsi, [rsp+48h+arg_20]
0x140027493  xor     edi, edi
0x140027495  mov     [rsi], rdi
0x140027498  mov     ecx, [rbp+0]
0x14002749b  mov     rax, [r15]
0x14002749e  mov     rbx, [rax+rcx*8]
0x1400274a2  test    rbx, rbx
0x1400274a5  jz      short loc_1400274F7
0x1400274a7  mov     eax, [r12]
0x1400274ab  cmp     [rbx+18h], eax
0x1400274ae  jz      short loc_1400274C4
0x1400274b0  mov     rdi, rbx
0x1400274b3  mov     rbx, [rbx+10h]
0x1400274b7  jmp     short loc_1400274A2
0x1400274b9  mov     ecx, 80004005h; int
0x1400274be  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400274c4  mov     r8, [rbx]; lpString1
0x1400274c7  mov     r9d, 0FFFFFFFFh; cchCount1
0x1400274cd  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x1400274d5  mov     edx, 1; dwCmpFlags
0x1400274da  mov     ecx, 7Fh; Locale
0x1400274df  mov     [rsp+48h+lpString2], r14; lpString2
0x1400274e4  call    cs:__imp_CompareStringW
0x1400274ea  cmp     eax, 2
0x1400274ed  jnz     short loc_1400274B0
0x1400274ef  mov     [rsi], rdi
0x1400274f2  mov     rax, rbx
0x1400274f5  jmp     short loc_1400274F9
0x1400274f7  xor     eax, eax
0x1400274f9  mov     rsi, [rsp+48h+arg_8]
0x1400274fe  mov     rbx, [rsp+48h+arg_0]
0x140027503  mov     rdi, [rsp+48h+arg_10]
0x140027508  mov     rbp, [rsp+48h+arg_18]
0x14002750d  add     rsp, 30h
0x140027511  pop     r15
0x140027513  pop     r14
0x140027515  pop     r12
0x140027517  retn
```
