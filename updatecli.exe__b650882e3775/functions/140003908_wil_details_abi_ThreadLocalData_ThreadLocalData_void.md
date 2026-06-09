# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003908`
- end: `0x140003984`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003750`

## callees

- `0x140003908`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000392d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000395e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000392d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000395e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000393b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000396c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000393b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000396c`

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
0x140003908  push    rbx
0x14000390a  push    rbp
0x14000390b  push    rsi
0x14000390c  push    rdi
0x14000390d  sub     rsp, 28h
0x140003911  movzx   eax, word ptr [rcx+20h]
0x140003915  mov     rsi, rcx
0x140003918  mov     rdi, [rcx+18h]
0x14000391c  lea     rbp, [rax+rax*4]
0x140003920  shl     rbp, 4
0x140003924  add     rbp, rdi
0x140003927  jmp     short loc_140003955
0x140003929  mov     rbx, [rdi+40h]
0x14000392d  call    cs:__imp_GetProcessHeap
0x140003933  mov     r8, rbx; lpMem
0x140003936  xor     edx, edx; dwFlags
0x140003938  mov     rcx, rax; hHeap
0x14000393b  call    cs:__imp_HeapFree
0x140003941  mov     qword ptr [rdi+40h], 0
0x140003949  mov     qword ptr [rdi+48h], 0
0x140003951  add     rdi, 50h ; 'P'
0x140003955  cmp     rdi, rbp
0x140003958  jnz     short loc_140003929
0x14000395a  mov     rbx, [rsi+18h]
0x14000395e  call    cs:__imp_GetProcessHeap
0x140003964  mov     r8, rbx; lpMem
0x140003967  xor     edx, edx; dwFlags
0x140003969  mov     rcx, rax; hHeap
0x14000396c  call    cs:__imp_HeapFree
0x140003972  xor     eax, eax
0x140003974  mov     [rsi+20h], eax
0x140003977  mov     [rsi+18h], rax
0x14000397b  add     rsp, 28h
0x14000397f  pop     rdi
0x140003980  pop     rsi
0x140003981  pop     rbp
0x140003982  pop     rbx
0x140003983  retn
```
