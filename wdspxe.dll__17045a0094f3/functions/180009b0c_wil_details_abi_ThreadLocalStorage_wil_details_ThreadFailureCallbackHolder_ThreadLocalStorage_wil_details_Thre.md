# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180009b0c`
- end: `0x180009b7f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012150`

## callees

- `0x180009b0c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009b38`
- `KERNEL32!GetProcessHeap` at `0x180009b38`
- `KERNEL32!HeapFree` at `0x180009b4c`
- `KERNEL32!HeapFree` at `0x180009b4c`

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
0x180009b0c  mov     [rsp+arg_0], rbx
0x180009b11  mov     [rsp+arg_8], rbp
0x180009b16  mov     [rsp+arg_10], rsi
0x180009b1b  push    rdi
0x180009b1c  sub     rsp, 20h
0x180009b20  lea     rbp, [rcx+50h]
0x180009b24  mov     rdi, rcx
0x180009b27  cmp     rcx, rbp
0x180009b2a  jz      short loc_180009B69
0x180009b2c  mov     rsi, [rdi]
0x180009b2f  jmp     short loc_180009B58
0x180009b31  mov     rbx, rsi
0x180009b34  mov     rsi, [rsi+8]
0x180009b38  call    cs:__imp_GetProcessHeap
0x180009b3f  nop     dword ptr [rax+rax+00h]
0x180009b44  mov     r8, rbx; lpMem
0x180009b47  xor     edx, edx; dwFlags
0x180009b49  mov     rcx, rax; hHeap
0x180009b4c  call    cs:__imp_HeapFree
0x180009b53  nop     dword ptr [rax+rax+00h]
0x180009b58  test    rsi, rsi
0x180009b5b  jnz     short loc_180009B31
0x180009b5d  mov     [rdi], rsi
0x180009b60  add     rdi, 8
0x180009b64  cmp     rdi, rbp
0x180009b67  jnz     short loc_180009B2C
0x180009b69  mov     rbx, [rsp+28h+arg_0]
0x180009b6e  mov     rbp, [rsp+28h+arg_8]
0x180009b73  mov     rsi, [rsp+28h+arg_10]
0x180009b78  add     rsp, 20h
0x180009b7c  pop     rdi
0x180009b7d  retn
```
