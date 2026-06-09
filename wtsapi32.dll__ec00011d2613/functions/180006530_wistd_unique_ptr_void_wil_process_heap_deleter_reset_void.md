# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x180006530`
- end: `0x180006561`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180006360`
- `0x18000d9d4`
- `0x180012040`

## callees

- `0x180006530`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006554`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006541`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006541`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void **a1, void *a2)
{
  void *v2; // rbx
  HANDLE ProcessHeap; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
}

```

## disassembly

```asm
0x180006530  push    rbx
0x180006532  sub     rsp, 20h
0x180006536  mov     rbx, [rcx]
0x180006539  mov     [rcx], rdx
0x18000653c  test    rbx, rbx
0x18000653f  jz      short loc_18000655B
0x180006541  call    cs:__imp_GetProcessHeap
0x180006547  mov     r8, rbx
0x18000654a  xor     edx, edx
0x18000654c  mov     rcx, rax
0x18000654f  add     rsp, 20h
0x180006553  pop     rbx
0x180006554  jmp     cs:__imp_HeapFree
0x18000655b  add     rsp, 20h
0x18000655f  pop     rbx
0x180006560  retn
```
