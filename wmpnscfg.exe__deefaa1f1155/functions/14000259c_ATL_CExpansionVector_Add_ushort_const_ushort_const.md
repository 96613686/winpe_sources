# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x14000259c`
- end: `0x140002800`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `612`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140002850`
- `0x140004d0c`
- `0x140005034`

## callees

- `0x1400011b0`
- `0x1400011bc`
- `0x14000259c`
- `0x140003004`
- `0x1400055c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140002752`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140002770`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140002752`
- `api-ms-win-crt-private-l1-1-0!_o__recalloc` at `0x140002770`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
_BOOL8 __fastcall ATL::CExpansionVector::Add(
        ATL::CExpansionVector *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r13
  const unsigned __int16 *v4; // r15
  ATL::CExpansionVector *v5; // r14
  int v6; // esi
  __int64 v7; // rax
  unsigned __int64 v8; // rax
  void *v9; // r12
  void *v10; // rdi
  __int64 v11; // rax
  void *v12; // rbx
  errno_t v13; // eax
  errno_t v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  rsize_t DestinationSize; // [rsp+28h] [rbp-50h]
  rsize_t SourceSize; // [rsp+38h] [rbp-40h]
  void *v29; // [rsp+98h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = this;
  v6 = 0;
  if ( a2 && a3 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    SourceSize = 2 * v7 + 2;
    v8 = 2 * SourceSize;
    if ( !is_mul_ok(SourceSize, 2u) )
      v8 = -1;
    try
    {
      v9 = operator new[](v8);
      v29 = v9;
    }
    catch ( ... )
    {
      v6 = 0;
      v5 = this;
      v3 = a3;
      v4 = a2;
      v9 = v29;
    }
    v10 = v9;
    v11 = -1;
    do
      ++v11;
    while ( v3[v11] );
    DestinationSize = 2LL * ((int)v11 + 1);
    v12 = operator new[](saturated_mul(DestinationSize, 2u));
    if ( !v9 || !v12 )
      goto LABEL_28;
    v13 = memcpy_s(v9, SourceSize, v4, SourceSize);
    if ( v13 )
    {
      if ( v13 == 12 )
        goto LABEL_33;
      if ( v13 == 22 || v13 == 34 )
        goto LABEL_32;
      if ( v13 != 80 )
        goto LABEL_31;
    }
    v14 = memcpy_s(v12, DestinationSize, v3, DestinationSize);
    if ( !v14 )
    {
LABEL_21:
      v15 = _o__recalloc(*(_QWORD *)v5, *((_DWORD *)v5 + 4) + 1, 8);
      if ( v15 )
      {
        *(_QWORD *)v5 = v15;
        v16 = _o__recalloc(*((_QWORD *)v5 + 1), *((_DWORD *)v5 + 4) + 1, 8);
        if ( v16 )
        {
          *((_QWORD *)v5 + 1) = v16;
          v17 = *((int *)v5 + 4);
          v18 = (_QWORD *)(*(_QWORD *)v5 + 8 * v17);
          if ( v18 )
            *v18 = v9;
          v19 = (_QWORD *)(*((_QWORD *)v5 + 1) + 8 * v17);
          if ( v19 )
            *v19 = v12;
          ++*((_DWORD *)v5 + 4);
          v10 = 0;
          v12 = 0;
          goto LABEL_29;
        }
      }
LABEL_28:
      v6 = -2147024882;
LABEL_29:
      operator delete(v12);
      operator delete(v10);
      return v6 >= 0;
    }
    if ( v14 != 12 )
    {
      if ( v14 != 22 && v14 != 34 )
      {
        if ( v14 == 80 )
          goto LABEL_21;
LABEL_31:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_32:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_33:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x14000259c  mov     [rsp+arg_10], r8
0x1400025a1  mov     [rsp+arg_8], rdx
0x1400025a6  mov     [rsp+arg_0], rcx
0x1400025ab  push    rbx
0x1400025ac  push    rsi
0x1400025ad  push    rdi
0x1400025ae  push    r12
0x1400025b0  push    r13
0x1400025b2  push    r14
0x1400025b4  push    r15
0x1400025b6  sub     rsp, 40h
0x1400025ba  mov     r13, r8
0x1400025bd  mov     r15, rdx
0x1400025c0  mov     r14, rcx
0x1400025c3  xor     esi, esi
0x1400025c5  test    rdx, rdx
0x1400025c8  jz      loc_1400027CD
0x1400025ce  test    r8, r8
0x1400025d1  jz      loc_1400027CD
0x1400025d7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400025db  mov     rax, rbx
0x1400025de  inc     rax
0x1400025e1  cmp     [rdx+rax*2], si
0x1400025e5  jnz     short loc_1400025DE
0x1400025e7  lea     rcx, ds:2[rax*2]
0x1400025ef  mov     [rsp+78h+SourceSize], rcx
0x1400025f4  mov     [rsp+78h+arg_18], rsi
0x1400025fc  mov     eax, 2
0x140002601  mul     rcx
0x140002604  cmovb   rax, rbx
0x140002608  mov     rcx, rax; unsigned __int64
0x14000260b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140002610  mov     r12, rax
0x140002613  mov     [rsp+78h+arg_18], rax
0x14000261b  jmp     short loc_140002643
0x14000261d  xor     esi, esi
0x14000261f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140002623  mov     r14, [rsp+78h+arg_0]
0x14000262b  mov     r13, [rsp+78h+arg_10]
0x140002633  mov     r15, [rsp+78h+arg_8]
0x14000263b  mov     r12, [rsp+78h+arg_18]
0x140002643  mov     rdi, r12
0x140002646  mov     [rsp+78h+var_48], r12
0x14000264b  mov     rax, rbx
0x14000264e  inc     rax
0x140002651  cmp     [r13+rax*2+0], si
0x140002657  jnz     short loc_14000264E
0x140002659  inc     eax
0x14000265b  movsxd  rcx, eax
0x14000265e  add     rcx, rcx
0x140002661  mov     [rsp+78h+DestinationSize], rcx
0x140002666  mov     [rsp+78h+var_58], rsi
0x14000266b  mov     eax, 2
0x140002670  mul     rcx
0x140002673  cmovb   rax, rbx
0x140002677  mov     rcx, rax; unsigned __int64
0x14000267a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000267f  mov     rbx, rax
0x140002682  mov     [rsp+78h+var_58], rax
0x140002687  jmp     short loc_1400026B5
0x140002689  xor     esi, esi
0x14000268b  mov     r14, [rsp+78h+arg_0]
0x140002693  mov     r13, [rsp+78h+arg_10]
0x14000269b  mov     r15, [rsp+78h+arg_8]
0x1400026a3  mov     r12, [rsp+78h+arg_18]
0x1400026ab  mov     rdi, [rsp+78h+var_48]
0x1400026b0  mov     rbx, [rsp+78h+var_58]
0x1400026b5  test    r12, r12
0x1400026b8  jz      loc_1400027AE
0x1400026be  test    rbx, rbx
0x1400026c1  jz      loc_1400027AE
0x1400026c7  mov     rdx, [rsp+78h+SourceSize]; DestinationSize
0x1400026cc  mov     r9, rdx; SourceSize
0x1400026cf  mov     r8, r15; Source
0x1400026d2  mov     rcx, r12; Destination
0x1400026d5  call    memcpy_s
0x1400026da  test    eax, eax
0x1400026dc  jz      short loc_140002702
0x1400026de  cmp     eax, 0Ch
0x1400026e1  jz      loc_1400027F5
0x1400026e7  cmp     eax, 16h
0x1400026ea  jz      loc_1400027EA
0x1400026f0  cmp     eax, 22h ; '"'
0x1400026f3  jz      loc_1400027EA
0x1400026f9  cmp     eax, 50h ; 'P'
0x1400026fc  jnz     loc_1400027DF
0x140002702  mov     r9, [rsp+78h+DestinationSize]; SourceSize
0x140002707  mov     r8, r13; Source
0x14000270a  mov     rdx, r9; DestinationSize
0x14000270d  mov     rcx, rbx; Destination
0x140002710  call    memcpy_s
0x140002715  test    eax, eax
0x140002717  jz      short loc_14000273D
0x140002719  cmp     eax, 0Ch
0x14000271c  jz      loc_1400027F5
0x140002722  cmp     eax, 16h
0x140002725  jz      loc_1400027EA
0x14000272b  cmp     eax, 22h ; '"'
0x14000272e  jz      loc_1400027EA
0x140002734  cmp     eax, 50h ; 'P'
0x140002737  jnz     loc_1400027DF
0x14000273d  mov     eax, [r14+10h]
0x140002741  inc     eax
0x140002743  movsxd  rdx, eax
0x140002746  mov     r15d, 8
0x14000274c  mov     r8d, r15d
0x14000274f  mov     rcx, [r14]
0x140002752  call    cs:__imp__o__recalloc
0x140002758  test    rax, rax
0x14000275b  jz      short loc_1400027AE
0x14000275d  mov     [r14], rax
0x140002760  mov     eax, [r14+10h]
0x140002764  inc     eax
0x140002766  movsxd  rdx, eax
0x140002769  mov     r8d, r15d
0x14000276c  mov     rcx, [r14+8]
0x140002770  call    cs:__imp__o__recalloc
0x140002776  test    rax, rax
0x140002779  jz      short loc_1400027AE
0x14000277b  mov     [r14+8], rax
0x14000277f  movsxd  rdx, dword ptr [r14+10h]
0x140002783  mov     rax, [r14]
0x140002786  lea     rcx, [rax+rdx*8]
0x14000278a  test    rcx, rcx
0x14000278d  jz      short loc_140002792
0x14000278f  mov     [rcx], r12
0x140002792  mov     rax, [r14+8]
0x140002796  lea     rcx, [rax+rdx*8]
0x14000279a  test    rcx, rcx
0x14000279d  jz      short loc_1400027A2
0x14000279f  mov     [rcx], rbx
0x1400027a2  inc     dword ptr [r14+10h]
0x1400027a6  mov     rdi, rsi
0x1400027a9  mov     rbx, rsi
0x1400027ac  jmp     short loc_1400027B3
0x1400027ae  mov     esi, 8007000Eh
0x1400027b3  not     esi
0x1400027b5  shr     esi, 1Fh
0x1400027b8  mov     rcx, rbx; Block
0x1400027bb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400027c0  nop
0x1400027c1  mov     rcx, rdi; Block
0x1400027c4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400027c9  mov     eax, esi
0x1400027cb  jmp     short loc_1400027CF
0x1400027cd  xor     eax, eax
0x1400027cf  add     rsp, 40h
0x1400027d3  pop     r15
0x1400027d5  pop     r14
0x1400027d7  pop     r13
0x1400027d9  pop     r12
0x1400027db  pop     rdi
0x1400027dc  pop     rsi
0x1400027dd  pop     rbx
0x1400027de  retn
0x1400027df  mov     ecx, 80004005h; int
0x1400027e4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400027ea  mov     ecx, 80070057h; int
0x1400027ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1400027f5  mov     ecx, 8007000Eh; int
0x1400027fa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
