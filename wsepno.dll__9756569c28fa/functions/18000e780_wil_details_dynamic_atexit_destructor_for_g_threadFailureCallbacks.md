# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000e780`
- end: `0x18000e7de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e780`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e7b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e7a2`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_InitializeResultHeader;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x18000e780  mov     [rsp+arg_0], rbx
0x18000e785  mov     [rsp+arg_8], rsi
0x18000e78a  push    rdi
0x18000e78b  sub     rsp, 20h
0x18000e78f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000e796  mov     rsi, [rdi]
0x18000e799  jmp     short loc_18000E7B6
0x18000e79b  mov     rbx, rsi
0x18000e79e  mov     rsi, [rsi+8]
0x18000e7a2  call    cs:__imp_GetProcessHeap
0x18000e7a8  mov     r8, rbx; lpMem
0x18000e7ab  xor     edx, edx; dwFlags
0x18000e7ad  mov     rcx, rax; hHeap
0x18000e7b0  call    cs:__imp_HeapFree
0x18000e7b6  test    rsi, rsi
0x18000e7b9  jnz     short loc_18000E79B
0x18000e7bb  mov     [rdi], rsi
0x18000e7be  lea     rax, g_header_init_InitializeResultHeader
0x18000e7c5  add     rdi, 8
0x18000e7c9  cmp     rdi, rax
0x18000e7cc  jnz     short loc_18000E796
0x18000e7ce  mov     rbx, [rsp+28h+arg_0]
0x18000e7d3  mov     rsi, [rsp+28h+arg_8]
0x18000e7d8  add     rsp, 20h
0x18000e7dc  pop     rdi
0x18000e7dd  retn
```
