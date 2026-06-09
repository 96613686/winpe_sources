# SusFree(void *)

- ea: `0x18000b198`
- end: `0x18000b1bf`
- name: `?SusFree@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180005d10`
- `0x18000e460`
- `0x18000e6a4`
- `0x18000e95c`
- `0x18000f64c`
- `0x18000fa6c`
- `0x180017180`

## callees

- `0x18000b198`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1a5`

## pseudocode

```c
void __fastcall SusFree(void *lpMem)
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
0x18000b198  test    rcx, rcx
0x18000b19b  jz      short locret_18000B1BE
0x18000b19d  push    rbx
0x18000b19e  sub     rsp, 20h
0x18000b1a2  mov     rbx, rcx
0x18000b1a5  call    cs:__imp_GetProcessHeap
0x18000b1ab  mov     r8, rbx; lpMem
0x18000b1ae  xor     edx, edx; dwFlags
0x18000b1b0  mov     rcx, rax; hHeap
0x18000b1b3  call    cs:__imp_HeapFree
0x18000b1b9  add     rsp, 20h
0x18000b1bd  pop     rbx
0x18000b1be  retn
```
