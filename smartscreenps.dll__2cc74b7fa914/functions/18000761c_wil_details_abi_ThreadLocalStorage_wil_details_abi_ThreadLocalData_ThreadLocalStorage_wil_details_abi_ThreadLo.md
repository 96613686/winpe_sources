# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000761c`
- end: `0x1800076f6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007594`

## callees

- `0x18000761c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007669`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000769a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007669`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000769a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800076b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007677`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007677`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800076c6`

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
0x18000761c  push    rbx
0x18000761e  push    rbp
0x18000761f  push    rsi
0x180007620  push    rdi
0x180007621  push    r12
0x180007623  push    r13
0x180007625  push    r14
0x180007627  push    r15
0x180007629  sub     rsp, 28h
0x18000762d  lea     r15, [rcx+50h]
0x180007631  mov     rdi, rcx
0x180007634  cmp     rcx, r15
0x180007637  jz      loc_1800076E5
0x18000763d  mov     rsi, [rdi]
0x180007640  jmp     loc_1800076CC
0x180007645  mov     r13, rsi
0x180007648  mov     r12, rsi
0x18000764b  mov     rsi, [rsi+8]
0x18000764f  movzx   eax, word ptr [r13+30h]
0x180007654  mov     rbp, [r13+28h]
0x180007658  lea     r14, [rax+rax*4]
0x18000765c  shl     r14, 4
0x180007660  add     r14, rbp
0x180007663  jmp     short loc_180007691
0x180007665  mov     rbx, [rbp+40h]
0x180007669  call    cs:__imp_GetProcessHeap
0x18000766f  mov     r8, rbx; lpMem
0x180007672  xor     edx, edx; dwFlags
0x180007674  mov     rcx, rax; hHeap
0x180007677  call    cs:__imp_HeapFree
0x18000767d  mov     qword ptr [rbp+40h], 0
0x180007685  mov     qword ptr [rbp+48h], 0
0x18000768d  add     rbp, 50h ; 'P'
0x180007691  cmp     rbp, r14
0x180007694  jnz     short loc_180007665
0x180007696  mov     rbx, [r13+28h]
0x18000769a  call    cs:__imp_GetProcessHeap
0x1800076a0  mov     r8, rbx; lpMem
0x1800076a3  xor     edx, edx; dwFlags
0x1800076a5  mov     rcx, rax; hHeap
0x1800076a8  call    cs:__imp_HeapFree
0x1800076ae  xor     eax, eax
0x1800076b0  mov     [r13+30h], eax
0x1800076b4  mov     [r13+28h], rax
0x1800076b8  call    cs:__imp_GetProcessHeap
0x1800076be  mov     r8, r12; lpMem
0x1800076c1  xor     edx, edx; dwFlags
0x1800076c3  mov     rcx, rax; hHeap
0x1800076c6  call    cs:__imp_HeapFree
0x1800076cc  test    rsi, rsi
0x1800076cf  jnz     loc_180007645
0x1800076d5  mov     [rdi], rsi
0x1800076d8  add     rdi, 8
0x1800076dc  cmp     rdi, r15
0x1800076df  jnz     loc_18000763D
0x1800076e5  add     rsp, 28h
0x1800076e9  pop     r15
0x1800076eb  pop     r14
0x1800076ed  pop     r13
0x1800076ef  pop     r12
0x1800076f1  pop     rdi
0x1800076f2  pop     rsi
0x1800076f3  pop     rbp
0x1800076f4  pop     rbx
0x1800076f5  retn
```
