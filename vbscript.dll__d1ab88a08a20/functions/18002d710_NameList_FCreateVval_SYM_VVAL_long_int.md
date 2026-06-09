# NameList::FCreateVval(SYM *,VVAL * *,long *,int)

- ea: `0x18002d710`
- end: `0x18002d9f9`
- name: `?FCreateVval@NameList@@QEAAHPEAUSYM@@PEAPEAUVVAL@@PEAJH@Z`
- size: `745`
- prototype: `int(NameList *__hidden this, struct SYM *, struct VVAL **, int *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18002d6b0`
- `0x180053ad8`

## callees

- `0x18001ed10`
- `0x18002d710`
- `0x18002da00`
- `0x18002db90`
- `0x1800414d8`
- `0x18007941e`
- `0x180079436`

## import_xrefs

- `msvcrt!malloc` at `0x18002d882`
- `msvcrt!malloc` at `0x18002d8f6`
- `msvcrt!malloc` at `0x18002d983`
- `msvcrt!malloc` at `0x18002d882`
- `msvcrt!malloc` at `0x18002d8f6`
- `msvcrt!malloc` at `0x18002d983`

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
0x18002d710  mov     [rsp+arg_10], r8
0x18002d715  push    rbx
0x18002d716  push    rbp
0x18002d717  push    rsi
0x18002d718  push    rdi
0x18002d719  push    r12
0x18002d71b  push    r13
0x18002d71d  push    r14
0x18002d71f  push    r15
0x18002d721  sub     rsp, 28h
0x18002d725  cmp     qword ptr [rcx+28h], 0
0x18002d72a  mov     r15, r9
0x18002d72d  mov     r14, rdx
0x18002d730  mov     rdi, rcx
0x18002d733  jz      loc_18002D872
0x18002d739  mov     eax, [rcx+38h]
0x18002d73c  cmp     [rcx+34h], eax
0x18002d73f  jge     loc_18002D9C4
0x18002d745  mov     esi, [r14+0Ch]
0x18002d749  mov     ecx, [rdi+30h]
0x18002d74c  mov     rax, [rdi+28h]
0x18002d750  and     rcx, rsi
0x18002d753  lea     r13, [rax+rcx*8]
0x18002d757  mov     r11, r13
0x18002d75a  mov     rbx, [r11]
0x18002d75d  test    rbx, rbx
0x18002d760  jnz     loc_18002D860
0x18002d766  mov     eax, [r14+8]
0x18002d76a  lea     ebx, ds:42h[rax*2]
0x18002d771  test    ebx, ebx
0x18002d773  jle     loc_18002D897
0x18002d779  mov     r12d, [rdi+0Ch]
0x18002d77d  xor     ebp, ebp
0x18002d77f  mov     esi, [rdi+8]
0x18002d782  mov     eax, r12d
0x18002d785  sub     eax, esi
0x18002d787  cmp     ebx, eax
0x18002d789  jg      loc_18002D8B6
0x18002d78f  lea     eax, [rbx+7]
0x18002d792  and     eax, 0FFFFFFF8h
0x18002d795  add     eax, esi
0x18002d797  mov     [rdi+8], eax
0x18002d79a  movsxd  rax, esi
0x18002d79d  add     rax, [rdi]
0x18002d7a0  lea     rbx, [rax+8]
0x18002d7a4  test    rbx, rbx
0x18002d7a7  jz      loc_18002D897
0x18002d7ad  lea     rcx, [rdi+40h]; this
0x18002d7b1  call    ?EnsureSlotsAvailable@CDISPIDTable@@AEAAHXZ; CDISPIDTable::EnsureSlotsAvailable(void)
0x18002d7b6  test    eax, eax
0x18002d7b8  jz      loc_18002D9F1
0x18002d7be  mov     ecx, [rdi+40h]
0x18002d7c1  mov     rax, [rdi+48h]
0x18002d7c5  mov     [rax+rcx*8], rbx
0x18002d7c9  add     dword ptr [rdi+40h], 1
0x18002d7cd  mov     eax, [rdi+40h]
0x18002d7d0  mov     [rbx+38h], eax
0x18002d7d3  jz      loc_18002D897
0x18002d7d9  mov     [rbx], bp
0x18002d7dc  lea     rcx, [rbx+40h]; void *
0x18002d7e0  mov     [rbx+18h], ebp
0x18002d7e3  mov     eax, [r14+0Ch]
0x18002d7e7  mov     [rbx+20h], eax
0x18002d7ea  mov     eax, [r14+8]
0x18002d7ee  add     eax, eax
0x18002d7f0  mov     [rbx+24h], eax
0x18002d7f3  mov     eax, [r14+8]
0x18002d7f7  mov     rdx, [r14]; Src
0x18002d7fa  add     eax, eax
0x18002d7fc  movsxd  r8, eax
0x18002d7ff  add     r8, 2; Size
0x18002d803  call    memcpy_0
0x18002d808  mov     rax, [r13+0]
0x18002d80c  lea     rcx, [rbx+28h]
0x18002d810  mov     [rbx+30h], rax
0x18002d814  mov     [r13+0], rbx
0x18002d818  inc     dword ptr [rdi+34h]
0x18002d81b  cmp     [rdi+18h], rbp
0x18002d81f  jz      loc_18002D8AD
0x18002d825  mov     rax, [rdi+20h]
0x18002d829  mov     [rax], rbx
0x18002d82c  mov     [rdi+20h], rcx
0x18002d830  mov     [rcx], rbp
0x18002d833  mov     rax, [rsp+68h+arg_10]
0x18002d83b  mov     [rax], rbx
0x18002d83e  test    r15, r15
0x18002d841  jz      short loc_18002D849
0x18002d843  mov     eax, [rbx+38h]
0x18002d846  mov     [r15], eax
0x18002d849  mov     eax, 1
0x18002d84e  add     rsp, 28h
0x18002d852  pop     r15
0x18002d854  pop     r14
0x18002d856  pop     r13
0x18002d858  pop     r12
0x18002d85a  pop     rdi
0x18002d85b  pop     rsi
0x18002d85c  pop     rbp
0x18002d85d  pop     rbx
0x18002d85e  retn
0x18002d860  cmp     [rbx+20h], esi
0x18002d863  jz      loc_18002D921
0x18002d869  lea     r11, [rbx+30h]
0x18002d86d  jmp     loc_18002D75A
0x18002d872  mov     eax, [rcx+30h]
0x18002d875  lea     eax, ds:8[rax*8]
0x18002d87c  movsxd  rbx, eax
0x18002d87f  mov     rcx, rbx; Size
0x18002d882  call    cs:__imp_malloc
0x18002d889  nop     dword ptr [rax+rax+00h]
0x18002d88e  mov     [rdi+28h], rax
0x18002d892  test    rax, rax
0x18002d895  jnz     short loc_18002D89B
0x18002d897  xor     eax, eax
0x18002d899  jmp     short loc_18002D84E
0x18002d89b  mov     r8, rbx; Size
0x18002d89e  xor     edx, edx; Val
0x18002d8a0  mov     rcx, rax; void *
0x18002d8a3  call    memset_0
0x18002d8a8  jmp     loc_18002D745
0x18002d8ad  mov     [rdi+18h], rbx
0x18002d8b1  jmp     loc_18002D82C
0x18002d8b6  mov     eax, [rdi+14h]
0x18002d8b9  mov     [rsp+68h+arg_20], eax
0x18002d8c0  cmp     ebx, eax
0x18002d8c2  jge     loc_18002D971
0x18002d8c8  mov     ecx, [rdi+10h]
0x18002d8cb  cmp     r12d, ebx
0x18002d8ce  cmovle  r12d, ebx
0x18002d8d2  add     r12d, r12d
0x18002d8d5  cmp     ecx, r12d
0x18002d8d8  cmovle  ecx, r12d
0x18002d8dc  cmp     ecx, eax
0x18002d8de  jle     loc_18002D9AE
0x18002d8e4  lea     ecx, [rax+8]
0x18002d8e7  cmp     ecx, eax
0x18002d8e9  jl      short loc_18002D897
0x18002d8eb  cmp     ecx, ebx
0x18002d8ed  jl      short loc_18002D897
0x18002d8ef  movsxd  rcx, eax
0x18002d8f2  add     rcx, 8; Size
0x18002d8f6  call    cs:__imp_malloc
0x18002d8fd  nop     dword ptr [rax+rax+00h]
0x18002d902  test    rax, rax
0x18002d905  jz      short loc_18002D897
0x18002d907  mov     rcx, [rdi]
0x18002d90a  mov     esi, ebp
0x18002d90c  mov     [rax], rcx
0x18002d90f  mov     [rdi], rax
0x18002d912  mov     eax, [rsp+68h+arg_20]
0x18002d919  mov     [rdi+0Ch], eax
0x18002d91c  jmp     loc_18002D78F
0x18002d921  mov     rdx, r14; struct SYM *
0x18002d924  mov     rcx, rbx; this
0x18002d927  call    ?FEqualRgch@NME@NameList@@QEAAHPEAUSYM@@@Z; NameList::NME::FEqualRgch(SYM *)
0x18002d92c  test    eax, eax
0x18002d92e  jz      loc_18002D869
0x18002d934  cmp     r11, r13
0x18002d937  jnz     loc_18002D9CE
0x18002d93d  mov     eax, 50h ; 'P'
0x18002d942  cmp     ax, [rbx]
0x18002d945  jz      loc_18002D833
0x18002d94b  mov     rcx, rbx; this
0x18002d94e  call    ?Clear@VAR@@QEAAJXZ; VAR::Clear(void)
0x18002d953  movsxd  r8, dword ptr [rbx+24h]
0x18002d957  lea     rcx, [rbx+40h]; void *
0x18002d95b  xor     ebp, ebp
0x18002d95d  add     r8, 2; Size
0x18002d961  mov     [rbx+18h], ebp
0x18002d964  mov     rdx, [r14]; Src
0x18002d967  call    memcpy_0
0x18002d96c  jmp     loc_18002D833
0x18002d971  lea     eax, [rbx+8]
0x18002d974  cmp     eax, ebx
0x18002d976  jl      loc_18002D897
0x18002d97c  movsxd  rcx, ebx
0x18002d97f  add     rcx, 8; Size
0x18002d983  call    cs:__imp_malloc
0x18002d98a  nop     dword ptr [rax+rax+00h]
0x18002d98f  test    rax, rax
0x18002d992  jz      loc_18002D897
0x18002d998  mov     rdx, [rdi]
0x18002d99b  cmp     esi, r12d
0x18002d99e  jge     short loc_18002D9E6
0x18002d9a0  mov     rcx, [rdx]; this
0x18002d9a3  mov     [rax], rcx
0x18002d9a6  mov     [rdx], rax
0x18002d9a9  jmp     loc_18002D7A0
0x18002d9ae  cmp     ebx, ecx
0x18002d9b0  jg      loc_18002D897
0x18002d9b6  mov     eax, ecx
0x18002d9b8  mov     [rsp+68h+arg_20], ecx
0x18002d9bf  jmp     loc_18002D8E4
0x18002d9c4  call    ?Rehash@NameList@@AEAAXXZ; NameList::Rehash(void)
0x18002d9c9  jmp     loc_18002D745
0x18002d9ce  mov     rax, [rbx+30h]
0x18002d9d2  mov     [r11], rax
0x18002d9d5  mov     rax, [r13+0]
0x18002d9d9  mov     [rbx+30h], rax
0x18002d9dd  mov     [r13+0], rbx
0x18002d9e1  jmp     loc_18002D93D
0x18002d9e6  mov     [rax], rdx
0x18002d9e9  mov     [rdi], rax
0x18002d9ec  jmp     loc_18002D7A0
0x18002d9f1  mov     [rbx+38h], ebp
0x18002d9f4  jmp     loc_18002D897
```
