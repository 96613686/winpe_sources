# utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180013580`
- end: `0x180013785`
- name: `?replace@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_K0PEBG0@Z`
- size: `517`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180011af0`

## callees

- `0x180005c80`
- `0x1800093bc`
- `0x180009408`
- `0x180009530`
- `0x180009580`
- `0x180013580`
- `0x180016c06`
- `0x180016c12`

## pseudocode

```c
char __fastcall utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::replace(
        char **a1,
        __int64 a2,
        unsigned __int64 a3,
        __int16 *a4,
        unsigned __int64 a5)
{
  char *v5; // rbx
  unsigned __int64 v9; // r8
  unsigned __int64 v11; // r15
  char v12; // di
  char *v13; // r12
  unsigned __int64 v14; // rax
  signed __int64 v15; // r13
  char *v16; // r10
  char *v17; // r11
  _WORD *v18; // rcx
  __int16 v19; // ax
  __int64 v20; // r15
  char *v21; // r13
  void *Src[2]; // [rsp+20h] [rbp-28h] BYREF
  char *v24; // [rsp+B0h] [rbp+68h]

  v5 = *a1;
  v9 = (unsigned __int64)a1[1];
  if ( (__int64)(v9 - (_QWORD)v5) >> 1 < a3 )
    a3 = (__int64)(v9 - (_QWORD)v5) >> 1;
  v11 = v9 + 2 * (a5 - a3);
  if ( v11 < (unsigned __int64)v5 )
    return 0;
  v12 = 1;
  v13 = &v5[2 * a3];
  if ( v5 == (char *)(a1 + 2) )
    v14 = (unsigned __int64)a1 + 30;
  else
    v14 = (unsigned __int64)a1[2];
  if ( v11 > v14 )
  {
    v20 = (__int64)(v11 - (_QWORD)v5) >> 1;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_GrowAlloc(
      a1,
      Src,
      v20);
    v21 = (char *)Src[0];
    if ( Src[0] )
    {
      memcpy_0(Src[0], a4, 2 * a5);
      memcpy_0(&v21[2 * a5], v13, 2 * ((a1[1] - v13) >> 1) + 2);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Reinit(
        a1,
        Src,
        v20);
      return v12;
    }
    return 0;
  }
  v15 = 2 * a5;
  v24 = (char *)&a4[a5];
  if ( v24 <= v5 || v9 < (unsigned __int64)a4 )
  {
    memmove_0(&v5[2 * a5], &v5[2 * a3], 2 * ((__int64)(v9 - (_QWORD)v13) >> 1) + 2);
    memcpy_0(v5, a4, v15);
    goto LABEL_22;
  }
  if ( a5 <= a3 )
  {
    memmove_0(v5, a4, 2 * a5);
    memmove_0(&v5[v15], v13, 2 * ((a1[1] - v13) >> 1) + 2);
LABEL_22:
    a1[1] = (char *)v11;
    return v12;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(Src);
  if ( (unsigned __int64)(v15 >> 1) < 8 )
    goto LABEL_16;
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Grow(Src) )
  {
    v16 = v24;
    v17 = &v5[v15];
LABEL_16:
    if ( a4 != (__int16 *)v16 )
    {
      v18 = Src[1];
      do
      {
        v19 = *a4++;
        *v18 = v19;
        v18 = (char *)Src[1] + 2;
        Src[1] = (char *)Src[1] + 2;
      }
      while ( a4 != (__int16 *)v16 );
    }
    memmove_0(v17, v13, 2 * ((a1[1] - v13) >> 1) + 2);
    memcpy_0(v5, Src[0], v15);
    a1[1] = (char *)v11;
    goto LABEL_20;
  }
  v12 = 0;
LABEL_20:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(Src);
  return v12;
}

```

## disassembly

```asm
0x180013580  push    rbp
0x180013582  push    rbx
0x180013583  push    rsi
0x180013584  push    rdi
0x180013585  push    r12
0x180013587  push    r13
0x180013589  push    r14
0x18001358b  push    r15
0x18001358d  mov     rbp, rsp
0x180013590  sub     rsp, 48h
0x180013594  mov     rbx, [rcx]
0x180013597  mov     rsi, r9
0x18001359a  mov     r9, r8
0x18001359d  mov     r14, rcx
0x1800135a0  mov     r8, [rcx+8]
0x1800135a4  mov     rcx, [rbp+arg_20]
0x1800135a8  mov     rax, r8
0x1800135ab  sub     rax, rbx
0x1800135ae  sar     rax, 1
0x1800135b1  cmp     rax, r9
0x1800135b4  cmovb   r9, rax
0x1800135b8  mov     rax, rcx
0x1800135bb  sub     rax, r9
0x1800135be  lea     r15, [r8+rax*2]
0x1800135c2  cmp     r15, rbx
0x1800135c5  jb      loc_18001376E
0x1800135cb  lea     rax, [r14+10h]
0x1800135cf  mov     dil, 1
0x1800135d2  lea     r12, [rbx+r9*2]
0x1800135d6  cmp     rbx, rax
0x1800135d9  jnz     short loc_1800135E1
0x1800135db  lea     rax, [r14+1Eh]
0x1800135df  jmp     short loc_1800135E4
0x1800135e1  mov     rax, [rax]
0x1800135e4  cmp     r15, rax
0x1800135e7  ja      loc_180013703
0x1800135ed  lea     r13, [rcx+rcx]
0x1800135f1  lea     r10, [rsi+r13]
0x1800135f5  mov     [rbp+arg_20], r10
0x1800135f9  lea     r11, [rbx+r13]
0x1800135fd  cmp     r10, rbx
0x180013600  jbe     loc_1800136D6
0x180013606  cmp     r8, rsi
0x180013609  jb      loc_1800136D6
0x18001360f  cmp     rcx, r9
0x180013612  ja      short loc_180013645
0x180013614  mov     r8, r13; Size
0x180013617  mov     rdx, rsi; Src
0x18001361a  mov     rcx, rbx; void *
0x18001361d  call    memmove_0
0x180013622  mov     r8, [r14+8]
0x180013626  lea     rcx, [rbx+r13]; void *
0x18001362a  sub     r8, r12
0x18001362d  mov     rdx, r12; Src
0x180013630  sar     r8, 1
0x180013633  lea     r8, ds:2[r8*2]; Size
0x18001363b  call    memmove_0
0x180013640  jmp     loc_1800136FD
0x180013645  lea     rcx, [rbp+Src]; void *
0x180013649  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x18001364e  mov     rdx, r13
0x180013651  sar     rdx, 1
0x180013654  cmp     rdx, 8
0x180013658  jb      short loc_180013674
0x18001365a  lea     rcx, [rbp+Src]
0x18001365e  call    ?_Grow@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA_N_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Grow(unsigned __int64)
0x180013663  test    al, al
0x180013665  jnz     short loc_18001366C
0x180013667  xor     dil, dil
0x18001366a  jmp     short loc_1800136C8
0x18001366c  mov     r10, [rbp+arg_20]
0x180013670  lea     r11, [rbx+r13]
0x180013674  cmp     rsi, r10
0x180013677  jz      short loc_180013698
0x180013679  mov     rcx, [rbp+Src+8]
0x18001367d  movzx   eax, word ptr [rsi]
0x180013680  add     rsi, 2
0x180013684  mov     [rcx], ax
0x180013687  mov     rcx, [rbp+Src+8]
0x18001368b  add     rcx, 2
0x18001368f  mov     [rbp+Src+8], rcx
0x180013693  cmp     rsi, r10
0x180013696  jnz     short loc_18001367D
0x180013698  mov     r8, [r14+8]
0x18001369c  mov     rdx, r12; Src
0x18001369f  sub     r8, r12
0x1800136a2  mov     rcx, r11; void *
0x1800136a5  sar     r8, 1
0x1800136a8  lea     r8, ds:2[r8*2]; Size
0x1800136b0  call    memmove_0
0x1800136b5  mov     rdx, [rbp+Src]; Src
0x1800136b9  mov     r8, r13; Size
0x1800136bc  mov     rcx, rbx; void *
0x1800136bf  call    memcpy_0
0x1800136c4  mov     [r14+8], r15
0x1800136c8  lea     rcx, [rbp+Src]
0x1800136cc  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800136d1  jmp     loc_180013771
0x1800136d6  sub     r8, r12
0x1800136d9  mov     rdx, r12; Src
0x1800136dc  sar     r8, 1
0x1800136df  mov     rcx, r11; void *
0x1800136e2  lea     r8, ds:2[r8*2]; Size
0x1800136ea  call    memmove_0
0x1800136ef  mov     r8, r13; Size
0x1800136f2  mov     rdx, rsi; Src
0x1800136f5  mov     rcx, rbx; void *
0x1800136f8  call    memcpy_0
0x1800136fd  mov     [r14+8], r15
0x180013701  jmp     short loc_180013771
0x180013703  sub     r15, rbx
0x180013706  lea     rdx, [rbp+Src]
0x18001370a  sar     r15, 1
0x18001370d  mov     rcx, r14
0x180013710  mov     r8, r15
0x180013713  call    ?_GrowAlloc@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAA?AU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_GrowAlloc(unsigned __int64)
0x180013718  mov     r13, [rbp+Src]
0x18001371c  test    r13, r13
0x18001371f  jz      short loc_18001376E
0x180013721  mov     rbx, [rbp+arg_20]
0x180013725  mov     rdx, rsi; Src
0x180013728  add     rbx, rbx
0x18001372b  mov     rcx, r13; void *
0x18001372e  mov     r8, rbx; Size
0x180013731  call    memcpy_0
0x180013736  mov     r8, [r14+8]
0x18001373a  lea     rcx, [rbx+r13]; void *
0x18001373e  sub     r8, r12
0x180013741  mov     rdx, r12; Src
0x180013744  sar     r8, 1
0x180013747  lea     r8, ds:2[r8*2]; Size
0x18001374f  call    memcpy_0
0x180013754  movaps  xmm0, xmmword ptr [rbp+Src]
0x180013758  lea     rdx, [rbp+Src]
0x18001375c  mov     r8, r15
0x18001375f  movdqa  xmmword ptr [rbp+Src], xmm0
0x180013764  mov     rcx, r14
0x180013767  call    ?_Reinit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXU?$pair@PEAG_K@2@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Reinit(utl::pair<ushort *,unsigned __int64>,unsigned __int64)
0x18001376c  jmp     short loc_180013771
0x18001376e  xor     dil, dil
0x180013771  mov     al, dil
0x180013774  add     rsp, 48h
0x180013778  pop     r15
0x18001377a  pop     r14
0x18001377c  pop     r13
0x18001377e  pop     r12
0x180013780  pop     rdi
0x180013781  pop     rsi
0x180013782  pop     rbx
0x180013783  pop     rbp
0x180013784  retn
```
