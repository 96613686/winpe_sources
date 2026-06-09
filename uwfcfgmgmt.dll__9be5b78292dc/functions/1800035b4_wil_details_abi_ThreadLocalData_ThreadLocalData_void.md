# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800035b4`
- end: `0x180003630`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034e8`

## callees

- `0x1800035b4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000360a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800035d9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000360a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003618`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800035e7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003618`

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
0x1800035b4  push    rbx
0x1800035b6  push    rbp
0x1800035b7  push    rsi
0x1800035b8  push    rdi
0x1800035b9  sub     rsp, 28h
0x1800035bd  movzx   eax, word ptr [rcx+20h]
0x1800035c1  mov     rsi, rcx
0x1800035c4  mov     rdi, [rcx+18h]
0x1800035c8  lea     rbp, [rax+rax*4]
0x1800035cc  shl     rbp, 4
0x1800035d0  add     rbp, rdi
0x1800035d3  jmp     short loc_180003601
0x1800035d5  mov     rbx, [rdi+40h]
0x1800035d9  call    cs:__imp_GetProcessHeap
0x1800035df  mov     r8, rbx; lpMem
0x1800035e2  xor     edx, edx; dwFlags
0x1800035e4  mov     rcx, rax; hHeap
0x1800035e7  call    cs:__imp_HeapFree
0x1800035ed  mov     qword ptr [rdi+40h], 0
0x1800035f5  mov     qword ptr [rdi+48h], 0
0x1800035fd  add     rdi, 50h ; 'P'
0x180003601  cmp     rdi, rbp
0x180003604  jnz     short loc_1800035D5
0x180003606  mov     rbx, [rsi+18h]
0x18000360a  call    cs:__imp_GetProcessHeap
0x180003610  mov     r8, rbx; lpMem
0x180003613  xor     edx, edx; dwFlags
0x180003615  mov     rcx, rax; hHeap
0x180003618  call    cs:__imp_HeapFree
0x18000361e  xor     eax, eax
0x180003620  mov     [rsi+20h], eax
0x180003623  mov     [rsi+18h], rax
0x180003627  add     rsp, 28h
0x18000362b  pop     rdi
0x18000362c  pop     rsi
0x18000362d  pop     rbp
0x18000362e  pop     rbx
0x18000362f  retn
```
