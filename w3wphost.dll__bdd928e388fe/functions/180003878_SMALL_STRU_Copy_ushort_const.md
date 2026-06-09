# SMALL_STRU::Copy(ushort const *)

- ea: `0x180003878`
- end: `0x1800038f3`
- name: `?Copy@SMALL_STRU@@QEAAJPEBG@Z`
- size: `123`
- prototype: `int(SMALL_STRU *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003150`
- `0x180005d44`
- `0x18000b46c`
- `0x18000b50c`

## callees

- `0x180001be0`
- `0x180003878`
- `0x18000c386`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800038c5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800038c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800038b4`

## pseudocode

```c
__int64 __fastcall SMALL_STRU::Copy(SMALL_STRU *this, const unsigned __int16 *a2)
{
  __int64 v5; // rax
  SIZE_T v6; // rsi
  HANDLE ProcessHeap; // rax
  void *v8; // rax

  if ( !a2 )
    return 2147942487LL;
  if ( a2 != *(const unsigned __int16 **)this )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = 2 * v5 + 2;
    SMALL_STRU::Reset(this);
    ProcessHeap = GetProcessHeap();
    v8 = HeapAlloc(ProcessHeap, 8u, v6);
    *(_QWORD *)this = v8;
    if ( !v8 )
      return 2147942408LL;
    memcpy_0(v8, a2, v6);
  }
  return 0;
}

```

## disassembly

```asm
0x180003878  push    rbx
0x18000387a  push    rbp
0x18000387b  push    rsi
0x18000387c  push    rdi
0x18000387d  sub     rsp, 28h
0x180003881  xor     ebp, ebp
0x180003883  mov     rbx, rdx
0x180003886  mov     rdi, rcx
0x180003889  test    rdx, rdx
0x18000388c  jnz     short loc_180003895
0x18000388e  mov     eax, 80070057h
0x180003893  jmp     short loc_1800038EA
0x180003895  cmp     rbx, [rcx]
0x180003898  jz      short loc_1800038E8
0x18000389a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000389e  inc     rax
0x1800038a1  cmp     [rdx+rax*2], bp
0x1800038a5  jnz     short loc_18000389E
0x1800038a7  lea     rsi, ds:2[rax*2]
0x1800038af  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x1800038b4  call    cs:__imp_GetProcessHeap
0x1800038ba  mov     r8, rsi; dwBytes
0x1800038bd  mov     edx, 8; dwFlags
0x1800038c2  mov     rcx, rax; hHeap
0x1800038c5  call    cs:__imp_HeapAlloc
0x1800038cb  mov     [rdi], rax
0x1800038ce  test    rax, rax
0x1800038d1  jnz     short loc_1800038DA
0x1800038d3  mov     eax, 80070008h
0x1800038d8  jmp     short loc_1800038EA
0x1800038da  mov     r8, rsi; Size
0x1800038dd  mov     rdx, rbx; Src
0x1800038e0  mov     rcx, rax; void *
0x1800038e3  call    memcpy_0
0x1800038e8  xor     eax, eax
0x1800038ea  add     rsp, 28h
0x1800038ee  pop     rdi
0x1800038ef  pop     rsi
0x1800038f0  pop     rbp
0x1800038f1  pop     rbx
0x1800038f2  retn
```
