# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180007164`
- end: `0x1800071ca`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180016250`

## callees

- `0x180007164`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007190`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007190`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000719e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000719e`

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
0x180007164  mov     [rsp+arg_0], rbx
0x180007169  mov     [rsp+arg_8], rbp
0x18000716e  mov     [rsp+arg_10], rsi
0x180007173  push    rdi
0x180007174  sub     rsp, 20h
0x180007178  lea     rbp, [rcx+50h]
0x18000717c  mov     rdi, rcx
0x18000717f  cmp     rcx, rbp
0x180007182  jz      short loc_1800071B5
0x180007184  mov     rsi, [rdi]
0x180007187  jmp     short loc_1800071A4
0x180007189  mov     rbx, rsi
0x18000718c  mov     rsi, [rsi+8]
0x180007190  call    cs:__imp_GetProcessHeap
0x180007196  mov     r8, rbx; lpMem
0x180007199  xor     edx, edx; dwFlags
0x18000719b  mov     rcx, rax; hHeap
0x18000719e  call    cs:__imp_HeapFree
0x1800071a4  test    rsi, rsi
0x1800071a7  jnz     short loc_180007189
0x1800071a9  mov     [rdi], rsi
0x1800071ac  add     rdi, 8
0x1800071b0  cmp     rdi, rbp
0x1800071b3  jnz     short loc_180007184
0x1800071b5  mov     rbx, [rsp+28h+arg_0]
0x1800071ba  mov     rbp, [rsp+28h+arg_8]
0x1800071bf  mov     rsi, [rsp+28h+arg_10]
0x1800071c4  add     rsp, 20h
0x1800071c8  pop     rdi
0x1800071c9  retn
```
