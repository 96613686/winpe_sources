# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800040c0`
- end: `0x18000413c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003ff4`

## callees

- `0x1800040c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004116`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800040e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004116`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004124`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800040f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004124`

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
0x1800040c0  push    rbx
0x1800040c2  push    rbp
0x1800040c3  push    rsi
0x1800040c4  push    rdi
0x1800040c5  sub     rsp, 28h
0x1800040c9  movzx   eax, word ptr [rcx+20h]
0x1800040cd  mov     rsi, rcx
0x1800040d0  mov     rdi, [rcx+18h]
0x1800040d4  lea     rbp, [rax+rax*4]
0x1800040d8  shl     rbp, 4
0x1800040dc  add     rbp, rdi
0x1800040df  jmp     short loc_18000410D
0x1800040e1  mov     rbx, [rdi+40h]
0x1800040e5  call    cs:__imp_GetProcessHeap
0x1800040eb  mov     r8, rbx; lpMem
0x1800040ee  xor     edx, edx; dwFlags
0x1800040f0  mov     rcx, rax; hHeap
0x1800040f3  call    cs:__imp_HeapFree
0x1800040f9  mov     qword ptr [rdi+40h], 0
0x180004101  mov     qword ptr [rdi+48h], 0
0x180004109  add     rdi, 50h ; 'P'
0x18000410d  cmp     rdi, rbp
0x180004110  jnz     short loc_1800040E1
0x180004112  mov     rbx, [rsi+18h]
0x180004116  call    cs:__imp_GetProcessHeap
0x18000411c  mov     r8, rbx; lpMem
0x18000411f  xor     edx, edx; dwFlags
0x180004121  mov     rcx, rax; hHeap
0x180004124  call    cs:__imp_HeapFree
0x18000412a  xor     eax, eax
0x18000412c  mov     [rsi+20h], eax
0x18000412f  mov     [rsi+18h], rax
0x180004133  add     rsp, 28h
0x180004137  pop     rdi
0x180004138  pop     rsi
0x180004139  pop     rbp
0x18000413a  pop     rbx
0x18000413b  retn
```
