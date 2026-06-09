# operator delete(void *)

- ea: `0x180002714`
- end: `0x18000273b`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `5`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180001bf0`
- `0x180001c40`
- `0x180001c80`
- `0x180002bb0`
- `0x180002f10`

## callees

- `0x180002714`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000272f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000272f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002721`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002721`

## pseudocode

```c
void __fastcall operator delete(void *lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x180002714  test    rcx, rcx
0x180002717  jz      short locret_18000273A
0x180002719  push    rbx
0x18000271a  sub     rsp, 20h
0x18000271e  mov     rbx, rcx
0x180002721  call    cs:__imp_GetProcessHeap
0x180002727  mov     r8, rbx; lpMem
0x18000272a  xor     edx, edx; dwFlags
0x18000272c  mov     rcx, rax; hHeap
0x18000272f  call    cs:__imp_HeapFree
0x180002735  add     rsp, 20h
0x180002739  pop     rbx
0x18000273a  retn
```
