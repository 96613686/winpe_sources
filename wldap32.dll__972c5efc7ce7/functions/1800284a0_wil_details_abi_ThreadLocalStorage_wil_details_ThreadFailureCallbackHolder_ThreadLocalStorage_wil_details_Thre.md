# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800284a0`
- end: `0x180028525`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180028480`

## callees

- `0x1800284a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800284fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800284fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028512`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028512`

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
0x1800284a0  mov     [rsp+arg_18], rbx
0x1800284a5  push    rbp
0x1800284a6  sub     rsp, 20h
0x1800284aa  lea     rbp, [rcx+50h]
0x1800284ae  mov     rbx, rcx
0x1800284b1  cmp     rcx, rbp
0x1800284b4  jz      short loc_1800284EB
0x1800284b6  mov     [rsp+28h+arg_0], rsi
0x1800284bb  mov     [rsp+28h+arg_8], rdi
0x1800284c0  mov     [rsp+28h+arg_10], r14
0x1800284c5  xor     r14d, r14d
0x1800284c8  mov     rsi, [rbx]
0x1800284cb  test    rsi, rsi
0x1800284ce  jnz     short loc_1800284F7
0x1800284d0  mov     [rbx], r14
0x1800284d3  add     rbx, 8
0x1800284d7  cmp     rbx, rbp
0x1800284da  jnz     short loc_1800284C8
0x1800284dc  mov     r14, [rsp+28h+arg_10]
0x1800284e1  mov     rdi, [rsp+28h+arg_8]
0x1800284e6  mov     rsi, [rsp+28h+arg_0]
0x1800284eb  mov     rbx, [rsp+28h+arg_18]
0x1800284f0  add     rsp, 20h
0x1800284f4  pop     rbp
0x1800284f5  retn
0x1800284f7  mov     rdi, rsi
0x1800284fa  mov     rsi, [rsi+8]
0x1800284fe  call    cs:__imp_GetProcessHeap
0x180028505  nop     dword ptr [rax+rax+00h]
0x18002850a  mov     r8, rdi; lpMem
0x18002850d  xor     edx, edx; dwFlags
0x18002850f  mov     rcx, rax; hHeap
0x180028512  call    cs:__imp_HeapFree
0x180028519  nop     dword ptr [rax+rax+00h]
0x18002851e  test    rsi, rsi
0x180028521  jnz     short loc_1800284F7
0x180028523  jmp     short loc_1800284D0
```
