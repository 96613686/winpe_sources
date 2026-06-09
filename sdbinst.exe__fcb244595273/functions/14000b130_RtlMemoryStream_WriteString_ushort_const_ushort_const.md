# RtlMemoryStream::WriteString(ushort const *,ushort const *)

- ea: `0x14000b130`
- end: `0x14000b355`
- name: `?WriteString@RtlMemoryStream@@QEAAJPEBG0@Z`
- size: `549`
- prototype: `__int64 __fastcall(RtlMemoryStream *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000c540`

## callees

- `0x140002206`
- `0x14000b130`
- `0x14002e3e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14000b1da`
- `ntdll!RtlAllocateHeap` at `0x14000b2b0`
- `ntdll!RtlAllocateHeap` at `0x14000b1da`
- `ntdll!RtlAllocateHeap` at `0x14000b2b0`
- `ntdll!RtlReAllocateHeap` at `0x14000b1fa`
- `ntdll!RtlReAllocateHeap` at `0x14000b2e1`
- `ntdll!RtlReAllocateHeap` at `0x14000b1fa`
- `ntdll!RtlReAllocateHeap` at `0x14000b2e1`

## pseudocode

```c
__int64 __fastcall RtlMemoryStream::WriteString(
        RtlMemoryStream *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdi
  __int64 v7; // rax
  size_t v8; // r15
  size_t *v9; // r14
  size_t v10; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rsi
  unsigned __int64 v13; // rax
  void *v14; // r8
  void *v15; // rcx
  SIZE_T v16; // rsi
  PVOID v17; // rax
  PVOID Heap; // rbp
  size_t *v20; // rcx
  size_t v21; // rcx
  size_t v22; // rax
  size_t v23; // r14
  size_t *v24; // rsi
  size_t v25; // rax
  unsigned __int64 v26; // rcx
  __int64 v27; // rdi
  unsigned __int64 v28; // rax
  void *v29; // r8
  void *v30; // rcx
  SIZE_T v31; // rdi
  PVOID v32; // rax
  PVOID v33; // rbp
  _QWORD *v34; // rcx
  size_t v35; // rcx
  size_t v36; // rax

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
    v8 = 2 * v7;
    if ( 2 * v7 )
    {
      v9 = (size_t *)((char *)this + 32);
      v10 = *((_QWORD *)this + 4);
      v11 = v10 + v8;
      if ( v10 + v8 < v10 )
        return 3221225485LL;
      if ( v11 <= *((_QWORD *)this + 2) )
      {
        v20 = v9;
      }
      else
      {
        v12 = *((_QWORD *)this + 3) - 1LL;
        v13 = v12 + v11;
        if ( v12 + v11 < v11 )
          return 3221225621LL;
        v14 = (void *)*((_QWORD *)this + 5);
        v15 = *(void **)this;
        v16 = v13 & ~v12;
        if ( v14 )
        {
          Heap = RtlReAllocateHeap(v15, 0, v14, v16);
        }
        else
        {
          v17 = RtlAllocateHeap(v15, 0, v16);
          Heap = v17;
          if ( v17 )
            memset_0(v17, 0, v16);
        }
        if ( !Heap )
          return 3221225495LL;
        *((_QWORD *)this + 5) = Heap;
        v20 = (size_t *)((char *)this + 32);
        *((_QWORD *)this + 2) = v16;
      }
      memcpy_0((void *)(*((_QWORD *)this + 5) + *v20), a2, v8);
      v21 = *v9 + v8;
      if ( v21 < *v9 )
      {
        *v9 = -1;
        return 3221225621LL;
      }
      *v9 = v21;
      v22 = *((_QWORD *)this + 1);
      if ( v22 <= v21 )
        v22 = v21;
      *((_QWORD *)this + 1) = v22;
    }
  }
  if ( a3 )
  {
    v23 = 2 * v6;
    if ( 2 * v6 )
    {
      v24 = (size_t *)((char *)this + 32);
      v25 = *((_QWORD *)this + 4);
      v26 = v25 + v23;
      if ( v25 + v23 >= v25 )
      {
        if ( v26 <= *((_QWORD *)this + 2) )
        {
          v34 = (_QWORD *)((char *)this + 32);
        }
        else
        {
          v27 = *((_QWORD *)this + 3) - 1LL;
          v28 = v26 + v27;
          if ( v26 + v27 < v26 )
            return 3221225621LL;
          v29 = (void *)*((_QWORD *)this + 5);
          v30 = *(void **)this;
          v31 = v28 & ~v27;
          if ( v29 )
          {
            v33 = RtlReAllocateHeap(v30, 0, v29, v31);
          }
          else
          {
            v32 = RtlAllocateHeap(v30, 0, v31);
            v33 = v32;
            if ( v32 )
              memset_0(v32, 0, v31);
          }
          if ( !v33 )
            return 3221225495LL;
          *((_QWORD *)this + 5) = v33;
          v34 = (_QWORD *)((char *)this + 32);
          *((_QWORD *)this + 2) = v31;
        }
        memcpy_0((void *)(*((_QWORD *)this + 5) + *v34), a3, v23);
        v35 = v23 + *v24;
        if ( v35 >= *v24 )
        {
          *v24 = v35;
          v36 = *((_QWORD *)this + 1);
          if ( v36 <= v35 )
            v36 = v35;
          *((_QWORD *)this + 1) = v36;
          return 0;
        }
        *v24 = -1;
        return 3221225621LL;
      }
      return 3221225485LL;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000b130  push    rbx
0x14000b132  push    rbp
0x14000b133  push    rsi
0x14000b134  push    rdi
0x14000b135  push    r12
0x14000b137  push    r13
0x14000b139  push    r14
0x14000b13b  push    r15
0x14000b13d  sub     rsp, 28h
0x14000b141  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000b145  xor     ebp, ebp
0x14000b147  mov     r13, r8
0x14000b14a  mov     r12, rdx
0x14000b14d  mov     rbx, rcx
0x14000b150  test    r8, r8
0x14000b153  jz      short loc_14000B170
0x14000b155  mov     rdi, rsi
0x14000b158  inc     rdi
0x14000b15b  cmp     [r8+rdi*2], bp
0x14000b160  jnz     short loc_14000B158
0x14000b162  mov     eax, 1
0x14000b167  cmp     rdi, rax
0x14000b16a  cmovb   rdi, rax
0x14000b16e  jmp     short loc_14000B173
0x14000b170  mov     rdi, rbp
0x14000b173  test    r12, r12
0x14000b176  jz      loc_14000B25D
0x14000b17c  mov     rax, rsi
0x14000b17f  inc     rax
0x14000b182  cmp     [rdx+rax*2], bp
0x14000b186  jnz     short loc_14000B17F
0x14000b188  lea     r15, [rax+rax]
0x14000b18c  test    r15, r15
0x14000b18f  jz      loc_14000B25D
0x14000b195  lea     r14, [rcx+20h]
0x14000b199  mov     rax, [r14]
0x14000b19c  lea     rcx, [rax+r15]
0x14000b1a0  cmp     rcx, rax
0x14000b1a3  jb      loc_14000B2D7
0x14000b1a9  cmp     rcx, [rbx+10h]
0x14000b1ad  jbe     short loc_14000B226
0x14000b1af  mov     rsi, [rbx+18h]
0x14000b1b3  dec     rsi
0x14000b1b6  lea     rax, [rsi+rcx]
0x14000b1ba  cmp     rax, rcx
0x14000b1bd  jb      loc_14000B2D0
0x14000b1c3  mov     r8, [rbx+28h]; Ptr
0x14000b1c7  not     rsi
0x14000b1ca  mov     rcx, [rbx]; Heap
0x14000b1cd  and     rsi, rax
0x14000b1d0  xor     edx, edx; Flags
0x14000b1d2  test    r8, r8
0x14000b1d5  jnz     short loc_14000B1F7
0x14000b1d7  mov     r8, rsi; Size
0x14000b1da  call    cs:__imp_RtlAllocateHeap
0x14000b1e0  mov     rbp, rax
0x14000b1e3  test    rax, rax
0x14000b1e6  jz      short loc_14000B203
0x14000b1e8  mov     r8, rsi; Size
0x14000b1eb  xor     edx, edx; Val
0x14000b1ed  mov     rcx, rax; void *
0x14000b1f0  call    memset_0
0x14000b1f5  jmp     short loc_14000B203
0x14000b1f7  mov     r9, rsi; Size
0x14000b1fa  call    cs:__imp_RtlReAllocateHeap
0x14000b200  mov     rbp, rax
0x14000b203  test    rbp, rbp
0x14000b206  jnz     short loc_14000B212
0x14000b208  mov     eax, 0C0000017h
0x14000b20d  jmp     loc_14000B338
0x14000b212  mov     [rbx+28h], rbp
0x14000b216  lea     rcx, [rbx+20h]
0x14000b21a  xor     ebp, ebp
0x14000b21c  mov     [rbx+10h], rsi
0x14000b220  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000b224  jmp     short loc_14000B229
0x14000b226  mov     rcx, r14
0x14000b229  mov     rcx, [rcx]
0x14000b22c  mov     r8, r15; Size
0x14000b22f  add     rcx, [rbx+28h]; void *
0x14000b233  mov     rdx, r12; Src
0x14000b236  call    memcpy_0
0x14000b23b  mov     rax, [r14]
0x14000b23e  lea     rcx, [rax+r15]
0x14000b242  cmp     rcx, rax
0x14000b245  jb      loc_14000B2CD
0x14000b24b  mov     [r14], rcx
0x14000b24e  mov     rax, [rbx+8]
0x14000b252  cmp     rax, rcx
0x14000b255  cmovbe  rax, rcx
0x14000b259  mov     [rbx+8], rax
0x14000b25d  test    r13, r13
0x14000b260  jz      loc_14000B336
0x14000b266  lea     r14, [rdi+rdi]
0x14000b26a  test    r14, r14
0x14000b26d  jz      loc_14000B336
0x14000b273  lea     rsi, [rbx+20h]
0x14000b277  mov     rax, [rsi]
0x14000b27a  lea     rcx, [rax+r14]
0x14000b27e  cmp     rcx, rax
0x14000b281  jb      short loc_14000B2D7
0x14000b283  cmp     rcx, [rbx+10h]
0x14000b287  jbe     short loc_14000B303
0x14000b289  mov     rdi, [rbx+18h]
0x14000b28d  dec     rdi
0x14000b290  lea     rax, [rcx+rdi]
0x14000b294  cmp     rax, rcx
0x14000b297  jb      short loc_14000B2D0
0x14000b299  mov     r8, [rbx+28h]; Ptr
0x14000b29d  not     rdi
0x14000b2a0  mov     rcx, [rbx]; Heap
0x14000b2a3  and     rdi, rax
0x14000b2a6  xor     edx, edx; Flags
0x14000b2a8  test    r8, r8
0x14000b2ab  jnz     short loc_14000B2DE
0x14000b2ad  mov     r8, rdi; Size
0x14000b2b0  call    cs:__imp_RtlAllocateHeap
0x14000b2b6  mov     rbp, rax
0x14000b2b9  test    rax, rax
0x14000b2bc  jz      short loc_14000B2EA
0x14000b2be  mov     r8, rdi; Size
0x14000b2c1  xor     edx, edx; Val
0x14000b2c3  mov     rcx, rax; void *
0x14000b2c6  call    memset_0
0x14000b2cb  jmp     short loc_14000B2EA
0x14000b2cd  mov     [r14], rsi
0x14000b2d0  mov     eax, 0C0000095h
0x14000b2d5  jmp     short loc_14000B338
0x14000b2d7  mov     eax, 0C000000Dh
0x14000b2dc  jmp     short loc_14000B338
0x14000b2de  mov     r9, rdi; Size
0x14000b2e1  call    cs:__imp_RtlReAllocateHeap
0x14000b2e7  mov     rbp, rax
0x14000b2ea  test    rbp, rbp
0x14000b2ed  jz      loc_14000B208
0x14000b2f3  mov     [rbx+28h], rbp
0x14000b2f7  lea     rcx, [rbx+20h]
0x14000b2fb  xor     ebp, ebp
0x14000b2fd  mov     [rbx+10h], rdi
0x14000b301  jmp     short loc_14000B306
0x14000b303  mov     rcx, rsi
0x14000b306  mov     rcx, [rcx]
0x14000b309  mov     r8, r14; Size
0x14000b30c  add     rcx, [rbx+28h]; void *
0x14000b310  mov     rdx, r13; Src
0x14000b313  call    memcpy_0
0x14000b318  mov     rax, [rsi]
0x14000b31b  lea     rcx, [r14+rax]
0x14000b31f  cmp     rcx, rax
0x14000b322  jb      short loc_14000B349
0x14000b324  mov     [rsi], rcx
0x14000b327  mov     rax, [rbx+8]
0x14000b32b  cmp     rax, rcx
0x14000b32e  cmovbe  rax, rcx
0x14000b332  mov     [rbx+8], rax
0x14000b336  mov     eax, ebp
0x14000b338  add     rsp, 28h
0x14000b33c  pop     r15
0x14000b33e  pop     r14
0x14000b340  pop     r13
0x14000b342  pop     r12
0x14000b344  pop     rdi
0x14000b345  pop     rsi
0x14000b346  pop     rbp
0x14000b347  pop     rbx
0x14000b348  retn
0x14000b349  mov     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x14000b350  jmp     loc_14000B2D0
```
