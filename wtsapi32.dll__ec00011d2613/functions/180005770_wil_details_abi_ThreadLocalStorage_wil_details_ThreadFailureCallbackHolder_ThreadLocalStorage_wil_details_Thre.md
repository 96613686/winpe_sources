# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180005770`
- end: `0x1800057e6`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015a80`

## callees

- `0x180005770`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800057b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800057a7`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rbx
  _QWORD *v3; // rsi
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v3 = (_QWORD *)v3[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      while ( v3 );
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180005770  mov     [rsp+arg_18], rbx
0x180005775  push    rbp
0x180005776  sub     rsp, 20h
0x18000577a  lea     rbp, [rcx+50h]
0x18000577e  mov     rbx, rcx
0x180005781  cmp     rcx, rbp
0x180005784  jz      short loc_1800057DB
0x180005786  mov     [rsp+28h+arg_0], rsi
0x18000578b  mov     [rsp+28h+arg_8], rdi
0x180005790  mov     [rsp+28h+arg_10], r14
0x180005795  xor     r14d, r14d
0x180005798  mov     rsi, [rbx]
0x18000579b  test    rsi, rsi
0x18000579e  jz      short loc_1800057C0
0x1800057a0  mov     rdi, rsi
0x1800057a3  mov     rsi, [rsi+8]
0x1800057a7  call    cs:__imp_GetProcessHeap
0x1800057ad  mov     r8, rdi; lpMem
0x1800057b0  xor     edx, edx; dwFlags
0x1800057b2  mov     rcx, rax; hHeap
0x1800057b5  call    cs:__imp_HeapFree
0x1800057bb  test    rsi, rsi
0x1800057be  jnz     short loc_1800057A0
0x1800057c0  mov     [rbx], r14
0x1800057c3  add     rbx, 8
0x1800057c7  cmp     rbx, rbp
0x1800057ca  jnz     short loc_180005798
0x1800057cc  mov     r14, [rsp+28h+arg_10]
0x1800057d1  mov     rdi, [rsp+28h+arg_8]
0x1800057d6  mov     rsi, [rsp+28h+arg_0]
0x1800057db  mov     rbx, [rsp+28h+arg_18]
0x1800057e0  add     rsp, 20h
0x1800057e4  pop     rbp
0x1800057e5  retn
```
