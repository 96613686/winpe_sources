# std::unique_ptr<uchar [0],std::default_delete<uchar [0]>>::~unique_ptr<uchar [0],std::default_delete<uchar [0]>>(void)

- ea: `0x1800096f0`
- end: `0x18000971e`
- name: `??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `void(void *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180009490`
- `0x1800094d0`
- `0x180009568`
- `0x18000ebe0`
- `0x18002bf50`
- `0x18002bf70`
- `0x18002bf90`
- `0x18002c550`
- `0x18002c5b0`
- `0x18002c670`
- `0x18002c6d0`
- `0x18002c730`
- `0x18002c790`

## callees

- `0x1800096f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009711`

## pseudocode

```c
void __fastcall std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(void **a1)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
}

```

## disassembly

```asm
0x1800096f0  push    rbx
0x1800096f2  sub     rsp, 20h
0x1800096f6  mov     rbx, [rcx]
0x1800096f9  test    rbx, rbx
0x1800096fc  jz      short loc_180009718
0x1800096fe  call    cs:__imp_GetProcessHeap
0x180009704  mov     r8, rbx
0x180009707  xor     edx, edx
0x180009709  mov     rcx, rax
0x18000970c  add     rsp, 20h
0x180009710  pop     rbx
0x180009711  jmp     cs:__imp_HeapFree
0x180009718  add     rsp, 20h
0x18000971c  pop     rbx
0x18000971d  retn
```
