# CHeap::CHeap(unsigned __int64,unsigned __int64,bool,bool)

- ea: `0x180001e40`
- end: `0x180001e6d`
- name: `??0CHeap@@QEAA@_K0_N1@Z`
- size: `45`
- prototype: `CHeap *__fastcall(CHeap *__hidden this, unsigned __int64, unsigned __int64, bool, bool)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180001e4b`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x180001e4b`

## pseudocode

```c
CHeap *__fastcall CHeap::CHeap(CHeap *this)
{
  CHeap *result; // rax

  g_heap = HeapCreate(0, 0, 0);
  result = (CHeap *)&g_heap;
  word_180015400 = 0;
  return result;
}

```

## disassembly

```asm
0x180001e40  sub     rsp, 28h
0x180001e44  xor     r8d, r8d; dwMaximumSize
0x180001e47  xor     edx, edx; dwInitialSize
0x180001e49  xor     ecx, ecx; flOptions
0x180001e4b  call    cs:__imp_HeapCreate
0x180001e51  mov     cs:?g_heap@@3VCHeap@@A, rax; CHeap g_heap
0x180001e58  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x180001e5f  mov     cs:word_180015400, 0
0x180001e68  add     rsp, 28h
0x180001e6c  retn
```
