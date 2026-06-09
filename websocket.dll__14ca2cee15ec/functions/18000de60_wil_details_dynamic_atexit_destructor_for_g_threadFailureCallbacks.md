# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000de60`
- end: `0x18000debe`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000de60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de82`

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
0x18000de60  mov     [rsp+arg_0], rbx
0x18000de65  mov     [rsp+arg_8], rsi
0x18000de6a  push    rdi
0x18000de6b  sub     rsp, 20h
0x18000de6f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000de76  mov     rsi, [rdi]
0x18000de79  jmp     short loc_18000DE96
0x18000de7b  mov     rbx, rsi
0x18000de7e  mov     rsi, [rsi+8]
0x18000de82  call    cs:__imp_GetProcessHeap
0x18000de88  mov     r8, rbx; lpMem
0x18000de8b  xor     edx, edx; dwFlags
0x18000de8d  mov     rcx, rax; hHeap
0x18000de90  call    cs:__imp_HeapFree
0x18000de96  test    rsi, rsi
0x18000de99  jnz     short loc_18000DE7B
0x18000de9b  mov     [rdi], rsi
0x18000de9e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18000dea5  add     rdi, 8
0x18000dea9  cmp     rdi, rax
0x18000deac  jnz     short loc_18000DE76
0x18000deae  mov     rbx, [rsp+28h+arg_0]
0x18000deb3  mov     rsi, [rsp+28h+arg_8]
0x18000deb8  add     rsp, 20h
0x18000debc  pop     rdi
0x18000debd  retn
```
