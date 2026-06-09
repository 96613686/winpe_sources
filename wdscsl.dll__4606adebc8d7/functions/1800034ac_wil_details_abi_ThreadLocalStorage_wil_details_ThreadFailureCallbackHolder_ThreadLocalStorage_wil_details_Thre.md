# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800034ac`
- end: `0x18000351f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dd00`

## callees

- `0x1800034ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800034ec`
- `KERNEL32!HeapFree` at `0x1800034ec`
- `KERNEL32!GetProcessHeap` at `0x1800034d8`
- `KERNEL32!GetProcessHeap` at `0x1800034d8`

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
0x1800034ac  mov     [rsp+arg_0], rbx
0x1800034b1  mov     [rsp+arg_8], rbp
0x1800034b6  mov     [rsp+arg_10], rsi
0x1800034bb  push    rdi
0x1800034bc  sub     rsp, 20h
0x1800034c0  lea     rbp, [rcx+50h]
0x1800034c4  mov     rdi, rcx
0x1800034c7  cmp     rcx, rbp
0x1800034ca  jz      short loc_180003509
0x1800034cc  mov     rsi, [rdi]
0x1800034cf  jmp     short loc_1800034F8
0x1800034d1  mov     rbx, rsi
0x1800034d4  mov     rsi, [rsi+8]
0x1800034d8  call    cs:__imp_GetProcessHeap
0x1800034df  nop     dword ptr [rax+rax+00h]
0x1800034e4  mov     r8, rbx; lpMem
0x1800034e7  xor     edx, edx; dwFlags
0x1800034e9  mov     rcx, rax; hHeap
0x1800034ec  call    cs:__imp_HeapFree
0x1800034f3  nop     dword ptr [rax+rax+00h]
0x1800034f8  test    rsi, rsi
0x1800034fb  jnz     short loc_1800034D1
0x1800034fd  mov     [rdi], rsi
0x180003500  add     rdi, 8
0x180003504  cmp     rdi, rbp
0x180003507  jnz     short loc_1800034CC
0x180003509  mov     rbx, [rsp+28h+arg_0]
0x18000350e  mov     rbp, [rsp+28h+arg_8]
0x180003513  mov     rsi, [rsp+28h+arg_10]
0x180003518  add     rsp, 20h
0x18000351c  pop     rdi
0x18000351d  retn
```
