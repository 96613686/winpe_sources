# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180006838`
- end: `0x180006887`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fea0`

## callees

- `0x180006838`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006867`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006867`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006859`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006859`

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
0x180006838  push    rbx
0x18000683a  push    rbp
0x18000683b  push    rsi
0x18000683c  push    rdi
0x18000683d  sub     rsp, 28h
0x180006841  lea     rbp, [rcx+50h]
0x180006845  mov     rdi, rcx
0x180006848  cmp     rcx, rbp
0x18000684b  jz      short loc_18000687E
0x18000684d  mov     rsi, [rdi]
0x180006850  jmp     short loc_18000686D
0x180006852  mov     rbx, rsi
0x180006855  mov     rsi, [rsi+8]
0x180006859  call    cs:__imp_GetProcessHeap
0x18000685f  mov     r8, rbx; lpMem
0x180006862  xor     edx, edx; dwFlags
0x180006864  mov     rcx, rax; hHeap
0x180006867  call    cs:__imp_HeapFree
0x18000686d  test    rsi, rsi
0x180006870  jnz     short loc_180006852
0x180006872  mov     [rdi], rsi
0x180006875  add     rdi, 8
0x180006879  cmp     rdi, rbp
0x18000687c  jnz     short loc_18000684D
0x18000687e  add     rsp, 28h
0x180006882  pop     rdi
0x180006883  pop     rsi
0x180006884  pop     rbp
0x180006885  pop     rbx
0x180006886  retn
```
