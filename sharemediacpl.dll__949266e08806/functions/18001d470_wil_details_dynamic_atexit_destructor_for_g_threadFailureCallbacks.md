# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001d470`
- end: `0x18001d4ce`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001d470`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001d4a0`
- `KERNEL32!HeapFree` at `0x18001d4a0`
- `KERNEL32!GetProcessHeap` at `0x18001d492`
- `KERNEL32!GetProcessHeap` at `0x18001d492`

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
0x18001d470  mov     [rsp+arg_0], rbx
0x18001d475  mov     [rsp+arg_8], rsi
0x18001d47a  push    rdi
0x18001d47b  sub     rsp, 20h
0x18001d47f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001d486  mov     rsi, [rdi]
0x18001d489  jmp     short loc_18001D4A6
0x18001d48b  mov     rbx, rsi
0x18001d48e  mov     rsi, [rsi+8]
0x18001d492  call    cs:__imp_GetProcessHeap
0x18001d498  mov     r8, rbx; lpMem
0x18001d49b  xor     edx, edx; dwFlags
0x18001d49d  mov     rcx, rax; hHeap
0x18001d4a0  call    cs:__imp_HeapFree
0x18001d4a6  test    rsi, rsi
0x18001d4a9  jnz     short loc_18001D48B
0x18001d4ab  mov     [rdi], rsi
0x18001d4ae  lea     rax, g_header_init_InitializeResultHeader
0x18001d4b5  add     rdi, 8
0x18001d4b9  cmp     rdi, rax
0x18001d4bc  jnz     short loc_18001D486
0x18001d4be  mov     rbx, [rsp+28h+arg_0]
0x18001d4c3  mov     rsi, [rsp+28h+arg_8]
0x18001d4c8  add     rsp, 20h
0x18001d4cc  pop     rdi
0x18001d4cd  retn
```
