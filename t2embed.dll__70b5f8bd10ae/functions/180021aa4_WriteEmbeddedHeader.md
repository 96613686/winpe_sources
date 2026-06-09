# WriteEmbeddedHeader

- ea: `0x180021aa4`
- end: `0x180021d4d`
- name: `WriteEmbeddedHeader`
- size: `681`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x1800205bc`
- `0x180020784`
- `0x18002089c`
- `0x180020c40`

## callees

- `0x180017ee0`
- `0x180019dc0`
- `0x18001ac80`
- `0x18001bff0`
- `0x180021aa4`
- `0x18002a54e`

## pseudocode

```c
__int64 __fastcall WriteEmbeddedHeader(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rax
  char *v7; // rsi
  __int64 v9; // rdx
  __int64 v10; // rdx
  int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rdx
  int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // ebx
  __int64 v18; // rdx
  __int64 v19; // rdx
  int v20; // ebx
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rdx
  int v28; // r15d
  unsigned int v29; // edi
  int FontData; // ebx

  v6 = T2malloc((unsigned int)(*(_DWORD *)a3 - *(_DWORD *)(a3 + 4)));
  v7 = (char *)v6;
  if ( !v6 )
    return 266;
  *(_DWORD *)v6 = *(_DWORD *)a3;
  *(_DWORD *)(v6 + 4) = *(_DWORD *)(a3 + 4);
  *(_DWORD *)(v6 + 8) = *(_DWORD *)(a3 + 8);
  *(_DWORD *)(v6 + 12) = *(_DWORD *)(a3 + 12);
  *(_QWORD *)(v6 + 16) = *(_QWORD *)(a3 + 16);
  *(_WORD *)(v6 + 24) = *(_WORD *)(a3 + 24);
  *(_BYTE *)(v6 + 26) = *(_BYTE *)(a3 + 26);
  *(_BYTE *)(v6 + 27) = *(_BYTE *)(a3 + 27);
  *(_DWORD *)(v6 + 28) = *(_DWORD *)(a3 + 28);
  *(_WORD *)(v6 + 32) = *(_WORD *)(a3 + 32);
  *(_WORD *)(v6 + 34) = *(_WORD *)(a3 + 34);
  *(_DWORD *)(v6 + 36) = *(_DWORD *)(a3 + 36);
  *(_DWORD *)(v6 + 40) = *(_DWORD *)(a3 + 40);
  *(_DWORD *)(v6 + 44) = *(_DWORD *)(a3 + 44);
  *(_DWORD *)(v6 + 48) = *(_DWORD *)(a3 + 48);
  *(_DWORD *)(v6 + 52) = *(_DWORD *)(a3 + 52);
  *(_DWORD *)(v6 + 56) = *(_DWORD *)(a3 + 56);
  *(_DWORD *)(v6 + 60) = *(_DWORD *)(a3 + 60);
  *(_DWORD *)(v6 + 64) = *(_DWORD *)(a3 + 64);
  *(_DWORD *)(v6 + 68) = *(_DWORD *)(a3 + 68);
  *(_DWORD *)(v6 + 72) = *(_DWORD *)(a3 + 72);
  *(_DWORD *)(v6 + 76) = *(_DWORD *)(a3 + 76);
  *(_WORD *)(v6 + 80) = *(_WORD *)(a3 + 80);
  *(_WORD *)(v6 + 82) = *(_WORD *)(a3 + 82);
  memcpy_0((void *)(v6 + 84), *(const void **)(a3 + 88), *(unsigned __int16 *)(a3 + 82));
  v9 = (unsigned int)*(unsigned __int16 *)(a3 + 82) + 84;
  *(_WORD *)&v7[v9] = *(_WORD *)(a3 + 96);
  v10 = (unsigned int)(v9 + 2);
  v11 = v10 + 2;
  *(_WORD *)&v7[v10] = *(_WORD *)(a3 + 98);
  memcpy_0(&v7[(unsigned int)(v10 + 2)], *(const void **)(a3 + 104), *(unsigned __int16 *)(a3 + 98));
  v12 = v11 + (unsigned int)*(unsigned __int16 *)(a3 + 98);
  *(_WORD *)&v7[v12] = *(_WORD *)(a3 + 112);
  v13 = (unsigned int)(v12 + 2);
  v14 = v13 + 2;
  *(_WORD *)&v7[v13] = *(_WORD *)(a3 + 114);
  memcpy_0(&v7[(unsigned int)(v13 + 2)], *(const void **)(a3 + 120), *(unsigned __int16 *)(a3 + 114));
  v15 = v14 + (unsigned int)*(unsigned __int16 *)(a3 + 114);
  *(_WORD *)&v7[v15] = *(_WORD *)(a3 + 128);
  v16 = (unsigned int)(v15 + 2);
  v17 = v16 + 2;
  *(_WORD *)&v7[v16] = *(_WORD *)(a3 + 130);
  memcpy_0(&v7[(unsigned int)(v16 + 2)], *(const void **)(a3 + 136), *(unsigned __int16 *)(a3 + 130));
  v18 = v17 + (unsigned int)*(unsigned __int16 *)(a3 + 130);
  *(_WORD *)&v7[v18] = *(_WORD *)(a3 + 144);
  v19 = (unsigned int)(v18 + 2);
  v20 = v19 + 2;
  *(_WORD *)&v7[v19] = *(_WORD *)(a3 + 146);
  memcpy_0(&v7[(unsigned int)(v19 + 2)], *(const void **)(a3 + 152), *(unsigned __int16 *)(a3 + 146));
  v21 = v20 + (unsigned int)*(unsigned __int16 *)(a3 + 146);
  *(_DWORD *)&v7[v21] = *(_DWORD *)(a3 + 160);
  v22 = (unsigned int)(v21 + 4);
  *(_DWORD *)&v7[v22] = *(_DWORD *)(a3 + 164);
  v23 = (unsigned int)(v22 + 4);
  *(_WORD *)&v7[v23] = *(_WORD *)(a3 + 168);
  v24 = (unsigned int)(v23 + 2);
  v25 = v24 + 2;
  *(_WORD *)&v7[v24] = *(_WORD *)(a3 + 170);
  memcpy_0(&v7[(unsigned int)(v24 + 2)], *(const void **)(a3 + 176), *(unsigned __int16 *)(a3 + 170));
  v26 = v25 + (unsigned int)*(unsigned __int16 *)(a3 + 170);
  *(_DWORD *)&v7[v26] = *(_DWORD *)(a3 + 184);
  v27 = (unsigned int)(v26 + 4);
  v28 = v27 + 4;
  *(_DWORD *)&v7[v27] = *(_DWORD *)(a3 + 188);
  memcpy_0(&v7[(unsigned int)(v27 + 4)], *(const void **)(a3 + 192), *(unsigned int *)(a3 + 188));
  if ( (*(_DWORD *)(a3 + 184) & 0x10000000) != 0 )
    XORBufferData(&v7[v28], *(unsigned int *)(a3 + 188));
  v29 = v28 + *(_DWORD *)(a3 + 188);
  FontData = T2OSSvcReadFontData(a1, a2, v7, v29);
  T2free(v7);
  return v29 != FontData ? 0x108 : 0;
}

```

## disassembly

```asm
0x180021aa4  push    rbx
0x180021aa6  push    rbp
0x180021aa7  push    rsi
0x180021aa8  push    rdi
0x180021aa9  push    r14
0x180021aab  push    r15
0x180021aad  sub     rsp, 38h
0x180021ab1  mov     r14, rcx
0x180021ab4  mov     rbp, rdx
0x180021ab7  mov     ecx, [r8]
0x180021aba  mov     edx, 1
0x180021abf  sub     ecx, [r8+4]; dwBytes
0x180021ac3  mov     rdi, r8
0x180021ac6  call    T2malloc
0x180021acb  mov     rsi, rax
0x180021ace  test    rax, rax
0x180021ad1  jnz     short loc_180021ADD
0x180021ad3  mov     eax, 10Ah
0x180021ad8  jmp     loc_180021D40
0x180021add  mov     eax, [rdi]
0x180021adf  lea     rcx, [rsi+54h]; void *
0x180021ae3  mov     [rsi], eax
0x180021ae5  mov     eax, [rdi+4]
0x180021ae8  mov     [rsi+4], eax
0x180021aeb  mov     eax, [rdi+8]
0x180021aee  mov     [rsi+8], eax
0x180021af1  mov     eax, [rdi+0Ch]
0x180021af4  mov     [rsi+0Ch], eax
0x180021af7  movsd   xmm0, qword ptr [rdi+10h]
0x180021afc  movsd   qword ptr [rsi+10h], xmm0
0x180021b01  movzx   eax, word ptr [rdi+18h]
0x180021b05  mov     [rsi+18h], ax
0x180021b09  mov     al, [rdi+1Ah]
0x180021b0c  mov     [rsi+1Ah], al
0x180021b0f  mov     al, [rdi+1Bh]
0x180021b12  mov     [rsi+1Bh], al
0x180021b15  mov     eax, [rdi+1Ch]
0x180021b18  mov     [rsi+1Ch], eax
0x180021b1b  movzx   eax, word ptr [rdi+20h]
0x180021b1f  mov     [rsi+20h], ax
0x180021b23  movzx   eax, word ptr [rdi+22h]
0x180021b27  mov     [rsi+22h], ax
0x180021b2b  mov     eax, [rdi+24h]
0x180021b2e  mov     [rsi+24h], eax
0x180021b31  mov     eax, [rdi+28h]
0x180021b34  mov     [rsi+28h], eax
0x180021b37  mov     eax, [rdi+2Ch]
0x180021b3a  mov     [rsi+2Ch], eax
0x180021b3d  mov     eax, [rdi+30h]
0x180021b40  mov     [rsi+30h], eax
0x180021b43  mov     eax, [rdi+34h]
0x180021b46  mov     [rsi+34h], eax
0x180021b49  mov     eax, [rdi+38h]
0x180021b4c  mov     [rsi+38h], eax
0x180021b4f  mov     eax, [rdi+3Ch]
0x180021b52  mov     [rsi+3Ch], eax
0x180021b55  mov     eax, [rdi+40h]
0x180021b58  mov     [rsi+40h], eax
0x180021b5b  mov     eax, [rdi+44h]
0x180021b5e  mov     [rsi+44h], eax
0x180021b61  mov     eax, [rdi+48h]
0x180021b64  mov     [rsi+48h], eax
0x180021b67  mov     eax, [rdi+4Ch]
0x180021b6a  mov     [rsi+4Ch], eax
0x180021b6d  movzx   eax, word ptr [rdi+50h]
0x180021b71  mov     [rsi+50h], ax
0x180021b75  movzx   eax, word ptr [rdi+52h]
0x180021b79  mov     [rsi+52h], ax
0x180021b7d  movzx   r8d, word ptr [rdi+52h]; Size
0x180021b82  mov     rdx, [rdi+58h]; Src
0x180021b86  call    memcpy_0
0x180021b8b  movzx   edx, word ptr [rdi+52h]
0x180021b8f  movzx   eax, word ptr [rdi+60h]
0x180021b93  add     edx, 54h ; 'T'
0x180021b96  mov     [rdx+rsi], ax
0x180021b9a  add     edx, 2
0x180021b9d  movzx   eax, word ptr [rdi+62h]
0x180021ba1  lea     ebx, [rdx+2]
0x180021ba4  mov     [rdx+rsi], ax
0x180021ba8  movzx   r8d, word ptr [rdi+62h]; Size
0x180021bad  mov     rdx, [rdi+68h]; Src
0x180021bb1  mov     ecx, ebx
0x180021bb3  add     rcx, rsi; void *
0x180021bb6  call    memcpy_0
0x180021bbb  movzx   edx, word ptr [rdi+62h]
0x180021bbf  movzx   eax, word ptr [rdi+70h]
0x180021bc3  add     edx, ebx
0x180021bc5  mov     [rdx+rsi], ax
0x180021bc9  add     edx, 2
0x180021bcc  movzx   eax, word ptr [rdi+72h]
0x180021bd0  lea     ebx, [rdx+2]
0x180021bd3  mov     [rdx+rsi], ax
0x180021bd7  movzx   r8d, word ptr [rdi+72h]; Size
0x180021bdc  mov     rdx, [rdi+78h]; Src
0x180021be0  mov     ecx, ebx
0x180021be2  add     rcx, rsi; void *
0x180021be5  call    memcpy_0
0x180021bea  movzx   edx, word ptr [rdi+72h]
0x180021bee  movzx   eax, word ptr [rdi+80h]
0x180021bf5  add     edx, ebx
0x180021bf7  mov     [rdx+rsi], ax
0x180021bfb  add     edx, 2
0x180021bfe  movzx   eax, word ptr [rdi+82h]
0x180021c05  lea     ebx, [rdx+2]
0x180021c08  mov     [rdx+rsi], ax
0x180021c0c  movzx   r8d, word ptr [rdi+82h]; Size
0x180021c14  mov     rdx, [rdi+88h]; Src
0x180021c1b  mov     ecx, ebx
0x180021c1d  add     rcx, rsi; void *
0x180021c20  call    memcpy_0
0x180021c25  movzx   edx, word ptr [rdi+82h]
0x180021c2c  movzx   eax, word ptr [rdi+90h]
0x180021c33  add     edx, ebx
0x180021c35  mov     [rdx+rsi], ax
0x180021c39  add     edx, 2
0x180021c3c  movzx   eax, word ptr [rdi+92h]
0x180021c43  lea     ebx, [rdx+2]
0x180021c46  mov     [rdx+rsi], ax
0x180021c4a  movzx   r8d, word ptr [rdi+92h]; Size
0x180021c52  mov     rdx, [rdi+98h]; Src
0x180021c59  mov     ecx, ebx
0x180021c5b  add     rcx, rsi; void *
0x180021c5e  call    memcpy_0
0x180021c63  movzx   edx, word ptr [rdi+92h]
0x180021c6a  mov     eax, [rdi+0A0h]
0x180021c70  add     edx, ebx
0x180021c72  mov     [rdx+rsi], eax
0x180021c75  add     edx, 4
0x180021c78  mov     eax, [rdi+0A4h]
0x180021c7e  mov     [rdx+rsi], eax
0x180021c81  add     edx, 4
0x180021c84  movzx   eax, word ptr [rdi+0A8h]
0x180021c8b  mov     [rdx+rsi], ax
0x180021c8f  add     edx, 2
0x180021c92  movzx   eax, word ptr [rdi+0AAh]
0x180021c99  lea     ebx, [rdx+2]
0x180021c9c  mov     [rdx+rsi], ax
0x180021ca0  movzx   r8d, word ptr [rdi+0AAh]; Size
0x180021ca8  mov     rdx, [rdi+0B0h]; Src
0x180021caf  mov     ecx, ebx
0x180021cb1  add     rcx, rsi; void *
0x180021cb4  call    memcpy_0
0x180021cb9  movzx   edx, word ptr [rdi+0AAh]
0x180021cc0  mov     eax, [rdi+0B8h]
0x180021cc6  add     edx, ebx
0x180021cc8  mov     [rdx+rsi], eax
0x180021ccb  add     edx, 4
0x180021cce  mov     eax, [rdi+0BCh]
0x180021cd4  lea     r15d, [rdx+4]
0x180021cd8  mov     [rdx+rsi], eax
0x180021cdb  mov     r8d, [rdi+0BCh]; Size
0x180021ce2  mov     rdx, [rdi+0C0h]; Src
0x180021ce9  mov     ebx, r15d
0x180021cec  add     rbx, rsi
0x180021cef  mov     rcx, rbx; void *
0x180021cf2  call    memcpy_0
0x180021cf7  test    dword ptr [rdi+0B8h], 10000000h
0x180021d01  jz      short loc_180021D11
0x180021d03  mov     edx, [rdi+0BCh]
0x180021d09  mov     rcx, rbx
0x180021d0c  call    XORBufferData
0x180021d11  mov     edi, [rdi+0BCh]
0x180021d17  mov     r8, rsi
0x180021d1a  add     edi, r15d
0x180021d1d  mov     rdx, rbp
0x180021d20  mov     r9d, edi
0x180021d23  mov     rcx, r14
0x180021d26  call    T2OSSvcReadFontData
0x180021d2b  mov     rcx, rsi; lpMem
0x180021d2e  mov     ebx, eax
0x180021d30  call    T2free
0x180021d35  sub     ebx, edi
0x180021d37  neg     ebx
0x180021d39  sbb     eax, eax
0x180021d3b  and     eax, 108h
0x180021d40  add     rsp, 38h
0x180021d44  pop     r15
0x180021d46  pop     r14
0x180021d48  pop     rdi
0x180021d49  pop     rsi
0x180021d4a  pop     rbp
0x180021d4b  pop     rbx
0x180021d4c  retn
```
