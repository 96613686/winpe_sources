# CopyUrlStr

- ea: `0x14001ed3c`
- end: `0x14001ed94`
- name: `CopyUrlStr`
- size: `88`
- prototype: `__int64 __fastcall(void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140022480`

## callees

- `0x14001ed3c`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ed52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001ed52`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ed63`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14001ed63`

## pseudocode

```c
__int64 __fastcall CopyUrlStr(void *Src, size_t Size)
{
  __int64 v2; // rbp
  unsigned int v4; // ebx
  HANDLE ProcessHeap; // rax
  void *v6; // rax
  __int64 v7; // rdi
  __int64 result; // rax

  v2 = (unsigned int)Size;
  if ( !Src )
    return 0;
  v4 = Size + 1;
  ProcessHeap = GetProcessHeap();
  v6 = HeapAlloc(ProcessHeap, 8u, v4);
  v7 = (__int64)v6;
  if ( !v6 )
    return 0;
  memcpy_0(v6, Src, (unsigned int)v2);
  result = v7;
  *(_BYTE *)(v2 + v7) = 0;
  return result;
}

```

## disassembly

```asm
0x14001ed3c  push    rbx
0x14001ed3e  push    rbp
0x14001ed3f  push    rsi
0x14001ed40  push    rdi
0x14001ed41  sub     rsp, 28h
0x14001ed45  mov     ebp, edx
0x14001ed47  mov     rsi, rcx
0x14001ed4a  test    rcx, rcx
0x14001ed4d  jz      short loc_14001ED89
0x14001ed4f  lea     ebx, [rbp+1]
0x14001ed52  call    cs:__imp_GetProcessHeap
0x14001ed58  mov     r8d, ebx; dwBytes
0x14001ed5b  mov     edx, 8; dwFlags
0x14001ed60  mov     rcx, rax; hHeap
0x14001ed63  call    cs:__imp_HeapAlloc
0x14001ed69  mov     rdi, rax
0x14001ed6c  test    rax, rax
0x14001ed6f  jz      short loc_14001ED89
0x14001ed71  mov     r8d, ebp; Size
0x14001ed74  mov     rdx, rsi; Src
0x14001ed77  mov     rcx, rax; void *
0x14001ed7a  call    memcpy_0
0x14001ed7f  mov     rax, rdi
0x14001ed82  mov     byte ptr [rbp+rdi+0], 0
0x14001ed87  jmp     short loc_14001ED8B
0x14001ed89  xor     eax, eax
0x14001ed8b  add     rsp, 28h
0x14001ed8f  pop     rdi
0x14001ed90  pop     rsi
0x14001ed91  pop     rbp
0x14001ed92  pop     rbx
0x14001ed93  retn
```
