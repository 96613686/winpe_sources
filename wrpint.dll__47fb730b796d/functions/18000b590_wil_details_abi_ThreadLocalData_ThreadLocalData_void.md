# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18000b590`
- end: `0x18000b60c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b184`

## callees

- `0x18000b590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5e6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5f4`

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
0x18000b590  push    rbx
0x18000b592  push    rbp
0x18000b593  push    rsi
0x18000b594  push    rdi
0x18000b595  sub     rsp, 28h
0x18000b599  movzx   eax, word ptr [rcx+20h]
0x18000b59d  mov     rsi, rcx
0x18000b5a0  mov     rdi, [rcx+18h]
0x18000b5a4  lea     rbp, [rax+rax*4]
0x18000b5a8  shl     rbp, 4
0x18000b5ac  add     rbp, rdi
0x18000b5af  jmp     short loc_18000B5DD
0x18000b5b1  mov     rbx, [rdi+40h]
0x18000b5b5  call    cs:__imp_GetProcessHeap
0x18000b5bb  mov     r8, rbx; lpMem
0x18000b5be  xor     edx, edx; dwFlags
0x18000b5c0  mov     rcx, rax; hHeap
0x18000b5c3  call    cs:__imp_HeapFree
0x18000b5c9  mov     qword ptr [rdi+40h], 0
0x18000b5d1  mov     qword ptr [rdi+48h], 0
0x18000b5d9  add     rdi, 50h ; 'P'
0x18000b5dd  cmp     rdi, rbp
0x18000b5e0  jnz     short loc_18000B5B1
0x18000b5e2  mov     rbx, [rsi+18h]
0x18000b5e6  call    cs:__imp_GetProcessHeap
0x18000b5ec  mov     r8, rbx; lpMem
0x18000b5ef  xor     edx, edx; dwFlags
0x18000b5f1  mov     rcx, rax; hHeap
0x18000b5f4  call    cs:__imp_HeapFree
0x18000b5fa  xor     eax, eax
0x18000b5fc  mov     [rsi+20h], eax
0x18000b5ff  mov     [rsi+18h], rax
0x18000b603  add     rsp, 28h
0x18000b607  pop     rdi
0x18000b608  pop     rsi
0x18000b609  pop     rbp
0x18000b60a  pop     rbx
0x18000b60b  retn
```
