# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140011700`
- end: `0x14001175e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140011700`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011722`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011722`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011730`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011730`

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
0x140011700  mov     [rsp+arg_0], rbx
0x140011705  mov     [rsp+arg_8], rsi
0x14001170a  push    rdi
0x14001170b  sub     rsp, 20h
0x14001170f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140011716  mov     rsi, [rdi]
0x140011719  jmp     short loc_140011736
0x14001171b  mov     rbx, rsi
0x14001171e  mov     rsi, [rsi+8]
0x140011722  call    cs:__imp_GetProcessHeap
0x140011728  mov     r8, rbx; lpMem
0x14001172b  xor     edx, edx; dwFlags
0x14001172d  mov     rcx, rax; hHeap
0x140011730  call    cs:__imp_HeapFree
0x140011736  test    rsi, rsi
0x140011739  jnz     short loc_14001171B
0x14001173b  mov     [rdi], rsi
0x14001173e  lea     rax, g_header_init_InitializeResultHeader
0x140011745  add     rdi, 8
0x140011749  cmp     rdi, rax
0x14001174c  jnz     short loc_140011716
0x14001174e  mov     rbx, [rsp+28h+arg_0]
0x140011753  mov     rsi, [rsp+28h+arg_8]
0x140011758  add     rsp, 20h
0x14001175c  pop     rdi
0x14001175d  retn
```
