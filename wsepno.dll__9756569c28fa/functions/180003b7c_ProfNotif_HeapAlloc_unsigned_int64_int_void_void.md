# ProfNotif_HeapAlloc(unsigned __int64,int,void * *,void *)

- ea: `0x180003b7c`
- end: `0x180003bd7`
- name: `?ProfNotif_HeapAlloc@@YAJ_KHPEAPEAXPEAX@Z`
- size: `91`
- prototype: `__int64 __fastcall(SIZE_T dwBytes, int, void **, void *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ab8`
- `0x180006040`
- `0x18000b4e8`
- `0x18000c234`
- `0x18000c444`

## callees

- `0x180003b7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003bb1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003bb1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003b91`

## pseudocode

```c
__int64 __fastcall ProfNotif_HeapAlloc(SIZE_T dwBytes, __int64 a2, void **a3, void *a4)
{
  HANDLE ProcessHeap; // rax
  unsigned int v7; // ebx
  void *v8; // rax

  ProcessHeap = GetProcessHeap();
  v7 = -2147418113;
  if ( ProcessHeap )
  {
    v7 = 0;
    v8 = HeapAlloc(ProcessHeap, 8u, dwBytes);
    *a3 = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
  }
  return v7;
}

```

## disassembly

```asm
0x180003b7c  mov     [rsp+arg_0], rbx
0x180003b81  mov     [rsp+arg_8], rsi
0x180003b86  push    rdi
0x180003b87  sub     rsp, 20h
0x180003b8b  mov     rdi, r8
0x180003b8e  mov     rsi, rcx
0x180003b91  call    cs:__imp_GetProcessHeap
0x180003b97  xor     edx, edx
0x180003b99  mov     ebx, 8000FFFFh
0x180003b9e  test    rax, rax
0x180003ba1  cmovnz  ebx, edx
0x180003ba4  jz      short loc_180003BC5
0x180003ba6  mov     r8, rsi; dwBytes
0x180003ba9  mov     edx, 8; dwFlags
0x180003bae  mov     rcx, rax; hHeap
0x180003bb1  call    cs:__imp_HeapAlloc
0x180003bb7  test    rax, rax
0x180003bba  mov     [rdi], rax
0x180003bbd  mov     ecx, 8007000Eh
0x180003bc2  cmovz   ebx, ecx
0x180003bc5  mov     rsi, [rsp+28h+arg_8]
0x180003bca  mov     eax, ebx
0x180003bcc  mov     rbx, [rsp+28h+arg_0]
0x180003bd1  add     rsp, 20h
0x180003bd5  pop     rdi
0x180003bd6  retn
```
