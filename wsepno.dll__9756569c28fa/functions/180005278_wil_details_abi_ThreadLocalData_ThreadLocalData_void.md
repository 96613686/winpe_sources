# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180005278`
- end: `0x1800052f4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004b28`

## callees

- `0x180005278`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052dc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052ab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000529d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000529d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800052ce`

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
0x180005278  push    rbx
0x18000527a  push    rbp
0x18000527b  push    rsi
0x18000527c  push    rdi
0x18000527d  sub     rsp, 28h
0x180005281  movzx   eax, word ptr [rcx+20h]
0x180005285  mov     rsi, rcx
0x180005288  mov     rdi, [rcx+18h]
0x18000528c  lea     rbp, [rax+rax*4]
0x180005290  shl     rbp, 4
0x180005294  add     rbp, rdi
0x180005297  jmp     short loc_1800052C5
0x180005299  mov     rbx, [rdi+40h]
0x18000529d  call    cs:__imp_GetProcessHeap
0x1800052a3  mov     r8, rbx; lpMem
0x1800052a6  xor     edx, edx; dwFlags
0x1800052a8  mov     rcx, rax; hHeap
0x1800052ab  call    cs:__imp_HeapFree
0x1800052b1  mov     qword ptr [rdi+40h], 0
0x1800052b9  mov     qword ptr [rdi+48h], 0
0x1800052c1  add     rdi, 50h ; 'P'
0x1800052c5  cmp     rdi, rbp
0x1800052c8  jnz     short loc_180005299
0x1800052ca  mov     rbx, [rsi+18h]
0x1800052ce  call    cs:__imp_GetProcessHeap
0x1800052d4  mov     r8, rbx; lpMem
0x1800052d7  xor     edx, edx; dwFlags
0x1800052d9  mov     rcx, rax; hHeap
0x1800052dc  call    cs:__imp_HeapFree
0x1800052e2  xor     eax, eax
0x1800052e4  mov     [rsi+20h], eax
0x1800052e7  mov     [rsi+18h], rax
0x1800052eb  add     rsp, 28h
0x1800052ef  pop     rdi
0x1800052f0  pop     rsi
0x1800052f1  pop     rbp
0x1800052f2  pop     rbx
0x1800052f3  retn
```
