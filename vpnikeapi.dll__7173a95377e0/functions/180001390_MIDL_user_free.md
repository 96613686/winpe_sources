# MIDL_user_free

- ea: `0x180001390`
- end: `0x1800013b7`
- name: `MIDL_user_free`
- size: `39`
- prototype: `void __stdcall(void *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800011c0`
- `0x1800022c4`
- `0x180002660`
- `0x180002f80`
- `0x180003120`
- `0x1800032c0`
- `0x180003470`
- `0x180003e30`

## callees

- `0x180001390`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000139d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000139d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800013ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800013ab`

## pseudocode

```c
void __stdcall MIDL_user_free(void *a1)
{
  HANDLE ProcessHeap; // rax

  if ( a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, a1);
  }
}

```

## disassembly

```asm
0x180001390  test    rcx, rcx
0x180001393  jz      short locret_1800013B6
0x180001395  push    rbx
0x180001396  sub     rsp, 20h
0x18000139a  mov     rbx, rcx
0x18000139d  call    cs:__imp_GetProcessHeap
0x1800013a3  mov     r8, rbx; lpMem
0x1800013a6  xor     edx, edx; dwFlags
0x1800013a8  mov     rcx, rax; hHeap
0x1800013ab  call    cs:__imp_HeapFree
0x1800013b1  add     rsp, 20h
0x1800013b5  pop     rbx
0x1800013b6  retn
```
