# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180029fa0`
- end: `0x180029ffe`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180029fa0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180029fc2`
- `KERNEL32!GetProcessHeap` at `0x180029fc2`
- `KERNEL32!HeapFree` at `0x180029fd0`
- `KERNEL32!HeapFree` at `0x180029fd0`

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
    result = &g_header_init_InitializeResultHeader;
    v0 += 8;
  }
  while ( v0 != &g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x180029fa0  mov     [rsp+arg_0], rbx
0x180029fa5  mov     [rsp+arg_8], rsi
0x180029faa  push    rdi
0x180029fab  sub     rsp, 20h
0x180029faf  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180029fb6  mov     rsi, [rdi]
0x180029fb9  jmp     short loc_180029FD6
0x180029fbb  mov     rbx, rsi
0x180029fbe  mov     rsi, [rsi+8]
0x180029fc2  call    cs:__imp_GetProcessHeap
0x180029fc8  mov     r8, rbx; lpMem
0x180029fcb  xor     edx, edx; dwFlags
0x180029fcd  mov     rcx, rax; hHeap
0x180029fd0  call    cs:__imp_HeapFree
0x180029fd6  test    rsi, rsi
0x180029fd9  jnz     short loc_180029FBB
0x180029fdb  mov     [rdi], rsi
0x180029fde  lea     rax, g_header_init_InitializeResultHeader
0x180029fe5  add     rdi, 8
0x180029fe9  cmp     rdi, rax
0x180029fec  jnz     short loc_180029FB6
0x180029fee  mov     rbx, [rsp+28h+arg_0]
0x180029ff3  mov     rsi, [rsp+28h+arg_8]
0x180029ff8  add     rsp, 20h
0x180029ffc  pop     rdi
0x180029ffd  retn
```
