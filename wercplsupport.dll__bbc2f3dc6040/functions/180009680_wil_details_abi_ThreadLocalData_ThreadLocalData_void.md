# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180009680`
- end: `0x1800096fc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009078`

## callees

- `0x180009680`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800096e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800096d6`

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
0x180009680  push    rbx
0x180009682  push    rbp
0x180009683  push    rsi
0x180009684  push    rdi
0x180009685  sub     rsp, 28h
0x180009689  movzx   eax, word ptr [rcx+20h]
0x18000968d  mov     rsi, rcx
0x180009690  mov     rdi, [rcx+18h]
0x180009694  lea     rbp, [rax+rax*4]
0x180009698  shl     rbp, 4
0x18000969c  add     rbp, rdi
0x18000969f  jmp     short loc_1800096CD
0x1800096a1  mov     rbx, [rdi+40h]
0x1800096a5  call    cs:__imp_GetProcessHeap
0x1800096ab  mov     r8, rbx; lpMem
0x1800096ae  xor     edx, edx; dwFlags
0x1800096b0  mov     rcx, rax; hHeap
0x1800096b3  call    cs:__imp_HeapFree
0x1800096b9  mov     qword ptr [rdi+40h], 0
0x1800096c1  mov     qword ptr [rdi+48h], 0
0x1800096c9  add     rdi, 50h ; 'P'
0x1800096cd  cmp     rdi, rbp
0x1800096d0  jnz     short loc_1800096A1
0x1800096d2  mov     rbx, [rsi+18h]
0x1800096d6  call    cs:__imp_GetProcessHeap
0x1800096dc  mov     r8, rbx; lpMem
0x1800096df  xor     edx, edx; dwFlags
0x1800096e1  mov     rcx, rax; hHeap
0x1800096e4  call    cs:__imp_HeapFree
0x1800096ea  xor     eax, eax
0x1800096ec  mov     [rsi+20h], eax
0x1800096ef  mov     [rsi+18h], rax
0x1800096f3  add     rsp, 28h
0x1800096f7  pop     rdi
0x1800096f8  pop     rsi
0x1800096f9  pop     rbp
0x1800096fa  pop     rbx
0x1800096fb  retn
```
