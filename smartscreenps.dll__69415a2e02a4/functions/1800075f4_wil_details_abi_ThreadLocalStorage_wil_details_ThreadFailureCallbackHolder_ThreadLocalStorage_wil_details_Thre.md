# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800075f4`
- end: `0x180007650`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d330`

## callees

- `0x1800075f4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007615`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007615`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007629`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007629`

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
0x1800075f4  push    rbx
0x1800075f6  push    rbp
0x1800075f7  push    rsi
0x1800075f8  push    rdi
0x1800075f9  sub     rsp, 28h
0x1800075fd  lea     rbp, [rcx+50h]
0x180007601  mov     rdi, rcx
0x180007604  cmp     rcx, rbp
0x180007607  jz      short loc_180007646
0x180007609  mov     rsi, [rdi]
0x18000760c  jmp     short loc_180007635
0x18000760e  mov     rbx, rsi
0x180007611  mov     rsi, [rsi+8]
0x180007615  call    cs:__imp_GetProcessHeap
0x18000761c  nop     dword ptr [rax+rax+00h]
0x180007621  mov     r8, rbx; lpMem
0x180007624  xor     edx, edx; dwFlags
0x180007626  mov     rcx, rax; hHeap
0x180007629  call    cs:__imp_HeapFree
0x180007630  nop     dword ptr [rax+rax+00h]
0x180007635  test    rsi, rsi
0x180007638  jnz     short loc_18000760E
0x18000763a  mov     [rdi], rsi
0x18000763d  add     rdi, 8
0x180007641  cmp     rdi, rbp
0x180007644  jnz     short loc_180007609
0x180007646  add     rsp, 28h
0x18000764a  pop     rdi
0x18000764b  pop     rsi
0x18000764c  pop     rbp
0x18000764d  pop     rbx
0x18000764e  retn
```
