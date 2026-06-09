# wil::details::FreeProcessHeap(void *)

- ea: `0x18000882c`
- end: `0x18000884f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x180007c20`
- `0x180007cd0`
- `0x180007d9c`
- `0x180007dd0`
- `0x180007e50`
- `0x180009a80`
- `0x180009ba8`
- `0x18000a6c0`
- `0x18000a9a0`
- `0x18000af90`
- `0x18000b46c`
- `0x18000bf00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008835`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008835`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008848`

## pseudocode

```c
void __fastcall wil::details::FreeProcessHeap(wil::details *this, void *a2)
{
  HANDLE ProcessHeap; // rax

  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, this);
}

```

## disassembly

```asm
0x18000882c  push    rbx
0x18000882e  sub     rsp, 20h
0x180008832  mov     rbx, rcx
0x180008835  call    cs:__imp_GetProcessHeap
0x18000883b  mov     r8, rbx
0x18000883e  xor     edx, edx
0x180008840  mov     rcx, rax
0x180008843  add     rsp, 20h
0x180008847  pop     rbx
0x180008848  jmp     cs:__imp_HeapFree
```
