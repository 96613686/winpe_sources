# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x140010b90`
- end: `0x140010bee`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `94`
- prototype: `char *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010b90`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140010bc0`
- `KERNEL32!HeapFree` at `0x140010bc0`
- `KERNEL32!GetProcessHeap` at `0x140010bb2`
- `KERNEL32!GetProcessHeap` at `0x140010bb2`

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
0x140010b90  mov     [rsp+arg_0], rbx
0x140010b95  mov     [rsp+arg_8], rsi
0x140010b9a  push    rdi
0x140010b9b  sub     rsp, 20h
0x140010b9f  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x140010ba6  mov     rsi, [rdi]
0x140010ba9  jmp     short loc_140010BC6
0x140010bab  mov     rbx, rsi
0x140010bae  mov     rsi, [rsi+8]
0x140010bb2  call    cs:__imp_GetProcessHeap
0x140010bb8  mov     r8, rbx; lpMem
0x140010bbb  xor     edx, edx; dwFlags
0x140010bbd  mov     rcx, rax; hHeap
0x140010bc0  call    cs:__imp_HeapFree
0x140010bc6  test    rsi, rsi
0x140010bc9  jnz     short loc_140010BAB
0x140010bcb  mov     [rdi], rsi
0x140010bce  lea     rax, g_header_init_InitializeStagingHeaderInternalApi
0x140010bd5  add     rdi, 8
0x140010bd9  cmp     rdi, rax
0x140010bdc  jnz     short loc_140010BA6
0x140010bde  mov     rbx, [rsp+28h+arg_0]
0x140010be3  mov     rsi, [rsp+28h+arg_8]
0x140010be8  add     rsp, 20h
0x140010bec  pop     rdi
0x140010bed  retn
```
