# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000d410`
- end: `0x18000d4ea`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d358`

## callees

- `0x18000d410`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d45d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d4ac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d45d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000d4ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d46b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d49c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d4ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d46b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d49c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000d4ba`

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
0x18000d410  push    rbx
0x18000d412  push    rbp
0x18000d413  push    rsi
0x18000d414  push    rdi
0x18000d415  push    r12
0x18000d417  push    r13
0x18000d419  push    r14
0x18000d41b  push    r15
0x18000d41d  sub     rsp, 28h
0x18000d421  lea     r15, [rcx+50h]
0x18000d425  mov     rdi, rcx
0x18000d428  cmp     rcx, r15
0x18000d42b  jz      loc_18000D4D9
0x18000d431  mov     rsi, [rdi]
0x18000d434  jmp     loc_18000D4C0
0x18000d439  mov     r13, rsi
0x18000d43c  mov     r12, rsi
0x18000d43f  mov     rsi, [rsi+8]
0x18000d443  movzx   eax, word ptr [r13+30h]
0x18000d448  mov     rbp, [r13+28h]
0x18000d44c  lea     r14, [rax+rax*4]
0x18000d450  shl     r14, 4
0x18000d454  add     r14, rbp
0x18000d457  jmp     short loc_18000D485
0x18000d459  mov     rbx, [rbp+40h]
0x18000d45d  call    cs:__imp_GetProcessHeap
0x18000d463  mov     r8, rbx; lpMem
0x18000d466  xor     edx, edx; dwFlags
0x18000d468  mov     rcx, rax; hHeap
0x18000d46b  call    cs:__imp_HeapFree
0x18000d471  mov     qword ptr [rbp+40h], 0
0x18000d479  mov     qword ptr [rbp+48h], 0
0x18000d481  add     rbp, 50h ; 'P'
0x18000d485  cmp     rbp, r14
0x18000d488  jnz     short loc_18000D459
0x18000d48a  mov     rbx, [r13+28h]
0x18000d48e  call    cs:__imp_GetProcessHeap
0x18000d494  mov     r8, rbx; lpMem
0x18000d497  xor     edx, edx; dwFlags
0x18000d499  mov     rcx, rax; hHeap
0x18000d49c  call    cs:__imp_HeapFree
0x18000d4a2  xor     eax, eax
0x18000d4a4  mov     [r13+30h], eax
0x18000d4a8  mov     [r13+28h], rax
0x18000d4ac  call    cs:__imp_GetProcessHeap
0x18000d4b2  mov     r8, r12; lpMem
0x18000d4b5  xor     edx, edx; dwFlags
0x18000d4b7  mov     rcx, rax; hHeap
0x18000d4ba  call    cs:__imp_HeapFree
0x18000d4c0  test    rsi, rsi
0x18000d4c3  jnz     loc_18000D439
0x18000d4c9  mov     [rdi], rsi
0x18000d4cc  add     rdi, 8
0x18000d4d0  cmp     rdi, r15
0x18000d4d3  jnz     loc_18000D431
0x18000d4d9  add     rsp, 28h
0x18000d4dd  pop     r15
0x18000d4df  pop     r14
0x18000d4e1  pop     r13
0x18000d4e3  pop     r12
0x18000d4e5  pop     rdi
0x18000d4e6  pop     rsi
0x18000d4e7  pop     rbp
0x18000d4e8  pop     rbx
0x18000d4e9  retn
```
