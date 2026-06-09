# HmmInternalAlloc(void *,void *,unsigned __int64)

- ea: `0x18003ef58`
- end: `0x18003efe7`
- name: `?HmmInternalAlloc@@YAPEAXPEAX0_K@Z`
- size: `143`
- prototype: `void *__fastcall(HANDLE hHeap, void *lpMem, unsigned __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003ee20`
- `0x18003f130`

## callees

- `0x180007bc0`
- `0x18003ef58`

## import_xrefs

- `KERNEL32!HeapCompact` at `0x18003ef9e`
- `KERNEL32!HeapCompact` at `0x18003ef9e`
- `KERNEL32!HeapReAlloc` at `0x18003ef83`
- `KERNEL32!HeapReAlloc` at `0x18003efb7`
- `KERNEL32!HeapReAlloc` at `0x18003ef83`
- `KERNEL32!HeapReAlloc` at `0x18003efb7`
- `KERNEL32!HeapAlloc` at `0x18003ef8e`
- `KERNEL32!HeapAlloc` at `0x18003efc2`
- `KERNEL32!HeapAlloc` at `0x18003ef8e`
- `KERNEL32!HeapAlloc` at `0x18003efc2`

## pseudocode

```c
LPVOID __fastcall HmmInternalAlloc(HANDLE hHeap, void *lpMem, SIZE_T a3)
{
  LPVOID result; // rax

  while ( 1 )
  {
    result = lpMem ? HeapReAlloc(hHeap, 8u, lpMem, a3) : HeapAlloc(hHeap, 8u, a3);
    if ( result )
      break;
    HeapCompact(hHeap, 0);
    result = lpMem ? HeapReAlloc(hHeap, 8u, lpMem, a3) : HeapAlloc(hHeap, 8u, a3);
    if ( result )
      break;
    UnBCL::Allocator::InvokeOOMHandler(a3);
  }
  return result;
}

```

## disassembly

```asm
0x18003ef58  mov     [rsp+arg_0], rbx
0x18003ef5d  mov     [rsp+arg_8], rsi
0x18003ef62  push    rdi
0x18003ef63  sub     rsp, 20h
0x18003ef67  mov     rbx, r8
0x18003ef6a  mov     rsi, rdx
0x18003ef6d  mov     rdi, rcx
0x18003ef70  mov     edx, 8; dwFlags
0x18003ef75  mov     rcx, rdi; hHeap
0x18003ef78  test    rsi, rsi
0x18003ef7b  jz      short loc_18003EF8B
0x18003ef7d  mov     r9, rbx; dwBytes
0x18003ef80  mov     r8, rsi; lpMem
0x18003ef83  call    cs:__imp_HeapReAlloc
0x18003ef89  jmp     short loc_18003EF94
0x18003ef8b  mov     r8, rbx; dwBytes
0x18003ef8e  call    cs:__imp_HeapAlloc
0x18003ef94  test    rax, rax
0x18003ef97  jnz     short loc_18003EFD7
0x18003ef99  xor     edx, edx; dwFlags
0x18003ef9b  mov     rcx, rdi; hHeap
0x18003ef9e  call    cs:__imp_HeapCompact
0x18003efa4  mov     edx, 8; dwFlags
0x18003efa9  mov     rcx, rdi; hHeap
0x18003efac  test    rsi, rsi
0x18003efaf  jz      short loc_18003EFBF
0x18003efb1  mov     r9, rbx; dwBytes
0x18003efb4  mov     r8, rsi; lpMem
0x18003efb7  call    cs:__imp_HeapReAlloc
0x18003efbd  jmp     short loc_18003EFC8
0x18003efbf  mov     r8, rbx; dwBytes
0x18003efc2  call    cs:__imp_HeapAlloc
0x18003efc8  test    rax, rax
0x18003efcb  jnz     short loc_18003EFD7
0x18003efcd  mov     rcx, rbx; unsigned __int64
0x18003efd0  call    ?InvokeOOMHandler@Allocator@UnBCL@@SAX_K@Z; UnBCL::Allocator::InvokeOOMHandler(unsigned __int64)
0x18003efd5  jmp     short loc_18003EF70
0x18003efd7  mov     rbx, [rsp+28h+arg_0]
0x18003efdc  mov     rsi, [rsp+28h+arg_8]
0x18003efe1  add     rsp, 20h
0x18003efe5  pop     rdi
0x18003efe6  retn
```
