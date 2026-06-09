# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800156ac`
- end: `0x1800156fb`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002a780`

## callees

- `0x1800156ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800156db`
- `KERNEL32!HeapFree` at `0x1800156db`
- `KERNEL32!GetProcessHeap` at `0x1800156cd`
- `KERNEL32!GetProcessHeap` at `0x1800156cd`

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
0x1800156ac  push    rbx
0x1800156ae  push    rbp
0x1800156af  push    rsi
0x1800156b0  push    rdi
0x1800156b1  sub     rsp, 28h
0x1800156b5  lea     rbp, [rcx+50h]
0x1800156b9  mov     rdi, rcx
0x1800156bc  cmp     rcx, rbp
0x1800156bf  jz      short loc_1800156F2
0x1800156c1  mov     rsi, [rdi]
0x1800156c4  jmp     short loc_1800156E1
0x1800156c6  mov     rbx, rsi
0x1800156c9  mov     rsi, [rsi+8]
0x1800156cd  call    cs:__imp_GetProcessHeap
0x1800156d3  mov     r8, rbx; lpMem
0x1800156d6  xor     edx, edx; dwFlags
0x1800156d8  mov     rcx, rax; hHeap
0x1800156db  call    cs:__imp_HeapFree
0x1800156e1  test    rsi, rsi
0x1800156e4  jnz     short loc_1800156C6
0x1800156e6  mov     [rdi], rsi
0x1800156e9  add     rdi, 8
0x1800156ed  cmp     rdi, rbp
0x1800156f0  jnz     short loc_1800156C1
0x1800156f2  add     rsp, 28h
0x1800156f6  pop     rdi
0x1800156f7  pop     rsi
0x1800156f8  pop     rbp
0x1800156f9  pop     rbx
0x1800156fa  retn
```
