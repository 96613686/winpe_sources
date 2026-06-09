# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180007048`
- end: `0x1800070bb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c6e0`

## callees

- `0x180007048`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180007074`
- `KERNEL32!GetProcessHeap` at `0x180007074`
- `KERNEL32!HeapFree` at `0x180007088`
- `KERNEL32!HeapFree` at `0x180007088`

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
0x180007048  mov     [rsp+arg_0], rbx
0x18000704d  mov     [rsp+arg_8], rbp
0x180007052  mov     [rsp+arg_10], rsi
0x180007057  push    rdi
0x180007058  sub     rsp, 20h
0x18000705c  lea     rbp, [rcx+50h]
0x180007060  mov     rdi, rcx
0x180007063  cmp     rcx, rbp
0x180007066  jz      short loc_1800070A5
0x180007068  mov     rsi, [rdi]
0x18000706b  jmp     short loc_180007094
0x18000706d  mov     rbx, rsi
0x180007070  mov     rsi, [rsi+8]
0x180007074  call    cs:__imp_GetProcessHeap
0x18000707b  nop     dword ptr [rax+rax+00h]
0x180007080  mov     r8, rbx; lpMem
0x180007083  xor     edx, edx; dwFlags
0x180007085  mov     rcx, rax; hHeap
0x180007088  call    cs:__imp_HeapFree
0x18000708f  nop     dword ptr [rax+rax+00h]
0x180007094  test    rsi, rsi
0x180007097  jnz     short loc_18000706D
0x180007099  mov     [rdi], rsi
0x18000709c  add     rdi, 8
0x1800070a0  cmp     rdi, rbp
0x1800070a3  jnz     short loc_180007068
0x1800070a5  mov     rbx, [rsp+28h+arg_0]
0x1800070aa  mov     rbp, [rsp+28h+arg_8]
0x1800070af  mov     rsi, [rsp+28h+arg_10]
0x1800070b4  add     rsp, 20h
0x1800070b8  pop     rdi
0x1800070b9  retn
```
