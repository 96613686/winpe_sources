# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180007f88`
- end: `0x180008004`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007dd8`

## callees

- `0x180007f88`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007fde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007fec`

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
0x180007f88  push    rbx
0x180007f8a  push    rbp
0x180007f8b  push    rsi
0x180007f8c  push    rdi
0x180007f8d  sub     rsp, 28h
0x180007f91  movzx   eax, word ptr [rcx+20h]
0x180007f95  mov     rsi, rcx
0x180007f98  mov     rdi, [rcx+18h]
0x180007f9c  lea     rbp, [rax+rax*4]
0x180007fa0  shl     rbp, 4
0x180007fa4  add     rbp, rdi
0x180007fa7  jmp     short loc_180007FD5
0x180007fa9  mov     rbx, [rdi+40h]
0x180007fad  call    cs:__imp_GetProcessHeap
0x180007fb3  mov     r8, rbx; lpMem
0x180007fb6  xor     edx, edx; dwFlags
0x180007fb8  mov     rcx, rax; hHeap
0x180007fbb  call    cs:__imp_HeapFree
0x180007fc1  mov     qword ptr [rdi+40h], 0
0x180007fc9  mov     qword ptr [rdi+48h], 0
0x180007fd1  add     rdi, 50h ; 'P'
0x180007fd5  cmp     rdi, rbp
0x180007fd8  jnz     short loc_180007FA9
0x180007fda  mov     rbx, [rsi+18h]
0x180007fde  call    cs:__imp_GetProcessHeap
0x180007fe4  mov     r8, rbx; lpMem
0x180007fe7  xor     edx, edx; dwFlags
0x180007fe9  mov     rcx, rax; hHeap
0x180007fec  call    cs:__imp_HeapFree
0x180007ff2  xor     eax, eax
0x180007ff4  mov     [rsi+20h], eax
0x180007ff7  mov     [rsi+18h], rax
0x180007ffb  add     rsp, 28h
0x180007fff  pop     rdi
0x180008000  pop     rsi
0x180008001  pop     rbp
0x180008002  pop     rbx
0x180008003  retn
```
