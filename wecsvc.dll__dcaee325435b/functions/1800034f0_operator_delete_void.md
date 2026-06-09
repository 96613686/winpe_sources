# operator delete(void *)

- ea: `0x1800034f0`
- end: `0x180003513`
- name: `??3@YAXPEAX@Z`
- size: `35`
- prototype: `void __fastcall(void *)`
- caller_count: `63`
- callee_count: `0`
- tags: `file_ops`

## callers

- `0x1800011c0`
- `0x180001200`
- `0x1800018e0`
- `0x180001e20`
- `0x180001fec`
- `0x180002560`
- `0x180002b78`
- `0x180003e10`
- `0x1800061b0`
- `0x1800062d4`
- `0x180006334`
- `0x180006370`
- `0x1800063b8`
- `0x180008014`
- `0x180008038`
- `0x1800086b0`
- `0x1800086f0`
- `0x180008730`
- `0x180008770`
- `0x1800087b0`
- `0x1800087f0`
- `0x180009a10`
- `0x18000c724`
- `0x180010624`
- `0x18001064c`
- `0x1800106ac`
- `0x180010780`
- `0x180010800`
- `0x180010894`
- `0x180010c48`
- `0x180012e90`
- `0x180012ec0`
- `0x18001334c`
- `0x180013370`
- `0x1800133c0`
- `0x180013450`
- `0x180013794`
- `0x180015430`
- `0x180015530`
- `0x180015570`
- `0x1800155b0`
- `0x180018dc8`
- `0x180018e28`
- `0x18001926c`
- `0x180019308`
- `0x1800195c8`
- `0x18001a864`
- `0x18001c298`
- `0x18001c378`
- `0x18001ccb0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800034f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000350c`

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
0x1800034f0  push    rbx
0x1800034f2  sub     rsp, 20h
0x1800034f6  mov     rbx, rcx
0x1800034f9  call    cs:__imp_GetProcessHeap
0x1800034ff  mov     r8, rbx
0x180003502  xor     edx, edx
0x180003504  mov     rcx, rax
0x180003507  add     rsp, 20h
0x18000350b  pop     rbx
0x18000350c  jmp     cs:__imp_HeapFree
```
