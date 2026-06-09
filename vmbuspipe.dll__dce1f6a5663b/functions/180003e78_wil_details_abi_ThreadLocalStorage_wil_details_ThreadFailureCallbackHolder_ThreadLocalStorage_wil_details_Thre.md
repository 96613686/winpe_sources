# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003e78`
- end: `0x180003ec7`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007bb0`

## callees

- `0x180003e78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e99`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ea7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ea7`

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
0x180003e78  push    rbx
0x180003e7a  push    rbp
0x180003e7b  push    rsi
0x180003e7c  push    rdi
0x180003e7d  sub     rsp, 28h
0x180003e81  lea     rbp, [rcx+50h]
0x180003e85  mov     rdi, rcx
0x180003e88  cmp     rcx, rbp
0x180003e8b  jz      short loc_180003EBE
0x180003e8d  mov     rsi, [rdi]
0x180003e90  jmp     short loc_180003EAD
0x180003e92  mov     rbx, rsi
0x180003e95  mov     rsi, [rsi+8]
0x180003e99  call    cs:__imp_GetProcessHeap
0x180003e9f  mov     r8, rbx; lpMem
0x180003ea2  xor     edx, edx; dwFlags
0x180003ea4  mov     rcx, rax; hHeap
0x180003ea7  call    cs:__imp_HeapFree
0x180003ead  test    rsi, rsi
0x180003eb0  jnz     short loc_180003E92
0x180003eb2  mov     [rdi], rsi
0x180003eb5  add     rdi, 8
0x180003eb9  cmp     rdi, rbp
0x180003ebc  jnz     short loc_180003E8D
0x180003ebe  add     rsp, 28h
0x180003ec2  pop     rdi
0x180003ec3  pop     rsi
0x180003ec4  pop     rbp
0x180003ec5  pop     rbx
0x180003ec6  retn
```
