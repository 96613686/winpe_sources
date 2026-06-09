# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180009fe4`
- end: `0x18000a09e`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b88`

## callees

- `0x180009fe4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a022`
- `KERNEL32!GetProcessHeap` at `0x18000a05a`
- `KERNEL32!GetProcessHeap` at `0x18000a022`
- `KERNEL32!GetProcessHeap` at `0x18000a05a`
- `KERNEL32!HeapFree` at `0x18000a036`
- `KERNEL32!HeapFree` at `0x18000a06e`
- `KERNEL32!HeapFree` at `0x18000a036`
- `KERNEL32!HeapFree` at `0x18000a06e`

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
0x180009fe4  mov     rax, rsp
0x180009fe7  mov     [rax+8], rbx
0x180009feb  mov     [rax+10h], rbp
0x180009fef  mov     [rax+18h], rsi
0x180009ff3  mov     [rax+20h], rdi
0x180009ff7  push    r14
0x180009ff9  sub     rsp, 20h
0x180009ffd  mov     rdi, [rcx+18h]
0x18000a001  xor     r14d, r14d
0x18000a004  movzx   eax, word ptr [rcx+20h]
0x18000a008  mov     rbp, rcx
0x18000a00b  lea     rsi, [rax+rax*4]
0x18000a00f  shl     rsi, 4
0x18000a013  add     rsi, rdi
0x18000a016  cmp     rdi, rsi
0x18000a019  jz      short loc_18000A056
0x18000a01b  add     rdi, 40h ; '@'
0x18000a01f  mov     rbx, [rdi]
0x18000a022  call    cs:__imp_GetProcessHeap
0x18000a029  nop     dword ptr [rax+rax+00h]
0x18000a02e  mov     r8, rbx; lpMem
0x18000a031  xor     edx, edx; dwFlags
0x18000a033  mov     rcx, rax; hHeap
0x18000a036  call    cs:__imp_HeapFree
0x18000a03d  nop     dword ptr [rax+rax+00h]
0x18000a042  mov     [rdi], r14
0x18000a045  mov     [rdi+8], r14
0x18000a049  lea     rdi, [rdi+50h]
0x18000a04d  lea     rax, [rdi-40h]
0x18000a051  cmp     rax, rsi
0x18000a054  jnz     short loc_18000A01F
0x18000a056  mov     rbx, [rbp+18h]
0x18000a05a  call    cs:__imp_GetProcessHeap
0x18000a061  nop     dword ptr [rax+rax+00h]
0x18000a066  mov     r8, rbx; lpMem
0x18000a069  xor     edx, edx; dwFlags
0x18000a06b  mov     rcx, rax; hHeap
0x18000a06e  call    cs:__imp_HeapFree
0x18000a075  nop     dword ptr [rax+rax+00h]
0x18000a07a  mov     rbx, [rsp+28h+arg_0]
0x18000a07f  mov     rsi, [rsp+28h+arg_10]
0x18000a084  mov     rdi, [rsp+28h+arg_18]
0x18000a089  mov     [rbp+20h], r14d
0x18000a08d  mov     [rbp+18h], r14
0x18000a091  mov     rbp, [rsp+28h+arg_8]
0x18000a096  add     rsp, 20h
0x18000a09a  pop     r14
0x18000a09c  retn
```
