# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000e910`
- end: `0x18000e96e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000e910`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e932`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e932`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e940`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e940`

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
0x18000e910  mov     [rsp+arg_0], rbx
0x18000e915  mov     [rsp+arg_8], rsi
0x18000e91a  push    rdi
0x18000e91b  sub     rsp, 20h
0x18000e91f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000e926  mov     rsi, [rdi]
0x18000e929  jmp     short loc_18000E946
0x18000e92b  mov     rbx, rsi
0x18000e92e  mov     rsi, [rsi+8]
0x18000e932  call    cs:__imp_GetProcessHeap
0x18000e938  mov     r8, rbx; lpMem
0x18000e93b  xor     edx, edx; dwFlags
0x18000e93d  mov     rcx, rax; hHeap
0x18000e940  call    cs:__imp_HeapFree
0x18000e946  test    rsi, rsi
0x18000e949  jnz     short loc_18000E92B
0x18000e94b  mov     [rdi], rsi
0x18000e94e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem
0x18000e955  add     rdi, 8
0x18000e959  cmp     rdi, rax
0x18000e95c  jnz     short loc_18000E926
0x18000e95e  mov     rbx, [rsp+28h+arg_0]
0x18000e963  mov     rsi, [rsp+28h+arg_8]
0x18000e968  add     rsp, 20h
0x18000e96c  pop     rdi
0x18000e96d  retn
```
