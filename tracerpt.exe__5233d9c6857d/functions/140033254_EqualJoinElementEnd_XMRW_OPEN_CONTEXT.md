# EqualJoinElementEnd(_XMRW_OPEN_CONTEXT *)

- ea: `0x140033254`
- end: `0x14003340c`
- name: `?EqualJoinElementEnd@@YAKPEAU_XMRW_OPEN_CONTEXT@@@Z`
- size: `440`
- prototype: `unsigned int __fastcall(struct _XMRW_OPEN_CONTEXT *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14003290c`

## callees

- `0x140033254`
- `0x14003694c`
- `0x1400400b2`
- `0x140041010`

## pseudocode

```c
__int64 __fastcall EqualJoinElementEnd(struct _XMRW_OPEN_CONTEXT *a1)
{
  __int64 v1; // rbx
  __int64 v3; // rdi
  __int128 v4; // xmm0
  __int16 v5; // r14
  __m128i v6; // xmm6
  __int16 v7; // si
  __int64 v8; // r10
  unsigned __int64 v9; // xmm6_8
  unsigned __int64 v10; // rax
  _WORD *v11; // rcx
  __int64 v12; // rax
  __int128 Buf2; // [rsp+20h] [rbp-40h] BYREF
  __int64 v14; // [rsp+30h] [rbp-30h]
  __m128i Buf1; // [rsp+38h] [rbp-28h] BYREF
  __int64 v16; // [rsp+48h] [rbp-18h]
  unsigned int v17; // [rsp+80h] [rbp+20h] BYREF

  v1 = *((_QWORD *)a1 + 10);
  v17 = 0;
  if ( !v1 )
    return 0;
  v3 = *((_QWORD *)a1 + 3);
  if ( (*(_BYTE *)(v1 + 392) & 8) != 0 && (*(_BYTE *)(v1 + 576) & 8) != 0 )
  {
    v4 = *(_OWORD *)(v1 + 440);
    v5 = *(_WORD *)(v1 + 272);
    v6 = *(__m128i *)(v1 + 256);
    v7 = *(_WORD *)(v1 + 456);
    v16 = 0;
    v14 = 0;
    BYTE2(v16) = *(_BYTE *)(v1 + 274);
    BYTE2(v14) = *(_BYTE *)(v1 + 458);
    Buf1 = v6;
    LOWORD(v16) = v5;
    Buf2 = v4;
    LOWORD(v14) = v7;
    if ( !memcmp_0(&Buf1, &Buf2, 0x10u) && v5 == v7 )
      goto LABEL_20;
    v8 = v6.m128i_i64[0];
    v9 = _mm_srli_si128(v6, 8).m128i_u64[0];
    v10 = v8 - *(_QWORD *)(v1 + 632);
    if ( v8 == *(_QWORD *)(v1 + 632) )
      v10 = v9 - *(_QWORD *)(v1 + 640);
    v11 = (_WORD *)(v1 + 648);
    if ( v10 || v5 != *v11 )
    {
      v12 = v1 + 656;
    }
    else
    {
      v12 = v1 + 656;
      if ( Buf2 == *(_OWORD *)(v1 + 656) && v7 == *(_WORD *)(v1 + 672) )
        return 0;
    }
    if ( v8 != *(_QWORD *)v12
      || v9 != *(_QWORD *)(v12 + 8)
      || v5 != *(_WORD *)(v12 + 16)
      || Buf2 != *(_OWORD *)(v1 + 632)
      || v7 != *v11 )
    {
LABEL_20:
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v3 + 168LL))(v3, &v17);
      PrintMessage(0x473u, v17);
      return 3221745197LL;
    }
    return 0;
  }
  (*(void (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v3 + 168LL))(*((_QWORD *)a1 + 3), &v17);
  PrintMessage(0x472u, v17);
  return 3221745171LL;
}

```

## disassembly

```asm
0x140033254  mov     [rsp-18h+arg_8], rbx
0x140033259  mov     [rsp-18h+arg_10], rsi
0x14003325e  push    rbp
0x14003325f  push    rdi
0x140033260  push    r14
0x140033262  mov     rbp, rsp
0x140033265  sub     rsp, 60h
0x140033269  mov     rbx, [rcx+50h]
0x14003326d  movaps  [rsp+60h+var_10], xmm6
0x140033272  mov     [rbp+arg_0], 0
0x140033279  test    rbx, rbx
0x14003327c  jnz     short loc_140033285
0x14003327e  xor     eax, eax
0x140033280  jmp     loc_1400333F2
0x140033285  test    byte ptr [rbx+188h], 8
0x14003328c  mov     rdi, [rcx+18h]
0x140033290  jz      loc_1400333CA
0x140033296  test    byte ptr [rbx+240h], 8
0x14003329d  jz      loc_1400333CA
0x1400332a3  movups  xmm0, xmmword ptr [rbx+1B8h]
0x1400332aa  movzx   r14d, word ptr [rbx+110h]
0x1400332b2  xor     eax, eax
0x1400332b4  movups  xmm6, xmmword ptr [rbx+100h]
0x1400332bb  movzx   esi, word ptr [rbx+1C8h]
0x1400332c2  lea     rdx, [rbp+Buf2]; Buf2
0x1400332c6  mov     [rbp+var_18], rax
0x1400332ca  lea     rcx, [rbp+Buf1]; Buf1
0x1400332ce  mov     [rbp+var_30], rax
0x1400332d2  mov     r8d, 10h; Size
0x1400332d8  mov     al, [rbx+112h]
0x1400332de  mov     byte ptr [rbp+var_18+2], al
0x1400332e1  mov     al, [rbx+1CAh]
0x1400332e7  mov     byte ptr [rbp+var_30+2], al
0x1400332ea  movups  [rbp+Buf1], xmm6
0x1400332ee  mov     word ptr [rbp+var_18], r14w
0x1400332f3  movdqu  [rbp+Buf2], xmm0
0x1400332f8  mov     word ptr [rbp+var_30], si
0x1400332fc  call    memcmp_0
0x140033301  test    eax, eax
0x140033303  jnz     short loc_14003330F
0x140033305  cmp     r14w, si
0x140033309  jz      loc_1400333A0
0x14003330f  movq    r10, xmm6
0x140033314  psrldq  xmm6, 8
0x140033319  mov     rax, r10
0x14003331c  movq    r9, xmm6
0x140033321  sub     rax, [rbx+278h]
0x140033328  jnz     short loc_140033334
0x14003332a  mov     rax, r9
0x14003332d  sub     rax, [rbx+280h]
0x140033334  mov     rdx, qword ptr [rbp+Buf2+8]
0x140033338  lea     rcx, [rbx+288h]
0x14003333f  mov     r8, qword ptr [rbp+Buf2]
0x140033343  test    rax, rax
0x140033346  jnz     short loc_14003336C
0x140033348  cmp     r14w, [rcx]
0x14003334c  jnz     short loc_14003336C
0x14003334e  lea     rax, [rbx+290h]
0x140033355  cmp     r8, [rax]
0x140033358  jnz     short loc_140033373
0x14003335a  cmp     rdx, [rax+8]
0x14003335e  jnz     short loc_140033373
0x140033360  cmp     si, [rax+10h]
0x140033364  jz      loc_14003327E
0x14003336a  jmp     short loc_140033373
0x14003336c  lea     rax, [rbx+290h]
0x140033373  cmp     r10, [rax]
0x140033376  jnz     short loc_1400333A0
0x140033378  cmp     r9, [rax+8]
0x14003337c  jnz     short loc_1400333A0
0x14003337e  cmp     r14w, [rax+10h]
0x140033383  jnz     short loc_1400333A0
0x140033385  cmp     r8, [rbx+278h]
0x14003338c  jnz     short loc_1400333A0
0x14003338e  cmp     rdx, [rbx+280h]
0x140033395  jnz     short loc_1400333A0
0x140033397  cmp     si, [rcx]
0x14003339a  jz      loc_14003327E
0x1400333a0  mov     rax, [rdi]
0x1400333a3  lea     rdx, [rbp+arg_0]
0x1400333a7  mov     rcx, rdi
0x1400333aa  mov     rax, [rax+0A8h]
0x1400333b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400333b6  mov     edx, [rbp+arg_0]
0x1400333b9  mov     ecx, 473h; unsigned int
0x1400333be  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400333c3  mov     eax, 0C007EE2Dh
0x1400333c8  jmp     short loc_1400333F2
0x1400333ca  mov     rax, [rdi]
0x1400333cd  lea     rdx, [rbp+arg_0]
0x1400333d1  mov     rcx, rdi
0x1400333d4  mov     rax, [rax+0A8h]
0x1400333db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400333e0  mov     edx, [rbp+arg_0]
0x1400333e3  mov     ecx, 472h; unsigned int
0x1400333e8  call    ?PrintMessage@@YAXIZZ; PrintMessage(uint,...)
0x1400333ed  mov     eax, 0C007EE13h
0x1400333f2  movaps  xmm6, [rsp+60h+var_10]
0x1400333f7  lea     r11, [rsp+60h+var_s0]
0x1400333fc  mov     rbx, [r11+28h]
0x140033400  mov     rsi, [r11+30h]
0x140033404  mov     rsp, r11
0x140033407  pop     r14
0x140033409  pop     rdi
0x14003340a  pop     rbp
0x14003340b  retn
```
