# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180010958`
- end: `0x180010c68`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `784`
- prototype: `_QWORD *__fastcall(_QWORD *Src, unsigned __int64, unsigned __int64, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180002300`

## callees

- `0x18000ff54`
- `0x180010360`
- `0x180010390`
- `0x180010958`
- `0x18001b3d6`
- `0x18001b3e2`

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
  _QWORD *v7; // rbp
  unsigned __int64 v8; // r8
  _QWORD *v10; // rbx
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r13
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r12
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // r13
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // rcx
  _QWORD *v25; // rdx
  char *v26; // rdx
  char *v27; // rcx
  size_t v28; // r8
  _QWORD *v29; // rcx
  _QWORD *v30; // rdx
  _QWORD *v31; // rax
  _QWORD *v32; // rcx
  unsigned __int64 v33; // rbp
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rcx
  __int64 v38; // rbp
  _QWORD *v39; // rax
  _QWORD *v40; // rcx
  _QWORD *v41; // rcx
  _QWORD *v42; // rdx
  _QWORD *v43; // rcx

  v7 = a4;
  v8 = Src[2];
  v10 = Src;
  if ( v8 < a2 || (v11 = a4[2], v12 = a5, v11 < a5) )
    std::wstring::_Xran(Src, a2, v8, a4);
  v13 = a6;
  v14 = v8 - a2;
  if ( v8 - a2 < a3 )
    a3 = v8 - a2;
  v15 = v11 - a5;
  if ( v15 < a6 )
    v13 = v15;
  if ( ~v13 <= v8 - a3 )
    std::wstring::_Xlen();
  v16 = v13 - a3 + v8;
  if ( v8 < v16 )
  {
    if ( v16 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( Src[3] >= v16 )
    {
      if ( !v16 )
      {
        if ( Src[3] >= 8u )
          Src = (_QWORD *)*Src;
        v10[2] = 0;
        *(_WORD *)Src = 0;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)Src, v13 - a3 + v8, v8);
    }
  }
  v17 = v10[3];
  v18 = v14 - a3;
  if ( v10 == v7 )
  {
    if ( v13 > a3 )
    {
      if ( a5 > a2 )
      {
        v33 = a2 + a3;
        if ( a2 + a3 > a5 )
        {
          if ( v17 < 8 )
          {
            v36 = v10;
            v37 = v10;
          }
          else
          {
            v36 = (_QWORD *)*v10;
            v37 = (_QWORD *)*v10;
          }
          memmove_0((char *)v36 + 2 * a2, (char *)v37 + 2 * a5, 2 * a3);
          v38 = 2 * v33;
          if ( v10[3] < 8u )
          {
            v40 = v10;
            v39 = v10;
          }
          else
          {
            v39 = (_QWORD *)*v10;
            v40 = (_QWORD *)*v10;
          }
          memmove_0((char *)v40 + 2 * a2 + 2 * v13, (char *)v39 + v38, 2 * v18);
          if ( v10[3] < 8u )
          {
            v41 = v10;
            v42 = v10;
          }
          else
          {
            v41 = (_QWORD *)*v10;
            v42 = (_QWORD *)*v10;
          }
          v28 = 2 * (v13 - a3);
          v26 = (char *)v42 + 2 * a5 + 2 * v13;
          v27 = (char *)v41 + v38;
          goto LABEL_60;
        }
        if ( v17 < 8 )
        {
          v34 = v10;
          v35 = v10;
        }
        else
        {
          v34 = (_QWORD *)*v10;
          v35 = (_QWORD *)*v10;
        }
        memmove_0((char *)v34 + 2 * a2 + 2 * v13, (char *)v35 + 2 * v33, 2 * v18);
        if ( v10[3] < 8u )
        {
          v31 = v10;
          v32 = v10;
        }
        else
        {
          v31 = (_QWORD *)*v10;
          v32 = (_QWORD *)*v10;
        }
        v12 = v13 + a5 - a3;
      }
      else
      {
        if ( v17 < 8 )
        {
          v29 = v10;
          v30 = v10;
        }
        else
        {
          v29 = (_QWORD *)*v10;
          v30 = (_QWORD *)*v10;
        }
        memmove_0((char *)v29 + 2 * a2 + 2 * v13, (char *)v30 + 2 * a2 + 2 * a3, 2 * v18);
        if ( v10[3] < 8u )
        {
          v31 = v10;
          v32 = v10;
        }
        else
        {
          v31 = (_QWORD *)*v10;
          v32 = (_QWORD *)*v10;
        }
      }
      v26 = (char *)v32 + 2 * v12;
      v27 = (char *)v31 + 2 * a2;
      v28 = 2 * v13;
    }
    else
    {
      if ( v17 < 8 )
      {
        v22 = v10;
        v23 = v10;
      }
      else
      {
        v22 = (_QWORD *)*v10;
        v23 = (_QWORD *)*v10;
      }
      memmove_0((char *)v22 + 2 * a2, (char *)v23 + 2 * a5, 2 * v13);
      if ( v10[3] < 8u )
      {
        v24 = v10;
        v25 = v10;
      }
      else
      {
        v24 = (_QWORD *)*v10;
        v25 = (_QWORD *)*v10;
      }
      v26 = (char *)v25 + 2 * a2 + 2 * a3;
      v27 = (char *)v24 + 2 * a2 + 2 * v13;
      v28 = 2 * v18;
    }
LABEL_60:
    memmove_0(v27, v26, v28);
    goto LABEL_61;
  }
  if ( v17 < 8 )
  {
    v19 = v10;
    v20 = v10;
  }
  else
  {
    v19 = (_QWORD *)*v10;
    v20 = (_QWORD *)*v10;
  }
  memmove_0((char *)v19 + 2 * a2 + 2 * v13, (char *)v20 + 2 * a2 + 2 * a3, 2 * v18);
  if ( v7[3] >= 8u )
    v7 = (_QWORD *)*v7;
  if ( v10[3] < 8u )
    v21 = v10;
  else
    v21 = (_QWORD *)*v10;
  memcpy_0((char *)v21 + 2 * a2, (char *)v7 + 2 * a5, 2 * v13);
LABEL_61:
  if ( v10[3] < 8u )
    v43 = v10;
  else
    v43 = (_QWORD *)*v10;
  v10[2] = v16;
  *((_WORD *)v43 + v16) = 0;
  return v10;
}

```

## disassembly

```asm
0x180010958  push    rbx
0x18001095a  push    rbp
0x18001095b  push    rsi
0x18001095c  push    rdi
0x18001095d  push    r12
0x18001095f  push    r13
0x180010961  push    r14
0x180010963  push    r15
0x180010965  sub     rsp, 28h
0x180010969  mov     r15, r8
0x18001096c  mov     rbp, r9
0x18001096f  mov     r8, [rcx+10h]
0x180010973  mov     rdi, rdx
0x180010976  mov     rbx, rcx
0x180010979  cmp     r8, rdx
0x18001097c  jb      loc_180010C56
0x180010982  mov     rax, [r9+10h]
0x180010986  mov     rsi, [rsp+68h+arg_20]
0x18001098e  cmp     rax, rsi
0x180010991  jb      loc_180010C56
0x180010997  mov     r14, [rsp+68h+arg_28]
0x18001099f  mov     r13, r8
0x1800109a2  sub     r13, rdx
0x1800109a5  mov     rcx, r8
0x1800109a8  cmp     r13, r15
0x1800109ab  cmovb   r15, r13
0x1800109af  sub     rax, rsi
0x1800109b2  cmp     rax, r14
0x1800109b5  cmovb   r14, rax
0x1800109b9  sub     rcx, r15
0x1800109bc  mov     rax, r14
0x1800109bf  not     rax
0x1800109c2  cmp     rax, rcx
0x1800109c5  jbe     loc_180010C5C
0x1800109cb  mov     rax, r14
0x1800109ce  sub     rax, r15
0x1800109d1  mov     [rsp+68h+arg_0], rax
0x1800109d6  lea     r12, [rax+r8]
0x1800109da  cmp     r8, r12
0x1800109dd  jnb     short loc_180010A26
0x1800109df  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800109e9  cmp     r12, rax
0x1800109ec  ja      loc_180010C62
0x1800109f2  cmp     [rbx+18h], r12
0x1800109f6  jnb     short loc_180010A05
0x1800109f8  mov     rdx, r12
0x1800109fb  mov     rcx, rbx; Src
0x1800109fe  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180010a03  jmp     short loc_180010A26
0x180010a05  test    r12, r12
0x180010a08  jnz     short loc_180010A26
0x180010a0a  cmp     qword ptr [rbx+18h], 8
0x180010a0f  jb      short loc_180010A16
0x180010a11  mov     rcx, [rbx]
0x180010a14  jmp     short loc_180010A19
0x180010a16  mov     rcx, rbx
0x180010a19  xor     eax, eax
0x180010a1b  mov     qword ptr [rbx+10h], 0
0x180010a23  mov     [rcx], ax
0x180010a26  mov     rax, [rbx+18h]
0x180010a2a  sub     r13, r15
0x180010a2d  cmp     rbx, rbp
0x180010a30  jz      short loc_180010A9A
0x180010a32  cmp     rax, 8
0x180010a36  jb      short loc_180010A40
0x180010a38  mov     rcx, [rbx]
0x180010a3b  mov     rdx, rcx
0x180010a3e  jmp     short loc_180010A46
0x180010a40  mov     rcx, rbx
0x180010a43  mov     rdx, rbx
0x180010a46  lea     rax, [rdi+r15]
0x180010a4a  lea     rdx, [rdx+rax*2]; Src
0x180010a4e  lea     rax, [rdi+r14]
0x180010a52  lea     rcx, [rcx+rax*2]; void *
0x180010a56  lea     r8, ds:0[r13*2]; Size
0x180010a5e  call    memmove_0
0x180010a63  cmp     qword ptr [rbp+18h], 8
0x180010a68  jb      short loc_180010A6E
0x180010a6a  mov     rbp, [rbp+0]
0x180010a6e  cmp     qword ptr [rbx+18h], 8
0x180010a73  jb      short loc_180010A7A
0x180010a75  mov     rax, [rbx]
0x180010a78  jmp     short loc_180010A7D
0x180010a7a  mov     rax, rbx
0x180010a7d  lea     rdx, ds:0[rsi*2]
0x180010a85  add     rdx, rbp; Src
0x180010a88  lea     r8, [r14+r14]; Size
0x180010a8c  lea     rcx, [rax+rdi*2]; void *
0x180010a90  call    memcpy_0
0x180010a95  jmp     loc_180010C28
0x180010a9a  cmp     r14, r15
0x180010a9d  ja      short loc_180010AF6
0x180010a9f  cmp     rax, 8
0x180010aa3  jb      short loc_180010AAD
0x180010aa5  mov     rax, [rbx]
0x180010aa8  mov     rcx, rax
0x180010aab  jmp     short loc_180010AB3
0x180010aad  mov     rax, rbx
0x180010ab0  mov     rcx, rbx
0x180010ab3  lea     rdx, [rcx+rsi*2]; Src
0x180010ab7  lea     rcx, [rax+rdi*2]; void *
0x180010abb  lea     r8, [r14+r14]; Size
0x180010abf  call    memmove_0
0x180010ac4  cmp     qword ptr [rbx+18h], 8
0x180010ac9  jb      short loc_180010AD3
0x180010acb  mov     rcx, [rbx]
0x180010ace  mov     rdx, rcx
0x180010ad1  jmp     short loc_180010AD9
0x180010ad3  mov     rcx, rbx
0x180010ad6  mov     rdx, rbx
0x180010ad9  lea     rax, [rdi+r15]
0x180010add  lea     rdx, [rdx+rax*2]
0x180010ae1  lea     rax, [rdi+r14]
0x180010ae5  lea     rcx, [rcx+rax*2]
0x180010ae9  lea     r8, ds:0[r13*2]
0x180010af1  jmp     loc_180010C23
0x180010af6  cmp     rsi, rdi
0x180010af9  ja      short loc_180010B52
0x180010afb  cmp     rax, 8
0x180010aff  jb      short loc_180010B09
0x180010b01  mov     rcx, [rbx]
0x180010b04  mov     rdx, rcx
0x180010b07  jmp     short loc_180010B0F
0x180010b09  mov     rcx, rbx
0x180010b0c  mov     rdx, rbx
0x180010b0f  lea     rax, [rdi+r15]
0x180010b13  lea     rdx, [rdx+rax*2]; Src
0x180010b17  lea     rax, [rdi+r14]
0x180010b1b  lea     rcx, [rcx+rax*2]; void *
0x180010b1f  lea     r8, ds:0[r13*2]; Size
0x180010b27  call    memmove_0
0x180010b2c  cmp     qword ptr [rbx+18h], 8
0x180010b31  jb      short loc_180010B3B
0x180010b33  mov     rax, [rbx]
0x180010b36  mov     rcx, rax
0x180010b39  jmp     short loc_180010B41
0x180010b3b  mov     rax, rbx
0x180010b3e  mov     rcx, rbx
0x180010b41  lea     rdx, [rcx+rsi*2]
0x180010b45  lea     rcx, [rax+rdi*2]
0x180010b49  lea     r8, [r14+r14]
0x180010b4d  jmp     loc_180010C23
0x180010b52  lea     rbp, [rdi+r15]
0x180010b56  cmp     rbp, rsi
0x180010b59  ja      short loc_180010BA5
0x180010b5b  cmp     rax, 8
0x180010b5f  jb      short loc_180010B69
0x180010b61  mov     rcx, [rbx]
0x180010b64  mov     rax, rcx
0x180010b67  jmp     short loc_180010B6F
0x180010b69  mov     rcx, rbx
0x180010b6c  mov     rax, rbx
0x180010b6f  lea     rdx, [rax+rbp*2]; Src
0x180010b73  lea     rax, [rdi+r14]
0x180010b77  lea     rcx, [rcx+rax*2]; void *
0x180010b7b  lea     r8, ds:0[r13*2]; Size
0x180010b83  call    memmove_0
0x180010b88  cmp     qword ptr [rbx+18h], 8
0x180010b8d  jb      short loc_180010B97
0x180010b8f  mov     rax, [rbx]
0x180010b92  mov     rcx, rax
0x180010b95  jmp     short loc_180010B9D
0x180010b97  mov     rax, rbx
0x180010b9a  mov     rcx, rbx
0x180010b9d  sub     rsi, r15
0x180010ba0  add     rsi, r14
0x180010ba3  jmp     short loc_180010B41
0x180010ba5  cmp     rax, 8
0x180010ba9  jb      short loc_180010BB3
0x180010bab  mov     rax, [rbx]
0x180010bae  mov     rcx, rax
0x180010bb1  jmp     short loc_180010BB9
0x180010bb3  mov     rax, rbx
0x180010bb6  mov     rcx, rbx
0x180010bb9  lea     rdx, [rcx+rsi*2]; Src
0x180010bbd  lea     rcx, [rax+rdi*2]; void *
0x180010bc1  lea     r8, [r15+r15]; Size
0x180010bc5  call    memmove_0
0x180010bca  add     rbp, rbp
0x180010bcd  cmp     qword ptr [rbx+18h], 8
0x180010bd2  jb      short loc_180010BDC
0x180010bd4  mov     rax, [rbx]
0x180010bd7  mov     rcx, rax
0x180010bda  jmp     short loc_180010BE2
0x180010bdc  mov     rcx, rbx
0x180010bdf  mov     rax, rbx
0x180010be2  lea     rdx, [rax+rbp]; Src
0x180010be6  lea     rax, [rdi+r14]
0x180010bea  lea     rcx, [rcx+rax*2]; void *
0x180010bee  lea     r8, ds:0[r13*2]; Size
0x180010bf6  call    memmove_0
0x180010bfb  cmp     qword ptr [rbx+18h], 8
0x180010c00  jb      short loc_180010C0A
0x180010c02  mov     rcx, [rbx]
0x180010c05  mov     rdx, rcx
0x180010c08  jmp     short loc_180010C10
0x180010c0a  mov     rcx, rbx
0x180010c0d  mov     rdx, rbx
0x180010c10  mov     r8, [rsp+68h+arg_0]
0x180010c15  lea     rax, [rsi+r14]
0x180010c19  add     r8, r8; Size
0x180010c1c  lea     rdx, [rdx+rax*2]; Src
0x180010c20  add     rcx, rbp; void *
0x180010c23  call    memmove_0
0x180010c28  cmp     qword ptr [rbx+18h], 8
0x180010c2d  jb      short loc_180010C34
0x180010c2f  mov     rcx, [rbx]
0x180010c32  jmp     short loc_180010C37
0x180010c34  mov     rcx, rbx
0x180010c37  xor     eax, eax
0x180010c39  mov     [rbx+10h], r12
0x180010c3d  mov     [rcx+r12*2], ax
0x180010c42  mov     rax, rbx
0x180010c45  add     rsp, 28h
0x180010c49  pop     r15
0x180010c4b  pop     r14
0x180010c4d  pop     r13
0x180010c4f  pop     r12
0x180010c51  pop     rdi
0x180010c52  pop     rsi
0x180010c53  pop     rbp
0x180010c54  pop     rbx
0x180010c55  retn
0x180010c56  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180010c5c  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x180010c62  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
