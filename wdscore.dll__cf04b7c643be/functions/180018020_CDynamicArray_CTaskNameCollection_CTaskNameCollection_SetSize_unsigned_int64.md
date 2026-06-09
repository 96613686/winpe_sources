# CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(unsigned __int64)

- ea: `0x180018020`
- end: `0x1800180a9`
- name: `?SetSize@?$CDynamicArray@PEAVCTaskNameCollection@@PEAPEAV1@@@QEAAH_K@Z`
- size: `137`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000fcac`
- `0x180012704`
- `0x1800128dc`
- `0x180012d1c`
- `0x180013068`
- `0x18001ab98`
- `0x18001bb80`
- `0x18001bc90`

## callees

- `0x180018020`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001806b`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18001806b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001807c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18001807c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001804f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001804f`

## pseudocode

```c
__int64 __fastcall CDynamicArray<CTaskNameCollection *,CTaskNameCollection * *>::SetSize(
        __int64 a1,
        unsigned __int64 a2)
{
  void *v4; // rbp
  unsigned __int64 v5; // rsi
  HANDLE ProcessHeap; // rax
  __int64 result; // rax

  if ( *(_QWORD *)(a1 + 16) >= a2 )
  {
    *(_QWORD *)(a1 + 8) = a2;
    return 1;
  }
  v4 = *(void **)a1;
  v5 = a2 + *(_QWORD *)(a1 + 24);
  ProcessHeap = GetProcessHeap();
  if ( v4 )
    result = (__int64)HeapReAlloc(ProcessHeap, 0, v4, 8 * v5);
  else
    result = (__int64)HeapAlloc(ProcessHeap, 0, 8 * v5);
  if ( result )
  {
    *(_QWORD *)(a1 + 16) = v5;
    *(_QWORD *)(a1 + 8) = a2;
    *(_QWORD *)a1 = result;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x180018020  push    rbx
0x180018022  push    rbp
0x180018023  push    rsi
0x180018024  push    rdi
0x180018025  push    r14
0x180018027  sub     rsp, 20h
0x18001802b  mov     rdi, rdx
0x18001802e  mov     rbx, rcx
0x180018031  cmp     [rcx+10h], rdx
0x180018035  jb      short loc_18001803D
0x180018037  mov     [rcx+8], rdx
0x18001803b  jmp     short loc_180018098
0x18001803d  mov     rsi, [rcx+18h]
0x180018041  mov     rbp, [rcx]
0x180018044  add     rsi, rdi
0x180018047  lea     r14, ds:0[rsi*8]
0x18001804f  call    cs:__imp_GetProcessHeap
0x180018056  nop     dword ptr [rax+rax+00h]
0x18001805b  xor     edx, edx; dwFlags
0x18001805d  mov     rcx, rax; hHeap
0x180018060  test    rbp, rbp
0x180018063  jz      short loc_180018079
0x180018065  mov     r9, r14; dwBytes
0x180018068  mov     r8, rbp; lpMem
0x18001806b  call    cs:__imp_HeapReAlloc
0x180018072  nop     dword ptr [rax+rax+00h]
0x180018077  jmp     short loc_180018088
0x180018079  mov     r8, r14; dwBytes
0x18001807c  call    cs:__imp_HeapAlloc
0x180018083  nop     dword ptr [rax+rax+00h]
0x180018088  test    rax, rax
0x18001808b  jz      short loc_18001809D
0x18001808d  mov     [rbx+10h], rsi
0x180018091  mov     [rbx+8], rdi
0x180018095  mov     [rbx], rax
0x180018098  mov     eax, 1
0x18001809d  add     rsp, 20h
0x1800180a1  pop     r14
0x1800180a3  pop     rdi
0x1800180a4  pop     rsi
0x1800180a5  pop     rbp
0x1800180a6  pop     rbx
0x1800180a7  retn
```
