# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Insert(int,ushort)

- ea: `0x1800079b0`
- end: `0x180007a80`
- name: `?Insert@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHHG@Z`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800066cc`
- `0x1800079b0`
- `0x180008310`

## import_xrefs

- `msvcrt!memmove_s` at `0x180007a17`
- `msvcrt!memmove_s` at `0x180007a17`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Insert(
        __int64 *a1,
        int a2,
        __int64 a3)
{
  __int64 v3; // rax
  int v4; // r9d
  __int16 v6; // r14
  __int64 v7; // rbp
  int v8; // esi
  int v9; // ebx
  rsize_t v10; // r9
  _WORD *v11; // rsi
  errno_t v12; // eax
  __int64 result; // rax

  v3 = *a1;
  v4 = 0;
  v6 = a3;
  if ( a2 >= 0 )
    v4 = a2;
  v7 = *(int *)(v3 - 16);
  v8 = *(_DWORD *)(v3 - 16);
  if ( v4 <= (int)v7 )
    v8 = v4;
  v9 = v7 + 1;
  if ( (int)((*(_DWORD *)(v3 - 12) - (v7 + 1)) | (1 - *(_DWORD *)(v3 - 8))) < 0 )
    ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a1, (unsigned int)v9, a3);
  v10 = 2LL * (v9 - v8);
  v11 = (_WORD *)(*a1 + 2LL * v8);
  v12 = memmove_s(v11 + 1, v10, v11, v10);
  if ( v12 )
  {
    if ( v12 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v12 == 22 || v12 == 34 )
LABEL_15:
      ATL::AtlThrowImpl(-2147024809);
    if ( v12 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  *v11 = v6;
  if ( v9 < 0 || v9 > *(_DWORD *)(*a1 - 12) )
    goto LABEL_15;
  *(_DWORD *)(*a1 - 16) = v9;
  result = (unsigned int)v9;
  *(_WORD *)(*a1 + 2 * v7 + 2) = 0;
  return result;
}

```

## disassembly

```asm
0x1800079b0  push    rbx
0x1800079b2  push    rbp
0x1800079b3  push    rsi
0x1800079b4  push    rdi
0x1800079b5  push    r14
0x1800079b7  sub     rsp, 20h
0x1800079bb  mov     rax, [rcx]
0x1800079be  xor     r9d, r9d
0x1800079c1  test    edx, edx
0x1800079c3  mov     rdi, rcx
0x1800079c6  mov     ecx, 1
0x1800079cb  movzx   r14d, r8w
0x1800079cf  cmovns  r9d, edx
0x1800079d3  movsxd  rbp, dword ptr [rax-10h]
0x1800079d7  cmp     r9d, ebp
0x1800079da  mov     esi, ebp
0x1800079dc  cmovle  esi, r9d
0x1800079e0  sub     ecx, [rax-8]
0x1800079e3  mov     eax, [rax-0Ch]
0x1800079e6  lea     ebx, [rbp+1]
0x1800079e9  sub     eax, ebx
0x1800079eb  or      ecx, eax
0x1800079ed  jge     short loc_1800079F9
0x1800079ef  mov     edx, ebx
0x1800079f1  mov     rcx, rdi
0x1800079f4  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x1800079f9  mov     eax, ebx
0x1800079fb  movsxd  rcx, esi
0x1800079fe  sub     eax, esi
0x180007a00  movsxd  rdx, eax
0x180007a03  mov     rax, [rdi]
0x180007a06  add     rdx, rdx; DestinationSize
0x180007a09  mov     r9, rdx; SourceSize
0x180007a0c  lea     rsi, [rax+rcx*2]
0x180007a10  lea     rcx, [rsi+2]; Destination
0x180007a14  mov     r8, rsi; Source
0x180007a17  call    cs:__imp_memmove_s
0x180007a1d  test    eax, eax
0x180007a1f  jz      short loc_180007A35
0x180007a21  cmp     eax, 0Ch
0x180007a24  jz      short loc_180007A75
0x180007a26  cmp     eax, 16h
0x180007a29  jz      short loc_180007A5F
0x180007a2b  cmp     eax, 22h ; '"'
0x180007a2e  jz      short loc_180007A5F
0x180007a30  cmp     eax, 50h ; 'P'
0x180007a33  jnz     short loc_180007A6A
0x180007a35  mov     [rsi], r14w
0x180007a39  test    ebx, ebx
0x180007a3b  js      short loc_180007A5F
0x180007a3d  mov     rax, [rdi]
0x180007a40  cmp     ebx, [rax-0Ch]
0x180007a43  jg      short loc_180007A5F
0x180007a45  mov     [rax-10h], ebx
0x180007a48  xor     ecx, ecx
0x180007a4a  mov     rdx, [rdi]
0x180007a4d  mov     eax, ebx
0x180007a4f  mov     [rdx+rbp*2+2], cx
0x180007a54  add     rsp, 20h
0x180007a58  pop     r14
0x180007a5a  pop     rdi
0x180007a5b  pop     rsi
0x180007a5c  pop     rbp
0x180007a5d  pop     rbx
0x180007a5e  retn
0x180007a5f  mov     ecx, 80070057h; int
0x180007a64  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007a6a  mov     ecx, 80004005h; int
0x180007a6f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007a75  mov     ecx, 8007000Eh; int
0x180007a7a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
