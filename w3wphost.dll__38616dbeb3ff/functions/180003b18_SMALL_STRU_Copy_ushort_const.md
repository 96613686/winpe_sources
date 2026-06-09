# SMALL_STRU::Copy(ushort const *)

- ea: `0x180003b18`
- end: `0x180003ba0`
- name: `?Copy@SMALL_STRU@@QEAAJPEBG@Z`
- size: `136`
- prototype: `int(SMALL_STRU *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180003340`
- `0x1800062bc`
- `0x18000c270`
- `0x18000c320`

## callees

- `0x180001c80`
- `0x180003b18`
- `0x18000d2a6`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003b6b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003b6b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b54`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b54`

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
0x180003b18  push    rbx
0x180003b1a  push    rbp
0x180003b1b  push    rsi
0x180003b1c  push    rdi
0x180003b1d  sub     rsp, 28h
0x180003b21  xor     ebp, ebp
0x180003b23  mov     rbx, rdx
0x180003b26  mov     rdi, rcx
0x180003b29  test    rdx, rdx
0x180003b2c  jnz     short loc_180003B35
0x180003b2e  mov     eax, 80070057h
0x180003b33  jmp     short loc_180003B96
0x180003b35  cmp     rbx, [rcx]
0x180003b38  jz      short loc_180003B94
0x180003b3a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b3e  inc     rax
0x180003b41  cmp     [rdx+rax*2], bp
0x180003b45  jnz     short loc_180003B3E
0x180003b47  lea     rsi, ds:2[rax*2]
0x180003b4f  call    ?Reset@SMALL_STRU@@QEAAXXZ; SMALL_STRU::Reset(void)
0x180003b54  call    cs:__imp_GetProcessHeap
0x180003b5b  nop     dword ptr [rax+rax+00h]
0x180003b60  mov     r8, rsi; dwBytes
0x180003b63  mov     edx, 8; dwFlags
0x180003b68  mov     rcx, rax; hHeap
0x180003b6b  call    cs:__imp_HeapAlloc
0x180003b72  nop     dword ptr [rax+rax+00h]
0x180003b77  mov     [rdi], rax
0x180003b7a  test    rax, rax
0x180003b7d  jnz     short loc_180003B86
0x180003b7f  mov     eax, 80070008h
0x180003b84  jmp     short loc_180003B96
0x180003b86  mov     r8, rsi; Size
0x180003b89  mov     rdx, rbx; Src
0x180003b8c  mov     rcx, rax; void *
0x180003b8f  call    memcpy_0
0x180003b94  xor     eax, eax
0x180003b96  add     rsp, 28h
0x180003b9a  pop     rdi
0x180003b9b  pop     rsi
0x180003b9c  pop     rbp
0x180003b9d  pop     rbx
0x180003b9e  retn
```
