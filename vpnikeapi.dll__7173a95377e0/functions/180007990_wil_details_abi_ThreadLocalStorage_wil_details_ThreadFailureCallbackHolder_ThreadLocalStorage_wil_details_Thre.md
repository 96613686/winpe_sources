# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180007990`
- end: `0x1800079df`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d4f0`

## callees

- `0x180007990`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800079b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800079bf`

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
0x180007990  push    rbx
0x180007992  push    rbp
0x180007993  push    rsi
0x180007994  push    rdi
0x180007995  sub     rsp, 28h
0x180007999  lea     rbp, [rcx+50h]
0x18000799d  mov     rdi, rcx
0x1800079a0  cmp     rcx, rbp
0x1800079a3  jz      short loc_1800079D6
0x1800079a5  mov     rsi, [rdi]
0x1800079a8  jmp     short loc_1800079C5
0x1800079aa  mov     rbx, rsi
0x1800079ad  mov     rsi, [rsi+8]
0x1800079b1  call    cs:__imp_GetProcessHeap
0x1800079b7  mov     r8, rbx; lpMem
0x1800079ba  xor     edx, edx; dwFlags
0x1800079bc  mov     rcx, rax; hHeap
0x1800079bf  call    cs:__imp_HeapFree
0x1800079c5  test    rsi, rsi
0x1800079c8  jnz     short loc_1800079AA
0x1800079ca  mov     [rdi], rsi
0x1800079cd  add     rdi, 8
0x1800079d1  cmp     rdi, rbp
0x1800079d4  jnz     short loc_1800079A5
0x1800079d6  add     rsp, 28h
0x1800079da  pop     rdi
0x1800079db  pop     rsi
0x1800079dc  pop     rbp
0x1800079dd  pop     rbx
0x1800079de  retn
```
