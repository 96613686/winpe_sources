# I_PinCacheEncryptPin

- ea: `0x180038f2c`
- end: `0x180038fd6`
- name: `I_PinCacheEncryptPin`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180038e28`

## callees

- `0x180009e76`
- `0x180038f2c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038f9b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038f9b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f5b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038f88`
- `CRYPTBASE!SystemFunction040` at `0x180038fc1`
- `CRYPTBASE!SystemFunction040` at `0x180038fc1`

## pseudocode

```c
__int64 __fastcall I_PinCacheEncryptPin(__int64 a1, const void *a2, unsigned int a3)
{
  void *v3; // rbx
  ULONG *v4; // rsi
  size_t v5; // rbp
  HANDLE ProcessHeap; // rax
  unsigned int v9; // ebx
  ULONG v10; // ebx
  HANDLE v11; // rax
  SIZE_T v12; // r8
  void *v13; // rax

  v3 = *(void **)(a1 + 16);
  v4 = (ULONG *)(a1 + 24);
  v5 = a3;
  if ( v3 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v3);
    *(_QWORD *)(a1 + 16) = 0;
    *v4 = 0;
  }
  *(_DWORD *)(a1 + 28) = v5;
  if ( (_DWORD)v5 )
  {
    v10 = (v5 + 15) & 0xFFFFFFF0;
    *v4 = v10;
    v11 = GetProcessHeap();
    v12 = v10;
    v9 = 8;
    v13 = HeapAlloc(v11, 8u, v12);
    *(_QWORD *)(a1 + 16) = v13;
    if ( v13 )
    {
      memcpy_0(v13, a2, v5);
      return (unsigned int)SystemFunction040(*(PVOID *)(a1 + 16), *v4, 0);
    }
  }
  else
  {
    v9 = 0;
    *v4 = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  return v9;
}

```

## disassembly

```asm
0x180038f2c  push    rbx
0x180038f2e  push    rbp
0x180038f2f  push    rsi
0x180038f30  push    rdi
0x180038f31  push    r14
0x180038f33  sub     rsp, 20h
0x180038f37  mov     rbx, [rcx+10h]
0x180038f3b  lea     rsi, [rcx+18h]
0x180038f3f  mov     ebp, r8d
0x180038f42  mov     r14, rdx
0x180038f45  mov     rdi, rcx
0x180038f48  test    rbx, rbx
0x180038f4b  jz      short loc_180038F6F
0x180038f4d  call    cs:__imp_GetProcessHeap
0x180038f53  mov     r8, rbx; lpMem
0x180038f56  xor     edx, edx; dwFlags
0x180038f58  mov     rcx, rax; hHeap
0x180038f5b  call    cs:__imp_HeapFree
0x180038f61  mov     qword ptr [rdi+10h], 0
0x180038f69  mov     dword ptr [rsi], 0
0x180038f6f  mov     [rdi+1Ch], ebp
0x180038f72  test    ebp, ebp
0x180038f74  jnz     short loc_180038F80
0x180038f76  xor     ebx, ebx
0x180038f78  mov     [rsi], ebx
0x180038f7a  mov     [rdi+10h], rbx
0x180038f7e  jmp     short loc_180038FC9
0x180038f80  lea     ebx, [rbp+0Fh]
0x180038f83  and     ebx, 0FFFFFFF0h
0x180038f86  mov     [rsi], ebx
0x180038f88  call    cs:__imp_GetProcessHeap
0x180038f8e  mov     r8d, ebx; dwBytes
0x180038f91  mov     ebx, 8
0x180038f96  mov     edx, ebx; dwFlags
0x180038f98  mov     rcx, rax; hHeap
0x180038f9b  call    cs:__imp_HeapAlloc
0x180038fa1  mov     [rdi+10h], rax
0x180038fa5  test    rax, rax
0x180038fa8  jz      short loc_180038FC9
0x180038faa  mov     r8, rbp; Size
0x180038fad  mov     rdx, r14; Src
0x180038fb0  mov     rcx, rax; void *
0x180038fb3  call    memcpy_0
0x180038fb8  mov     edx, [rsi]; MemorySize
0x180038fba  xor     r8d, r8d; OptionFlags
0x180038fbd  mov     rcx, [rdi+10h]; Memory
0x180038fc1  call    cs:__imp_SystemFunction040
0x180038fc7  mov     ebx, eax
0x180038fc9  mov     eax, ebx
0x180038fcb  add     rsp, 20h
0x180038fcf  pop     r14
0x180038fd1  pop     rdi
0x180038fd2  pop     rsi
0x180038fd3  pop     rbp
0x180038fd4  pop     rbx
0x180038fd5  retn
```
