# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000d400`
- end: `0x14000d45e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000d400`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d430`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000d430`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d422`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d422`

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
0x14000d400  mov     [rsp+arg_0], rbx
0x14000d405  mov     [rsp+arg_8], rsi
0x14000d40a  push    rdi
0x14000d40b  sub     rsp, 20h
0x14000d40f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000d416  mov     rsi, [rdi]
0x14000d419  jmp     short loc_14000D436
0x14000d41b  mov     rbx, rsi
0x14000d41e  mov     rsi, [rsi+8]
0x14000d422  call    cs:__imp_GetProcessHeap
0x14000d428  mov     r8, rbx; lpMem
0x14000d42b  xor     edx, edx; dwFlags
0x14000d42d  mov     rcx, rax; hHeap
0x14000d430  call    cs:__imp_HeapFree
0x14000d436  test    rsi, rsi
0x14000d439  jnz     short loc_14000D41B
0x14000d43b  mov     [rdi], rsi
0x14000d43e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x14000d445  add     rdi, 8
0x14000d449  cmp     rdi, rax
0x14000d44c  jnz     short loc_14000D416
0x14000d44e  mov     rbx, [rsp+28h+arg_0]
0x14000d453  mov     rsi, [rsp+28h+arg_8]
0x14000d458  add     rsp, 20h
0x14000d45c  pop     rdi
0x14000d45d  retn
```
