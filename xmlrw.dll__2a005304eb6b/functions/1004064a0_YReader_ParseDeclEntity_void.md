# YReader::ParseDeclEntity(void)

- ea: `0x1004064a0`
- end: `0x1004069cd`
- name: `?ParseDeclEntity@YReader@@AEAAXXZ`
- size: `1325`
- prototype: `void __fastcall(YReader *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x100408ea0`
- `0x100409110`

## callees

- `0x100401780`
- `0x1004018f0`
- `0x1004064a0`
- `0x1004069e0`
- `0x100407100`
- `0x10040a020`
- `0x100415560`
- `0x100416970`
- `0x100416bc0`
- `0x100417060`
- `0x10041db90`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x1004066f4`
- `KERNEL32!HeapAlloc` at `0x10040679b`
- `KERNEL32!HeapAlloc` at `0x1004066f4`
- `KERNEL32!HeapAlloc` at `0x10040679b`

## pseudocode

```c
void __fastcall YReader::ParseDeclEntity(struct IMalloc **this)
{
  bool v2; // r14
  unsigned int v3; // eax
  __int64 v4; // rsi
  struct BlockAlloc::Header *v5; // rbx
  _WORD *v6; // rdx
  __int64 v7; // rcx
  struct BlockAlloc::Header *v8; // rax
  char *v9; // rcx
  void ***v10; // rax
  struct IMalloc *v11; // rbx
  DeclEntity *v12; // rax
  DeclEntity *v13; // rsi
  _OWORD *v14; // r15
  struct IMalloc *v15; // rbx
  DeclEntity *v16; // rax
  struct IMalloc *v17; // rcx
  struct IMallocVtbl *lpVtbl; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rax
  _OWORD *v24; // rax
  int v25; // [rsp+30h] [rbp-78h]
  _WORD *v26; // [rsp+50h] [rbp-58h] BYREF
  int v27; // [rsp+58h] [rbp-50h]
  __int64 v28; // [rsp+60h] [rbp-48h] BYREF
  int v29; // [rsp+68h] [rbp-40h]
  __int64 v30; // [rsp+70h] [rbp-38h] BYREF
  int v31; // [rsp+78h] [rbp-30h]
  DeclEntity *v32; // [rsp+B0h] [rbp+8h]

  v27 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  v2 = 0;
  if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) == 51 )
  {
    v2 = 1;
    YReader::GetTokenDeclInner((YReader *)this);
  }
  if ( *((_DWORD *)this + 28) != 12 )
  {
LABEL_67:
    MXRRaiseException(-1072894407);
    if ( v32 )
      (**(void (__fastcall ***)(DeclEntity *, __int64))v32)(v32, 1);
    MXRRaiseException(v25);
    goto LABEL_70;
  }
  v3 = ((__int64 (__fastcall *)(struct IMalloc *))this[13]->lpVtbl[1].Alloc)(this[13]);
  v4 = v3;
  v5 = (struct BlockAlloc::Header *)this[55];
  v6 = (_WORD *)*((_QWORD *)v5 + 2);
  if ( *((_DWORD *)v5 + 6) - (int)v6 < v3 )
  {
    v7 = *((_QWORD *)v5 + 1);
    if ( v7 )
    {
      while ( 1 )
      {
        v5 = (struct BlockAlloc::Header *)v7;
        if ( *(_DWORD *)(v7 + 24) - (int)v7 - 32 >= v3 )
          break;
        v7 = *(_QWORD *)(v7 + 8);
        if ( !v7 )
          goto LABEL_8;
      }
      *(_QWORD *)(v7 + 16) = v7 + 32;
    }
    else
    {
LABEL_8:
      _mm_lfence();
      v8 = BlockAlloc::EnqueueBlock((BlockAlloc *)(this + 52), v3, v5);
      *((_QWORD *)v5 + 1) = v8;
      v5 = v8;
    }
    this[55] = (struct IMalloc *)v5;
    v6 = (_WORD *)*((_QWORD *)v5 + 2);
  }
  *((_QWORD *)v5 + 2) += v4;
  v26 = v6;
  ((void (__fastcall *)(struct IMalloc *, _WORD **))this[13]->lpVtbl[1].Realloc)(this[13], &v26);
  if ( v2 )
  {
    v9 = (char *)(this + 172);
LABEL_33:
    v10 = (void ***)_htable<DeclEntity>::lookup(v9, &v26);
    goto LABEL_34;
  }
  if ( v27 != 4 )
  {
    if ( v27 == 2 )
    {
      if ( *v26 == 103 && *(_DWORD *)v26 == *CodeStringPtr::gt )
      {
        v10 = &s_EntityGt;
        goto LABEL_34;
      }
      if ( *v26 == 108 && *(_DWORD *)v26 == *CodeStringPtr::lt )
      {
        v10 = &s_EntityLt;
        goto LABEL_34;
      }
    }
    else if ( v27 == 3
           && *v26 == 97
           && *(_DWORD *)v26 == *CodeStringPtr::amp
           && v26[2] == *(_WORD *)(CodeStringPtr::amp + 4LL) )
    {
      v10 = &s_EntityAmp;
      goto LABEL_34;
    }
    goto LABEL_32;
  }
  if ( *v26 != 113 || *(_QWORD *)v26 != *CodeStringPtr::quot )
  {
    if ( *v26 == 97 && *(_QWORD *)v26 == *CodeStringPtr::apos )
    {
      v10 = &s_EntityApos;
      goto LABEL_34;
    }
LABEL_32:
    v9 = (char *)(this + 167);
    goto LABEL_33;
  }
  v10 = &s_EntityQuot;
LABEL_34:
  if ( v10 || *((_BYTE *)this + 1795) )
  {
    v15 = this[1];
    if ( v15 )
    {
      v16 = (DeclEntity *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v15->lpVtbl->Alloc)(this[1], 144);
    }
    else if ( g_pMalloc )
    {
      v16 = (DeclEntity *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 144);
    }
    else
    {
      v16 = (DeclEntity *)HeapAlloc(g_hHeap, 0, 0x90u);
    }
    if ( v16 )
    {
      *((_QWORD *)v16 + 1) = v15;
      v14 = &CodeStringPtr::empty;
      v13 = DeclEntity::DeclEntity(v16, this[1], (struct StringPtr *)&CodeStringPtr::empty, v2, 0, 0);
      v17 = this[187];
      if ( v17 )
        ((void (__fastcall *)(struct IMalloc *, __int64))v17->lpVtbl->QueryInterface)(v17, 1);
      this[187] = (struct IMalloc *)v13;
      goto LABEL_52;
    }
LABEL_70:
    MXRRaiseException(-2147024882);
    __debugbreak();
  }
  v11 = this[1];
  if ( v11 )
  {
    v12 = (DeclEntity *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v11->lpVtbl->Alloc)(this[1], 144);
  }
  else if ( g_pMalloc )
  {
    v12 = (DeclEntity *)((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMalloc->lpVtbl->Alloc)(g_pMalloc, 144);
  }
  else
  {
    v12 = (DeclEntity *)HeapAlloc(g_hHeap, 0, 0x90u);
  }
  if ( !v12 )
    goto LABEL_70;
  *((_QWORD *)v12 + 1) = v11;
  v13 = DeclEntity::DeclEntity(v12, this[1], (struct StringPtr *)&v26, v2, 0, 0);
  v32 = v13;
  DeclDoctype::InsertEntity((DeclDoctype *)(this + 157), v13);
  v14 = &CodeStringPtr::empty;
LABEL_52:
  *((_BYTE *)v13 + 130) = *((_DWORD *)this + 464) != 0;
  YReader::ParseDeclExternalId((YReader *)this, (struct StringPtr *)&v30, (struct StringPtr *)&v28, 0);
  (*(void (__fastcall **)(DeclEntity *, __int64 *))(*(_QWORD *)v13 + 32LL))(v13, &v30);
  if ( v29 )
  {
    lpVtbl = this[58][*((_DWORD *)this + 118) - 1].lpVtbl;
    v19 = (*((__int64 (__fastcall **)(struct IMallocVtbl *))lpVtbl->QueryInterface + 5))(lpVtbl);
    v20 = *(_QWORD *)v13;
    v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v19 + 40LL))(v19);
    (*(void (__fastcall **)(DeclEntity *, __int64 *, __int64))(v20 + 72))(v13, &v28, v21);
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v22 = *((_DWORD *)this + 28);
      if ( v22 != 44 )
        break;
      if ( v2 )
      {
        MXRRaiseException(-1072894412);
        JUMPOUT(0x1004069CDLL);
      }
      if ( (unsigned int)YReader::GetTokenDeclInner((YReader *)this) != 12 )
        goto LABEL_67;
      YReader::GetTokenData((YReader *)this, (DeclEntity *)((char *)v13 + 112));
      YReader::GetTokenDeclInner((YReader *)this);
    }
    if ( v22 == 48 )
      break;
    if ( v22 != 54 )
    {
      MXRRaiseException(-1072894419);
      __debugbreak();
    }
    YReader::ParseDeclEntityValue((YReader *)this, v13);
    YReader::GetTokenDeclInner((YReader *)this);
  }
  *((_DWORD *)this + 444) = 12;
  if ( *((_DWORD *)v13 + 30) )
    v14 = (_OWORD *)(*(__int64 (__fastcall **)(DeclEntity *))(*(_QWORD *)v13 + 8LL))(v13);
  *((_OWORD *)this + 101) = *v14;
  *((_OWORD *)this + 104) = *(_OWORD *)(*(__int64 (__fastcall **)(DeclEntity *))(*(_QWORD *)v13 + 24LL))(v13);
  v23 = *(_QWORD *)v13;
  if ( *((_BYTE *)this + 1788) )
    v24 = (_OWORD *)(*(__int64 (__fastcall **)(DeclEntity *))(v23 + 56))(v13);
  else
    v24 = (_OWORD *)(*(__int64 (__fastcall **)(DeclEntity *))(v23 + 40))(v13);
  *((_OWORD *)this + 105) = *v24;
  *((_OWORD *)this + 106) = *((_OWORD *)v13 + 7);
}

```

## disassembly

```asm
0x1004064a0  mov     rax, rsp
0x1004064a3  mov     [rax+10h], rbx
0x1004064a7  mov     [rax+18h], rsi
0x1004064ab  push    rdi
0x1004064ac  push    r12
0x1004064ae  push    r13
0x1004064b0  push    r14
0x1004064b2  push    r15
0x1004064b4  sub     rsp, 80h
0x1004064bb  mov     rdi, rcx
0x1004064be  xor     r12d, r12d
0x1004064c1  mov     [rax-50h], r12d
0x1004064c5  mov     [rax-38h], r12
0x1004064c9  mov     [rax-30h], r12d
0x1004064cd  mov     [rax-48h], r12
0x1004064d1  mov     [rax-40h], r12d
0x1004064d5  xor     r14b, r14b
0x1004064d8  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004064dd  cmp     eax, 33h ; '3'
0x1004064e0  jnz     short loc_1004064ED
0x1004064e2  mov     r14b, 1
0x1004064e5  mov     rcx, rdi; this
0x1004064e8  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004064ed  cmp     dword ptr [rdi+70h], 0Ch
0x1004064f1  jnz     loc_100406979
0x1004064f7  mov     rcx, [rdi+68h]
0x1004064fb  mov     rax, [rcx]
0x1004064fe  mov     rax, [rax+60h]
0x100406502  call    cs:__guard_dispatch_icall_fptr
0x100406508  mov     esi, eax
0x10040650a  mov     rbx, [rdi+1B8h]
0x100406511  mov     rdx, [rbx+10h]
0x100406515  mov     ecx, [rbx+18h]
0x100406518  sub     ecx, edx
0x10040651a  cmp     ecx, eax
0x10040651c  jnb     short loc_10040656E
0x10040651e  mov     rcx, [rbx+8]
0x100406522  test    rcx, rcx
0x100406525  jz      short loc_100406548
0x100406527  nop     word ptr [rax+rax+00000000h]
0x100406530  mov     rbx, rcx
0x100406533  mov     eax, [rcx+18h]
0x100406536  sub     eax, ecx
0x100406538  sub     eax, 20h ; ' '
0x10040653b  cmp     eax, esi
0x10040653d  jnb     short loc_10040659E
0x10040653f  mov     rcx, [rcx+8]
0x100406543  test    rcx, rcx
0x100406546  jnz     short loc_100406530
0x100406548  lfence
0x10040654b  mov     r8, rbx; struct BlockAlloc::Header *
0x10040654e  mov     edx, esi; unsigned int
0x100406550  lea     rcx, [rdi+1A0h]; this
0x100406557  call    ?EnqueueBlock@BlockAlloc@@AEAAPEAUHeader@1@KPEAU21@@Z; BlockAlloc::EnqueueBlock(ulong,BlockAlloc::Header *)
0x10040655c  mov     [rbx+8], rax
0x100406560  mov     rbx, rax
0x100406563  mov     [rdi+1B8h], rbx
0x10040656a  mov     rdx, [rbx+10h]
0x10040656e  add     [rbx+10h], rsi
0x100406572  mov     [rsp+0A8h+var_58], rdx
0x100406577  mov     rcx, [rdi+68h]
0x10040657b  mov     rax, [rcx]
0x10040657e  lea     rdx, [rsp+0A8h+var_58]
0x100406583  mov     rax, [rax+68h]
0x100406587  call    cs:__guard_dispatch_icall_fptr
0x10040658d  test    r14b, r14b
0x100406590  jz      short loc_1004065A8
0x100406592  lea     rcx, [rdi+560h]
0x100406599  jmp     loc_100406685
0x10040659e  lea     rax, [rcx+20h]
0x1004065a2  mov     [rcx+10h], rax
0x1004065a6  jmp     short loc_100406563
0x1004065a8  mov     eax, [rsp+0A8h+var_50]
0x1004065ac  cmp     eax, 4
0x1004065af  jnz     short loc_100406606
0x1004065b1  mov     rdx, [rsp+0A8h+var_58]
0x1004065b6  movzx   r8d, word ptr [rdx]
0x1004065ba  cmp     r8w, 71h ; 'q'
0x1004065bf  jnz     short loc_1004065DC
0x1004065c1  mov     rcx, cs:?quot@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::quot
0x1004065c8  mov     rax, [rdx]
0x1004065cb  cmp     rax, [rcx]
0x1004065ce  jnz     short loc_1004065DC
0x1004065d0  lea     rax, ?s_EntityQuot@@3VDeclEntity@@A; DeclEntity s_EntityQuot
0x1004065d7  jmp     loc_10040668F
0x1004065dc  cmp     r8w, 61h ; 'a'
0x1004065e1  jnz     loc_10040667E
0x1004065e7  mov     rcx, cs:?apos@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::apos
0x1004065ee  mov     rax, [rdx]
0x1004065f1  cmp     rax, [rcx]
0x1004065f4  jnz     loc_10040667E
0x1004065fa  lea     rax, ?s_EntityApos@@3VDeclEntity@@A; DeclEntity s_EntityApos
0x100406601  jmp     loc_10040668F
0x100406606  cmp     eax, 2
0x100406609  jnz     short loc_10040664E
0x10040660b  mov     rdx, [rsp+0A8h+var_58]
0x100406610  movzx   r8d, word ptr [rdx]
0x100406614  cmp     r8w, 67h ; 'g'
0x100406619  jnz     short loc_100406631
0x10040661b  mov     rcx, cs:?gt@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::gt
0x100406622  mov     eax, [rdx]
0x100406624  cmp     eax, [rcx]
0x100406626  jnz     short loc_100406631
0x100406628  lea     rax, ?s_EntityGt@@3VDeclEntity@@A; DeclEntity s_EntityGt
0x10040662f  jmp     short loc_10040668F
0x100406631  cmp     r8w, 6Ch ; 'l'
0x100406636  jnz     short loc_10040667E
0x100406638  mov     rcx, cs:?lt@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::lt
0x10040663f  mov     eax, [rdx]
0x100406641  cmp     eax, [rcx]
0x100406643  jnz     short loc_10040667E
0x100406645  lea     rax, ?s_EntityLt@@3VDeclEntity@@A; DeclEntity s_EntityLt
0x10040664c  jmp     short loc_10040668F
0x10040664e  cmp     eax, 3
0x100406651  jnz     short loc_10040667E
0x100406653  mov     rcx, [rsp+0A8h+var_58]
0x100406658  cmp     word ptr [rcx], 61h ; 'a'
0x10040665c  jnz     short loc_10040667E
0x10040665e  mov     rdx, cs:?amp@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::amp
0x100406665  mov     eax, [rcx]
0x100406667  cmp     eax, [rdx]
0x100406669  jnz     short loc_10040667E
0x10040666b  movzx   eax, word ptr [rcx+4]
0x10040666f  cmp     ax, [rdx+4]
0x100406673  jnz     short loc_10040667E
0x100406675  lea     rax, ?s_EntityAmp@@3VDeclEntity@@A; DeclEntity s_EntityAmp
0x10040667c  jmp     short loc_10040668F
0x10040667e  lea     rcx, [rdi+538h]
0x100406685  lea     rdx, [rsp+0A8h+var_58]
0x10040668a  call    ?lookup@?$_htable@VDeclEntity@@@@QEAAPEAVDeclEntity@@PEAUStringPtr@@@Z; _htable<DeclEntity>::lookup(StringPtr *)
0x10040668f  test    rax, rax
0x100406692  jnz     loc_10040674C
0x100406698  cmp     [rdi+703h], r12b
0x10040669f  jnz     loc_10040674C
0x1004066a5  mov     rbx, [rdi+8]
0x1004066a9  test    rbx, rbx
0x1004066ac  jz      short loc_1004066C5
0x1004066ae  mov     rax, [rbx]
0x1004066b1  mov     edx, 90h
0x1004066b6  mov     rcx, rbx
0x1004066b9  mov     rax, [rax+18h]
0x1004066bd  call    cs:__guard_dispatch_icall_fptr
0x1004066c3  jmp     short loc_1004066FA
0x1004066c5  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1004066cc  test    rcx, rcx
0x1004066cf  jz      short loc_1004066E5
0x1004066d1  mov     rax, [rcx]
0x1004066d4  mov     edx, 90h
0x1004066d9  mov     rax, [rax+18h]
0x1004066dd  call    cs:__guard_dispatch_icall_fptr
0x1004066e3  jmp     short loc_1004066FA
0x1004066e5  xor     edx, edx; dwFlags
0x1004066e7  mov     r8d, 90h; dwBytes
0x1004066ed  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x1004066f4  call    cs:__imp_HeapAlloc
0x1004066fa  test    rax, rax
0x1004066fd  jz      loc_1004069AC
0x100406703  mov     [rax+8], rbx
0x100406707  mov     [rsp+0A8h+var_80], r12b; bool
0x10040670c  mov     [rsp+0A8h+var_88], r12; struct StringPtr *
0x100406711  movzx   r9d, r14b; bool
0x100406715  lea     r8, [rsp+0A8h+var_58]; struct StringPtr *
0x10040671a  mov     rdx, [rdi+8]; struct IMalloc *
0x10040671e  mov     rcx, rax; this
0x100406721  call    ??0DeclEntity@@QEAA@PEAUIMalloc@@PEAUStringPtr@@_N12@Z; DeclEntity::DeclEntity(IMalloc *,StringPtr *,bool,StringPtr *,bool)
0x100406726  mov     rsi, rax
0x100406729  mov     [rsp+0A8h+arg_0], rax
0x100406731  mov     rdx, rax; struct DeclEntity *
0x100406734  lea     rcx, [rdi+4E8h]; this
0x10040673b  call    ?InsertEntity@DeclDoctype@@QEAAXPEAVDeclEntity@@@Z; DeclDoctype::InsertEntity(DeclEntity *)
0x100406740  lea     r15, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x100406747  jmp     loc_1004067F9
0x10040674c  mov     rbx, [rdi+8]
0x100406750  test    rbx, rbx
0x100406753  jz      short loc_10040676C
0x100406755  mov     rax, [rbx]
0x100406758  mov     edx, 90h
0x10040675d  mov     rcx, rbx
0x100406760  mov     rax, [rax+18h]
0x100406764  call    cs:__guard_dispatch_icall_fptr
0x10040676a  jmp     short loc_1004067A1
0x10040676c  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100406773  test    rcx, rcx
0x100406776  jz      short loc_10040678C
0x100406778  mov     rax, [rcx]
0x10040677b  mov     edx, 90h
0x100406780  mov     rax, [rax+18h]
0x100406784  call    cs:__guard_dispatch_icall_fptr
0x10040678a  jmp     short loc_1004067A1
0x10040678c  xor     edx, edx; dwFlags
0x10040678e  mov     r8d, 90h; dwBytes
0x100406794  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10040679b  call    cs:__imp_HeapAlloc
0x1004067a1  test    rax, rax
0x1004067a4  jz      loc_1004069AC
0x1004067aa  mov     [rax+8], rbx
0x1004067ae  mov     [rsp+0A8h+var_80], r12b; bool
0x1004067b3  mov     [rsp+0A8h+var_88], r12; struct StringPtr *
0x1004067b8  movzx   r9d, r14b; bool
0x1004067bc  lea     r15, ?empty@CodeStringPtr@@2UStringPtr@@A; StringPtr CodeStringPtr::empty
0x1004067c3  mov     r8, r15; struct StringPtr *
0x1004067c6  mov     rdx, [rdi+8]; struct IMalloc *
0x1004067ca  mov     rcx, rax; this
0x1004067cd  call    ??0DeclEntity@@QEAA@PEAUIMalloc@@PEAUStringPtr@@_N12@Z; DeclEntity::DeclEntity(IMalloc *,StringPtr *,bool,StringPtr *,bool)
0x1004067d2  mov     rsi, rax
0x1004067d5  mov     rcx, [rdi+5D8h]
0x1004067dc  test    rcx, rcx
0x1004067df  jz      short loc_1004067F2
0x1004067e1  mov     rax, [rcx]
0x1004067e4  mov     edx, 1
0x1004067e9  mov     rax, [rax]
0x1004067ec  call    cs:__guard_dispatch_icall_fptr
0x1004067f2  mov     [rdi+5D8h], rsi
0x1004067f9  cmp     dword ptr [rdi+740h], 0
0x100406800  setnz   al
0x100406803  mov     [rsi+82h], al
0x100406809  xor     r9d, r9d; bool
0x10040680c  lea     r8, [rsp+0A8h+var_48]; struct StringPtr *
0x100406811  lea     rdx, [rsp+0A8h+var_38]; struct StringPtr *
0x100406816  mov     rcx, rdi; this
0x100406819  call    ?ParseDeclExternalId@YReader@@AEAAXPEAUStringPtr@@0_N@Z; YReader::ParseDeclExternalId(StringPtr *,StringPtr *,bool)
0x10040681e  mov     rax, [rsi]
0x100406821  lea     rdx, [rsp+0A8h+var_38]
0x100406826  mov     rcx, rsi
0x100406829  mov     rax, [rax+20h]
0x10040682d  call    cs:__guard_dispatch_icall_fptr
0x100406833  cmp     [rsp+0A8h+var_40], 0
0x100406838  jz      short loc_100406885
0x10040683a  mov     ecx, [rdi+1D8h]
0x100406840  dec     ecx
0x100406842  mov     rax, [rdi+1D0h]
0x100406849  mov     rcx, [rax+rcx*8]
0x10040684d  mov     rax, [rcx]
0x100406850  mov     rax, [rax+28h]
0x100406854  call    cs:__guard_dispatch_icall_fptr
0x10040685a  mov     rdx, rax
0x10040685d  mov     rbx, [rsi]
0x100406860  mov     rcx, [rax]
0x100406863  mov     rax, [rcx+28h]
0x100406867  mov     rcx, rdx
0x10040686a  call    cs:__guard_dispatch_icall_fptr
0x100406870  mov     r8, rax
0x100406873  lea     rdx, [rsp+0A8h+var_48]
0x100406878  mov     rcx, rsi
0x10040687b  mov     rax, [rbx+48h]
0x10040687f  call    cs:__guard_dispatch_icall_fptr
0x100406885  mov     eax, [rdi+70h]
0x100406888  cmp     eax, 2Ch ; ','
0x10040688b  jz      short loc_1004068B0
0x10040688d  cmp     eax, 30h ; '0'
0x100406890  jz      short loc_1004068E0
0x100406892  cmp     eax, 36h ; '6'
0x100406895  jnz     loc_1004069B7
0x10040689b  mov     rdx, rsi; struct DeclEntity *
0x10040689e  mov     rcx, rdi; this
0x1004068a1  call    ?ParseDeclEntityValue@YReader@@AEAAXPEAVDeclEntity@@@Z; YReader::ParseDeclEntityValue(DeclEntity *)
0x1004068a6  mov     rcx, rdi; this
0x1004068a9  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004068ae  jmp     short loc_100406885
0x1004068b0  test    r14b, r14b
0x1004068b3  jnz     loc_1004069C2
0x1004068b9  mov     rcx, rdi; this
0x1004068bc  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004068c1  cmp     eax, 0Ch
0x1004068c4  jnz     loc_100406979
0x1004068ca  lea     rdx, [rsi+70h]; struct StringPtr *
0x1004068ce  mov     rcx, rdi; this
0x1004068d1  call    ?GetTokenData@YReader@@AEAAXPEAUStringPtr@@@Z; YReader::GetTokenData(StringPtr *)
0x1004068d6  mov     rcx, rdi; this
0x1004068d9  call    ?GetTokenDeclInner@YReader@@AEAAHXZ; YReader::GetTokenDeclInner(void)
0x1004068de  jmp     short loc_100406885
0x1004068e0  mov     dword ptr [rdi+6F0h], 0Ch
0x1004068ea  cmp     dword ptr [rsi+78h], 0
0x1004068ee  jz      short loc_100406903
0x1004068f0  mov     rax, [rsi]
0x1004068f3  mov     rcx, rsi
0x1004068f6  mov     rax, [rax+8]
0x1004068fa  call    cs:__guard_dispatch_icall_fptr
0x100406900  mov     r15, rax
0x100406903  movups  xmm0, xmmword ptr [r15]
0x100406907  movups  xmmword ptr [rdi+650h], xmm0
0x10040690e  mov     rax, [rsi]
0x100406911  mov     rcx, rsi
0x100406914  mov     rax, [rax+18h]
0x100406918  call    cs:__guard_dispatch_icall_fptr
0x10040691e  movups  xmm0, xmmword ptr [rax]
0x100406921  movups  xmmword ptr [rdi+680h], xmm0
0x100406928  mov     rax, [rsi]
0x10040692b  mov     rcx, rsi
0x10040692e  cmp     byte ptr [rdi+6FCh], 0
0x100406935  jz      short loc_10040693D
0x100406937  mov     rax, [rax+38h]
0x10040693b  jmp     short loc_100406941
0x10040693d  mov     rax, [rax+28h]
0x100406941  call    cs:__guard_dispatch_icall_fptr
0x100406947  movups  xmm0, xmmword ptr [rax]
0x10040694a  movups  xmmword ptr [rdi+690h], xmm0
0x100406951  movups  xmm0, xmmword ptr [rsi+70h]
0x100406955  movups  xmmword ptr [rdi+6A0h], xmm0
0x10040695c  lea     r11, [rsp+0A8h+var_28]
  ... truncated ...
```
