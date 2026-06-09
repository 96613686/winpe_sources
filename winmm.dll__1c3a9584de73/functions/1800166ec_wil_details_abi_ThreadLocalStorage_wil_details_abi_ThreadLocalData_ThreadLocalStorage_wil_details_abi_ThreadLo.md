# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800166ec`
- end: `0x1800167c6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001668c`

## callees

- `0x1800166ec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016739`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001676a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016788`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016739`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001676a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016788`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016747`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016796`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016747`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016778`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016796`

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
0x1800166ec  push    rbx
0x1800166ee  push    rbp
0x1800166ef  push    rsi
0x1800166f0  push    rdi
0x1800166f1  push    r12
0x1800166f3  push    r13
0x1800166f5  push    r14
0x1800166f7  push    r15
0x1800166f9  sub     rsp, 28h
0x1800166fd  lea     r15, [rcx+50h]
0x180016701  mov     rdi, rcx
0x180016704  cmp     rcx, r15
0x180016707  jz      loc_1800167B5
0x18001670d  mov     rsi, [rdi]
0x180016710  jmp     loc_18001679C
0x180016715  mov     r13, rsi
0x180016718  mov     r12, rsi
0x18001671b  mov     rsi, [rsi+8]
0x18001671f  movzx   eax, word ptr [r13+30h]
0x180016724  mov     rbp, [r13+28h]
0x180016728  lea     r14, [rax+rax*4]
0x18001672c  shl     r14, 4
0x180016730  add     r14, rbp
0x180016733  jmp     short loc_180016761
0x180016735  mov     rbx, [rbp+40h]
0x180016739  call    cs:__imp_GetProcessHeap
0x18001673f  mov     r8, rbx; lpMem
0x180016742  xor     edx, edx; dwFlags
0x180016744  mov     rcx, rax; hHeap
0x180016747  call    cs:__imp_HeapFree
0x18001674d  mov     qword ptr [rbp+40h], 0
0x180016755  mov     qword ptr [rbp+48h], 0
0x18001675d  add     rbp, 50h ; 'P'
0x180016761  cmp     rbp, r14
0x180016764  jnz     short loc_180016735
0x180016766  mov     rbx, [r13+28h]
0x18001676a  call    cs:__imp_GetProcessHeap
0x180016770  mov     r8, rbx; lpMem
0x180016773  xor     edx, edx; dwFlags
0x180016775  mov     rcx, rax; hHeap
0x180016778  call    cs:__imp_HeapFree
0x18001677e  xor     eax, eax
0x180016780  mov     [r13+30h], eax
0x180016784  mov     [r13+28h], rax
0x180016788  call    cs:__imp_GetProcessHeap
0x18001678e  mov     r8, r12; lpMem
0x180016791  xor     edx, edx; dwFlags
0x180016793  mov     rcx, rax; hHeap
0x180016796  call    cs:__imp_HeapFree
0x18001679c  test    rsi, rsi
0x18001679f  jnz     loc_180016715
0x1800167a5  mov     [rdi], rsi
0x1800167a8  add     rdi, 8
0x1800167ac  cmp     rdi, r15
0x1800167af  jnz     loc_18001670D
0x1800167b5  add     rsp, 28h
0x1800167b9  pop     r15
0x1800167bb  pop     r14
0x1800167bd  pop     r13
0x1800167bf  pop     r12
0x1800167c1  pop     rdi
0x1800167c2  pop     rsi
0x1800167c3  pop     rbp
0x1800167c4  pop     rbx
0x1800167c5  retn
```
