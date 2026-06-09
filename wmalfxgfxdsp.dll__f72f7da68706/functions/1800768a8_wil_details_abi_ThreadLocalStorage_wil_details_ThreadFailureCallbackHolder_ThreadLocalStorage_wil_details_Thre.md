# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800768a8`
- end: `0x1800768f7`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014890`

## callees

- `0x1800768a8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800768c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800768c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800768d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800768d7`

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
0x1800768a8  push    rbx
0x1800768aa  push    rbp
0x1800768ab  push    rsi
0x1800768ac  push    rdi
0x1800768ad  sub     rsp, 28h
0x1800768b1  lea     rbp, [rcx+50h]
0x1800768b5  mov     rdi, rcx
0x1800768b8  cmp     rcx, rbp
0x1800768bb  jz      short loc_1800768EE
0x1800768bd  mov     rsi, [rdi]
0x1800768c0  jmp     short loc_1800768DD
0x1800768c2  mov     rbx, rsi
0x1800768c5  mov     rsi, [rsi+8]
0x1800768c9  call    cs:__imp_GetProcessHeap
0x1800768cf  mov     r8, rbx; lpMem
0x1800768d2  xor     edx, edx; dwFlags
0x1800768d4  mov     rcx, rax; hHeap
0x1800768d7  call    cs:__imp_HeapFree
0x1800768dd  test    rsi, rsi
0x1800768e0  jnz     short loc_1800768C2
0x1800768e2  mov     [rdi], rsi
0x1800768e5  add     rdi, 8
0x1800768e9  cmp     rdi, rbp
0x1800768ec  jnz     short loc_1800768BD
0x1800768ee  add     rsp, 28h
0x1800768f2  pop     rdi
0x1800768f3  pop     rsi
0x1800768f4  pop     rbp
0x1800768f5  pop     rbx
0x1800768f6  retn
```
