# CreateNewEventEntry

- ea: `0x140044a18`
- end: `0x140044c81`
- name: `CreateNewEventEntry`
- size: `617`
- prototype: `__int64 __fastcall(char, __int128 *, unsigned __int8, __int64, char, int, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140044e4c`

## callees

- `0x140044a18`
- `0x140045640`
- `0x140045940`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140044ac3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140044ac3`

## pseudocode

```c
__int64 __fastcall CreateNewEventEntry(
        char a1,
        __int128 *a2,
        unsigned __int8 a3,
        __int64 a4,
        char a5,
        int a6,
        _QWORD *a7)
{
  __int64 v7; // r10
  __int64 v8; // r11
  unsigned __int8 v9; // r13
  unsigned __int8 v10; // bl
  __int64 v13; // rcx
  __int64 v14; // rax
  unsigned __int64 v16; // rdi
  SIZE_T v17; // rbx
  char *PoolWithTag; // rax
  char *v19; // rbp
  int v20; // r9d
  char *v21; // rsi
  char *v22; // r15
  char v23; // dl
  unsigned __int8 v24; // r14
  unsigned __int8 v25; // bp
  __int64 v26; // r13
  size_t v27; // r8
  char *v28; // rax
  unsigned __int64 v29; // rcx
  char *v30; // rdi
  __int128 v31; // xmm0
  __int64 v32; // r15
  __int64 v33; // r14
  size_t v34; // r8
  char *v35; // rbp
  int v36; // r9d
  int v37; // [rsp+20h] [rbp-48h]
  char *v38; // [rsp+28h] [rbp-40h]

  v7 = 0;
  v8 = 0;
  v9 = a3;
  v10 = 0;
  *a7 = 0;
  if ( a3 )
  {
    do
    {
      v13 = *(unsigned int *)(a4 + 16LL * v10 + 8);
      if ( v10 >= 2u )
        v7 += v13;
      v14 = v13 + v8;
      if ( v10 >= 2u )
        v14 = v8;
      ++v10;
      v8 = v14;
    }
    while ( v10 < a3 );
    if ( (unsigned __int64)(v7 + v14) > 0xFFFF )
      return 3221225621LL;
  }
  v16 = 16LL * a3;
  v17 = v7 + v16 + 46;
  if ( !v17 )
    return 3221225495LL;
  PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(a1 != 0 ? PagedPool : NonPagedPoolNx), v17, 0x47417254u);
  v19 = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225495LL;
  memset(PoolWithTag, 0, v17);
  if ( v16 && v17 >= v16 )
  {
    v21 = &v19[v16];
    v17 -= v16;
    v22 = v19;
  }
  else
  {
    v22 = 0;
    v21 = v19;
  }
  v23 = a5;
  v24 = 0;
  v25 = a5 + 2;
  LOBYTE(v20) = a5 + 2;
  v37 = v20;
  if ( a5 != -2 )
  {
    v26 = 0;
    do
    {
      if ( v24 >= 2u )
      {
        v27 = *(unsigned int *)(a4 + 16 * v26 + 8);
        if ( *(_DWORD *)(a4 + 16 * v26 + 8) && v17 >= v27 )
        {
          v28 = v21;
          v21 += v27;
          v17 -= v27;
        }
        else
        {
          v28 = 0;
        }
        v38 = v28;
        memmove(v28, *(const void **)(a4 + 16 * v26), v27);
        *(_QWORD *)&v22[16 * v26] = v38;
        *(_DWORD *)&v22[16 * v26 + 12] = *(_DWORD *)(a4 + 16 * v26 + 12);
        *(_DWORD *)&v22[16 * v26 + 8] = *(_DWORD *)(a4 + 16 * v26 + 8);
      }
      else
      {
        *(_OWORD *)&v22[16 * v26] = *(_OWORD *)(a4 + 16 * v26);
      }
      ++v24;
      ++v26;
    }
    while ( v24 < v25 );
    v9 = a3;
    v23 = a5;
    LOBYTE(v20) = v37;
  }
  v29 = v17;
  v30 = v21;
  if ( v17 >= 0x2E )
  {
    v21 += 46;
    v17 -= 46LL;
  }
  if ( v29 < 0x2E )
    v30 = 0;
  *((_QWORD *)v30 + 2) = v22;
  v31 = *a2;
  v30[44] = v9;
  v30[45] = v23;
  *((_DWORD *)v30 + 10) = a6;
  *(_OWORD *)v30 = v31;
  if ( (unsigned __int8)v20 < v9 )
  {
    v32 = v25;
    do
    {
      v33 = 2 * v32;
      v34 = *(unsigned int *)(a4 + 16 * v32 + 8);
      if ( *(_DWORD *)(a4 + 16 * v32 + 8) && v17 >= v34 )
      {
        v35 = v21;
        v21 += v34;
        v17 -= v34;
      }
      else
      {
        v35 = 0;
      }
      memmove(v35, *(const void **)(a4 + 16 * v32++), v34);
      v36 = v37;
      LOBYTE(v36) = v37 + 1;
      v37 = v36;
      *(_QWORD *)(*((_QWORD *)v30 + 2) + 8 * v33) = v35;
      *(_DWORD *)(*((_QWORD *)v30 + 2) + 8 * v33 + 12) = *(_DWORD *)(a4 + 8 * v33 + 12);
      *(_DWORD *)(*((_QWORD *)v30 + 2) + 8 * v33 + 8) = *(_DWORD *)(a4 + 8 * v33 + 8);
    }
    while ( (unsigned __int8)v36 < v9 );
  }
  *a7 = v30;
  return 0;
}

```

## disassembly

```asm
0x140044a18  mov     [rsp+arg_0], rbx
0x140044a1d  mov     [rsp+arg_10], r8b
0x140044a22  mov     [rsp+arg_8], rdx
0x140044a27  push    rbp
0x140044a28  push    rsi
0x140044a29  push    rdi
0x140044a2a  push    r12
0x140044a2c  push    r13
0x140044a2e  push    r14
0x140044a30  push    r15
0x140044a32  sub     rsp, 30h
0x140044a36  mov     rax, [rsp+68h+arg_30]
0x140044a3e  xor     r10d, r10d
0x140044a41  xor     r11d, r11d
0x140044a44  movzx   r13d, r8b
0x140044a48  xor     bl, bl
0x140044a4a  mov     r12, r9
0x140044a4d  mov     r9b, cl
0x140044a50  mov     [rax], r10
0x140044a53  test    r8b, r8b
0x140044a56  jz      short loc_140044A95
0x140044a58  movzx   eax, bl
0x140044a5b  add     rax, rax
0x140044a5e  cmp     bl, 2
0x140044a61  mov     ecx, [r12+rax*8+8]
0x140044a66  lea     rax, [rcx+r10]
0x140044a6a  cmovnb  r10, rax
0x140044a6e  lea     rax, [rcx+r11]
0x140044a72  cmovnb  rax, r11
0x140044a76  inc     bl
0x140044a78  mov     r11, rax
0x140044a7b  cmp     bl, r13b
0x140044a7e  jb      short loc_140044A58
0x140044a80  add     rax, r10
0x140044a83  cmp     rax, 0FFFFh
0x140044a89  jbe     short loc_140044A95
0x140044a8b  mov     eax, 0C0000095h
0x140044a90  jmp     loc_140044C6B
0x140044a95  mov     rdi, r13
0x140044a98  shl     rdi, 4
0x140044a9c  lea     rbx, [rdi+2Eh]
0x140044aa0  add     rbx, r10
0x140044aa3  jz      loc_140044C66
0x140044aa9  neg     r9b
0x140044aac  mov     r8d, 47417254h; Tag
0x140044ab2  mov     rdx, rbx; NumberOfBytes
0x140044ab5  sbb     ecx, ecx
0x140044ab7  and     ecx, 0FFFFFE01h
0x140044abd  add     ecx, 200h; PoolType
0x140044ac3  call    cs:__imp_ExAllocatePoolWithTag
0x140044aca  nop     dword ptr [rax+rax+00h]
0x140044acf  mov     rbp, rax
0x140044ad2  test    rax, rax
0x140044ad5  jz      loc_140044C66
0x140044adb  mov     r8, rbx; Size
0x140044ade  xor     edx, edx; Val
0x140044ae0  mov     rcx, rax; void *
0x140044ae3  call    memset
0x140044ae8  test    rdi, rdi
0x140044aeb  jz      short loc_140044AFE
0x140044aed  cmp     rbx, rdi
0x140044af0  jb      short loc_140044AFE
0x140044af2  lea     rsi, [rdi+rbp]
0x140044af6  sub     rbx, rdi
0x140044af9  mov     r15, rbp
0x140044afc  jmp     short loc_140044B04
0x140044afe  xor     r15d, r15d
0x140044b01  mov     rsi, rbp
0x140044b04  mov     dl, [rsp+68h+arg_20]
0x140044b0b  xor     r14b, r14b
0x140044b0e  mov     bpl, dl
0x140044b11  add     bpl, 2
0x140044b15  mov     r9b, bpl
0x140044b18  mov     [rsp+68h+var_48], r9d
0x140044b1d  jz      loc_140044BA8
0x140044b23  xor     r13d, r13d
0x140044b26  mov     rdi, r13
0x140044b29  add     rdi, rdi
0x140044b2c  cmp     r14b, 2
0x140044b30  jnb     short loc_140044B3F
0x140044b32  movups  xmm0, xmmword ptr [r12+rdi*8]
0x140044b37  movdqu  xmmword ptr [r15+rdi*8], xmm0
0x140044b3d  jmp     short loc_140044B89
0x140044b3f  mov     r8d, [r12+rdi*8+8]; Size
0x140044b44  test    r8, r8
0x140044b47  jz      short loc_140044B59
0x140044b49  cmp     rbx, r8
0x140044b4c  jb      short loc_140044B59
0x140044b4e  mov     rax, rsi
0x140044b51  add     rsi, r8
0x140044b54  sub     rbx, r8
0x140044b57  jmp     short loc_140044B5B
0x140044b59  xor     eax, eax
0x140044b5b  mov     rdx, [r12+rdi*8]; Src
0x140044b5f  mov     rcx, rax; void *
0x140044b62  mov     [rsp+68h+var_40], rax
0x140044b67  call    memmove
0x140044b6c  mov     rax, [rsp+68h+var_40]
0x140044b71  mov     [r15+rdi*8], rax
0x140044b75  mov     eax, [r12+rdi*8+0Ch]
0x140044b7a  mov     [r15+rdi*8+0Ch], eax
0x140044b7f  mov     eax, [r12+rdi*8+8]
0x140044b84  mov     [r15+rdi*8+8], eax
0x140044b89  inc     r14b
0x140044b8c  inc     r13
0x140044b8f  cmp     r14b, bpl
0x140044b92  jb      short loc_140044B26
0x140044b94  mov     r13b, [rsp+68h+arg_10]
0x140044b9c  mov     dl, [rsp+68h+arg_20]
0x140044ba3  mov     r9d, [rsp+68h+var_48]
0x140044ba8  mov     rcx, rbx
0x140044bab  mov     rdi, rsi
0x140044bae  cmp     rbx, 2Eh ; '.'
0x140044bb2  jb      short loc_140044BBC
0x140044bb4  add     rsi, 2Eh ; '.'
0x140044bb8  sub     rbx, 2Eh ; '.'
0x140044bbc  xor     eax, eax
0x140044bbe  cmp     rcx, 2Eh ; '.'
0x140044bc2  cmovb   rdi, rax
0x140044bc6  mov     rax, [rsp+68h+arg_8]
0x140044bcb  mov     [rdi+10h], r15
0x140044bcf  movups  xmm0, xmmword ptr [rax]
0x140044bd2  mov     eax, [rsp+68h+arg_28]
0x140044bd9  mov     [rdi+2Ch], r13b
0x140044bdd  mov     [rdi+2Dh], dl
0x140044be0  mov     [rdi+28h], eax
0x140044be3  movdqu  xmmword ptr [rdi], xmm0
0x140044be7  cmp     r9b, r13b
0x140044bea  jnb     short loc_140044C57
0x140044bec  movzx   r15d, bpl
0x140044bf0  mov     r14, r15
0x140044bf3  add     r14, r14
0x140044bf6  mov     r8d, [r12+r14*8+8]; Size
0x140044bfb  test    r8, r8
0x140044bfe  jz      short loc_140044C10
0x140044c00  cmp     rbx, r8
0x140044c03  jb      short loc_140044C10
0x140044c05  mov     rbp, rsi
0x140044c08  add     rsi, r8
0x140044c0b  sub     rbx, r8
0x140044c0e  jmp     short loc_140044C12
0x140044c10  xor     ebp, ebp
0x140044c12  mov     rdx, [r12+r14*8]; Src
0x140044c16  mov     rcx, rbp; void *
0x140044c19  call    memmove
0x140044c1e  mov     rax, [rdi+10h]
0x140044c22  inc     r15
0x140044c25  mov     r9d, [rsp+68h+var_48]
0x140044c2a  inc     r9b
0x140044c2d  mov     [rsp+68h+var_48], r9d
0x140044c32  mov     [rax+r14*8], rbp
0x140044c36  mov     rcx, [rdi+10h]
0x140044c3a  mov     eax, [r12+r14*8+0Ch]
0x140044c3f  mov     [rcx+r14*8+0Ch], eax
0x140044c44  mov     rcx, [rdi+10h]
0x140044c48  mov     eax, [r12+r14*8+8]
0x140044c4d  mov     [rcx+r14*8+8], eax
0x140044c52  cmp     r9b, r13b
0x140044c55  jb      short loc_140044BF0
0x140044c57  mov     rax, [rsp+68h+arg_30]
0x140044c5f  mov     [rax], rdi
0x140044c62  xor     eax, eax
0x140044c64  jmp     short loc_140044C6B
0x140044c66  mov     eax, 0C0000017h
0x140044c6b  mov     rbx, [rsp+68h+arg_0]
0x140044c70  add     rsp, 30h
0x140044c74  pop     r15
0x140044c76  pop     r14
0x140044c78  pop     r13
0x140044c7a  pop     r12
0x140044c7c  pop     rdi
0x140044c7d  pop     rsi
0x140044c7e  pop     rbp
0x140044c7f  retn
```
