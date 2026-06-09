# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNode(ushort const *,uint &,uint &,ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ContentProviderInfo *>>::CNode * &)

- ea: `0x14002aa50`
- end: `0x14002ab4b`
- name: `?GetNode@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEAUContentProviderInfo@@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@PEAUContentProviderInfo@@@2@@ATL@@AEBAPEAVCNode@12@PEBGAEAI1AEAPEAV312@@Z`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002a994`
- `0x14004c0f4`

## callees

- `0x14002aa50`
- `0x1400396dc`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002ab2c`
- `KERNEL32!CompareStringW` at `0x14002ab2c`
- `USER32!CharUpperW` at `0x14002aa8a`
- `USER32!CharUpperW` at `0x14002aa8a`

## pseudocode

```c
__int64 __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ContentProviderInfo *,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ContentProviderInfo *>>::GetNode(
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
  __int64 v14; // rdi
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
    v14 = 0;
    *a5 = 0;
    for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (unsigned int)*a3); i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 24) == *a4 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, a2, -1) == 2 )
      {
        *a5 = v14;
        return i;
      }
      v14 = i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002aa50  mov     [rsp+arg_18], rbp
0x14002aa55  push    r12
0x14002aa57  push    r14
0x14002aa59  push    r15
0x14002aa5b  sub     rsp, 30h
0x14002aa5f  mov     r12, r9
0x14002aa62  mov     rbp, r8
0x14002aa65  mov     r14, rdx
0x14002aa68  mov     r15, rcx
0x14002aa6b  test    rdx, rdx
0x14002aa6e  jz      short loc_14002AADF
0x14002aa70  movzx   eax, word ptr [rdx]
0x14002aa73  mov     [rsp+48h+arg_0], rbx
0x14002aa78  mov     [rsp+48h+arg_10], rdi
0x14002aa7d  xor     edi, edi
0x14002aa7f  test    ax, ax
0x14002aa82  jz      short loc_14002AAA4
0x14002aa84  mov     rbx, rdx
0x14002aa87  movzx   ecx, ax; lpsz
0x14002aa8a  call    cs:__imp_CharUpperW
0x14002aa90  imul    edi, 21h ; '!'
0x14002aa93  lea     rbx, [rbx+2]
0x14002aa97  movzx   ecx, ax
0x14002aa9a  movzx   eax, word ptr [rbx]
0x14002aa9d  add     edi, ecx
0x14002aa9f  test    ax, ax
0x14002aaa2  jnz     short loc_14002AA87
0x14002aaa4  mov     [r12], edi
0x14002aaa8  xor     edx, edx
0x14002aaaa  mov     eax, edi
0x14002aaac  mov     [rsp+48h+arg_8], rsi
0x14002aab1  div     dword ptr [r15+10h]
0x14002aab5  mov     [rbp+0], edx
0x14002aab8  cmp     qword ptr [r15], 0
0x14002aabc  jnz     short loc_14002AAEA
0x14002aabe  xor     eax, eax
0x14002aac0  mov     rsi, [rsp+48h+arg_8]
0x14002aac5  mov     rbx, [rsp+48h+arg_0]
0x14002aaca  mov     rdi, [rsp+48h+arg_10]
0x14002aacf  mov     rbp, [rsp+48h+arg_18]
0x14002aad4  add     rsp, 30h
0x14002aad8  pop     r15
0x14002aada  pop     r14
0x14002aadc  pop     r12
0x14002aade  retn
0x14002aadf  mov     ecx, 80004005h; int
0x14002aae4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002aaea  mov     rsi, [rsp+48h+arg_20]
0x14002aaef  xor     edi, edi
0x14002aaf1  mov     [rsi], rdi
0x14002aaf4  mov     ecx, [rbp+0]
0x14002aaf7  mov     rax, [r15]
0x14002aafa  mov     rbx, [rax+rcx*8]
0x14002aafe  test    rbx, rbx
0x14002ab01  jz      short loc_14002AABE
0x14002ab03  mov     eax, [r12]
0x14002ab07  cmp     [rbx+18h], eax
0x14002ab0a  jnz     short loc_14002AB37
0x14002ab0c  mov     r8, [rbx]; lpString1
0x14002ab0f  mov     r9d, 0FFFFFFFFh; cchCount1
0x14002ab15  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x14002ab1d  mov     edx, 1; dwCmpFlags
0x14002ab22  mov     ecx, 7Fh; Locale
0x14002ab27  mov     [rsp+48h+lpString2], r14; lpString2
0x14002ab2c  call    cs:__imp_CompareStringW
0x14002ab32  cmp     eax, 2
0x14002ab35  jz      short loc_14002AB40
0x14002ab37  mov     rdi, rbx
0x14002ab3a  mov     rbx, [rbx+10h]
0x14002ab3e  jmp     short loc_14002AAFE
0x14002ab40  mov     [rsi], rdi
0x14002ab43  mov     rax, rbx
0x14002ab46  jmp     loc_14002AAC0
```
