# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180008620`
- end: `0x18000866f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015940`

## callees

- `0x180008620`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000864f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000864f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008641`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008641`

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
0x180008620  push    rbx
0x180008622  push    rbp
0x180008623  push    rsi
0x180008624  push    rdi
0x180008625  sub     rsp, 28h
0x180008629  lea     rbp, [rcx+50h]
0x18000862d  mov     rdi, rcx
0x180008630  cmp     rcx, rbp
0x180008633  jz      short loc_180008666
0x180008635  mov     rsi, [rdi]
0x180008638  jmp     short loc_180008655
0x18000863a  mov     rbx, rsi
0x18000863d  mov     rsi, [rsi+8]
0x180008641  call    cs:__imp_GetProcessHeap
0x180008647  mov     r8, rbx; lpMem
0x18000864a  xor     edx, edx; dwFlags
0x18000864c  mov     rcx, rax; hHeap
0x18000864f  call    cs:__imp_HeapFree
0x180008655  test    rsi, rsi
0x180008658  jnz     short loc_18000863A
0x18000865a  mov     [rdi], rsi
0x18000865d  add     rdi, 8
0x180008661  cmp     rdi, rbp
0x180008664  jnz     short loc_180008635
0x180008666  add     rsp, 28h
0x18000866a  pop     rdi
0x18000866b  pop     rsi
0x18000866c  pop     rbp
0x18000866d  pop     rbx
0x18000866e  retn
```
