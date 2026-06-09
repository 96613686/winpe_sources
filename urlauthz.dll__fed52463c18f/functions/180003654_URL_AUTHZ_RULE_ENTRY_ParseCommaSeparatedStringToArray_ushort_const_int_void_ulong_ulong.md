# URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(ushort const *,int,void * *,ulong *,ulong *)

- ea: `0x180003654`
- end: `0x180003907`
- name: `?ParseCommaSeparatedStringToArray@URL_AUTHZ_RULE_ENTRY@@AEAAJPEBGHPEAPEAXPEAK2@Z`
- size: `691`
- prototype: `__int64 __fastcall(URL_AUTHZ_RULE_ENTRY *__hidden this, const unsigned __int16 *, int, void **, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800032f8`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003654`
- `0x180004010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@XZ` at `0x180003757`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800036fb`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003812`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003812`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x18000381d`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBGK@Z` at `0x18000381d`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800038ba`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003882`

## pseudocode

```c
__int64 __fastcall URL_AUTHZ_RULE_ENTRY::ParseCommaSeparatedStringToArray(
        URL_AUTHZ_RULE_ENTRY *this,
        const unsigned __int16 *a2,
        int a3,
        void **a4,
        unsigned int *a5,
        unsigned int *a6)
{
  const unsigned __int16 *v8; // rbx
  unsigned int v9; // ecx
  unsigned __int16 v10; // dx
  const unsigned __int16 *v11; // r8
  bool v12; // zf
  unsigned int v13; // eax
  __int64 v14; // rdi
  __int64 v15; // rax
  bool v16; // cf
  size_t v17; // rax
  _QWORD *v18; // rax
  const unsigned __int16 *v19; // rdx
  const unsigned __int16 *v20; // r8
  __int64 v21; // r9
  _QWORD *v22; // rbp
  _QWORD *i; // rsi
  _QWORD *v24; // r14
  __int64 v25; // rax
  size_t v26; // rax
  _QWORD *v27; // rax
  _QWORD *j; // rsi
  unsigned int v29; // edi
  unsigned int v30; // esi
  const unsigned __int16 *v31; // rax
  int v32; // eax
  __int64 v33; // r8
  __int64 v34; // rcx
  int v35; // eax
  unsigned __int16 v36; // ax
  void *v37; // rax
  __int64 v38; // rbx
  _QWORD *k; // rsi
  __int64 v40; // rbx
  _QWORD *m; // rsi

  v8 = a2;
  if ( !a2 || !*a2 )
  {
    *a4 = 0;
    *a5 = 0;
    return 0;
  }
  v9 = 1;
  if ( a6 )
    *a6 = 0;
  v10 = *a2;
  if ( v10 )
  {
    v11 = v8;
    do
    {
      v12 = v10 == 44;
      v13 = v9 + 1;
      v10 = *++v11;
      if ( !v12 )
        v13 = v9;
      v9 = v13;
    }
    while ( v10 );
  }
  v14 = v9;
  if ( a3 )
  {
    v15 = 56LL * v9;
    if ( !is_mul_ok(v9, 0x38u) )
      v15 = -1;
    v16 = __CFADD__(v15, 8);
    v17 = v15 + 8;
    if ( v16 )
      v17 = -1;
    v18 = operator new(v17);
    v21 = 0;
    if ( v18 )
    {
      *v18 = v14;
      v22 = v18 + 1;
      for ( i = v18 + 1; v14; --v14 )
      {
        ((void (__fastcall *)(_QWORD *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))STRU::STRU)(
          i,
          v19,
          v20,
          0);
        v21 = 0;
        i += 7;
      }
      if ( v22 )
      {
        v24 = 0;
        goto LABEL_29;
      }
    }
    return (unsigned int)-2147024888;
  }
  v25 = 56LL * v9;
  if ( !is_mul_ok(v9, 0x38u) )
    v25 = -1;
  v16 = __CFADD__(v25, 8);
  v26 = v25 + 8;
  if ( v16 )
    v26 = -1;
  v27 = operator new(v26);
  v21 = 0;
  if ( !v27 )
    return (unsigned int)-2147024888;
  *v27 = v14;
  v24 = v27 + 1;
  for ( j = v27 + 1; v14; --v14 )
  {
    ((void (__fastcall *)(_QWORD *, const unsigned __int16 *, const unsigned __int16 *, _QWORD))STRA::STRA)(
      j,
      v19,
      v20,
      0);
    v21 = 0;
    j += 7;
  }
  if ( !v24 )
    return (unsigned int)-2147024888;
  v22 = 0;
LABEL_29:
  v29 = 0;
  v30 = 0;
LABEL_53:
  v36 = *v8;
  while ( v36 )
  {
    if ( v36 == 32 )
    {
      do
        ++v8;
      while ( *v8 == 32 );
    }
    v19 = v8;
    while ( *v8 != 44 && *v8 )
      ++v8;
    v20 = v8;
    if ( v19 != v8 )
    {
      do
      {
        v31 = v20 - 1;
        if ( *(v20 - 1) != 32 )
          break;
        --v20;
      }
      while ( v19 != v31 );
    }
    if ( !a6 || (char *)v20 - (char *)v19 != 2 )
    {
LABEL_46:
      v33 = v20 - v19;
      v34 = 7LL * v30;
      if ( a3 )
        v35 = STRU::Copy((STRU *)&v22[v34], v19, v33);
      else
        v35 = STRA::CopyWTruncate((STRA *)&v24[v34], v19, v33);
      v21 = 0;
      v29 = v35;
      if ( v35 < 0 )
        goto LABEL_59;
      ++v30;
      goto LABEL_51;
    }
    v32 = 1;
    if ( *v19 == 42 )
    {
      *a6 |= 2u;
      v32 = 0;
    }
    if ( *v19 == 63 )
    {
      *a6 |= 1u;
    }
    else if ( v32 )
    {
      goto LABEL_46;
    }
LABEL_51:
    v36 = *v8;
    if ( *v8 == 44 )
    {
      ++v8;
      goto LABEL_53;
    }
  }
  if ( a3 )
  {
    v37 = v22;
    v22 = 0;
  }
  else
  {
    v37 = v24;
    v24 = 0;
  }
  *a4 = v37;
  *a5 = v30;
LABEL_59:
  if ( v22 )
  {
    v38 = *(v22 - 1);
    for ( k = &v22[7 * v38]; v38; --v38 )
    {
      k -= 7;
      ((void (__fastcall *)(_QWORD *, const unsigned __int16 *, const unsigned __int16 *, __int64))STRU::~STRU)(
        k,
        v19,
        v20,
        v21);
    }
    operator delete(v22 - 1);
  }
  if ( v24 )
  {
    v40 = *(v24 - 1);
    for ( m = &v24[7 * v40]; v40; --v40 )
    {
      m -= 7;
      ((void (__fastcall *)(_QWORD *, const unsigned __int16 *, const unsigned __int16 *, __int64))STRA::~STRA)(
        m,
        v19,
        v20,
        v21);
    }
    operator delete(v24 - 1);
  }
  return v29;
}

```

## disassembly

```asm
0x180003654  push    rbx
0x180003656  push    rbp
0x180003657  push    rsi
0x180003658  push    rdi
0x180003659  push    r12
0x18000365b  push    r13
0x18000365d  push    r14
0x18000365f  push    r15
0x180003661  sub     rsp, 28h
0x180003665  xor     ebp, ebp
0x180003667  mov     r13, r9
0x18000366a  mov     r12d, r8d
0x18000366d  mov     rbx, rdx
0x180003670  test    rdx, rdx
0x180003673  jz      loc_1800038E7
0x180003679  cmp     [rdx], bp
0x18000367c  jz      loc_1800038E7
0x180003682  mov     r15, [rsp+68h+arg_28]
0x18000368a  lea     ecx, [rbp+1]
0x18000368d  test    r15, r15
0x180003690  jz      short loc_180003695
0x180003692  mov     [r15], ebp
0x180003695  movzx   edx, word ptr [rdx]
0x180003698  test    dx, dx
0x18000369b  jz      short loc_1800036B9
0x18000369d  mov     r8, rbx
0x1800036a0  cmp     dx, 2Ch ; ','
0x1800036a4  lea     eax, [rcx+1]
0x1800036a7  lea     r8, [r8+2]
0x1800036ab  movzx   edx, word ptr [r8]
0x1800036af  cmovnz  eax, ecx
0x1800036b2  mov     ecx, eax
0x1800036b4  test    dx, dx
0x1800036b7  jnz     short loc_1800036A0
0x1800036b9  mov     edi, ecx
0x1800036bb  mov     eax, 38h ; '8'
0x1800036c0  lea     rcx, [rax-39h]
0x1800036c4  test    r12d, r12d
0x1800036c7  jz      short loc_180003725
0x1800036c9  mul     rdi
0x1800036cc  cmovb   rax, rcx
0x1800036d0  add     rax, 8
0x1800036d4  cmovb   rax, rcx
0x1800036d8  mov     rcx, rax; Size
0x1800036db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800036e0  xor     r9d, r9d
0x1800036e3  test    rax, rax
0x1800036e6  jz      loc_1800038DE
0x1800036ec  mov     [rax], rdi
0x1800036ef  lea     rbp, [rax+8]
0x1800036f3  mov     rsi, rbp
0x1800036f6  test    rdi, rdi
0x1800036f9  jz      short loc_180003717
0x1800036fb  mov     rax, cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180003702  mov     rcx, rsi
0x180003705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370a  xor     r9d, r9d
0x18000370d  add     rsi, 38h ; '8'
0x180003711  sub     rdi, 1
0x180003715  jnz     short loc_1800036FB
0x180003717  test    rbp, rbp
0x18000371a  jz      loc_1800038DE
0x180003720  mov     r14, r9
0x180003723  jmp     short loc_18000377F
0x180003725  mul     rdi
0x180003728  cmovb   rax, rcx
0x18000372c  add     rax, 8
0x180003730  cmovb   rax, rcx
0x180003734  mov     rcx, rax; Size
0x180003737  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000373c  xor     r9d, r9d
0x18000373f  test    rax, rax
0x180003742  jz      loc_1800038DE
0x180003748  mov     [rax], rdi
0x18000374b  lea     r14, [rax+8]
0x18000374f  mov     rsi, r14
0x180003752  test    rdi, rdi
0x180003755  jz      short loc_180003773
0x180003757  mov     rax, cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18000375e  mov     rcx, rsi
0x180003761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003766  xor     r9d, r9d
0x180003769  add     rsi, 38h ; '8'
0x18000376d  sub     rdi, 1
0x180003771  jnz     short loc_180003757
0x180003773  test    r14, r14
0x180003776  jz      loc_1800038DE
0x18000377c  mov     rbp, r9
0x18000377f  mov     edi, r9d
0x180003782  mov     esi, r9d
0x180003785  jmp     loc_18000383B
0x18000378a  cmp     ax, 20h ; ' '
0x18000378e  jnz     short loc_18000379A
0x180003790  add     rbx, 2
0x180003794  cmp     word ptr [rbx], 20h ; ' '
0x180003798  jz      short loc_180003790
0x18000379a  mov     rdx, rbx
0x18000379d  jmp     short loc_1800037A8
0x18000379f  test    ax, ax
0x1800037a2  jz      short loc_1800037B1
0x1800037a4  add     rbx, 2
0x1800037a8  movzx   eax, word ptr [rbx]
0x1800037ab  cmp     ax, 2Ch ; ','
0x1800037af  jnz     short loc_18000379F
0x1800037b1  mov     r8, rbx
0x1800037b4  cmp     rdx, rbx
0x1800037b7  jz      short loc_1800037CB
0x1800037b9  lea     rax, [r8-2]
0x1800037bd  cmp     word ptr [rax], 20h ; ' '
0x1800037c1  jnz     short loc_1800037CB
0x1800037c3  mov     r8, rax
0x1800037c6  cmp     rdx, rax
0x1800037c9  jnz     short loc_1800037B9
0x1800037cb  test    r15, r15
0x1800037ce  jz      short loc_1800037FE
0x1800037d0  mov     rax, r8
0x1800037d3  sub     rax, rdx
0x1800037d6  cmp     rax, 2
0x1800037da  jnz     short loc_1800037FE
0x1800037dc  cmp     word ptr [rdx], 2Ah ; '*'
0x1800037e0  mov     eax, 1
0x1800037e5  jnz     short loc_1800037EE
0x1800037e7  or      dword ptr [r15], 2
0x1800037eb  mov     eax, r9d
0x1800037ee  cmp     word ptr [rdx], 3Fh ; '?'
0x1800037f2  jnz     short loc_1800037FA
0x1800037f4  or      dword ptr [r15], 1
0x1800037f8  jmp     short loc_18000382E
0x1800037fa  test    eax, eax
0x1800037fc  jz      short loc_18000382E
0x1800037fe  sub     r8, rdx
0x180003801  mov     eax, esi
0x180003803  sar     r8, 1
0x180003806  imul    rcx, rax, 38h ; '8'
0x18000380a  test    r12d, r12d
0x18000380d  jz      short loc_18000381A
0x18000380f  add     rcx, rbp
0x180003812  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180003818  jmp     short loc_180003823
0x18000381a  add     rcx, r14
0x18000381d  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBGK@Z; STRA::CopyWTruncate(ushort const *,ulong)
0x180003823  xor     r9d, r9d
0x180003826  mov     edi, eax
0x180003828  test    eax, eax
0x18000382a  js      short loc_180003868
0x18000382c  inc     esi
0x18000382e  movzx   eax, word ptr [rbx]
0x180003831  cmp     ax, 2Ch ; ','
0x180003835  jnz     short loc_18000383E
0x180003837  add     rbx, 2
0x18000383b  movzx   eax, word ptr [rbx]
0x18000383e  test    ax, ax
0x180003841  jnz     loc_18000378A
0x180003847  test    r12d, r12d
0x18000384a  jz      short loc_180003854
0x18000384c  mov     rax, rbp
0x18000384f  mov     rbp, r9
0x180003852  jmp     short loc_18000385A
0x180003854  mov     rax, r14
0x180003857  mov     r14, r9
0x18000385a  mov     [r13+0], rax
0x18000385e  mov     rax, [rsp+68h+arg_20]
0x180003866  mov     [rax], esi
0x180003868  test    rbp, rbp
0x18000386b  jz      short loc_1800038A3
0x18000386d  lea     r15, [rbp-8]
0x180003871  mov     rbx, [r15]
0x180003874  imul    rsi, rbx, 38h ; '8'
0x180003878  add     rsi, rbp
0x18000387b  test    rbx, rbx
0x18000387e  jz      short loc_18000389B
0x180003880  xor     ebp, ebp
0x180003882  mov     rax, cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003889  sub     rsi, 38h ; '8'
0x18000388d  mov     rcx, rsi
0x180003890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003895  sub     rbx, 1
0x180003899  jnz     short loc_180003882
0x18000389b  mov     rcx, r15; Block
0x18000389e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038a3  test    r14, r14
0x1800038a6  jz      short loc_1800038E3
0x1800038a8  mov     rbx, [r14-8]
0x1800038ac  imul    rsi, rbx, 38h ; '8'
0x1800038b0  add     rsi, r14
0x1800038b3  test    rbx, rbx
0x1800038b6  jz      short loc_1800038D3
0x1800038b8  xor     ebp, ebp
0x1800038ba  mov     rax, cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800038c1  sub     rsi, 38h ; '8'
0x1800038c5  mov     rcx, rsi
0x1800038c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038cd  sub     rbx, 1
0x1800038d1  jnz     short loc_1800038BA
0x1800038d3  lea     rcx, [r14-8]; Block
0x1800038d7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800038dc  jmp     short loc_1800038E3
0x1800038de  mov     edi, 80070008h
0x1800038e3  mov     eax, edi
0x1800038e5  jmp     short loc_1800038F6
0x1800038e7  mov     rax, [rsp+68h+arg_20]
0x1800038ef  mov     [r9], rbp
0x1800038f2  mov     [rax], ebp
0x1800038f4  xor     eax, eax
0x1800038f6  add     rsp, 28h
0x1800038fa  pop     r15
0x1800038fc  pop     r14
0x1800038fe  pop     r13
0x180003900  pop     r12
0x180003902  pop     rdi
0x180003903  pop     rsi
0x180003904  pop     rbp
0x180003905  pop     rbx
0x180003906  retn
```
