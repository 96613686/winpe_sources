# huffman_decode_create

- ea: `0x14000a35c`
- end: `0x14000a56f`
- name: `huffman_decode_create`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000a1dc`

## callees

- `0x14000a35c`
- `0x140011560`
- `0x1400119c0`

## pseudocode

```c
__int64 __fastcall huffman_decode_create(__int64 a1, __int64 a2)
{
  __int64 v4; // r8
  unsigned __int64 v5; // rcx
  int v6; // edx
  int v7; // r8d
  int v8; // edx
  int v9; // ecx
  __int64 i; // rax
  int v11; // r10d
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r9
  __int64 v18; // rdx
  int v19; // r8d
  int v20; // edx
  __int64 j; // r9
  int k; // r11d
  int v23; // edx
  int v24; // r9d
  __int64 v25; // rax
  __int16 v26; // r8
  int v27; // edx
  _OWORD v29[4]; // [rsp+20h] [rbp-49h]
  _OWORD v30[4]; // [rsp+60h] [rbp-9h] BYREF

  memset(v30, 0, sizeof(v30));
  v4 = 256;
  do
  {
    --v4;
    v5 = (unsigned __int64)*(unsigned __int8 *)(a2 + v4) >> 4;
    ++*((_DWORD *)v30 + (*(_BYTE *)(a2 + v4) & 0xF));
    ++*((_DWORD *)v30 + v5);
  }
  while ( v4 );
  if ( SLODWORD(v30[0]) < 511 )
  {
    v6 = 0;
    v29[0] = v30[0];
    v29[1] = v30[1];
    v7 = 15;
    v29[2] = v30[2];
    v29[3] = v30[3];
    while ( 1 )
    {
      v8 = *((_DWORD *)v30 + v7) + v6;
      if ( (v8 & 1) != 0 )
        break;
      v6 = v8 >> 1;
      if ( !--v7 )
      {
        if ( v6 != 1 )
          return 0;
        v9 = 0;
        for ( i = 1; i != 16; ++i )
        {
          *((_DWORD *)v30 + i) += v9;
          v9 = *((_DWORD *)v30 + i);
        }
        v11 = HIDWORD(v30[3]);
        v12 = 0x2000;
        do
        {
          v13 = v12 - 16;
          v14 = *(unsigned __int8 *)(((v12 - 16LL) >> 5) + a2) >> 4;
          if ( (_DWORD)v14 )
          {
            v15 = *((int *)v30 + v14);
            *((_DWORD *)v30 + v14) = v15 - 1;
            *(_WORD *)(a1 + 2 * v15 - 2) = v13 | v14;
          }
          v12 = v13 - 16;
          v16 = (__int64)(v13 - 16) >> 5;
          v17 = *(_BYTE *)(v16 + a2) & 0xF;
          if ( (*(_BYTE *)(v16 + a2) & 0xF) != 0 )
          {
            v18 = *((int *)v30 + v17);
            *((_DWORD *)v30 + v17) = v18 - 1;
            *(_WORD *)(a1 + 2 * v18 - 2) = v12 | v17;
          }
        }
        while ( v12 );
        v19 = 2048;
        v20 = 2048;
        for ( j = 15; j != 10; --j )
        {
          for ( k = v19; v20 > k; *(_WORD *)(a1 + 2LL * v19) = v20 | 0x8000 )
          {
            v20 -= 2;
            --v19;
          }
          v23 = *((_DWORD *)v29 + j);
          while ( --v23 >= 0 )
            *(_WORD *)(a1 + 2LL * --v19) = *(_WORD *)(a1 + 2LL * --v11);
          v20 = k;
        }
        v24 = 1024;
        while ( v20 > v19 )
        {
          --v24;
          v20 -= 2;
          *(_WORD *)(a1 + 2LL * v24) = v20 | 0x8000;
        }
        while ( v11 > 0 )
        {
          v25 = (unsigned int)v11--;
          v26 = *(_WORD *)(a1 + 2 * v25 - 2);
          v27 = v24 - (1024 >> (v26 & 0xF));
          do
            *(_WORD *)(a1 + 2LL * --v24) = v26;
          while ( v24 != v27 );
        }
        return 1;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000a35c  mov     [rsp-8+arg_10], rbx
0x14000a361  push    rbp
0x14000a362  push    rsi
0x14000a363  push    rdi
0x14000a364  lea     rbp, [rsp-47h]
0x14000a369  sub     rsp, 0B0h
0x14000a370  mov     rax, cs:__security_cookie
0x14000a377  xor     rax, rsp
0x14000a37a  mov     [rbp+57h+var_20], rax
0x14000a37e  mov     rdi, rdx
0x14000a381  mov     rbx, rcx
0x14000a384  xor     edx, edx; Val
0x14000a386  lea     rcx, [rbp+57h+var_60]; void *
0x14000a38a  lea     r8d, [rdx+40h]; Size
0x14000a38e  call    memset
0x14000a393  mov     r8d, 100h
0x14000a399  mov     esi, 1
0x14000a39e  dec     r8
0x14000a3a1  movzx   ecx, byte ptr [rdi+r8]
0x14000a3a6  mov     eax, ecx
0x14000a3a8  shr     rcx, 4
0x14000a3ac  and     eax, 0Fh
0x14000a3af  add     dword ptr [rbp+rax*4+57h+var_60], esi
0x14000a3b3  add     dword ptr [rbp+rcx*4+57h+var_60], esi
0x14000a3b7  test    r8, r8
0x14000a3ba  jnz     short loc_14000A39E
0x14000a3bc  cmp     dword ptr [rbp+57h+var_60], 1FFh
0x14000a3c3  jge     loc_14000A56B
0x14000a3c9  movaps  xmm0, [rbp+57h+var_60]
0x14000a3cd  xor     edx, edx
0x14000a3cf  movaps  xmm1, [rbp+57h+var_50]
0x14000a3d3  movaps  [rbp+57h+var_A0], xmm0
0x14000a3d7  movaps  xmm0, [rbp+57h+var_40]
0x14000a3db  movaps  [rbp+57h+var_90], xmm1
0x14000a3df  lea     r8d, [rdx+0Fh]
0x14000a3e3  movaps  xmm1, [rbp+57h+var_30]
0x14000a3e7  movaps  [rbp+57h+var_80], xmm0
0x14000a3eb  movaps  [rbp+57h+var_70], xmm1
0x14000a3ef  movsxd  rax, r8d
0x14000a3f2  add     edx, dword ptr [rbp+rax*4+57h+var_60]
0x14000a3f6  test    sil, dl
0x14000a3f9  jnz     loc_14000A56B
0x14000a3ff  sar     edx, 1
0x14000a401  sub     r8d, esi
0x14000a404  jnz     short loc_14000A3EF
0x14000a406  cmp     edx, esi
0x14000a408  jnz     loc_14000A56B
0x14000a40e  xor     ecx, ecx
0x14000a410  mov     rax, rsi
0x14000a413  add     dword ptr [rbp+rax*4+57h+var_60], ecx
0x14000a417  mov     ecx, dword ptr [rbp+rax*4+57h+var_60]
0x14000a41b  add     rax, rsi
0x14000a41e  cmp     rax, 10h
0x14000a422  jnz     short loc_14000A413
0x14000a424  mov     r10d, dword ptr [rbp+57h+var_30+0Ch]
0x14000a428  mov     r8d, 2000h
0x14000a42e  movsxd  rax, r8d
0x14000a431  lea     r9d, [r8-10h]
0x14000a435  sub     rax, 10h
0x14000a439  sar     rax, 5
0x14000a43d  movzx   r8d, byte ptr [rax+rdi]
0x14000a442  shr     r8d, 4
0x14000a446  test    r8d, r8d
0x14000a449  jz      short loc_14000A462
0x14000a44b  movsxd  rdx, dword ptr [rbp+r8*4+57h+var_60]
0x14000a450  lea     eax, [rdx-1]
0x14000a453  mov     dword ptr [rbp+r8*4+57h+var_60], eax
0x14000a458  or      r8w, r9w
0x14000a45c  mov     [rbx+rdx*2-2], r8w
0x14000a462  lea     r8d, [r9-10h]
0x14000a466  movsxd  rax, r8d
0x14000a469  sar     rax, 5
0x14000a46d  movzx   r9d, byte ptr [rax+rdi]
0x14000a472  and     r9d, 0Fh
0x14000a476  jz      short loc_14000A48F
0x14000a478  movsxd  rdx, dword ptr [rbp+r9*4+57h+var_60]
0x14000a47d  lea     eax, [rdx-1]
0x14000a480  mov     dword ptr [rbp+r9*4+57h+var_60], eax
0x14000a485  or      r9w, r8w
0x14000a489  mov     [rbx+rdx*2-2], r9w
0x14000a48f  test    r8d, r8d
0x14000a492  jnz     short loc_14000A42E
0x14000a494  mov     r8d, 800h
0x14000a49a  mov     edi, 8000h
0x14000a49f  mov     edx, r8d
0x14000a4a2  mov     r9d, 0Fh
0x14000a4a8  mov     r11d, r8d
0x14000a4ab  cmp     edx, r8d
0x14000a4ae  jle     short loc_14000A4C8
0x14000a4b0  sub     edx, 2
0x14000a4b3  sub     r8d, esi
0x14000a4b6  movzx   ecx, dx
0x14000a4b9  movsxd  rax, r8d
0x14000a4bc  or      cx, di
0x14000a4bf  mov     [rbx+rax*2], cx
0x14000a4c3  cmp     edx, r11d
0x14000a4c6  jg      short loc_14000A4B0
0x14000a4c8  mov     edx, dword ptr [rbp+r9*4+57h+var_A0]
0x14000a4cd  jmp     short loc_14000A4E3
0x14000a4cf  sub     r10d, esi
0x14000a4d2  sub     r8d, esi
0x14000a4d5  movsxd  rax, r10d
0x14000a4d8  movsxd  rcx, r8d
0x14000a4db  movzx   eax, word ptr [rbx+rax*2]
0x14000a4df  mov     [rbx+rcx*2], ax
0x14000a4e3  sub     edx, esi
0x14000a4e5  jns     short loc_14000A4CF
0x14000a4e7  dec     r9
0x14000a4ea  mov     edx, r11d
0x14000a4ed  cmp     r9, 0Ah
0x14000a4f1  jnz     short loc_14000A4A8
0x14000a4f3  mov     r11d, 400h
0x14000a4f9  mov     r9d, r11d
0x14000a4fc  jmp     short loc_14000A511
0x14000a4fe  sub     r9d, esi
0x14000a501  sub     edx, 2
0x14000a504  movsxd  rax, r9d
0x14000a507  movzx   ecx, dx
0x14000a50a  or      cx, di
0x14000a50d  mov     [rbx+rax*2], cx
0x14000a511  cmp     edx, r8d
0x14000a514  jg      short loc_14000A4FE
0x14000a516  jmp     short loc_14000A544
0x14000a518  mov     eax, r10d
0x14000a51b  mov     edx, r9d
0x14000a51e  sub     r10d, esi
0x14000a521  movzx   r8d, word ptr [rbx+rax*2-2]
0x14000a527  mov     eax, r11d
0x14000a52a  mov     ecx, r8d
0x14000a52d  and     ecx, 0Fh
0x14000a530  sar     eax, cl
0x14000a532  sub     edx, eax
0x14000a534  sub     r9d, esi
0x14000a537  movsxd  rcx, r9d
0x14000a53a  mov     [rbx+rcx*2], r8w
0x14000a53f  cmp     r9d, edx
0x14000a542  jnz     short loc_14000A534
0x14000a544  test    r10d, r10d
0x14000a547  jg      short loc_14000A518
0x14000a549  mov     eax, esi
0x14000a54b  mov     rcx, [rbp+57h+var_20]
0x14000a54f  xor     rcx, rsp; StackCookie
0x14000a552  call    __security_check_cookie
0x14000a557  mov     rbx, [rsp+0C0h+arg_10]
0x14000a55f  add     rsp, 0B0h
0x14000a566  pop     rdi
0x14000a567  pop     rsi
0x14000a568  pop     rbp
0x14000a569  retn
0x14000a56b  xor     eax, eax
0x14000a56d  jmp     short loc_14000A54B
```
