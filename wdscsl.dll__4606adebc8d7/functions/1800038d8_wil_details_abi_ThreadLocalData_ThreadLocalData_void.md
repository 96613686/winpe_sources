# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800038d8`
- end: `0x180003992`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003528`

## callees

- `0x1800038d8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000392a`
- `KERNEL32!HeapFree` at `0x180003962`
- `KERNEL32!HeapFree` at `0x18000392a`
- `KERNEL32!HeapFree` at `0x180003962`
- `KERNEL32!GetProcessHeap` at `0x180003916`
- `KERNEL32!GetProcessHeap` at `0x18000394e`
- `KERNEL32!GetProcessHeap` at `0x180003916`
- `KERNEL32!GetProcessHeap` at `0x18000394e`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax

  v1 = *((_QWORD *)this + 3);
  v3 = v1 + 80LL * *((unsigned __int16 *)this + 16);
  if ( v1 != v3 )
  {
    v4 = v1 + 64;
    do
    {
      v5 = *(void **)v4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *(_QWORD *)v4 = 0;
      *(_QWORD *)(v4 + 8) = 0;
      v4 += 80;
    }
    while ( v4 - 64 != v3 );
  }
  v7 = (void *)*((_QWORD *)this + 3);
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v7);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800038d8  mov     rax, rsp
0x1800038db  mov     [rax+8], rbx
0x1800038df  mov     [rax+10h], rbp
0x1800038e3  mov     [rax+18h], rsi
0x1800038e7  mov     [rax+20h], rdi
0x1800038eb  push    r14
0x1800038ed  sub     rsp, 20h
0x1800038f1  mov     rdi, [rcx+18h]
0x1800038f5  xor     r14d, r14d
0x1800038f8  movzx   eax, word ptr [rcx+20h]
0x1800038fc  mov     rbp, rcx
0x1800038ff  lea     rsi, [rax+rax*4]
0x180003903  shl     rsi, 4
0x180003907  add     rsi, rdi
0x18000390a  cmp     rdi, rsi
0x18000390d  jz      short loc_18000394A
0x18000390f  add     rdi, 40h ; '@'
0x180003913  mov     rbx, [rdi]
0x180003916  call    cs:__imp_GetProcessHeap
0x18000391d  nop     dword ptr [rax+rax+00h]
0x180003922  mov     r8, rbx; lpMem
0x180003925  xor     edx, edx; dwFlags
0x180003927  mov     rcx, rax; hHeap
0x18000392a  call    cs:__imp_HeapFree
0x180003931  nop     dword ptr [rax+rax+00h]
0x180003936  mov     [rdi], r14
0x180003939  mov     [rdi+8], r14
0x18000393d  lea     rdi, [rdi+50h]
0x180003941  lea     rax, [rdi-40h]
0x180003945  cmp     rax, rsi
0x180003948  jnz     short loc_180003913
0x18000394a  mov     rbx, [rbp+18h]
0x18000394e  call    cs:__imp_GetProcessHeap
0x180003955  nop     dword ptr [rax+rax+00h]
0x18000395a  mov     r8, rbx; lpMem
0x18000395d  xor     edx, edx; dwFlags
0x18000395f  mov     rcx, rax; hHeap
0x180003962  call    cs:__imp_HeapFree
0x180003969  nop     dword ptr [rax+rax+00h]
0x18000396e  mov     rbx, [rsp+28h+arg_0]
0x180003973  mov     rsi, [rsp+28h+arg_10]
0x180003978  mov     rdi, [rsp+28h+arg_18]
0x18000397d  mov     [rbp+20h], r14d
0x180003981  mov     [rbp+18h], r14
0x180003985  mov     rbp, [rsp+28h+arg_8]
0x18000398a  add     rsp, 20h
0x18000398e  pop     r14
0x180003990  retn
```
