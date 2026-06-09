# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800126b0`
- end: `0x18001270e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800126b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800126e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800126e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800126d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800126d2`

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
    result = g_header_init_InitializeStagingHeaderInternalApi;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x1800126b0  mov     [rsp+arg_0], rbx
0x1800126b5  mov     [rsp+arg_8], rsi
0x1800126ba  push    rdi
0x1800126bb  sub     rsp, 20h
0x1800126bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800126c6  mov     rsi, [rdi]
0x1800126c9  jmp     short loc_1800126E6
0x1800126cb  mov     rbx, rsi
0x1800126ce  mov     rsi, [rsi+8]
0x1800126d2  call    cs:__imp_GetProcessHeap
0x1800126d8  mov     r8, rbx; lpMem
0x1800126db  xor     edx, edx; dwFlags
0x1800126dd  mov     rcx, rax; hHeap
0x1800126e0  call    cs:__imp_HeapFree
0x1800126e6  test    rsi, rsi
0x1800126e9  jnz     short loc_1800126CB
0x1800126eb  mov     [rdi], rsi
0x1800126ee  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x1800126f5  add     rdi, 8
0x1800126f9  cmp     rdi, rax
0x1800126fc  jnz     short loc_1800126C6
0x1800126fe  mov     rbx, [rsp+28h+arg_0]
0x180012703  mov     rsi, [rsp+28h+arg_8]
0x180012708  add     rsp, 20h
0x18001270c  pop     rdi
0x18001270d  retn
```
