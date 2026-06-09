# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180009500`
- end: `0x1800095ba`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009270`

## callees

- `0x180009500`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180009552`
- `KERNEL32!HeapFree` at `0x18000958a`
- `KERNEL32!HeapFree` at `0x180009552`
- `KERNEL32!HeapFree` at `0x18000958a`
- `KERNEL32!GetProcessHeap` at `0x18000953e`
- `KERNEL32!GetProcessHeap` at `0x180009576`
- `KERNEL32!GetProcessHeap` at `0x18000953e`
- `KERNEL32!GetProcessHeap` at `0x180009576`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  if ( v2 != v3 )
  {
    v4 = v2 + 64;
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
0x180009500  mov     rax, rsp
0x180009503  mov     [rax+8], rbx
0x180009507  mov     [rax+10h], rbp
0x18000950b  mov     [rax+18h], rsi
0x18000950f  mov     [rax+20h], rdi
0x180009513  push    r14
0x180009515  sub     rsp, 20h
0x180009519  mov     rbp, rcx
0x18000951c  mov     rdi, [rcx+18h]
0x180009520  movzx   eax, word ptr [rcx+20h]
0x180009524  lea     rsi, [rax+rax*4]
0x180009528  shl     rsi, 4
0x18000952c  add     rsi, rdi
0x18000952f  xor     r14d, r14d
0x180009532  cmp     rdi, rsi
0x180009535  jz      short loc_180009572
0x180009537  add     rdi, 40h ; '@'
0x18000953b  mov     rbx, [rdi]
0x18000953e  call    cs:__imp_GetProcessHeap
0x180009545  nop     dword ptr [rax+rax+00h]
0x18000954a  mov     r8, rbx; lpMem
0x18000954d  xor     edx, edx; dwFlags
0x18000954f  mov     rcx, rax; hHeap
0x180009552  call    cs:__imp_HeapFree
0x180009559  nop     dword ptr [rax+rax+00h]
0x18000955e  mov     [rdi], r14
0x180009561  mov     [rdi+8], r14
0x180009565  lea     rdi, [rdi+50h]
0x180009569  lea     rax, [rdi-40h]
0x18000956d  cmp     rax, rsi
0x180009570  jnz     short loc_18000953B
0x180009572  mov     rbx, [rbp+18h]
0x180009576  call    cs:__imp_GetProcessHeap
0x18000957d  nop     dword ptr [rax+rax+00h]
0x180009582  mov     r8, rbx; lpMem
0x180009585  xor     edx, edx; dwFlags
0x180009587  mov     rcx, rax; hHeap
0x18000958a  call    cs:__imp_HeapFree
0x180009591  nop     dword ptr [rax+rax+00h]
0x180009596  mov     [rbp+20h], r14d
0x18000959a  mov     [rbp+18h], r14
0x18000959e  mov     rbx, [rsp+28h+arg_0]
0x1800095a3  mov     rbp, [rsp+28h+arg_8]
0x1800095a8  mov     rsi, [rsp+28h+arg_10]
0x1800095ad  mov     rdi, [rsp+28h+arg_18]
0x1800095b2  add     rsp, 20h
0x1800095b6  pop     r14
0x1800095b8  retn
```
