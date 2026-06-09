# YReader::ParseDeclAttlist(void)

- ea: `0x100405110`
- end: `0x1004055bb`
- name: `?ParseDeclAttlist@YReader@@AEAAXXZ`
- size: `1195`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x1004017f0`
- `0x100405110`
- `0x1004055d0`
- `0x100405a00`
- `0x10040a020`
- `0x10040ca10`
- `0x100415560`
- `0x1004169d0`
- `0x100416cb0`
- `0x100417840`
- `0x100423dd0`
- `0x1004394f0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x10040524d`
- `KERNEL32!HeapAlloc` at `0x10040544f`
- `KERNEL32!HeapAlloc` at `0x1004054cd`
- `KERNEL32!HeapAlloc` at `0x10040524d`
- `KERNEL32!HeapAlloc` at `0x10040544f`
- `KERNEL32!HeapAlloc` at `0x1004054cd`

## pseudocode

```c
void __fastcall YReader::ParseDeclAttlist(struct IMalloc **this)
{
  unsigned int v2; // eax
  __int64 v3; // rdi
  struct BlockAlloc::Header *v4; // rbx
  void *v5; // rdx
  __int64 v6; // rcx
  struct BlockAlloc::Header *v7; // rax
  struct DeclElement *v8; // r15
  struct IMalloc *v9; // rbx
  DeclElement *v10; // rax
  __int64 v11; // rax
  int TokenDeclInner; // eax
  unsigned int v13; // eax
  __int64 v14; // rdi
  struct BlockAlloc::Header *v15; // rbx
  void *v16; // rdx
  __int64 v17; // rcx
  struct BlockAlloc::Header *v18; // rax
  __int64 v19; // rax
  _QWORD *v20; // rdi
  _QWORD *v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rbx
  const void **v24; // rax
  unsigned int v25; // eax
  DeclAttDef **v26; // rdi
  struct IMalloc *v27; // rbx
  DeclAttDef *v28; // rax
  DeclAttDef *v29; // rbx
  struct IMalloc *v30; // rbx
  DeclAttDef *v31; // rax
  struct IMalloc *v32; // rcx
  int v33; // [rsp+20h] [rbp-68h]
  void *Buf1; // [rsp+40h] [rbp-48h] BYREF
  unsigned int v35; // [rsp+48h] [rbp-40h]
  __int128 v36; // [rsp+50h] [rbp-38h]
  void (__fastcall ***v37)(_QWORD, __int64); // [rsp+98h] [rbp+10h]

  v35 = 0;
  if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 12 )
  {
    MXRRaiseException(-1072894407);
    if ( v37 )
      (**v37)(v37, 1);
    MXRRaiseException(v33);
    goto LABEL_57;
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
  v8 = DeclDoctype::LookupElement((DeclDoctype *)(this + 157), (struct StringPtr *)&Buf1);
  if ( v8 )
    goto LABEL_17;
  v9 = this[1];
  if ( v9 )
  {
    v10 = (DeclElement *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v9->lpVtbl->Alloc)(this[1], 120);
  }
  else if ( g_pMalloc )
  {
    v10 = (DeclElement *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 120);
  }
  else
  {
    v10 = (DeclElement *)HeapAlloc(g_hHeap, 0, 0x78u);
  }
  if ( !v10 )
  {
LABEL_57:
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  *((_QWORD *)v10 + 1) = v9;
  v8 = DeclElement::DeclElement(v10, this[1], (struct StringPtr *)&Buf1);
  v11 = (*(__int64 (__fastcall **)(struct DeclElement *))(*(_QWORD *)v8 + 8LL))(v8);
  _htable<DeclNotation>::insert(this + 182, v8, v11);
LABEL_17:
  while ( 1 )
  {
    TokenDeclInner = YReader::GetTokenDeclInner((YReader *)this);
    if ( TokenDeclInner != 12 )
      break;
    v13 = ((__int64 (__fastcall *)(struct IMalloc *))this[13]->lpVtbl[1].Alloc)(this[13]);
    v14 = v13;
    v15 = (struct BlockAlloc::Header *)this[55];
    v16 = (void *)*((_QWORD *)v15 + 2);
    if ( *((_DWORD *)v15 + 6) - (int)v16 < v13 )
    {
      v17 = *((_QWORD *)v15 + 1);
      if ( v17 )
      {
        while ( 1 )
        {
          v15 = (struct BlockAlloc::Header *)v17;
          if ( *(_DWORD *)(v17 + 24) - (int)v17 - 32 >= v13 )
            break;
          v17 = *(_QWORD *)(v17 + 8);
          if ( !v17 )
            goto LABEL_22;
        }
        *(_QWORD *)(v17 + 16) = v17 + 32;
      }
      else
      {
LABEL_22:
        _mm_lfence();
        v18 = BlockAlloc::EnqueueBlock((BlockAlloc *)(this + 52), v13, v15);
        *((_QWORD *)v15 + 1) = v18;
        v15 = v18;
      }
      this[55] = (struct IMalloc *)v15;
      v16 = (void *)*((_QWORD *)v15 + 2);
    }
    *((_QWORD *)v15 + 2) += v14;
    Buf1 = v16;
    ((void (__fastcall *)(struct IMalloc *, void **))this[13]->lpVtbl[1].Realloc)(this[13], &Buf1);
    *(_QWORD *)&v36 = Buf1;
    DWORD2(v36) = *((_DWORD *)this + 80);
    v19 = *((unsigned int *)v8 + 20);
    if ( (_DWORD)v19 )
    {
      v20 = (_QWORD *)*((_QWORD *)v8 + 9);
      v21 = &v20[v19];
      while ( 1 )
      {
        if ( v20 >= v21 )
          goto LABEL_32;
        v22 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
        if ( v35 == *(_DWORD *)(v22 + 8) )
        {
          v23 = v35;
          v24 = (const void **)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v20 + 8LL))(*v20);
          if ( !memcmp(Buf1, *v24, 2 * v23) )
            break;
        }
        ++v20;
      }
      if ( *v20 )
      {
LABEL_42:
        v30 = this[1];
        if ( v30 )
        {
          v31 = (DeclAttDef *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v30->lpVtbl->Alloc)(this[1], 184);
        }
        else if ( g_pMalloc )
        {
          v31 = (DeclAttDef *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(
                                g_pMalloc,
                                184);
        }
        else
        {
          v31 = (DeclAttDef *)HeapAlloc(g_hHeap, 0, 0xB8u);
        }
        if ( !v31 )
          goto LABEL_57;
        *((_QWORD *)v31 + 1) = v30;
        v29 = DeclAttDef::DeclAttDef(v31, this[1], (struct StringPtr *)&CodeStringPtr::empty);
        v32 = this[187];
        if ( v32 )
          ((void (__fastcall *)(struct IMalloc *, __int64))v32->lpVtbl->QueryInterface)(v32, 1);
        this[187] = (struct IMalloc *)v29;
        goto LABEL_51;
      }
    }
LABEL_32:
    if ( *((_BYTE *)this + 1795) )
      goto LABEL_42;
    v25 = *((_DWORD *)v8 + 20);
    if ( *((_DWORD *)v8 + 21) == v25 )
    {
      _stack<void (Scanner::*)(void),8>::grow((__int64)v8 + 56, 0);
      v25 = *((_DWORD *)v8 + 20);
    }
    v26 = (DeclAttDef **)(*((_QWORD *)v8 + 9) + 8LL * v25);
    *((_DWORD *)v8 + 20) = v25 + 1;
    *v26 = 0;
    v27 = this[1];
    if ( v27 )
    {
      v28 = (DeclAttDef *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v27->lpVtbl->Alloc)(this[1], 184);
    }
    else if ( g_pMalloc )
    {
      v28 = (DeclAttDef *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 184);
    }
    else
    {
      v28 = (DeclAttDef *)HeapAlloc(g_hHeap, 0, 0xB8u);
    }
    if ( !v28 )
      goto LABEL_57;
    *((_QWORD *)v28 + 1) = v27;
    v29 = DeclAttDef::DeclAttDef(v28, this[1], (struct StringPtr *)&Buf1);
    *v26 = v29;
LABEL_51:
    *((_OWORD *)v29 + 3) = v36;
    YReader::ParseDeclAttlistType((YReader *)this, v29);
    YReader::ParseDeclAttlistDefault((YReader *)this, v29);
    *((_DWORD *)v29 + 33) = 0;
    *((_QWORD *)v29 + 17) = 0;
  }
  if ( TokenDeclInner != 48 )
  {
    MXRRaiseException(-1072894419);
    JUMPOUT(0x1004055BBLL);
  }
}

```

## disassembly

```asm
0x100405110  mov     [rsp+arg_0], rbx
0x100405115  mov     [rsp+arg_10], rsi
0x10040511a  push    rdi
0x10040511b  push    r12
0x10040511d  push    r13
0x10040511f  push    r14
0x100405121  push    r15
0x100405123  sub     rsp, 60h
0x100405127  mov     r14, rcx
0x10040512a  mov     [rsp+88h+var_40], 0
0x100405132  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x100405137  cmp     eax, 0Ch
0x10040513a  jnz     loc_100405572
0x100405140  mov     rcx, [r14+68h]
0x100405144  mov     rax, [rcx]
0x100405147  mov     rax, [rax+60h]
0x10040514b  call    cs:__guard_dispatch_icall_fptr
0x100405151  mov     edi, eax
0x100405153  lea     r13, [r14+1A0h]
0x10040515a  mov     rbx, [r13+18h]
0x10040515e  mov     rdx, [rbx+10h]
0x100405162  mov     ecx, [rbx+18h]
0x100405165  sub     ecx, edx
0x100405167  cmp     ecx, eax
0x100405169  jnb     short loc_1004051BB
0x10040516b  mov     rcx, [rbx+8]
0x10040516f  test    rcx, rcx
0x100405172  jz      short loc_10040519C
0x100405174  nop     dword ptr [rax+00h]
0x100405178  nop     dword ptr [rax+rax+00000000h]
0x100405180  mov     rbx, rcx
0x100405183  mov     eax, [rcx+18h]
0x100405186  sub     eax, ecx
0x100405188  sub     eax, 20h ; ' '
0x10040518b  cmp     eax, edi
0x10040518d  jnb     loc_100405216
0x100405193  mov     rcx, [rcx+8]
0x100405197  test    rcx, rcx
0x10040519a  jnz     short loc_100405180
0x10040519c  lfence
0x10040519f  mov     r8, rbx; struct BlockAlloc::Header *
0x1004051a2  mov     edx, edi; unsigned int
0x1004051a4  mov     rcx, r13; this
0x1004051a7  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x1004051ac  mov     [rbx+8], rax
0x1004051b0  mov     rbx, rax
0x1004051b3  mov     [r13+18h], rbx
0x1004051b7  mov     rdx, [rbx+10h]
0x1004051bb  add     [rbx+10h], rdi
0x1004051bf  mov     [rsp+88h+Buf1], rdx
0x1004051c4  mov     rcx, [r14+68h]
0x1004051c8  mov     rax, [rcx]
0x1004051cb  lea     rdx, [rsp+88h+Buf1]
0x1004051d0  mov     rax, [rax+68h]
0x1004051d4  call    cs:__guard_dispatch_icall_fptr
0x1004051da  lea     rdx, [rsp+88h+Buf1]; struct StringPtr *
0x1004051df  lea     rcx, [r14+4E8h]; this
0x1004051e6  call    ?LookupElement@DeclDoctype@@QEAAPEAVDeclElement@@PEAUStringPtr@@@Z; DeclDoctype::LookupElement(StringPtr *)
0x1004051eb  mov     r15, rax
0x1004051ee  test    rax, rax
0x1004051f1  jnz     loc_10040529F
0x1004051f7  mov     rbx, [r14+8]
0x1004051fb  test    rbx, rbx
0x1004051fe  jz      short loc_100405220
0x100405200  mov     rax, [rbx]
0x100405203  lea     edx, [r15+78h]
0x100405207  mov     rcx, rbx
0x10040520a  mov     rax, [rax+18h]
0x10040520e  call    cs:__guard_dispatch_icall_fptr
0x100405214  jmp     short loc_100405253
0x100405216  lea     rax, [rcx+20h]
0x10040521a  mov     [rcx+10h], rax
0x10040521e  jmp     short loc_1004051B3
0x100405220  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100405227  test    rcx, rcx
0x10040522a  jz      short loc_100405240
0x10040522c  mov     rax, [rcx]
0x10040522f  mov     edx, 78h ; 'x'
0x100405234  mov     rax, [rax+18h]
0x100405238  call    cs:__guard_dispatch_icall_fptr
0x10040523e  jmp     short loc_100405253
0x100405240  xor     edx, edx; dwFlags
0x100405242  lea     r8d, [rdx+78h]; dwBytes
0x100405246  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040524d  call    cs:__imp_HeapAlloc
0x100405253  test    rax, rax
0x100405256  jz      loc_1004055A5
0x10040525c  mov     [rax+8], rbx
0x100405260  lea     r8, [rsp+88h+Buf1]; struct StringPtr *
0x100405265  mov     rdx, [r14+8]; struct IMalloc *
0x100405269  mov     rcx, rax; this
0x10040526c  call    ??0DeclElement@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclElement::DeclElement(IMalloc *,StringPtr *)
0x100405271  mov     r15, rax
0x100405274  mov     [rsp+88h+arg_8], rax
0x10040527c  mov     rax, [rax]
0x10040527f  mov     rcx, r15
0x100405282  mov     rax, [rax+8]
0x100405286  call    cs:__guard_dispatch_icall_fptr
0x10040528c  mov     r8, rax
0x10040528f  lea     rcx, [r14+5B0h]
0x100405296  mov     rdx, r15
0x100405299  call    ?insert@?$_htable@VDeclNotation@@@@QEAAXPEAVDeclNotation@@PEAUStringPtr@@@Z; _htable<DeclNotation>::insert(DeclNotation *,StringPtr *)
0x10040529e  nop
0x10040529f  mov     rcx, r14; this
0x1004052a2  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004052a7  cmp     eax, 0Ch
0x1004052aa  jnz     loc_100405553
0x1004052b0  mov     rcx, [r14+68h]
0x1004052b4  mov     rax, [rcx]
0x1004052b7  mov     rax, [rax+60h]
0x1004052bb  call    cs:__guard_dispatch_icall_fptr
0x1004052c1  mov     edi, eax
0x1004052c3  mov     rbx, [r13+18h]
0x1004052c7  mov     rdx, [rbx+10h]
0x1004052cb  mov     ecx, [rbx+18h]
0x1004052ce  sub     ecx, edx
0x1004052d0  cmp     ecx, eax
0x1004052d2  jnb     short loc_10040531B
0x1004052d4  mov     rcx, [rbx+8]
0x1004052d8  test    rcx, rcx
0x1004052db  jz      short loc_1004052FC
0x1004052dd  nop     dword ptr [rax]
0x1004052e0  mov     rbx, rcx
0x1004052e3  mov     eax, [rcx+18h]
0x1004052e6  sub     eax, ecx
0x1004052e8  sub     eax, 20h ; ' '
0x1004052eb  cmp     eax, edi
0x1004052ed  jnb     loc_1004053AA
0x1004052f3  mov     rcx, [rcx+8]
0x1004052f7  test    rcx, rcx
0x1004052fa  jnz     short loc_1004052E0
0x1004052fc  lfence
0x1004052ff  mov     r8, rbx; struct BlockAlloc::Header *
0x100405302  mov     edx, edi; unsigned int
0x100405304  mov     rcx, r13; this
0x100405307  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040530c  mov     [rbx+8], rax
0x100405310  mov     rbx, rax
0x100405313  mov     [r13+18h], rbx
0x100405317  mov     rdx, [rbx+10h]
0x10040531b  add     [rbx+10h], rdi
0x10040531f  mov     [rsp+88h+Buf1], rdx
0x100405324  mov     rcx, [r14+68h]
0x100405328  mov     rax, [rcx]
0x10040532b  lea     rdx, [rsp+88h+Buf1]
0x100405330  mov     rax, [rax+68h]
0x100405334  call    cs:__guard_dispatch_icall_fptr
0x10040533a  mov     rax, [rsp+88h+Buf1]
0x10040533f  mov     qword ptr [rsp+88h+var_38], rax
0x100405344  mov     eax, [r14+140h]
0x10040534b  mov     dword ptr [rsp+88h+var_38+8], eax
0x10040534f  mov     eax, [r15+50h]
0x100405353  test    eax, eax
0x100405355  jz      short loc_1004053C1
0x100405357  mov     rdi, [r15+48h]
0x10040535b  lea     rsi, [rdi+rax*8]
0x10040535f  cmp     rdi, rsi
0x100405362  jnb     short loc_1004053C1
0x100405364  mov     rcx, [rdi]
0x100405367  mov     rax, [rcx]
0x10040536a  mov     rax, [rax+8]
0x10040536e  call    cs:__guard_dispatch_icall_fptr
0x100405374  mov     ecx, [rsp+88h+var_40]
0x100405378  cmp     ecx, [rax+8]
0x10040537b  jnz     short loc_1004053A4
0x10040537d  mov     ebx, ecx
0x10040537f  mov     rcx, [rdi]
0x100405382  mov     rax, [rcx]
0x100405385  mov     rax, [rax+8]
0x100405389  call    cs:__guard_dispatch_icall_fptr
0x10040538f  lea     r8, [rbx+rbx]; Size
0x100405393  mov     rdx, [rax]; Buf2
0x100405396  mov     rcx, [rsp+88h+Buf1]; Buf1
0x10040539b  call    memcmp
0x1004053a0  test    eax, eax
0x1004053a2  jz      short loc_1004053B7
0x1004053a4  add     rdi, 8
0x1004053a8  jmp     short loc_10040535F
0x1004053aa  lea     rax, [rcx+20h]
0x1004053ae  mov     [rcx+10h], rax
0x1004053b2  jmp     loc_100405313
0x1004053b7  cmp     qword ptr [rdi], 0
0x1004053bb  jnz     loc_10040547E
0x1004053c1  cmp     byte ptr [r14+703h], 0
0x1004053c9  jnz     loc_10040547E
0x1004053cf  mov     eax, [r15+50h]
0x1004053d3  cmp     [r15+54h], eax
0x1004053d7  jnz     short loc_1004053E8
0x1004053d9  xor     edx, edx
0x1004053db  lea     rcx, [r15+38h]
0x1004053df  call    ?grow@?$_stack@P8Scanner@@EAAXXZ$07@@AEAAXI@Z; _stack<void (Scanner::*)(void),8>::grow(uint)
0x1004053e4  mov     eax, [r15+50h]
0x1004053e8  mov     ecx, eax
0x1004053ea  mov     rax, [r15+48h]
0x1004053ee  lea     rdi, [rax+rcx*8]
0x1004053f2  lea     eax, [rcx+1]
0x1004053f5  mov     [r15+50h], eax
0x1004053f9  mov     qword ptr [rdi], 0
0x100405400  mov     rbx, [r14+8]
0x100405404  test    rbx, rbx
0x100405407  jz      short loc_100405420
0x100405409  mov     rax, [rbx]
0x10040540c  mov     edx, 0B8h
0x100405411  mov     rcx, rbx
0x100405414  mov     rax, [rax+18h]
0x100405418  call    cs:__guard_dispatch_icall_fptr
0x10040541e  jmp     short loc_100405455
0x100405420  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100405427  test    rcx, rcx
0x10040542a  jz      short loc_100405440
0x10040542c  mov     rax, [rcx]
0x10040542f  mov     edx, 0B8h
0x100405434  mov     rax, [rax+18h]
0x100405438  call    cs:__guard_dispatch_icall_fptr
0x10040543e  jmp     short loc_100405455
0x100405440  xor     edx, edx; dwFlags
0x100405442  mov     r8d, 0B8h; dwBytes
0x100405448  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040544f  call    cs:__imp_HeapAlloc
0x100405455  test    rax, rax
0x100405458  jz      loc_1004055A5
0x10040545e  mov     [rax+8], rbx
0x100405462  lea     r8, [rsp+88h+Buf1]; struct StringPtr *
0x100405467  mov     rdx, [r14+8]; struct IMalloc *
0x10040546b  mov     rcx, rax; this
0x10040546e  call    ??0DeclAttDef@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclAttDef::DeclAttDef(IMalloc *,StringPtr *)
0x100405473  mov     rbx, rax
0x100405476  mov     [rdi], rax
0x100405479  jmp     loc_10040551A
0x10040547e  mov     rbx, [r14+8]
0x100405482  test    rbx, rbx
0x100405485  jz      short loc_10040549E
0x100405487  mov     rax, [rbx]
0x10040548a  mov     edx, 0B8h
0x10040548f  mov     rcx, rbx
0x100405492  mov     rax, [rax+18h]
0x100405496  call    cs:__guard_dispatch_icall_fptr
0x10040549c  jmp     short loc_1004054D3
0x10040549e  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004054a5  test    rcx, rcx
0x1004054a8  jz      short loc_1004054BE
0x1004054aa  mov     rax, [rcx]
0x1004054ad  mov     edx, 0B8h
0x1004054b2  mov     rax, [rax+18h]
0x1004054b6  call    cs:__guard_dispatch_icall_fptr
0x1004054bc  jmp     short loc_1004054D3
0x1004054be  xor     edx, edx; dwFlags
0x1004054c0  mov     r8d, 0B8h; dwBytes
0x1004054c6  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004054cd  call    cs:__imp_HeapAlloc
0x1004054d3  test    rax, rax
0x1004054d6  jz      loc_1004055A5
0x1004054dc  mov     [rax+8], rbx
0x1004054e0  lea     r8, ?empty@CodeStringPtr@@2UStringPtr@@A; struct StringPtr *
0x1004054e7  mov     rdx, [r14+8]; struct IMalloc *
0x1004054eb  mov     rcx, rax; this
0x1004054ee  call    ??0DeclAttDef@@QEAA@PEAUIMalloc@@PEAUStringPtr@@@Z; DeclAttDef::DeclAttDef(IMalloc *,StringPtr *)
0x1004054f3  mov     rbx, rax
0x1004054f6  mov     rcx, [r14+5D8h]
0x1004054fd  test    rcx, rcx
0x100405500  jz      short loc_100405513
0x100405502  mov     rax, [rcx]
0x100405505  mov     edx, 1
0x10040550a  mov     rax, [rax]
0x10040550d  call    cs:__guard_dispatch_icall_fptr
0x100405513  mov     [r14+5D8h], rbx
0x10040551a  movups  xmm0, [rsp+88h+var_38]
0x10040551f  movups  xmmword ptr [rbx+30h], xmm0
0x100405523  mov     rdx, rbx; struct DeclAttDef *
0x100405526  mov     rcx, r14; this
0x100405529  call    ?ParseDeclAttlistType@YReader@@AEAAXPEAVDeclAttDef@@@Z; YReader::ParseDeclAttlistType(DeclAttDef *)
0x10040552e  mov     rdx, rbx; struct DeclAttDef *
0x100405531  mov     rcx, r14; this
0x100405534  call    ?ParseDeclAttlistDefault@YReader@@AEAAXPEAVDeclAttDef@@@Z; YReader::ParseDeclAttlistDefault(DeclAttDef *)
0x100405539  mov     dword ptr [rbx+84h], 0
0x100405543  mov     qword ptr [rbx+88h], 0
0x10040554e  jmp     loc_10040529F
0x100405553  cmp     eax, 30h ; '0'
0x100405556  jnz     short loc_1004055B0
0x100405558  lea     r11, [rsp+88h+var_28]
0x10040555d  mov     rbx, [r11+30h]
0x100405561  mov     rsi, [r11+40h]
0x100405565  mov     rsp, r11
0x100405568  pop     r15
0x10040556a  pop     r14
0x10040556c  pop     r13
0x10040556e  pop     r12
0x100405570  pop     rdi
0x100405571  retn
0x100405572  mov     ecx, 0C00CEE39h; int
0x100405577  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x10040557c  nop
0x10040557d  mov     rcx, [rsp+88h+arg_8]
0x100405585  test    rcx, rcx
0x100405588  jz      short loc_10040559B
0x10040558a  mov     rax, [rcx]
0x10040558d  mov     edx, 1
0x100405592  mov     rax, [rax]
0x100405595  call    cs:__guard_dispatch_icall_fptr
0x10040559b  mov     ecx, [rsp+88h+var_68]; int
  ... truncated ...
```
