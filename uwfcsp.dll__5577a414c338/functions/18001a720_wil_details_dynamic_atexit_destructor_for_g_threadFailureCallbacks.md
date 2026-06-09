# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001a720`
- end: `0x18001a77e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a720`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a742`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a742`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a750`

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
    result = g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x18001a720  mov     [rsp+arg_0], rbx
0x18001a725  mov     [rsp+arg_8], rsi
0x18001a72a  push    rdi
0x18001a72b  sub     rsp, 20h
0x18001a72f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001a736  mov     rsi, [rdi]
0x18001a739  jmp     short loc_18001A756
0x18001a73b  mov     rbx, rsi
0x18001a73e  mov     rsi, [rsi+8]
0x18001a742  call    cs:__imp_GetProcessHeap
0x18001a748  mov     r8, rbx; lpMem
0x18001a74b  xor     edx, edx; dwFlags
0x18001a74d  mov     rcx, rax; hHeap
0x18001a750  call    cs:__imp_HeapFree
0x18001a756  test    rsi, rsi
0x18001a759  jnz     short loc_18001A73B
0x18001a75b  mov     [rdi], rsi
0x18001a75e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18001a765  add     rdi, 8
0x18001a769  cmp     rdi, rax
0x18001a76c  jnz     short loc_18001A736
0x18001a76e  mov     rbx, [rsp+28h+arg_0]
0x18001a773  mov     rsi, [rsp+28h+arg_8]
0x18001a778  add     rsp, 20h
0x18001a77c  pop     rdi
0x18001a77d  retn
```
