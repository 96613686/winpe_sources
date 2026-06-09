# CEsExecBase::Init(CEsCompBase const *,CEsExecContext *,IBlobHandleFactory *)

- ea: `0x100404990`
- end: `0x100404a78`
- name: `?Init@CEsExecBase@@QEAAXPEBVCEsCompBase@@PEAVCEsExecContext@@PEAUIBlobHandleFactory@@@Z`
- size: `232`
- prototype: `void __fastcall(CEsExecBase *__hidden this, const struct CEsCompBase *, struct CEsExecContext *, struct IBlobHandleFactory *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100404890`
- `0x10080d790`
- `0x10080e7c0`

## callees

- `0x1004011fc`
- `0x100404990`
- `0x100404a80`
- `0x10083c470`

## import_xrefs

- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100402378`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004023c1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004dadd8`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x100402378`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004023c1`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z` at `0x1004dadd8`

## string_xrefs

- `0x1004dadc4`: `sql\ntdbms\msql\expr\runtime\esx_compinfoseg.cpp`

## pseudocode

```c
void __fastcall CEsExecBase::Init(
        CEsExecBase *this,
        const struct CEsCompBase *a2,
        struct IMemObj **a3,
        struct IBlobHandleFactory *a4)
{
  unsigned __int64 v4; // rax
  void *v5; // rax
  __int64 v6; // rbx
  void *v7; // rax
  unsigned __int64 v8; // rdx
  __int64 v9; // rsi
  const struct CEsCompBase *v12; // rcx
  struct IMemObj *v14; // r12
  unsigned __int16 v15; // ax
  __int16 v16; // cx
  unsigned __int16 v17; // bx
  unsigned __int16 i; // r14
  struct IMemObj *v19; // r9
  __int64 j; // r8
  int v21; // edx
  int v22; // r8d
  __int64 v23; // r14
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rax
  void *v26; // rax
  __int64 v27; // rbx
  __int64 v28; // rcx

  v9 = 0;
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 9) = a3;
  v12 = a2;
  if ( (*((_BYTE *)a2 + 8) & 8) != 0 )
    goto LABEL_6;
  v14 = *a3;
  *((_QWORD *)this + 10) = a4;
  v15 = *((_WORD *)a2 + 10);
  v16 = *((_WORD *)a2 + 9);
  v17 = v16 + v15;
  if ( (unsigned __int16)(v16 + v15) < v15 )
  {
    v17 = -1;
    _mm_lfence();
    IntSafeWrapperRtlAssertFailure(-2147024362, *((unsigned __int16 *)a2 + 10), *((unsigned __int16 *)a2 + 9));
    goto LABEL_10;
  }
  if ( v17 )
  {
LABEL_10:
    _mm_lfence();
    v4 = 8LL * v17;
    if ( !is_mul_ok(v17, 8u) )
      v4 = -1;
    v5 = operator new[](v4, v14, "sql\\ntdbms\\msql\\expr\\runtime\\esx_exec.cpp", 139, 2u);
    *((_QWORD *)this + 7) = v5;
    memset_0(v5, 0, 8LL * v17);
  }
  for ( i = 0; i < *((_WORD *)a2 + 10); *(_QWORD *)(*((_QWORD *)this + 7) + 8 * v6) = v7 )
  {
    v6 = i;
    v7 = operator new[](
           *(unsigned __int16 *)(*((_QWORD *)a2 + 4) + 2LL * i++),
           v14,
           "sql\\ntdbms\\msql\\expr\\runtime\\esx_exec.cpp",
           150,
           2u);
  }
  v12 = (const struct CEsCompBase *)*((_QWORD *)this + 2);
  v19 = a3[48];
  for ( j = *((unsigned __int16 *)v12 + 10);
        (unsigned int)j < (unsigned __int16)(*((_WORD *)v12 + 9) + *((_WORD *)v12 + 10));
        j = (unsigned int)(j + 1) )
  {
    *(_QWORD *)(*((_QWORD *)this + 7) + 8 * j) = v19;
    v8 = *(unsigned __int16 *)(*((_QWORD *)a2 + 4) + 2 * j);
    if ( (v8 & 0xF) != 0 )
      v8 = (v8 + 15) & 0xFFFFFFFFFFFFFFF0uLL;
    v12 = (const struct CEsCompBase *)*((_QWORD *)this + 2);
    v19 = (struct IMemObj *)((char *)v19 + v8);
  }
LABEL_6:
  v21 = *((_DWORD *)v12 + 18);
  if ( (unsigned int)(v21 - 1) <= 1 || (v22 = 1, v21 == 8) )
    v22 = 0;
  CEsCompValSeg::CreateExecValSeg(
    (const struct CEsCompBase *)((char *)v12 + 40),
    a3,
    v22,
    (struct CValExec ***)this + 5,
    (struct CXVariant ***)this + 6);
  v23 = *((_QWORD *)this + 2);
  v24 = *(unsigned int *)(v23 + 120);
  if ( (_DWORD)v24 )
  {
    v25 = 8 * v24;
    if ( !is_mul_ok(v24, 8u) )
      v25 = -1;
    v26 = operator new[](v25, *a3, "sql\\ntdbms\\msql\\expr\\runtime\\esx_compinfoseg.cpp", 79, 3u);
    *((_QWORD *)this + 8) = v26;
    memset_0(v26, 0, (unsigned int)(8 * *(_DWORD *)(v23 + 120)));
    if ( *(_DWORD *)(v23 + 120) )
    {
      do
      {
        v27 = 8 * v9;
        v28 = *(_QWORD *)(8 * v9 + *(_QWORD *)(v23 + 112));
        v9 = (unsigned int)(v9 + 1);
        *(_QWORD *)(v27 + *((_QWORD *)this + 8)) = (*(__int64 (__fastcall **)(__int64, struct IMemObj **))(*(_QWORD *)v28 + 8LL))(
                                                     v28,
                                                     a3);
      }
      while ( (unsigned int)v9 < *(_DWORD *)(v23 + 120) );
    }
  }
}

```

## disassembly

```asm
0x100404990  mov     [rsp+arg_10], rbx
0x100404995  push    rsi
0x100404996  push    rdi
0x100404997  push    r13
0x100404999  push    r14
0x10040499b  push    r15
0x10040499d  sub     rsp, 30h
0x1004049a1  xor     esi, esi
0x1004049a3  mov     [rcx+10h], rdx
0x1004049a7  mov     [rcx+48h], r8
0x1004049ab  mov     rdi, rcx
0x1004049ae  test    byte ptr [rdx+8], 8
0x1004049b2  mov     r15, r8
0x1004049b5  mov     [rsp+58h+arg_0], rbp
0x1004049ba  mov     rcx, rdx
0x1004049bd  lea     r13, [rsi-1]
0x1004049c1  mov     rbp, rdx
0x1004049c4  jnz     short loc_100404A26
0x1004049c6  mov     [rsp+58h+arg_8], r12
0x1004049cb  mov     r12, [r8]
0x1004049ce  mov     [rdi+50h], r9
0x1004049d2  movzx   eax, word ptr [rdx+14h]
0x1004049d6  movzx   ecx, word ptr [rdx+12h]
0x1004049da  lea     ebx, [rcx+rax]
0x1004049dd  cmp     bx, ax
0x1004049e0  jb      loc_1004DAD95
0x1004049e6  test    bx, bx
0x1004049e9  jnz     loc_10040234B
0x1004049ef  movzx   r14d, si
0x1004049f3  cmp     si, [rbp+14h]
0x1004049f7  jb      loc_10040239B
0x1004049fd  mov     rcx, [rdi+10h]
0x100404a01  mov     r9, [r15+180h]
0x100404a08  mov     r12, [rsp+58h+arg_8]
0x100404a0d  movzx   r8d, word ptr [rcx+14h]
0x100404a12  movzx   eax, r8w
0x100404a16  add     ax, [rcx+12h]
0x100404a1a  movzx   eax, ax
0x100404a1d  cmp     r8d, eax
0x100404a20  jb      loc_1004023E4
0x100404a26  mov     edx, [rcx+48h]
0x100404a29  mov     rbp, [rsp+58h+arg_0]
0x100404a2e  lea     eax, [rdx-1]
0x100404a31  cmp     eax, 1
0x100404a34  ja      loc_100404C18
0x100404a3a  mov     r8d, esi; int
0x100404a3d  lea     rax, [rdi+30h]
0x100404a41  add     rcx, 28h ; '('; this
0x100404a45  lea     r9, [rdi+28h]; struct CValExec ***
0x100404a49  mov     [rsp+58h+var_38], rax; struct CXVariant ***
0x100404a4e  mov     rdx, r15; struct CEsExecContext *
0x100404a51  call    ?CreateExecValSeg@CEsCompValSeg@@QEBAXPEAVCEsExecContext@@HPEAPEAPEAVCValExec@@PEAPEAPEAVCXVariant@@PEAX@Z; CEsCompValSeg::CreateExecValSeg(CEsExecContext *,int,CValExec * * *,CXVariant * * *,void *)
0x100404a56  mov     r14, [rdi+10h]
0x100404a5a  mov     ecx, [r14+78h]
0x100404a5e  test    ecx, ecx
0x100404a60  jnz     loc_1004DADB4
0x100404a66  mov     rbx, [rsp+58h+arg_10]
0x100404a6b  add     rsp, 30h
0x100404a6f  pop     r15
0x100404a71  pop     r14
0x100404a73  pop     r13
0x100404a75  pop     rdi
0x100404a76  pop     rsi
0x100404a77  retn
0x10040234b  jmp     short loc_10040234E
0x10040234e  lfence
0x100402351  movzx   ebx, bx
0x100402354  lea     r8, aSqlNtdbmsMsqlE_6; "sql\\ntdbms\\msql\\expr\\runtime\\esx_e"...
0x10040235b  mov     eax, 8
0x100402360  mov     byte ptr [rsp+58h+var_38], 2
0x100402365  mul     rbx
0x100402368  mov     r9d, 8Bh
0x10040236e  mov     rdx, r12
0x100402371  cmovo   rax, r13
0x100402375  mov     rcx, rax
0x100402378  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x10040237e  lea     r8, ds:0[rbx*8]; Size
0x100402386  xor     edx, edx; Val
0x100402388  mov     rcx, rax; void *
0x10040238b  mov     [rdi+38h], rax
0x10040238f  call    memset_0
0x100402394  nop
0x100402395  jmp     loc_1004049EF
0x10040239b  nop     word ptr [rax+rax]
0x1004023a0  mov     rax, [rbp+20h]
0x1004023a4  lea     r8, aSqlNtdbmsMsqlE_6; "sql\\ntdbms\\msql\\expr\\runtime\\esx_e"...
0x1004023ab  movzx   ebx, r14w
0x1004023af  mov     r9d, 96h
0x1004023b5  mov     rdx, r12
0x1004023b8  mov     byte ptr [rsp+58h+var_38], 2
0x1004023bd  movzx   ecx, word ptr [rax+rbx*2]
0x1004023c1  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004023c7  mov     rcx, rax
0x1004023ca  inc     r14w
0x1004023ce  mov     rax, [rdi+38h]
0x1004023d2  mov     [rax+rbx*8], rcx
0x1004023d6  cmp     r14w, [rbp+14h]
0x1004023db  jnb     loc_1004049FD
0x1004023e1  jmp     short loc_1004023A0
0x1004023e4  mov     rax, [rdi+38h]
0x1004023e8  mov     [rax+r8*8], r9
0x1004023ec  mov     rax, [rbp+20h]
0x1004023f0  movzx   edx, word ptr [rax+r8*2]
0x1004023f5  test    dl, 0Fh
0x1004023f8  jz      short loc_100402402
0x1004023fa  add     rdx, 0Fh
0x1004023fe  and     rdx, 0FFFFFFFFFFFFFFF0h
0x100402402  mov     rcx, [rdi+10h]
0x100402406  add     r9, rdx
0x100402409  inc     r8d
0x10040240c  movzx   eax, word ptr [rcx+14h]
0x100402410  add     ax, [rcx+12h]
0x100402414  movzx   eax, ax
0x100402417  cmp     r8d, eax
0x10040241a  jb      short loc_1004023E4
0x10040241c  jmp     loc_100404A26
0x100404c18  mov     r8d, 1
0x100404c1e  cmp     edx, 8
0x100404c21  jnz     loc_100404A3D
0x100404c27  jmp     loc_100404A3A
0x1004dad95  mov     ebx, 0FFFFh
0x1004dad9a  lfence
0x1004dad9d  mov     r8, rcx; unsigned __int64
0x1004dada0  mov     rdx, rax; unsigned __int64
0x1004dada3  mov     ecx, 80070216h; int
0x1004dada8  call    ?IntSafeWrapperRtlAssertFailure@@YAXJ_K0@Z; IntSafeWrapperRtlAssertFailure(long,unsigned __int64,unsigned __int64)
0x1004dadad  nop
0x1004dadae  jmp     loc_10040234E
0x1004dadb4  mov     eax, 8
0x1004dadb9  mov     byte ptr [rsp+58h+var_38], 3
0x1004dadbe  mul     rcx
0x1004dadc1  mov     rdx, [r15]
0x1004dadc4  lea     r8, aSqlNtdbmsMsqlE_0; "sql\\ntdbms\\msql\\expr\\runtime\\esx_c"...
0x1004dadcb  mov     r9d, 4Fh ; 'O'
0x1004dadd1  cmovo   rax, r13
0x1004dadd5  mov     rcx, rax
0x1004dadd8  call    cs:__imp_??_U@YAPEAX_KPEAVIMemObj@@PEBDHE@Z; operator new[](unsigned __int64,IMemObj *,char const *,int,uchar)
0x1004dadde  mov     [rdi+40h], rax
0x1004dade2  xor     edx, edx; Val
0x1004dade4  mov     r8d, [r14+78h]
0x1004dade8  mov     rcx, rax; void *
0x1004dadeb  shl     r8d, 3; Size
0x1004dadef  call    memset_0
0x1004dadf4  cmp     [r14+78h], esi
0x1004dadf8  jbe     loc_100404A66
0x1004dadfe  xchg    ax, ax
0x1004dae00  mov     rax, [r14+70h]
0x1004dae04  lea     rbx, ds:0[rsi*8]
0x1004dae0c  mov     rdx, r15
0x1004dae0f  mov     rcx, [rbx+rax]
0x1004dae13  mov     rax, [rcx]
0x1004dae16  call    qword ptr [rax+8]
0x1004dae19  mov     rcx, [rdi+40h]
0x1004dae1d  inc     esi
0x1004dae1f  mov     [rbx+rcx], rax
0x1004dae23  cmp     esi, [r14+78h]
0x1004dae27  jnb     loc_100404A66
0x1004dae2d  jmp     short loc_1004DAE00
```
