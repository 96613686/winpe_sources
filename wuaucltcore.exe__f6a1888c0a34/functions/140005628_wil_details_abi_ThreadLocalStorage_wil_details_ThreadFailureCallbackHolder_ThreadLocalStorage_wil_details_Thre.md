# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140005628`
- end: `0x14000568e`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140022010`

## callees

- `0x140005628`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005662`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005662`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005654`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005654`

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
0x140005628  mov     [rsp+arg_0], rbx
0x14000562d  mov     [rsp+arg_8], rbp
0x140005632  mov     [rsp+arg_10], rsi
0x140005637  push    rdi
0x140005638  sub     rsp, 20h
0x14000563c  lea     rbp, [rcx+50h]
0x140005640  mov     rdi, rcx
0x140005643  cmp     rcx, rbp
0x140005646  jz      short loc_140005679
0x140005648  mov     rsi, [rdi]
0x14000564b  jmp     short loc_140005668
0x14000564d  mov     rbx, rsi
0x140005650  mov     rsi, [rsi+8]
0x140005654  call    cs:__imp_GetProcessHeap
0x14000565a  mov     r8, rbx; lpMem
0x14000565d  xor     edx, edx; dwFlags
0x14000565f  mov     rcx, rax; hHeap
0x140005662  call    cs:__imp_HeapFree
0x140005668  test    rsi, rsi
0x14000566b  jnz     short loc_14000564D
0x14000566d  mov     [rdi], rsi
0x140005670  add     rdi, 8
0x140005674  cmp     rdi, rbp
0x140005677  jnz     short loc_140005648
0x140005679  mov     rbx, [rsp+28h+arg_0]
0x14000567e  mov     rbp, [rsp+28h+arg_8]
0x140005683  mov     rsi, [rsp+28h+arg_10]
0x140005688  add     rsp, 20h
0x14000568c  pop     rdi
0x14000568d  retn
```
