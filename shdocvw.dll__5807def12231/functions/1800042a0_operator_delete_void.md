# operator delete(void *)

- ea: `0x1800042a0`
- end: `0x1800042c7`
- name: `??3@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `6`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800086f0`
- `0x180008700`
- `0x180014b44`
- `0x180014b60`
- `0x180024790`
- `0x1800248f0`

## callees

- `0x1800042a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042bb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800042bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042ad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800042ad`

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
0x1800042a0  test    rcx, rcx
0x1800042a3  jz      short locret_1800042C6
0x1800042a5  push    rbx
0x1800042a6  sub     rsp, 20h
0x1800042aa  mov     rbx, rcx
0x1800042ad  call    cs:__imp_GetProcessHeap
0x1800042b3  mov     r8, rbx; lpMem
0x1800042b6  xor     edx, edx; dwFlags
0x1800042b8  mov     rcx, rax; hHeap
0x1800042bb  call    cs:__imp_HeapFree
0x1800042c1  add     rsp, 20h
0x1800042c5  pop     rbx
0x1800042c6  retn
```
