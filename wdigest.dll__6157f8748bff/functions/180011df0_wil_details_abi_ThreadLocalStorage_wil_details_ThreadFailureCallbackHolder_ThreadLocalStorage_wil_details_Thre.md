# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180011df0`
- end: `0x180011e3f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180037ab0`

## callees

- `0x180011df0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011e1f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e11`

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
0x180011df0  push    rbx
0x180011df2  push    rbp
0x180011df3  push    rsi
0x180011df4  push    rdi
0x180011df5  sub     rsp, 28h
0x180011df9  lea     rbp, [rcx+50h]
0x180011dfd  mov     rdi, rcx
0x180011e00  cmp     rcx, rbp
0x180011e03  jz      short loc_180011E36
0x180011e05  mov     rsi, [rdi]
0x180011e08  jmp     short loc_180011E25
0x180011e0a  mov     rbx, rsi
0x180011e0d  mov     rsi, [rsi+8]
0x180011e11  call    cs:__imp_GetProcessHeap
0x180011e17  mov     r8, rbx; lpMem
0x180011e1a  xor     edx, edx; dwFlags
0x180011e1c  mov     rcx, rax; hHeap
0x180011e1f  call    cs:__imp_HeapFree
0x180011e25  test    rsi, rsi
0x180011e28  jnz     short loc_180011E0A
0x180011e2a  mov     [rdi], rsi
0x180011e2d  add     rdi, 8
0x180011e31  cmp     rdi, rbp
0x180011e34  jnz     short loc_180011E05
0x180011e36  add     rsp, 28h
0x180011e3a  pop     rdi
0x180011e3b  pop     rsi
0x180011e3c  pop     rbp
0x180011e3d  pop     rbx
0x180011e3e  retn
```
