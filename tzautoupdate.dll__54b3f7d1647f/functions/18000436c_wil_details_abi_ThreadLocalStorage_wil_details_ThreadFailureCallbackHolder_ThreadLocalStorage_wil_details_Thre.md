# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000436c`
- end: `0x1800043bb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c780`

## callees

- `0x18000436c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000438d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000438d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000439b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000439b`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18000436c  push    rbx
0x18000436e  push    rbp
0x18000436f  push    rsi
0x180004370  push    rdi
0x180004371  sub     rsp, 28h
0x180004375  lea     rbp, [rcx+50h]
0x180004379  mov     rdi, rcx
0x18000437c  cmp     rcx, rbp
0x18000437f  jz      short loc_1800043B2
0x180004381  mov     rsi, [rdi]
0x180004384  jmp     short loc_1800043A1
0x180004386  mov     rbx, rsi
0x180004389  mov     rsi, [rsi+8]
0x18000438d  call    cs:__imp_GetProcessHeap
0x180004393  mov     r8, rbx; lpMem
0x180004396  xor     edx, edx; dwFlags
0x180004398  mov     rcx, rax; hHeap
0x18000439b  call    cs:__imp_HeapFree
0x1800043a1  test    rsi, rsi
0x1800043a4  jnz     short loc_180004386
0x1800043a6  mov     [rdi], rsi
0x1800043a9  add     rdi, 8
0x1800043ad  cmp     rdi, rbp
0x1800043b0  jnz     short loc_180004381
0x1800043b2  add     rsp, 28h
0x1800043b6  pop     rdi
0x1800043b7  pop     rsi
0x1800043b8  pop     rbp
0x1800043b9  pop     rbx
0x1800043ba  retn
```
