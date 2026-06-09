# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x14000354c`
- end: `0x1400035c8`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003480`

## callees

- `0x14000354c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000357f`
- `KERNEL32!HeapFree` at `0x1400035b0`
- `KERNEL32!HeapFree` at `0x14000357f`
- `KERNEL32!HeapFree` at `0x1400035b0`
- `KERNEL32!GetProcessHeap` at `0x140003571`
- `KERNEL32!GetProcessHeap` at `0x1400035a2`
- `KERNEL32!GetProcessHeap` at `0x140003571`
- `KERNEL32!GetProcessHeap` at `0x1400035a2`

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
0x14000354c  push    rbx
0x14000354e  push    rbp
0x14000354f  push    rsi
0x140003550  push    rdi
0x140003551  sub     rsp, 28h
0x140003555  movzx   eax, word ptr [rcx+20h]
0x140003559  mov     rsi, rcx
0x14000355c  mov     rdi, [rcx+18h]
0x140003560  lea     rbp, [rax+rax*4]
0x140003564  shl     rbp, 4
0x140003568  add     rbp, rdi
0x14000356b  jmp     short loc_140003599
0x14000356d  mov     rbx, [rdi+40h]
0x140003571  call    cs:__imp_GetProcessHeap
0x140003577  mov     r8, rbx; lpMem
0x14000357a  xor     edx, edx; dwFlags
0x14000357c  mov     rcx, rax; hHeap
0x14000357f  call    cs:__imp_HeapFree
0x140003585  mov     qword ptr [rdi+40h], 0
0x14000358d  mov     qword ptr [rdi+48h], 0
0x140003595  add     rdi, 50h ; 'P'
0x140003599  cmp     rdi, rbp
0x14000359c  jnz     short loc_14000356D
0x14000359e  mov     rbx, [rsi+18h]
0x1400035a2  call    cs:__imp_GetProcessHeap
0x1400035a8  mov     r8, rbx; lpMem
0x1400035ab  xor     edx, edx; dwFlags
0x1400035ad  mov     rcx, rax; hHeap
0x1400035b0  call    cs:__imp_HeapFree
0x1400035b6  xor     eax, eax
0x1400035b8  mov     [rsi+20h], eax
0x1400035bb  mov     [rsi+18h], rax
0x1400035bf  add     rsp, 28h
0x1400035c3  pop     rdi
0x1400035c4  pop     rsi
0x1400035c5  pop     rbp
0x1400035c6  pop     rbx
0x1400035c7  retn
```
