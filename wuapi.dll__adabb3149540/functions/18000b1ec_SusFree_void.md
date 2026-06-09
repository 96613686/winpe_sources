# SusFree(void *)

- ea: `0x18000b1ec`
- end: `0x18000b213`
- name: `?SusFree@@YAXPEAX@Z`
- size: `39`
- prototype: `void __fastcall(void *lpMem)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180007af4`
- `0x18000e3ec`
- `0x18000e6f8`
- `0x18000e9b0`
- `0x18000f69c`
- `0x18000fabc`
- `0x1800171d0`

## callees

- `0x18000b1ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b207`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b207`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1f9`

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
0x18000b1ec  test    rcx, rcx
0x18000b1ef  jz      short locret_18000B212
0x18000b1f1  push    rbx
0x18000b1f2  sub     rsp, 20h
0x18000b1f6  mov     rbx, rcx
0x18000b1f9  call    cs:__imp_GetProcessHeap
0x18000b1ff  mov     r8, rbx; lpMem
0x18000b202  xor     edx, edx; dwFlags
0x18000b204  mov     rcx, rax; hHeap
0x18000b207  call    cs:__imp_HeapFree
0x18000b20d  add     rsp, 20h
0x18000b211  pop     rbx
0x18000b212  retn
```
