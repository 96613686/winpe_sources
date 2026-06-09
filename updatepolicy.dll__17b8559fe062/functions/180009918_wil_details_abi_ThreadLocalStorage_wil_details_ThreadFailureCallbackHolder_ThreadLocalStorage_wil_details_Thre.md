# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180009918`
- end: `0x18000997e`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016b90`

## callees

- `0x180009918`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009944`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009944`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009952`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009952`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180009918  mov     [rsp+arg_0], rbx
0x18000991d  mov     [rsp+arg_8], rbp
0x180009922  mov     [rsp+arg_10], rsi
0x180009927  push    rdi
0x180009928  sub     rsp, 20h
0x18000992c  lea     rbp, [rcx+50h]
0x180009930  mov     rdi, rcx
0x180009933  cmp     rcx, rbp
0x180009936  jz      short loc_180009969
0x180009938  mov     rsi, [rdi]
0x18000993b  jmp     short loc_180009958
0x18000993d  mov     rbx, rsi
0x180009940  mov     rsi, [rsi+8]
0x180009944  call    cs:__imp_GetProcessHeap
0x18000994a  mov     r8, rbx; lpMem
0x18000994d  xor     edx, edx; dwFlags
0x18000994f  mov     rcx, rax; hHeap
0x180009952  call    cs:__imp_HeapFree
0x180009958  test    rsi, rsi
0x18000995b  jnz     short loc_18000993D
0x18000995d  mov     [rdi], rsi
0x180009960  add     rdi, 8
0x180009964  cmp     rdi, rbp
0x180009967  jnz     short loc_180009938
0x180009969  mov     rbx, [rsp+28h+arg_0]
0x18000996e  mov     rbp, [rsp+28h+arg_8]
0x180009973  mov     rsi, [rsp+28h+arg_10]
0x180009978  add     rsp, 20h
0x18000997c  pop     rdi
0x18000997d  retn
```
