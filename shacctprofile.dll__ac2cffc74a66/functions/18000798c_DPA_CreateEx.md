# DPA_CreateEx

- ea: `0x18000798c`
- end: `0x1800079db`
- name: `DPA_CreateEx`
- size: `79`
- prototype: `HDPA __stdcall(int cpGrow, HANDLE hheap)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007980`

## callees

- `0x18000798c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000799d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000799d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800079b4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800079b4`

## pseudocode

```c
HDPA __stdcall DPA_CreateEx(int cpGrow, HANDLE hheap)
{
  int v3; // ebx
  HANDLE ProcessHeap; // rsi
  HDPA result; // rax

  v3 = 8;
  ProcessHeap = GetProcessHeap();
  result = (HDPA)HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( result )
  {
    *((_QWORD *)result + 2) = ProcessHeap;
    if ( cpGrow >= 8 )
      v3 = cpGrow;
    *((_DWORD *)result + 7) = v3;
  }
  return result;
}

```

## disassembly

```asm
0x18000798c  mov     [rsp+arg_0], rbx
0x180007991  mov     [rsp+arg_8], rsi
0x180007996  push    rdi
0x180007997  sub     rsp, 20h
0x18000799b  mov     edi, ecx
0x18000799d  call    cs:__imp_GetProcessHeap
0x1800079a3  mov     ebx, 8
0x1800079a8  mov     rcx, rax; hHeap
0x1800079ab  mov     edx, ebx; dwFlags
0x1800079ad  mov     rsi, rax
0x1800079b0  lea     r8d, [rbx+18h]; dwBytes
0x1800079b4  call    cs:__imp_HeapAlloc
0x1800079ba  test    rax, rax
0x1800079bd  jz      short loc_1800079CB
0x1800079bf  cmp     edi, ebx
0x1800079c1  mov     [rax+10h], rsi
0x1800079c5  cmovge  ebx, edi
0x1800079c8  mov     [rax+1Ch], ebx
0x1800079cb  mov     rbx, [rsp+28h+arg_0]
0x1800079d0  mov     rsi, [rsp+28h+arg_8]
0x1800079d5  add     rsp, 20h
0x1800079d9  pop     rdi
0x1800079da  retn
```
