# NameList::FCreateVval(SYM *,VVAL * *,long *,int)

- ea: `0x180028230`
- end: `0x180028503`
- name: `?FCreateVval@NameList@@QEAAHPEAUSYM@@PEAPEAUVVAL@@PEAJH@Z`
- size: `723`
- prototype: `int(NameList *__hidden this, struct SYM *, struct VVAL **, int *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x1800281d0`
- `0x1800522c0`

## callees

- `0x180022b20`
- `0x180028230`
- `0x18002850c`
- `0x180028690`
- `0x18003fd80`
- `0x18007672e`
- `0x180076746`

## import_xrefs

- `msvcrt!malloc` at `0x1800283a1`
- `msvcrt!malloc` at `0x18002840c`
- `msvcrt!malloc` at `0x180028493`
- `msvcrt!malloc` at `0x1800283a1`
- `msvcrt!malloc` at `0x18002840c`
- `msvcrt!malloc` at `0x180028493`

## pseudocode

```c
__int64 __fastcall NameList::FCreateVval(NameList *this, struct SYM *a2, struct VVAL **a3, int *a4)
{
  unsigned int v7; // esi
  NameList::NME **v8; // r13
  NameList::NME **i; // r11
  NameList::NME *v10; // rbx
  int v11; // ebx
  int v12; // r12d
  int v13; // esi
  _QWORD *v14; // rax
  bool v15; // zf
  _QWORD *v16; // rcx
  size_t v18; // rbx
  void *v19; // rax
  int v20; // eax
  int v21; // ecx
  int v22; // r12d
  _QWORD *v23; // rax
  NameList::NME **v24; // r11
  size_t v25; // r8
  _QWORD *v26; // rdx
  int v29; // [rsp+90h] [rbp+28h]

  if ( *((_QWORD *)this + 5) )
  {
    if ( *((_DWORD *)this + 13) >= *((_DWORD *)this + 14) )
      NameList::Rehash(this);
  }
  else
  {
    v18 = 8 * *((_DWORD *)this + 12) + 8;
    v19 = malloc(v18);
    *((_QWORD *)this + 5) = v19;
    if ( !v19 )
      return 0;
    memset_0(v19, 0, v18);
  }
  v7 = *((_DWORD *)a2 + 3);
  v8 = (NameList::NME **)(*((_QWORD *)this + 5) + 8LL * (v7 & *((_DWORD *)this + 12)));
  for ( i = v8; ; i = (NameList::NME **)((char *)v10 + 48) )
  {
    v10 = *i;
    if ( !*i )
      break;
    if ( *((_DWORD *)v10 + 8) == v7 && (unsigned int)NameList::NME::FEqualRgch(*i, a2) )
    {
      if ( v24 != v8 )
      {
        *v24 = (NameList::NME *)*((_QWORD *)v10 + 6);
        *((_QWORD *)v10 + 6) = *v8;
        *v8 = v10;
      }
      if ( *(_WORD *)v10 != 80 )
      {
        VAR::Clear(v10);
        v25 = *((int *)v10 + 9) + 2LL;
        *((_DWORD *)v10 + 6) = 0;
        memcpy_0((char *)v10 + 64, *(const void **)a2, v25);
      }
LABEL_15:
      *a3 = v10;
      if ( a4 )
        *a4 = *((_DWORD *)v10 + 14);
      return 1;
    }
  }
  v11 = 2 * *((_DWORD *)a2 + 2) + 66;
  if ( v11 <= 0 )
    return 0;
  v12 = *((_DWORD *)this + 3);
  v13 = *((_DWORD *)this + 2);
  if ( v11 <= v12 - v13 )
    goto LABEL_8;
  v20 = *((_DWORD *)this + 5);
  v29 = v20;
  if ( v11 >= v20 )
  {
    if ( 2 * *((_DWORD *)a2 + 2) + 74 <= 2 * *((_DWORD *)a2 + 2) + 66 )
      return 0;
    v14 = malloc(v11 + 8LL);
    if ( !v14 )
      return 0;
    v26 = *(_QWORD **)this;
    if ( v13 >= v12 )
    {
      *v14 = v26;
      *(_QWORD *)this = v14;
    }
    else
    {
      *v14 = *v26;
      *v26 = v14;
    }
    goto LABEL_9;
  }
  v21 = *((_DWORD *)this + 4);
  if ( v12 <= v11 )
    v12 = 2 * *((_DWORD *)a2 + 2) + 66;
  v22 = 2 * v12;
  if ( v21 <= v22 )
    v21 = v22;
  if ( v21 <= v20 )
  {
    if ( v11 > v21 )
      return 0;
    v20 = v21;
    v29 = v21;
  }
  if ( v20 + 8 > v20 && v20 + 8 >= v11 )
  {
    v23 = malloc(v20 + 8LL);
    if ( v23 )
    {
      v13 = 0;
      *v23 = *(_QWORD *)this;
      *(_QWORD *)this = v23;
      *((_DWORD *)this + 3) = v29;
LABEL_8:
      *((_DWORD *)this + 2) = v13 + ((v11 + 7) & 0xFFFFFFF8);
      v14 = (_QWORD *)(*(_QWORD *)this + v13);
LABEL_9:
      v10 = (NameList::NME *)(v14 + 1);
      if ( v14 == (_QWORD *)-8LL )
        return 0;
      if ( !(unsigned int)CDISPIDTable::EnsureSlotsAvailable((NameList *)((char *)this + 64)) )
      {
        *((_DWORD *)v10 + 14) = 0;
        return 0;
      }
      *(_QWORD *)(*((_QWORD *)this + 9) + 8LL * *((unsigned int *)this + 16)) = v10;
      v15 = (*((_DWORD *)this + 16))++ == -1;
      *((_DWORD *)v10 + 14) = *((_DWORD *)this + 16);
      if ( v15 )
        return 0;
      *(_WORD *)v10 = 0;
      *((_DWORD *)v10 + 6) = 0;
      *((_DWORD *)v10 + 8) = *((_DWORD *)a2 + 3);
      *((_DWORD *)v10 + 9) = 2 * *((_DWORD *)a2 + 2);
      memcpy_0((char *)v10 + 64, *(const void **)a2, 2 * *((_DWORD *)a2 + 2) + 2LL);
      v16 = (_QWORD *)((char *)v10 + 40);
      *((_QWORD *)v10 + 6) = *v8;
      *v8 = v10;
      ++*((_DWORD *)this + 13);
      if ( *((_QWORD *)this + 3) )
        **((_QWORD **)this + 4) = v10;
      else
        *((_QWORD *)this + 3) = v10;
      *((_QWORD *)this + 4) = v16;
      *v16 = 0;
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028230  mov     [rsp+arg_10], r8
0x180028235  push    rbx
0x180028236  push    rbp
0x180028237  push    rsi
0x180028238  push    rdi
0x180028239  push    r12
0x18002823b  push    r13
0x18002823d  push    r14
0x18002823f  push    r15
0x180028241  sub     rsp, 28h
0x180028245  cmp     qword ptr [rcx+28h], 0
0x18002824a  mov     r15, r9
0x18002824d  mov     r14, rdx
0x180028250  mov     rdi, rcx
0x180028253  jz      loc_180028391
0x180028259  mov     eax, [rcx+38h]
0x18002825c  cmp     [rcx+34h], eax
0x18002825f  jge     loc_1800284CE
0x180028265  mov     esi, [r14+0Ch]
0x180028269  mov     ecx, [rdi+30h]
0x18002826c  mov     rax, [rdi+28h]
0x180028270  and     rcx, rsi
0x180028273  lea     r13, [rax+rcx*8]
0x180028277  mov     r11, r13
0x18002827a  mov     rbx, [r11]
0x18002827d  test    rbx, rbx
0x180028280  jnz     loc_18002837F
0x180028286  mov     eax, [r14+8]
0x18002828a  lea     ebx, ds:42h[rax*2]
0x180028291  test    ebx, ebx
0x180028293  jle     loc_1800283B0
0x180028299  mov     r12d, [rdi+0Ch]
0x18002829d  xor     ebp, ebp
0x18002829f  mov     esi, [rdi+8]
0x1800282a2  mov     eax, r12d
0x1800282a5  sub     eax, esi
0x1800282a7  cmp     ebx, eax
0x1800282a9  jg      loc_1800283CC
0x1800282af  lea     eax, [rbx+7]
0x1800282b2  and     eax, 0FFFFFFF8h
0x1800282b5  add     eax, esi
0x1800282b7  mov     [rdi+8], eax
0x1800282ba  movsxd  rax, esi
0x1800282bd  add     rax, [rdi]
0x1800282c0  lea     rbx, [rax+8]
0x1800282c4  test    rbx, rbx
0x1800282c7  jz      loc_1800283B0
0x1800282cd  lea     rcx, [rdi+40h]; this
0x1800282d1  call    ?EnsureSlotsAvailable@CDISPIDTable@@AEAAHXZ; CDISPIDTable::EnsureSlotsAvailable(void)
0x1800282d6  test    eax, eax
0x1800282d8  jz      loc_1800284FB
0x1800282de  mov     ecx, [rdi+40h]
0x1800282e1  mov     rax, [rdi+48h]
0x1800282e5  mov     [rax+rcx*8], rbx
0x1800282e9  add     dword ptr [rdi+40h], 1
0x1800282ed  mov     eax, [rdi+40h]
0x1800282f0  mov     [rbx+38h], eax
0x1800282f3  jz      loc_1800283B0
0x1800282f9  mov     [rbx], bp
0x1800282fc  lea     rcx, [rbx+40h]; void *
0x180028300  mov     [rbx+18h], ebp
0x180028303  mov     eax, [r14+0Ch]
0x180028307  mov     [rbx+20h], eax
0x18002830a  mov     eax, [r14+8]
0x18002830e  add     eax, eax
0x180028310  mov     [rbx+24h], eax
0x180028313  mov     eax, [r14+8]
0x180028317  mov     rdx, [r14]; Src
0x18002831a  add     eax, eax
0x18002831c  movsxd  r8, eax
0x18002831f  add     r8, 2; Size
0x180028323  call    memcpy_0
0x180028328  mov     rax, [r13+0]
0x18002832c  lea     rcx, [rbx+28h]
0x180028330  mov     [rbx+30h], rax
0x180028334  mov     [r13+0], rbx
0x180028338  inc     dword ptr [rdi+34h]
0x18002833b  cmp     [rdi+18h], rbp
0x18002833f  jz      loc_1800283C6
0x180028345  mov     rax, [rdi+20h]
0x180028349  mov     [rax], rbx
0x18002834c  mov     [rdi+20h], rcx
0x180028350  mov     [rcx], rbp
0x180028353  mov     rax, [rsp+68h+arg_10]
0x18002835b  mov     [rax], rbx
0x18002835e  test    r15, r15
0x180028361  jz      short loc_180028369
0x180028363  mov     eax, [rbx+38h]
0x180028366  mov     [r15], eax
0x180028369  mov     eax, 1
0x18002836e  add     rsp, 28h
0x180028372  pop     r15
0x180028374  pop     r14
0x180028376  pop     r13
0x180028378  pop     r12
0x18002837a  pop     rdi
0x18002837b  pop     rsi
0x18002837c  pop     rbp
0x18002837d  pop     rbx
0x18002837e  retn
0x18002837f  cmp     [rbx+20h], esi
0x180028382  jz      loc_180028431
0x180028388  lea     r11, [rbx+30h]
0x18002838c  jmp     loc_18002827A
0x180028391  mov     eax, [rcx+30h]
0x180028394  lea     eax, ds:8[rax*8]
0x18002839b  movsxd  rbx, eax
0x18002839e  mov     rcx, rbx; Size
0x1800283a1  call    cs:__imp_malloc
0x1800283a7  mov     [rdi+28h], rax
0x1800283ab  test    rax, rax
0x1800283ae  jnz     short loc_1800283B4
0x1800283b0  xor     eax, eax
0x1800283b2  jmp     short loc_18002836E
0x1800283b4  mov     r8, rbx; Size
0x1800283b7  xor     edx, edx; Val
0x1800283b9  mov     rcx, rax; void *
0x1800283bc  call    memset_0
0x1800283c1  jmp     loc_180028265
0x1800283c6  mov     [rdi+18h], rbx
0x1800283ca  jmp     short loc_18002834C
0x1800283cc  mov     eax, [rdi+14h]
0x1800283cf  mov     [rsp+68h+arg_20], eax
0x1800283d6  cmp     ebx, eax
0x1800283d8  jge     loc_180028481
0x1800283de  mov     ecx, [rdi+10h]
0x1800283e1  cmp     r12d, ebx
0x1800283e4  cmovle  r12d, ebx
0x1800283e8  add     r12d, r12d
0x1800283eb  cmp     ecx, r12d
0x1800283ee  cmovle  ecx, r12d
0x1800283f2  cmp     ecx, eax
0x1800283f4  jle     loc_1800284B8
0x1800283fa  lea     ecx, [rax+8]
0x1800283fd  cmp     ecx, eax
0x1800283ff  jl      short loc_1800283B0
0x180028401  cmp     ecx, ebx
0x180028403  jl      short loc_1800283B0
0x180028405  movsxd  rcx, eax
0x180028408  add     rcx, 8; Size
0x18002840c  call    cs:__imp_malloc
0x180028412  test    rax, rax
0x180028415  jz      short loc_1800283B0
0x180028417  mov     rcx, [rdi]
0x18002841a  mov     esi, ebp
0x18002841c  mov     [rax], rcx
0x18002841f  mov     [rdi], rax
0x180028422  mov     eax, [rsp+68h+arg_20]
0x180028429  mov     [rdi+0Ch], eax
0x18002842c  jmp     loc_1800282AF
0x180028431  mov     rdx, r14; struct SYM *
0x180028434  mov     rcx, rbx; this
0x180028437  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x18002843c  test    eax, eax
0x18002843e  jz      loc_180028388
0x180028444  cmp     r11, r13
0x180028447  jnz     loc_1800284D8
0x18002844d  mov     eax, 50h ; 'P'
0x180028452  cmp     ax, [rbx]
0x180028455  jz      loc_180028353
0x18002845b  mov     rcx, rbx; this
0x18002845e  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x180028463  movsxd  r8, dword ptr [rbx+24h]
0x180028467  lea     rcx, [rbx+40h]; void *
0x18002846b  xor     ebp, ebp
0x18002846d  add     r8, 2; Size
0x180028471  mov     [rbx+18h], ebp
0x180028474  mov     rdx, [r14]; Src
0x180028477  call    memcpy_0
0x18002847c  jmp     loc_180028353
0x180028481  lea     eax, [rbx+8]
0x180028484  cmp     eax, ebx
0x180028486  jl      loc_1800283B0
0x18002848c  movsxd  rcx, ebx
0x18002848f  add     rcx, 8; Size
0x180028493  call    cs:__imp_malloc
0x180028499  test    rax, rax
0x18002849c  jz      loc_1800283B0
0x1800284a2  mov     rdx, [rdi]
0x1800284a5  cmp     esi, r12d
0x1800284a8  jge     short loc_1800284F0
0x1800284aa  mov     rcx, [rdx]; this
0x1800284ad  mov     [rax], rcx
0x1800284b0  mov     [rdx], rax
0x1800284b3  jmp     loc_1800282C0
0x1800284b8  cmp     ebx, ecx
0x1800284ba  jg      loc_1800283B0
0x1800284c0  mov     eax, ecx
0x1800284c2  mov     [rsp+68h+arg_20], ecx
0x1800284c9  jmp     loc_1800283FA
0x1800284ce  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x1800284d3  jmp     loc_180028265
0x1800284d8  mov     rax, [rbx+30h]
0x1800284dc  mov     [r11], rax
0x1800284df  mov     rax, [r13+0]
0x1800284e3  mov     [rbx+30h], rax
0x1800284e7  mov     [r13+0], rbx
0x1800284eb  jmp     loc_18002844D
0x1800284f0  mov     [rax], rdx
0x1800284f3  mov     [rdi], rax
0x1800284f6  jmp     loc_1800282C0
0x1800284fb  mov     [rbx+38h], ebp
0x1800284fe  jmp     loc_1800283B0
```
