# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18000fe30`
- end: `0x18000fe8e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000fe30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe60`

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
    result = &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse;
    v0 += 8;
  }
  while ( v0 != &g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse );
  return result;
}

```

## disassembly

```asm
0x18000fe30  mov     [rsp+arg_0], rbx
0x18000fe35  mov     [rsp+arg_8], rsi
0x18000fe3a  push    rdi
0x18000fe3b  sub     rsp, 20h
0x18000fe3f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18000fe46  mov     rsi, [rdi]
0x18000fe49  jmp     short loc_18000FE66
0x18000fe4b  mov     rbx, rsi
0x18000fe4e  mov     rsi, [rsi+8]
0x18000fe52  call    cs:__imp_GetProcessHeap
0x18000fe58  mov     r8, rbx; lpMem
0x18000fe5b  xor     edx, edx; dwFlags
0x18000fe5d  mov     rcx, rax; hHeap
0x18000fe60  call    cs:__imp_HeapFree
0x18000fe66  test    rsi, rsi
0x18000fe69  jnz     short loc_18000FE4B
0x18000fe6b  mov     [rdi], rsi
0x18000fe6e  lea     rax, g_header_init_WilInitialize_ResultMacros_DesktopOrSystem_SuppressPrivateApiUse
0x18000fe75  add     rdi, 8
0x18000fe79  cmp     rdi, rax
0x18000fe7c  jnz     short loc_18000FE46
0x18000fe7e  mov     rbx, [rsp+28h+arg_0]
0x18000fe83  mov     rsi, [rsp+28h+arg_8]
0x18000fe88  add     rsp, 20h
0x18000fe8c  pop     rdi
0x18000fe8d  retn
```
