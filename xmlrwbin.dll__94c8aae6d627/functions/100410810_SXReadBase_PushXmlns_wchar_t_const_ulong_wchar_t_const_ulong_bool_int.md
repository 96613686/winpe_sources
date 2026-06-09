# SXReadBase::PushXmlns(wchar_t const *,ulong,wchar_t const *,ulong,bool,int)

- ea: `0x100410810`
- end: `0x100410b91`
- name: `?PushXmlns@SXReadBase@@IEAAXPEB_WK0K_NH@Z`
- size: `897`
- prototype: `void(SXReadBase *__hidden this, const wchar_t *, unsigned int, const wchar_t *, unsigned int, bool, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x100410ba0`
- `0x100410d20`

## callees

- `0x100401350`
- `0x100410810`
- `0x100411520`
- `0x100415d60`
- `0x1004177d0`
- `0x100424580`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100410891`
- `KERNEL32!HeapAlloc` at `0x100410921`
- `KERNEL32!HeapAlloc` at `0x100410a58`
- `KERNEL32!HeapAlloc` at `0x100410891`
- `KERNEL32!HeapAlloc` at `0x100410921`
- `KERNEL32!HeapAlloc` at `0x100410a58`
- `KERNEL32!HeapFree` at `0x10041096a`
- `KERNEL32!HeapFree` at `0x10041096a`

## pseudocode

```c
void __fastcall SXReadBase::PushXmlns(
        SXReadBase *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        bool a6,
        int a7)
{
  void *v7; // rsi
  unsigned int v8; // r13d
  size_t v10; // r12
  struct IMalloc *v12; // rcx
  void *v13; // rax
  size_t v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rbp
  struct IMalloc *v17; // rcx
  SIZE_T v18; // r8
  bool v19; // zf
  LPVOID v20; // rax
  struct IMalloc *v21; // rcx
  unsigned int v22; // r9d
  __int64 v23; // r10
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // rdx
  unsigned int v27; // eax
  struct IMalloc *v28; // rcx
  SIZE_T v29; // r8
  char *v30; // rax
  char *v31; // r14
  unsigned int v32; // eax
  size_t v33; // rcx
  __int64 v34; // rsi
  size_t v35; // r12
  const wchar_t *v36; // rdx
  unsigned int i; // eax
  int v38; // ecx
  __int64 v39; // rdx

  v7 = (void *)*((_QWORD *)this + 11);
  v8 = *((_DWORD *)this + 30);
  v10 = a3;
  if ( !v7 )
  {
    *((_DWORD *)this + 21) = 64;
    v12 = (struct IMalloc *)*((_QWORD *)this + 1);
    if ( v12 || (v12 = g_pMalloc) != 0 )
      v13 = (void *)((__int64 (__fastcall *)(struct IMalloc *, __int64))v12->lpVtbl->Alloc)(v12, 256);
    else
      v13 = HeapAlloc(g_hHeap, 0, 0x100u);
    if ( v13 )
    {
      v14 = 4LL * *((unsigned int *)this + 21);
      *((_QWORD *)this + 11) = v13;
      memset(v13, 0, v14);
      goto LABEL_26;
    }
LABEL_50:
    MXRRaiseException(-2147024882);
    JUMPOUT(0x100410B90LL);
  }
  v15 = *((_DWORD *)this + 21);
  if ( v8 > v15 )
  {
    v16 = 2 * v15;
    if ( (unsigned int)v16 < v15 )
      goto LABEL_49;
    v17 = (struct IMalloc *)*((_QWORD *)this + 1);
    v18 = 4LL * (unsigned int)v16;
    if ( !is_mul_ok((unsigned int)v16, 4u) )
      v18 = -1;
    if ( v17 )
    {
      _mm_lfence();
    }
    else
    {
      v19 = g_pMalloc == 0;
      _mm_lfence();
      if ( v19 )
      {
        v20 = HeapAlloc(g_hHeap, 0, v18);
        goto LABEL_18;
      }
      v17 = g_pMalloc;
    }
    v20 = (LPVOID)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v17->lpVtbl->Alloc)(v17, v18);
LABEL_18:
    if ( !v20 )
      goto LABEL_50;
    v21 = (struct IMalloc *)*((_QWORD *)this + 1);
    *((_QWORD *)this + 11) = v20;
    *((_DWORD *)this + 21) = v16;
    if ( v21 || (v21 = g_pMalloc) != 0 )
      ((void (__fastcall *)(struct IMalloc *, void *))v21->lpVtbl->Free)(v21, v7);
    else
      HeapFree(g_hHeap, 0, v7);
    memset(*((void **)this + 11), 0, 4 * v16);
    v22 = 1;
    if ( v8 > 1 )
    {
      v23 = 48;
      do
      {
        v24 = *((_QWORD *)this + 14);
        v23 += 48;
        v25 = 4LL * (unsigned int)(*(_DWORD *)(v24 + v23 - 12) % *((_DWORD *)this + 21));
        *(_DWORD *)(v24 + v23 - 8) = *(_DWORD *)(v25 + *((_QWORD *)this + 11));
        *(_DWORD *)(v25 + *((_QWORD *)this + 11)) = v22++;
      }
      while ( v22 < v8 );
    }
  }
LABEL_26:
  v26 = v8 + 1;
  if ( *((_DWORD *)this + 31) < (unsigned int)v26 )
  {
    _mm_lfence();
    _stack<SXReadBase::XmlNsDecl,10>::grow((char *)this + 96, v26);
  }
  v27 = v10 + a5;
  if ( (unsigned int)v10 + a5 < (unsigned int)v10 )
  {
LABEL_49:
    MXRRaiseException(-2147352566);
    __debugbreak();
  }
  v28 = (struct IMalloc *)*((_QWORD *)this + 1);
  if ( !v27 )
    v27 = 1;
  v29 = 2LL * v27;
  if ( !is_mul_ok(v27, 2u) )
    v29 = -1;
  if ( v28 )
  {
    _mm_lfence();
LABEL_35:
    v30 = (char *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v28->lpVtbl->Alloc)(v28, v29);
    goto LABEL_39;
  }
  v19 = g_pMalloc == 0;
  _mm_lfence();
  if ( !v19 )
  {
    v28 = g_pMalloc;
    goto LABEL_35;
  }
  v30 = (char *)HeapAlloc(g_hHeap, 0, v29);
LABEL_39:
  v31 = v30;
  if ( !v30 )
    goto LABEL_50;
  v32 = *((_DWORD *)this + 30);
  if ( *((_DWORD *)this + 31) == v32 )
  {
    _stack<SXReadBase::XmlNsDecl,10>::grow((char *)this + 96, 0);
    v32 = *((_DWORD *)this + 30);
  }
  v33 = v10;
  *((_DWORD *)this + 30) = v32 + 1;
  v34 = *((_QWORD *)this + 14) + 48LL * v32;
  *(_DWORD *)(v34 + 12) = 0;
  *(_QWORD *)(v34 + 28) = 0;
  *(_QWORD *)(v34 + 36) = 0;
  *(_DWORD *)(v34 + 44) = 0;
  *(_DWORD *)(v34 + 8) = v10;
  v35 = 2 * v10;
  *(_QWORD *)v34 = v31;
  *(_DWORD *)(v34 + 24) = a5;
  *(_QWORD *)(v34 + 16) = &v31[v35];
  if ( v35 < v33 || (memmove(v31, a2, v35), *(_DWORD *)(v34 + 24) < a5) || 2 * (unsigned __int64)a5 < a5 )
  {
    MXRRaiseException(-2147467259);
    __debugbreak();
  }
  memmove(*(void **)(v34 + 16), a4, 2LL * a5);
  v36 = &a2[v35 / 2];
  *(_DWORD *)(v34 + 28) = a7;
  *(_BYTE *)(v34 + 32) = a6;
  for ( i = *((_DWORD *)this + 20); a2 < v36; i = v38 ^ (33 * i) )
    v38 = *a2++;
  *(_DWORD *)(v34 + 36) = i;
  v39 = 4LL * (i % *((_DWORD *)this + 21));
  *(_DWORD *)(v34 + 40) = *(_DWORD *)(v39 + *((_QWORD *)this + 11));
  *(_DWORD *)(v39 + *((_QWORD *)this + 11)) = v8;
}

```

## disassembly

```asm
0x100410810  mov     [rsp+arg_0], rbx
0x100410815  mov     [rsp+arg_8], rbp
0x10041081a  mov     [rsp+arg_10], rsi
0x10041081f  mov     [rsp+Src], r9
0x100410824  push    rdi
0x100410825  push    r12
0x100410827  push    r13
0x100410829  push    r14
0x10041082b  push    r15
0x10041082d  sub     rsp, 20h
0x100410831  mov     rsi, [rcx+58h]
0x100410835  mov     r9, 0FFFFFFFFFFFFFFFFh
0x10041083c  mov     r13d, [rcx+78h]
0x100410840  mov     rdi, rdx
0x100410843  mov     r12d, r8d
0x100410846  mov     rbx, rcx
0x100410849  lea     r14d, [r9+2]
0x10041084d  test    rsi, rsi
0x100410850  jnz     short loc_1004108BB
0x100410852  mov     dword ptr [rcx+54h], 40h ; '@'
0x100410859  mov     rcx, [rcx+8]
0x10041085d  test    rcx, rcx
0x100410860  jnz     short loc_10041086E
0x100410862  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410869  test    rcx, rcx
0x10041086c  jz      short loc_100410882
0x10041086e  mov     rax, [rcx]
0x100410871  mov     edx, 100h
0x100410876  mov     rax, [rax+18h]
0x10041087a  call    cs:__guard_dispatch_icall_fptr
0x100410880  jmp     short loc_100410897
0x100410882  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410889  xor     edx, edx; dwFlags
0x10041088b  mov     r8d, 100h; dwBytes
0x100410891  call    cs:__imp_HeapAlloc
0x100410897  test    rax, rax
0x10041089a  jz      loc_100410B86
0x1004108a0  mov     r8d, [rbx+54h]
0x1004108a4  xor     edx, edx; Val
0x1004108a6  shl     r8, 2; Size
0x1004108aa  mov     rcx, rax; void *
0x1004108ad  mov     [rbx+58h], rax
0x1004108b1  call    memset
0x1004108b6  jmp     loc_1004109D6
0x1004108bb  mov     eax, [rcx+54h]
0x1004108be  cmp     r13d, eax
0x1004108c1  jbe     loc_1004109D6
0x1004108c7  lea     ebp, [rax+rax]
0x1004108ca  cmp     ebp, eax
0x1004108cc  jb      loc_100410B7B
0x1004108d2  mov     rcx, [rcx+8]
0x1004108d6  mov     eax, 4
0x1004108db  mov     r14d, ebp
0x1004108de  mul     r14
0x1004108e1  mov     r8, rax
0x1004108e4  cmovo   r8, r9; dwBytes
0x1004108e8  test    rcx, rcx
0x1004108eb  jz      short loc_1004108F2
0x1004108ed  lfence
0x1004108f0  jmp     short loc_100410906
0x1004108f2  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x1004108fa  lfence
0x1004108fd  jz      short loc_100410918
0x1004108ff  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410906  mov     rax, [rcx]
0x100410909  mov     rdx, r8
0x10041090c  mov     rax, [rax+18h]
0x100410910  call    cs:__guard_dispatch_icall_fptr
0x100410916  jmp     short loc_100410927
0x100410918  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x10041091f  xor     edx, edx; dwFlags
0x100410921  call    cs:__imp_HeapAlloc
0x100410927  test    rax, rax
0x10041092a  jz      loc_100410B86
0x100410930  mov     rcx, [rbx+8]
0x100410934  mov     [rbx+58h], rax
0x100410938  mov     [rbx+54h], ebp
0x10041093b  test    rcx, rcx
0x10041093e  jnz     short loc_10041094C
0x100410940  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410947  test    rcx, rcx
0x10041094a  jz      short loc_10041095E
0x10041094c  mov     rax, [rcx]
0x10041094f  mov     rdx, rsi
0x100410952  mov     rax, [rax+28h]
0x100410956  call    cs:__guard_dispatch_icall_fptr
0x10041095c  jmp     short loc_100410970
0x10041095e  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410965  mov     r8, rsi; lpMem
0x100410968  xor     edx, edx; dwFlags
0x10041096a  call    cs:__imp_HeapFree
0x100410970  mov     rcx, [rbx+58h]; void *
0x100410974  lea     r8, ds:0[rbp*4]; Size
0x10041097c  xor     edx, edx; Val
0x10041097e  call    memset
0x100410983  mov     r14d, 1
0x100410989  mov     r9d, r14d
0x10041098c  cmp     r13d, r14d
0x10041098f  jbe     short loc_1004109D6
0x100410991  mov     r10d, 30h ; '0'
0x100410997  nop     word ptr [rax+rax+00000000h]
0x1004109a0  mov     r8, [rbx+70h]
0x1004109a4  lea     r10, [r10+30h]
0x1004109a8  xor     edx, edx
0x1004109aa  mov     eax, [r8+r10-0Ch]
0x1004109af  div     dword ptr [rbx+54h]
0x1004109b2  mov     rax, [rbx+58h]
0x1004109b6  lea     rdx, ds:0[rdx*4]
0x1004109be  mov     ecx, [rdx+rax]
0x1004109c1  mov     [r8+r10-8], ecx
0x1004109c6  mov     rax, [rbx+58h]
0x1004109ca  mov     [rdx+rax], r9d
0x1004109ce  inc     r9d
0x1004109d1  cmp     r9d, r13d
0x1004109d4  jb      short loc_1004109A0
0x1004109d6  lea     edx, [r13+1]
0x1004109da  cmp     [rbx+7Ch], edx
0x1004109dd  jnb     short loc_1004109EB
0x1004109df  lfence
0x1004109e2  lea     rcx, [rbx+60h]
0x1004109e6  call    ?grow@?$_stack@UXmlNsDecl@SXReadBase@@$09@@AEAAXI@Z; _stack<SXReadBase::XmlNsDecl,10>::grow(uint)
0x1004109eb  mov     r15d, [rsp+48h+arg_20]
0x1004109f0  lea     eax, [r12+r15]
0x1004109f4  cmp     eax, r12d
0x1004109f7  jb      loc_100410B7B
0x1004109fd  mov     rcx, [rbx+8]
0x100410a01  test    eax, eax
0x100410a03  cmovz   eax, r14d
0x100410a07  mov     edx, eax
0x100410a09  mov     eax, 2
0x100410a0e  mul     rdx
0x100410a11  mov     r8, rax
0x100410a14  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100410a1b  cmovo   r8, rax; dwBytes
0x100410a1f  test    rcx, rcx
0x100410a22  jz      short loc_100410A39
0x100410a24  lfence
0x100410a27  mov     rax, [rcx]
0x100410a2a  mov     rdx, r8
0x100410a2d  mov     rax, [rax+18h]
0x100410a31  call    cs:__guard_dispatch_icall_fptr
0x100410a37  jmp     short loc_100410A5E
0x100410a39  cmp     cs:?g_pMalloc@@3PEAUIMalloc@@EA, 0; IMalloc * g_pMalloc
0x100410a41  lfence
0x100410a44  jz      short loc_100410A4F
0x100410a46  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100410a4d  jmp     short loc_100410A27
0x100410a4f  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100410a56  xor     edx, edx; dwFlags
0x100410a58  call    cs:__imp_HeapAlloc
0x100410a5e  mov     r14, rax
0x100410a61  test    rax, rax
0x100410a64  jz      loc_100410B86
0x100410a6a  mov     eax, [rbx+78h]
0x100410a6d  cmp     [rbx+7Ch], eax
0x100410a70  jnz     short loc_100410A80
0x100410a72  xor     edx, edx
0x100410a74  lea     rcx, [rbx+60h]
0x100410a78  call    ?grow@?$_stack@UXmlNsDecl@SXReadBase@@$09@@AEAAXI@Z; _stack<SXReadBase::XmlNsDecl,10>::grow(uint)
0x100410a7d  mov     eax, [rbx+78h]
0x100410a80  mov     edx, eax
0x100410a82  mov     rcx, r12
0x100410a85  lea     eax, [rdx+1]
0x100410a88  mov     [rbx+78h], eax
0x100410a8b  lea     rsi, [rdx+rdx*2]
0x100410a8f  xor     eax, eax
0x100410a91  shl     rsi, 4
0x100410a95  add     rsi, [rbx+70h]
0x100410a99  mov     [rsi+0Ch], eax
0x100410a9c  mov     [rsi+1Ch], rax
0x100410aa0  mov     [rsi+24h], rax
0x100410aa4  mov     [rsi+2Ch], eax
0x100410aa7  mov     [rsi+8], r12d
0x100410aab  add     r12, r12
0x100410aae  mov     [rsi], r14
0x100410ab1  mov     [rsi+18h], r15d
0x100410ab5  lea     rax, [r12+r14]
0x100410ab9  mov     [rsi+10h], rax
0x100410abd  cmp     r12, rcx
0x100410ac0  jb      loc_100410B70
0x100410ac6  mov     r8, r12; Size
0x100410ac9  mov     rdx, rdi; Src
0x100410acc  mov     rcx, r14; void *
0x100410acf  call    memmove
0x100410ad4  cmp     [rsi+18h], r15d
0x100410ad8  jb      loc_100410B70
0x100410ade  lea     r8, [r15+r15]; Size
0x100410ae2  cmp     r8, r15
0x100410ae5  jb      loc_100410B70
0x100410aeb  mov     rdx, [rsp+48h+Src]; Src
0x100410af0  mov     rcx, [rsi+10h]; void *
0x100410af4  call    memmove
0x100410af9  mov     eax, [rsp+48h+arg_30]
0x100410b00  lea     rdx, [r12+rdi]
0x100410b04  mov     [rsi+1Ch], eax
0x100410b07  movzx   eax, [rsp+48h+arg_28]
0x100410b0c  mov     [rsi+20h], al
0x100410b0f  mov     eax, [rbx+50h]
0x100410b12  cmp     rdi, rdx
0x100410b15  jnb     short loc_100410B31
0x100410b17  nop     word ptr [rax+rax+00000000h]
0x100410b20  movzx   ecx, word ptr [rdi]
0x100410b23  add     rdi, 2
0x100410b27  imul    eax, 21h ; '!'
0x100410b2a  xor     eax, ecx
0x100410b2c  cmp     rdi, rdx
0x100410b2f  jb      short loc_100410B20
0x100410b31  mov     rbp, [rsp+48h+arg_8]
0x100410b36  xor     edx, edx
0x100410b38  mov     [rsi+24h], eax
0x100410b3b  div     dword ptr [rbx+54h]
0x100410b3e  mov     rax, [rbx+58h]
0x100410b42  lea     rdx, ds:0[rdx*4]
0x100410b4a  mov     ecx, [rdx+rax]
0x100410b4d  mov     [rsi+28h], ecx
0x100410b50  mov     rax, [rbx+58h]
0x100410b54  mov     rbx, [rsp+48h+arg_0]
0x100410b59  mov     rsi, [rsp+48h+arg_10]
0x100410b5e  mov     [rdx+rax], r13d
0x100410b62  add     rsp, 20h
0x100410b66  pop     r15
0x100410b68  pop     r14
0x100410b6a  pop     r13
0x100410b6c  pop     r12
0x100410b6e  pop     rdi
0x100410b6f  retn
0x100410b70  mov     ecx, 80004005h; int
0x100410b75  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100410b7a  int     3; Trap to Debugger
0x100410b7b  mov     ecx, 8002000Ah; int
0x100410b80  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100410b85  int     3; Trap to Debugger
0x100410b86  mov     ecx, 8007000Eh; int
0x100410b8b  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
