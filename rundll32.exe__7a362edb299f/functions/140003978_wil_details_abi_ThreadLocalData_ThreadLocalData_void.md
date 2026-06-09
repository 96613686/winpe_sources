# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003978`
- end: `0x1400039f4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000388c`

## callees

- `0x140003978`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400039dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000399d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000399d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400039ce`

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
0x140003978  push    rbx
0x14000397a  push    rbp
0x14000397b  push    rsi
0x14000397c  push    rdi
0x14000397d  sub     rsp, 28h
0x140003981  movzx   eax, word ptr [rcx+20h]
0x140003985  mov     rsi, rcx
0x140003988  mov     rdi, [rcx+18h]
0x14000398c  lea     rbp, [rax+rax*4]
0x140003990  shl     rbp, 4
0x140003994  add     rbp, rdi
0x140003997  jmp     short loc_1400039C5
0x140003999  mov     rbx, [rdi+40h]
0x14000399d  call    cs:__imp_GetProcessHeap
0x1400039a3  mov     r8, rbx; lpMem
0x1400039a6  xor     edx, edx; dwFlags
0x1400039a8  mov     rcx, rax; hHeap
0x1400039ab  call    cs:__imp_HeapFree
0x1400039b1  mov     qword ptr [rdi+40h], 0
0x1400039b9  mov     qword ptr [rdi+48h], 0
0x1400039c1  add     rdi, 50h ; 'P'
0x1400039c5  cmp     rdi, rbp
0x1400039c8  jnz     short loc_140003999
0x1400039ca  mov     rbx, [rsi+18h]
0x1400039ce  call    cs:__imp_GetProcessHeap
0x1400039d4  mov     r8, rbx; lpMem
0x1400039d7  xor     edx, edx; dwFlags
0x1400039d9  mov     rcx, rax; hHeap
0x1400039dc  call    cs:__imp_HeapFree
0x1400039e2  xor     eax, eax
0x1400039e4  mov     [rsi+20h], eax
0x1400039e7  mov     [rsi+18h], rax
0x1400039eb  add     rsp, 28h
0x1400039ef  pop     rdi
0x1400039f0  pop     rsi
0x1400039f1  pop     rbp
0x1400039f2  pop     rbx
0x1400039f3  retn
```
