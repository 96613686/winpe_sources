# Free_SECONDARYLOGONINFOW

- ea: `0x180002f70`
- end: `0x180002fbc`
- name: `Free_SECONDARYLOGONINFOW`
- size: `76`
- prototype: `int __fastcall(LPVOID *lpMem)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180001160`
- `0x180002b40`
- `0x180002d80`

## callees

- `0x180002f70`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f7d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f7d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f9d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fab`

## pseudocode

```c
int __fastcall Free_SECONDARYLOGONINFOW(LPVOID *lpMem)
{
  HANDLE ProcessHeap; // rax
  void *v3; // rdi

  ProcessHeap = GetProcessHeap();
  v3 = ProcessHeap;
  if ( ProcessHeap && lpMem )
  {
    if ( *lpMem )
      HeapFree(ProcessHeap, 0, *lpMem);
    LODWORD(ProcessHeap) = HeapFree(v3, 0, lpMem);
  }
  return (int)ProcessHeap;
}

```

## disassembly

```asm
0x180002f70  mov     [rsp+arg_0], rbx
0x180002f75  push    rdi
0x180002f76  sub     rsp, 20h
0x180002f7a  mov     rbx, rcx
0x180002f7d  call    cs:__imp_GetProcessHeap
0x180002f83  mov     rdi, rax
0x180002f86  test    rax, rax
0x180002f89  jz      short loc_180002FB1
0x180002f8b  test    rbx, rbx
0x180002f8e  jz      short loc_180002FB1
0x180002f90  mov     r8, [rbx]; lpMem
0x180002f93  test    r8, r8
0x180002f96  jz      short loc_180002FA3
0x180002f98  xor     edx, edx; dwFlags
0x180002f9a  mov     rcx, rax; hHeap
0x180002f9d  call    cs:__imp_HeapFree
0x180002fa3  mov     r8, rbx; lpMem
0x180002fa6  xor     edx, edx; dwFlags
0x180002fa8  mov     rcx, rdi; hHeap
0x180002fab  call    cs:__imp_HeapFree
0x180002fb1  mov     rbx, [rsp+28h+arg_0]
0x180002fb6  add     rsp, 20h
0x180002fba  pop     rdi
0x180002fbb  retn
```
