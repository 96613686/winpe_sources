# DeleteMofEvent(_MOF_EVENT *)

- ea: `0x140029f84`
- end: `0x140029fd2`
- name: `?DeleteMofEvent@@YAXPEAU_MOF_EVENT@@@Z`
- size: `78`
- prototype: `void __fastcall(struct _MOF_EVENT *lpMem)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14001c320`
- `0x14002be9c`

## callees

- `0x140029f84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029fc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029fad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140029fc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029fb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029f9f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140029fb3`

## pseudocode

```c
void __fastcall DeleteMofEvent(struct _MOF_EVENT *lpMem)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  HANDLE v4; // rax

  if ( lpMem )
  {
    v1 = (void *)*((_QWORD *)lpMem + 13);
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    v4 = GetProcessHeap();
    HeapFree(v4, 0, lpMem);
  }
}

```

## disassembly

```asm
0x140029f84  test    rcx, rcx
0x140029f87  jz      short locret_140029FD1
0x140029f89  mov     [rsp+arg_0], rbx
0x140029f8e  push    rdi
0x140029f8f  sub     rsp, 20h
0x140029f93  mov     rdi, [rcx+68h]
0x140029f97  mov     rbx, rcx
0x140029f9a  test    rdi, rdi
0x140029f9d  jz      short loc_140029FB3
0x140029f9f  call    cs:__imp_GetProcessHeap
0x140029fa5  mov     r8, rdi; lpMem
0x140029fa8  xor     edx, edx; dwFlags
0x140029faa  mov     rcx, rax; hHeap
0x140029fad  call    cs:__imp_HeapFree
0x140029fb3  call    cs:__imp_GetProcessHeap
0x140029fb9  mov     r8, rbx; lpMem
0x140029fbc  xor     edx, edx; dwFlags
0x140029fbe  mov     rcx, rax; hHeap
0x140029fc1  call    cs:__imp_HeapFree
0x140029fc7  mov     rbx, [rsp+28h+arg_0]
0x140029fcc  add     rsp, 20h
0x140029fd0  pop     rdi
0x140029fd1  retn
```
