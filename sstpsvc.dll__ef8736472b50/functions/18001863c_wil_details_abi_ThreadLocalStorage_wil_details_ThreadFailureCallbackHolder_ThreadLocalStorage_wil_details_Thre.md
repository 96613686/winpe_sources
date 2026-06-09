# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18001863c`
- end: `0x180018698`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001db40`

## callees

- `0x18001863c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018671`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018671`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001865d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001865d`

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
0x18001863c  push    rbx
0x18001863e  push    rbp
0x18001863f  push    rsi
0x180018640  push    rdi
0x180018641  sub     rsp, 28h
0x180018645  lea     rbp, [rcx+50h]
0x180018649  mov     rdi, rcx
0x18001864c  cmp     rcx, rbp
0x18001864f  jz      short loc_18001868E
0x180018651  mov     rsi, [rdi]
0x180018654  jmp     short loc_18001867D
0x180018656  mov     rbx, rsi
0x180018659  mov     rsi, [rsi+8]
0x18001865d  call    cs:__imp_GetProcessHeap
0x180018664  nop     dword ptr [rax+rax+00h]
0x180018669  mov     r8, rbx; lpMem
0x18001866c  xor     edx, edx; dwFlags
0x18001866e  mov     rcx, rax; hHeap
0x180018671  call    cs:__imp_HeapFree
0x180018678  nop     dword ptr [rax+rax+00h]
0x18001867d  test    rsi, rsi
0x180018680  jnz     short loc_180018656
0x180018682  mov     [rdi], rsi
0x180018685  add     rdi, 8
0x180018689  cmp     rdi, rbp
0x18001868c  jnz     short loc_180018651
0x18001868e  add     rsp, 28h
0x180018692  pop     rdi
0x180018693  pop     rsi
0x180018694  pop     rbp
0x180018695  pop     rbx
0x180018696  retn
```
