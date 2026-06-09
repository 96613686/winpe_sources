# wistd::unique_ptr<void,wil::process_heap_deleter>::reset(void *)

- ea: `0x14000b060`
- end: `0x14000b091`
- name: `?reset@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAAXPEAX@Z`
- size: `49`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x140046064`
- `0x1400460e0`
- `0x1400461ac`
- `0x1400480e0`
- `0x140048230`
- `0x140048c04`
- `0x140048f18`
- `0x1400497dc`
- `0x14004a000`
- `0x14004af28`

## callees

- `0x14000b060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b071`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b084`

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
0x14000b060  push    rbx
0x14000b062  sub     rsp, 20h
0x14000b066  mov     rbx, [rcx]
0x14000b069  mov     [rcx], rdx
0x14000b06c  test    rbx, rbx
0x14000b06f  jz      short loc_14000B08B
0x14000b071  call    cs:__imp_GetProcessHeap
0x14000b077  mov     r8, rbx
0x14000b07a  xor     edx, edx
0x14000b07c  mov     rcx, rax
0x14000b07f  add     rsp, 20h
0x14000b083  pop     rbx
0x14000b084  jmp     cs:__imp_HeapFree
0x14000b08b  add     rsp, 20h
0x14000b08f  pop     rbx
0x14000b090  retn
```
