# DPA_Create

- ea: `0x180008c10`
- end: `0x180008c61`
- name: `DPA_Create`
- size: `81`
- prototype: `HDPA __stdcall(int cItemGrow)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ff0`
- `0x180006ba0`
- `0x180008640`
- `0x18000ad20`
- `0x18000bc90`
- `0x180014d90`

## callees

- `0x180008c10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008c3a`

## pseudocode

```c
HDPA __stdcall DPA_Create(int cItemGrow)
{
  int v2; // ebx
  HANDLE ProcessHeap; // rdi
  HDPA result; // rax

  v2 = 8;
  ProcessHeap = GetProcessHeap();
  result = (HDPA)HeapAlloc(ProcessHeap, 8u, 0x20u);
  if ( result )
  {
    *((_QWORD *)result + 2) = ProcessHeap;
    if ( cItemGrow >= 8 )
      v2 = cItemGrow;
    *((_DWORD *)result + 7) = v2;
  }
  return result;
}

```

## disassembly

```asm
0x180008c10  mov     [rsp+arg_0], rbx
0x180008c15  mov     [rsp+arg_8], rsi
0x180008c1a  push    rdi
0x180008c1b  sub     rsp, 20h
0x180008c1f  mov     esi, ecx
0x180008c21  call    cs:__imp_GetProcessHeap
0x180008c27  mov     ebx, 8
0x180008c2c  mov     r8d, 20h ; ' '; dwBytes
0x180008c32  mov     edx, ebx; dwFlags
0x180008c34  mov     rcx, rax; hHeap
0x180008c37  mov     rdi, rax
0x180008c3a  call    cs:__imp_HeapAlloc
0x180008c40  test    rax, rax
0x180008c43  jz      short loc_180008C51
0x180008c45  cmp     esi, ebx
0x180008c47  mov     [rax+10h], rdi
0x180008c4b  cmovge  ebx, esi
0x180008c4e  mov     [rax+1Ch], ebx
0x180008c51  mov     rbx, [rsp+28h+arg_0]
0x180008c56  mov     rsi, [rsp+28h+arg_8]
0x180008c5b  add     rsp, 20h
0x180008c5f  pop     rdi
0x180008c60  retn
```
