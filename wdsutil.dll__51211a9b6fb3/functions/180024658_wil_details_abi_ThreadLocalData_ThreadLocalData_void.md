# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180024658`
- end: `0x1800246ed`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023f28`

## callees

- `0x180024658`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180024691`
- `KERNEL32!HeapFree` at `0x1800246ce`
- `KERNEL32!HeapFree` at `0x180024691`
- `KERNEL32!HeapFree` at `0x1800246ce`
- `KERNEL32!GetProcessHeap` at `0x18002467d`
- `KERNEL32!GetProcessHeap` at `0x1800246ba`
- `KERNEL32!GetProcessHeap` at `0x18002467d`
- `KERNEL32!GetProcessHeap` at `0x1800246ba`

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
0x180024658  push    rbx
0x18002465a  push    rbp
0x18002465b  push    rsi
0x18002465c  push    rdi
0x18002465d  sub     rsp, 28h
0x180024661  movzx   eax, word ptr [rcx+20h]
0x180024665  mov     rsi, rcx
0x180024668  mov     rdi, [rcx+18h]
0x18002466c  lea     rbp, [rax+rax*4]
0x180024670  shl     rbp, 4
0x180024674  add     rbp, rdi
0x180024677  jmp     short loc_1800246B1
0x180024679  mov     rbx, [rdi+40h]
0x18002467d  call    cs:__imp_GetProcessHeap
0x180024684  nop     dword ptr [rax+rax+00h]
0x180024689  mov     r8, rbx; lpMem
0x18002468c  xor     edx, edx; dwFlags
0x18002468e  mov     rcx, rax; hHeap
0x180024691  call    cs:__imp_HeapFree
0x180024698  nop     dword ptr [rax+rax+00h]
0x18002469d  mov     qword ptr [rdi+40h], 0
0x1800246a5  mov     qword ptr [rdi+48h], 0
0x1800246ad  add     rdi, 50h ; 'P'
0x1800246b1  cmp     rdi, rbp
0x1800246b4  jnz     short loc_180024679
0x1800246b6  mov     rbx, [rsi+18h]
0x1800246ba  call    cs:__imp_GetProcessHeap
0x1800246c1  nop     dword ptr [rax+rax+00h]
0x1800246c6  mov     r8, rbx; lpMem
0x1800246c9  xor     edx, edx; dwFlags
0x1800246cb  mov     rcx, rax; hHeap
0x1800246ce  call    cs:__imp_HeapFree
0x1800246d5  nop     dword ptr [rax+rax+00h]
0x1800246da  xor     eax, eax
0x1800246dc  mov     [rsi+20h], eax
0x1800246df  mov     [rsi+18h], rax
0x1800246e3  add     rsp, 28h
0x1800246e7  pop     rdi
0x1800246e8  pop     rsi
0x1800246e9  pop     rbp
0x1800246ea  pop     rbx
0x1800246eb  retn
```
