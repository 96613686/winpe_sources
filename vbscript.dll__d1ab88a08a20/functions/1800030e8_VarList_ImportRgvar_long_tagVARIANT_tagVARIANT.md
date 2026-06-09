# VarList::ImportRgvar(long,tagVARIANT *,tagVARIANT *)

- ea: `0x1800030e8`
- end: `0x1800033a1`
- name: `?ImportRgvar@VarList@@QEAAJJPEAUtagVARIANT@@0@Z`
- size: `697`
- prototype: `int(VarList *__hidden this, int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001cb70`

## callees

- `0x1800030e8`
- `0x180003c40`

## import_xrefs

- `msvcrt!malloc` at `0x180003354`
- `msvcrt!malloc` at `0x180003354`
- `msvcrt!free` at `0x18000332f`
- `msvcrt!free` at `0x18000332f`
- `OLEAUT32!__imp_VariantCopy` at `0x180003235`
- `OLEAUT32!__imp_VariantCopy` at `0x180003283`
- `OLEAUT32!__imp_VariantCopy` at `0x180003235`
- `OLEAUT32!__imp_VariantCopy` at `0x180003283`
- `KERNEL32!TlsGetValue` at `0x180003192`
- `KERNEL32!TlsGetValue` at `0x180003192`

## pseudocode

```c
HRESULT __fastcall VarList::ImportRgvar(VarList *this, int a2, struct tagVARIANT *a3, struct tagVARIANT *a4)
{
  __int64 v4; // r14
  unsigned int v7; // ebp
  __int64 v8; // r8
  _OWORD *v9; // rdx
  __int64 v10; // r9
  VARIANTARG **v11; // rdi
  __int64 v12; // rbx
  _QWORD *Value; // rax
  signed int v14; // ebp
  _OWORD *v15; // r9
  __int64 v16; // r8
  VARIANTARG *v17; // r8
  HRESULT result; // eax
  struct tagVARIANT *v19; // rax
  const VARIANTARG *v20; // rbx
  _DWORD *v21; // rcx
  __int64 v22; // rdx
  int v23; // ebp
  _DWORD *v24; // rax

  v4 = a2;
  if ( a2 < 0 )
    return -2147024809;
  v7 = (a4 != 0) + a2;
  if ( v7 < a2 )
    return -2147467259;
  v8 = *((_QWORD *)this + 1);
  if ( v8 )
  {
    v9 = *(_OWORD **)(v8 + 32);
    v10 = *(_QWORD *)(v8 + 8);
    *(_OWORD *)(v8 + 24) = *v9;
    if ( v9 == (_OWORD *)(v10 + 8 * (3LL * *(int *)(v10 + 8) - 1)) )
    {
      *(_QWORD *)(v8 + 8) = *(_QWORD *)v10;
      *(_QWORD *)v10 = *(_QWORD *)(v8 + 16);
      *(_QWORD *)(v8 + 16) = v10;
    }
    v11 = (VARIANTARG **)((char *)this + 16);
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
    *((_QWORD *)this + 3) = 0;
  }
  else
  {
    v11 = (VARIANTARG **)((char *)this + 16);
  }
  if ( !v7 )
    return 0;
  v12 = *(_QWORD *)(*(_QWORD *)this + 200LL);
  if ( !v12 )
  {
    Value = TlsGetValue(g_luTls);
    v12 = Value ? Value[5] : 0LL;
    if ( !v12 )
      return -2147467259;
  }
  v14 = v7 + 1;
  if ( *(_QWORD *)(v12 + 8)
    && (v15 = (_OWORD *)(v12 + 24), v16 = **(_QWORD **)(v12 + 24), (v16 - *(_QWORD *)(v12 + 8) - 16) / 24 >= v14) )
  {
LABEL_14:
    v17 = (VARIANTARG *)(v16 - 24);
    *v11 = v17;
    *(_OWORD *)&v17->vt = *v15;
    *(_QWORD *)v15 = v11;
    *(_QWORD *)(v12 + 32) = v17;
    *((_QWORD *)this + 1) = v12;
    if ( !a4 )
      goto LABEL_18;
    --*v11;
    (*v11)->vt = 0;
    result = VariantCopy(*v11, a4);
    if ( result >= 0 )
    {
      result = VAR::Import((VAR *)*v11);
      if ( result >= 0 )
      {
        *((_QWORD *)this + 3) = *v11;
LABEL_18:
        v19 = a3;
        v20 = &a3[v4];
        while ( v20 > v19 )
        {
          --*v11;
          --v20;
          (*v11)->vt = 0;
          result = VariantCopy(*v11, v20);
          if ( result < 0 )
            return result;
          result = VAR::Import((VAR *)*v11);
          if ( result < 0 )
            return result;
          v19 = a3;
        }
        return 0;
      }
    }
  }
  else
  {
    while ( 1 )
    {
      v21 = *(_DWORD **)(v12 + 16);
      if ( !v21 )
        break;
      if ( v21[2] >= v14 )
        goto LABEL_28;
      *(_QWORD *)(v12 + 16) = *(_QWORD *)v21;
      free(v21);
    }
    v23 = 2 * v14;
    if ( *(_DWORD *)v12 < v23 )
      *(_DWORD *)v12 = v23;
    else
      v23 = *(_DWORD *)v12;
    v24 = malloc(24LL * v23 + 40);
    *(_QWORD *)(v12 + 16) = v24;
    if ( v24 )
    {
      v24[2] = v23;
      **(_QWORD **)(v12 + 16) = 0;
      *(_DWORD *)v12 *= 2;
LABEL_28:
      v22 = *(_QWORD *)(v12 + 16);
      v15 = (_OWORD *)(v12 + 24);
      *(_QWORD *)(v12 + 16) = *(_QWORD *)v22;
      *(_QWORD *)v22 = *(_QWORD *)(v12 + 8);
      *(_QWORD *)(v12 + 8) = v22;
      v16 = v22 + 8 * (*(int *)(v22 + 8) + 2 * (*(int *)(v22 + 8) + 1LL));
      goto LABEL_14;
    }
    *v11 = 0;
    return -2147024882;
  }
  return result;
}

```

## disassembly

```asm
0x1800030e8  mov     [rsp+arg_10], r8
0x1800030ed  push    rbx
0x1800030ee  push    rbp
0x1800030ef  push    rsi
0x1800030f0  push    rdi
0x1800030f1  push    r12
0x1800030f3  push    r13
0x1800030f5  push    r14
0x1800030f7  push    r15
0x1800030f9  sub     rsp, 28h
0x1800030fd  movsxd  r14, edx
0x180003100  mov     r12, r9
0x180003103  mov     rsi, rcx
0x180003106  test    edx, edx
0x180003108  js      loc_180003321
0x18000310e  xor     eax, eax
0x180003110  test    r9, r9
0x180003113  setnz   al
0x180003116  lea     ebp, [rax+r14]
0x18000311a  cmp     ebp, r14d
0x18000311d  jb      loc_180003382
0x180003123  mov     r8, [rcx+8]
0x180003127  test    r8, r8
0x18000312a  jz      loc_180003318
0x180003130  mov     rdx, [r8+20h]
0x180003134  mov     r9, [r8+8]
0x180003138  movups  xmm0, xmmword ptr [rdx]
0x18000313b  movdqu  xmmword ptr [r8+18h], xmm0
0x180003141  movsxd  rax, dword ptr [r9+8]
0x180003145  lea     rax, [rax+rax*2]
0x180003149  lea     rax, [rax-1]
0x18000314d  lea     rax, [r9+rax*8]
0x180003151  cmp     rdx, rax
0x180003154  jz      loc_1800032C4
0x18000315a  lea     rdi, [rcx+10h]
0x18000315e  mov     qword ptr [rcx+8], 0
0x180003166  mov     qword ptr [rdi], 0
0x18000316d  mov     qword ptr [rcx+18h], 0
0x180003175  test    ebp, ebp
0x180003177  jz      loc_1800032A9
0x18000317d  mov     rax, [rcx]
0x180003180  mov     rbx, [rax+0C8h]
0x180003187  test    rbx, rbx
0x18000318a  jnz     short loc_1800031B4
0x18000318c  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x180003192  call    cs:__imp_TlsGetValue
0x180003199  nop     dword ptr [rax+rax+00h]
0x18000319e  test    rax, rax
0x1800031a1  jz      loc_1800032BD
0x1800031a7  mov     rbx, [rax+28h]
0x1800031ab  test    rbx, rbx
0x1800031ae  jz      loc_180003382
0x1800031b4  inc     ebp
0x1800031b6  mov     r15, rbx
0x1800031b9  cmp     qword ptr [rbx+8], 0
0x1800031be  mov     r13, rbx
0x1800031c1  jz      loc_1800032DB
0x1800031c7  lea     r9, [rbx+18h]
0x1800031cb  mov     rax, [r9]
0x1800031ce  mov     r8, [rax]
0x1800031d1  mov     rax, 2AAAAAAAAAAAAAABh
0x1800031db  mov     rcx, r8
0x1800031de  sub     rcx, [rbx+8]
0x1800031e2  sub     rcx, 10h
0x1800031e6  imul    rcx
0x1800031e9  sar     rdx, 2
0x1800031ed  mov     rax, rdx
0x1800031f0  shr     rax, 3Fh
0x1800031f4  add     rdx, rax
0x1800031f7  movsxd  rax, ebp
0x1800031fa  cmp     rdx, rax
0x1800031fd  jl      loc_1800032DB
0x180003203  sub     r8, 18h
0x180003207  mov     [rdi], r8
0x18000320a  movups  xmm0, xmmword ptr [r9]
0x18000320e  movdqu  xmmword ptr [r8], xmm0
0x180003213  mov     [r9], rdi
0x180003216  mov     [rbx+20h], r8
0x18000321a  mov     [rsi+8], rbx
0x18000321e  test    r12, r12
0x180003221  jz      short loc_180003258
0x180003223  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x180003227  xor     eax, eax
0x180003229  mov     rcx, [rdi]
0x18000322c  mov     rdx, r12; pvargSrc
0x18000322f  mov     [rcx], ax
0x180003232  mov     rcx, [rdi]; pvargDest
0x180003235  call    cs:__imp_VariantCopy
0x18000323c  nop     dword ptr [rax+rax+00h]
0x180003241  test    eax, eax
0x180003243  js      short loc_1800032AB
0x180003245  mov     rcx, [rdi]; this
0x180003248  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x18000324d  test    eax, eax
0x18000324f  js      short loc_1800032AB
0x180003251  mov     rax, [rdi]
0x180003254  mov     [rsi+18h], rax
0x180003258  mov     rax, [rsp+68h+arg_10]
0x180003260  lea     rcx, [r14+r14*2]
0x180003264  lea     rbx, [rax+rcx*8]
0x180003268  cmp     rbx, rax
0x18000326b  jbe     short loc_1800032A9
0x18000326d  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x180003271  xor     eax, eax
0x180003273  mov     rcx, [rdi]
0x180003276  sub     rbx, 18h
0x18000327a  mov     rdx, rbx; pvargSrc
0x18000327d  mov     [rcx], ax
0x180003280  mov     rcx, [rdi]; pvargDest
0x180003283  call    cs:__imp_VariantCopy
0x18000328a  nop     dword ptr [rax+rax+00h]
0x18000328f  test    eax, eax
0x180003291  js      short loc_1800032AB
0x180003293  mov     rcx, [rdi]; this
0x180003296  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x18000329b  test    eax, eax
0x18000329d  js      short loc_1800032AB
0x18000329f  mov     rax, [rsp+68h+arg_10]
0x1800032a7  jmp     short loc_180003268
0x1800032a9  xor     eax, eax
0x1800032ab  add     rsp, 28h
0x1800032af  pop     r15
0x1800032b1  pop     r14
0x1800032b3  pop     r13
0x1800032b5  pop     r12
0x1800032b7  pop     rdi
0x1800032b8  pop     rsi
0x1800032b9  pop     rbp
0x1800032ba  pop     rbx
0x1800032bb  retn
0x1800032bd  xor     ebx, ebx
0x1800032bf  jmp     loc_1800031AB
0x1800032c4  mov     rax, [r9]
0x1800032c7  mov     [r8+8], rax
0x1800032cb  mov     rax, [r8+10h]
0x1800032cf  mov     [r9], rax
0x1800032d2  mov     [r8+10h], r9
0x1800032d6  jmp     loc_18000315A
0x1800032db  mov     rcx, [r15+10h]; Block
0x1800032df  test    rcx, rcx
0x1800032e2  jz      short loc_18000333D
0x1800032e4  cmp     [rcx+8], ebp
0x1800032e7  jl      short loc_180003328
0x1800032e9  mov     rdx, [rbx+10h]
0x1800032ed  lea     r9, [r13+18h]
0x1800032f1  mov     rax, [rdx]
0x1800032f4  mov     [r15+10h], rax
0x1800032f8  mov     rax, [rbx+8]
0x1800032fc  mov     [rdx], rax
0x1800032ff  mov     [rbx+8], rdx
0x180003303  movsxd  rax, dword ptr [rdx+8]
0x180003307  lea     r8, [rax+1]
0x18000330b  lea     r8, [rax+r8*2]
0x18000330f  lea     r8, [rdx+r8*8]
0x180003313  jmp     loc_180003203
0x180003318  lea     rdi, [rcx+10h]
0x18000331c  jmp     loc_180003175
0x180003321  mov     eax, 80070057h
0x180003326  jmp     short loc_1800032AB
0x180003328  mov     rax, [rcx]
0x18000332b  mov     [rbx+10h], rax
0x18000332f  call    cs:__imp_free
0x180003336  nop     dword ptr [rax+rax+00h]
0x18000333b  jmp     short loc_1800032DB
0x18000333d  add     ebp, ebp
0x18000333f  cmp     [rbx], ebp
0x180003341  jl      short loc_18000338C
0x180003343  mov     ebp, [rbx]
0x180003345  movsxd  rax, ebp
0x180003348  lea     rcx, [rax+rax*2]
0x18000334c  lea     rcx, ds:28h[rcx*8]; Size
0x180003354  call    cs:__imp_malloc
0x18000335b  nop     dword ptr [rax+rax+00h]
0x180003360  mov     [rbx+10h], rax
0x180003364  test    rax, rax
0x180003367  jz      short loc_180003390
0x180003369  mov     [rax+8], ebp
0x18000336c  mov     rax, [rbx+10h]
0x180003370  mov     qword ptr [rax], 0
0x180003377  mov     eax, [rbx]
0x180003379  add     eax, eax
0x18000337b  mov     [rbx], eax
0x18000337d  jmp     loc_1800032E9
0x180003382  mov     eax, 80004005h
0x180003387  jmp     loc_1800032AB
0x18000338c  mov     [rbx], ebp
0x18000338e  jmp     short loc_180003345
0x180003390  mov     qword ptr [rdi], 0
0x180003397  mov     eax, 8007000Eh
0x18000339c  jmp     loc_1800032AB
```
