# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort const *)

- ea: `0x180011584`
- end: `0x18001166f`
- name: `?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHPEBG@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180011308`

## callees

- `0x180003870`
- `0x18000c228`
- `0x180011584`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800115dc`
- `msvcrt!memmove_s` at `0x1800115dc`
- `msvcrt!memcpy_s` at `0x18001160c`
- `msvcrt!memcpy_s` at `0x18001160c`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
        _QWORD *a1)
{
  int v1; // ebp
  __int64 v3; // rsi
  int v4; // ebx
  rsize_t v5; // r9
  __int64 v6; // rbp
  errno_t v7; // eax
  errno_t v8; // eax
  __int64 result; // rax

  v1 = 23;
  v3 = *(int *)(*a1 - 16LL);
  if ( (int)v3 < 23 )
    v1 = *(_DWORD *)(*a1 - 16LL);
  v4 = v3 + 3;
  if ( (int)((*(_DWORD *)(*a1 - 12LL) - (v3 + 3)) | (1 - *(_DWORD *)(*a1 - 8LL))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v4);
  v5 = 2LL * ((int)v3 - v1 + 1);
  v6 = *a1 + 2LL * v1;
  v7 = memmove_s((void *const)(v6 + 6), v5, (const void *const)v6, v5);
  if ( v7 )
  {
    if ( v7 == 12 )
      goto LABEL_20;
    if ( v7 == 22 || v7 == 34 )
      goto LABEL_18;
    if ( v7 != 80 )
      goto LABEL_19;
  }
  v8 = memcpy_s((void *const)v6, 6u, L"...", 6u);
  if ( v8 )
  {
    if ( v8 != 12 )
    {
      if ( v8 != 22 && v8 != 34 )
      {
        if ( v8 == 80 )
          goto LABEL_15;
LABEL_19:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_18:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_20:
    ATL::AtlThrowImpl(-2147024882);
  }
LABEL_15:
  if ( v4 < 0 || v4 > *(_DWORD *)(*a1 - 12LL) )
    goto LABEL_18;
  *(_DWORD *)(*a1 - 16LL) = v4;
  result = (unsigned int)v4;
  *(_WORD *)(*a1 + 2 * v3 + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x180011584  push    rbx
0x180011586  push    rbp
0x180011587  push    rsi
0x180011588  push    rdi
0x180011589  sub     rsp, 28h
0x18001158d  mov     rax, [rcx]
0x180011590  mov     ebp, 17h
0x180011595  mov     edx, 1
0x18001159a  mov     rdi, rcx
0x18001159d  movsxd  rsi, dword ptr [rax-10h]
0x1800115a1  cmp     esi, ebp
0x1800115a3  cmovl   ebp, esi
0x1800115a6  sub     edx, [rax-8]
0x1800115a9  mov     eax, [rax-0Ch]
0x1800115ac  lea     ebx, [rsi+3]
0x1800115af  sub     eax, ebx
0x1800115b1  or      edx, eax
0x1800115b3  jge     short loc_1800115BC
0x1800115b5  mov     edx, ebx
0x1800115b7  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800115bc  mov     eax, esi
0x1800115be  movsxd  rcx, ebp
0x1800115c1  sub     eax, ebp
0x1800115c3  inc     eax
0x1800115c5  movsxd  rdx, eax
0x1800115c8  mov     rax, [rdi]
0x1800115cb  add     rdx, rdx; DestinationSize
0x1800115ce  mov     r9, rdx; SourceSize
0x1800115d1  lea     rbp, [rax+rcx*2]
0x1800115d5  lea     rcx, [rbp+6]; Destination
0x1800115d9  mov     r8, rbp; Source
0x1800115dc  call    cs:__imp_memmove_s
0x1800115e2  test    eax, eax
0x1800115e4  jz      short loc_1800115FA
0x1800115e6  cmp     eax, 0Ch
0x1800115e9  jz      short loc_180011664
0x1800115eb  cmp     eax, 16h
0x1800115ee  jz      short loc_18001164E
0x1800115f0  cmp     eax, 22h ; '"'
0x1800115f3  jz      short loc_18001164E
0x1800115f5  cmp     eax, 50h ; 'P'
0x1800115f8  jnz     short loc_180011659
0x1800115fa  mov     edx, 6; DestinationSize
0x1800115ff  lea     r8, asc_180021110; "..."
0x180011606  mov     r9d, edx; SourceSize
0x180011609  mov     rcx, rbp; Destination
0x18001160c  call    cs:__imp_memcpy_s
0x180011612  test    eax, eax
0x180011614  jz      short loc_18001162A
0x180011616  cmp     eax, 0Ch
0x180011619  jz      short loc_180011664
0x18001161b  cmp     eax, 16h
0x18001161e  jz      short loc_18001164E
0x180011620  cmp     eax, 22h ; '"'
0x180011623  jz      short loc_18001164E
0x180011625  cmp     eax, 50h ; 'P'
0x180011628  jnz     short loc_180011659
0x18001162a  test    ebx, ebx
0x18001162c  js      short loc_18001164E
0x18001162e  mov     rax, [rdi]
0x180011631  cmp     ebx, [rax-0Ch]
0x180011634  jg      short loc_18001164E
0x180011636  mov     [rax-10h], ebx
0x180011639  xor     ecx, ecx
0x18001163b  mov     rdx, [rdi]
0x18001163e  mov     eax, ebx
0x180011640  mov     [rdx+rsi*2+6], cx
0x180011645  add     rsp, 28h
0x180011649  pop     rdi
0x18001164a  pop     rsi
0x18001164b  pop     rbp
0x18001164c  pop     rbx
0x18001164d  retn
0x18001164e  mov     ecx, 80070057h; int
0x180011653  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011659  mov     ecx, 80004005h; int
0x18001165e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011664  mov     ecx, 8007000Eh; int
0x180011669  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
