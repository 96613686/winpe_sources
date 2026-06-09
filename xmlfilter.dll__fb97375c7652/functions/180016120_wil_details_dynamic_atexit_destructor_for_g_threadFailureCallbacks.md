# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x180016120`
- end: `0x18001617e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180016120`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016150`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016150`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016142`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016142`

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
0x180016120  mov     [rsp+arg_0], rbx
0x180016125  mov     [rsp+arg_8], rsi
0x18001612a  push    rdi
0x18001612b  sub     rsp, 20h
0x18001612f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180016136  mov     rsi, [rdi]
0x180016139  jmp     short loc_180016156
0x18001613b  mov     rbx, rsi
0x18001613e  mov     rsi, [rsi+8]
0x180016142  call    cs:__imp_GetProcessHeap
0x180016148  mov     r8, rbx; lpMem
0x18001614b  xor     edx, edx; dwFlags
0x18001614d  mov     rcx, rax; hHeap
0x180016150  call    cs:__imp_HeapFree
0x180016156  test    rsi, rsi
0x180016159  jnz     short loc_18001613B
0x18001615b  mov     [rdi], rsi
0x18001615e  lea     rax, g_header_init_InitializeResultHeader
0x180016165  add     rdi, 8
0x180016169  cmp     rdi, rax
0x18001616c  jnz     short loc_180016136
0x18001616e  mov     rbx, [rsp+28h+arg_0]
0x180016173  mov     rsi, [rsp+28h+arg_8]
0x180016178  add     rsp, 20h
0x18001617c  pop     rdi
0x18001617d  retn
```
