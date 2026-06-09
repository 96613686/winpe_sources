# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800064d0`
- end: `0x180006562`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007d10`

## callees

- `0x1800064d0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006507`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006533`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006507`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006533`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006515`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006541`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006515`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006541`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
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
0x1800064d0  mov     [rsp+arg_8], rbx
0x1800064d5  mov     [rsp+arg_10], rbp
0x1800064da  push    rsi
0x1800064db  push    rdi
0x1800064dc  push    r14
0x1800064de  sub     rsp, 20h
0x1800064e2  mov     rdi, [rcx+18h]
0x1800064e6  xor     r14d, r14d
0x1800064e9  movzx   eax, word ptr [rcx+20h]
0x1800064ed  mov     rsi, rcx
0x1800064f0  lea     rbp, [rax+rax*4]
0x1800064f4  shl     rbp, 4
0x1800064f8  add     rbp, rdi
0x1800064fb  cmp     rdi, rbp
0x1800064fe  jz      short loc_18000652F
0x180006500  add     rdi, 40h ; '@'
0x180006504  mov     rbx, [rdi]
0x180006507  call    cs:__imp_GetProcessHeap
0x18000650d  mov     r8, rbx; lpMem
0x180006510  xor     edx, edx; dwFlags
0x180006512  mov     rcx, rax; hHeap
0x180006515  call    cs:__imp_HeapFree
0x18000651b  mov     [rdi], r14
0x18000651e  mov     [rdi+8], r14
0x180006522  lea     rdi, [rdi+50h]
0x180006526  lea     rax, [rdi-40h]
0x18000652a  cmp     rax, rbp
0x18000652d  jnz     short loc_180006504
0x18000652f  mov     rbx, [rsi+18h]
0x180006533  call    cs:__imp_GetProcessHeap
0x180006539  mov     r8, rbx; lpMem
0x18000653c  xor     edx, edx; dwFlags
0x18000653e  mov     rcx, rax; hHeap
0x180006541  call    cs:__imp_HeapFree
0x180006547  mov     rbx, [rsp+38h+arg_8]
0x18000654c  mov     rbp, [rsp+38h+arg_10]
0x180006551  mov     [rsi+20h], r14d
0x180006555  mov     [rsi+18h], r14
0x180006559  add     rsp, 20h
0x18000655d  pop     r14
0x18000655f  pop     rdi
0x180006560  pop     rsi
0x180006561  retn
```
