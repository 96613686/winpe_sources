# Pca::MergeSdb::Utils::RegValue::RegValueCreateBuffer(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &,ulong &,ushort const *,ulong,ulong,uchar const *)

- ea: `0x14002dce4`
- end: `0x14002de6e`
- name: `?RegValueCreateBuffer@RegValue@Utils@MergeSdb@Pca@@CAKAEAV?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@AEAKPEBGKKPEBE@Z`
- size: `394`
- prototype: `__int64 __fastcall(void **, _DWORD *, _WORD *, int, unsigned int, _BYTE *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14002ae60`
- `0x14002e0a4`

## callees

- `0x140002206`
- `0x1400025f8`
- `0x14002dce4`
- `0x14002e3e2`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x14002dd1b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002de47`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002dd1b`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002de47`

## pseudocode

```c
__int64 __fastcall Pca::MergeSdb::Utils::RegValue::RegValueCreateBuffer(
        void **a1,
        _DWORD *a2,
        _WORD *a3,
        int a4,
        unsigned int a5,
        _BYTE *Src)
{
  void *v8; // rcx
  unsigned int v11; // ebp
  __int64 v12; // rax
  unsigned int v13; // ebx
  unsigned __int64 v14; // rdi
  unsigned __int64 v15; // rdi
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // rax
  _DWORD *v19; // rax
  void *v20; // rcx
  size_t Size; // [rsp+20h] [rbp-48h]
  int v23; // [rsp+28h] [rbp-40h]
  _DWORD *v26; // [rsp+80h] [rbp+18h]

  v8 = *a1;
  *a1 = 0;
  if ( v8 )
    operator delete[](v8);
  *a2 = 0;
  if ( a3 )
  {
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    v11 = 2 * v12 + 2;
  }
  else
  {
    v11 = 0;
  }
  if ( (unsigned int)(a4 - 1) <= 1 || a4 == 7 )
  {
    v13 = a5;
    if ( Src[a5 - 2] || Src[a5 - 1] )
      v13 = a5 + 2;
  }
  else
  {
    v13 = a5;
  }
  v14 = 4;
  if ( v11 )
    v14 = v11 + 3LL;
  v15 = v14 >> 2;
  v16 = 4;
  if ( v13 )
    v16 = v13 + 3LL;
  v17 = v15 + (v16 >> 2) + 3;
  v18 = 4 * v17;
  v23 = v17;
  if ( !is_mul_ok(v17, 4u) )
    v18 = -1;
  Size = v18;
  v19 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
  v26 = v19;
  if ( !v19 )
    return 14;
  memset_0(v19, 0, Size);
  v26[2] = v13;
  *v26 = a4;
  v26[1] = v11;
  memcpy_0(v26 + 3, a3, v11);
  memcpy_0(&v26[v15 + 3], Src, v13);
  v20 = *a1;
  *a1 = v26;
  *a2 = v23;
  if ( v20 )
    operator delete[](v20);
  return 0;
}

```

## disassembly

```asm
0x14002dce4  mov     [rsp+arg_18], rbx
0x14002dce9  mov     [rsp+arg_8], rdx
0x14002dcee  mov     [rsp+arg_0], rcx
0x14002dcf3  push    rbp
0x14002dcf4  push    rsi
0x14002dcf5  push    rdi
0x14002dcf6  push    r12
0x14002dcf8  push    r13
0x14002dcfa  push    r14
0x14002dcfc  push    r15
0x14002dcfe  sub     rsp, 30h
0x14002dd02  mov     rax, rcx
0x14002dd05  mov     rbx, rdx
0x14002dd08  mov     rcx, [rcx]
0x14002dd0b  xor     edx, edx
0x14002dd0d  mov     r13d, r9d
0x14002dd10  mov     r12, r8
0x14002dd13  mov     [rax], rdx
0x14002dd16  test    rcx, rcx
0x14002dd19  jz      short loc_14002DD23
0x14002dd1b  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002dd21  xor     edx, edx
0x14002dd23  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002dd27  mov     [rbx], edx
0x14002dd29  test    r12, r12
0x14002dd2c  jnz     short loc_14002DD32
0x14002dd2e  mov     ebp, edx
0x14002dd30  jmp     short loc_14002DD46
0x14002dd32  mov     rax, r9
0x14002dd35  inc     rax
0x14002dd38  cmp     [r12+rax*2], dx
0x14002dd3d  jnz     short loc_14002DD35
0x14002dd3f  lea     ebp, ds:2[rax*2]
0x14002dd46  mov     r14, [rsp+68h+Src]
0x14002dd4e  lea     eax, [r13-1]
0x14002dd52  cmp     eax, 1
0x14002dd55  jbe     short loc_14002DD66
0x14002dd57  cmp     r13d, 7
0x14002dd5b  jz      short loc_14002DD66
0x14002dd5d  mov     ebx, dword ptr [rsp+68h+arg_20]
0x14002dd64  jmp     short loc_14002DD82
0x14002dd66  mov     ebx, dword ptr [rsp+68h+arg_20]
0x14002dd6d  lea     eax, [rbx-2]
0x14002dd70  cmp     [rax+r14], dl
0x14002dd74  jnz     short loc_14002DD7F
0x14002dd76  lea     eax, [rbx-1]
0x14002dd79  cmp     [rax+r14], dl
0x14002dd7d  jz      short loc_14002DD82
0x14002dd7f  add     ebx, 2
0x14002dd82  mov     esi, ebp
0x14002dd84  mov     r8d, 4
0x14002dd8a  mov     edi, r8d
0x14002dd8d  test    ebp, ebp
0x14002dd8f  jz      short loc_14002DD95
0x14002dd91  lea     rdi, [rsi+3]
0x14002dd95  shr     rdi, 2
0x14002dd99  mov     rax, r8
0x14002dd9c  mov     r15d, ebx
0x14002dd9f  test    ebx, ebx
0x14002dda1  jz      short loc_14002DDA7
0x14002dda3  lea     rax, [r15+3]
0x14002dda7  shr     rax, 2
0x14002ddab  lea     rcx, [rax+3]
0x14002ddaf  mov     rax, r8
0x14002ddb2  add     rcx, rdi
0x14002ddb5  mul     rcx
0x14002ddb8  mov     qword ptr [rsp+68h+var_40], rcx
0x14002ddbd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002ddc4  cmovb   rax, r9
0x14002ddc8  mov     rcx, rax; unsigned __int64
0x14002ddcb  mov     [rsp+68h+Size], rax
0x14002ddd0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002ddd5  mov     [rsp+68h+arg_10], rax
0x14002dddd  test    rax, rax
0x14002dde0  jz      short loc_14002DE51
0x14002dde2  mov     r8, [rsp+68h+Size]; Size
0x14002dde7  xor     edx, edx; Val
0x14002dde9  mov     rcx, rax; void *
0x14002ddec  call    memset_0
0x14002ddf1  mov     rax, [rsp+68h+arg_10]
0x14002ddf9  mov     r8, rsi; Size
0x14002ddfc  mov     rdx, r12; Src
0x14002ddff  mov     [rax+8], ebx
0x14002de02  lea     rbx, [rax+0Ch]
0x14002de06  mov     rcx, rbx; void *
0x14002de09  mov     [rax], r13d
0x14002de0c  mov     [rax+4], ebp
0x14002de0f  call    memcpy_0
0x14002de14  lea     rcx, [rbx+rdi*4]; void *
0x14002de18  mov     r8, r15; Size
0x14002de1b  mov     rdx, r14; Src
0x14002de1e  call    memcpy_0
0x14002de23  mov     rax, [rsp+68h+arg_0]
0x14002de28  mov     r9, [rsp+68h+arg_10]
0x14002de30  mov     rdx, qword ptr [rsp+68h+var_40]
0x14002de35  mov     rcx, [rax]
0x14002de38  mov     [rax], r9
0x14002de3b  mov     rax, [rsp+68h+arg_8]
0x14002de40  mov     [rax], edx
0x14002de42  test    rcx, rcx
0x14002de45  jz      short loc_14002DE4D
0x14002de47  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002de4d  xor     eax, eax
0x14002de4f  jmp     short loc_14002DE56
0x14002de51  mov     eax, 0Eh
0x14002de56  mov     rbx, [rsp+68h+arg_18]
0x14002de5e  add     rsp, 30h
0x14002de62  pop     r15
0x14002de64  pop     r14
0x14002de66  pop     r13
0x14002de68  pop     r12
0x14002de6a  pop     rdi
0x14002de6b  pop     rsi
0x14002de6c  pop     rbp
0x14002de6d  retn
```
