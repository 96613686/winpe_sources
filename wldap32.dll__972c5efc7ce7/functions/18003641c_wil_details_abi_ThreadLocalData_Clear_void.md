# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x18003641c`
- end: `0x1800364b1`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180035e78`

## callees

- `0x18003641c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036441`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003647e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180036441`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003647e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036492`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036455`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036492`

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
0x18003641c  push    rbx
0x18003641e  push    rbp
0x18003641f  push    rsi
0x180036420  push    rdi
0x180036421  sub     rsp, 28h
0x180036425  movzx   eax, word ptr [rcx+20h]
0x180036429  mov     rsi, rcx
0x18003642c  mov     rdi, [rcx+18h]
0x180036430  lea     rbp, [rax+rax*4]
0x180036434  shl     rbp, 4
0x180036438  add     rbp, rdi
0x18003643b  jmp     short loc_180036475
0x18003643d  mov     rbx, [rdi+40h]
0x180036441  call    cs:__imp_GetProcessHeap
0x180036448  nop     dword ptr [rax+rax+00h]
0x18003644d  mov     r8, rbx; lpMem
0x180036450  xor     edx, edx; dwFlags
0x180036452  mov     rcx, rax; hHeap
0x180036455  call    cs:__imp_HeapFree
0x18003645c  nop     dword ptr [rax+rax+00h]
0x180036461  mov     qword ptr [rdi+40h], 0
0x180036469  mov     qword ptr [rdi+48h], 0
0x180036471  add     rdi, 50h ; 'P'
0x180036475  cmp     rdi, rbp
0x180036478  jnz     short loc_18003643D
0x18003647a  mov     rbx, [rsi+18h]
0x18003647e  call    cs:__imp_GetProcessHeap
0x180036485  nop     dword ptr [rax+rax+00h]
0x18003648a  mov     r8, rbx; lpMem
0x18003648d  xor     edx, edx; dwFlags
0x18003648f  mov     rcx, rax; hHeap
0x180036492  call    cs:__imp_HeapFree
0x180036499  nop     dword ptr [rax+rax+00h]
0x18003649e  xor     eax, eax
0x1800364a0  mov     [rsi+20h], eax
0x1800364a3  mov     [rsi+18h], rax
0x1800364a7  add     rsp, 28h
0x1800364ab  pop     rdi
0x1800364ac  pop     rsi
0x1800364ad  pop     rbp
0x1800364ae  pop     rbx
0x1800364af  retn
```
