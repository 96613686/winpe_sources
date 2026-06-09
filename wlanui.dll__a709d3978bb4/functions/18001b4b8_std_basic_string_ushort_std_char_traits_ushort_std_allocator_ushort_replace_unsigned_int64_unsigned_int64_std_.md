# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18001b4b8`
- end: `0x18001b817`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `863`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18001a8c0`
- `0x18001b820`

## callees

- `0x180001e26`
- `0x180001e32`
- `0x18001661c`
- `0x180016634`
- `0x18001af34`
- `0x18001b4b8`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *Src,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  _QWORD *v7; // r15
  unsigned __int64 v8; // r8
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rdi
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbp
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // r14
  _QWORD *v18; // rcx
  _QWORD *v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  _QWORD *v24; // rdx
  char *v25; // rdx
  char *v26; // rcx
  size_t v27; // r8
  _QWORD *v28; // rcx
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  _QWORD *v31; // rcx
  unsigned __int64 v32; // rbp
  _QWORD *v33; // rcx
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rcx
  size_t v37; // r8
  char *v38; // rdx
  char *v39; // rcx
  _QWORD *v40; // rax
  _QWORD *v41; // rcx
  __int64 v42; // rbp
  _QWORD *v43; // rax
  _QWORD *v44; // rcx
  _QWORD *v45; // rcx
  _QWORD *v46; // rdx
  _QWORD *v47; // rcx
  unsigned __int64 v49; // [rsp+60h] [rbp+8h]
  unsigned __int64 v50; // [rsp+68h] [rbp+10h]

  v7 = a4;
  v8 = Src[2];
  v10 = Src;
  if ( v8 < a2 || (v11 = a4[2], v11 < a5) )
    std::wstring::_Xran();
  v12 = a6;
  v13 = v8 - a2;
  if ( v8 - a2 < a3 )
    a3 = v8 - a2;
  v14 = v11 - a5;
  if ( v14 < a6 )
    v12 = v14;
  if ( ~v12 <= v8 - a3 )
    std::wstring::_Xlen();
  v50 = v12 - a3;
  v15 = v12 - a3 + v8;
  v49 = v15;
  if ( v8 < v15 )
  {
    if ( v15 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( Src[3] >= v15 )
    {
      if ( !v15 )
      {
        if ( Src[3] >= 8u )
          Src = (_QWORD *)*Src;
        v10[2] = 0;
        *(_WORD *)Src = 0;
      }
    }
    else
    {
      std::wstring::_Copy(Src);
    }
  }
  v16 = v10[3];
  v17 = v13 - a3;
  if ( v10 != v7 )
  {
    if ( v16 < 8 )
    {
      v18 = v10;
      v19 = v10;
    }
    else
    {
      v18 = (_QWORD *)*v10;
      v19 = (_QWORD *)*v10;
    }
    if ( v17 )
    {
      memmove_0((char *)v18 + 2 * a2 + 2 * v12, (char *)v19 + 2 * a2 + 2 * a3, 2 * v17);
      v16 = v10[3];
    }
    if ( v7[3] >= 8u )
      v7 = (_QWORD *)*v7;
    if ( v16 < 8 )
      v20 = v10;
    else
      v20 = (_QWORD *)*v10;
    if ( v12 )
      memcpy_0((char *)v20 + 2 * a2, (char *)v7 + 2 * a5, 2 * v12);
    goto LABEL_80;
  }
  if ( v12 <= a3 )
  {
    if ( v16 < 8 )
    {
      v21 = v10;
      v22 = v10;
    }
    else
    {
      v21 = (_QWORD *)*v10;
      v22 = (_QWORD *)*v10;
    }
    if ( v12 )
      memmove_0((char *)v21 + 2 * a2, (char *)v22 + 2 * a5, 2 * v12);
    if ( v10[3] < 8u )
    {
      v23 = v10;
      v24 = v10;
    }
    else
    {
      v23 = (_QWORD *)*v10;
      v24 = (_QWORD *)*v10;
    }
    if ( v17 )
    {
      v25 = (char *)v24 + 2 * a2 + 2 * a3;
      v26 = (char *)v23 + 2 * a2 + 2 * v12;
      v27 = 2 * v17;
LABEL_51:
      memmove_0(v26, v25, v27);
      goto LABEL_80;
    }
    goto LABEL_80;
  }
  if ( a5 > a2 )
  {
    v32 = a2 + a3;
    if ( a2 + a3 > a5 )
    {
      if ( v16 < 8 )
      {
        v40 = v10;
        v41 = v10;
      }
      else
      {
        v40 = (_QWORD *)*v10;
        v41 = (_QWORD *)*v10;
      }
      if ( a3 )
        memmove_0((char *)v40 + 2 * a2, (char *)v41 + 2 * a5, 2 * a3);
      v42 = 2 * v32;
      if ( v10[3] < 8u )
      {
        v44 = v10;
        v43 = v10;
      }
      else
      {
        v43 = (_QWORD *)*v10;
        v44 = (_QWORD *)*v10;
      }
      if ( v17 )
        memmove_0((char *)v44 + 2 * a2 + 2 * v12, (char *)v43 + v42, 2 * v17);
      if ( v10[3] < 8u )
      {
        v45 = v10;
        v46 = v10;
      }
      else
      {
        v45 = (_QWORD *)*v10;
        v46 = (_QWORD *)*v10;
      }
      if ( !v50 )
        goto LABEL_79;
      v37 = 2 * v50;
      v38 = (char *)v46 + 2 * v12 + 2 * a5;
      v39 = (char *)v45 + v42;
    }
    else
    {
      if ( v16 < 8 )
      {
        v33 = v10;
        v34 = v10;
      }
      else
      {
        v33 = (_QWORD *)*v10;
        v34 = (_QWORD *)*v10;
      }
      if ( v17 )
        memmove_0((char *)v33 + 2 * a2 + 2 * v12, (char *)v34 + 2 * v32, 2 * v17);
      if ( v10[3] < 8u )
      {
        v35 = v10;
        v36 = v10;
      }
      else
      {
        v35 = (_QWORD *)*v10;
        v36 = (_QWORD *)*v10;
      }
      if ( !v12 )
        goto LABEL_79;
      v37 = 2 * v12;
      v38 = (char *)v36 + 2 * v12 + 2 * (a5 - a3);
      v39 = (char *)v35 + 2 * a2;
    }
    memmove_0(v39, v38, v37);
LABEL_79:
    v15 = v49;
    goto LABEL_80;
  }
  if ( v16 < 8 )
  {
    v28 = v10;
    v29 = v10;
  }
  else
  {
    v28 = (_QWORD *)*v10;
    v29 = (_QWORD *)*v10;
  }
  if ( v17 )
    memmove_0((char *)v28 + 2 * a2 + 2 * v12, (char *)v29 + 2 * a2 + 2 * a3, 2 * v17);
  if ( v10[3] < 8u )
  {
    v30 = v10;
    v31 = v10;
  }
  else
  {
    v30 = (_QWORD *)*v10;
    v31 = (_QWORD *)*v10;
  }
  if ( v12 )
  {
    v25 = (char *)v31 + 2 * a5;
    v26 = (char *)v30 + 2 * a2;
    v27 = 2 * v12;
    goto LABEL_51;
  }
LABEL_80:
  if ( v10[3] < 8u )
    v47 = v10;
  else
    v47 = (_QWORD *)*v10;
  v10[2] = v15;
  *((_WORD *)v47 + v15) = 0;
  return v10;
}

```

## disassembly

```asm
0x18001b4b8  mov     [rsp+arg_10], rbx
0x18001b4bd  push    rbp
0x18001b4be  push    rsi
0x18001b4bf  push    rdi
0x18001b4c0  push    r12
0x18001b4c2  push    r13
0x18001b4c4  push    r14
0x18001b4c6  push    r15
0x18001b4c8  sub     rsp, 20h
0x18001b4cc  mov     r12, r8
0x18001b4cf  mov     r15, r9
0x18001b4d2  mov     r8, [rcx+10h]
0x18001b4d6  mov     rsi, rdx
0x18001b4d9  mov     rbx, rcx
0x18001b4dc  cmp     r8, rdx
0x18001b4df  jb      loc_18001B805
0x18001b4e5  mov     rax, [r9+10h]
0x18001b4e9  mov     r13, [rsp+58h+arg_20]
0x18001b4f1  cmp     rax, r13
0x18001b4f4  jb      loc_18001B805
0x18001b4fa  mov     rdi, [rsp+58h+arg_28]
0x18001b502  mov     r14, r8
0x18001b505  sub     r14, rdx
0x18001b508  mov     rcx, r8
0x18001b50b  cmp     r14, r12
0x18001b50e  cmovb   r12, r14
0x18001b512  sub     rax, r13
0x18001b515  cmp     rax, rdi
0x18001b518  cmovb   rdi, rax
0x18001b51c  sub     rcx, r12
0x18001b51f  mov     rax, rdi
0x18001b522  not     rax
0x18001b525  cmp     rax, rcx
0x18001b528  jbe     loc_18001B80B
0x18001b52e  mov     rax, rdi
0x18001b531  sub     rax, r12
0x18001b534  mov     [rsp+58h+arg_8], rax
0x18001b539  lea     rbp, [rax+r8]
0x18001b53d  mov     [rsp+58h+arg_0], rbp
0x18001b542  cmp     r8, rbp
0x18001b545  jnb     short loc_18001B58E
0x18001b547  mov     rax, 7FFFFFFFFFFFFFFEh
0x18001b551  cmp     rbp, rax
0x18001b554  ja      loc_18001B811
0x18001b55a  cmp     [rbx+18h], rbp
0x18001b55e  jnb     short loc_18001B56D
0x18001b560  mov     rdx, rbp
0x18001b563  mov     rcx, rbx; Src
0x18001b566  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18001b56b  jmp     short loc_18001B58E
0x18001b56d  test    rbp, rbp
0x18001b570  jnz     short loc_18001B58E
0x18001b572  cmp     qword ptr [rbx+18h], 8
0x18001b577  jb      short loc_18001B57E
0x18001b579  mov     rcx, [rbx]
0x18001b57c  jmp     short loc_18001B581
0x18001b57e  mov     rcx, rbx
0x18001b581  xor     eax, eax
0x18001b583  mov     qword ptr [rbx+10h], 0
0x18001b58b  mov     [rcx], ax
0x18001b58e  mov     rax, [rbx+18h]
0x18001b592  sub     r14, r12
0x18001b595  cmp     rbx, r15
0x18001b598  jz      short loc_18001B607
0x18001b59a  cmp     rax, 8
0x18001b59e  jb      short loc_18001B5A8
0x18001b5a0  mov     rcx, [rbx]
0x18001b5a3  mov     rdx, rcx
0x18001b5a6  jmp     short loc_18001B5AE
0x18001b5a8  mov     rcx, rbx
0x18001b5ab  mov     rdx, rbx
0x18001b5ae  test    r14, r14
0x18001b5b1  jz      short loc_18001B5D0
0x18001b5b3  lea     rax, [rsi+r12]
0x18001b5b7  lea     rdx, [rdx+rax*2]; Src
0x18001b5bb  lea     rax, [rsi+rdi]
0x18001b5bf  lea     rcx, [rcx+rax*2]; void *
0x18001b5c3  lea     r8, [r14+r14]; Size
0x18001b5c7  call    memmove_0
0x18001b5cc  mov     rax, [rbx+18h]
0x18001b5d0  cmp     qword ptr [r15+18h], 8
0x18001b5d5  jb      short loc_18001B5DA
0x18001b5d7  mov     r15, [r15]
0x18001b5da  cmp     rax, 8
0x18001b5de  jb      short loc_18001B5E5
0x18001b5e0  mov     rax, [rbx]
0x18001b5e3  jmp     short loc_18001B5E8
0x18001b5e5  mov     rax, rbx
0x18001b5e8  test    rdi, rdi
0x18001b5eb  jz      loc_18001B7D4
0x18001b5f1  lea     r8, [rdi+rdi]; Size
0x18001b5f5  lea     rdx, [r15+r13*2]; Src
0x18001b5f9  lea     rcx, [rax+rsi*2]; void *
0x18001b5fd  call    memcpy_0
0x18001b602  jmp     loc_18001B7D4
0x18001b607  cmp     rdi, r12
0x18001b60a  ja      short loc_18001B66A
0x18001b60c  cmp     rax, 8
0x18001b610  jb      short loc_18001B61A
0x18001b612  mov     rax, [rbx]
0x18001b615  mov     rcx, rax
0x18001b618  jmp     short loc_18001B620
0x18001b61a  mov     rax, rbx
0x18001b61d  mov     rcx, rbx
0x18001b620  test    rdi, rdi
0x18001b623  jz      short loc_18001B636
0x18001b625  lea     rdx, [rcx+r13*2]; Src
0x18001b629  lea     rcx, [rax+rsi*2]; void *
0x18001b62d  lea     r8, [rdi+rdi]; Size
0x18001b631  call    memmove_0
0x18001b636  cmp     qword ptr [rbx+18h], 8
0x18001b63b  jb      short loc_18001B645
0x18001b63d  mov     rcx, [rbx]
0x18001b640  mov     rdx, rcx
0x18001b643  jmp     short loc_18001B64B
0x18001b645  mov     rcx, rbx
0x18001b648  mov     rdx, rbx
0x18001b64b  test    r14, r14
0x18001b64e  jz      loc_18001B7D4
0x18001b654  lea     rax, [rsi+r12]
0x18001b658  lea     rdx, [rdx+rax*2]
0x18001b65c  lea     rax, [rsi+rdi]
0x18001b660  lea     rcx, [rcx+rax*2]
0x18001b664  lea     r8, [r14+r14]
0x18001b668  jmp     short loc_18001B6CB
0x18001b66a  cmp     r13, rsi
0x18001b66d  ja      short loc_18001B6D5
0x18001b66f  cmp     rax, 8
0x18001b673  jb      short loc_18001B67D
0x18001b675  mov     rcx, [rbx]
0x18001b678  mov     rdx, rcx
0x18001b67b  jmp     short loc_18001B683
0x18001b67d  mov     rcx, rbx
0x18001b680  mov     rdx, rbx
0x18001b683  test    r14, r14
0x18001b686  jz      short loc_18001B6A1
0x18001b688  lea     rax, [rsi+r12]
0x18001b68c  lea     rdx, [rdx+rax*2]; Src
0x18001b690  lea     rax, [rsi+rdi]
0x18001b694  lea     rcx, [rcx+rax*2]; void *
0x18001b698  lea     r8, [r14+r14]; Size
0x18001b69c  call    memmove_0
0x18001b6a1  cmp     qword ptr [rbx+18h], 8
0x18001b6a6  jb      short loc_18001B6B0
0x18001b6a8  mov     rax, [rbx]
0x18001b6ab  mov     rcx, rax
0x18001b6ae  jmp     short loc_18001B6B6
0x18001b6b0  mov     rax, rbx
0x18001b6b3  mov     rcx, rbx
0x18001b6b6  test    rdi, rdi
0x18001b6b9  jz      loc_18001B7D4
0x18001b6bf  lea     rdx, [rcx+r13*2]; Src
0x18001b6c3  lea     rcx, [rax+rsi*2]; void *
0x18001b6c7  lea     r8, [rdi+rdi]; Size
0x18001b6cb  call    memmove_0
0x18001b6d0  jmp     loc_18001B7D4
0x18001b6d5  lea     rbp, [rsi+r12]
0x18001b6d9  cmp     rbp, r13
0x18001b6dc  ja      short loc_18001B741
0x18001b6de  cmp     rax, 8
0x18001b6e2  jb      short loc_18001B6EC
0x18001b6e4  mov     rcx, [rbx]
0x18001b6e7  mov     rax, rcx
0x18001b6ea  jmp     short loc_18001B6F2
0x18001b6ec  mov     rcx, rbx
0x18001b6ef  mov     rax, rbx
0x18001b6f2  test    r14, r14
0x18001b6f5  jz      short loc_18001B70C
0x18001b6f7  lea     rdx, [rax+rbp*2]; Src
0x18001b6fb  lea     rax, [rsi+rdi]
0x18001b6ff  lea     rcx, [rcx+rax*2]; void *
0x18001b703  lea     r8, [r14+r14]; Size
0x18001b707  call    memmove_0
0x18001b70c  cmp     qword ptr [rbx+18h], 8
0x18001b711  jb      short loc_18001B71B
0x18001b713  mov     rax, [rbx]
0x18001b716  mov     rcx, rax
0x18001b719  jmp     short loc_18001B721
0x18001b71b  mov     rax, rbx
0x18001b71e  mov     rcx, rbx
0x18001b721  test    rdi, rdi
0x18001b724  jz      loc_18001B7CF
0x18001b72a  sub     r13, r12
0x18001b72d  lea     r8, [rdi+rdi]
0x18001b731  add     r13, rdi
0x18001b734  lea     rdx, [rcx+r13*2]
0x18001b738  lea     rcx, [rax+rsi*2]
0x18001b73c  jmp     loc_18001B7CA
0x18001b741  cmp     rax, 8
0x18001b745  jb      short loc_18001B74F
0x18001b747  mov     rax, [rbx]
0x18001b74a  mov     rcx, rax
0x18001b74d  jmp     short loc_18001B755
0x18001b74f  mov     rax, rbx
0x18001b752  mov     rcx, rbx
0x18001b755  test    r12, r12
0x18001b758  jz      short loc_18001B76B
0x18001b75a  lea     rdx, [rcx+r13*2]; Src
0x18001b75e  lea     rcx, [rax+rsi*2]; void *
0x18001b762  lea     r8, [r12+r12]; Size
0x18001b766  call    memmove_0
0x18001b76b  add     rbp, rbp
0x18001b76e  cmp     qword ptr [rbx+18h], 8
0x18001b773  jb      short loc_18001B77D
0x18001b775  mov     rax, [rbx]
0x18001b778  mov     rcx, rax
0x18001b77b  jmp     short loc_18001B783
0x18001b77d  mov     rcx, rbx
0x18001b780  mov     rax, rbx
0x18001b783  test    r14, r14
0x18001b786  jz      short loc_18001B79D
0x18001b788  lea     rdx, [rax+rbp]; Src
0x18001b78c  lea     rax, [rsi+rdi]
0x18001b790  lea     rcx, [rcx+rax*2]; void *
0x18001b794  lea     r8, [r14+r14]; Size
0x18001b798  call    memmove_0
0x18001b79d  cmp     qword ptr [rbx+18h], 8
0x18001b7a2  jb      short loc_18001B7AC
0x18001b7a4  mov     rcx, [rbx]
0x18001b7a7  mov     rdx, rcx
0x18001b7aa  jmp     short loc_18001B7B2
0x18001b7ac  mov     rcx, rbx
0x18001b7af  mov     rdx, rbx
0x18001b7b2  mov     r8, [rsp+58h+arg_8]
0x18001b7b7  test    r8, r8
0x18001b7ba  jz      short loc_18001B7CF
0x18001b7bc  add     r8, r8; Size
0x18001b7bf  lea     rax, [rdi+r13]
0x18001b7c3  lea     rdx, [rdx+rax*2]; Src
0x18001b7c7  add     rcx, rbp; void *
0x18001b7ca  call    memmove_0
0x18001b7cf  mov     rbp, [rsp+58h+arg_0]
0x18001b7d4  cmp     qword ptr [rbx+18h], 8
0x18001b7d9  jb      short loc_18001B7E0
0x18001b7db  mov     rcx, [rbx]
0x18001b7de  jmp     short loc_18001B7E3
0x18001b7e0  mov     rcx, rbx
0x18001b7e3  xor     eax, eax
0x18001b7e5  mov     [rbx+10h], rbp
0x18001b7e9  mov     [rcx+rbp*2], ax
0x18001b7ed  mov     rax, rbx
0x18001b7f0  mov     rbx, [rsp+58h+arg_10]
0x18001b7f5  add     rsp, 20h
0x18001b7f9  pop     r15
0x18001b7fb  pop     r14
0x18001b7fd  pop     r13
0x18001b7ff  pop     r12
0x18001b801  pop     rdi
0x18001b802  pop     rsi
0x18001b803  pop     rbp
0x18001b804  retn
0x18001b805  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18001b80b  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18001b811  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
