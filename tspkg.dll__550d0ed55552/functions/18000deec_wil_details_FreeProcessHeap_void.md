# wil::details::FreeProcessHeap(void *)

- ea: `0x18000deec`
- end: `0x18000df0f`
- name: `?FreeProcessHeap@details@wil@@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800097ac`
- `0x18000a3dc`
- `0x18000a704`
- `0x18000a858`
- `0x18000ad70`
- `0x18000b054`
- `0x18000b0f8`
- `0x18000d5bc`
- `0x18000f5f8`
- `0x18000fbfc`
- `0x180010a7c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000def5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000def5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df08`

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
0x18000deec  push    rbx
0x18000deee  sub     rsp, 20h
0x18000def2  mov     rbx, rcx
0x18000def5  call    cs:__imp_GetProcessHeap
0x18000defb  mov     r8, rbx
0x18000defe  xor     edx, edx
0x18000df00  mov     rcx, rax
0x18000df03  add     rsp, 20h
0x18000df07  pop     rbx
0x18000df08  jmp     cs:__imp_HeapFree
```
