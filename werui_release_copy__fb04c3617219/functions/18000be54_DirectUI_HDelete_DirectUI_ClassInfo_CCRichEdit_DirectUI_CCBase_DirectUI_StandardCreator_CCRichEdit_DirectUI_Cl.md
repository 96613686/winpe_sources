# DirectUI::HDelete<DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>>(DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>> *)

- ea: `0x18000be54`
- end: `0x18000be88`
- name: `??$HDelete@V?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@DirectUI@@@DirectUI@@YAXPEAV?$ClassInfo@VCCRichEdit@@VCCBase@DirectUI@@V?$StandardCreator@VCCRichEdit@@@3@@0@@Z`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bfa0`
- `0x18000c0a0`

## callees

- `0x180018010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000be6e`
- `KERNEL32!GetProcessHeap` at `0x18000be6e`
- `KERNEL32!HeapFree` at `0x18000be81`

## pseudocode

```c
BOOL __fastcall DirectUI::HDelete<DirectUI::ClassInfo<CCRichEdit,DirectUI::CCBase,DirectUI::StandardCreator<CCRichEdit>>>(
        void *a1)
{
  HANDLE ProcessHeap; // rax

  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 144LL))(a1, 0);
  ProcessHeap = GetProcessHeap();
  return HeapFree(ProcessHeap, 0, a1);
}

```

## disassembly

```asm
0x18000be54  push    rbx
0x18000be56  sub     rsp, 20h
0x18000be5a  mov     rax, [rcx]
0x18000be5d  xor     edx, edx
0x18000be5f  mov     rbx, rcx
0x18000be62  mov     rax, [rax+90h]
0x18000be69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6e  call    cs:__imp_GetProcessHeap
0x18000be74  mov     r8, rbx
0x18000be77  xor     edx, edx
0x18000be79  mov     rcx, rax
0x18000be7c  add     rsp, 20h
0x18000be80  pop     rbx
0x18000be81  jmp     cs:__imp_HeapFree
```
