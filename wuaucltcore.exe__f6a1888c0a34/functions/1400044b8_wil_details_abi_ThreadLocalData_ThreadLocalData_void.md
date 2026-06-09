# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1400044b8`
- end: `0x14000454a`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005de8`

## callees

- `0x1400044b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400044fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004529`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400044fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004529`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400044ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000451b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400044ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000451b`

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
0x1400044b8  mov     [rsp+arg_8], rbx
0x1400044bd  mov     [rsp+arg_10], rbp
0x1400044c2  push    rsi
0x1400044c3  push    rdi
0x1400044c4  push    r14
0x1400044c6  sub     rsp, 20h
0x1400044ca  mov     rdi, [rcx+18h]
0x1400044ce  xor     r14d, r14d
0x1400044d1  movzx   eax, word ptr [rcx+20h]
0x1400044d5  mov     rsi, rcx
0x1400044d8  lea     rbp, [rax+rax*4]
0x1400044dc  shl     rbp, 4
0x1400044e0  add     rbp, rdi
0x1400044e3  cmp     rdi, rbp
0x1400044e6  jz      short loc_140004517
0x1400044e8  add     rdi, 40h ; '@'
0x1400044ec  mov     rbx, [rdi]
0x1400044ef  call    cs:__imp_GetProcessHeap
0x1400044f5  mov     r8, rbx; lpMem
0x1400044f8  xor     edx, edx; dwFlags
0x1400044fa  mov     rcx, rax; hHeap
0x1400044fd  call    cs:__imp_HeapFree
0x140004503  mov     [rdi], r14
0x140004506  mov     [rdi+8], r14
0x14000450a  lea     rdi, [rdi+50h]
0x14000450e  lea     rax, [rdi-40h]
0x140004512  cmp     rax, rbp
0x140004515  jnz     short loc_1400044EC
0x140004517  mov     rbx, [rsi+18h]
0x14000451b  call    cs:__imp_GetProcessHeap
0x140004521  mov     r8, rbx; lpMem
0x140004524  xor     edx, edx; dwFlags
0x140004526  mov     rcx, rax; hHeap
0x140004529  call    cs:__imp_HeapFree
0x14000452f  mov     rbx, [rsp+38h+arg_8]
0x140004534  mov     rbp, [rsp+38h+arg_10]
0x140004539  mov     [rsi+20h], r14d
0x14000453d  mov     [rsi+18h], r14
0x140004541  add     rsp, 20h
0x140004545  pop     r14
0x140004547  pop     rdi
0x140004548  pop     rsi
0x140004549  retn
```
