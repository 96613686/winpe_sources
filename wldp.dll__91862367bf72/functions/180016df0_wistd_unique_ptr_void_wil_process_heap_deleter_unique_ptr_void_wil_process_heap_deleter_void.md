# wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(void)

- ea: `0x180016df0`
- end: `0x180016e20`
- name: `??1?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@XZ`
- size: `48`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: ``

## callers

- `0x18003e0d0`
- `0x18003e110`
- `0x18003e190`
- `0x18003e1d0`
- `0x18003e210`
- `0x18003e3f0`
- `0x18003e770`
- `0x18003e88a`
- `0x18003e9a4`
- `0x18003e9f0`
- `0x18003ea8b`
- `0x18003eac9`
- `0x18003eb19`
- `0x18003f069`
- `0x18003f0b9`
- `0x18003f0f3`
- `0x18003f250`
- `0x18003f3c6`
- `0x18003fcc3`

## callees

- `0x180016df0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016e13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016e13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016e05`

## pseudocode

```c
void __fastcall wistd::unique_ptr<void,wil::process_heap_deleter>::~unique_ptr<void,wil::process_heap_deleter>(
        void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  *a1 = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x180016df0  push    rbx
0x180016df2  sub     rsp, 20h
0x180016df6  mov     rbx, [rcx]
0x180016df9  mov     qword ptr [rcx], 0
0x180016e00  test    rbx, rbx
0x180016e03  jz      short loc_180016E1A
0x180016e05  call    cs:__imp_GetProcessHeap
0x180016e0b  mov     rcx, rax; hHeap
0x180016e0e  mov     r8, rbx; lpMem
0x180016e11  xor     edx, edx; dwFlags
0x180016e13  call    cs:__imp_HeapFree
0x180016e19  nop
0x180016e1a  add     rsp, 20h
0x180016e1e  pop     rbx
0x180016e1f  retn
```
