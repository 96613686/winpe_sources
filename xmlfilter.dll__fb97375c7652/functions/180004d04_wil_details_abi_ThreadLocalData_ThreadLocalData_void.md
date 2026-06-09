# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180004d04`
- end: `0x180004d80`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043a8`

## callees

- `0x180004d04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004d68`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004d5a`

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
0x180004d04  push    rbx
0x180004d06  push    rbp
0x180004d07  push    rsi
0x180004d08  push    rdi
0x180004d09  sub     rsp, 28h
0x180004d0d  movzx   eax, word ptr [rcx+20h]
0x180004d11  mov     rsi, rcx
0x180004d14  mov     rdi, [rcx+18h]
0x180004d18  lea     rbp, [rax+rax*4]
0x180004d1c  shl     rbp, 4
0x180004d20  add     rbp, rdi
0x180004d23  jmp     short loc_180004D51
0x180004d25  mov     rbx, [rdi+40h]
0x180004d29  call    cs:__imp_GetProcessHeap
0x180004d2f  mov     r8, rbx; lpMem
0x180004d32  xor     edx, edx; dwFlags
0x180004d34  mov     rcx, rax; hHeap
0x180004d37  call    cs:__imp_HeapFree
0x180004d3d  mov     qword ptr [rdi+40h], 0
0x180004d45  mov     qword ptr [rdi+48h], 0
0x180004d4d  add     rdi, 50h ; 'P'
0x180004d51  cmp     rdi, rbp
0x180004d54  jnz     short loc_180004D25
0x180004d56  mov     rbx, [rsi+18h]
0x180004d5a  call    cs:__imp_GetProcessHeap
0x180004d60  mov     r8, rbx; lpMem
0x180004d63  xor     edx, edx; dwFlags
0x180004d65  mov     rcx, rax; hHeap
0x180004d68  call    cs:__imp_HeapFree
0x180004d6e  xor     eax, eax
0x180004d70  mov     [rsi+20h], eax
0x180004d73  mov     [rsi+18h], rax
0x180004d77  add     rsp, 28h
0x180004d7b  pop     rdi
0x180004d7c  pop     rsi
0x180004d7d  pop     rbp
0x180004d7e  pop     rbx
0x180004d7f  retn
```
