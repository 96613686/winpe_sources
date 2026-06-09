# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000d3b8`
- end: `0x18000d407`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c810`

## callees

- `0x18000d3b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d3d9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d3e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d3e7`

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
0x18000d3b8  push    rbx
0x18000d3ba  push    rbp
0x18000d3bb  push    rsi
0x18000d3bc  push    rdi
0x18000d3bd  sub     rsp, 28h
0x18000d3c1  lea     rbp, [rcx+50h]
0x18000d3c5  mov     rdi, rcx
0x18000d3c8  cmp     rcx, rbp
0x18000d3cb  jz      short loc_18000D3FE
0x18000d3cd  mov     rsi, [rdi]
0x18000d3d0  jmp     short loc_18000D3ED
0x18000d3d2  mov     rbx, rsi
0x18000d3d5  mov     rsi, [rsi+8]
0x18000d3d9  call    cs:__imp_GetProcessHeap
0x18000d3df  mov     r8, rbx; lpMem
0x18000d3e2  xor     edx, edx; dwFlags
0x18000d3e4  mov     rcx, rax; hHeap
0x18000d3e7  call    cs:__imp_HeapFree
0x18000d3ed  test    rsi, rsi
0x18000d3f0  jnz     short loc_18000D3D2
0x18000d3f2  mov     [rdi], rsi
0x18000d3f5  add     rdi, 8
0x18000d3f9  cmp     rdi, rbp
0x18000d3fc  jnz     short loc_18000D3CD
0x18000d3fe  add     rsp, 28h
0x18000d402  pop     rdi
0x18000d403  pop     rsi
0x18000d404  pop     rbp
0x18000d405  pop     rbx
0x18000d406  retn
```
