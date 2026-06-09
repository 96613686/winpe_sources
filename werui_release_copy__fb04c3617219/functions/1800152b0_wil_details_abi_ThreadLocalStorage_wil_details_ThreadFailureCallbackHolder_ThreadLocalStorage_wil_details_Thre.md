# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800152b0`
- end: `0x1800152ff`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800174a0`

## callees

- `0x1800152b0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800152d1`
- `KERNEL32!GetProcessHeap` at `0x1800152d1`
- `KERNEL32!HeapFree` at `0x1800152df`
- `KERNEL32!HeapFree` at `0x1800152df`

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
0x1800152b0  push    rbx
0x1800152b2  push    rbp
0x1800152b3  push    rsi
0x1800152b4  push    rdi
0x1800152b5  sub     rsp, 28h
0x1800152b9  lea     rbp, [rcx+50h]
0x1800152bd  mov     rdi, rcx
0x1800152c0  cmp     rcx, rbp
0x1800152c3  jz      short loc_1800152F6
0x1800152c5  mov     rsi, [rdi]
0x1800152c8  jmp     short loc_1800152E5
0x1800152ca  mov     rbx, rsi
0x1800152cd  mov     rsi, [rsi+8]
0x1800152d1  call    cs:__imp_GetProcessHeap
0x1800152d7  mov     r8, rbx; lpMem
0x1800152da  xor     edx, edx; dwFlags
0x1800152dc  mov     rcx, rax; hHeap
0x1800152df  call    cs:__imp_HeapFree
0x1800152e5  test    rsi, rsi
0x1800152e8  jnz     short loc_1800152CA
0x1800152ea  mov     [rdi], rsi
0x1800152ed  add     rdi, 8
0x1800152f1  cmp     rdi, rbp
0x1800152f4  jnz     short loc_1800152C5
0x1800152f6  add     rsp, 28h
0x1800152fa  pop     rdi
0x1800152fb  pop     rsi
0x1800152fc  pop     rbp
0x1800152fd  pop     rbx
0x1800152fe  retn
```
