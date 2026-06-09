# VarList::ImportRgvar(long,tagVARIANT *,tagVARIANT *)

- ea: `0x18000530c`
- end: `0x1800055a6`
- name: `?ImportRgvar@VarList@@QEAAJJPEAUtagVARIANT@@0@Z`
- size: `666`
- prototype: `int(VarList *__hidden this, int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180021540`

## callees

- `0x18000530c`
- `0x180005e00`

## import_xrefs

- `msvcrt!malloc` at `0x18000555f`
- `msvcrt!malloc` at `0x18000555f`
- `msvcrt!free` at `0x180005540`
- `msvcrt!free` at `0x180005540`
- `OLEAUT32!__imp_VariantCopy` at `0x180005453`
- `OLEAUT32!__imp_VariantCopy` at `0x18000549b`
- `OLEAUT32!__imp_VariantCopy` at `0x180005453`
- `OLEAUT32!__imp_VariantCopy` at `0x18000549b`
- `KERNEL32!TlsGetValue` at `0x1800053b6`
- `KERNEL32!TlsGetValue` at `0x1800053b6`

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
0x18000530c  mov     [rsp+arg_10], r8
0x180005311  push    rbx
0x180005312  push    rbp
0x180005313  push    rsi
0x180005314  push    rdi
0x180005315  push    r12
0x180005317  push    r13
0x180005319  push    r14
0x18000531b  push    r15
0x18000531d  sub     rsp, 28h
0x180005321  movsxd  r14, edx
0x180005324  mov     r12, r9
0x180005327  mov     rsi, rcx
0x18000532a  test    edx, edx
0x18000532c  js      loc_180005532
0x180005332  xor     eax, eax
0x180005334  test    r9, r9
0x180005337  setnz   al
0x18000533a  lea     ebp, [rax+r14]
0x18000533e  cmp     ebp, r14d
0x180005341  jb      loc_180005587
0x180005347  mov     r8, [rcx+8]
0x18000534b  test    r8, r8
0x18000534e  jz      loc_180005529
0x180005354  mov     rdx, [r8+20h]
0x180005358  mov     r9, [r8+8]
0x18000535c  movups  xmm0, xmmword ptr [rdx]
0x18000535f  movdqu  xmmword ptr [r8+18h], xmm0
0x180005365  movsxd  rax, dword ptr [r9+8]
0x180005369  lea     rax, [rax+rax*2]
0x18000536d  lea     rax, [rax-1]
0x180005371  lea     rax, [r9+rax*8]
0x180005375  cmp     rdx, rax
0x180005378  jz      loc_1800054D5
0x18000537e  lea     rdi, [rcx+10h]
0x180005382  mov     qword ptr [rcx+8], 0
0x18000538a  mov     qword ptr [rdi], 0
0x180005391  mov     qword ptr [rcx+18h], 0
0x180005399  test    ebp, ebp
0x18000539b  jz      loc_1800054BB
0x1800053a1  mov     rax, [rcx]
0x1800053a4  mov     rbx, [rax+0C8h]
0x1800053ab  test    rbx, rbx
0x1800053ae  jnz     short loc_1800053D2
0x1800053b0  mov     ecx, cs:?g_luTls@@3KA; dwTlsIndex
0x1800053b6  call    cs:__imp_TlsGetValue
0x1800053bc  test    rax, rax
0x1800053bf  jz      loc_1800054CE
0x1800053c5  mov     rbx, [rax+28h]
0x1800053c9  test    rbx, rbx
0x1800053cc  jz      loc_180005587
0x1800053d2  inc     ebp
0x1800053d4  mov     r15, rbx
0x1800053d7  cmp     qword ptr [rbx+8], 0
0x1800053dc  mov     r13, rbx
0x1800053df  jz      loc_1800054EC
0x1800053e5  lea     r9, [rbx+18h]
0x1800053e9  mov     rax, [r9]
0x1800053ec  mov     r8, [rax]
0x1800053ef  mov     rax, 2AAAAAAAAAAAAAABh
0x1800053f9  mov     rcx, r8
0x1800053fc  sub     rcx, [rbx+8]
0x180005400  sub     rcx, 10h
0x180005404  imul    rcx
0x180005407  sar     rdx, 2
0x18000540b  mov     rax, rdx
0x18000540e  shr     rax, 3Fh
0x180005412  add     rdx, rax
0x180005415  movsxd  rax, ebp
0x180005418  cmp     rdx, rax
0x18000541b  jl      loc_1800054EC
0x180005421  sub     r8, 18h
0x180005425  mov     [rdi], r8
0x180005428  movups  xmm0, xmmword ptr [r9]
0x18000542c  movdqu  xmmword ptr [r8], xmm0
0x180005431  mov     [r9], rdi
0x180005434  mov     [rbx+20h], r8
0x180005438  mov     [rsi+8], rbx
0x18000543c  test    r12, r12
0x18000543f  jz      short loc_180005470
0x180005441  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x180005445  xor     eax, eax
0x180005447  mov     rcx, [rdi]
0x18000544a  mov     rdx, r12; pvargSrc
0x18000544d  mov     [rcx], ax
0x180005450  mov     rcx, [rdi]; pvargDest
0x180005453  call    cs:__imp_VariantCopy
0x180005459  test    eax, eax
0x18000545b  js      short loc_1800054BD
0x18000545d  mov     rcx, [rdi]; this
0x180005460  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x180005465  test    eax, eax
0x180005467  js      short loc_1800054BD
0x180005469  mov     rax, [rdi]
0x18000546c  mov     [rsi+18h], rax
0x180005470  mov     rax, [rsp+68h+arg_10]
0x180005478  lea     rcx, [r14+r14*2]
0x18000547c  lea     rbx, [rax+rcx*8]
0x180005480  cmp     rbx, rax
0x180005483  jbe     short loc_1800054BB
0x180005485  add     qword ptr [rdi], 0FFFFFFFFFFFFFFE8h
0x180005489  xor     eax, eax
0x18000548b  mov     rcx, [rdi]
0x18000548e  sub     rbx, 18h
0x180005492  mov     rdx, rbx; pvargSrc
0x180005495  mov     [rcx], ax
0x180005498  mov     rcx, [rdi]; pvargDest
0x18000549b  call    cs:__imp_VariantCopy
0x1800054a1  test    eax, eax
0x1800054a3  js      short loc_1800054BD
0x1800054a5  mov     rcx, [rdi]; this
0x1800054a8  call    ?Import@VAR@@QEAAJXZ; VAR::Import(void)
0x1800054ad  test    eax, eax
0x1800054af  js      short loc_1800054BD
0x1800054b1  mov     rax, [rsp+68h+arg_10]
0x1800054b9  jmp     short loc_180005480
0x1800054bb  xor     eax, eax
0x1800054bd  add     rsp, 28h
0x1800054c1  pop     r15
0x1800054c3  pop     r14
0x1800054c5  pop     r13
0x1800054c7  pop     r12
0x1800054c9  pop     rdi
0x1800054ca  pop     rsi
0x1800054cb  pop     rbp
0x1800054cc  pop     rbx
0x1800054cd  retn
0x1800054ce  xor     ebx, ebx
0x1800054d0  jmp     loc_1800053C9
0x1800054d5  mov     rax, [r9]
0x1800054d8  mov     [r8+8], rax
0x1800054dc  mov     rax, [r8+10h]
0x1800054e0  mov     [r9], rax
0x1800054e3  mov     [r8+10h], r9
0x1800054e7  jmp     loc_18000537E
0x1800054ec  mov     rcx, [r15+10h]; Block
0x1800054f0  test    rcx, rcx
0x1800054f3  jz      short loc_180005548
0x1800054f5  cmp     [rcx+8], ebp
0x1800054f8  jl      short loc_180005539
0x1800054fa  mov     rdx, [rbx+10h]
0x1800054fe  lea     r9, [r13+18h]
0x180005502  mov     rax, [rdx]
0x180005505  mov     [r15+10h], rax
0x180005509  mov     rax, [rbx+8]
0x18000550d  mov     [rdx], rax
0x180005510  mov     [rbx+8], rdx
0x180005514  movsxd  rax, dword ptr [rdx+8]
0x180005518  lea     r8, [rax+1]
0x18000551c  lea     r8, [rax+r8*2]
0x180005520  lea     r8, [rdx+r8*8]
0x180005524  jmp     loc_180005421
0x180005529  lea     rdi, [rcx+10h]
0x18000552d  jmp     loc_180005399
0x180005532  mov     eax, 80070057h
0x180005537  jmp     short loc_1800054BD
0x180005539  mov     rax, [rcx]
0x18000553c  mov     [rbx+10h], rax
0x180005540  call    cs:__imp_free
0x180005546  jmp     short loc_1800054EC
0x180005548  add     ebp, ebp
0x18000554a  cmp     [rbx], ebp
0x18000554c  jl      short loc_180005591
0x18000554e  mov     ebp, [rbx]
0x180005550  movsxd  rax, ebp
0x180005553  lea     rcx, [rax+rax*2]
0x180005557  lea     rcx, ds:28h[rcx*8]; Size
0x18000555f  call    cs:__imp_malloc
0x180005565  mov     [rbx+10h], rax
0x180005569  test    rax, rax
0x18000556c  jz      short loc_180005595
0x18000556e  mov     [rax+8], ebp
0x180005571  mov     rax, [rbx+10h]
0x180005575  mov     qword ptr [rax], 0
0x18000557c  mov     eax, [rbx]
0x18000557e  add     eax, eax
0x180005580  mov     [rbx], eax
0x180005582  jmp     loc_1800054FA
0x180005587  mov     eax, 80004005h
0x18000558c  jmp     loc_1800054BD
0x180005591  mov     [rbx], ebp
0x180005593  jmp     short loc_180005550
0x180005595  mov     qword ptr [rdi], 0
0x18000559c  mov     eax, 8007000Eh
0x1800055a1  jmp     loc_1800054BD
```
