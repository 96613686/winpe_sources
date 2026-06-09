# RtlMemoryStream::WriteStringA(char const *,char const *)

- ea: `0x14000b35c`
- end: `0x14000b56b`
- name: `?WriteStringA@RtlMemoryStream@@QEAAJPEBD0@Z`
- size: `527`
- prototype: `__int64 __fastcall(RtlMemoryStream *this, const char *, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c540`

## callees

- `0x140002206`
- `0x14000b35c`
- `0x14002e3e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000b3ff`
- `ntdll!RtlAllocateHeap` at `0x14000b4cb`
- `ntdll!RtlAllocateHeap` at `0x14000b3ff`
- `ntdll!RtlAllocateHeap` at `0x14000b4cb`
- `ntdll!RtlReAllocateHeap` at `0x14000b41f`
- `ntdll!RtlReAllocateHeap` at `0x14000b4fc`
- `ntdll!RtlReAllocateHeap` at `0x14000b41f`
- `ntdll!RtlReAllocateHeap` at `0x14000b4fc`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteStringA(RtlMemoryStream *this, const char *a2, const char *a3)
{
  size_t v6; // rdi
  size_t v7; // rsi
  size_t *v8; // r15
  size_t v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // r14
  unsigned __int64 v12; // rax
  void *v13; // r8
  void *v14; // rcx
  SIZE_T v15; // r14
  PVOID v16; // rax
  PVOID Heap; // rbp
  size_t *v19; // rax
  size_t v20; // rcx
  size_t v21; // rax
  size_t *v22; // r14
  size_t v23; // rax
  unsigned __int64 v24; // rcx
  __int64 v25; // rsi
  unsigned __int64 v26; // rax
  void *v27; // r8
  void *v28; // rcx
  SIZE_T v29; // rsi
  PVOID v30; // rax
  PVOID v31; // rbp
  _QWORD *v32; // rax
  size_t v33; // rcx
  size_t v34; // rax

  if ( a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a3[v6] );
    if ( !v6 )
      v6 = 1;
  }
  else
  {
    v6 = 0;
  }
  if ( a2 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a2[v7] );
    if ( v7 )
    {
      v8 = (size_t *)((char *)this + 32);
      v9 = *((_QWORD *)this + 4);
      v10 = v9 + v7;
      if ( v9 + v7 < v9 )
        return 3221225485LL;
      if ( v10 <= *((_QWORD *)this + 2) )
      {
        v19 = v8;
      }
      else
      {
        v11 = *((_QWORD *)this + 3) - 1LL;
        v12 = v11 + v10;
        if ( v11 + v10 < v10 )
          return 3221225621LL;
        v13 = (void *)*((_QWORD *)this + 5);
        v14 = *(void **)this;
        v15 = v12 & ~v11;
        if ( v13 )
        {
          Heap = RtlReAllocateHeap(v14, 0, v13, v15);
        }
        else
        {
          v16 = RtlAllocateHeap(v14, 0, v15);
          Heap = v16;
          if ( v16 )
            memset_0(v16, 0, v15);
        }
        if ( !Heap )
          return 3221225495LL;
        *((_QWORD *)this + 5) = Heap;
        v19 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v15;
      }
      memcpy_0((void *)(*v19 + *((_QWORD *)this + 5)), a2, v7);
      v20 = *v8 + v7;
      if ( v20 < *v8 )
      {
        *v8 = -1;
        return 3221225621LL;
      }
      *v8 = v20;
      v21 = *((_QWORD *)this + 1);
      if ( v21 <= v20 )
        v21 = v20;
      *((_QWORD *)this + 1) = v21;
    }
  }
  if ( a3 && v6 )
  {
    v22 = (size_t *)((char *)this + 32);
    v23 = *((_QWORD *)this + 4);
    v24 = v23 + v6;
    if ( v23 + v6 >= v23 )
    {
      if ( v24 <= *((_QWORD *)this + 2) )
      {
        v32 = (_QWORD *)((char *)this + 32);
      }
      else
      {
        v25 = *((_QWORD *)this + 3) - 1LL;
        v26 = v24 + v25;
        if ( v24 + v25 < v24 )
          return 3221225621LL;
        v27 = (void *)*((_QWORD *)this + 5);
        v28 = *(void **)this;
        v29 = v26 & ~v25;
        if ( v27 )
        {
          v31 = RtlReAllocateHeap(v28, 0, v27, v29);
        }
        else
        {
          v30 = RtlAllocateHeap(v28, 0, v29);
          v31 = v30;
          if ( v30 )
            memset_0(v30, 0, v29);
        }
        if ( !v31 )
          return 3221225495LL;
        *((_QWORD *)this + 5) = v31;
        v32 = (_QWORD *)((char *)this + 32);
        *((_QWORD *)this + 2) = v29;
      }
      memcpy_0((void *)(*v32 + *((_QWORD *)this + 5)), a3, v6);
      v33 = *v22 + v6;
      if ( v33 >= *v22 )
      {
        *v22 = v33;
        v34 = *((_QWORD *)this + 1);
        if ( v34 <= v33 )
          v34 = v33;
        *((_QWORD *)this + 1) = v34;
        return 0;
      }
      *v22 = -1;
      return 3221225621LL;
    }
    return 3221225485LL;
  }
  return 0;
}

```

## disassembly

```asm
0x14000b35c  push    rbx
0x14000b35e  push    rbp
0x14000b35f  push    rsi
0x14000b360  push    rdi
0x14000b361  push    r12
0x14000b363  push    r13
0x14000b365  push    r14
0x14000b367  push    r15
0x14000b369  sub     rsp, 28h
0x14000b36d  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000b371  mov     r13, r8
0x14000b374  mov     r12, rdx
0x14000b377  mov     rbx, rcx
0x14000b37a  test    r8, r8
0x14000b37d  jz      short loc_14000B39A
0x14000b37f  mov     rdi, rbp
0x14000b382  inc     rdi
0x14000b385  cmp     byte ptr [rdi+r8], 0
0x14000b38a  jnz     short loc_14000B382
0x14000b38c  mov     eax, 1
0x14000b391  cmp     rdi, rax
0x14000b394  cmovb   rdi, rax
0x14000b398  jmp     short loc_14000B39C
0x14000b39a  xor     edi, edi
0x14000b39c  test    r12, r12
0x14000b39f  jz      loc_14000B47C
0x14000b3a5  mov     rsi, rbp
0x14000b3a8  inc     rsi
0x14000b3ab  cmp     byte ptr [rdx+rsi], 0
0x14000b3af  jnz     short loc_14000B3A8
0x14000b3b1  test    rsi, rsi
0x14000b3b4  jz      loc_14000B47C
0x14000b3ba  lea     r15, [rcx+20h]
0x14000b3be  mov     rax, [r15]
0x14000b3c1  lea     rcx, [rax+rsi]
0x14000b3c5  cmp     rcx, rax
0x14000b3c8  jb      loc_14000B4F2
0x14000b3ce  cmp     rcx, [rbx+10h]
0x14000b3d2  jbe     short loc_14000B449
0x14000b3d4  mov     r14, [rbx+18h]
0x14000b3d8  dec     r14
0x14000b3db  lea     rax, [r14+rcx]
0x14000b3df  cmp     rax, rcx
0x14000b3e2  jb      loc_14000B4EB
0x14000b3e8  mov     r8, [rbx+28h]; Ptr
0x14000b3ec  not     r14
0x14000b3ef  mov     rcx, [rbx]; Heap
0x14000b3f2  and     r14, rax
0x14000b3f5  xor     edx, edx; Flags
0x14000b3f7  test    r8, r8
0x14000b3fa  jnz     short loc_14000B41C
0x14000b3fc  mov     r8, r14; Size
0x14000b3ff  call    cs:__imp_RtlAllocateHeap
0x14000b405  mov     rbp, rax
0x14000b408  test    rax, rax
0x14000b40b  jz      short loc_14000B428
0x14000b40d  mov     r8, r14; Size
0x14000b410  xor     edx, edx; Val
0x14000b412  mov     rcx, rax; void *
0x14000b415  call    memset_0
0x14000b41a  jmp     short loc_14000B428
0x14000b41c  mov     r9, r14; Size
0x14000b41f  call    cs:__imp_RtlReAllocateHeap
0x14000b425  mov     rbp, rax
0x14000b428  test    rbp, rbp
0x14000b42b  jnz     short loc_14000B437
0x14000b42d  mov     eax, 0C0000017h
0x14000b432  jmp     loc_14000B551
0x14000b437  mov     [rbx+28h], rbp
0x14000b43b  lea     rax, [rbx+20h]
0x14000b43f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000b443  mov     [rbx+10h], r14
0x14000b447  jmp     short loc_14000B44C
0x14000b449  mov     rax, r15
0x14000b44c  mov     rcx, [rbx+28h]
0x14000b450  mov     r8, rsi; Size
0x14000b453  add     rcx, [rax]; void *
0x14000b456  mov     rdx, r12; Src
0x14000b459  call    memcpy_0
0x14000b45e  mov     rax, [r15]
0x14000b461  lea     rcx, [rax+rsi]
0x14000b465  cmp     rcx, rax
0x14000b468  jb      short loc_14000B4E8
0x14000b46a  mov     [r15], rcx
0x14000b46d  mov     rax, [rbx+8]
0x14000b471  cmp     rax, rcx
0x14000b474  cmovbe  rax, rcx
0x14000b478  mov     [rbx+8], rax
0x14000b47c  test    r13, r13
0x14000b47f  jz      loc_14000B54F
0x14000b485  test    rdi, rdi
0x14000b488  jz      loc_14000B54F
0x14000b48e  lea     r14, [rbx+20h]
0x14000b492  mov     rax, [r14]
0x14000b495  lea     rcx, [rax+rdi]
0x14000b499  cmp     rcx, rax
0x14000b49c  jb      short loc_14000B4F2
0x14000b49e  cmp     rcx, [rbx+10h]
0x14000b4a2  jbe     short loc_14000B51C
0x14000b4a4  mov     rsi, [rbx+18h]
0x14000b4a8  dec     rsi
0x14000b4ab  lea     rax, [rcx+rsi]
0x14000b4af  cmp     rax, rcx
0x14000b4b2  jb      short loc_14000B4EB
0x14000b4b4  mov     r8, [rbx+28h]; Ptr
0x14000b4b8  not     rsi
0x14000b4bb  mov     rcx, [rbx]; Heap
0x14000b4be  and     rsi, rax
0x14000b4c1  xor     edx, edx; Flags
0x14000b4c3  test    r8, r8
0x14000b4c6  jnz     short loc_14000B4F9
0x14000b4c8  mov     r8, rsi; Size
0x14000b4cb  call    cs:__imp_RtlAllocateHeap
0x14000b4d1  mov     rbp, rax
0x14000b4d4  test    rax, rax
0x14000b4d7  jz      short loc_14000B505
0x14000b4d9  mov     r8, rsi; Size
0x14000b4dc  xor     edx, edx; Val
0x14000b4de  mov     rcx, rax; void *
0x14000b4e1  call    memset_0
0x14000b4e6  jmp     short loc_14000B505
0x14000b4e8  mov     [r15], rbp
0x14000b4eb  mov     eax, 0C0000095h
0x14000b4f0  jmp     short loc_14000B551
0x14000b4f2  mov     eax, 0C000000Dh
0x14000b4f7  jmp     short loc_14000B551
0x14000b4f9  mov     r9, rsi; Size
0x14000b4fc  call    cs:__imp_RtlReAllocateHeap
0x14000b502  mov     rbp, rax
0x14000b505  test    rbp, rbp
0x14000b508  jz      loc_14000B42D
0x14000b50e  mov     [rbx+28h], rbp
0x14000b512  lea     rax, [rbx+20h]
0x14000b516  mov     [rbx+10h], rsi
0x14000b51a  jmp     short loc_14000B51F
0x14000b51c  mov     rax, r14
0x14000b51f  mov     rcx, [rbx+28h]
0x14000b523  mov     r8, rdi; Size
0x14000b526  add     rcx, [rax]; void *
0x14000b529  mov     rdx, r13; Src
0x14000b52c  call    memcpy_0
0x14000b531  mov     rax, [r14]
0x14000b534  lea     rcx, [rax+rdi]
0x14000b538  cmp     rcx, rax
0x14000b53b  jb      short loc_14000B562
0x14000b53d  mov     [r14], rcx
0x14000b540  mov     rax, [rbx+8]
0x14000b544  cmp     rax, rcx
0x14000b547  cmovbe  rax, rcx
0x14000b54b  mov     [rbx+8], rax
0x14000b54f  xor     eax, eax
0x14000b551  add     rsp, 28h
0x14000b555  pop     r15
0x14000b557  pop     r14
0x14000b559  pop     r13
0x14000b55b  pop     r12
0x14000b55d  pop     rdi
0x14000b55e  pop     rsi
0x14000b55f  pop     rbp
0x14000b560  pop     rbx
0x14000b561  retn
0x14000b562  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x14000b569  jmp     short loc_14000B4EB
```
