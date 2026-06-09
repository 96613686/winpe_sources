# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000aff0`
- end: `0x14000b04e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000aff0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b012`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b012`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b020`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b020`

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
0x14000aff0  mov     [rsp+arg_0], rbx
0x14000aff5  mov     [rsp+arg_8], rsi
0x14000affa  push    rdi
0x14000affb  sub     rsp, 20h
0x14000afff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000b006  mov     rsi, [rdi]
0x14000b009  jmp     short loc_14000B026
0x14000b00b  mov     rbx, rsi
0x14000b00e  mov     rsi, [rsi+8]
0x14000b012  call    cs:__imp_GetProcessHeap
0x14000b018  mov     r8, rbx; lpMem
0x14000b01b  xor     edx, edx; dwFlags
0x14000b01d  mov     rcx, rax; hHeap
0x14000b020  call    cs:__imp_HeapFree
0x14000b026  test    rsi, rsi
0x14000b029  jnz     short loc_14000B00B
0x14000b02b  mov     [rdi], rsi
0x14000b02e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x14000b035  add     rdi, 8
0x14000b039  cmp     rdi, rax
0x14000b03c  jnz     short loc_14000B006
0x14000b03e  mov     rbx, [rsp+28h+arg_0]
0x14000b043  mov     rsi, [rsp+28h+arg_8]
0x14000b048  add     rsp, 20h
0x14000b04c  pop     rdi
0x14000b04d  retn
```
