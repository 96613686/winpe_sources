# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1400156a0`
- end: `0x1400156fe`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400156a0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400156d0`
- `KERNEL32!HeapFree` at `0x1400156d0`
- `KERNEL32!GetProcessHeap` at `0x1400156c2`
- `KERNEL32!GetProcessHeap` at `0x1400156c2`

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
0x1400156a0  mov     [rsp+arg_0], rbx
0x1400156a5  mov     [rsp+arg_8], rsi
0x1400156aa  push    rdi
0x1400156ab  sub     rsp, 20h
0x1400156af  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x1400156b6  mov     rsi, [rdi]
0x1400156b9  jmp     short loc_1400156D6
0x1400156bb  mov     rbx, rsi
0x1400156be  mov     rsi, [rsi+8]
0x1400156c2  call    cs:__imp_GetProcessHeap
0x1400156c8  mov     r8, rbx; lpMem
0x1400156cb  xor     edx, edx; dwFlags
0x1400156cd  mov     rcx, rax; hHeap
0x1400156d0  call    cs:__imp_HeapFree
0x1400156d6  test    rsi, rsi
0x1400156d9  jnz     short loc_1400156BB
0x1400156db  mov     [rdi], rsi
0x1400156de  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x1400156e5  add     rdi, 8
0x1400156e9  cmp     rdi, rax
0x1400156ec  jnz     short loc_1400156B6
0x1400156ee  mov     rbx, [rsp+28h+arg_0]
0x1400156f3  mov     rsi, [rsp+28h+arg_8]
0x1400156f8  add     rsp, 20h
0x1400156fc  pop     rdi
0x1400156fd  retn
```
