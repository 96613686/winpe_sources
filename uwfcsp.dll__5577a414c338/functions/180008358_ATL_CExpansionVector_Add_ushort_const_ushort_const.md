# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x180008358`
- end: `0x18000852d`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `469`
- prototype: `_BOOL8 __fastcall(void **this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800085c0`
- `0x18000bb3c`
- `0x18000be5c`

## callees

- `0x180002c8c`
- `0x180003b60`
- `0x180008358`
- `0x180008c94`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180008401`
- `msvcrt!memcpy_s` at `0x18000843b`
- `msvcrt!memcpy_s` at `0x180008401`
- `msvcrt!memcpy_s` at `0x18000843b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800084e6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800084ef`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800084e6`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800084ef`

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
0x180008358  push    rbx
0x18000835a  push    rbp
0x18000835b  push    rsi
0x18000835c  push    rdi
0x18000835d  push    r12
0x18000835f  push    r13
0x180008361  push    r14
0x180008363  push    r15
0x180008365  sub     rsp, 28h
0x180008369  xor     r13d, r13d
0x18000836c  mov     r14, r8
0x18000836f  mov     rbp, rdx
0x180008372  mov     rsi, rcx
0x180008375  test    rdx, rdx
0x180008378  jz      loc_1800084F9
0x18000837e  test    r8, r8
0x180008381  jz      loc_1800084F9
0x180008387  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000838b  mov     rax, rbx
0x18000838e  inc     rax
0x180008391  cmp     [rdx+rax*2], r13w
0x180008396  jnz     short loc_18000838E
0x180008398  lea     r12, ds:2[rax*2]
0x1800083a0  mov     eax, 2
0x1800083a5  mul     r12
0x1800083a8  cmovb   rax, rbx
0x1800083ac  mov     rcx, rax; unsigned __int64
0x1800083af  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800083b4  mov     rdi, rax
0x1800083b7  mov     rcx, rbx
0x1800083ba  inc     rcx
0x1800083bd  cmp     [r14+rcx*2], r13w
0x1800083c2  jnz     short loc_1800083BA
0x1800083c4  inc     ecx
0x1800083c6  mov     eax, 2
0x1800083cb  movsxd  r15, ecx
0x1800083ce  add     r15, r15
0x1800083d1  mul     r15
0x1800083d4  cmovb   rax, rbx
0x1800083d8  mov     rcx, rax; unsigned __int64
0x1800083db  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800083e0  mov     rbx, rax
0x1800083e3  test    rdi, rdi
0x1800083e6  jz      loc_1800084D9
0x1800083ec  test    rax, rax
0x1800083ef  jz      loc_1800084D9
0x1800083f5  mov     r9, r12; SourceSize
0x1800083f8  mov     r8, rbp; Source
0x1800083fb  mov     rdx, r12; DestinationSize
0x1800083fe  mov     rcx, rdi; Destination
0x180008401  call    cs:__imp_memcpy_s
0x180008407  test    eax, eax
0x180008409  jz      short loc_18000842F
0x18000840b  cmp     eax, 0Ch
0x18000840e  jz      loc_18000850C
0x180008414  cmp     eax, 16h
0x180008417  jz      loc_180008522
0x18000841d  cmp     eax, 22h ; '"'
0x180008420  jz      loc_180008522
0x180008426  cmp     eax, 50h ; 'P'
0x180008429  jnz     loc_180008517
0x18000842f  mov     r9, r15; SourceSize
0x180008432  mov     r8, r14; Source
0x180008435  mov     rdx, r15; DestinationSize
0x180008438  mov     rcx, rbx; Destination
0x18000843b  call    cs:__imp_memcpy_s
0x180008441  test    eax, eax
0x180008443  jz      short loc_180008469
0x180008445  cmp     eax, 0Ch
0x180008448  jz      loc_18000850C
0x18000844e  cmp     eax, 16h
0x180008451  jz      loc_180008522
0x180008457  cmp     eax, 22h ; '"'
0x18000845a  jz      loc_180008522
0x180008460  cmp     eax, 50h ; 'P'
0x180008463  jnz     loc_180008517
0x180008469  mov     eax, [rsi+10h]
0x18000846c  mov     ebp, 8
0x180008471  mov     rcx, [rsi]; Block
0x180008474  inc     eax
0x180008476  movsxd  rdx, eax; Count
0x180008479  mov     r8d, ebp; Size
0x18000847c  call    cs:__imp__recalloc
0x180008482  test    rax, rax
0x180008485  jz      short loc_1800084D9
0x180008487  mov     rcx, [rsi+8]; Block
0x18000848b  mov     r8d, ebp; Size
0x18000848e  mov     [rsi], rax
0x180008491  mov     eax, [rsi+10h]
0x180008494  inc     eax
0x180008496  movsxd  rdx, eax; Count
0x180008499  call    cs:__imp__recalloc
0x18000849f  test    rax, rax
0x1800084a2  jz      short loc_1800084D9
0x1800084a4  movsxd  rdx, dword ptr [rsi+10h]
0x1800084a8  mov     [rsi+8], rax
0x1800084ac  mov     rax, [rsi]
0x1800084af  lea     rcx, [rax+rdx*8]
0x1800084b3  test    rcx, rcx
0x1800084b6  jz      short loc_1800084BB
0x1800084b8  mov     [rcx], rdi
0x1800084bb  mov     rax, [rsi+8]
0x1800084bf  lea     rcx, [rax+rdx*8]
0x1800084c3  test    rcx, rcx
0x1800084c6  jz      short loc_1800084CB
0x1800084c8  mov     [rcx], rbx
0x1800084cb  inc     dword ptr [rsi+10h]
0x1800084ce  mov     rdi, r13
0x1800084d1  mov     esi, r13d
0x1800084d4  mov     rbx, r13
0x1800084d7  jmp     short loc_1800084DE
0x1800084d9  mov     esi, 8007000Eh
0x1800084de  not     esi
0x1800084e0  mov     rcx, rbx
0x1800084e3  shr     esi, 1Fh
0x1800084e6  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800084ec  mov     rcx, rdi
0x1800084ef  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800084f5  mov     eax, esi
0x1800084f7  jmp     short loc_1800084FB
0x1800084f9  xor     eax, eax
0x1800084fb  add     rsp, 28h
0x1800084ff  pop     r15
0x180008501  pop     r14
0x180008503  pop     r13
0x180008505  pop     r12
0x180008507  pop     rdi
0x180008508  pop     rsi
0x180008509  pop     rbp
0x18000850a  pop     rbx
0x18000850b  retn
0x18000850c  mov     ecx, 8007000Eh; int
0x180008511  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008517  mov     ecx, 80004005h; int
0x18000851c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180008522  mov     ecx, 80070057h; int
0x180008527  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
