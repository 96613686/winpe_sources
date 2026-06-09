# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003670`
- end: `0x18000374a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035e8`

## callees

- `0x180003670`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000371a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800036fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000371a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000370c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800036ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000370c`

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
0x180003670  push    rbx
0x180003672  push    rbp
0x180003673  push    rsi
0x180003674  push    rdi
0x180003675  push    r12
0x180003677  push    r13
0x180003679  push    r14
0x18000367b  push    r15
0x18000367d  sub     rsp, 28h
0x180003681  lea     r15, [rcx+50h]
0x180003685  mov     rdi, rcx
0x180003688  cmp     rcx, r15
0x18000368b  jz      loc_180003739
0x180003691  mov     rsi, [rdi]
0x180003694  jmp     loc_180003720
0x180003699  mov     r13, rsi
0x18000369c  mov     r12, rsi
0x18000369f  mov     rsi, [rsi+8]
0x1800036a3  movzx   eax, word ptr [r13+30h]
0x1800036a8  mov     rbp, [r13+28h]
0x1800036ac  lea     r14, [rax+rax*4]
0x1800036b0  shl     r14, 4
0x1800036b4  add     r14, rbp
0x1800036b7  jmp     short loc_1800036E5
0x1800036b9  mov     rbx, [rbp+40h]
0x1800036bd  call    cs:__imp_GetProcessHeap
0x1800036c3  mov     r8, rbx; lpMem
0x1800036c6  xor     edx, edx; dwFlags
0x1800036c8  mov     rcx, rax; hHeap
0x1800036cb  call    cs:__imp_HeapFree
0x1800036d1  mov     qword ptr [rbp+40h], 0
0x1800036d9  mov     qword ptr [rbp+48h], 0
0x1800036e1  add     rbp, 50h ; 'P'
0x1800036e5  cmp     rbp, r14
0x1800036e8  jnz     short loc_1800036B9
0x1800036ea  mov     rbx, [r13+28h]
0x1800036ee  call    cs:__imp_GetProcessHeap
0x1800036f4  mov     r8, rbx; lpMem
0x1800036f7  xor     edx, edx; dwFlags
0x1800036f9  mov     rcx, rax; hHeap
0x1800036fc  call    cs:__imp_HeapFree
0x180003702  xor     eax, eax
0x180003704  mov     [r13+30h], eax
0x180003708  mov     [r13+28h], rax
0x18000370c  call    cs:__imp_GetProcessHeap
0x180003712  mov     r8, r12; lpMem
0x180003715  xor     edx, edx; dwFlags
0x180003717  mov     rcx, rax; hHeap
0x18000371a  call    cs:__imp_HeapFree
0x180003720  test    rsi, rsi
0x180003723  jnz     loc_180003699
0x180003729  mov     [rdi], rsi
0x18000372c  add     rdi, 8
0x180003730  cmp     rdi, r15
0x180003733  jnz     loc_180003691
0x180003739  add     rsp, 28h
0x18000373d  pop     r15
0x18000373f  pop     r14
0x180003741  pop     r13
0x180003743  pop     r12
0x180003745  pop     rdi
0x180003746  pop     rsi
0x180003747  pop     rbp
0x180003748  pop     rbx
0x180003749  retn
```
