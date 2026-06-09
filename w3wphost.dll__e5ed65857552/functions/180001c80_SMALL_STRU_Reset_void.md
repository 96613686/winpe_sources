# SMALL_STRU::Reset(void)

- ea: `0x180001c80`
- end: `0x180001cc8`
- name: `?Reset@SMALL_STRU@@QEAAXXZ`
- size: `72`
- prototype: `void __fastcall(SMALL_STRU *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c30`
- `0x180002dbc`
- `0x18000315c`
- `0x180003b18`

## callees

- `0x180001c80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001c95`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ca9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001ca9`

## pseudocode

```c
void __fastcall SMALL_STRU::Reset(void **this)
{
  void *v1; // rbx
  HANDLE ProcessHeap; // rax

  v1 = *this;
  if ( *this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180001c80  mov     [rsp+arg_0], rbx
0x180001c85  push    rdi
0x180001c86  sub     rsp, 20h
0x180001c8a  mov     rbx, [rcx]
0x180001c8d  mov     rdi, rcx
0x180001c90  test    rbx, rbx
0x180001c93  jz      short loc_180001CBC
0x180001c95  call    cs:__imp_GetProcessHeap
0x180001c9c  nop     dword ptr [rax+rax+00h]
0x180001ca1  mov     r8, rbx; lpMem
0x180001ca4  xor     edx, edx; dwFlags
0x180001ca6  mov     rcx, rax; hHeap
0x180001ca9  call    cs:__imp_HeapFree
0x180001cb0  nop     dword ptr [rax+rax+00h]
0x180001cb5  mov     qword ptr [rdi], 0
0x180001cbc  mov     rbx, [rsp+28h+arg_0]
0x180001cc1  add     rsp, 20h
0x180001cc5  pop     rdi
0x180001cc6  retn
```
