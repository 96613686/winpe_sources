# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800031b0`
- end: `0x1800031ff`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800152b0`

## callees

- `0x1800031b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031d1`

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
0x1800031b0  push    rbx
0x1800031b2  push    rbp
0x1800031b3  push    rsi
0x1800031b4  push    rdi
0x1800031b5  sub     rsp, 28h
0x1800031b9  lea     rbp, [rcx+50h]
0x1800031bd  mov     rdi, rcx
0x1800031c0  cmp     rcx, rbp
0x1800031c3  jz      short loc_1800031F6
0x1800031c5  mov     rsi, [rdi]
0x1800031c8  jmp     short loc_1800031E5
0x1800031ca  mov     rbx, rsi
0x1800031cd  mov     rsi, [rsi+8]
0x1800031d1  call    cs:__imp_GetProcessHeap
0x1800031d7  mov     r8, rbx; lpMem
0x1800031da  xor     edx, edx; dwFlags
0x1800031dc  mov     rcx, rax; hHeap
0x1800031df  call    cs:__imp_HeapFree
0x1800031e5  test    rsi, rsi
0x1800031e8  jnz     short loc_1800031CA
0x1800031ea  mov     [rdi], rsi
0x1800031ed  add     rdi, 8
0x1800031f1  cmp     rdi, rbp
0x1800031f4  jnz     short loc_1800031C5
0x1800031f6  add     rsp, 28h
0x1800031fa  pop     rdi
0x1800031fb  pop     rsi
0x1800031fc  pop     rbp
0x1800031fd  pop     rbx
0x1800031fe  retn
```
