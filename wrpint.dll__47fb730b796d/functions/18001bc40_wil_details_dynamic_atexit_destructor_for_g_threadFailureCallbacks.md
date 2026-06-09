# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x18001bc40`
- end: `0x18001bc9e`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001bc40`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001bc62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bc70`

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
0x18001bc40  mov     [rsp+arg_0], rbx
0x18001bc45  mov     [rsp+arg_8], rsi
0x18001bc4a  push    rdi
0x18001bc4b  sub     rsp, 20h
0x18001bc4f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x18001bc56  mov     rsi, [rdi]
0x18001bc59  jmp     short loc_18001BC76
0x18001bc5b  mov     rbx, rsi
0x18001bc5e  mov     rsi, [rsi+8]
0x18001bc62  call    cs:__imp_GetProcessHeap
0x18001bc68  mov     r8, rbx; lpMem
0x18001bc6b  xor     edx, edx; dwFlags
0x18001bc6d  mov     rcx, rax; hHeap
0x18001bc70  call    cs:__imp_HeapFree
0x18001bc76  test    rsi, rsi
0x18001bc79  jnz     short loc_18001BC5B
0x18001bc7b  mov     [rdi], rsi
0x18001bc7e  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x18001bc85  add     rdi, 8
0x18001bc89  cmp     rdi, rax
0x18001bc8c  jnz     short loc_18001BC56
0x18001bc8e  mov     rbx, [rsp+28h+arg_0]
0x18001bc93  mov     rsi, [rsp+28h+arg_8]
0x18001bc98  add     rsp, 20h
0x18001bc9c  pop     rdi
0x18001bc9d  retn
```
