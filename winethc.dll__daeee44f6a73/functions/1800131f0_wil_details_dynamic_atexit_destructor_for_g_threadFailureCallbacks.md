# wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__

- ea: `0x1800131f0`
- end: `0x18001325b`
- name: `wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800131f0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180013212`
- `KERNEL32!GetProcessHeap` at `0x180013212`
- `KERNEL32!HeapFree` at `0x180013226`
- `KERNEL32!HeapFree` at `0x180013226`

## pseudocode

```c
__int64 *wil::details::_dynamic_atexit_destructor_for__g_threadFailureCallbacks__()
{
  __int64 *v0; // rdi
  __int64 v1; // rsi
  void *v2; // rbx
  HANDLE ProcessHeap; // rax
  __int64 *result; // rax

  v0 = wil::details::g_threadFailureCallbacks;
  do
  {
    v1 = *v0;
    while ( v1 )
    {
      v2 = (void *)v1;
      v1 = *(_QWORD *)(v1 + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v2);
    }
    *v0 = 0;
    result = g_header_init_InitializeResultHeader;
    ++v0;
  }
  while ( v0 != g_header_init_InitializeResultHeader );
  return result;
}

```

## disassembly

```asm
0x1800131f0  mov     [rsp+arg_0], rbx
0x1800131f5  mov     [rsp+arg_8], rsi
0x1800131fa  push    rdi
0x1800131fb  sub     rsp, 20h
0x1800131ff  lea     rdi, ?g_threadFailureCallbacks@details@wil@@3V?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@A; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> wil::details::g_threadFailureCallbacks
0x180013206  mov     rsi, [rdi]
0x180013209  jmp     short loc_180013232
0x18001320b  mov     rbx, rsi
0x18001320e  mov     rsi, [rsi+8]
0x180013212  call    cs:__imp_GetProcessHeap
0x180013219  nop     dword ptr [rax+rax+00h]
0x18001321e  mov     r8, rbx; lpMem
0x180013221  xor     edx, edx; dwFlags
0x180013223  mov     rcx, rax; hHeap
0x180013226  call    cs:__imp_HeapFree
0x18001322d  nop     dword ptr [rax+rax+00h]
0x180013232  test    rsi, rsi
0x180013235  jnz     short loc_18001320B
0x180013237  mov     [rdi], rsi
0x18001323a  lea     rax, g_header_init_InitializeResultHeader
0x180013241  add     rdi, 8
0x180013245  cmp     rdi, rax
0x180013248  jnz     short loc_180013206
0x18001324a  mov     rbx, [rsp+28h+arg_0]
0x18001324f  mov     rsi, [rsp+28h+arg_8]
0x180013254  add     rsp, 20h
0x180013258  pop     rdi
0x180013259  retn
```
