# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180006850`
- end: `0x1800068ae`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180006850`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006872`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006872`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006880`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006880`

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
0x180006850  mov     [rsp+arg_0], rbx
0x180006855  mov     [rsp+arg_8], rsi
0x18000685a  push    rdi
0x18000685b  sub     rsp, 20h
0x18000685f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180006866  mov     rsi, [rdi]
0x180006869  jmp     short loc_180006886
0x18000686b  mov     rbx, rsi
0x18000686e  mov     rsi, [rsi+8]
0x180006872  call    cs:__imp_GetProcessHeap
0x180006878  mov     r8, rbx; lpMem
0x18000687b  xor     edx, edx; dwFlags
0x18000687d  mov     rcx, rax; hHeap
0x180006880  call    cs:__imp_HeapFree
0x180006886  test    rsi, rsi
0x180006889  jnz     short loc_18000686B
0x18000688b  mov     [rdi], rsi
0x18000688e  lea     rax, g_header_init_InitializeResultHeader
0x180006895  add     rdi, 8
0x180006899  cmp     rdi, rax
0x18000689c  jnz     short loc_180006866
0x18000689e  mov     rbx, [rsp+28h+arg_0]
0x1800068a3  mov     rsi, [rsp+28h+arg_8]
0x1800068a8  add     rsp, 20h
0x1800068ac  pop     rdi
0x1800068ad  retn
```
