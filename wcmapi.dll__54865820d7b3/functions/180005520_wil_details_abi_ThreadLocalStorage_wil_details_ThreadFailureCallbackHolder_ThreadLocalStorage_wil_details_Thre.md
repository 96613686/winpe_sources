# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180005520`
- end: `0x1800055a5`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005500`

## callees

- `0x180005520`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005592`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000557e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000557e`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rbx
  _QWORD *v3; // rsi
  void *v4; // rdi
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    if ( *v2 )
    {
      do
      {
        v4 = v3;
        v3 = (_QWORD *)v3[1];
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      while ( v3 );
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180005520  mov     [rsp+arg_18], rbx
0x180005525  push    rbp
0x180005526  sub     rsp, 20h
0x18000552a  lea     rbp, [rcx+50h]
0x18000552e  mov     rbx, rcx
0x180005531  cmp     rcx, rbp
0x180005534  jz      short loc_18000556B
0x180005536  mov     [rsp+28h+arg_0], rsi
0x18000553b  mov     [rsp+28h+arg_8], rdi
0x180005540  mov     [rsp+28h+arg_10], r14
0x180005545  xor     r14d, r14d
0x180005548  mov     rsi, [rbx]
0x18000554b  test    rsi, rsi
0x18000554e  jnz     short loc_180005577
0x180005550  mov     [rbx], r14
0x180005553  add     rbx, 8
0x180005557  cmp     rbx, rbp
0x18000555a  jnz     short loc_180005548
0x18000555c  mov     r14, [rsp+28h+arg_10]
0x180005561  mov     rdi, [rsp+28h+arg_8]
0x180005566  mov     rsi, [rsp+28h+arg_0]
0x18000556b  mov     rbx, [rsp+28h+arg_18]
0x180005570  add     rsp, 20h
0x180005574  pop     rbp
0x180005575  retn
0x180005577  mov     rdi, rsi
0x18000557a  mov     rsi, [rsi+8]
0x18000557e  call    cs:__imp_GetProcessHeap
0x180005585  nop     dword ptr [rax+rax+00h]
0x18000558a  mov     r8, rdi; lpMem
0x18000558d  xor     edx, edx; dwFlags
0x18000558f  mov     rcx, rax; hHeap
0x180005592  call    cs:__imp_HeapFree
0x180005599  nop     dword ptr [rax+rax+00h]
0x18000559e  test    rsi, rsi
0x1800055a1  jz      short loc_180005550
0x1800055a3  jmp     short loc_180005577
```
