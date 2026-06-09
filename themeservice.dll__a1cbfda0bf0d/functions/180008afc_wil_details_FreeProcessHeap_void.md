# wil::details::FreeProcessHeap(void *)

- ea: `0x180008afc`
- end: `0x180008b1f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18000601c`
- `0x18000654c`
- `0x180006d88`
- `0x180007094`
- `0x180007368`
- `0x18000740c`
- `0x1800096fc`
- `0x18000a848`
- `0x18000b6cc`
- `0x18000bcd4`
- `0x18000bfc8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008b18`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008b05`

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
0x180008afc  push    rbx
0x180008afe  sub     rsp, 20h
0x180008b02  mov     rbx, rcx
0x180008b05  call    cs:__imp_GetProcessHeap
0x180008b0b  mov     r8, rbx
0x180008b0e  xor     edx, edx
0x180008b10  mov     rcx, rax
0x180008b13  add     rsp, 20h
0x180008b17  pop     rbx
0x180008b18  jmp     cs:__imp_HeapFree
```
