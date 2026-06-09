# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x14000b380`
- end: `0x14000b3de`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000b380`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b3b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b3a2`

## pseudocode

```c
char *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  char *v0; // rdi
  _QWORD *v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  char *result; // rax

  v0 = (char *)wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *(_QWORD **)v0;
    while ( v1 )
    {
      v2 = v1;
      v1 = (_QWORD *)v1[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *(_QWORD *)v0 = 0;
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem );
  return result;
}

```

## disassembly

```asm
0x14000b380  mov     [rsp+arg_0], rbx
0x14000b385  mov     [rsp+arg_8], rsi
0x14000b38a  push    rdi
0x14000b38b  sub     rsp, 20h
0x14000b38f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x14000b396  mov     rsi, [rdi]
0x14000b399  jmp     short loc_14000B3B6
0x14000b39b  mov     rbx, rsi
0x14000b39e  mov     rsi, [rsi+8]
0x14000b3a2  call    cs:__imp_GetProcessHeap
0x14000b3a8  mov     r8, rbx; lpMem
0x14000b3ab  xor     edx, edx; dwFlags
0x14000b3ad  mov     rcx, rax; hHeap
0x14000b3b0  call    cs:__imp_HeapFree
0x14000b3b6  test    rsi, rsi
0x14000b3b9  jnz     short loc_14000B39B
0x14000b3bb  mov     [rdi], rsi
0x14000b3be  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x14000b3c5  add     rdi, 8
0x14000b3c9  cmp     rdi, rax
0x14000b3cc  jnz     short loc_14000B396
0x14000b3ce  mov     rbx, [rsp+28h+arg_0]
0x14000b3d3  mov     rsi, [rsp+28h+arg_8]
0x14000b3d8  add     rsp, 20h
0x14000b3dc  pop     rdi
0x14000b3dd  retn
```
