# I_PinCacheDecryptPin

- ea: `0x180038e7c`
- end: `0x180038f24`
- name: `I_PinCacheDecryptPin`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800391c4`
- `0x18003982c`

## callees

- `0x180009e76`
- `0x180038e7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038eb6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038eb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f0a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038f0a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038efc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038ea3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038efc`
- `CRYPTBASE!SystemFunction041` at `0x180038ee0`
- `CRYPTBASE!SystemFunction041` at `0x180038ee0`

## pseudocode

```c
__int64 __fastcall I_PinCacheDecryptPin(__int64 a1, void **a2, _DWORD *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // ebx
  HANDLE ProcessHeap; // rax
  SIZE_T v9; // r8
  void *v10; // rax
  void *v11; // rbp
  void *v12; // rsi
  HANDLE v13; // rax

  if ( *(_DWORD *)(a1 + 24) )
  {
    v7 = *(_DWORD *)(a1 + 24);
    ProcessHeap = GetProcessHeap();
    v9 = v7;
    v6 = 8;
    v10 = HeapAlloc(ProcessHeap, 8u, v9);
    *a2 = v10;
    v11 = v10;
    if ( !v10
      || (memcpy_0(v10, *(const void **)(a1 + 16), *(unsigned int *)(a1 + 24)),
          (v6 = SystemFunction041(v11, *(_DWORD *)(a1 + 24), 0)) != 0) )
    {
      v12 = *a2;
      if ( *a2 )
      {
        v13 = GetProcessHeap();
        HeapFree(v13, 0, v12);
        *a2 = 0;
      }
    }
    else
    {
      *a3 = *(_DWORD *)(a1 + 28);
    }
  }
  else
  {
    v6 = 0;
    *a2 = 0;
    *a3 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x180038e7c  push    rbx
0x180038e7e  push    rbp
0x180038e7f  push    rsi
0x180038e80  push    rdi
0x180038e81  push    r14
0x180038e83  sub     rsp, 20h
0x180038e87  cmp     dword ptr [rcx+18h], 0
0x180038e8b  mov     r14, r8
0x180038e8e  mov     rdi, rdx
0x180038e91  mov     rsi, rcx
0x180038e94  jnz     short loc_180038EA0
0x180038e96  xor     ebx, ebx
0x180038e98  mov     [rdx], rbx
0x180038e9b  mov     [r8], ebx
0x180038e9e  jmp     short loc_180038F17
0x180038ea0  mov     ebx, [rcx+18h]
0x180038ea3  call    cs:__imp_GetProcessHeap
0x180038ea9  mov     r8d, ebx; dwBytes
0x180038eac  mov     ebx, 8
0x180038eb1  mov     edx, ebx; dwFlags
0x180038eb3  mov     rcx, rax; hHeap
0x180038eb6  call    cs:__imp_HeapAlloc
0x180038ebc  mov     [rdi], rax
0x180038ebf  mov     rbp, rax
0x180038ec2  test    rax, rax
0x180038ec5  jz      short loc_180038EF4
0x180038ec7  mov     r8d, [rsi+18h]; Size
0x180038ecb  mov     rcx, rax; void *
0x180038ece  mov     rdx, [rsi+10h]; Src
0x180038ed2  call    memcpy_0
0x180038ed7  mov     edx, [rsi+18h]; MemorySize
0x180038eda  xor     r8d, r8d; OptionFlags
0x180038edd  mov     rcx, rbp; Memory
0x180038ee0  call    cs:__imp_SystemFunction041
0x180038ee6  mov     ebx, eax
0x180038ee8  test    eax, eax
0x180038eea  jnz     short loc_180038EF4
0x180038eec  mov     ecx, [rsi+1Ch]
0x180038eef  mov     [r14], ecx
0x180038ef2  jmp     short loc_180038F17
0x180038ef4  mov     rsi, [rdi]
0x180038ef7  test    rsi, rsi
0x180038efa  jz      short loc_180038F17
0x180038efc  call    cs:__imp_GetProcessHeap
0x180038f02  mov     r8, rsi; lpMem
0x180038f05  xor     edx, edx; dwFlags
0x180038f07  mov     rcx, rax; hHeap
0x180038f0a  call    cs:__imp_HeapFree
0x180038f10  mov     qword ptr [rdi], 0
0x180038f17  mov     eax, ebx
0x180038f19  add     rsp, 20h
0x180038f1d  pop     r14
0x180038f1f  pop     rdi
0x180038f20  pop     rsi
0x180038f21  pop     rbp
0x180038f22  pop     rbx
0x180038f23  retn
```
