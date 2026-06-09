# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>>>::Lookup(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x14002d0e8`
- end: `0x14002d1fd`
- name: `?Lookup@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z`
- size: `277`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140077dac`
- `0x140079e5c`
- `0x14007cc80`

## callees

- `0x140014f90`
- `0x14001b560`
- `0x14002d0e8`
- `0x1400396dc`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002d18b`
- `KERNEL32!CompareStringW` at `0x14002d18b`
- `USER32!CharUpperW` at `0x14002d117`
- `USER32!CharUpperW` at `0x14002d117`

## pseudocode

```c
char __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>>>::Lookup(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3)
{
  WCHAR v6; // ax
  unsigned int v7; // ebp
  WCHAR *v8; // rbx
  int v9; // ecx
  __int64 i; // rbx
  __int64 v12; // rdx
  volatile signed __int32 *v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // rdi

  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  v6 = *a2;
  v7 = 0;
  if ( *a2 )
  {
    v8 = (WCHAR *)a2;
    do
    {
      ++v8;
      v9 = (unsigned __int16)CharUpperW((LPWSTR)v6);
      v6 = *v8;
      v7 = v9 + 33 * v7;
    }
    while ( *v8 );
  }
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v7 % *(_DWORD *)(a1 + 16))); i; i = *(_QWORD *)(i + 16) )
    {
      if ( *(_DWORD *)(i + 24) == v7 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, a2, -1) == 2 )
      {
        v12 = *(_QWORD *)(i + 8);
        v13 = (volatile signed __int32 *)(*a3 - 24LL);
        v14 = (_QWORD *)(v12 - 24);
        if ( (volatile signed __int32 *)(v12 - 24) != v13 )
        {
          if ( *((int *)v13 + 4) >= 0 && *v14 == *(_QWORD *)v13 )
          {
            v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v14);
            if ( _InterlockedDecrement(v13 + 4) <= 0 )
              (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13, v13);
            *a3 = v15 + 24;
          }
          else
          {
            ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v12, *(unsigned int *)(v12 - 16));
          }
        }
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14002d0e8  push    rbx
0x14002d0ea  push    rbp
0x14002d0eb  push    rsi
0x14002d0ec  push    rdi
0x14002d0ed  push    r14
0x14002d0ef  push    r15
0x14002d0f1  sub     rsp, 38h
0x14002d0f5  xor     r15d, r15d
0x14002d0f8  mov     rsi, r8
0x14002d0fb  mov     rdi, rdx
0x14002d0fe  mov     r14, rcx
0x14002d101  test    rdx, rdx
0x14002d104  jz      short loc_14002D159
0x14002d106  movzx   eax, word ptr [rdx]
0x14002d109  mov     ebp, r15d
0x14002d10c  test    ax, ax
0x14002d10f  jz      short loc_14002D131
0x14002d111  mov     rbx, rdx
0x14002d114  movzx   ecx, ax; lpsz
0x14002d117  call    cs:__imp_CharUpperW
0x14002d11d  imul    ebp, 21h ; '!'
0x14002d120  lea     rbx, [rbx+2]
0x14002d124  movzx   ecx, ax
0x14002d127  movzx   eax, word ptr [rbx]
0x14002d12a  add     ebp, ecx
0x14002d12c  test    ax, ax
0x14002d12f  jnz     short loc_14002D114
0x14002d131  mov     rbx, [r14]
0x14002d134  test    rbx, rbx
0x14002d137  jz      short loc_14002D164
0x14002d139  xor     edx, edx
0x14002d13b  mov     eax, ebp
0x14002d13d  div     dword ptr [r14+10h]
0x14002d141  or      r14d, 0FFFFFFFFh
0x14002d145  mov     rbx, [rbx+rdx*8]
0x14002d149  test    rbx, rbx
0x14002d14c  jz      short loc_14002D164
0x14002d14e  cmp     [rbx+18h], ebp
0x14002d151  jz      short loc_14002D173
0x14002d153  mov     rbx, [rbx+10h]
0x14002d157  jmp     short loc_14002D149
0x14002d159  mov     ecx, 80004005h; int
0x14002d15e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002d164  xor     al, al
0x14002d166  add     rsp, 38h
0x14002d16a  pop     r15
0x14002d16c  pop     r14
0x14002d16e  pop     rdi
0x14002d16f  pop     rsi
0x14002d170  pop     rbp
0x14002d171  pop     rbx
0x14002d172  retn
0x14002d173  mov     r8, [rbx]; lpString1
0x14002d176  mov     edx, 1; dwCmpFlags
0x14002d17b  mov     [rsp+68h+cchCount2], r14d; cchCount2
0x14002d180  mov     r9d, r14d; cchCount1
0x14002d183  mov     [rsp+68h+lpString2], rdi; lpString2
0x14002d188  lea     ecx, [rdx+7Eh]; Locale
0x14002d18b  call    cs:__imp_CompareStringW
0x14002d191  cmp     eax, 2
0x14002d194  jnz     short loc_14002D153
0x14002d196  mov     rdx, [rbx+8]
0x14002d19a  mov     rbx, [rsi]
0x14002d19d  add     rbx, 0FFFFFFFFFFFFFFE8h
0x14002d1a1  lea     rcx, [rdx-18h]
0x14002d1a5  cmp     rcx, rbx
0x14002d1a8  jz      short loc_14002D1E8
0x14002d1aa  cmp     [rbx+10h], r15d
0x14002d1ae  jl      short loc_14002D1EF
0x14002d1b0  mov     rax, [rbx]
0x14002d1b3  cmp     [rcx], rax
0x14002d1b6  jnz     short loc_14002D1EF
0x14002d1b8  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x14002d1bd  mov     rdi, rax
0x14002d1c0  mov     ecx, r14d
0x14002d1c3  lock xadd [rbx+10h], ecx
0x14002d1c8  add     ecx, r14d
0x14002d1cb  test    ecx, ecx
0x14002d1cd  jg      short loc_14002D1E1
0x14002d1cf  mov     rcx, [rbx]
0x14002d1d2  mov     rdx, rbx
0x14002d1d5  mov     r8, [rcx]
0x14002d1d8  mov     rax, [r8+8]
0x14002d1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002d1e1  lea     rax, [rdi+18h]
0x14002d1e5  mov     [rsi], rax
0x14002d1e8  mov     al, 1
0x14002d1ea  jmp     loc_14002D166
0x14002d1ef  mov     r8d, [rdx-10h]
0x14002d1f3  mov     rcx, rsi
0x14002d1f6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002d1fb  jmp     short loc_14002D1E8
```
