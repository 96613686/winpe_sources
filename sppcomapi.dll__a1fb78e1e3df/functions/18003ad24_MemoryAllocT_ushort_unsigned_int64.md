# MemoryAllocT<ushort *>(unsigned __int64)

- ea: `0x18003ad24`
- end: `0x18003ad4d`
- name: `??$MemoryAllocT@PEAG@@YAPEAPEAG_K@Z`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad28`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003ad28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003ad41`

## pseudocode

```c
LPVOID MemoryAllocT<unsigned short *>()
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  return HeapAlloc(ProcessHeap, 0, 0x18u);
}

```

## disassembly

```asm
0x18003ad24  sub     rsp, 28h
0x18003ad28  call    cs:__imp_GetProcessHeap
0x18003ad2f  nop     dword ptr [rax+rax+00h]
0x18003ad34  xor     edx, edx
0x18003ad36  mov     rcx, rax
0x18003ad39  lea     r8d, [rdx+18h]
0x18003ad3d  add     rsp, 28h
0x18003ad41  jmp     cs:__imp_HeapAlloc
```
