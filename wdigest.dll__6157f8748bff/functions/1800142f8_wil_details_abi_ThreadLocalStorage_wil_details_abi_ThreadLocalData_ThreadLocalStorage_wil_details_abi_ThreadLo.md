# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800142f8`
- end: `0x1800143d2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014298`

## callees

- `0x1800142f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014353`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014384`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800143a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014353`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014384`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800143a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014376`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014394`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014376`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014394`

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
0x1800142f8  push    rbx
0x1800142fa  push    rbp
0x1800142fb  push    rsi
0x1800142fc  push    rdi
0x1800142fd  push    r12
0x1800142ff  push    r13
0x180014301  push    r14
0x180014303  push    r15
0x180014305  sub     rsp, 28h
0x180014309  lea     r15, [rcx+50h]
0x18001430d  mov     rdi, rcx
0x180014310  cmp     rcx, r15
0x180014313  jz      loc_1800143C1
0x180014319  mov     rsi, [rdi]
0x18001431c  jmp     loc_1800143A8
0x180014321  mov     r13, rsi
0x180014324  mov     r12, rsi
0x180014327  mov     rsi, [rsi+8]
0x18001432b  movzx   eax, word ptr [r13+30h]
0x180014330  mov     rbp, [r13+28h]
0x180014334  lea     r14, [rax+rax*4]
0x180014338  shl     r14, 4
0x18001433c  add     r14, rbp
0x18001433f  jmp     short loc_18001436D
0x180014341  mov     rbx, [rbp+40h]
0x180014345  call    cs:__imp_GetProcessHeap
0x18001434b  mov     r8, rbx; lpMem
0x18001434e  xor     edx, edx; dwFlags
0x180014350  mov     rcx, rax; hHeap
0x180014353  call    cs:__imp_HeapFree
0x180014359  mov     qword ptr [rbp+40h], 0
0x180014361  mov     qword ptr [rbp+48h], 0
0x180014369  add     rbp, 50h ; 'P'
0x18001436d  cmp     rbp, r14
0x180014370  jnz     short loc_180014341
0x180014372  mov     rbx, [r13+28h]
0x180014376  call    cs:__imp_GetProcessHeap
0x18001437c  mov     r8, rbx; lpMem
0x18001437f  xor     edx, edx; dwFlags
0x180014381  mov     rcx, rax; hHeap
0x180014384  call    cs:__imp_HeapFree
0x18001438a  xor     eax, eax
0x18001438c  mov     [r13+30h], eax
0x180014390  mov     [r13+28h], rax
0x180014394  call    cs:__imp_GetProcessHeap
0x18001439a  mov     r8, r12; lpMem
0x18001439d  xor     edx, edx; dwFlags
0x18001439f  mov     rcx, rax; hHeap
0x1800143a2  call    cs:__imp_HeapFree
0x1800143a8  test    rsi, rsi
0x1800143ab  jnz     loc_180014321
0x1800143b1  mov     [rdi], rsi
0x1800143b4  add     rdi, 8
0x1800143b8  cmp     rdi, r15
0x1800143bb  jnz     loc_180014319
0x1800143c1  add     rsp, 28h
0x1800143c5  pop     r15
0x1800143c7  pop     r14
0x1800143c9  pop     r13
0x1800143cb  pop     r12
0x1800143cd  pop     rdi
0x1800143ce  pop     rsi
0x1800143cf  pop     rbp
0x1800143d0  pop     rbx
0x1800143d1  retn
```
