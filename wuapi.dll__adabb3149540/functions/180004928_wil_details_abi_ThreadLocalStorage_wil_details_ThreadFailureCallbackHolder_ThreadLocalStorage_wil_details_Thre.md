# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180004928`
- end: `0x18000498e`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017150`

## callees

- `0x180004928`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004962`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004962`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004954`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004954`

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
0x180004928  mov     [rsp+arg_0], rbx
0x18000492d  mov     [rsp+arg_8], rbp
0x180004932  mov     [rsp+arg_10], rsi
0x180004937  push    rdi
0x180004938  sub     rsp, 20h
0x18000493c  lea     rbp, [rcx+50h]
0x180004940  mov     rdi, rcx
0x180004943  cmp     rcx, rbp
0x180004946  jz      short loc_180004979
0x180004948  mov     rsi, [rdi]
0x18000494b  jmp     short loc_180004968
0x18000494d  mov     rbx, rsi
0x180004950  mov     rsi, [rsi+8]
0x180004954  call    cs:__imp_GetProcessHeap
0x18000495a  mov     r8, rbx; lpMem
0x18000495d  xor     edx, edx; dwFlags
0x18000495f  mov     rcx, rax; hHeap
0x180004962  call    cs:__imp_HeapFree
0x180004968  test    rsi, rsi
0x18000496b  jnz     short loc_18000494D
0x18000496d  mov     [rdi], rsi
0x180004970  add     rdi, 8
0x180004974  cmp     rdi, rbp
0x180004977  jnz     short loc_180004948
0x180004979  mov     rbx, [rsp+28h+arg_0]
0x18000497e  mov     rbp, [rsp+28h+arg_8]
0x180004983  mov     rsi, [rsp+28h+arg_10]
0x180004988  add     rsp, 20h
0x18000498c  pop     rdi
0x18000498d  retn
```
