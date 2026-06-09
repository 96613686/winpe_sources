# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800075c4`
- end: `0x180007613`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d050`

## callees

- `0x1800075c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075f3`

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
0x1800075c4  push    rbx
0x1800075c6  push    rbp
0x1800075c7  push    rsi
0x1800075c8  push    rdi
0x1800075c9  sub     rsp, 28h
0x1800075cd  lea     rbp, [rcx+50h]
0x1800075d1  mov     rdi, rcx
0x1800075d4  cmp     rcx, rbp
0x1800075d7  jz      short loc_18000760A
0x1800075d9  mov     rsi, [rdi]
0x1800075dc  jmp     short loc_1800075F9
0x1800075de  mov     rbx, rsi
0x1800075e1  mov     rsi, [rsi+8]
0x1800075e5  call    cs:__imp_GetProcessHeap
0x1800075eb  mov     r8, rbx; lpMem
0x1800075ee  xor     edx, edx; dwFlags
0x1800075f0  mov     rcx, rax; hHeap
0x1800075f3  call    cs:__imp_HeapFree
0x1800075f9  test    rsi, rsi
0x1800075fc  jnz     short loc_1800075DE
0x1800075fe  mov     [rdi], rsi
0x180007601  add     rdi, 8
0x180007605  cmp     rdi, rbp
0x180007608  jnz     short loc_1800075D9
0x18000760a  add     rsp, 28h
0x18000760e  pop     rdi
0x18000760f  pop     rsi
0x180007610  pop     rbp
0x180007611  pop     rbx
0x180007612  retn
```
