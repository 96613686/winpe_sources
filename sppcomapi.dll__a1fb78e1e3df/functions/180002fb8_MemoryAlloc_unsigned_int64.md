# MemoryAlloc(unsigned __int64)

- ea: `0x180002fb8`
- end: `0x180002fe6`
- name: `?MemoryAlloc@@YAPEAX_K@Z`
- size: `46`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fc1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002fda`

## pseudocode

```c
LPVOID __fastcall MemoryAlloc(SIZE_T a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180002fb8  push    rbx
0x180002fba  sub     rsp, 20h
0x180002fbe  mov     rbx, rcx
0x180002fc1  call    cs:__imp_GetProcessHeap
0x180002fc8  nop     dword ptr [rax+rax+00h]
0x180002fcd  mov     r8, rbx
0x180002fd0  xor     edx, edx
0x180002fd2  mov     rcx, rax
0x180002fd5  add     rsp, 20h
0x180002fd9  pop     rbx
0x180002fda  jmp     cs:__imp_HeapAlloc
```
