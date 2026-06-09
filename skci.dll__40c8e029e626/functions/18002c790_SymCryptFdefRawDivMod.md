# SymCryptFdefRawDivMod

- ea: `0x18002c790`
- end: `0x18002c9f0`
- name: `SymCryptFdefRawDivMod`
- size: `608`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, void *, __int64, void *)`
- caller_count: `13`
- callee_count: `4`
- tags: ``

## callers

- `0x180022c8c`
- `0x180024be8`
- `0x1800255cc`
- `0x180025888`
- `0x180026024`
- `0x180026108`
- `0x180027604`
- `0x180028790`
- `0x180028e98`
- `0x180029120`
- `0x18002b580`
- `0x18002ba40`
- `0x18002bcd0`

## callees

- `0x1800041f0`
- `0x180009780`
- `0x18002c790`
- `0x18003392c`

## pseudocode

```c
__int64 __fastcall SymCryptFdefRawDivMod(void *Src, int a2, _DWORD *a3, __int64 a4, char *a5, _QWORD *a6)
{
  unsigned __int64 v7; // rdi
  int v9; // ebp
  __int64 v11; // rsi
  __int64 result; // rax
  unsigned int v13; // ebp
  char *v14; // rcx
  _QWORD *v15; // r12
  int v16; // r15d
  __int64 v17; // rsi
  int v18; // r11d
  char v19; // r13
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // r11
  __int64 v24; // r10
  __int64 v25; // rdx
  unsigned __int64 v26; // rax
  unsigned __int64 v27; // rdx
  unsigned int v28; // r8d
  unsigned __int64 v29; // rcx
  unsigned __int64 v30; // r9
  __int64 v31; // rcx
  char *v32; // r10
  unsigned int v33; // r15d
  unsigned __int64 v34; // r9
  unsigned __int64 v35; // rcx
  unsigned __int64 v36; // rcx
  __int64 v37; // rdx
  unsigned __int64 v38; // r11
  int v39; // r11d

  v7 = ((unsigned __int64)(unsigned int)a3[3] + 31) >> 5;
  v9 = a3[1] << 6 >> 2;
  v11 = (unsigned int)(16 * a2);
  if ( (unsigned int)v11 >= (unsigned int)v7 )
  {
    v15 = a6;
    *a6 = 0;
    memcpy_0(a6 + 1, Src, 4LL * (unsigned int)v11);
    *((_DWORD *)a6 + (unsigned int)(v11 + 3)) = 0;
    *((_DWORD *)a6 + (unsigned int)(v11 + 2)) = 0;
    v16 = -a3[3] & 0x1F;
    v17 = (unsigned int)(v11 - v7 + 1);
    if ( a4 )
      SymCryptWipeAsm(a4 + 4 * v17, 4LL * (unsigned int)(v7 - 1));
    v18 = v7 + 2;
    v19 = 32 - v16;
    do
    {
      v20 = (unsigned int)a3[6];
      v21 = *((unsigned int *)v15 + (unsigned int)(v7 + v17));
      v17 = (unsigned int)(v17 - 1);
      v22 = (unsigned int)(v18 + v17);
      v23 = 0;
      v24 = (unsigned int)((((unsigned __int64)(unsigned int)v21 << 32)
                          + *((unsigned int *)v15 + (unsigned int)(v17 + v7))) >> v19);
      v25 = *((unsigned int *)v15 + v22);
      v26 = v20 + 0x100000000LL;
      v27 = (unsigned __int64)(v21 + (v25 << 32)) >> v19;
      v28 = 0;
      v29 = (v20 >> 1) & -((unsigned int)v24 >> 31);
      v30 = 0;
      v31 = v24 + v26 * (unsigned int)v27 + v29;
      v32 = (char *)v15 + 4 * (unsigned int)(v17 + 2);
      v33 = HIDWORD(v31) + 1 + ~((unsigned __int64)-(__int64)(unsigned int)(HIDWORD(v31) + 1) >> 32);
      if ( (_DWORD)v7 )
      {
        do
        {
          v34 = v33 * (unsigned __int64)(unsigned int)a3[v23 + 16] + v30;
          v35 = *(unsigned int *)&v32[4 * v23] - (unsigned __int64)(unsigned int)v34;
          v30 = HIDWORD(v34);
          v36 = v35 - v28;
          *(_DWORD *)&v32[4 * v23] = v36;
          v23 = (unsigned int)(v23 + 1);
          v28 = BYTE4(v36) & 1;
        }
        while ( (unsigned int)v23 < (unsigned int)v7 );
        v15 = a6;
      }
      v37 = (unsigned int)v23;
      v38 = *(unsigned int *)&v32[4 * v23] - (unsigned __int64)v28 - v30;
      *(_DWORD *)&v32[4 * v37] = v38;
      result = SymCryptFdefRawMaskedAddSubdigit(v32, a3 + 16, -(BYTE4(v38) & 1), (unsigned int)v7);
      if ( a4 )
        *(_DWORD *)(a4 + 4 * v17) = v33 - v39;
      v18 = v7 + 2;
    }
    while ( (_DWORD)v17 );
    if ( a5 )
    {
      memcpy_0(a5, a6 + 1, 4LL * (unsigned int)v7);
      v13 = v9 - v7;
      v14 = &a5[4 * (unsigned int)v7];
      return SymCryptWipeAsm((__int64)v14, 4LL * v13);
    }
  }
  else
  {
    if ( a4 )
      result = SymCryptWipeAsm(a4, (unsigned int)(a2 << 6));
    if ( a5 )
    {
      memcpy_0(a5, Src, 4 * v11);
      v13 = v9 - v11;
      v14 = &a5[4 * v11];
      return SymCryptWipeAsm((__int64)v14, 4LL * v13);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002c790  mov     [rsp+arg_0], rbx
0x18002c795  push    rbp
0x18002c796  push    rsi
0x18002c797  push    rdi
0x18002c798  push    r12
0x18002c79a  push    r13
0x18002c79c  push    r14
0x18002c79e  push    r15
0x18002c7a0  sub     rsp, 20h
0x18002c7a4  mov     edi, [r8+0Ch]
0x18002c7a8  mov     esi, edx
0x18002c7aa  mov     ebp, [r8+4]
0x18002c7ae  add     rdi, 1Fh
0x18002c7b2  shl     ebp, 6
0x18002c7b5  mov     rbx, r9
0x18002c7b8  shr     rdi, 5
0x18002c7bc  mov     r14, r8
0x18002c7bf  shr     ebp, 2
0x18002c7c2  mov     r15, rcx
0x18002c7c5  shl     esi, 4
0x18002c7c8  cmp     esi, edi
0x18002c7ca  jnb     short loc_18002C80E
0x18002c7cc  test    rbx, rbx
0x18002c7cf  jz      short loc_18002C7DC
0x18002c7d1  shl     edx, 6
0x18002c7d4  mov     rcx, rbx
0x18002c7d7  call    SymCryptWipeAsm
0x18002c7dc  mov     rdi, [rsp+58h+arg_20]
0x18002c7e4  test    rdi, rdi
0x18002c7e7  jz      loc_18002C9DA
0x18002c7ed  lea     rbx, ds:0[rsi*4]
0x18002c7f5  mov     rdx, r15; Src
0x18002c7f8  mov     r8, rbx; MaxCount
0x18002c7fb  mov     rcx, rdi; void *
0x18002c7fe  call    memcpy_0
0x18002c803  sub     ebp, esi
0x18002c805  lea     rcx, [rbx+rdi]
0x18002c809  jmp     loc_18002C9CF
0x18002c80e  mov     r12, [rsp+58h+arg_28]
0x18002c816  mov     rdx, r15; Src
0x18002c819  mov     r8d, esi
0x18002c81c  shl     r8, 2; MaxCount
0x18002c820  lea     rax, [r12+8]
0x18002c825  mov     qword ptr [r12], 0
0x18002c82d  mov     rcx, rax; void *
0x18002c830  mov     [rsp+58h+Src], rax
0x18002c838  call    memcpy_0
0x18002c83d  lea     eax, [rsi+3]
0x18002c840  mov     dword ptr [r12+rax*4], 0
0x18002c848  lea     eax, [rsi+2]
0x18002c84b  sub     esi, edi
0x18002c84d  mov     dword ptr [r12+rax*4], 0
0x18002c855  mov     r15d, [r14+0Ch]
0x18002c859  neg     r15d
0x18002c85c  and     r15d, 1Fh
0x18002c860  inc     esi
0x18002c862  test    rbx, rbx
0x18002c865  jz      short loc_18002C877
0x18002c867  lea     edx, [rdi-1]
0x18002c86a  shl     rdx, 2
0x18002c86e  lea     rcx, [rbx+rsi*4]
0x18002c872  call    SymCryptWipeAsm
0x18002c877  mov     r13d, 20h ; ' '
0x18002c87d  lea     r11d, [rdi+2]
0x18002c881  sub     r13d, r15d
0x18002c884  mov     [rsp+58h+arg_8], r11d
0x18002c889  mov     r9d, [r14+18h]
0x18002c88d  lea     eax, [rdi+rsi]
0x18002c890  mov     r8d, [r12+rax*4]
0x18002c894  dec     esi
0x18002c896  mov     ecx, r13d
0x18002c899  lea     eax, [rsi+rdi]
0x18002c89c  mov     r10d, [r12+rax*4]
0x18002c8a0  mov     eax, r8d
0x18002c8a3  shl     rax, 20h
0x18002c8a7  add     r10, rax
0x18002c8aa  lea     eax, [r11+rsi]
0x18002c8ae  shr     r10, cl
0x18002c8b1  xor     r11d, r11d
0x18002c8b4  mov     r10d, r10d
0x18002c8b7  mov     edx, [r12+rax*4]
0x18002c8bb  mov     rax, 100000000h
0x18002c8c5  add     rax, r9
0x18002c8c8  shl     rdx, 20h
0x18002c8cc  add     rdx, r8
0x18002c8cf  shr     r9, 1
0x18002c8d2  shr     rdx, cl
0x18002c8d5  xor     r8d, r8d
0x18002c8d8  mov     ecx, r10d
0x18002c8db  mov     edx, edx
0x18002c8dd  shr     ecx, 1Fh
0x18002c8e0  neg     ecx
0x18002c8e2  and     rcx, r9
0x18002c8e5  xor     r9d, r9d
0x18002c8e8  imul    rdx, rax
0x18002c8ec  lea     eax, [rsi+2]
0x18002c8ef  add     rcx, rdx
0x18002c8f2  add     rcx, r10
0x18002c8f5  lea     r10, [r12+rax*4]
0x18002c8f9  shr     rcx, 20h
0x18002c8fd  inc     ecx
0x18002c8ff  mov     r15d, ecx
0x18002c902  neg     r15
0x18002c905  shr     r15, 20h
0x18002c909  not     r15d
0x18002c90c  add     r15d, ecx
0x18002c90f  test    edi, edi
0x18002c911  jz      short loc_18002C955
0x18002c913  mov     r12d, r15d
0x18002c916  mov     eax, [r14+r11*4+40h]
0x18002c91b  mov     ecx, [r10+r11*4]
0x18002c91f  imul    rax, r12
0x18002c923  add     r9, rax
0x18002c926  mov     eax, r9d
0x18002c929  sub     rcx, rax
0x18002c92c  shr     r9, 20h
0x18002c930  mov     eax, r8d
0x18002c933  sub     rcx, rax
0x18002c936  mov     r8, rcx
0x18002c939  mov     [r10+r11*4], ecx
0x18002c93d  shr     r8, 20h
0x18002c941  inc     r11d
0x18002c944  and     r8d, 1
0x18002c948  cmp     r11d, edi
0x18002c94b  jb      short loc_18002C916
0x18002c94d  mov     r12, [rsp+58h+arg_28]
0x18002c955  mov     edx, r11d
0x18002c958  mov     rcx, r10
0x18002c95b  mov     r11d, [r10+r11*4]
0x18002c95f  mov     eax, r8d
0x18002c962  sub     r11, rax
0x18002c965  sub     r11, r9
0x18002c968  mov     r9d, edi
0x18002c96b  mov     [r10+rdx*4], r11d
0x18002c96f  lea     rdx, [r14+40h]
0x18002c973  shr     r11, 20h
0x18002c977  and     r11d, 1
0x18002c97b  mov     r8d, r11d
0x18002c97e  neg     r8d
0x18002c981  call    SymCryptFdefRawMaskedAddSubdigit
0x18002c986  test    rbx, rbx
0x18002c989  jz      short loc_18002C992
0x18002c98b  sub     r15d, r11d
0x18002c98e  mov     [rbx+rsi*4], r15d
0x18002c992  mov     r11d, [rsp+58h+arg_8]
0x18002c997  test    esi, esi
0x18002c999  jnz     loc_18002C889
0x18002c99f  mov     rsi, [rsp+58h+arg_20]
0x18002c9a7  test    rsi, rsi
0x18002c9aa  jz      short loc_18002C9DA
0x18002c9ac  mov     rdx, [rsp+58h+Src]; Src
0x18002c9b4  mov     rcx, rsi; void *
0x18002c9b7  mov     eax, edi
0x18002c9b9  lea     rbx, ds:0[rax*4]
0x18002c9c1  mov     r8, rbx; MaxCount
0x18002c9c4  call    memcpy_0
0x18002c9c9  sub     ebp, edi
0x18002c9cb  lea     rcx, [rbx+rsi]
0x18002c9cf  mov     edx, ebp
0x18002c9d1  shl     rdx, 2
0x18002c9d5  call    SymCryptWipeAsm
0x18002c9da  mov     rbx, [rsp+58h+arg_0]
0x18002c9df  add     rsp, 20h
0x18002c9e3  pop     r15
0x18002c9e5  pop     r14
0x18002c9e7  pop     r13
0x18002c9e9  pop     r12
0x18002c9eb  pop     rdi
0x18002c9ec  pop     rsi
0x18002c9ed  pop     rbp
0x18002c9ee  retn
```
