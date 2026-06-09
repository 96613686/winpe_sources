# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003618`
- end: `0x180003667`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180036c00`

## callees

- `0x180003618`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003647`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003647`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003639`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003639`

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
0x180003618  push    rbx
0x18000361a  push    rbp
0x18000361b  push    rsi
0x18000361c  push    rdi
0x18000361d  sub     rsp, 28h
0x180003621  lea     rbp, [rcx+50h]
0x180003625  mov     rdi, rcx
0x180003628  cmp     rcx, rbp
0x18000362b  jz      short loc_18000365E
0x18000362d  mov     rsi, [rdi]
0x180003630  jmp     short loc_18000364D
0x180003632  mov     rbx, rsi
0x180003635  mov     rsi, [rsi+8]
0x180003639  call    cs:__imp_GetProcessHeap
0x18000363f  mov     r8, rbx; lpMem
0x180003642  xor     edx, edx; dwFlags
0x180003644  mov     rcx, rax; hHeap
0x180003647  call    cs:__imp_HeapFree
0x18000364d  test    rsi, rsi
0x180003650  jnz     short loc_180003632
0x180003652  mov     [rdi], rsi
0x180003655  add     rdi, 8
0x180003659  cmp     rdi, rbp
0x18000365c  jnz     short loc_18000362D
0x18000365e  add     rsp, 28h
0x180003662  pop     rdi
0x180003663  pop     rsi
0x180003664  pop     rbp
0x180003665  pop     rbx
0x180003666  retn
```
