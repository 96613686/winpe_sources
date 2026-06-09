# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000d744`
- end: `0x18000d793`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013a10`

## callees

- `0x18000d744`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d765`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d765`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d773`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d773`

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
0x18000d744  push    rbx
0x18000d746  push    rbp
0x18000d747  push    rsi
0x18000d748  push    rdi
0x18000d749  sub     rsp, 28h
0x18000d74d  lea     rbp, [rcx+50h]
0x18000d751  mov     rdi, rcx
0x18000d754  cmp     rcx, rbp
0x18000d757  jz      short loc_18000D78A
0x18000d759  mov     rsi, [rdi]
0x18000d75c  jmp     short loc_18000D779
0x18000d75e  mov     rbx, rsi
0x18000d761  mov     rsi, [rsi+8]
0x18000d765  call    cs:__imp_GetProcessHeap
0x18000d76b  mov     r8, rbx; lpMem
0x18000d76e  xor     edx, edx; dwFlags
0x18000d770  mov     rcx, rax; hHeap
0x18000d773  call    cs:__imp_HeapFree
0x18000d779  test    rsi, rsi
0x18000d77c  jnz     short loc_18000D75E
0x18000d77e  mov     [rdi], rsi
0x18000d781  add     rdi, 8
0x18000d785  cmp     rdi, rbp
0x18000d788  jnz     short loc_18000D759
0x18000d78a  add     rsp, 28h
0x18000d78e  pop     rdi
0x18000d78f  pop     rsi
0x18000d790  pop     rbp
0x18000d791  pop     rbx
0x18000d792  retn
```
