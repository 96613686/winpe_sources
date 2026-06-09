# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180003814`
- end: `0x180003a00`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `492`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003ad0`
- `0x18000ce24`

## callees

- `0x1800012cc`
- `0x1800012d8`
- `0x180001820`
- `0x180003814`
- `0x1800041f8`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800038bd`
- `msvcrt!memcpy_s` at `0x1800038fd`
- `msvcrt!memcpy_s` at `0x1800038bd`
- `msvcrt!memcpy_s` at `0x1800038fd`

## pseudocode

```c
_BOOL8 __fastcall ATL::CExpansionVector::Add(void **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  void *v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r15
  void *v11; // rax
  void *v12; // rbx
  errno_t v13; // eax
  errno_t v14; // eax
  void *v15; // rax
  void *v16; // rcx
  void *v17; // rax
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  int v21; // esi

  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
    v8 = operator new[](saturated_mul(v7, 2u));
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v10 = 2LL * ((int)v9 + 1);
    v11 = operator new[](saturated_mul(v10, 2u));
    v12 = v11;
    if ( !v8 || !v11 )
      goto LABEL_26;
    v13 = memcpy_s(v8, v7, a2, v7);
    if ( v13 )
    {
      if ( v13 == 12 )
        goto LABEL_29;
      if ( v13 == 22 || v13 == 34 )
        goto LABEL_31;
      if ( v13 != 80 )
        goto LABEL_30;
    }
    v14 = memcpy_s(v12, v10, a3, v10);
    if ( !v14 )
    {
LABEL_19:
      v15 = _recalloc(*this, *((_DWORD *)this + 4) + 1, 8u);
      if ( v15 )
      {
        v16 = this[1];
        *this = v15;
        v17 = _recalloc(v16, *((_DWORD *)this + 4) + 1, 8u);
        if ( v17 )
        {
          v18 = *((int *)this + 4);
          this[1] = v17;
          v19 = (char *)*this + 8 * v18;
          if ( v19 )
            *v19 = v8;
          v20 = (char *)this[1] + 8 * v18;
          if ( v20 )
            *v20 = v12;
          ++*((_DWORD *)this + 4);
          v8 = 0;
          v21 = 0;
          v12 = 0;
          goto LABEL_27;
        }
      }
LABEL_26:
      v21 = -2147024882;
LABEL_27:
      operator delete[](v12);
      operator delete[](v8);
      return v21 >= 0;
    }
    if ( v14 != 12 )
    {
      if ( v14 != 22 && v14 != 34 )
      {
        if ( v14 == 80 )
          goto LABEL_19;
LABEL_30:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_31:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_29:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x180003814  push    rbx
0x180003816  push    rbp
0x180003817  push    rsi
0x180003818  push    rdi
0x180003819  push    r12
0x18000381b  push    r13
0x18000381d  push    r14
0x18000381f  push    r15
0x180003821  sub     rsp, 28h
0x180003825  xor     r13d, r13d
0x180003828  mov     r14, r8
0x18000382b  mov     rbp, rdx
0x18000382e  mov     rsi, rcx
0x180003831  test    rdx, rdx
0x180003834  jz      loc_1800039CB
0x18000383a  test    r8, r8
0x18000383d  jz      loc_1800039CB
0x180003843  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180003847  mov     rax, rbx
0x18000384a  inc     rax
0x18000384d  cmp     [rdx+rax*2], r13w
0x180003852  jnz     short loc_18000384A
0x180003854  lea     r12, ds:2[rax*2]
0x18000385c  mov     eax, 2
0x180003861  mul     r12
0x180003864  cmovb   rax, rbx
0x180003868  mov     rcx, rax; unsigned __int64
0x18000386b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003870  mov     rdi, rax
0x180003873  mov     rcx, rbx
0x180003876  inc     rcx
0x180003879  cmp     [r14+rcx*2], r13w
0x18000387e  jnz     short loc_180003876
0x180003880  inc     ecx
0x180003882  mov     eax, 2
0x180003887  movsxd  r15, ecx
0x18000388a  add     r15, r15
0x18000388d  mul     r15
0x180003890  cmovb   rax, rbx
0x180003894  mov     rcx, rax; unsigned __int64
0x180003897  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000389c  mov     rbx, rax
0x18000389f  test    rdi, rdi
0x1800038a2  jz      loc_1800039AD
0x1800038a8  test    rax, rax
0x1800038ab  jz      loc_1800039AD
0x1800038b1  mov     r9, r12; SourceSize
0x1800038b4  mov     r8, rbp; Source
0x1800038b7  mov     rdx, r12; DestinationSize
0x1800038ba  mov     rcx, rdi; Destination
0x1800038bd  call    cs:__imp_memcpy_s
0x1800038c4  nop     dword ptr [rax+rax+00h]
0x1800038c9  test    eax, eax
0x1800038cb  jz      short loc_1800038F1
0x1800038cd  cmp     eax, 0Ch
0x1800038d0  jz      loc_1800039DF
0x1800038d6  cmp     eax, 16h
0x1800038d9  jz      loc_1800039F5
0x1800038df  cmp     eax, 22h ; '"'
0x1800038e2  jz      loc_1800039F5
0x1800038e8  cmp     eax, 50h ; 'P'
0x1800038eb  jnz     loc_1800039EA
0x1800038f1  mov     r9, r15; SourceSize
0x1800038f4  mov     r8, r14; Source
0x1800038f7  mov     rdx, r15; DestinationSize
0x1800038fa  mov     rcx, rbx; Destination
0x1800038fd  call    cs:__imp_memcpy_s
0x180003904  nop     dword ptr [rax+rax+00h]
0x180003909  test    eax, eax
0x18000390b  jz      short loc_180003931
0x18000390d  cmp     eax, 0Ch
0x180003910  jz      loc_1800039DF
0x180003916  cmp     eax, 16h
0x180003919  jz      loc_1800039F5
0x18000391f  cmp     eax, 22h ; '"'
0x180003922  jz      loc_1800039F5
0x180003928  cmp     eax, 50h ; 'P'
0x18000392b  jnz     loc_1800039EA
0x180003931  mov     eax, [rsi+10h]
0x180003934  mov     ebp, 8
0x180003939  mov     rcx, [rsi]; Block
0x18000393c  inc     eax
0x18000393e  movsxd  rdx, eax; Count
0x180003941  mov     r8d, ebp; Size
0x180003944  call    cs:__imp__recalloc
0x18000394b  nop     dword ptr [rax+rax+00h]
0x180003950  test    rax, rax
0x180003953  jz      short loc_1800039AD
0x180003955  mov     rcx, [rsi+8]; Block
0x180003959  mov     r8d, ebp; Size
0x18000395c  mov     [rsi], rax
0x18000395f  mov     eax, [rsi+10h]
0x180003962  inc     eax
0x180003964  movsxd  rdx, eax; Count
0x180003967  call    cs:__imp__recalloc
0x18000396e  nop     dword ptr [rax+rax+00h]
0x180003973  test    rax, rax
0x180003976  jz      short loc_1800039AD
0x180003978  movsxd  rdx, dword ptr [rsi+10h]
0x18000397c  mov     [rsi+8], rax
0x180003980  mov     rax, [rsi]
0x180003983  lea     rcx, [rax+rdx*8]
0x180003987  test    rcx, rcx
0x18000398a  jz      short loc_18000398F
0x18000398c  mov     [rcx], rdi
0x18000398f  mov     rax, [rsi+8]
0x180003993  lea     rcx, [rax+rdx*8]
0x180003997  test    rcx, rcx
0x18000399a  jz      short loc_18000399F
0x18000399c  mov     [rcx], rbx
0x18000399f  inc     dword ptr [rsi+10h]
0x1800039a2  mov     rdi, r13
0x1800039a5  mov     esi, r13d
0x1800039a8  mov     rbx, r13
0x1800039ab  jmp     short loc_1800039B2
0x1800039ad  mov     esi, 8007000Eh
0x1800039b2  not     esi
0x1800039b4  mov     rcx, rbx; Block
0x1800039b7  shr     esi, 1Fh
0x1800039ba  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800039bf  mov     rcx, rdi; Block
0x1800039c2  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800039c7  mov     eax, esi
0x1800039c9  jmp     short loc_1800039CD
0x1800039cb  xor     eax, eax
0x1800039cd  add     rsp, 28h
0x1800039d1  pop     r15
0x1800039d3  pop     r14
0x1800039d5  pop     r13
0x1800039d7  pop     r12
0x1800039d9  pop     rdi
0x1800039da  pop     rsi
0x1800039db  pop     rbp
0x1800039dc  pop     rbx
0x1800039dd  retn
0x1800039df  mov     ecx, 8007000Eh; int
0x1800039e4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800039ea  mov     ecx, 80004005h; int
0x1800039ef  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800039f5  mov     ecx, 80070057h; int
0x1800039fa  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
