# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180008650`
- end: `0x18000872a`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008620`

## callees

- `0x180008650`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000869d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000869d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086ec`

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
0x180008650  push    rbx
0x180008652  push    rbp
0x180008653  push    rsi
0x180008654  push    rdi
0x180008655  push    r12
0x180008657  push    r13
0x180008659  push    r14
0x18000865b  push    r15
0x18000865d  sub     rsp, 28h
0x180008661  lea     r15, [rcx+50h]
0x180008665  mov     rdi, rcx
0x180008668  cmp     rcx, r15
0x18000866b  jz      loc_180008719
0x180008671  mov     rsi, [rdi]
0x180008674  jmp     loc_180008700
0x180008679  mov     r13, rsi
0x18000867c  mov     r12, rsi
0x18000867f  mov     rsi, [rsi+8]
0x180008683  movzx   eax, word ptr [r13+30h]
0x180008688  mov     rbp, [r13+28h]
0x18000868c  lea     r14, [rax+rax*4]
0x180008690  shl     r14, 4
0x180008694  add     r14, rbp
0x180008697  jmp     short loc_1800086C5
0x180008699  mov     rbx, [rbp+40h]
0x18000869d  call    cs:__imp_GetProcessHeap
0x1800086a3  mov     r8, rbx; lpMem
0x1800086a6  xor     edx, edx; dwFlags
0x1800086a8  mov     rcx, rax; hHeap
0x1800086ab  call    cs:__imp_HeapFree
0x1800086b1  mov     qword ptr [rbp+40h], 0
0x1800086b9  mov     qword ptr [rbp+48h], 0
0x1800086c1  add     rbp, 50h ; 'P'
0x1800086c5  cmp     rbp, r14
0x1800086c8  jnz     short loc_180008699
0x1800086ca  mov     rbx, [r13+28h]
0x1800086ce  call    cs:__imp_GetProcessHeap
0x1800086d4  mov     r8, rbx; lpMem
0x1800086d7  xor     edx, edx; dwFlags
0x1800086d9  mov     rcx, rax; hHeap
0x1800086dc  call    cs:__imp_HeapFree
0x1800086e2  xor     eax, eax
0x1800086e4  mov     [r13+30h], eax
0x1800086e8  mov     [r13+28h], rax
0x1800086ec  call    cs:__imp_GetProcessHeap
0x1800086f2  mov     r8, r12; lpMem
0x1800086f5  xor     edx, edx; dwFlags
0x1800086f7  mov     rcx, rax; hHeap
0x1800086fa  call    cs:__imp_HeapFree
0x180008700  test    rsi, rsi
0x180008703  jnz     loc_180008679
0x180008709  mov     [rdi], rsi
0x18000870c  add     rdi, 8
0x180008710  cmp     rdi, r15
0x180008713  jnz     loc_180008671
0x180008719  add     rsp, 28h
0x18000871d  pop     r15
0x18000871f  pop     r14
0x180008721  pop     r13
0x180008723  pop     r12
0x180008725  pop     rdi
0x180008726  pop     rsi
0x180008727  pop     rbp
0x180008728  pop     rbx
0x180008729  retn
```
