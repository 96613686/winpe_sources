# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003450`
- end: `0x1800034ac`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016cb0`

## callees

- `0x180003450`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003485`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003485`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003471`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003471`

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
0x180003450  push    rbx
0x180003452  push    rbp
0x180003453  push    rsi
0x180003454  push    rdi
0x180003455  sub     rsp, 28h
0x180003459  lea     rbp, [rcx+50h]
0x18000345d  mov     rdi, rcx
0x180003460  cmp     rcx, rbp
0x180003463  jz      short loc_1800034A2
0x180003465  mov     rsi, [rdi]
0x180003468  jmp     short loc_180003491
0x18000346a  mov     rbx, rsi
0x18000346d  mov     rsi, [rsi+8]
0x180003471  call    cs:__imp_GetProcessHeap
0x180003478  nop     dword ptr [rax+rax+00h]
0x18000347d  mov     r8, rbx; lpMem
0x180003480  xor     edx, edx; dwFlags
0x180003482  mov     rcx, rax; hHeap
0x180003485  call    cs:__imp_HeapFree
0x18000348c  nop     dword ptr [rax+rax+00h]
0x180003491  test    rsi, rsi
0x180003494  jnz     short loc_18000346A
0x180003496  mov     [rdi], rsi
0x180003499  add     rdi, 8
0x18000349d  cmp     rdi, rbp
0x1800034a0  jnz     short loc_180003465
0x1800034a2  add     rsp, 28h
0x1800034a6  pop     rdi
0x1800034a7  pop     rsi
0x1800034a8  pop     rbp
0x1800034a9  pop     rbx
0x1800034aa  retn
```
