# DPA_CreateEx

- ea: `0x18000332c`
- end: `0x18000337b`
- name: `DPA_CreateEx`
- size: `79`
- prototype: `HDPA __stdcall(int cpGrow, HANDLE hheap)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003320`

## callees

- `0x18000332c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003354`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180003354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000333d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000333d`

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
0x18000332c  mov     [rsp+arg_0], rbx
0x180003331  mov     [rsp+arg_8], rsi
0x180003336  push    rdi
0x180003337  sub     rsp, 20h
0x18000333b  mov     edi, ecx
0x18000333d  call    cs:__imp_GetProcessHeap
0x180003343  mov     ebx, 8
0x180003348  mov     rcx, rax; hHeap
0x18000334b  mov     edx, ebx; dwFlags
0x18000334d  mov     rsi, rax
0x180003350  lea     r8d, [rbx+18h]; dwBytes
0x180003354  call    cs:__imp_HeapAlloc
0x18000335a  test    rax, rax
0x18000335d  jz      short loc_18000336B
0x18000335f  cmp     edi, ebx
0x180003361  mov     [rax+10h], rsi
0x180003365  cmovge  ebx, edi
0x180003368  mov     [rax+1Ch], ebx
0x18000336b  mov     rbx, [rsp+28h+arg_0]
0x180003370  mov     rsi, [rsp+28h+arg_8]
0x180003375  add     rsp, 20h
0x180003379  pop     rdi
0x18000337a  retn
```
