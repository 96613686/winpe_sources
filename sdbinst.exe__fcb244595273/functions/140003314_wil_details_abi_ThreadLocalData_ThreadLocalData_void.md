# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003314`
- end: `0x140003390`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030ec`

## callees

- `0x140003314`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140003339`
- `KERNEL32!GetProcessHeap` at `0x14000336a`
- `KERNEL32!GetProcessHeap` at `0x140003339`
- `KERNEL32!GetProcessHeap` at `0x14000336a`
- `KERNEL32!HeapFree` at `0x140003347`
- `KERNEL32!HeapFree` at `0x140003378`
- `KERNEL32!HeapFree` at `0x140003347`
- `KERNEL32!HeapFree` at `0x140003378`

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
0x140003314  push    rbx
0x140003316  push    rbp
0x140003317  push    rsi
0x140003318  push    rdi
0x140003319  sub     rsp, 28h
0x14000331d  movzx   eax, word ptr [rcx+20h]
0x140003321  mov     rsi, rcx
0x140003324  mov     rdi, [rcx+18h]
0x140003328  lea     rbp, [rax+rax*4]
0x14000332c  shl     rbp, 4
0x140003330  add     rbp, rdi
0x140003333  jmp     short loc_140003361
0x140003335  mov     rbx, [rdi+40h]
0x140003339  call    cs:__imp_GetProcessHeap
0x14000333f  mov     r8, rbx; lpMem
0x140003342  xor     edx, edx; dwFlags
0x140003344  mov     rcx, rax; hHeap
0x140003347  call    cs:__imp_HeapFree
0x14000334d  mov     qword ptr [rdi+40h], 0
0x140003355  mov     qword ptr [rdi+48h], 0
0x14000335d  add     rdi, 50h ; 'P'
0x140003361  cmp     rdi, rbp
0x140003364  jnz     short loc_140003335
0x140003366  mov     rbx, [rsi+18h]
0x14000336a  call    cs:__imp_GetProcessHeap
0x140003370  mov     r8, rbx; lpMem
0x140003373  xor     edx, edx; dwFlags
0x140003375  mov     rcx, rax; hHeap
0x140003378  call    cs:__imp_HeapFree
0x14000337e  xor     eax, eax
0x140003380  mov     [rsi+20h], eax
0x140003383  mov     [rsi+18h], rax
0x140003387  add     rsp, 28h
0x14000338b  pop     rdi
0x14000338c  pop     rsi
0x14000338d  pop     rbp
0x14000338e  pop     rbx
0x14000338f  retn
```
