# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x180018dec`
- end: `0x180018e81`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800186a0`

## callees

- `0x180018dec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018e25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018e62`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018e25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180018e62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018e4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018e11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180018e4e`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
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
0x180018dec  push    rbx
0x180018dee  push    rbp
0x180018def  push    rsi
0x180018df0  push    rdi
0x180018df1  sub     rsp, 28h
0x180018df5  movzx   eax, word ptr [rcx+20h]
0x180018df9  mov     rsi, rcx
0x180018dfc  mov     rdi, [rcx+18h]
0x180018e00  lea     rbp, [rax+rax*4]
0x180018e04  shl     rbp, 4
0x180018e08  add     rbp, rdi
0x180018e0b  jmp     short loc_180018E45
0x180018e0d  mov     rbx, [rdi+40h]
0x180018e11  call    cs:__imp_GetProcessHeap
0x180018e18  nop     dword ptr [rax+rax+00h]
0x180018e1d  mov     r8, rbx; lpMem
0x180018e20  xor     edx, edx; dwFlags
0x180018e22  mov     rcx, rax; hHeap
0x180018e25  call    cs:__imp_HeapFree
0x180018e2c  nop     dword ptr [rax+rax+00h]
0x180018e31  mov     qword ptr [rdi+40h], 0
0x180018e39  mov     qword ptr [rdi+48h], 0
0x180018e41  add     rdi, 50h ; 'P'
0x180018e45  cmp     rdi, rbp
0x180018e48  jnz     short loc_180018E0D
0x180018e4a  mov     rbx, [rsi+18h]
0x180018e4e  call    cs:__imp_GetProcessHeap
0x180018e55  nop     dword ptr [rax+rax+00h]
0x180018e5a  mov     r8, rbx; lpMem
0x180018e5d  xor     edx, edx; dwFlags
0x180018e5f  mov     rcx, rax; hHeap
0x180018e62  call    cs:__imp_HeapFree
0x180018e69  nop     dword ptr [rax+rax+00h]
0x180018e6e  xor     eax, eax
0x180018e70  mov     [rsi+20h], eax
0x180018e73  mov     [rsi+18h], rax
0x180018e77  add     rsp, 28h
0x180018e7b  pop     rdi
0x180018e7c  pop     rsi
0x180018e7d  pop     rbp
0x180018e7e  pop     rbx
0x180018e7f  retn
```
