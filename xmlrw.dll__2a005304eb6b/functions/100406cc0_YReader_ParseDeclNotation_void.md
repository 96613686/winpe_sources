# YReader::ParseDeclNotation(void)

- ea: `0x100406cc0`
- end: `0x1004070f8`
- name: `?ParseDeclNotation@YReader@@AEAAXXZ`
- size: `1080`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x100406cc0`
- `0x100407100`
- `0x10040a020`
- `0x100415560`
- `0x100416cb0`
- `0x1004179f0`
- `0x100423dd0`
- `0x1004394f0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100406eb4`
- `KERNEL32!HeapAlloc` at `0x100406f5a`
- `KERNEL32!HeapAlloc` at `0x100406eb4`
- `KERNEL32!HeapAlloc` at `0x100406f5a`

## pseudocode

```c
void __fastcall YReader::ParseDeclNotation(struct IMalloc **this)
{
  unsigned int v2; // eax
  __int64 v3; // rdi
  struct BlockAlloc::Header *v4; // rbx
  void *v5; // rdx
  __int64 v6; // rcx
  struct BlockAlloc::Header *v7; // rax
  char *v8; // r14
  struct IMalloc *v9; // r15
  void *v10; // r12
  unsigned __int16 *v11; // rcx
  unsigned int v12; // r14d
  size_t v13; // r13
  unsigned int v14; // edi
  __int64 v15; // r8
  struct IMalloc *v16; // rbx
  struct IMallocVtbl *lpVtbl; // rax
  struct IMalloc *v19; // rbx
  DeclNotation *v20; // rax
  DeclNotation *v21; // rdi
  struct IMalloc *v22; // rcx
  struct IMalloc *v23; // rbx
  DeclNotation *v24; // rax
  __int64 v25; // rax
  struct IMallocVtbl *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rax
  __int64 v30; // rax
  _OWORD *v31; // rax
  void *Buf1; // [rsp+40h] [rbp-58h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-50h]
  __int64 v34; // [rsp+50h] [rbp-48h] BYREF
  int v35; // [rsp+58h] [rbp-40h]
  __int64 v36; // [rsp+60h] [rbp-38h] BYREF
  int v37; // [rsp+68h] [rbp-30h]
  struct IMalloc *v38; // [rsp+A8h] [rbp+10h]

  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 12 )
  {
    MXRRaiseException(-1072894407);
    __debugbreak();
  }
  v2 = ((__int64 (__fastcall *)(struct IMalloc *))this[13]->lpVtbl[1].Alloc)(this[13]);
  v3 = v2;
  v4 = (struct BlockAlloc::Header *)this[55];
  v5 = (void *)*((_QWORD *)v4 + 2);
  if ( *((_DWORD *)v4 + 6) - (int)v5 < v2 )
  {
    v6 = *((_QWORD *)v4 + 1);
    if ( v6 )
    {
      while ( 1 )
      {
        v4 = (struct BlockAlloc::Header *)v6;
        if ( *(_DWORD *)(v6 + 24) - (int)v6 - 32 >= v2 )
          break;
        v6 = *(_QWORD *)(v6 + 8);
        if ( !v6 )
          goto LABEL_6;
      }
      *(_QWORD *)(v6 + 16) = v6 + 32;
    }
    else
    {
LABEL_6:
      _mm_lfence();
      v7 = BlockAlloc::EnqueueBlock((BlockAlloc *)(this + 52), v2, v4);
      *((_QWORD *)v4 + 1) = v7;
      v4 = v7;
    }
    this[55] = (struct IMalloc *)v4;
    v5 = (void *)*((_QWORD *)v4 + 2);
  }
  *((_QWORD *)v4 + 2) += v3;
  Buf1 = v5;
  ((void (__fastcall *)(struct IMalloc *, void **))this[13]->lpVtbl[1].Realloc)(this[13], &Buf1);
  v8 = (char *)(this + 177);
  v9 = this[179];
  if ( !v9 )
  {
LABEL_34:
    v23 = this[1];
    if ( v23 )
    {
      v24 = (DeclNotation *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v23->lpVtbl->Alloc)(this[1], 80);
    }
    else if ( g_pMalloc )
    {
      v24 = (DeclNotation *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 80);
    }
    else
    {
      v24 = (DeclNotation *)HeapAlloc(g_hHeap, 0, 0x50u);
    }
    if ( v24 )
    {
      *((_QWORD *)v24 + 1) = v23;
      v21 = DeclNotation::DeclNotation(v24, this[1], (struct StringPtr *)&Buf1);
      v25 = (*(__int64 (__fastcall **)(DeclNotation *))(*(_QWORD *)v21 + 8LL))(v21);
      _htable<DeclNotation>::insert(v8, v21, v25);
      goto LABEL_41;
    }
LABEL_49:
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  v10 = Buf1;
  v11 = (unsigned __int16 *)Buf1;
  v12 = v33;
  v13 = 2LL * v33;
  v14 = v33;
  if ( Buf1 < (char *)Buf1 + v13 )
  {
    do
      v14 = *v11++ ^ (33 * v14);
    while ( v11 < (unsigned __int16 *)((char *)Buf1 + v13) );
  }
  v15 = *((unsigned int *)this + 361);
  v16 = &v9[3 * (v14 % ((int)v15 - 1))];
  v38 = &v9[3 * v15];
  while ( 1 )
  {
    lpVtbl = v16[1].lpVtbl;
    if ( !lpVtbl )
      goto LABEL_33;
    if ( v14 == LODWORD(v16[2].lpVtbl) && v12 == LODWORD(lpVtbl->AddRef) && !memcmp(v10, lpVtbl->QueryInterface, v13) )
      break;
    v16 += 3;
    if ( v16 == v38 )
      v16 = v9;
  }
  if ( !v16->lpVtbl )
  {
LABEL_33:
    v8 = (char *)(this + 177);
    goto LABEL_34;
  }
  v19 = this[1];
  if ( v19 )
  {
    v20 = (DeclNotation *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v19->lpVtbl->Alloc)(this[1], 80);
  }
  else if ( g_pMalloc )
  {
    v20 = (DeclNotation *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 80);
  }
  else
  {
    v20 = (DeclNotation *)HeapAlloc(g_hHeap, 0, 0x50u);
  }
  if ( !v20 )
    goto LABEL_49;
  *((_QWORD *)v20 + 1) = v19;
  v21 = DeclNotation::DeclNotation(v20, this[1], (struct StringPtr *)&CodeStringPtr::empty);
  v22 = this[187];
  if ( v22 )
    ((void (__fastcall *)(struct IMalloc *, __int64))v22->lpVtbl->QueryInterface)(v22, 1);
  this[187] = (struct IMalloc *)v21;
LABEL_41:
  YReader::ParseDeclExternalId((YReader *)this, (struct StringPtr *)&v36, (struct StringPtr *)&v34, 1);
  (*(void (__fastcall **)(DeclNotation *, __int64 *))(*(_QWORD *)v21 + 32LL))(v21, &v36);
  if ( v35 )
  {
    v26 = this[58][*((_DWORD *)this + 118) - 1].lpVtbl;
    v27 = (*((__int64 (__fastcall **)(struct IMallocVtbl *))v26->QueryInterface + 5))(v26);
    v28 = *(_QWORD *)v21;
    v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 40LL))(v27);
    (*(void (__fastcall **)(DeclNotation *, __int64 *, __int64))(v28 + 72))(v21, &v34, v29);
  }
  if ( *((_DWORD *)this + 28) != 48 )
  {
    MXRRaiseException(-1072894419);
    JUMPOUT(0x1004070F8LL);
  }
  *((_DWORD *)this + 444) = 13;
  *((_OWORD *)this + 101) = *(_OWORD *)(*(__int64 (__fastcall **)(DeclNotation *))(*(_QWORD *)v21 + 8LL))(v21);
  *((_OWORD *)this + 104) = *(_OWORD *)(*(__int64 (__fastcall **)(DeclNotation *))(*(_QWORD *)v21 + 24LL))(v21);
  v30 = *(_QWORD *)v21;
  if ( *((_BYTE *)this + 1788) )
    v31 = (_OWORD *)(*(__int64 (__fastcall **)(DeclNotation *))(v30 + 56))(v21);
  else
    v31 = (_OWORD *)(*(__int64 (__fastcall **)(DeclNotation *))(v30 + 40))(v21);
  *((_OWORD *)this + 105) = *v31;
}

```

## disassembly

```asm
0x100406cc0  mov     [rsp+arg_0], rbx
0x100406cc5  mov     [rsp+arg_10], rsi
0x100406cca  push    rdi
0x100406ccb  push    r12
0x100406ccd  push    r13
0x100406ccf  push    r14
0x100406cd1  push    r15
0x100406cd3  sub     rsp, 70h
0x100406cd7  mov     rsi, rcx
0x100406cda  xor     eax, eax
0x100406cdc  mov     [rsp+98h+var_50], eax
0x100406ce0  mov     [rsp+98h+var_38], rax
0x100406ce5  mov     [rsp+98h+var_30], eax
0x100406ce9  mov     [rsp+98h+var_48], rax
0x100406cee  mov     [rsp+98h+var_40], eax
0x100406cf2  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100406cf7  cmp     eax, 0Ch
0x100406cfa  jnz     loc_1004070D7
0x100406d00  mov     rcx, [rsi+68h]
0x100406d04  mov     rax, [rcx]
0x100406d07  mov     rax, [rax+60h]
0x100406d0b  call    cs:__guard_dispatch_icall_fptr
0x100406d11  mov     edi, eax
0x100406d13  mov     rbx, [rsi+1B8h]
0x100406d1a  mov     rdx, [rbx+10h]
0x100406d1e  mov     ecx, [rbx+18h]
0x100406d21  sub     ecx, edx
0x100406d23  cmp     ecx, eax
0x100406d25  jnb     short loc_100406D72
0x100406d27  mov     rcx, [rbx+8]
0x100406d2b  test    rcx, rcx
0x100406d2e  jz      short loc_100406D4C
0x100406d30  mov     rbx, rcx
0x100406d33  mov     eax, [rcx+18h]
0x100406d36  sub     eax, ecx
0x100406d38  sub     eax, 20h ; ' '
0x100406d3b  cmp     eax, edi
0x100406d3d  jnb     loc_100406E38
0x100406d43  mov     rcx, [rcx+8]
0x100406d47  test    rcx, rcx
0x100406d4a  jnz     short loc_100406D30
0x100406d4c  lfence
0x100406d4f  mov     r8, rbx; struct BlockAlloc::Header *
0x100406d52  mov     edx, edi; unsigned int
0x100406d54  lea     rcx, [rsi+1A0h]; this
0x100406d5b  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x100406d60  mov     [rbx+8], rax
0x100406d64  mov     rbx, rax
0x100406d67  mov     [rsi+1B8h], rbx
0x100406d6e  mov     rdx, [rbx+10h]
0x100406d72  add     [rbx+10h], rdi
0x100406d76  mov     [rsp+98h+Buf1], rdx
0x100406d7b  mov     rcx, [rsi+68h]
0x100406d7f  mov     rax, [rcx]
0x100406d82  lea     rdx, [rsp+98h+Buf1]
0x100406d87  mov     rax, [rax+68h]
0x100406d8b  call    cs:__guard_dispatch_icall_fptr
0x100406d91  lea     r14, [rsi+588h]
0x100406d98  mov     r15, [rsi+598h]
0x100406d9f  test    r15, r15
0x100406da2  jz      loc_100406F0D
0x100406da8  mov     r12, [rsp+98h+Buf1]
0x100406dad  mov     rcx, r12
0x100406db0  mov     r14d, [rsp+98h+var_50]
0x100406db5  lea     r13, [r14+r14]
0x100406db9  lea     rdx, [r12+r13]
0x100406dbd  mov     edi, r14d
0x100406dc0  cmp     r12, rdx
0x100406dc3  jnb     short loc_100406DE1
0x100406dc5  nop     word ptr [rax+rax+00000000h]
0x100406dd0  imul    edi, 21h ; '!'
0x100406dd3  movzx   eax, word ptr [rcx]
0x100406dd6  xor     edi, eax
0x100406dd8  add     rcx, 2
0x100406ddc  cmp     rcx, rdx
0x100406ddf  jb      short loc_100406DD0
0x100406de1  mov     r8d, [rsi+5A4h]
0x100406de8  lea     ecx, [r8-1]
0x100406dec  xor     edx, edx
0x100406dee  mov     eax, edi
0x100406df0  div     ecx
0x100406df2  lea     rax, [rdx+rdx*2]
0x100406df6  lea     rbx, [r15+rax*8]
0x100406dfa  lea     rax, [r8+r8*2]
0x100406dfe  lea     rax, [r15+rax*8]
0x100406e02  mov     [rsp+98h+arg_8], rax
0x100406e0a  mov     rax, [rbx+8]
0x100406e0e  test    rax, rax
0x100406e11  jz      loc_100406F06
0x100406e17  cmp     edi, [rbx+10h]
0x100406e1a  jnz     short loc_100406E4B
0x100406e1c  cmp     r14d, [rax+8]
0x100406e20  jnz     short loc_100406E45
0x100406e22  mov     r8, r13; Size
0x100406e25  mov     rdx, [rax]; Buf2
0x100406e28  mov     rcx, r12; Buf1
0x100406e2b  call    memcmp
0x100406e30  test    eax, eax
0x100406e32  jnz     short loc_100406E45
0x100406e34  mov     al, 1
0x100406e36  jmp     short loc_100406E47
0x100406e38  lea     rax, [rcx+20h]
0x100406e3c  mov     [rcx+10h], rax
0x100406e40  jmp     loc_100406D67
0x100406e45  xor     al, al
0x100406e47  test    al, al
0x100406e49  jnz     short loc_100406E5D
0x100406e4b  add     rbx, 18h
0x100406e4f  cmp     rbx, [rsp+98h+arg_8]
0x100406e57  cmovz   rbx, r15
0x100406e5b  jmp     short loc_100406E0A
0x100406e5d  cmp     qword ptr [rbx], 0
0x100406e61  jz      loc_100406F06
0x100406e67  mov     rbx, [rsi+8]
0x100406e6b  test    rbx, rbx
0x100406e6e  jz      short loc_100406E87
0x100406e70  mov     rax, [rbx]
0x100406e73  mov     edx, 50h ; 'P'
0x100406e78  mov     rcx, rbx
0x100406e7b  mov     rax, [rax+18h]
0x100406e7f  call    cs:__guard_dispatch_icall_fptr
0x100406e85  jmp     short loc_100406EBA
0x100406e87  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100406e8e  test    rcx, rcx
0x100406e91  jz      short loc_100406EA7
0x100406e93  mov     rax, [rcx]
0x100406e96  mov     edx, 50h ; 'P'
0x100406e9b  mov     rax, [rax+18h]
0x100406e9f  call    cs:__guard_dispatch_icall_fptr
0x100406ea5  jmp     short loc_100406EBA
0x100406ea7  xor     edx, edx; dwFlags
0x100406ea9  lea     r8d, [rdx+50h]; dwBytes
0x100406ead  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100406eb4  call    cs:__imp_HeapAlloc
0x100406eba  test    rax, rax
0x100406ebd  jz      loc_1004070E2
0x100406ec3  mov     [rax+8], rbx
0x100406ec7  lea     r8, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x100406ece  mov     rdx, [rsi+8]; struct IMalloc *
0x100406ed2  mov     rcx, rax; this
0x100406ed5  call    ??0DeclNotation@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclNotation::DeclNotation(IMalloc *,StringPtr *)
0x100406eda  mov     rdi, rax
0x100406edd  mov     rcx, [rsi+5D8h]
0x100406ee4  test    rcx, rcx
0x100406ee7  jz      short loc_100406EFA
0x100406ee9  mov     rdx, [rcx]
0x100406eec  mov     rax, [rdx]
0x100406eef  mov     edx, 1
0x100406ef4  call    cs:__guard_dispatch_icall_fptr
0x100406efa  mov     [rsi+5D8h], rdi
0x100406f01  jmp     loc_100406FA8
0x100406f06  lea     r14, [rsi+588h]
0x100406f0d  mov     rbx, [rsi+8]
0x100406f11  test    rbx, rbx
0x100406f14  jz      short loc_100406F2D
0x100406f16  mov     rax, [rbx]
0x100406f19  mov     edx, 50h ; 'P'
0x100406f1e  mov     rcx, rbx
0x100406f21  mov     rax, [rax+18h]
0x100406f25  call    cs:__guard_dispatch_icall_fptr
0x100406f2b  jmp     short loc_100406F60
0x100406f2d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100406f34  test    rcx, rcx
0x100406f37  jz      short loc_100406F4D
0x100406f39  mov     rax, [rcx]
0x100406f3c  mov     edx, 50h ; 'P'
0x100406f41  mov     rax, [rax+18h]
0x100406f45  call    cs:__guard_dispatch_icall_fptr
0x100406f4b  jmp     short loc_100406F60
0x100406f4d  xor     edx, edx; dwFlags
0x100406f4f  lea     r8d, [rdx+50h]; dwBytes
0x100406f53  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100406f5a  call    cs:__imp_HeapAlloc
0x100406f60  test    rax, rax
0x100406f63  jz      loc_1004070E2
0x100406f69  mov     [rax+8], rbx
0x100406f6d  lea     r8, [rsp+98h+Buf1]; struct StringPtr *
0x100406f72  mov     rdx, [rsi+8]; struct IMalloc *
0x100406f76  mov     rcx, rax; this
0x100406f79  call    ??0DeclNotation@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclNotation::DeclNotation(IMalloc *,StringPtr *)
0x100406f7e  mov     rdi, rax
0x100406f81  mov     [rsp+98h+arg_8], rax
0x100406f89  mov     rax, [rax]
0x100406f8c  mov     rcx, rdi
0x100406f8f  mov     rax, [rax+8]
0x100406f93  call    cs:__guard_dispatch_icall_fptr
0x100406f99  mov     r8, rax
0x100406f9c  mov     rdx, rdi
0x100406f9f  mov     rcx, r14
0x100406fa2  call    ?insert@?$_htable@VDeclNotation@@@@QEAAXPEAVDeclNotation@@PEAUStringPtr@@@Z; _htable<DeclNotation>::insert(DeclNotation *,StringPtr *)
0x100406fa7  nop
0x100406fa8  mov     r9b, 1; bool
0x100406fab  lea     r8, [rsp+98h+var_48]; struct StringPtr *
0x100406fb0  lea     rdx, [rsp+98h+var_38]; struct StringPtr *
0x100406fb5  mov     rcx, rsi; this
0x100406fb8  call    ?ParseDeclExternalId@YReader@@AEAAXPEAUStringPtr@@0_N@Z; YReader::ParseDeclExternalId(StringPtr *,StringPtr *,bool)
0x100406fbd  mov     rax, [rdi]
0x100406fc0  lea     rdx, [rsp+98h+var_38]
0x100406fc5  mov     rcx, rdi
0x100406fc8  mov     rax, [rax+20h]
0x100406fcc  call    cs:__guard_dispatch_icall_fptr
0x100406fd2  cmp     [rsp+98h+var_40], 0
0x100406fd7  jz      short loc_100407024
0x100406fd9  mov     ecx, [rsi+1D8h]
0x100406fdf  dec     ecx
0x100406fe1  mov     rax, [rsi+1D0h]
0x100406fe8  mov     rcx, [rax+rcx*8]
0x100406fec  mov     rax, [rcx]
0x100406fef  mov     rax, [rax+28h]
0x100406ff3  call    cs:__guard_dispatch_icall_fptr
0x100406ff9  mov     rdx, rax
0x100406ffc  mov     rbx, [rdi]
0x100406fff  mov     rcx, [rax]
0x100407002  mov     rax, [rcx+28h]
0x100407006  mov     rcx, rdx
0x100407009  call    cs:__guard_dispatch_icall_fptr
0x10040700f  mov     r8, rax
0x100407012  lea     rdx, [rsp+98h+var_48]
0x100407017  mov     rcx, rdi
0x10040701a  mov     rax, [rbx+48h]
0x10040701e  call    cs:__guard_dispatch_icall_fptr
0x100407024  cmp     dword ptr [rsi+70h], 30h ; '0'
0x100407028  jnz     loc_1004070ED
0x10040702e  mov     dword ptr [rsi+6F0h], 0Dh
0x100407038  mov     rax, [rdi]
0x10040703b  mov     rcx, rdi
0x10040703e  mov     rax, [rax+8]
0x100407042  call    cs:__guard_dispatch_icall_fptr
0x100407048  movups  xmm0, xmmword ptr [rax]
0x10040704b  movups  xmmword ptr [rsi+650h], xmm0
0x100407052  mov     rax, [rdi]
0x100407055  mov     rcx, rdi
0x100407058  mov     rax, [rax+18h]
0x10040705c  call    cs:__guard_dispatch_icall_fptr
0x100407062  movups  xmm0, xmmword ptr [rax]
0x100407065  movups  xmmword ptr [rsi+680h], xmm0
0x10040706c  mov     rax, [rdi]
0x10040706f  mov     rcx, rdi
0x100407072  cmp     byte ptr [rsi+6FCh], 0
0x100407079  jz      short loc_100407081
0x10040707b  mov     rax, [rax+38h]
0x10040707f  jmp     short loc_100407085
0x100407081  mov     rax, [rax+28h]
0x100407085  call    cs:__guard_dispatch_icall_fptr
0x10040708b  movups  xmm0, xmmword ptr [rax]
0x10040708e  movups  xmmword ptr [rsi+690h], xmm0
0x100407095  lea     r11, [rsp+98h+var_28]
0x10040709a  mov     rbx, [r11+30h]
0x10040709e  mov     rsi, [r11+40h]
0x1004070a2  mov     rsp, r11
0x1004070a5  pop     r15
0x1004070a7  pop     r14
0x1004070a9  pop     r13
0x1004070ab  pop     r12
0x1004070ad  pop     rdi
0x1004070ae  retn
0x1004070af  mov     rcx, [rsp+98h+arg_8]
0x1004070b7  test    rcx, rcx
0x1004070ba  jz      short loc_1004070CD
0x1004070bc  mov     rax, [rcx]
0x1004070bf  mov     edx, 1
0x1004070c4  mov     rax, [rax]
0x1004070c7  call    cs:__guard_dispatch_icall_fptr
0x1004070cd  mov     ecx, [rsp+98h+var_78]; int
0x1004070d1  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004070d6  nop
0x1004070d7  mov     ecx, 0C00CEE39h; int
0x1004070dc  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004070e1  int     3; Trap to Debugger
0x1004070e2  mov     ecx, 8007000Eh; int
0x1004070e7  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004070ec  int     3; Trap to Debugger
0x1004070ed  mov     ecx, 0C00CEE2Dh; int
0x1004070f2  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x1004070f7  nop
0x100439f20  push    rbp
0x100439f22  sub     rsp, 20h
0x100439f26  mov     rbp, rdx
0x100439f29  mov     [rbp+38h], rcx
0x100439f2d  mov     [rbp+30h], rcx
0x100439f31  mov     rax, [rbp+30h]
0x100439f35  mov     rcx, [rax]
0x100439f38  mov     [rbp+28h], rcx
0x100439f3c  mov     rax, [rbp+28h]
0x100439f40  mov     eax, [rax]
0x100439f42  cmp     eax, 0C0000005h
0x100439f47  jz      short loc_100439F79
0x100439f49  add     eax, 1FFFFFFFh
0x100439f4e  cmp     eax, 1
0x100439f51  ja      short loc_100439F69
0x100439f53  mov     rax, [rbp+28h]
0x100439f57  cmp     dword ptr [rax+18h], 1
0x100439f5b  jnz     short loc_100439F69
0x100439f5d  mov     rax, [rbp+28h]
0x100439f61  mov     ecx, [rax+20h]
0x100439f64  mov     [rbp+20h], ecx
0x100439f67  jmp     short loc_100439F70
0x100439f69  mov     dword ptr [rbp+20h], 8000FFFFh
0x100439f70  mov     dword ptr [rbp+24h], 1
0x100439f77  jmp     short loc_100439F80
  ... truncated ...
```
