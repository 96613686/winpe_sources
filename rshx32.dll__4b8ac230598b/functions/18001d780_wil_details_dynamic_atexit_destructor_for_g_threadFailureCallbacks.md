# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001d780`
- end: `0x18001d7de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d780`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d7a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001d7a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d7b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001d7b0`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x18001d780  mov     [rsp+arg_0], rbx
0x18001d785  mov     [rsp+arg_8], rsi
0x18001d78a  push    rdi
0x18001d78b  sub     rsp, 20h
0x18001d78f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001d796  mov     rsi, [rdi]
0x18001d799  jmp     short loc_18001D7B6
0x18001d79b  mov     rbx, rsi
0x18001d79e  mov     rsi, [rsi+8]
0x18001d7a2  call    cs:__imp_GetProcessHeap
0x18001d7a8  mov     r8, rbx; lpMem
0x18001d7ab  xor     edx, edx; dwFlags
0x18001d7ad  mov     rcx, rax; hHeap
0x18001d7b0  call    cs:__imp_HeapFree
0x18001d7b6  test    rsi, rsi
0x18001d7b9  jnz     short loc_18001D79B
0x18001d7bb  mov     [rdi], rsi
0x18001d7be  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18001d7c5  add     rdi, 8
0x18001d7c9  cmp     rdi, rax
0x18001d7cc  jnz     short loc_18001D796
0x18001d7ce  mov     rbx, [rsp+28h+arg_0]
0x18001d7d3  mov     rsi, [rsp+28h+arg_8]
0x18001d7d8  add     rsp, 20h
0x18001d7dc  pop     rdi
0x18001d7dd  retn
```
