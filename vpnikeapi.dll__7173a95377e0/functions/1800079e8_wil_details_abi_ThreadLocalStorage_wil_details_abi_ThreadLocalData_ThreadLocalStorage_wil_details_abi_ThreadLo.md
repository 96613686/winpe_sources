# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800079e8`
- end: `0x180007ac2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007930`

## callees

- `0x1800079e8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a84`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a35`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a66`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007a84`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a92`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a74`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007a92`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x1800079e8  push    rbx
0x1800079ea  push    rbp
0x1800079eb  push    rsi
0x1800079ec  push    rdi
0x1800079ed  push    r12
0x1800079ef  push    r13
0x1800079f1  push    r14
0x1800079f3  push    r15
0x1800079f5  sub     rsp, 28h
0x1800079f9  lea     r15, [rcx+50h]
0x1800079fd  mov     rdi, rcx
0x180007a00  cmp     rcx, r15
0x180007a03  jz      loc_180007AB1
0x180007a09  mov     rsi, [rdi]
0x180007a0c  jmp     loc_180007A98
0x180007a11  mov     r13, rsi
0x180007a14  mov     r12, rsi
0x180007a17  mov     rsi, [rsi+8]
0x180007a1b  movzx   eax, word ptr [r13+30h]
0x180007a20  mov     rbp, [r13+28h]
0x180007a24  lea     r14, [rax+rax*4]
0x180007a28  shl     r14, 4
0x180007a2c  add     r14, rbp
0x180007a2f  jmp     short loc_180007A5D
0x180007a31  mov     rbx, [rbp+40h]
0x180007a35  call    cs:__imp_GetProcessHeap
0x180007a3b  mov     r8, rbx; lpMem
0x180007a3e  xor     edx, edx; dwFlags
0x180007a40  mov     rcx, rax; hHeap
0x180007a43  call    cs:__imp_HeapFree
0x180007a49  mov     qword ptr [rbp+40h], 0
0x180007a51  mov     qword ptr [rbp+48h], 0
0x180007a59  add     rbp, 50h ; 'P'
0x180007a5d  cmp     rbp, r14
0x180007a60  jnz     short loc_180007A31
0x180007a62  mov     rbx, [r13+28h]
0x180007a66  call    cs:__imp_GetProcessHeap
0x180007a6c  mov     r8, rbx; lpMem
0x180007a6f  xor     edx, edx; dwFlags
0x180007a71  mov     rcx, rax; hHeap
0x180007a74  call    cs:__imp_HeapFree
0x180007a7a  xor     eax, eax
0x180007a7c  mov     [r13+30h], eax
0x180007a80  mov     [r13+28h], rax
0x180007a84  call    cs:__imp_GetProcessHeap
0x180007a8a  mov     r8, r12; lpMem
0x180007a8d  xor     edx, edx; dwFlags
0x180007a8f  mov     rcx, rax; hHeap
0x180007a92  call    cs:__imp_HeapFree
0x180007a98  test    rsi, rsi
0x180007a9b  jnz     loc_180007A11
0x180007aa1  mov     [rdi], rsi
0x180007aa4  add     rdi, 8
0x180007aa8  cmp     rdi, r15
0x180007aab  jnz     loc_180007A09
0x180007ab1  add     rsp, 28h
0x180007ab5  pop     r15
0x180007ab7  pop     r14
0x180007ab9  pop     r13
0x180007abb  pop     r12
0x180007abd  pop     rdi
0x180007abe  pop     rsi
0x180007abf  pop     rbp
0x180007ac0  pop     rbx
0x180007ac1  retn
```
