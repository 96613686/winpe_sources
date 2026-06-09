# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x180019164`
- end: `0x180019368`
- name: `?GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `516`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180016698`
- `0x18001a9f8`

## callees

- `0x1800085b8`
- `0x18000b92c`
- `0x18000e390`
- `0x180019164`
- `0x1800319ba`
- `0x1800319c6`

## import_xrefs

- `msvcrt!wcschr` at `0x180019217`
- `msvcrt!wcschr` at `0x18001926c`
- `msvcrt!wcschr` at `0x180019217`
- `msvcrt!wcschr` at `0x18001926c`
- `msvcrt!_wcsnicmp` at `0x18001919a`
- `msvcrt!_wcsnicmp` at `0x18001919a`

## pseudocode

```c
char __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName(
        __int64 *a1,
        __int64 a2,
        char **a3)
{
  __int64 i; // rbx
  const wchar_t *v7; // rcx
  _QWORD *v8; // r8
  __int64 v9; // r9
  __int64 j; // rbx
  const wchar_t *v11; // rcx
  _QWORD *v12; // r8
  wchar_t *v13; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // r8

  for ( i = *a1; i != a1[1]; i += 64 )
  {
    if ( *(_QWORD *)(i + 24) < 8u )
      v7 = (const wchar_t *)i;
    else
      v7 = *(const wchar_t **)i;
    if ( !_wcsnicmp(v7, (const wchar_t *)a2, *(_QWORD *)(i + 16)) )
    {
      v8 = (_QWORD *)(i + 32);
      v9 = a2 + 2LL * *(_QWORD *)(i + 16);
      if ( *(_QWORD *)(i + 56) >= 8u )
        v8 = (_QWORD *)*v8;
      goto LABEL_10;
    }
  }
  for ( j = a1[3]; j != a1[4]; j += 32 )
  {
    if ( *(_QWORD *)(j + 24) < 8u )
      v11 = (const wchar_t *)j;
    else
      v11 = *(const wchar_t **)j;
    if ( !wcsncmp_0(v11, (const wchar_t *)a2, *(unsigned int *)(j + 16)) )
      goto LABEL_35;
  }
  if ( !wcschr((const wchar_t *)a2, 0x5Cu) )
  {
    if ( a1[8] )
    {
      v12 = a1 + 6;
      if ( (unsigned __int64)a1[9] >= 8 )
        v12 = (_QWORD *)*v12;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
        a3,
        L"%ws\\drivers\\%ws",
        v12,
        a2);
      return 1;
    }
LABEL_47:
    ATL::AtlThrowImpl(-2147418113);
  }
  if ( *(_WORD *)a2 == 92
    && *(_WORD *)(a2 + 2) == 59
    && *(_WORD *)(a2 + 4)
    && *(_WORD *)(a2 + 6) == 58
    && (v13 = wcschr((const wchar_t *)(a2 + 8), 0x5Cu)) != 0 )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
      a3,
      L"\\%ws",
      v13);
  }
  else
  {
    if ( *(_WORD *)a2 && *(_WORD *)(a2 + 2) != 58 )
    {
      if ( !a1[12] )
        goto LABEL_47;
      if ( *(_WORD *)a2 != 92 )
      {
        v8 = a1 + 10;
        if ( (unsigned __int64)a1[13] >= 8 )
          v8 = (_QWORD *)*v8;
        v9 = a2;
LABEL_10:
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%ws%ws",
          v8,
          v9);
        return 1;
      }
      if ( !wcsncmp_0(
              (const wchar_t *)a2,
              `Performance::NtImagePathDecoder::CNtImagePathDecoderBase::GetFileName'::`35'::wchDevicePrefix,
              8u) )
      {
LABEL_35:
        ATL::CSimpleStringT<unsigned short,0>::SetString(a3, &Src, 0);
        return 0;
      }
      if ( wcscmp_0((const wchar_t *)a2, L"\\FI_UNKNOWN") )
      {
        v15 = (unsigned __int16 *)(a1 + 10);
        if ( *((_QWORD *)v15 + 3) >= 8u )
          v15 = *(unsigned __int16 **)v15;
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Format(
          a3,
          L"%wc:%ws",
          *v15,
          a2);
        return 1;
      }
    }
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)(a2 + 2 * v16) );
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, (_BYTE *)a2, v16);
  }
  return 1;
}

```

## disassembly

```asm
0x180019164  push    rbx
0x180019166  push    rbp
0x180019167  push    rsi
0x180019168  push    rdi
0x180019169  push    r14
0x18001916b  sub     rsp, 20h
0x18001916f  mov     rbx, [rcx]
0x180019172  mov     rbp, r8
0x180019175  mov     rdi, rdx
0x180019178  mov     rsi, rcx
0x18001917b  xor     r14d, r14d
0x18001917e  cmp     rbx, [rsi+8]
0x180019182  jz      short loc_1800191DA
0x180019184  cmp     qword ptr [rbx+18h], 8
0x180019189  jb      short loc_180019190
0x18001918b  mov     rcx, [rbx]
0x18001918e  jmp     short loc_180019193
0x180019190  mov     rcx, rbx; String1
0x180019193  mov     r8, [rbx+10h]; MaxCount
0x180019197  mov     rdx, rdi; String2
0x18001919a  call    cs:__imp__wcsnicmp
0x1800191a1  nop     dword ptr [rax+rax+00h]
0x1800191a6  test    eax, eax
0x1800191a8  jz      short loc_1800191B0
0x1800191aa  add     rbx, 40h ; '@'
0x1800191ae  jmp     short loc_18001917E
0x1800191b0  mov     rax, [rbx+10h]
0x1800191b4  lea     r8, [rbx+20h]
0x1800191b8  cmp     qword ptr [r8+18h], 8
0x1800191bd  lea     r9, [rdi+rax*2]
0x1800191c1  jb      short loc_1800191C6
0x1800191c3  mov     r8, [r8]
0x1800191c6  lea     rdx, aWsWs; "%ws%ws"
0x1800191cd  mov     rcx, rbp
0x1800191d0  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x1800191d5  jmp     loc_18001934F
0x1800191da  mov     rbx, [rsi+18h]
0x1800191de  cmp     rbx, [rsi+20h]
0x1800191e2  jz      short loc_18001920D
0x1800191e4  cmp     qword ptr [rbx+18h], 8
0x1800191e9  jb      short loc_1800191F0
0x1800191eb  mov     rcx, [rbx]
0x1800191ee  jmp     short loc_1800191F3
0x1800191f0  mov     rcx, rbx; String1
0x1800191f3  mov     r8d, [rbx+10h]; MaxCount
0x1800191f7  mov     rdx, rdi; String2
0x1800191fa  call    wcsncmp_0
0x1800191ff  test    eax, eax
0x180019201  jz      loc_1800192D1
0x180019207  add     rbx, 20h ; ' '
0x18001920b  jmp     short loc_1800191DE
0x18001920d  mov     ebx, 5Ch ; '\'
0x180019212  mov     rcx, rdi; Str
0x180019215  mov     edx, ebx; Ch
0x180019217  call    cs:__imp_wcschr
0x18001921e  nop     dword ptr [rax+rax+00h]
0x180019223  test    rax, rax
0x180019226  jnz     short loc_18001924C
0x180019228  cmp     [rsi+40h], r14
0x18001922c  jz      loc_18001935D
0x180019232  lea     r8, [rsi+30h]
0x180019236  cmp     qword ptr [r8+18h], 8
0x18001923b  jb      short loc_180019240
0x18001923d  mov     r8, [r8]
0x180019240  mov     r9, rdi
0x180019243  lea     rdx, aWsDriversWs; "%ws\\drivers\\%ws"
0x18001924a  jmp     short loc_1800191CD
0x18001924c  cmp     [rdi], bx
0x18001924f  jnz     short loc_180019294
0x180019251  cmp     word ptr [rdi+2], 3Bh ; ';'
0x180019256  jnz     short loc_180019294
0x180019258  cmp     [rdi+4], r14w
0x18001925d  jz      short loc_180019294
0x18001925f  cmp     word ptr [rdi+6], 3Ah ; ':'
0x180019264  jnz     short loc_180019294
0x180019266  mov     edx, ebx; Ch
0x180019268  lea     rcx, [rdi+8]; Str
0x18001926c  call    cs:__imp_wcschr
0x180019273  nop     dword ptr [rax+rax+00h]
0x180019278  test    rax, rax
0x18001927b  jz      short loc_180019294
0x18001927d  mov     r8, rax
0x180019280  lea     rdx, aWs; "\\%ws"
0x180019287  mov     rcx, rbp
0x18001928a  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001928f  jmp     loc_18001934F
0x180019294  cmp     [rdi], r14w
0x180019298  jz      loc_180019336
0x18001929e  cmp     word ptr [rdi+2], 3Ah ; ':'
0x1800192a3  jz      loc_180019336
0x1800192a9  cmp     [rsi+60h], r14
0x1800192ad  jz      loc_18001935D
0x1800192b3  cmp     [rdi], bx
0x1800192b6  jnz     short loc_180019320
0x1800192b8  mov     r8d, 8; MaxCount
0x1800192be  lea     rdx, ?wchDevicePrefix@?CD@??GetFileName@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEBA_NPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z@4PAGA; "\\Device\\"
0x1800192c5  mov     rcx, rdi; String1
0x1800192c8  call    wcsncmp_0
0x1800192cd  test    eax, eax
0x1800192cf  jnz     short loc_1800192E7
0x1800192d1  xor     r8d, r8d
0x1800192d4  lea     rdx, Src
0x1800192db  mov     rcx, rbp
0x1800192de  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800192e3  xor     al, al
0x1800192e5  jmp     short loc_180019351
0x1800192e7  lea     rdx, aFiUnknown; "\\FI_UNKNOWN"
0x1800192ee  mov     rcx, rdi; String1
0x1800192f1  call    wcscmp_0
0x1800192f6  test    eax, eax
0x1800192f8  jz      short loc_180019336
0x1800192fa  add     rsi, 50h ; 'P'
0x1800192fe  cmp     qword ptr [rsi+18h], 8
0x180019303  jb      short loc_180019308
0x180019305  mov     rsi, [rsi]
0x180019308  movzx   r8d, word ptr [rsi]
0x18001930c  lea     rdx, aWcWs; "%wc:%ws"
0x180019313  mov     r9, rdi
0x180019316  mov     rcx, rbp
0x180019319  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Format(ushort const *,...)
0x18001931e  jmp     short loc_18001934F
0x180019320  lea     r8, [rsi+50h]
0x180019324  cmp     qword ptr [r8+18h], 8
0x180019329  jb      short loc_18001932E
0x18001932b  mov     r8, [r8]
0x18001932e  mov     r9, rdi
0x180019331  jmp     loc_1800191C6
0x180019336  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001933a  inc     r8
0x18001933d  cmp     [rdi+r8*2], r14w
0x180019342  jnz     short loc_18001933A
0x180019344  mov     rdx, rdi
0x180019347  mov     rcx, rbp
0x18001934a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001934f  mov     al, 1
0x180019351  add     rsp, 20h
0x180019355  pop     r14
0x180019357  pop     rdi
0x180019358  pop     rsi
0x180019359  pop     rbp
0x18001935a  pop     rbx
0x18001935b  retn
0x18001935d  mov     ecx, 8000FFFFh; int
0x180019362  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
