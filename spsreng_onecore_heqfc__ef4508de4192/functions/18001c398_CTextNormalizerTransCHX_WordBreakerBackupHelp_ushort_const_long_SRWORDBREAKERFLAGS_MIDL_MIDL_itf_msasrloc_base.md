# CTextNormalizerTransCHX::WordBreakerBackupHelp(ushort const *,long,SRWORDBREAKERFLAGS,__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)

- ea: `0x18001c398`
- end: `0x18001c810`
- name: `?WordBreakerBackupHelp@CTextNormalizerTransCHX@@AEAAJPEBGJW4SRWORDBREAKERFLAGS@@PEAU__MIDL___MIDL_itf_msasrloc_base_0000_0000_0003@@@Z`
- size: `1144`
- prototype: `int __high(const unsigned __int16 *, int, enum SRWORDBREAKERFLAGS, struct __MIDL___MIDL_itf_msasrloc_base_0000_0000_0003 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x18001c1f0`

## callees

- `0x180002aac`
- `0x1800034b0`
- `0x180003640`
- `0x180004312`
- `0x180006b20`
- `0x1800141c0`
- `0x18001b9dc`
- `0x18001c398`
- `0x18004c4d8`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c6d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c464`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c6d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTextNormalizerTransCHX::WordBreakerBackupHelp(
        __int64 a1,
        _WORD *a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v5; // esi
  int v7; // ebx
  _DWORD *v8; // r15
  _QWORD *v9; // rax
  const unsigned __int16 *v10; // rdi
  int v11; // r13d
  const unsigned __int16 *v12; // rsi
  const unsigned __int16 *v13; // rbx
  size_t v14; // rcx
  __int64 v15; // rbx
  __int64 v16; // rax
  unsigned __int64 v17; // rcx
  __int64 v18; // rsi
  unsigned __int64 v19; // rbx
  unsigned __int64 v20; // rdi
  char *v21; // rax
  char *v22; // rax
  char *v23; // rcx
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rbx
  bool v28; // [rsp+30h] [rbp-D0h]
  unsigned int i; // [rsp+40h] [rbp-C0h] BYREF
  int v30; // [rsp+44h] [rbp-BCh]
  void *v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  size_t Size; // [rsp+58h] [rbp-A8h]
  __int128 v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 v36[12]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v37[128]; // [rsp+90h] [rbp-70h] BYREF

  v5 = a3;
  v32 = a1;
  v34 = 0;
  v35 = 0;
  v7 = 0;
  v8 = 0;
  v31 = 0;
  for ( i = 0; v5 > 0; --v5 )
  {
    if ( a2[v5 - 1] != 32 && a2[v5 - 1] != 12288 )
      break;
  }
  if ( *a2 == 47 && v5 > 1 && a2[v5 - 1] == 59 )
  {
    v9 = CoTaskMemAlloc(((2LL * v5 + 9) & 0xFFFFFFFFFFFFFFF8uLL) + 40);
    if ( !v9 )
      goto LABEL_42;
    *(_QWORD *)(a5 + 40) = v9;
    *(_DWORD *)a5 = 1;
    *(_QWORD *)(a5 + 24) = v9;
    *(_WORD *)v9 = 0;
    *(_QWORD *)(a5 + 16) = v9 + 1;
    v9[1] = v9 + 4;
    *(_QWORD *)(a5 + 32) = v9 + 2;
    *((_DWORD *)v9 + 4) = 0;
    *(_WORD *)(*(_QWORD *)(a5 + 32) + 4LL) = v5;
    *(_DWORD *)(*(_QWORD *)(a5 + 32) + 8LL) = 0;
    *(_QWORD *)(a5 + 8) = v9 + 4;
    memcpy_0(v9 + 4, a2, 2LL * v5 + 2);
    *(_WORD *)(*(_QWORD *)(a5 + 8) + 2LL * v5) = 0;
    goto LABEL_50;
  }
  v10 = a2;
  v11 = 0;
  v12 = &a2[v5];
  while ( v10 < v12 )
  {
    do
    {
      if ( *v10 != 32 && *v10 != 12288 )
        break;
      ++v10;
    }
    while ( v10 < v12 );
    if ( v10 == v12 )
      break;
    v30 = v11 + 1;
    v7 = EnsureArrayVoid(&v31, 0xCu, v11 + 1, &i, 0x40u, (struct CHeap *)&g_heap, v28);
    v8 = v31;
    if ( v7 < 0 )
      goto LABEL_43;
    v13 = v10;
    v14 = 3LL * v11;
    Size = v14;
    *((_DWORD *)v31 + v14) = v10 - a2;
    v8[v14 + 2] = 0;
    if ( v10 >= v12 )
    {
LABEL_29:
      v15 = v12 - v10;
      if ( v15 >= 8 )
        LODWORD(v15) = 8;
      StringCchCopyNW(v36, 9u, v10, (int)v15);
      while ( (int)v15 >= 1 )
      {
        v17 = 2LL * (int)v15;
        if ( v17 >= 0x12 )
          _report_rangecheckfailure(v17, 0);
        v36[(int)v15] = 0;
        if ( (*(int (__fastcall **)(_QWORD, unsigned __int16 *, _QWORD, __int64, __int128 *))(**(_QWORD **)(v32 + 80)
                                                                                            + 24LL))(
               *(_QWORD *)(v32 + 80),
               v36,
               *(unsigned __int16 *)(v32 + 72),
               4096,
               &v34) >= 0 )
          goto LABEL_28;
        LODWORD(v15) = v15 - 1;
      }
      goto LABEL_27;
    }
    do
    {
      if ( *v13 >= 0x20u )
        break;
      ++v13;
    }
    while ( v13 < v12 );
    if ( v13 <= v10 )
    {
      if ( v13 >= v12 )
        goto LABEL_29;
      do
      {
        if ( (unsigned __int16)(*v13 - 1) > 0x7Eu )
          break;
        ++v13;
      }
      while ( v13 < v12 );
      if ( v13 <= v10 )
        goto LABEL_29;
    }
    else
    {
      v8[3 * v11 + 2] = 2;
    }
    v15 = v13 - v10;
LABEL_27:
    if ( (int)v15 <= 0 )
    {
      v16 = 2;
    }
    else
    {
LABEL_28:
      LOWORD(v8[Size + 1]) = v15;
      v11 = v30;
      v16 = 2LL * (unsigned int)v15;
    }
    v10 = (const unsigned __int16 *)((char *)v10 + v16);
  }
  if ( !v11 )
  {
    v7 = 1;
    goto LABEL_43;
  }
  v18 = 8LL * v11;
  v32 = 4LL * (v11 + v8[3 * v11 - 3] + (unsigned int)LOWORD(v8[3 * v11 - 2]));
  Size = 12LL * v11;
  v19 = (2LL * v11 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v20 = (v32 + 7) & 0xFFFFFFFFFFFFFFF8uLL;
  v21 = (char *)CoTaskMemAlloc(v19 + v20 + v18 + ((Size + 7) & 0xFFFFFFFFFFFFFFF8uLL));
  if ( v21 )
  {
    *(_QWORD *)(a5 + 40) = v21;
    *(_DWORD *)a5 = v11;
    *(_QWORD *)(a5 + 24) = v21;
    v22 = &v21[v19];
    *(_QWORD *)(a5 + 16) = v22;
    *(_QWORD *)(a5 + 8) = &v22[v18];
    v23 = &v22[v18 + v20];
    *(_QWORD *)(a5 + 32) = v23;
    memcpy_0(v23, v8, Size);
    v24 = 0;
    i = 0;
    v7 = 0;
    if ( v11 > 0 )
    {
      v25 = 0;
      do
      {
        *(_WORD *)(*(_QWORD *)(a5 + 24) + 2 * v25) = 0;
        *(_QWORD *)(*(_QWORD *)(a5 + 16) + 8 * v25) = *(_QWORD *)(a5 + 8) + 2 * v24;
        StringCchCopyNW(v37, 0x80u, &a2[v8[3 * v25]], LOWORD(v8[3 * v25 + 1]));
        v26 = -1;
        do
          ++v26;
        while ( v37[v26] );
        StringCchCopyW((unsigned __int16 *)(*(_QWORD *)(a5 + 8) + 2 * v24), v32 - v24, v37);
        v24 += v26 + 1;
        ++i;
        ++v25;
      }
      while ( (int)i < v11 );
      v7 = 0;
    }
  }
  else
  {
LABEL_42:
    v7 = -2147024882;
LABEL_43:
    *(_OWORD *)a5 = 0;
    *(_OWORD *)(a5 + 16) = 0;
    *(_OWORD *)(a5 + 32) = 0;
  }
LABEL_50:
  CWinHeap::Free((CWinHeap *)&g_heap, v8);
  CWordPronunciationList::~CWordPronunciationList((CWordPronunciationList *)&v34);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001c398  mov     [rsp-8+arg_18], rbx
0x18001c39d  push    rbp
0x18001c39e  push    rsi
0x18001c39f  push    rdi
0x18001c3a0  push    r12
0x18001c3a2  push    r13
0x18001c3a4  push    r14
0x18001c3a6  push    r15
0x18001c3a8  lea     rbp, [rsp-0A0h]
0x18001c3b0  sub     rsp, 1A0h
0x18001c3b7  mov     rax, cs:__security_cookie
0x18001c3be  xor     rax, rsp
0x18001c3c1  mov     [rbp+0D0h+var_40], rax
0x18001c3c8  mov     esi, r8d
0x18001c3cb  mov     r12, rdx
0x18001c3ce  mov     [rsp+1D0h+var_180], rcx
0x18001c3d3  mov     r14, [rbp+0D0h+arg_20]
0x18001c3da  xorps   xmm0, xmm0
0x18001c3dd  xor     eax, eax
0x18001c3df  movups  [rsp+1D0h+var_170], xmm0
0x18001c3e4  mov     [rsp+1D0h+var_160], rax
0x18001c3e9  xor     ebx, ebx
0x18001c3eb  mov     r15d, ebx
0x18001c3ee  mov     [rsp+1D0h+var_188], rbx
0x18001c3f3  mov     [rsp+1D0h+var_190], ebx
0x18001c3f7  mov     edx, 3000h
0x18001c3fc  lea     ecx, [rax+1]
0x18001c3ff  test    r8d, r8d
0x18001c402  jle     short loc_18001C41D
0x18001c404  mov     eax, esi
0x18001c406  cmp     word ptr [r12+rax*2-2], 20h ; ' '
0x18001c40d  jz      short loc_18001C417
0x18001c40f  cmp     [r12+rax*2-2], dx
0x18001c415  jnz     short loc_18001C41D
0x18001c417  sub     esi, ecx
0x18001c419  test    esi, esi
0x18001c41b  jg      short loc_18001C404
0x18001c41d  mov     eax, 2Fh ; '/'
0x18001c422  lea     r8, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18001c429  cmp     ax, [r12]
0x18001c42e  jnz     loc_18001C4D4
0x18001c434  cmp     esi, ecx
0x18001c436  jle     loc_18001C4D4
0x18001c43c  movsxd  rdi, esi
0x18001c43f  mov     eax, 3Bh ; ';'
0x18001c444  cmp     ax, [r12+rdi*2-2]
0x18001c44a  jnz     loc_18001C4D4
0x18001c450  lea     r13, ds:2[rdi*2]
0x18001c458  lea     rcx, [r13+7]
0x18001c45c  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18001c460  add     rcx, 28h ; '('; cb
0x18001c464  call    cs:__imp_CoTaskMemAlloc
0x18001c46a  mov     rcx, rax
0x18001c46d  test    rax, rax
0x18001c470  jz      loc_18001C6E1
0x18001c476  mov     [r14+28h], rax
0x18001c47a  mov     dword ptr [r14], 1
0x18001c481  mov     [r14+18h], rax
0x18001c485  xor     edx, edx
0x18001c487  mov     [rax], dx
0x18001c48a  add     rcx, 8
0x18001c48e  mov     [r14+10h], rcx
0x18001c492  lea     rax, [rcx+18h]
0x18001c496  mov     [rcx], rax
0x18001c499  add     rcx, 8
0x18001c49d  mov     [r14+20h], rcx
0x18001c4a1  mov     [rcx], edx
0x18001c4a3  mov     rax, [r14+20h]
0x18001c4a7  mov     [rax+4], si
0x18001c4ab  mov     rax, [r14+20h]
0x18001c4af  mov     [rax+8], edx
0x18001c4b2  add     rcx, 10h; void *
0x18001c4b6  mov     [r14+8], rcx
0x18001c4ba  mov     r8, r13; Size
0x18001c4bd  mov     rdx, r12; Src
0x18001c4c0  call    memcpy_0
0x18001c4c5  mov     rcx, [r14+8]
0x18001c4c9  xor     eax, eax
0x18001c4cb  mov     [rcx+rdi*2], ax
0x18001c4cf  jmp     loc_18001C7CA
0x18001c4d4  mov     rdi, r12
0x18001c4d7  mov     r13d, ebx
0x18001c4da  movsxd  rax, esi
0x18001c4dd  lea     rsi, [r12+rax*2]
0x18001c4e1  cmp     rdi, rsi
0x18001c4e4  jnb     loc_18001C673
0x18001c4ea  cmp     word ptr [rdi], 20h ; ' '
0x18001c4ee  jz      short loc_18001C4F5
0x18001c4f0  cmp     [rdi], dx
0x18001c4f3  jnz     short loc_18001C4FE
0x18001c4f5  add     rdi, 2
0x18001c4f9  cmp     rdi, rsi
0x18001c4fc  jb      short loc_18001C4EA
0x18001c4fe  cmp     rdi, rsi
0x18001c501  jz      loc_18001C673
0x18001c507  lea     eax, [r13+1]
0x18001c50b  mov     [rsp+1D0h+var_18C], eax
0x18001c50f  mov     [rsp+1D0h+var_1A8], r8; struct CHeap *
0x18001c514  mov     [rsp+1D0h+var_1B0], 40h ; '@'; unsigned int
0x18001c51c  lea     r9, [rsp+1D0h+var_190]; unsigned int *
0x18001c521  mov     r8d, eax; unsigned int
0x18001c524  mov     edx, 0Ch; unsigned __int64
0x18001c529  lea     rcx, [rsp+1D0h+var_188]; void **
0x18001c52e  call    ?EnsureArrayVoid@@YAJPEAPEAX_KKPEAKKPEAVCHeap@@_N@Z; EnsureArrayVoid(void * *,unsigned __int64,ulong,ulong *,ulong,CHeap *,bool)
0x18001c533  mov     ebx, eax
0x18001c535  xor     edx, edx
0x18001c537  mov     r15, [rsp+1D0h+var_188]
0x18001c53c  test    eax, eax
0x18001c53e  js      loc_18001C6E6
0x18001c544  mov     rbx, rdi
0x18001c547  movsxd  rax, r13d
0x18001c54a  lea     rcx, [rax+rax*2]
0x18001c54e  mov     [rsp+1D0h+Size], rcx
0x18001c553  mov     rax, rdi
0x18001c556  sub     rax, r12
0x18001c559  sar     rax, 1
0x18001c55c  mov     [r15+rcx*4], eax
0x18001c560  mov     [r15+rcx*4+8], edx
0x18001c565  cmp     rdi, rsi
0x18001c568  jnb     short loc_18001C5D5
0x18001c56a  cmp     word ptr [rbx], 20h ; ' '
0x18001c56e  jnb     short loc_18001C579
0x18001c570  add     rbx, 2
0x18001c574  cmp     rbx, rsi
0x18001c577  jb      short loc_18001C56A
0x18001c579  cmp     rbx, rdi
0x18001c57c  jbe     short loc_18001C589
0x18001c57e  mov     dword ptr [r15+rcx*4+8], 2
0x18001c587  jmp     short loc_18001C5AD
0x18001c589  cmp     rbx, rsi
0x18001c58c  jnb     short loc_18001C5D5
0x18001c58e  mov     ecx, 1
0x18001c593  movzx   eax, word ptr [rbx]
0x18001c596  sub     ax, cx
0x18001c599  cmp     ax, 7Eh ; '~'
0x18001c59d  ja      short loc_18001C5A8
0x18001c59f  add     rbx, 2
0x18001c5a3  cmp     rbx, rsi
0x18001c5a6  jb      short loc_18001C593
0x18001c5a8  cmp     rbx, rdi
0x18001c5ab  jbe     short loc_18001C5D5
0x18001c5ad  sub     rbx, rdi
0x18001c5b0  sar     rbx, 1
0x18001c5b3  test    ebx, ebx
0x18001c5b5  jle     loc_18001C654
0x18001c5bb  mov     rax, [rsp+1D0h+Size]
0x18001c5c0  mov     [r15+rax*4+4], bx
0x18001c5c6  mov     r13d, [rsp+1D0h+var_18C]
0x18001c5cb  mov     eax, ebx
0x18001c5cd  add     rax, rax
0x18001c5d0  jmp     loc_18001C659
0x18001c5d5  mov     rbx, rsi
0x18001c5d8  sub     rbx, rdi
0x18001c5db  sar     rbx, 1
0x18001c5de  cmp     rbx, 8
0x18001c5e2  jl      short loc_18001C5E9
0x18001c5e4  mov     ebx, 8
0x18001c5e9  movsxd  r9, ebx; unsigned __int64
0x18001c5ec  mov     r8, rdi; unsigned __int16 *
0x18001c5ef  mov     edx, 9; unsigned __int64
0x18001c5f4  lea     rcx, [rsp+1D0h+var_158]; unsigned __int16 *
0x18001c5f9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001c5fe  xor     edx, edx
0x18001c600  cmp     ebx, 1
0x18001c603  jl      short loc_18001C5B3
0x18001c605  movsxd  rax, ebx
0x18001c608  lea     rcx, [rax+rax]
0x18001c60c  cmp     rcx, 12h
0x18001c610  jnb     short loc_18001C66D
0x18001c612  mov     [rsp+rcx+1D0h+var_158], dx
0x18001c617  mov     rdx, [rsp+1D0h+var_180]
0x18001c61c  mov     rcx, [rdx+50h]
0x18001c620  mov     rax, [rcx]
0x18001c623  lea     r8, [rsp+1D0h+var_170]
0x18001c628  mov     qword ptr [rsp+1D0h+var_1B0], r8
0x18001c62d  mov     r9d, 1000h
0x18001c633  movzx   r8d, word ptr [rdx+48h]
0x18001c638  lea     rdx, [rsp+1D0h+var_158]
0x18001c63d  mov     rax, [rax+18h]
0x18001c641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c646  xor     edx, edx
0x18001c648  test    eax, eax
0x18001c64a  jns     loc_18001C5BB
0x18001c650  dec     ebx
0x18001c652  jmp     short loc_18001C600
0x18001c654  mov     eax, 2
0x18001c659  add     rdi, rax
0x18001c65c  mov     edx, 3000h
0x18001c661  lea     r8, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x18001c668  jmp     loc_18001C4E1
0x18001c66d  call    __report_rangecheckfailure
0x18001c673  test    r13d, r13d
0x18001c676  jnz     short loc_18001C67E
0x18001c678  lea     ebx, [r13+1]
0x18001c67c  jmp     short loc_18001C6E6
0x18001c67e  movsxd  rdx, r13d
0x18001c681  lea     rsi, ds:0[rdx*8]
0x18001c689  lea     rax, [rdx+rdx*2]
0x18001c68d  movzx   ecx, word ptr [r15+rax*4-8]
0x18001c693  add     ecx, [r15+rax*4-0Ch]
0x18001c698  add     ecx, r13d
0x18001c69b  shl     rcx, 2
0x18001c69f  mov     [rsp+1D0h+var_180], rcx
0x18001c6a4  lea     rax, [rdx+rdx*2]
0x18001c6a8  shl     rax, 2
0x18001c6ac  mov     [rsp+1D0h+Size], rax
0x18001c6b1  lea     rbx, ds:7[rdx*2]
0x18001c6b9  and     rbx, 0FFFFFFFFFFFFFFF8h
0x18001c6bd  lea     rdi, [rcx+7]
0x18001c6c1  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18001c6c5  lea     rcx, [rax+7]
0x18001c6c9  and     rcx, 0FFFFFFFFFFFFFFF8h
0x18001c6cd  add     rcx, rsi
0x18001c6d0  add     rcx, rdi
0x18001c6d3  add     rcx, rbx; cb
0x18001c6d6  call    cs:__imp_CoTaskMemAlloc
0x18001c6dc  test    rax, rax
0x18001c6df  jnz     short loc_18001C6FC
0x18001c6e1  mov     ebx, 8007000Eh
0x18001c6e6  xorps   xmm0, xmm0
0x18001c6e9  movups  xmmword ptr [r14], xmm0
0x18001c6ed  movups  xmmword ptr [r14+10h], xmm0
0x18001c6f2  movups  xmmword ptr [r14+20h], xmm0
0x18001c6f7  jmp     loc_18001C7CA
0x18001c6fc  mov     [r14+28h], rax
0x18001c700  mov     [r14], r13d
0x18001c703  mov     [r14+18h], rax
0x18001c707  add     rax, rbx
0x18001c70a  mov     [r14+10h], rax
0x18001c70e  lea     rcx, [rsi+rax]
0x18001c712  mov     [r14+8], rcx
0x18001c716  add     rcx, rdi; void *
0x18001c719  mov     [r14+20h], rcx
0x18001c71d  mov     r8, [rsp+1D0h+Size]; Size
0x18001c722  mov     rdx, r15; Src
0x18001c725  call    memcpy_0
0x18001c72a  xor     eax, eax
0x18001c72c  mov     esi, eax
0x18001c72e  mov     [rsp+1D0h+var_190], eax
0x18001c732  mov     ebx, eax
0x18001c734  test    r13d, r13d
0x18001c737  jle     loc_18001C7CA
0x18001c73d  mov     edi, eax
0x18001c73f  jmp     short loc_18001C743
0x18001c741  xor     eax, eax
0x18001c743  mov     rcx, [r14+18h]
0x18001c747  mov     [rcx+rdi*2], ax
0x18001c74b  mov     rax, [r14+8]
0x18001c74f  lea     rcx, [rax+rsi*2]
0x18001c753  mov     rax, [r14+10h]
0x18001c757  mov     [rax+rdi*8], rcx
0x18001c75b  lea     rax, [rdi+rdi*2]
0x18001c75f  movzx   r9d, word ptr [r15+rax*4+4]; unsigned __int64
0x18001c765  mov     eax, [r15+rax*4]
0x18001c769  lea     r8, [r12+rax*2]; unsigned __int16 *
0x18001c76d  mov     edx, 80h; unsigned __int64
0x18001c772  lea     rcx, [rbp+0D0h+var_140]; unsigned __int16 *
0x18001c776  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18001c77b  lea     rcx, [rbp+0D0h+var_140]
0x18001c77f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c783  xor     eax, eax
0x18001c785  inc     rbx
0x18001c788  cmp     [rcx+rbx*2], ax
0x18001c78c  jnz     short loc_18001C785
0x18001c78e  mov     rdx, [rsp+1D0h+var_180]
0x18001c793  sub     rdx, rsi; unsigned __int64
0x18001c796  mov     rax, [r14+8]
0x18001c79a  lea     rcx, [rax+rsi*2]; unsigned __int16 *
0x18001c79e  lea     r8, [rbp+0D0h+var_140]; unsigned __int16 *
0x18001c7a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001c7a7  inc     rsi
0x18001c7aa  add     rsi, rbx
0x18001c7ad  mov     eax, [rsp+1D0h+var_190]
0x18001c7b1  mov     ecx, 1
0x18001c7b6  add     eax, ecx
0x18001c7b8  mov     [rsp+1D0h+var_190], eax
0x18001c7bc  add     rdi, rcx
0x18001c7bf  cmp     eax, r13d
0x18001c7c2  jl      loc_18001C741
0x18001c7c8  xor     ebx, ebx
0x18001c7ca  mov     rdx, r15; void *
0x18001c7cd  lea     rcx, ?g_heap@@3VCHeap@@A; this
0x18001c7d4  call    ?Free@CWinHeap@@QEAA_NPEAX@Z; CWinHeap::Free(void *)
0x18001c7d9  nop
0x18001c7da  lea     rcx, [rsp+1D0h+var_170]; this
0x18001c7df  call    ??1CWordPronunciationList@@QEAA@XZ; CWordPronunciationList::~CWordPronunciationList(void)
0x18001c7e4  mov     eax, ebx
0x18001c7e6  mov     rcx, [rbp+0D0h+var_40]
0x18001c7ed  xor     rcx, rsp; StackCookie
0x18001c7f0  call    __security_check_cookie
0x18001c7f5  mov     rbx, [rsp+1D0h+arg_18]
0x18001c7fd  add     rsp, 1A0h
0x18001c804  pop     r15
0x18001c806  pop     r14
0x18001c808  pop     r13
0x18001c80a  pop     r12
0x18001c80c  pop     rdi
0x18001c80d  pop     rsi
0x18001c80e  pop     rbp
0x18001c80f  retn
  ... truncated ...
```
