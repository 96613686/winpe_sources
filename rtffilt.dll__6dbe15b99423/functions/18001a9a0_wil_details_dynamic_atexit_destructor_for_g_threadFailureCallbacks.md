# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001a9a0`
- end: `0x18001a9fe`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a9a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a9c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a9c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a9d0`

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
    result = &g_header_init_InitializeStagingHeaderInternalApi;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeStagingHeaderInternalApi );
  return result;
}

```

## disassembly

```asm
0x18001a9a0  mov     [rsp+arg_0], rbx
0x18001a9a5  mov     [rsp+arg_8], rsi
0x18001a9aa  push    rdi
0x18001a9ab  sub     rsp, 20h
0x18001a9af  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001a9b6  mov     rsi, [rdi]
0x18001a9b9  jmp     short loc_18001A9D6
0x18001a9bb  mov     rbx, rsi
0x18001a9be  mov     rsi, [rsi+8]
0x18001a9c2  call    cs:__imp_GetProcessHeap
0x18001a9c8  mov     r8, rbx; lpMem
0x18001a9cb  xor     edx, edx; dwFlags
0x18001a9cd  mov     rcx, rax; hHeap
0x18001a9d0  call    cs:__imp_HeapFree
0x18001a9d6  test    rsi, rsi
0x18001a9d9  jnz     short loc_18001A9BB
0x18001a9db  mov     [rdi], rsi
0x18001a9de  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18001a9e5  add     rdi, 8
0x18001a9e9  cmp     rdi, rax
0x18001a9ec  jnz     short loc_18001A9B6
0x18001a9ee  mov     rbx, [rsp+28h+arg_0]
0x18001a9f3  mov     rsi, [rsp+28h+arg_8]
0x18001a9f8  add     rsp, 20h
0x18001a9fc  pop     rdi
0x18001a9fd  retn
```
