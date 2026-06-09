# _dict<uint,0>::replace(StringPtr *,uint,uint *)

- ea: `0x100415fd0`
- end: `0x100416220`
- name: `?replace@?$_dict@I$0A@@@QEAAXPEAUStringPtr@@IPEAI@Z`
- size: `592`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x100407d90`
- `0x100415950`

## callees

- `0x100401780`
- `0x100415fd0`
- `0x100416310`
- `0x1004277a0`
- `0x1004394f0`
- `0x100439df0`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x100416055`
- `KERNEL32!HeapAlloc` at `0x100416055`

## pseudocode

```c
__int64 __fastcall _dict<unsigned int,0>::replace(__int64 a1, const void **a2, int a3, _DWORD *a4)
{
  __int64 v4; // rsi
  const void **v6; // r14
  unsigned __int64 v8; // rbx
  struct IMalloc *v9; // rcx
  SIZE_T v10; // r8
  char *v11; // rax
  void *v12; // rcx
  __int64 v13; // rax
  const void *v14; // r12
  __int64 v15; // r15
  unsigned __int16 *v16; // rcx
  unsigned int v17; // edi
  size_t v18; // r9
  unsigned __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // r10
  __int64 v23; // rbx
  int v24; // r14d
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 result; // rax
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int128 v32; // xmm0
  __int128 v33; // xmm0
  __int64 v34; // [rsp+60h] [rbp+8h]

  v4 = 0;
  v6 = a2;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    if ( !a3 )
      goto LABEL_43;
    v8 = *(unsigned int *)(a1 + 32);
    v9 = *(struct IMalloc **)(a1 + 8);
    v10 = 24 * v8;
    if ( !is_mul_ok(v8, 0x18u) )
      v10 = -1;
    if ( v9 || (v9 = g_pMalloc) != 0 )
      v11 = (char *)((__int64 (__fastcall *)(struct IMalloc *, SIZE_T))v9->lpVtbl->Alloc)(v9, v10);
    else
      v11 = (char *)HeapAlloc(g_hHeap, 0, v10);
    v12 = v11;
    if ( !v11 )
    {
      MXRRaiseException(-2147024882);
      __debugbreak();
    }
    for ( ; v8; --v8 )
    {
      *(_QWORD *)v11 = 0;
      *((_DWORD *)v11 + 2) = 0;
      v11 += 24;
    }
    v13 = *(unsigned int *)(a1 + 32);
    *(_QWORD *)(a1 + 16) = v12;
    memset(v12, 0, 24 * v13);
  }
  v14 = *v6;
  v15 = *((unsigned int *)v6 + 2);
  v16 = (unsigned __int16 *)*v6;
  v17 = *(_DWORD *)(a1 + 24);
  v18 = 2 * v15;
  v19 = (unsigned __int64)*v6 + 2 * v15;
  if ( (unsigned __int64)*v6 < v19 )
  {
    do
    {
      v20 = *v16++;
      v17 = v20 ^ (33 * v17);
    }
    while ( (unsigned __int64)v16 < v19 );
  }
  v21 = *(unsigned int *)(a1 + 32);
  v22 = *(_QWORD *)(a1 + 16);
  v23 = v22 + 24LL * (v17 % ((int)v21 - 1));
  v34 = v22 + 24 * v21;
  if ( *(_QWORD *)v23 )
  {
    while ( 1 )
    {
      v24 = *(_DWORD *)(v23 + 20);
      v25 = v4;
      if ( v24 )
      {
        if ( v17 == *(_DWORD *)(v23 + 16) && (_DWORD)v15 == *(_DWORD *)(v23 + 8) )
        {
          if ( !memcmp(v14, *(const void **)v23, v18) )
          {
            result = (__int64)a4;
            *(_DWORD *)(v23 + 20) = a3;
            *a4 = v24;
            return result;
          }
          v22 = *(_QWORD *)(a1 + 16);
          v18 = 2 * v15;
        }
      }
      else
      {
        v4 = v23;
        if ( v25 )
          v4 = v25;
      }
      v26 = v23 + 24;
      v23 = v22;
      if ( v26 != v34 )
        v23 = v26;
      if ( !*(_QWORD *)v23 )
      {
        v6 = a2;
        break;
      }
    }
  }
  if ( !a3 )
  {
LABEL_43:
    MXRRaiseException(-2147418113);
    JUMPOUT(0x10041621FLL);
  }
  result = (__int64)a4;
  *a4 = 0;
  if ( v4 )
  {
    v23 = v4;
LABEL_41:
    v33 = *(_OWORD *)v6;
    *(_DWORD *)(v23 + 20) = a3;
    *(_DWORD *)(v23 + 16) = v17;
    *(_OWORD *)v23 = v33;
    return result;
  }
  result = (unsigned int)(*(_DWORD *)(a1 + 28) + 1);
  if ( *(_DWORD *)(a1 + 36) != (_DWORD)result )
  {
    *(_DWORD *)(a1 + 28) = result;
    goto LABEL_41;
  }
  _dict<unsigned int,0>::grow(a1);
  v28 = *(unsigned int *)(a1 + 32);
  v29 = *(_QWORD *)(a1 + 16);
  v30 = v17 % ((int)v28 - 1);
  v31 = v29 + 24LL * (unsigned int)v30;
  result = 3 * v28;
  if ( *(_QWORD *)(v29 + 24 * v30) )
  {
    do
    {
      if ( !*(_DWORD *)(v31 + 20) )
        break;
      result = v31 + 24;
      v31 = *(_QWORD *)(a1 + 16);
      if ( result != v29 + 24 * v28 )
        v31 = result;
    }
    while ( *(_QWORD *)v31 );
  }
  *(_DWORD *)(v31 + 20) = a3;
  v32 = *(_OWORD *)v6;
  *(_DWORD *)(v31 + 16) = v17;
  *(_OWORD *)v31 = v32;
  ++*(_DWORD *)(a1 + 28);
  return result;
}

```

## disassembly

```asm
0x100415fd0  mov     [rsp+arg_10], rbx
0x100415fd5  mov     [rsp+arg_18], r9
0x100415fda  mov     [rsp+arg_8], rdx
0x100415fdf  push    rbp
0x100415fe0  push    rsi
0x100415fe1  push    rdi
0x100415fe2  push    r12
0x100415fe4  push    r13
0x100415fe6  push    r14
0x100415fe8  push    r15
0x100415fea  sub     rsp, 20h
0x100415fee  xor     esi, esi
0x100415ff0  mov     r13d, r8d
0x100415ff3  mov     r14, rdx
0x100415ff6  mov     rbp, rcx
0x100415ff9  cmp     [rcx+10h], rsi
0x100415ffd  jnz     loc_100416096
0x100416003  test    r8d, r8d
0x100416006  jz      loc_100416215
0x10041600c  mov     ebx, [rcx+20h]
0x10041600f  mov     eax, 18h
0x100416014  mov     rcx, [rcx+8]
0x100416018  mul     rbx
0x10041601b  mov     r8, rax
0x10041601e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100416025  cmovo   r8, rax; dwBytes
0x100416029  test    rcx, rcx
0x10041602c  jz      short loc_100416040
0x10041602e  mov     rax, [rcx]
0x100416031  mov     rdx, r8
0x100416034  mov     rax, [rax+18h]
0x100416038  call    cs:__guard_dispatch_icall_fptr
0x10041603e  jmp     short loc_10041605B
0x100416040  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x100416047  test    rcx, rcx
0x10041604a  jnz     short loc_10041602E
0x10041604c  mov     rcx, cs:?g_hHeap@@3PEAXEA; hHeap
0x100416053  xor     edx, edx; dwFlags
0x100416055  call    cs:__imp_HeapAlloc
0x10041605b  mov     rcx, rax; void *
0x10041605e  test    rax, rax
0x100416061  jz      loc_10041620A
0x100416067  test    rbx, rbx
0x10041606a  jz      short loc_100416080
0x10041606c  nop     dword ptr [rax+00h]
0x100416070  mov     [rax], rsi
0x100416073  mov     [rax+8], esi
0x100416076  lea     rax, [rax+18h]
0x10041607a  sub     rbx, 1
0x10041607e  jnz     short loc_100416070
0x100416080  mov     eax, [rbp+20h]
0x100416083  xor     edx, edx; Val
0x100416085  mov     [rbp+10h], rcx
0x100416089  lea     r8, [rax+rax*2]
0x10041608d  shl     r8, 3; Size
0x100416091  call    memset
0x100416096  mov     r12, [r14]
0x100416099  mov     r15d, [r14+8]
0x10041609d  mov     rcx, r12
0x1004160a0  mov     edi, [rbp+18h]
0x1004160a3  lea     r9, [r15+r15]
0x1004160a7  lea     rdx, [r9+r12]
0x1004160ab  cmp     r12, rdx
0x1004160ae  jnb     short loc_1004160C1
0x1004160b0  movzx   eax, word ptr [rcx]
0x1004160b3  add     rcx, 2
0x1004160b7  imul    edi, 21h ; '!'
0x1004160ba  xor     edi, eax
0x1004160bc  cmp     rcx, rdx
0x1004160bf  jb      short loc_1004160B0
0x1004160c1  mov     r8d, [rbp+20h]
0x1004160c5  xor     edx, edx
0x1004160c7  mov     r10, [rbp+10h]
0x1004160cb  mov     eax, edi
0x1004160cd  lea     ecx, [r8-1]
0x1004160d1  div     ecx
0x1004160d3  lea     rax, [rdx+rdx*2]
0x1004160d7  lea     rbx, [r10+rax*8]
0x1004160db  lea     rax, [r8+r8*2]
0x1004160df  lea     rax, [r10+rax*8]
0x1004160e3  mov     [rsp+58h+arg_0], rax
0x1004160e8  cmp     [rbx], rsi
0x1004160eb  jz      short loc_10041614B
0x1004160ed  nop     dword ptr [rax]
0x1004160f0  mov     r14d, [rbx+14h]
0x1004160f4  mov     rcx, rsi
0x1004160f7  mov     rax, rsi
0x1004160fa  test    r14d, r14d
0x1004160fd  jnz     short loc_10041610B
0x1004160ff  test    rax, rax
0x100416102  mov     rsi, rbx
0x100416105  cmovnz  rsi, rax
0x100416109  jmp     short loc_100416130
0x10041610b  cmp     edi, [rbx+10h]
0x10041610e  jnz     short loc_100416130
0x100416110  cmp     r15d, [rbx+8]
0x100416114  jnz     short loc_100416130
0x100416116  mov     rdx, [rbx]; Buf2
0x100416119  mov     r8, r9; Size
0x10041611c  mov     rcx, r12; Buf1
0x10041611f  call    memcmp
0x100416124  test    eax, eax
0x100416126  jz      short loc_100416156
0x100416128  mov     r10, [rbp+10h]
0x10041612c  lea     r9, [r15+r15]
0x100416130  lea     rax, [rbx+18h]
0x100416134  mov     rbx, r10
0x100416137  cmp     rax, [rsp+58h+arg_0]
0x10041613c  cmovnz  rbx, rax
0x100416140  cmp     qword ptr [rbx], 0
0x100416144  jnz     short loc_1004160F0
0x100416146  mov     r14, [rsp+58h+arg_8]
0x10041614b  test    r13d, r13d
0x10041614e  jz      loc_100416215
0x100416154  jmp     short loc_100416167
0x100416156  mov     rax, [rsp+58h+arg_18]
0x10041615b  mov     [rbx+14h], r13d
0x10041615f  mov     [rax], r14d
0x100416162  jmp     loc_1004161F5
0x100416167  mov     rax, [rsp+58h+arg_18]
0x10041616c  mov     dword ptr [rax], 0
0x100416172  test    rsi, rsi
0x100416175  jz      short loc_10041617C
0x100416177  mov     rbx, rsi
0x10041617a  jmp     short loc_1004161E7
0x10041617c  mov     eax, [rbp+1Ch]
0x10041617f  inc     eax
0x100416181  cmp     [rbp+24h], eax
0x100416184  jnz     short loc_1004161E4
0x100416186  mov     rcx, rbp
0x100416189  call    ?grow@?$_dict@I$0A@@@AEAAXXZ; _dict<uint,0>::grow(void)
0x10041618e  mov     r8d, [rbp+20h]
0x100416192  xor     edx, edx
0x100416194  mov     r9, [rbp+10h]
0x100416198  mov     eax, edi
0x10041619a  lea     ecx, [r8-1]
0x10041619e  div     ecx
0x1004161a0  lea     rax, [rdx+rdx*2]
0x1004161a4  cmp     qword ptr [r9+rax*8], 0
0x1004161a9  lea     rcx, [r9+rax*8]
0x1004161ad  lea     rax, [r8+r8*2]
0x1004161b1  lea     rdx, [r9+rax*8]
0x1004161b5  jz      short loc_1004161D1
0x1004161b7  cmp     dword ptr [rcx+14h], 0
0x1004161bb  jz      short loc_1004161D1
0x1004161bd  lea     rax, [rcx+18h]
0x1004161c1  mov     rcx, r9
0x1004161c4  cmp     rax, rdx
0x1004161c7  cmovnz  rcx, rax
0x1004161cb  cmp     qword ptr [rcx], 0
0x1004161cf  jnz     short loc_1004161B7
0x1004161d1  mov     [rcx+14h], r13d
0x1004161d5  movups  xmm0, xmmword ptr [r14]
0x1004161d9  mov     [rcx+10h], edi
0x1004161dc  movups  xmmword ptr [rcx], xmm0
0x1004161df  inc     dword ptr [rbp+1Ch]
0x1004161e2  jmp     short loc_1004161F5
0x1004161e4  mov     [rbp+1Ch], eax
0x1004161e7  movups  xmm0, xmmword ptr [r14]
0x1004161eb  mov     [rbx+14h], r13d
0x1004161ef  mov     [rbx+10h], edi
0x1004161f2  movups  xmmword ptr [rbx], xmm0
0x1004161f5  mov     rbx, [rsp+58h+arg_10]
0x1004161fa  add     rsp, 20h
0x1004161fe  pop     r15
0x100416200  pop     r14
0x100416202  pop     r13
0x100416204  pop     r12
0x100416206  pop     rdi
0x100416207  pop     rsi
0x100416208  pop     rbp
0x100416209  retn
0x10041620a  mov     ecx, 8007000Eh; int
0x10041620f  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
0x100416214  int     3; Trap to Debugger
0x100416215  mov     ecx, 8000FFFFh; int
0x10041621a  call    ?MXRRaiseException@@YAXJ@Z; MXRRaiseException(long)
```
