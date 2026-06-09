# wil::details::FreeProcessHeap(void *)

- ea: `0x180014b2c`
- end: `0x180014b4f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e9fc`
- `0x18000ec34`
- `0x180010d98`
- `0x180010f6c`
- `0x18001102c`
- `0x180011138`
- `0x1800111dc`
- `0x180011768`
- `0x1800117c8`
- `0x180012390`
- `0x1800158f8`
- `0x180015a1c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014b48`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014b35`

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
0x180014b2c  push    rbx
0x180014b2e  sub     rsp, 20h
0x180014b32  mov     rbx, rcx
0x180014b35  call    cs:__imp_GetProcessHeap
0x180014b3b  mov     r8, rbx
0x180014b3e  xor     edx, edx
0x180014b40  mov     rcx, rax
0x180014b43  add     rsp, 20h
0x180014b47  pop     rbx
0x180014b48  jmp     cs:__imp_HeapFree
```
