# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003928`
- end: `0x1400039a4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003770`

## callees

- `0x140003928`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000394d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000397e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000394d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000397e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000395b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000398c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000395b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000398c`

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
0x140003928  push    rbx
0x14000392a  push    rbp
0x14000392b  push    rsi
0x14000392c  push    rdi
0x14000392d  sub     rsp, 28h
0x140003931  movzx   eax, word ptr [rcx+20h]
0x140003935  mov     rsi, rcx
0x140003938  mov     rdi, [rcx+18h]
0x14000393c  lea     rbp, [rax+rax*4]
0x140003940  shl     rbp, 4
0x140003944  add     rbp, rdi
0x140003947  jmp     short loc_140003975
0x140003949  mov     rbx, [rdi+40h]
0x14000394d  call    cs:__imp_GetProcessHeap
0x140003953  mov     r8, rbx; lpMem
0x140003956  xor     edx, edx; dwFlags
0x140003958  mov     rcx, rax; hHeap
0x14000395b  call    cs:__imp_HeapFree
0x140003961  mov     qword ptr [rdi+40h], 0
0x140003969  mov     qword ptr [rdi+48h], 0
0x140003971  add     rdi, 50h ; 'P'
0x140003975  cmp     rdi, rbp
0x140003978  jnz     short loc_140003949
0x14000397a  mov     rbx, [rsi+18h]
0x14000397e  call    cs:__imp_GetProcessHeap
0x140003984  mov     r8, rbx; lpMem
0x140003987  xor     edx, edx; dwFlags
0x140003989  mov     rcx, rax; hHeap
0x14000398c  call    cs:__imp_HeapFree
0x140003992  xor     eax, eax
0x140003994  mov     [rsi+20h], eax
0x140003997  mov     [rsi+18h], rax
0x14000399b  add     rsp, 28h
0x14000399f  pop     rdi
0x1400039a0  pop     rsi
0x1400039a1  pop     rbp
0x1400039a2  pop     rbx
0x1400039a3  retn
```
