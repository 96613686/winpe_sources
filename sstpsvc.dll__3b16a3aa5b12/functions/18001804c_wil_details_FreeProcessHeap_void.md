# wil::details::FreeProcessHeap(void *)

- ea: `0x18001804c`
- end: `0x18001806f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800175b4`
- `0x180017680`
- `0x1800176b4`
- `0x180017734`
- `0x1800191a8`
- `0x1800192d0`
- `0x180019c6c`
- `0x180019f4c`
- `0x18001a540`
- `0x18001aad8`
- `0x18001b450`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018068`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018055`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018055`

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
0x18001804c  push    rbx
0x18001804e  sub     rsp, 20h
0x180018052  mov     rbx, rcx
0x180018055  call    cs:__imp_GetProcessHeap
0x18001805b  mov     r8, rbx
0x18001805e  xor     edx, edx
0x180018060  mov     rcx, rax
0x180018063  add     rsp, 20h
0x180018067  pop     rbx
0x180018068  jmp     cs:__imp_HeapFree
```
