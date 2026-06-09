# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800130a0`
- end: `0x1800130ef`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800225c0`

## callees

- `0x1800130a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800130e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800130e7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800130d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800130d9`

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
0x1800130a0  push    rbx
0x1800130a2  push    rbp
0x1800130a3  push    rsi
0x1800130a4  push    rdi
0x1800130a5  sub     rsp, 28h
0x1800130a9  lea     rbp, [rcx+50h]
0x1800130ad  mov     rdi, rcx
0x1800130b0  cmp     rcx, rbp
0x1800130b3  jz      short loc_1800130C9
0x1800130b5  mov     rsi, [rdi]
0x1800130b8  test    rsi, rsi
0x1800130bb  jnz     short loc_1800130D2
0x1800130bd  mov     [rdi], rsi
0x1800130c0  add     rdi, 8
0x1800130c4  cmp     rdi, rbp
0x1800130c7  jnz     short loc_1800130B5
0x1800130c9  add     rsp, 28h
0x1800130cd  pop     rdi
0x1800130ce  pop     rsi
0x1800130cf  pop     rbp
0x1800130d0  pop     rbx
0x1800130d1  retn
0x1800130d2  mov     rbx, rsi
0x1800130d5  mov     rsi, [rsi+8]
0x1800130d9  call    cs:__imp_GetProcessHeap
0x1800130df  mov     r8, rbx; lpMem
0x1800130e2  xor     edx, edx; dwFlags
0x1800130e4  mov     rcx, rax; hHeap
0x1800130e7  call    cs:__imp_HeapFree
0x1800130ed  jmp     short loc_1800130B8
```
