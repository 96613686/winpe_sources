# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800084e4`
- end: `0x180008533`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800084d0`

## callees

- `0x1800084e4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000851d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000851d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000852b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000852b`

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
0x1800084e4  push    rbx
0x1800084e6  push    rbp
0x1800084e7  push    rsi
0x1800084e8  push    rdi
0x1800084e9  sub     rsp, 28h
0x1800084ed  lea     rbp, [rcx+50h]
0x1800084f1  mov     rdi, rcx
0x1800084f4  cmp     rcx, rbp
0x1800084f7  jz      short loc_18000850D
0x1800084f9  mov     rsi, [rdi]
0x1800084fc  test    rsi, rsi
0x1800084ff  jnz     short loc_180008516
0x180008501  mov     [rdi], rsi
0x180008504  add     rdi, 8
0x180008508  cmp     rdi, rbp
0x18000850b  jnz     short loc_1800084F9
0x18000850d  add     rsp, 28h
0x180008511  pop     rdi
0x180008512  pop     rsi
0x180008513  pop     rbp
0x180008514  pop     rbx
0x180008515  retn
0x180008516  mov     rbx, rsi
0x180008519  mov     rsi, [rsi+8]
0x18000851d  call    cs:__imp_GetProcessHeap
0x180008523  mov     r8, rbx; lpMem
0x180008526  xor     edx, edx; dwFlags
0x180008528  mov     rcx, rax; hHeap
0x18000852b  call    cs:__imp_HeapFree
0x180008531  jmp     short loc_1800084FC
```
