# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400052f0`
- end: `0x14000536c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004e28`

## callees

- `0x1400052f0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005354`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005354`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005346`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005315`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005346`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1400052f0  push    rbx
0x1400052f2  push    rbp
0x1400052f3  push    rsi
0x1400052f4  push    rdi
0x1400052f5  sub     rsp, 28h
0x1400052f9  movzx   eax, word ptr [rcx+20h]
0x1400052fd  mov     rsi, rcx
0x140005300  mov     rdi, [rcx+18h]
0x140005304  lea     rbp, [rax+rax*4]
0x140005308  shl     rbp, 4
0x14000530c  add     rbp, rdi
0x14000530f  jmp     short loc_14000533D
0x140005311  mov     rbx, [rdi+40h]
0x140005315  call    cs:__imp_GetProcessHeap
0x14000531b  mov     r8, rbx; lpMem
0x14000531e  xor     edx, edx; dwFlags
0x140005320  mov     rcx, rax; hHeap
0x140005323  call    cs:__imp_HeapFree
0x140005329  mov     qword ptr [rdi+40h], 0
0x140005331  mov     qword ptr [rdi+48h], 0
0x140005339  add     rdi, 50h ; 'P'
0x14000533d  cmp     rdi, rbp
0x140005340  jnz     short loc_140005311
0x140005342  mov     rbx, [rsi+18h]
0x140005346  call    cs:__imp_GetProcessHeap
0x14000534c  mov     r8, rbx; lpMem
0x14000534f  xor     edx, edx; dwFlags
0x140005351  mov     rcx, rax; hHeap
0x140005354  call    cs:__imp_HeapFree
0x14000535a  xor     eax, eax
0x14000535c  mov     [rsi+20h], eax
0x14000535f  mov     [rsi+18h], rax
0x140005363  add     rsp, 28h
0x140005367  pop     rdi
0x140005368  pop     rsi
0x140005369  pop     rbp
0x14000536a  pop     rbx
0x14000536b  retn
```
