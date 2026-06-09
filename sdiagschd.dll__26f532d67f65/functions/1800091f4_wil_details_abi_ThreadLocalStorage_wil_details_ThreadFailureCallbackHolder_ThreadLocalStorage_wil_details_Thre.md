# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800091f4`
- end: `0x180009267`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ce30`

## callees

- `0x1800091f4`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180009234`
- `KERNEL32!HeapFree` at `0x180009234`
- `KERNEL32!GetProcessHeap` at `0x180009220`
- `KERNEL32!GetProcessHeap` at `0x180009220`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rdi
  _QWORD *v2; // rbp
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1;
  v2 = a1 + 10;
  do
  {
    v3 = (_QWORD *)*v1;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v1++ = 0;
  }
  while ( v1 != v2 );
}

```

## disassembly

```asm
0x1800091f4  mov     [rsp+arg_0], rbx
0x1800091f9  mov     [rsp+arg_8], rbp
0x1800091fe  mov     [rsp+arg_10], rsi
0x180009203  push    rdi
0x180009204  sub     rsp, 20h
0x180009208  mov     rdi, rcx
0x18000920b  lea     rbp, [rcx+50h]
0x18000920f  cmp     rcx, rbp
0x180009212  jz      short loc_180009251
0x180009214  mov     rsi, [rdi]
0x180009217  jmp     short loc_180009240
0x180009219  mov     rbx, rsi
0x18000921c  mov     rsi, [rsi+8]
0x180009220  call    cs:__imp_GetProcessHeap
0x180009227  nop     dword ptr [rax+rax+00h]
0x18000922c  mov     rcx, rax; hHeap
0x18000922f  mov     r8, rbx; lpMem
0x180009232  xor     edx, edx; dwFlags
0x180009234  call    cs:__imp_HeapFree
0x18000923b  nop     dword ptr [rax+rax+00h]
0x180009240  test    rsi, rsi
0x180009243  jnz     short loc_180009219
0x180009245  mov     [rdi], rsi
0x180009248  add     rdi, 8
0x18000924c  cmp     rdi, rbp
0x18000924f  jnz     short loc_180009214
0x180009251  mov     rbx, [rsp+28h+arg_0]
0x180009256  mov     rbp, [rsp+28h+arg_8]
0x18000925b  mov     rsi, [rsp+28h+arg_10]
0x180009260  add     rsp, 20h
0x180009264  pop     rdi
0x180009265  retn
```
