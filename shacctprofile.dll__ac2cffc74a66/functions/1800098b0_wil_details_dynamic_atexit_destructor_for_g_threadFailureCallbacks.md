# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800098b0`
- end: `0x18000990e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `void *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800098b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800098d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800098e0`

## pseudocode

```c
void *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  _QWORD **v0; // rdi
  _QWORD *v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  void *result; // rax

  v0 = (_QWORD **)&wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = v1;
      v1 = (_QWORD *)v1[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    ++v0;
  }
  while ( v0 != (_QWORD **)&g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x1800098b0  mov     [rsp+arg_0], rbx
0x1800098b5  mov     [rsp+arg_8], rsi
0x1800098ba  push    rdi
0x1800098bb  sub     rsp, 20h
0x1800098bf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1800098c6  mov     rsi, [rdi]
0x1800098c9  jmp     short loc_1800098E6
0x1800098cb  mov     rbx, rsi
0x1800098ce  mov     rsi, [rsi+8]
0x1800098d2  call    cs:__imp_GetProcessHeap
0x1800098d8  mov     r8, rbx; lpMem
0x1800098db  xor     edx, edx; dwFlags
0x1800098dd  mov     rcx, rax; hHeap
0x1800098e0  call    cs:__imp_HeapFree
0x1800098e6  test    rsi, rsi
0x1800098e9  jnz     short loc_1800098CB
0x1800098eb  mov     [rdi], rsi
0x1800098ee  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1800098f5  add     rdi, 8
0x1800098f9  cmp     rdi, rax
0x1800098fc  jnz     short loc_1800098C6
0x1800098fe  mov     rbx, [rsp+28h+arg_0]
0x180009903  mov     rsi, [rsp+28h+arg_8]
0x180009908  add     rsp, 20h
0x18000990c  pop     rdi
0x18000990d  retn
```
