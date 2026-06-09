# compress_block

- ea: `0x180008b00`
- end: `0x180008f28`
- name: `compress_block`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008190`

## callees

- `0x180008b00`

## pseudocode

```c
__int64 __fastcall compress_block(__int64 a1, __int64 a2, __int64 a3)
{
  int *v3; // r11
  __int64 v4; // r10
  _DWORD *v5; // rax
  __int64 v6; // r14
  _QWORD *v7; // rdi
  __int64 v8; // r12
  __int64 v10; // r9
  _QWORD *v11; // r13
  _DWORD *v12; // rsi
  int v13; // r8d
  __int64 v14; // r14
  int v15; // edx
  __int64 v16; // r14
  __int64 v17; // rbp
  int v18; // ecx
  unsigned __int16 v19; // r9
  int v20; // edi
  __int16 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  int v24; // edx
  __int64 v25; // r13
  __int64 v26; // rcx
  unsigned __int16 v27; // r9
  int v28; // esi
  __int16 v29; // dx
  __int64 v30; // rcx
  char v31; // dl
  int v32; // r8d
  __int16 v33; // r9
  int v34; // r12d
  unsigned __int16 v35; // bp
  __int16 v36; // si
  int v37; // r8d
  char v38; // cl
  __int16 v39; // bp
  __int16 v40; // si
  unsigned int v41; // ecx
  int v42; // r12d
  unsigned __int16 v43; // r9
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int16 v46; // r8
  _QWORD *v47; // r13
  int v48; // r12d
  _DWORD *v49; // rdx
  __int16 v50; // r9
  int v51; // ebp
  unsigned __int16 v52; // si
  __int16 v53; // r8
  int v54; // r8d
  unsigned __int16 v55; // r9
  int v56; // ebx
  int v57; // ecx
  __int16 v58; // dx
  __int64 result; // rax
  _QWORD *v60; // [rsp+0h] [rbp-58h]
  int v61; // [rsp+60h] [rbp+8h]
  __int64 v62; // [rsp+60h] [rbp+8h]

  v3 = (int *)(a1 + 5904);
  v4 = a1 + 5900;
  v5 = (_DWORD *)(a1 + 40);
  v6 = 0;
  v7 = (_QWORD *)(a1 + 16);
  v8 = a2;
  if ( *(_DWORD *)(a1 + 5876) )
  {
    while ( 1 )
    {
      v10 = *(_QWORD *)(a1 + 5864);
      v11 = v7;
      v60 = v7;
      v12 = v5;
      v13 = *(unsigned __int8 *)(v6 + v10);
      v14 = (unsigned int)(v6 + 1);
      v15 = *(unsigned __int8 *)(v14 + v10);
      v16 = (unsigned int)(v14 + 1);
      v61 = v13 + (v15 << 8);
      v17 = *(unsigned __int8 *)(v16 + v10);
      v6 = (unsigned int)(v16 + 1);
      if ( !v61 )
      {
        v18 = *v3;
        v19 = *(_WORD *)(v8 + 4 * v17);
        v20 = *(unsigned __int16 *)(v8 + 4 * v17 + 2);
        v21 = *(_WORD *)v4 | (v19 << *v3);
        if ( *v3 <= 16 - v20 )
        {
          *(_WORD *)v4 = v21;
          *v3 = v18 + v20;
          v5 = (_DWORD *)(a1 + 40);
          v7 = (_QWORD *)(a1 + 16);
        }
        else
        {
          v22 = *(unsigned int *)(a1 + 40);
          v23 = *(_QWORD *)(a1 + 16);
          *(_WORD *)v4 = v21;
          *(_BYTE *)(v22 + v23) = v21;
          *(_BYTE *)((unsigned int)++*(_DWORD *)(a1 + 40) + *(_QWORD *)(a1 + 16)) = *(_BYTE *)(v4 + 1);
          LODWORD(v23) = *v3;
          LOBYTE(v22) = 16 - *v3;
          ++*(_DWORD *)(a1 + 40);
          v24 = v20 + v23 - 16;
          v5 = (_DWORD *)(a1 + 40);
          v7 = (_QWORD *)(a1 + 16);
          *(_WORD *)v4 = v19 >> v22;
          *v3 = v24;
        }
        goto LABEL_26;
      }
      v25 = (unsigned __int8)length_code[v17];
      v26 = (unsigned int)(v25 + 257);
      v27 = *(_WORD *)(v8 + 4 * v26);
      v28 = *(unsigned __int16 *)(v8 + 4 * v26 + 2);
      v29 = *(_WORD *)v4 | (v27 << *v3);
      if ( *v3 <= 16 - v28 )
      {
        v32 = v28 + *v3;
        v33 = *(_WORD *)v4 | (v27 << *v3);
      }
      else
      {
        v30 = *v7;
        *(_WORD *)v4 = v29;
        *(_BYTE *)((unsigned int)(*v5)++ + v30) = v29;
        *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
        LODWORD(v30) = *v3;
        v31 = 16 - *v3;
        ++*v5;
        v32 = v28 + v30 - 16;
        v33 = v27 >> v31;
      }
      *(_WORD *)v4 = v33;
      *v3 = v32;
      v34 = dword_18003E460[v25];
      if ( v34 )
      {
        v35 = v17 - word_18003EAD0[2 * v25];
        v36 = v33 | (v35 << v32);
        *(_WORD *)v4 = v36;
        if ( v32 <= 16 - v34 )
        {
          v32 += v34;
          v39 = v36;
        }
        else
        {
          *(_BYTE *)((unsigned int)(*v5)++ + *v7) = v36;
          *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
          v37 = *v3;
          v38 = 16 - *v3;
          ++*v5;
          v39 = v35 >> v38;
          v32 = v34 + v37 - 16;
          *(_WORD *)v4 = v39;
        }
        *v3 = v32;
      }
      else
      {
        v39 = v33;
      }
      v40 = v61 - 1;
      v41 = v61 - 1;
      if ( (unsigned int)(v61 - 1) >= 0x100 )
        v41 = (v41 >> 7) + 256;
      v62 = 4LL * (unsigned __int8)dist_code[v41];
      v42 = *(unsigned __int16 *)(v62 + a3 + 2);
      v43 = *(_WORD *)(v62 + a3);
      if ( v32 <= 16 - v42 )
      {
        v48 = v32 + v42;
        v50 = v39 | (v43 << v32);
        v49 = (_DWORD *)(a1 + 40);
        v47 = (_QWORD *)(a1 + 16);
      }
      else
      {
        v44 = (unsigned int)*v5;
        v45 = *v7;
        v46 = v39 | (v43 << v32);
        *(_WORD *)v4 = v46;
        v47 = v7;
        *(_BYTE *)(v44 + v45) = v46;
        *(_BYTE *)((unsigned int)++*v5 + *v7) = *(_BYTE *)(v4 + 1);
        LODWORD(v45) = *v3;
        v48 = *v3 + v42 - 16;
        ++*v5;
        v49 = v5;
        v50 = v43 >> (16 - v45);
      }
      *(_WORD *)v4 = v50;
      *v3 = v48;
      v51 = *(_DWORD *)((char *)&qword_18003E480[12] + v62);
      if ( !v51 )
        goto LABEL_24;
      v52 = v40 - *(_WORD *)((char *)qword_18003EB50 + v62);
      v53 = v50 | (v52 << v48);
      *(_WORD *)v4 = v53;
      if ( v48 <= 16 - v51 )
        break;
      v11 = v7;
      *(_BYTE *)((unsigned int)(*v5)++ + *v7) = v53;
      *(_BYTE *)((unsigned int)*v5 + *v7) = *(_BYTE *)(v4 + 1);
      v54 = *v3;
      ++*v5;
      *(_WORD *)v4 = v52 >> (16 - v54);
      *v3 = v54 + v51 - 16;
      v12 = v5;
LABEL_25:
      v8 = a2;
LABEL_26:
      if ( (unsigned int)v6 >= *(_DWORD *)(a1 + 5876) )
        goto LABEL_29;
    }
    *v3 = v48 + v51;
LABEL_24:
    v12 = v5;
    v7 = v47;
    v11 = v60;
    v5 = v49;
    goto LABEL_25;
  }
  v12 = (_DWORD *)(a1 + 40);
  v11 = (_QWORD *)(a1 + 16);
LABEL_29:
  v55 = *(_WORD *)(v8 + 1024);
  v56 = *(unsigned __int16 *)(v8 + 1026);
  v57 = *v3;
  v58 = *(_WORD *)v4 | (v55 << *v3);
  *(_WORD *)v4 = v58;
  if ( v57 <= 16 - v56 )
  {
    result = (unsigned int)(v57 + v56);
    *v3 = result;
  }
  else
  {
    *(_BYTE *)((unsigned int)(*v12)++ + *v11) = v58;
    *(_BYTE *)((unsigned int)*v12 + *v11) = *(_BYTE *)(v4 + 1);
    result = (unsigned int)*v3;
    ++*v12;
    *(_WORD *)v4 = v55 >> (16 - result);
    *v3 = v56 + result - 16;
  }
  return result;
}

```

## disassembly

```asm
0x180008b00  mov     [rsp+arg_10], r8
0x180008b05  mov     [rsp+arg_8], rdx
0x180008b0a  push    rbx
0x180008b0b  push    rsi
0x180008b0c  push    r13
0x180008b0e  push    r15
0x180008b10  sub     rsp, 38h
0x180008b14  mov     [rsp+58h+var_30], rdi
0x180008b19  lea     r11, [rcx+1710h]
0x180008b20  mov     [rsp+58h+var_38], r12
0x180008b25  lea     r10, [rcx+170Ch]
0x180008b2c  mov     [rsp+58h+var_40], r14
0x180008b31  lea     rax, [rcx+28h]
0x180008b35  xor     r14d, r14d
0x180008b38  lea     rdi, [rcx+10h]
0x180008b3c  mov     r12, rdx
0x180008b3f  mov     rbx, rcx
0x180008b42  mov     r15d, 10h
0x180008b48  cmp     [rcx+16F4h], r14d
0x180008b4f  jz      loc_180008E8E
0x180008b55  mov     [rsp+58h+var_28], rbp
0x180008b5a  nop     word ptr [rax+rax+00h]
0x180008b60  mov     r9, [rbx+16E8h]
0x180008b67  mov     r13, rdi
0x180008b6a  mov     [rsp+58h+var_58], rdi
0x180008b6e  mov     rsi, rax
0x180008b71  mov     [rsp+58h+arg_18], rax
0x180008b76  movzx   r8d, byte ptr [r14+r9]
0x180008b7b  inc     r14d
0x180008b7e  movzx   edx, byte ptr [r14+r9]
0x180008b83  inc     r14d
0x180008b86  shl     edx, 8
0x180008b89  add     edx, r8d
0x180008b8c  mov     dword ptr [rsp+58h+arg_0], edx
0x180008b90  movzx   ebp, byte ptr [r14+r9]
0x180008b95  inc     r14d
0x180008b98  test    edx, edx
0x180008b9a  jnz     loc_180008C27
0x180008ba0  mov     ecx, [r11]
0x180008ba3  mov     eax, r15d
0x180008ba6  movzx   r9d, word ptr [r12+rbp*4]
0x180008bab  movzx   edi, word ptr [r12+rbp*4+2]
0x180008bb1  movzx   r8d, r9w
0x180008bb5  shl     r8w, cl
0x180008bb9  sub     eax, edi
0x180008bbb  or      r8w, [r10]
0x180008bbf  cmp     ecx, eax
0x180008bc1  jle     short loc_180008C0C
0x180008bc3  mov     ecx, [rbx+28h]
0x180008bc6  mov     rax, [rbx+10h]
0x180008bca  mov     [r10], r8w
0x180008bce  mov     [rcx+rax], r8b
0x180008bd2  inc     dword ptr [rbx+28h]
0x180008bd5  mov     edx, [rbx+28h]
0x180008bd8  movzx   eax, byte ptr [r10+1]
0x180008bdd  mov     rcx, [rbx+10h]
0x180008be1  mov     [rdx+rcx], al
0x180008be4  mov     ecx, r15d
0x180008be7  mov     eax, [r11]
0x180008bea  sub     cl, al
0x180008bec  inc     dword ptr [rbx+28h]
0x180008bef  lea     edx, [rax-10h]
0x180008bf2  add     edx, edi
0x180008bf4  lea     rax, [rbx+28h]
0x180008bf8  shr     r9w, cl
0x180008bfc  lea     rdi, [rbx+10h]
0x180008c00  mov     [r10], r9w
0x180008c04  mov     [r11], edx
0x180008c07  jmp     loc_180008E7A
0x180008c0c  lea     edx, [rcx+rdi]
0x180008c0f  mov     [r10], r8w
0x180008c13  mov     [r11], edx
0x180008c16  lea     rax, [rbx+28h]
0x180008c1a  movzx   r9d, r8w
0x180008c1e  lea     rdi, [rbx+10h]
0x180008c22  jmp     loc_180008E7A
0x180008c27  mov     r8d, [r11]
0x180008c2a  lea     rcx, __ImageBase
0x180008c31  movzx   r13d, ds:rva _length_code[rcx+rbp]
0x180008c3a  lea     ecx, [r13+101h]
0x180008c41  movzx   r9d, word ptr [r12+rcx*4]
0x180008c46  movzx   esi, word ptr [r12+rcx*4+2]
0x180008c4c  movzx   edx, r9w
0x180008c50  mov     ecx, r8d
0x180008c53  shl     dx, cl
0x180008c56  mov     ecx, r15d
0x180008c59  or      dx, [r10]
0x180008c5d  sub     ecx, esi
0x180008c5f  cmp     r8d, ecx
0x180008c62  jle     short loc_180008CA0
0x180008c64  mov     rcx, [rdi]
0x180008c67  movzx   r8d, dx
0x180008c6b  mov     [r10], dx
0x180008c6f  mov     edx, [rax]
0x180008c71  mov     [rdx+rcx], r8b
0x180008c75  inc     dword ptr [rax]
0x180008c77  mov     r8d, [rax]
0x180008c7a  mov     rdx, [rdi]
0x180008c7d  movzx   ecx, byte ptr [r10+1]
0x180008c82  mov     [r8+rdx], cl
0x180008c86  mov     edx, r15d
0x180008c89  mov     ecx, [r11]
0x180008c8c  sub     dl, cl
0x180008c8e  inc     dword ptr [rax]
0x180008c90  lea     r8d, [rcx-10h]
0x180008c94  movzx   ecx, dl
0x180008c97  add     r8d, esi
0x180008c9a  shr     r9w, cl
0x180008c9e  jmp     short loc_180008CA7
0x180008ca0  add     r8d, esi
0x180008ca3  movzx   r9d, dx
0x180008ca7  mov     rcx, r13
0x180008caa  mov     [r10], r9w
0x180008cae  lea     r13, __ImageBase
0x180008cb5  mov     [r11], r8d
0x180008cb8  mov     r12d, ds:rva dword_18003E460[r13+rcx*4]
0x180008cc0  test    r12d, r12d
0x180008cc3  jz      short loc_180008D2D
0x180008cc5  sub     bp, ds:rva word_18003EAD0[r13+rcx*4]
0x180008cce  mov     ecx, r8d
0x180008cd1  movzx   esi, bp
0x180008cd4  shl     si, cl
0x180008cd7  mov     ecx, r15d
0x180008cda  or      si, r9w
0x180008cde  sub     ecx, r12d
0x180008ce1  mov     [r10], si
0x180008ce5  cmp     r8d, ecx
0x180008ce8  jle     short loc_180008D22
0x180008cea  mov     edx, [rax]
0x180008cec  mov     rcx, [rdi]
0x180008cef  mov     [rdx+rcx], sil
0x180008cf3  inc     dword ptr [rax]
0x180008cf5  mov     r8d, [rax]
0x180008cf8  movzx   ecx, byte ptr [r10+1]
0x180008cfd  mov     rdx, [rdi]
0x180008d00  mov     [r8+rdx], cl
0x180008d04  mov     ecx, r15d
0x180008d07  mov     r8d, [r11]
0x180008d0a  sub     cl, r8b
0x180008d0d  inc     dword ptr [rax]
0x180008d0f  add     r8d, 0FFFFFFF0h
0x180008d13  shr     bp, cl
0x180008d16  add     r8d, r12d
0x180008d19  mov     [r10], bp
0x180008d1d  mov     [r11], r8d
0x180008d20  jmp     short loc_180008D31
0x180008d22  add     r8d, r12d
0x180008d25  movzx   ebp, si
0x180008d28  mov     [r11], r8d
0x180008d2b  jmp     short loc_180008D31
0x180008d2d  movzx   ebp, r9w
0x180008d31  mov     esi, dword ptr [rsp+58h+arg_0]
0x180008d35  dec     esi
0x180008d37  mov     ecx, esi
0x180008d39  cmp     esi, 100h
0x180008d3f  jb      short loc_180008D4A
0x180008d41  shr     ecx, 7
0x180008d44  add     ecx, 100h
0x180008d4a  mov     edx, ecx
0x180008d4c  movzx   edx, byte ptr [rdx+r13+3E260h]
0x180008d55  lea     rcx, ds:0[rdx*4]
0x180008d5d  mov     rdx, [rsp+58h+arg_10]
0x180008d62  mov     [rsp+58h+arg_0], rcx
0x180008d67  movzx   r12d, word ptr [rcx+rdx+2]
0x180008d6d  movzx   r9d, word ptr [rcx+rdx]
0x180008d72  mov     edx, r15d
0x180008d75  sub     edx, r12d
0x180008d78  mov     ecx, r8d
0x180008d7b  cmp     r8d, edx
0x180008d7e  jle     short loc_180008DCA
0x180008d80  mov     edx, [rax]
0x180008d82  movzx   r8d, r9w
0x180008d86  shl     r8w, cl
0x180008d8a  add     r12d, 0FFFFFFF0h
0x180008d8e  mov     rcx, [rdi]
0x180008d91  or      r8w, bp
0x180008d95  mov     [r10], r8w
0x180008d99  mov     r13, rdi
0x180008d9c  mov     [rdx+rcx], r8b
0x180008da0  inc     dword ptr [rax]
0x180008da2  mov     rdx, [rdi]
0x180008da5  mov     r8d, [rax]
0x180008da8  movzx   ecx, byte ptr [r10+1]
0x180008dad  mov     [r8+rdx], cl
0x180008db1  mov     edx, r15d
0x180008db4  mov     ecx, [r11]
0x180008db7  add     r12d, ecx
0x180008dba  inc     dword ptr [rax]
0x180008dbc  sub     dl, cl
0x180008dbe  movzx   ecx, dl
0x180008dc1  mov     rdx, rax
0x180008dc4  shr     r9w, cl
0x180008dc8  jmp     short loc_180008DDD
0x180008dca  add     r12d, r8d
0x180008dcd  shl     r9w, cl
0x180008dd1  or      r9w, bp
0x180008dd5  lea     rdx, [rbx+28h]
0x180008dd9  lea     r13, [rbx+10h]
0x180008ddd  mov     rcx, [rsp+58h+arg_0]
0x180008de2  lea     r8, __ImageBase
0x180008de9  mov     [r10], r9w
0x180008ded  mov     [r11], r12d
0x180008df0  mov     ebp, [rcx+r8+3E4E0h]
0x180008df8  test    ebp, ebp
0x180008dfa  jz      short loc_180008E66
0x180008dfc  sub     si, [rcx+r8+3EB50h]
0x180008e05  mov     ecx, r12d
0x180008e08  movzx   r8d, si
0x180008e0c  shl     r8w, cl
0x180008e10  mov     ecx, r15d
0x180008e13  or      r8w, r9w
0x180008e17  sub     ecx, ebp
0x180008e19  mov     [r10], r8w
0x180008e1d  cmp     r12d, ecx
0x180008e20  jle     short loc_180008E5F
0x180008e22  mov     edx, [rax]
0x180008e24  mov     r13, rdi
0x180008e27  mov     rcx, [rdi]
0x180008e2a  mov     [rdx+rcx], r8b
0x180008e2e  inc     dword ptr [rax]
0x180008e30  mov     r8d, [rax]
0x180008e33  movzx   ecx, byte ptr [r10+1]
0x180008e38  mov     rdx, [rdi]
0x180008e3b  mov     [r8+rdx], cl
0x180008e3f  mov     ecx, r15d
0x180008e42  mov     r8d, [r11]
0x180008e45  sub     cl, r8b
0x180008e48  inc     dword ptr [rax]
0x180008e4a  shr     si, cl
0x180008e4d  lea     ecx, [rbp-10h]
0x180008e50  add     ecx, r8d
0x180008e53  mov     [r10], si
0x180008e57  mov     [r11], ecx
0x180008e5a  mov     rsi, rax
0x180008e5d  jmp     short loc_180008E75
0x180008e5f  lea     eax, [r12+rbp]
0x180008e63  mov     [r11], eax
0x180008e66  mov     rsi, [rsp+58h+arg_18]
0x180008e6b  mov     rdi, r13
0x180008e6e  mov     r13, [rsp+58h+var_58]
0x180008e72  mov     rax, rdx
0x180008e75  mov     r12, [rsp+58h+arg_8]
0x180008e7a  cmp     r14d, [rbx+16F4h]
0x180008e81  jb      loc_180008B60
0x180008e87  mov     rbp, [rsp+58h+var_28]
0x180008e8c  jmp     short loc_180008E94
0x180008e8e  mov     rsi, rax
0x180008e91  mov     r13, rdi
0x180008e94  movzx   r9d, word ptr [r12+400h]
0x180008e9d  mov     eax, r15d
0x180008ea0  movzx   ebx, word ptr [r12+402h]
0x180008ea9  movzx   edx, r9w
0x180008ead  mov     ecx, [r11]
0x180008eb0  sub     eax, ebx
0x180008eb2  mov     r14, [rsp+58h+var_40]
0x180008eb7  mov     r12, [rsp+58h+var_38]
0x180008ebc  mov     rdi, [rsp+58h+var_30]
0x180008ec1  shl     dx, cl
0x180008ec4  or      dx, [r10]
0x180008ec8  mov     [r10], dx
0x180008ecc  cmp     ecx, eax
0x180008ece  jle     short loc_180008F17
0x180008ed0  mov     rax, [r13+0]
0x180008ed4  movzx   r8d, dx
0x180008ed8  mov     edx, [rsi]
0x180008eda  mov     [rdx+rax], r8b
0x180008ede  inc     dword ptr [rsi]
0x180008ee0  mov     r8d, [rsi]
0x180008ee3  mov     rdx, [r13+0]
0x180008ee7  movzx   eax, byte ptr [r10+1]
0x180008eec  mov     [r8+rdx], al
0x180008ef0  mov     eax, [r11]
0x180008ef3  sub     r15b, al
0x180008ef6  inc     dword ptr [rsi]
0x180008ef8  movzx   ecx, r15b
0x180008efc  lea     edx, [rax-10h]
0x180008eff  add     edx, ebx
0x180008f01  shr     r9w, cl
0x180008f05  mov     [r10], r9w
0x180008f09  mov     [r11], edx
0x180008f0c  add     rsp, 38h
0x180008f10  pop     r15
0x180008f12  pop     r13
0x180008f14  pop     rsi
0x180008f15  pop     rbx
0x180008f16  retn
0x180008f17  lea     eax, [rcx+rbx]
0x180008f1a  mov     [r11], eax
0x180008f1d  add     rsp, 38h
0x180008f21  pop     r15
0x180008f23  pop     r13
0x180008f25  pop     rsi
0x180008f26  pop     rbx
0x180008f27  retn
```
