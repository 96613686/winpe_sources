# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x140006180`
- end: `0x14000657b`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1019`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400037b4`

## callees

- `0x140001c8f`
- `0x140003738`
- `0x140006180`
- `0x1400070e8`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140006381`
- `KERNEL32!GetProcessHeap` at `0x140006381`
- `KERNEL32!HeapFree` at `0x14000638f`
- `KERNEL32!HeapFree` at `0x14000638f`
- `msvcrt!memcpy_s` at `0x1400063fd`
- `msvcrt!memcpy_s` at `0x1400064d1`
- `msvcrt!memcpy_s` at `0x14000653d`
- `msvcrt!memcpy_s` at `0x1400063fd`
- `msvcrt!memcpy_s` at `0x1400064d1`
- `msvcrt!memcpy_s` at `0x14000653d`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::SetFailureInfo(wil::StoredFailureInfo *this, const struct wil::FailureInfo *a2)
{
  __int64 v2; // rsi
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r10
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  void **v36; // r14
  volatile signed __int32 *v37; // rcx
  volatile signed __int32 *v38; // r15
  void *v39; // rbx
  HANDLE ProcessHeap; // rax
  char *v41; // rbx
  rsize_t v42; // rdx
  char **v43; // r15
  char *v44; // r14
  _WORD *v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // r12
  char *v48; // rax
  char *v49; // rax
  char *v50; // rax
  char *v51; // rax
  char *v52; // rax
  char **v53; // r15
  char *v54; // rbx
  _WORD *v55; // r8
  __int64 v56; // rax
  unsigned __int64 v57; // r12
  char *v58; // rax
  char **v59; // rbp
  char *v60; // rbx
  _WORD *v61; // r8
  rsize_t v62; // rsi

  v2 = -1;
  *(_OWORD *)this = *(_OWORD *)a2;
  v5 = 2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 7);
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 8);
  *((_QWORD *)this + 18) = *((_QWORD *)a2 + 18);
  v6 = *((_QWORD *)a2 + 3);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    v7 = 2 * v8 + 2;
  }
  else
  {
    v7 = 2;
  }
  v9 = *((_QWORD *)a2 + 5);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 6);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v12 + v14) );
    v13 = v14 + 1;
  }
  else
  {
    v13 = 1;
  }
  v15 = *((_QWORD *)a2 + 7);
  if ( v15 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_BYTE *)(v15 + v17) );
    v16 = v17 + 1;
  }
  else
  {
    v16 = 1;
  }
  v18 = *((_QWORD *)a2 + 9);
  if ( v18 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_BYTE *)(v18 + v20) );
    v19 = v20 + 1;
  }
  else
  {
    v19 = 1;
  }
  v21 = *((_QWORD *)a2 + 16);
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(v21 + v23) );
    v22 = v23 + 1;
  }
  else
  {
    v22 = 1;
  }
  v24 = *((_QWORD *)a2 + 14);
  if ( v24 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(v24 + v26) );
    v25 = v26 + 1;
  }
  else
  {
    v25 = 1;
  }
  v27 = *((_QWORD *)a2 + 15);
  if ( v27 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(v27 + 2 * v29) );
    v28 = 2 * v29 + 2;
  }
  else
  {
    v28 = 2;
  }
  v30 = *((_QWORD *)a2 + 11);
  if ( v30 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_BYTE *)(v30 + v32) );
    v31 = v32 + 1;
  }
  else
  {
    v31 = 1;
  }
  v33 = *((_QWORD *)a2 + 12);
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(v33 + 2 * v34) );
    v5 = 2 * v34 + 2;
  }
  v35 = v16 + v19 + v22 + v25 + v28 + v5 + v31;
  v36 = (void **)((char *)this + 152);
  v37 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  v38 = (volatile signed __int32 *)(v7 + v10 + v35 + v13);
  if ( !v37 )
    goto LABEL_56;
  if ( *v37 != 1 || *((_QWORD *)this + 20) < (unsigned __int64)v38 )
  {
    if ( _InterlockedExchangeAdd(v37, 0xFFFFFFFF) == 1 )
    {
      v39 = *v36;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v39);
    }
    *v36 = 0;
    *((_QWORD *)this + 20) = 0;
LABEL_56:
    wil::details::shared_buffer::create((volatile signed __int32 **)this + 19, v38);
  }
  v41 = (char *)(((unsigned __int64)*v36 + 4) & -(__int64)(*v36 != 0));
  if ( v41 )
  {
    v42 = *((_QWORD *)this + 20);
    v43 = (char **)((char *)this + 24);
    v44 = &v41[v42];
    if ( v41 == &v41[v42] )
      goto LABEL_67;
    v45 = (_WORD *)*((_QWORD *)a2 + 3);
    if ( !v45 )
      goto LABEL_67;
    if ( !*v45 )
      goto LABEL_67;
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v47 = 2 * v46 + 2;
    if ( v42 >= v47 )
    {
      memcpy_s(v41, v42, v45, 2 * v46 + 2);
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = v41;
      v41 += v47;
    }
    else
    {
LABEL_67:
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = 0;
    }
    v48 = wil::details::WriteResultString<char const *>(v41, v44, *((_BYTE **)a2 + 5), (_QWORD *)this + 5);
    v49 = wil::details::WriteResultString<char const *>(v48, v44, *((_BYTE **)a2 + 6), (_QWORD *)this + 6);
    v50 = wil::details::WriteResultString<char const *>(v49, v44, *((_BYTE **)a2 + 7), (_QWORD *)this + 7);
    v51 = wil::details::WriteResultString<char const *>(v50, v44, *((_BYTE **)a2 + 9), (_QWORD *)this + 9);
    v52 = wil::details::WriteResultString<char const *>(v51, v44, *((_BYTE **)a2 + 16), (_QWORD *)this + 16);
    v53 = (char **)((char *)this + 120);
    v54 = wil::details::WriteResultString<char const *>(v52, v44, *((_BYTE **)a2 + 14), (_QWORD *)this + 14);
    if ( v54 == v44 )
      goto LABEL_78;
    v55 = (_WORD *)*((_QWORD *)a2 + 15);
    if ( !v55 )
      goto LABEL_78;
    if ( !*v55 )
      goto LABEL_78;
    v56 = -1;
    do
      ++v56;
    while ( v55[v56] );
    v57 = 2 * v56 + 2;
    if ( v44 - v54 >= v57 )
    {
      memcpy_s(v54, v44 - v54, v55, 2 * v56 + 2);
      if ( this != (wil::StoredFailureInfo *)-120LL )
        *v53 = v54;
      v54 += v57;
    }
    else
    {
LABEL_78:
      if ( this != (wil::StoredFailureInfo *)-120LL )
        *v53 = 0;
    }
    v58 = wil::details::WriteResultString<char const *>(v54, v44, *((_BYTE **)a2 + 11), (_QWORD *)this + 11);
    v59 = (char **)((char *)this + 96);
    v60 = v58;
    if ( v58 == v44 )
      goto LABEL_88;
    v61 = (_WORD *)*((_QWORD *)a2 + 12);
    if ( !v61 || !*v61 )
      goto LABEL_88;
    do
      ++v2;
    while ( v61[v2] );
    v62 = 2 * v2 + 2;
    if ( v44 - v58 >= v62 )
    {
      memcpy_s(v58, v44 - v58, v61, v62);
      if ( v59 )
        *v59 = v60;
      v60 += v62;
    }
    else
    {
LABEL_88:
      if ( v59 )
        *v59 = 0;
    }
    memset_0(v60, 0, v44 - v60);
  }
}

```

## disassembly

```asm
0x140006180  push    rbx
0x140006182  push    rbp
0x140006183  push    rsi
0x140006184  push    rdi
0x140006185  push    r12
0x140006187  push    r13
0x140006189  push    r14
0x14000618b  push    r15
0x14000618d  sub     rsp, 28h
0x140006191  movups  xmm0, xmmword ptr [rdx]
0x140006194  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140006198  mov     rbp, rcx
0x14000619b  mov     rdi, rdx
0x14000619e  movups  xmmword ptr [rcx], xmm0
0x1400061a1  movups  xmm1, xmmword ptr [rdx+10h]
0x1400061a5  lea     r9d, [rsi+3]
0x1400061a9  movups  xmmword ptr [rcx+10h], xmm1
0x1400061ad  movups  xmm0, xmmword ptr [rdx+20h]
0x1400061b1  movups  xmmword ptr [rcx+20h], xmm0
0x1400061b5  movups  xmm1, xmmword ptr [rdx+30h]
0x1400061b9  movups  xmmword ptr [rcx+30h], xmm1
0x1400061bd  movups  xmm0, xmmword ptr [rdx+40h]
0x1400061c1  movups  xmmword ptr [rcx+40h], xmm0
0x1400061c5  movups  xmm1, xmmword ptr [rdx+50h]
0x1400061c9  movups  xmmword ptr [rcx+50h], xmm1
0x1400061cd  movups  xmm0, xmmword ptr [rdx+60h]
0x1400061d1  movups  xmmword ptr [rcx+60h], xmm0
0x1400061d5  movups  xmm1, xmmword ptr [rdx+70h]
0x1400061d9  movups  xmmword ptr [rcx+70h], xmm1
0x1400061dd  movups  xmm0, xmmword ptr [rdx+80h]
0x1400061e4  movups  xmmword ptr [rcx+80h], xmm0
0x1400061eb  mov     rax, [rdx+90h]
0x1400061f2  mov     [rcx+90h], rax
0x1400061f9  mov     rcx, [rdx+18h]
0x1400061fd  xor     edx, edx
0x1400061ff  test    rcx, rcx
0x140006202  jnz     short loc_140006209
0x140006204  mov     r13d, r9d
0x140006207  jmp     short loc_14000621D
0x140006209  mov     rax, rsi
0x14000620c  inc     rax
0x14000620f  cmp     [rcx+rax*2], dx
0x140006213  jnz     short loc_14000620C
0x140006215  lea     r13, ds:2[rax*2]
0x14000621d  mov     rcx, [rdi+28h]
0x140006221  test    rcx, rcx
0x140006224  jnz     short loc_14000622C
0x140006226  lea     r12d, [rcx+1]
0x14000622a  jmp     short loc_14000623B
0x14000622c  mov     rax, rsi
0x14000622f  inc     rax
0x140006232  cmp     [rcx+rax], dl
0x140006235  jnz     short loc_14000622F
0x140006237  lea     r12, [rax+1]
0x14000623b  mov     rcx, [rdi+30h]
0x14000623f  test    rcx, rcx
0x140006242  jnz     short loc_14000624A
0x140006244  lea     r15d, [rcx+1]
0x140006248  jmp     short loc_140006259
0x14000624a  mov     rax, rsi
0x14000624d  inc     rax
0x140006250  cmp     [rcx+rax], dl
0x140006253  jnz     short loc_14000624D
0x140006255  lea     r15, [rax+1]
0x140006259  mov     rcx, [rdi+38h]
0x14000625d  test    rcx, rcx
0x140006260  jnz     short loc_140006268
0x140006262  lea     r14d, [rcx+1]
0x140006266  jmp     short loc_140006277
0x140006268  mov     rax, rsi
0x14000626b  inc     rax
0x14000626e  cmp     [rcx+rax], dl
0x140006271  jnz     short loc_14000626B
0x140006273  lea     r14, [rax+1]
0x140006277  mov     rcx, [rdi+48h]
0x14000627b  test    rcx, rcx
0x14000627e  jnz     short loc_140006285
0x140006280  lea     ebx, [rcx+1]
0x140006283  jmp     short loc_140006294
0x140006285  mov     rax, rsi
0x140006288  inc     rax
0x14000628b  cmp     [rcx+rax], dl
0x14000628e  jnz     short loc_140006288
0x140006290  lea     rbx, [rax+1]
0x140006294  mov     rcx, [rdi+80h]
0x14000629b  test    rcx, rcx
0x14000629e  jnz     short loc_1400062A6
0x1400062a0  lea     r11d, [rcx+1]
0x1400062a4  jmp     short loc_1400062B5
0x1400062a6  mov     rax, rsi
0x1400062a9  inc     rax
0x1400062ac  cmp     [rcx+rax], dl
0x1400062af  jnz     short loc_1400062A9
0x1400062b1  lea     r11, [rax+1]
0x1400062b5  mov     rcx, [rdi+70h]
0x1400062b9  test    rcx, rcx
0x1400062bc  jnz     short loc_1400062C4
0x1400062be  lea     r10d, [rcx+1]
0x1400062c2  jmp     short loc_1400062D3
0x1400062c4  mov     rax, rsi
0x1400062c7  inc     rax
0x1400062ca  cmp     [rcx+rax], dl
0x1400062cd  jnz     short loc_1400062C7
0x1400062cf  lea     r10, [rax+1]
0x1400062d3  mov     rcx, [rdi+78h]
0x1400062d7  test    rcx, rcx
0x1400062da  jnz     short loc_1400062E1
0x1400062dc  mov     r8, r9
0x1400062df  jmp     short loc_1400062F5
0x1400062e1  mov     rax, rsi
0x1400062e4  inc     rax
0x1400062e7  cmp     [rcx+rax*2], dx
0x1400062eb  jnz     short loc_1400062E4
0x1400062ed  lea     r8, ds:2[rax*2]
0x1400062f5  mov     rcx, [rdi+58h]
0x1400062f9  test    rcx, rcx
0x1400062fc  jnz     short loc_140006303
0x1400062fe  lea     edx, [rcx+1]
0x140006301  jmp     short loc_140006312
0x140006303  mov     rax, rsi
0x140006306  inc     rax
0x140006309  cmp     [rcx+rax], dl
0x14000630c  jnz     short loc_140006306
0x14000630e  lea     rdx, [rax+1]
0x140006312  mov     rcx, [rdi+60h]
0x140006316  test    rcx, rcx
0x140006319  jz      short loc_140006333
0x14000631b  mov     rax, rsi
0x14000631e  xor     r9d, r9d
0x140006321  inc     rax
0x140006324  cmp     [rcx+rax*2], r9w
0x140006329  jnz     short loc_140006321
0x14000632b  lea     r9, ds:2[rax*2]
0x140006333  lea     rax, [r9+rdx]
0x140006337  add     rax, r8
0x14000633a  add     rax, r10
0x14000633d  add     rax, r11
0x140006340  add     rax, rbx
0x140006343  add     rax, r14
0x140006346  lea     r14, [rbp+98h]
0x14000634d  mov     rcx, [r14]
0x140006350  add     r15, rax
0x140006353  add     r15, r12
0x140006356  add     r15, r13
0x140006359  xor     r13d, r13d
0x14000635c  test    rcx, rcx
0x14000635f  jz      short loc_14000639C
0x140006361  cmp     dword ptr [rcx], 1
0x140006364  jnz     short loc_140006374
0x140006366  cmp     [rbp+0A0h], r15
0x14000636d  jnb     short loc_1400063A7
0x14000636f  test    rcx, rcx
0x140006372  jz      short loc_14000639C
0x140006374  mov     eax, esi
0x140006376  lock xadd [rcx], eax
0x14000637a  add     eax, esi
0x14000637c  jnz     short loc_140006395
0x14000637e  mov     rbx, [r14]
0x140006381  call    cs:__imp_GetProcessHeap
0x140006387  mov     r8, rbx; lpMem
0x14000638a  xor     edx, edx; dwFlags
0x14000638c  mov     rcx, rax; hHeap
0x14000638f  call    cs:__imp_HeapFree
0x140006395  mov     [r14], r13
0x140006398  mov     [r14+8], r13
0x14000639c  mov     rdx, r15; unsigned __int64
0x14000639f  mov     rcx, r14; this
0x1400063a2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x1400063a7  mov     rax, [r14]
0x1400063aa  lea     rcx, [rax+4]
0x1400063ae  neg     rax
0x1400063b1  sbb     rbx, rbx
0x1400063b4  and     rbx, rcx
0x1400063b7  jz      loc_14000656A
0x1400063bd  mov     rdx, [r14+8]; DestinationSize
0x1400063c1  lea     r15, [rbp+18h]
0x1400063c5  lea     r14, [rbx+rdx]
0x1400063c9  cmp     rbx, r14
0x1400063cc  jz      short loc_140006410
0x1400063ce  mov     r8, [rdi+18h]; Source
0x1400063d2  test    r8, r8
0x1400063d5  jz      short loc_140006410
0x1400063d7  cmp     [r8], r13w
0x1400063db  jz      short loc_140006410
0x1400063dd  mov     rax, rsi
0x1400063e0  inc     rax
0x1400063e3  cmp     [r8+rax*2], r13w
0x1400063e8  jnz     short loc_1400063E0
0x1400063ea  lea     r12, ds:2[rax*2]
0x1400063f2  cmp     rdx, r12
0x1400063f5  jb      short loc_140006410
0x1400063f7  mov     r9, r12; SourceSize
0x1400063fa  mov     rcx, rbx; Destination
0x1400063fd  call    cs:__imp_memcpy_s
0x140006403  test    r15, r15
0x140006406  jz      short loc_14000640B
0x140006408  mov     [r15], rbx
0x14000640b  add     rbx, r12
0x14000640e  jmp     short loc_140006418
0x140006410  test    r15, r15
0x140006413  jz      short loc_140006418
0x140006415  mov     [r15], r13
0x140006418  mov     r8, [rdi+28h]
0x14000641c  lea     r9, [rbp+28h]
0x140006420  mov     rdx, r14
0x140006423  mov     rcx, rbx
0x140006426  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000642b  mov     r8, [rdi+30h]
0x14000642f  lea     r9, [rbp+30h]
0x140006433  mov     rdx, r14
0x140006436  mov     rcx, rax
0x140006439  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000643e  mov     r8, [rdi+38h]
0x140006442  lea     r9, [rbp+38h]
0x140006446  mov     rdx, r14
0x140006449  mov     rcx, rax
0x14000644c  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006451  mov     r8, [rdi+48h]
0x140006455  lea     r9, [rbp+48h]
0x140006459  mov     rdx, r14
0x14000645c  mov     rcx, rax
0x14000645f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006464  mov     r8, [rdi+80h]
0x14000646b  lea     r9, [rbp+80h]
0x140006472  mov     rdx, r14
0x140006475  mov     rcx, rax
0x140006478  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x14000647d  mov     r8, [rdi+70h]
0x140006481  lea     r9, [rbp+70h]
0x140006485  mov     rdx, r14
0x140006488  mov     rcx, rax
0x14000648b  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x140006490  lea     r15, [rbp+78h]
0x140006494  mov     rbx, rax
0x140006497  cmp     rax, r14
0x14000649a  jz      short loc_1400064E4
0x14000649c  mov     r8, [rdi+78h]; Source
0x1400064a0  test    r8, r8
0x1400064a3  jz      short loc_1400064E4
0x1400064a5  cmp     [r8], r13w
0x1400064a9  jz      short loc_1400064E4
0x1400064ab  mov     rax, rsi
0x1400064ae  inc     rax
0x1400064b1  cmp     [r8+rax*2], r13w
0x1400064b6  jnz     short loc_1400064AE
0x1400064b8  mov     rdx, r14
0x1400064bb  lea     r12, ds:2[rax*2]
0x1400064c3  sub     rdx, rbx; DestinationSize
0x1400064c6  cmp     rdx, r12
0x1400064c9  jb      short loc_1400064E4
0x1400064cb  mov     r9, r12; SourceSize
0x1400064ce  mov     rcx, rbx; Destination
0x1400064d1  call    cs:__imp_memcpy_s
0x1400064d7  test    r15, r15
0x1400064da  jz      short loc_1400064DF
0x1400064dc  mov     [r15], rbx
0x1400064df  add     rbx, r12
0x1400064e2  jmp     short loc_1400064EC
0x1400064e4  test    r15, r15
0x1400064e7  jz      short loc_1400064EC
0x1400064e9  mov     [r15], r13
0x1400064ec  mov     r8, [rdi+58h]
0x1400064f0  lea     r9, [rbp+58h]
0x1400064f4  mov     rdx, r14
0x1400064f7  mov     rcx, rbx
0x1400064fa  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1400064ff  add     rbp, 60h ; '`'
0x140006503  mov     rbx, rax
0x140006506  cmp     rax, r14
0x140006509  jz      short loc_140006551
0x14000650b  mov     r8, [rdi+60h]; Source
0x14000650f  test    r8, r8
0x140006512  jz      short loc_140006551
0x140006514  cmp     [r8], r13w
0x140006518  jz      short loc_140006551
0x14000651a  inc     rsi
0x14000651d  cmp     [r8+rsi*2], r13w
0x140006522  jnz     short loc_14000651A
0x140006524  mov     rdx, r14
0x140006527  lea     rsi, ds:2[rsi*2]
0x14000652f  sub     rdx, rbx; DestinationSize
0x140006532  cmp     rdx, rsi
0x140006535  jb      short loc_140006551
0x140006537  mov     r9, rsi; SourceSize
0x14000653a  mov     rcx, rbx; Destination
0x14000653d  call    cs:__imp_memcpy_s
0x140006543  test    rbp, rbp
0x140006546  jz      short loc_14000654C
0x140006548  mov     [rbp+0], rbx
0x14000654c  add     rbx, rsi
0x14000654f  jmp     short loc_14000655A
0x140006551  test    rbp, rbp
0x140006554  jz      short loc_14000655A
0x140006556  mov     [rbp+0], r13
0x14000655a  sub     r14, rbx
0x14000655d  xor     edx, edx; Val
0x14000655f  mov     r8, r14; Size
0x140006562  mov     rcx, rbx; void *
0x140006565  call    memset_0
0x14000656a  add     rsp, 28h
  ... truncated ...
```
