# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x180002c10`
- end: `0x180002c3c`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `44`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x1800029c0`
- `0x180002aa0`
- `0x180002d80`
- `0x1800032c4`
- `0x180005660`
- `0x1800058c4`
- `0x180005ad0`
- `0x180025958`
- `0x180025af0`

## callees

- `0x180002c10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c21`

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
0x180002c10  push    rbx
0x180002c12  sub     rsp, 20h
0x180002c16  mov     rbx, [rcx]
0x180002c19  mov     [rcx], rdx
0x180002c1c  test    rbx, rbx
0x180002c1f  jz      short loc_180002C36
0x180002c21  call    cs:__imp_GetProcessHeap
0x180002c27  mov     rcx, rax; hHeap
0x180002c2a  mov     r8, rbx; lpMem
0x180002c2d  xor     edx, edx; dwFlags
0x180002c2f  call    cs:__imp_HeapFree
0x180002c35  nop
0x180002c36  add     rsp, 20h
0x180002c3a  pop     rbx
0x180002c3b  retn
```
