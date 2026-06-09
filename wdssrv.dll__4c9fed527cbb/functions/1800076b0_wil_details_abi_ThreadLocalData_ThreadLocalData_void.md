# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800076b0`
- end: `0x18000776a`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `186`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070c4`

## callees

- `0x1800076b0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800076ee`
- `KERNEL32!GetProcessHeap` at `0x180007726`
- `KERNEL32!GetProcessHeap` at `0x1800076ee`
- `KERNEL32!GetProcessHeap` at `0x180007726`
- `KERNEL32!HeapFree` at `0x180007702`
- `KERNEL32!HeapFree` at `0x18000773a`
- `KERNEL32!HeapFree` at `0x180007702`
- `KERNEL32!HeapFree` at `0x18000773a`

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
0x1800076b0  mov     rax, rsp
0x1800076b3  mov     [rax+8], rbx
0x1800076b7  mov     [rax+10h], rbp
0x1800076bb  mov     [rax+18h], rsi
0x1800076bf  mov     [rax+20h], rdi
0x1800076c3  push    r14
0x1800076c5  sub     rsp, 20h
0x1800076c9  mov     rdi, [rcx+18h]
0x1800076cd  xor     r14d, r14d
0x1800076d0  movzx   eax, word ptr [rcx+20h]
0x1800076d4  mov     rbp, rcx
0x1800076d7  lea     rsi, [rax+rax*4]
0x1800076db  shl     rsi, 4
0x1800076df  add     rsi, rdi
0x1800076e2  cmp     rdi, rsi
0x1800076e5  jz      short loc_180007722
0x1800076e7  add     rdi, 40h ; '@'
0x1800076eb  mov     rbx, [rdi]
0x1800076ee  call    cs:__imp_GetProcessHeap
0x1800076f5  nop     dword ptr [rax+rax+00h]
0x1800076fa  mov     r8, rbx; lpMem
0x1800076fd  xor     edx, edx; dwFlags
0x1800076ff  mov     rcx, rax; hHeap
0x180007702  call    cs:__imp_HeapFree
0x180007709  nop     dword ptr [rax+rax+00h]
0x18000770e  mov     [rdi], r14
0x180007711  mov     [rdi+8], r14
0x180007715  lea     rdi, [rdi+50h]
0x180007719  lea     rax, [rdi-40h]
0x18000771d  cmp     rax, rsi
0x180007720  jnz     short loc_1800076EB
0x180007722  mov     rbx, [rbp+18h]
0x180007726  call    cs:__imp_GetProcessHeap
0x18000772d  nop     dword ptr [rax+rax+00h]
0x180007732  mov     r8, rbx; lpMem
0x180007735  xor     edx, edx; dwFlags
0x180007737  mov     rcx, rax; hHeap
0x18000773a  call    cs:__imp_HeapFree
0x180007741  nop     dword ptr [rax+rax+00h]
0x180007746  mov     rbx, [rsp+28h+arg_0]
0x18000774b  mov     rsi, [rsp+28h+arg_10]
0x180007750  mov     rdi, [rsp+28h+arg_18]
0x180007755  mov     [rbp+20h], r14d
0x180007759  mov     [rbp+18h], r14
0x18000775d  mov     rbp, [rsp+28h+arg_8]
0x180007762  add     rsp, 20h
0x180007766  pop     r14
0x180007768  retn
```
