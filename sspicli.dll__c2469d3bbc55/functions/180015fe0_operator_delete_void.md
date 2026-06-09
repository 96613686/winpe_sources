# operator delete(void *)

- ea: `0x180015fe0`
- end: `0x180016003`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `12`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x180010dc0`
- `0x180010ea8`
- `0x180013ca0`
- `0x180014434`
- `0x180015c60`
- `0x180015ce0`
- `0x180015d84`
- `0x180015f80`
- `0x18001600c`
- `0x18001e090`
- `0x18001eb38`
- `0x18001ec5c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015ffc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fe9`

## pseudocode

```c
void __fastcall operator delete(void *a1)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x180015fe0  push    rbx
0x180015fe2  sub     rsp, 20h
0x180015fe6  mov     rbx, rcx
0x180015fe9  call    cs:__imp_GetProcessHeap
0x180015fef  mov     r8, rbx
0x180015ff2  xor     edx, edx
0x180015ff4  mov     rcx, rax
0x180015ff7  add     rsp, 20h
0x180015ffb  pop     rbx
0x180015ffc  jmp     cs:__imp_HeapFree
```
