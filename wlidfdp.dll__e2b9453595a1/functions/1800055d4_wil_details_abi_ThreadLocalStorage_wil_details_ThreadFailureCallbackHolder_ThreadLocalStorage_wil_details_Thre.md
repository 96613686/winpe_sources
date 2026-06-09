# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800055d4`
- end: `0x180005623`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800113e0`

## callees

- `0x1800055d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800055f5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005603`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005603`

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
0x1800055d4  push    rbx
0x1800055d6  push    rbp
0x1800055d7  push    rsi
0x1800055d8  push    rdi
0x1800055d9  sub     rsp, 28h
0x1800055dd  lea     rbp, [rcx+50h]
0x1800055e1  mov     rdi, rcx
0x1800055e4  cmp     rcx, rbp
0x1800055e7  jz      short loc_18000561A
0x1800055e9  mov     rsi, [rdi]
0x1800055ec  jmp     short loc_180005609
0x1800055ee  mov     rbx, rsi
0x1800055f1  mov     rsi, [rsi+8]
0x1800055f5  call    cs:__imp_GetProcessHeap
0x1800055fb  mov     r8, rbx; lpMem
0x1800055fe  xor     edx, edx; dwFlags
0x180005600  mov     rcx, rax; hHeap
0x180005603  call    cs:__imp_HeapFree
0x180005609  test    rsi, rsi
0x18000560c  jnz     short loc_1800055EE
0x18000560e  mov     [rdi], rsi
0x180005611  add     rdi, 8
0x180005615  cmp     rdi, rbp
0x180005618  jnz     short loc_1800055E9
0x18000561a  add     rsp, 28h
0x18000561e  pop     rdi
0x18000561f  pop     rsi
0x180005620  pop     rbp
0x180005621  pop     rbx
0x180005622  retn
```
