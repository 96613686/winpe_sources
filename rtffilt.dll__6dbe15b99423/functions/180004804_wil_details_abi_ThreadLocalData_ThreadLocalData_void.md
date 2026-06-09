# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004804`
- end: `0x180004880`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fa0`

## callees

- `0x180004804`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000485a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004829`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000485a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004837`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004868`

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
0x180004804  push    rbx
0x180004806  push    rbp
0x180004807  push    rsi
0x180004808  push    rdi
0x180004809  sub     rsp, 28h
0x18000480d  movzx   eax, word ptr [rcx+20h]
0x180004811  mov     rsi, rcx
0x180004814  mov     rdi, [rcx+18h]
0x180004818  lea     rbp, [rax+rax*4]
0x18000481c  shl     rbp, 4
0x180004820  add     rbp, rdi
0x180004823  jmp     short loc_180004851
0x180004825  mov     rbx, [rdi+40h]
0x180004829  call    cs:__imp_GetProcessHeap
0x18000482f  mov     r8, rbx; lpMem
0x180004832  xor     edx, edx; dwFlags
0x180004834  mov     rcx, rax; hHeap
0x180004837  call    cs:__imp_HeapFree
0x18000483d  mov     qword ptr [rdi+40h], 0
0x180004845  mov     qword ptr [rdi+48h], 0
0x18000484d  add     rdi, 50h ; 'P'
0x180004851  cmp     rdi, rbp
0x180004854  jnz     short loc_180004825
0x180004856  mov     rbx, [rsi+18h]
0x18000485a  call    cs:__imp_GetProcessHeap
0x180004860  mov     r8, rbx; lpMem
0x180004863  xor     edx, edx; dwFlags
0x180004865  mov     rcx, rax; hHeap
0x180004868  call    cs:__imp_HeapFree
0x18000486e  xor     eax, eax
0x180004870  mov     [rsi+20h], eax
0x180004873  mov     [rsi+18h], rax
0x180004877  add     rsp, 28h
0x18000487b  pop     rdi
0x18000487c  pop     rsi
0x18000487d  pop     rbp
0x18000487e  pop     rbx
0x18000487f  retn
```
