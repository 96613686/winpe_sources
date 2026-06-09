# wil::details::FreeProcessHeap(void *)

- ea: `0x180019424`
- end: `0x180019452`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `46`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x18001832c`
- `0x180018898`
- `0x180018964`
- `0x1800189a0`
- `0x180018a24`
- `0x18001a624`
- `0x18001a74c`
- `0x18001b168`
- `0x18001b450`
- `0x18001ba74`
- `0x18001c904`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019446`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001942d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001942d`

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
0x180019424  push    rbx
0x180019426  sub     rsp, 20h
0x18001942a  mov     rbx, rcx
0x18001942d  call    cs:__imp_GetProcessHeap
0x180019434  nop     dword ptr [rax+rax+00h]
0x180019439  mov     r8, rbx
0x18001943c  xor     edx, edx
0x18001943e  mov     rcx, rax
0x180019441  add     rsp, 20h
0x180019445  pop     rbx
0x180019446  jmp     cs:__imp_HeapFree
```
