# SMALL_STRU::Reset(void)

- ea: `0x180001be0`
- end: `0x180001c1b`
- name: `?Reset@SMALL_STRU@@QEAAXXZ`
- size: `59`
- prototype: `void __fastcall(SMALL_STRU *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b90`
- `0x180002c20`
- `0x180002f84`
- `0x180003878`

## callees

- `0x180001be0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001bf5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180001bf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c03`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180001c03`

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
0x180001be0  mov     [rsp+arg_0], rbx
0x180001be5  push    rdi
0x180001be6  sub     rsp, 20h
0x180001bea  mov     rbx, [rcx]
0x180001bed  mov     rdi, rcx
0x180001bf0  test    rbx, rbx
0x180001bf3  jz      short loc_180001C10
0x180001bf5  call    cs:__imp_GetProcessHeap
0x180001bfb  mov     r8, rbx; lpMem
0x180001bfe  xor     edx, edx; dwFlags
0x180001c00  mov     rcx, rax; hHeap
0x180001c03  call    cs:__imp_HeapFree
0x180001c09  mov     qword ptr [rdi], 0
0x180001c10  mov     rbx, [rsp+28h+arg_0]
0x180001c15  add     rsp, 20h
0x180001c19  pop     rdi
0x180001c1a  retn
```
