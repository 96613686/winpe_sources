# ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>>::Lookup(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)

- ea: `0x14002b89c`
- end: `0x14002ba51`
- name: `?Lookup@?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V12@V?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V3@@ATL@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@@Z`
- size: `437`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x14002ac5c`
- `0x140041c80`

## callees

- `0x140014f90`
- `0x14002b89c`
- `0x1400395c0`
- `0x1400396dc`
- `0x140046c32`
- `0x140046d00`
- `0x14009ad10`
- `0x14009e010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x14002b9b8`
- `KERNEL32!CompareStringW` at `0x14002b9b8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002ba27`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14002ba27`
- `USER32!CharUpperW` at `0x14002b8c9`
- `USER32!CharUpperW` at `0x14002b8c9`

## pseudocode

```c
char __fastcall ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>>::Lookup(
        __int64 a1,
        const WCHAR *a2,
        _QWORD *a3)
{
  WCHAR v6; // ax
  unsigned int v7; // esi
  WCHAR *v8; // rbx
  int v9; // ecx
  __int64 i; // rbx
  char *v12; // rsi
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rbx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, __int64); // rax
  size_t v16; // r8
  void *v17; // rcx
  _DWORD *v18; // r14
  __int64 v19; // rax
  __int64 v20; // rdx

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
    for ( i = *(_QWORD *)(*(_QWORD *)a1 + 8LL * (v7 % *(_DWORD *)(a1 + 16))); ; i = *(_QWORD *)(i + 16) )
    {
      if ( !i )
        return 0;
      if ( *(_DWORD *)(i + 24) == v7 && CompareStringW(0x7Fu, 1u, *(PCNZWCH *)i, -1, a2, -1) == 2 )
        break;
    }
    v12 = *(char **)(i + 8);
    v13 = (volatile signed __int32 *)(*a3 - 24LL);
    v14 = (volatile signed __int32 *)(v12 - 24);
    if ( v12 - 24 != (char *)v13 )
    {
      if ( *((int *)v13 + 4) >= 0 && *(_QWORD *)v14 == *(_QWORD *)v13 )
      {
        v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, __int64))(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v14 + 32LL))(*(_QWORD *)v14);
        if ( *((int *)v14 + 4) >= 0 && v15 == *(__int64 (__fastcall ****)(_QWORD, _QWORD, __int64))v14 )
        {
          _InterlockedIncrement(v14 + 4);
LABEL_18:
          if ( _InterlockedExchangeAdd(v13 + 4, 0xFFFFFFFF) <= 1 )
            (*(void (__fastcall **)(_QWORD, volatile signed __int32 *))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13, v13);
          *a3 = v14 + 6;
          return 1;
        }
        v18 = v14 + 2;
        v19 = (**v15)(v15, *((unsigned int *)v14 + 2), 2);
        v14 = (volatile signed __int32 *)v19;
        if ( !v19 )
          ATL::CSimpleStringT<char,0>::ThrowMemoryException();
        *(_DWORD *)(v19 + 8) = *v18;
        v16 = 2LL * (*v18 + 1);
        if ( !v16 )
          goto LABEL_18;
        v17 = (void *)(v19 + 24);
        if ( v19 != -24 )
        {
          if ( v12 )
          {
            memcpy_0(v17, v12, v16);
            goto LABEL_18;
          }
          memset_0(v17, 0, v16);
        }
        *(_DWORD *)_o__errno(v17, v20, v16) = 22;
        invalid_parameter_noinfo();
        goto LABEL_18;
      }
      ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v12, *((unsigned int *)v12 - 4));
    }
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14002b89c  push    rbx
0x14002b89e  push    rbp
0x14002b89f  push    rsi
0x14002b8a0  push    rdi
0x14002b8a1  push    r14
0x14002b8a3  push    r15
0x14002b8a5  sub     rsp, 38h
0x14002b8a9  xor     ebp, ebp
0x14002b8ab  mov     r15, r8
0x14002b8ae  mov     rdi, rdx
0x14002b8b1  mov     r14, rcx
0x14002b8b4  test    rdx, rdx
0x14002b8b7  jz      short loc_14002B90B
0x14002b8b9  movzx   eax, word ptr [rdx]
0x14002b8bc  mov     esi, ebp
0x14002b8be  test    ax, ax
0x14002b8c1  jz      short loc_14002B8E3
0x14002b8c3  mov     rbx, rdx
0x14002b8c6  movzx   ecx, ax; lpsz
0x14002b8c9  call    cs:__imp_CharUpperW
0x14002b8cf  imul    esi, 21h ; '!'
0x14002b8d2  lea     rbx, [rbx+2]
0x14002b8d6  movzx   ecx, ax
0x14002b8d9  movzx   eax, word ptr [rbx]
0x14002b8dc  add     esi, ecx
0x14002b8de  test    ax, ax
0x14002b8e1  jnz     short loc_14002B8C6
0x14002b8e3  mov     rbx, [r14]
0x14002b8e6  test    rbx, rbx
0x14002b8e9  jz      short loc_14002B916
0x14002b8eb  xor     edx, edx
0x14002b8ed  mov     eax, esi
0x14002b8ef  div     dword ptr [r14+10h]
0x14002b8f3  mov     rbx, [rbx+rdx*8]
0x14002b8f7  test    rbx, rbx
0x14002b8fa  jz      short loc_14002B916
0x14002b8fc  cmp     [rbx+18h], esi
0x14002b8ff  jz      loc_14002B99D
0x14002b905  mov     rbx, [rbx+10h]
0x14002b909  jmp     short loc_14002B8F7
0x14002b90b  mov     ecx, 80004005h; int
0x14002b910  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14002b916  xor     al, al
0x14002b918  jmp     short loc_14002B990
0x14002b91a  mov     rsi, [rbx+8]
0x14002b91e  mov     rdi, [r15]
0x14002b921  add     rdi, 0FFFFFFFFFFFFFFE8h
0x14002b925  lea     rbx, [rsi-18h]
0x14002b929  cmp     rbx, rdi
0x14002b92c  jz      short loc_14002B98E
0x14002b92e  cmp     [rdi+10h], ebp
0x14002b931  jl      loc_14002BA3D
0x14002b937  mov     rcx, [rbx]
0x14002b93a  cmp     rcx, [rdi]
0x14002b93d  jnz     loc_14002BA3D
0x14002b943  mov     rax, [rcx]
0x14002b946  mov     rax, [rax+20h]
0x14002b94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b94f  mov     rcx, rax
0x14002b952  cmp     [rbx+10h], ebp
0x14002b955  jl      loc_14002B9FA
0x14002b95b  cmp     rax, [rbx]
0x14002b95e  jnz     loc_14002B9FA
0x14002b964  lock inc dword ptr [rbx+10h]
0x14002b968  or      eax, 0FFFFFFFFh
0x14002b96b  lock xadd [rdi+10h], eax
0x14002b970  sub     eax, 1
0x14002b973  jg      short loc_14002B987
0x14002b975  mov     rcx, [rdi]
0x14002b978  mov     rdx, rdi
0x14002b97b  mov     rax, [rcx]
0x14002b97e  mov     rax, [rax+8]
0x14002b982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b987  lea     rax, [rbx+18h]
0x14002b98b  mov     [r15], rax
0x14002b98e  mov     al, 1
0x14002b990  add     rsp, 38h
0x14002b994  pop     r15
0x14002b996  pop     r14
0x14002b998  pop     rdi
0x14002b999  pop     rsi
0x14002b99a  pop     rbp
0x14002b99b  pop     rbx
0x14002b99c  retn
0x14002b99d  mov     r8, [rbx]; lpString1
0x14002b9a0  or      r9d, 0FFFFFFFFh; cchCount1
0x14002b9a4  mov     [rsp+68h+cchCount2], 0FFFFFFFFh; cchCount2
0x14002b9ac  mov     [rsp+68h+lpString2], rdi; lpString2
0x14002b9b1  lea     edx, [r9+2]; dwCmpFlags
0x14002b9b5  lea     ecx, [rdx+7Eh]; Locale
0x14002b9b8  call    cs:__imp_CompareStringW
0x14002b9be  cmp     eax, 2
0x14002b9c1  jz      loc_14002B91A
0x14002b9c7  jmp     loc_14002B905
0x14002b9cc  mov     eax, [r14]
0x14002b9cf  mov     [rbx+8], eax
0x14002b9d2  mov     eax, [r14]
0x14002b9d5  inc     eax
0x14002b9d7  movsxd  r8, eax
0x14002b9da  add     r8, r8; Size
0x14002b9dd  jz      short loc_14002B968
0x14002b9df  lea     rcx, [rbx+18h]; void *
0x14002b9e3  test    rcx, rcx
0x14002b9e6  jz      short loc_14002BA27
0x14002b9e8  test    rsi, rsi
0x14002b9eb  jz      short loc_14002BA20
0x14002b9ed  mov     rdx, rsi; Src
0x14002b9f0  call    memcpy_0
0x14002b9f5  jmp     loc_14002B968
0x14002b9fa  mov     rax, [rax]
0x14002b9fd  lea     r14, [rbx+8]
0x14002ba01  mov     edx, [r14]
0x14002ba04  mov     r8d, 2
0x14002ba0a  mov     rax, [rax]
0x14002ba0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002ba12  mov     rbx, rax
0x14002ba15  test    rax, rax
0x14002ba18  jnz     short loc_14002B9CC
0x14002ba1a  call    ?ThrowMemoryException@?$CSimpleStringT@D$0A@@ATL@@KAXXZ; ATL::CSimpleStringT<char,0>::ThrowMemoryException(void)
0x14002ba20  xor     edx, edx; Val
0x14002ba22  call    memset_0
0x14002ba27  call    cs:__imp__o__errno
0x14002ba2d  mov     dword ptr [rax], 16h
0x14002ba33  call    _invalid_parameter_noinfo
0x14002ba38  jmp     loc_14002B968
0x14002ba3d  mov     r8d, [rsi-10h]
0x14002ba41  mov     rdx, rsi
0x14002ba44  mov     rcx, r15
0x14002ba47  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x14002ba4c  jmp     loc_14002B98E
```
