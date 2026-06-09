# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140014af0`
- end: `0x140014b4e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140014af0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140014b20`
- `KERNEL32!HeapFree` at `0x140014b20`
- `KERNEL32!GetProcessHeap` at `0x140014b12`
- `KERNEL32!GetProcessHeap` at `0x140014b12`

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
0x140014af0  mov     [rsp+arg_0], rbx
0x140014af5  mov     [rsp+arg_8], rsi
0x140014afa  push    rdi
0x140014afb  sub     rsp, 20h
0x140014aff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140014b06  mov     rsi, [rdi]
0x140014b09  jmp     short loc_140014B26
0x140014b0b  mov     rbx, rsi
0x140014b0e  mov     rsi, [rsi+8]
0x140014b12  call    cs:__imp_GetProcessHeap
0x140014b18  mov     r8, rbx; lpMem
0x140014b1b  xor     edx, edx; dwFlags
0x140014b1d  mov     rcx, rax; hHeap
0x140014b20  call    cs:__imp_HeapFree
0x140014b26  test    rsi, rsi
0x140014b29  jnz     short loc_140014B0B
0x140014b2b  mov     [rdi], rsi
0x140014b2e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x140014b35  add     rdi, 8
0x140014b39  cmp     rdi, rax
0x140014b3c  jnz     short loc_140014B06
0x140014b3e  mov     rbx, [rsp+28h+arg_0]
0x140014b43  mov     rsi, [rsp+28h+arg_8]
0x140014b48  add     rsp, 20h
0x140014b4c  pop     rdi
0x140014b4d  retn
```
