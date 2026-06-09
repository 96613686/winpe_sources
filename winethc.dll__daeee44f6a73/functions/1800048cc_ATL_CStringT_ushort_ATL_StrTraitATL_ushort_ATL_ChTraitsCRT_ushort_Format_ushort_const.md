# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)

- ea: `0x1800048cc`
- end: `0x180004a35`
- name: `?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ`
- size: `361`
- prototype: ``
- caller_count: `8`
- callee_count: `6`
- tags: ``

## callers

- `0x180002f7c`
- `0x1800082f0`
- `0x180008ec0`
- `0x18000929c`
- `0x180009528`
- `0x180009ae4`
- `0x180009e04`
- `0x18000d160`

## callees

- `0x180003358`
- `0x1800041f8`
- `0x1800048cc`
- `0x180008858`
- `0x18000ae24`
- `0x180014010`

## import_xrefs

- `msvcrt!_vscwprintf` at `0x180004904`
- `msvcrt!_vscwprintf` at `0x180004904`
- `msvcrt!vswprintf_s` at `0x1800049c6`
- `msvcrt!vswprintf_s` at `0x1800049c6`

## pseudocode

```c
__int64 ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        __int64 *a1,
        wchar_t *a2,
        ...)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  wchar_t *v8; // rbx
  signed __int32 v9; // eax
  bool v10; // cc
  __int64 result; // rax
  wchar_t *Format[7]; // [rsp+20h] [rbp-38h] BYREF
  va_list va; // [rsp+70h] [rbp+18h] BYREF

  va_start(va, a2);
  Format[0] = 0;
  if ( !a2 )
    goto LABEL_17;
  v4 = _vscwprintf(a2, va);
  v5 = v4;
  if ( v4 == -1 )
    ATL::AtlThrowImpl(-2147024882);
  v6 = *(_QWORD *)(*a1 - 24);
  if ( !v6 || (v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 32LL))(v6)) == 0 )
  {
    v7 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[4])(&ATL::g_strmgr);
    if ( !v7 )
      ATL::AtlThrowImpl(-2147467259);
  }
  Format[0] = (wchar_t *)((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7) + 24);
  if ( (unsigned __int64)a2 >= 0x10000 )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      (char **)Format,
      (char *)a2);
  else
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
      Format,
      (unsigned __int16)a2);
  if ( (int)((*(_DWORD *)(*a1 - 12) - v5) | (1 - *(_DWORD *)(*a1 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, v5);
  v8 = Format[0];
  vswprintf_s((wchar_t *const)*a1, (int)v5 + 1, Format[0], va);
  if ( (int)v5 < 0 || (int)v5 > *(_DWORD *)(*a1 - 12) )
LABEL_17:
    ATL::AtlThrowImpl(-2147024809);
  *(_DWORD *)(*a1 - 16) = v5;
  *(_WORD *)(*a1 + 2 * v5) = 0;
  v9 = _InterlockedExchangeAdd((volatile signed __int32 *)v8 - 2, 0xFFFFFFFF);
  v10 = v9 <= 1;
  result = (unsigned int)(v9 - 1);
  if ( v10 )
    return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v8 - 3) + 8LL))(*((_QWORD *)v8 - 3));
  return result;
}

```

## disassembly

```asm
0x1800048cc  mov     rax, rsp
0x1800048cf  mov     [rax+10h], rdx
0x1800048d3  mov     [rax+18h], r8
0x1800048d7  mov     [rax+20h], r9
0x1800048db  push    rbx
0x1800048dc  push    rbp
0x1800048dd  push    rsi
0x1800048de  push    rdi
0x1800048df  sub     rsp, 38h
0x1800048e3  mov     qword ptr [rax-38h], 0
0x1800048eb  mov     rbx, rdx
0x1800048ee  lea     rbp, [rax+18h]
0x1800048f2  mov     rsi, rcx
0x1800048f5  test    rdx, rdx
0x1800048f8  jz      loc_180004A1F
0x1800048fe  mov     rdx, rbp; ArgList
0x180004901  mov     rcx, rbx; Format
0x180004904  call    cs:__imp__vscwprintf
0x18000490b  nop     dword ptr [rax+rax+00h]
0x180004910  movsxd  rdi, eax
0x180004913  cmp     edi, 0FFFFFFFFh
0x180004916  jz      loc_180004A2A
0x18000491c  mov     rax, [rsi]
0x18000491f  mov     rcx, [rax-18h]
0x180004923  test    rcx, rcx
0x180004926  jz      short loc_18000493C
0x180004928  mov     rax, [rcx]
0x18000492b  mov     rax, [rax+20h]
0x18000492f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004934  mov     rcx, rax
0x180004937  test    rax, rax
0x18000493a  jnz     short loc_18000495F
0x18000493c  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180004943  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x18000494a  mov     rax, [rax+20h]
0x18000494e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004953  mov     rcx, rax
0x180004956  test    rax, rax
0x180004959  jz      loc_180004A14
0x18000495f  mov     rax, [rcx]
0x180004962  mov     rax, [rax+18h]
0x180004966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496b  add     rax, 18h
0x18000496f  lea     rcx, [rsp+58h+Format]
0x180004974  mov     [rsp+58h+Format], rax
0x180004979  cmp     rbx, 10000h
0x180004980  jnb     short loc_18000498C
0x180004982  movzx   edx, bx
0x180004985  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)
0x18000498a  jmp     short loc_180004994
0x18000498c  mov     rdx, rbx
0x18000498f  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)
0x180004994  mov     rax, [rsi]
0x180004997  mov     edx, 1
0x18000499c  mov     ecx, [rax-0Ch]
0x18000499f  sub     edx, [rax-8]
0x1800049a2  sub     ecx, edi
0x1800049a4  or      edx, ecx
0x1800049a6  jge     short loc_1800049B2
0x1800049a8  mov     edx, edi
0x1800049aa  mov     rcx, rsi
0x1800049ad  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800049b2  mov     rbx, [rsp+58h+Format]
0x1800049b7  lea     eax, [rdi+1]
0x1800049ba  mov     rcx, [rsi]; Buffer
0x1800049bd  mov     r8, rbx; Format
0x1800049c0  movsxd  rdx, eax; BufferCount
0x1800049c3  mov     r9, rbp; ArgList
0x1800049c6  call    cs:__imp_vswprintf_s
0x1800049cd  nop     dword ptr [rax+rax+00h]
0x1800049d2  test    edi, edi
0x1800049d4  js      short loc_180004A1F
0x1800049d6  mov     rax, [rsi]
0x1800049d9  cmp     edi, [rax-0Ch]
0x1800049dc  jg      short loc_180004A1F
0x1800049de  mov     [rax-10h], edi
0x1800049e1  lea     rdx, [rbx-18h]
0x1800049e5  mov     rcx, [rsi]
0x1800049e8  xor     eax, eax
0x1800049ea  mov     [rcx+rdi*2], ax
0x1800049ee  or      eax, 0FFFFFFFFh
0x1800049f1  lock xadd [rdx+10h], eax
0x1800049f6  sub     eax, 1
0x1800049f9  jg      short loc_180004A0A
0x1800049fb  mov     rcx, [rdx]
0x1800049fe  mov     rax, [rcx]
0x180004a01  mov     rax, [rax+8]
0x180004a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a0a  add     rsp, 38h
0x180004a0e  pop     rdi
0x180004a0f  pop     rsi
0x180004a10  pop     rbp
0x180004a11  pop     rbx
0x180004a12  retn
0x180004a14  mov     ecx, 80004005h; int
0x180004a19  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004a1f  mov     ecx, 80070057h; int
0x180004a24  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180004a2a  mov     ecx, 8007000Eh; int
0x180004a2f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
