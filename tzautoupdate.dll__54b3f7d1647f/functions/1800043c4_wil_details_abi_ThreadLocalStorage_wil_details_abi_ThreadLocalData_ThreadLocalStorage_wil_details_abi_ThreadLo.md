# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800043c4`
- end: `0x18000449e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042e0`

## callees

- `0x1800043c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004442`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004460`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004442`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004460`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000441f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004450`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000446e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000441f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004450`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000446e`

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
0x1800043c4  push    rbx
0x1800043c6  push    rbp
0x1800043c7  push    rsi
0x1800043c8  push    rdi
0x1800043c9  push    r12
0x1800043cb  push    r13
0x1800043cd  push    r14
0x1800043cf  push    r15
0x1800043d1  sub     rsp, 28h
0x1800043d5  lea     r15, [rcx+50h]
0x1800043d9  mov     rdi, rcx
0x1800043dc  cmp     rcx, r15
0x1800043df  jz      loc_18000448D
0x1800043e5  mov     rsi, [rdi]
0x1800043e8  jmp     loc_180004474
0x1800043ed  mov     r13, rsi
0x1800043f0  mov     r12, rsi
0x1800043f3  mov     rsi, [rsi+8]
0x1800043f7  movzx   eax, word ptr [r13+30h]
0x1800043fc  mov     rbp, [r13+28h]
0x180004400  lea     r14, [rax+rax*4]
0x180004404  shl     r14, 4
0x180004408  add     r14, rbp
0x18000440b  jmp     short loc_180004439
0x18000440d  mov     rbx, [rbp+40h]
0x180004411  call    cs:__imp_GetProcessHeap
0x180004417  mov     r8, rbx; lpMem
0x18000441a  xor     edx, edx; dwFlags
0x18000441c  mov     rcx, rax; hHeap
0x18000441f  call    cs:__imp_HeapFree
0x180004425  mov     qword ptr [rbp+40h], 0
0x18000442d  mov     qword ptr [rbp+48h], 0
0x180004435  add     rbp, 50h ; 'P'
0x180004439  cmp     rbp, r14
0x18000443c  jnz     short loc_18000440D
0x18000443e  mov     rbx, [r13+28h]
0x180004442  call    cs:__imp_GetProcessHeap
0x180004448  mov     r8, rbx; lpMem
0x18000444b  xor     edx, edx; dwFlags
0x18000444d  mov     rcx, rax; hHeap
0x180004450  call    cs:__imp_HeapFree
0x180004456  xor     eax, eax
0x180004458  mov     [r13+30h], eax
0x18000445c  mov     [r13+28h], rax
0x180004460  call    cs:__imp_GetProcessHeap
0x180004466  mov     r8, r12; lpMem
0x180004469  xor     edx, edx; dwFlags
0x18000446b  mov     rcx, rax; hHeap
0x18000446e  call    cs:__imp_HeapFree
0x180004474  test    rsi, rsi
0x180004477  jnz     loc_1800043ED
0x18000447d  mov     [rdi], rsi
0x180004480  add     rdi, 8
0x180004484  cmp     rdi, r15
0x180004487  jnz     loc_1800043E5
0x18000448d  add     rsp, 28h
0x180004491  pop     r15
0x180004493  pop     r14
0x180004495  pop     r13
0x180004497  pop     r12
0x180004499  pop     rdi
0x18000449a  pop     rsi
0x18000449b  pop     rbp
0x18000449c  pop     rbx
0x18000449d  retn
```
