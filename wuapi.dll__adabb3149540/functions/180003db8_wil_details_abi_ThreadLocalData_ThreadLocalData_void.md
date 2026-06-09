# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003db8`
- end: `0x180003e4a`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800054ac`

## callees

- `0x180003db8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e29`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003dfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e1b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003e1b`

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
0x180003db8  mov     [rsp+arg_8], rbx
0x180003dbd  mov     [rsp+arg_10], rbp
0x180003dc2  push    rsi
0x180003dc3  push    rdi
0x180003dc4  push    r14
0x180003dc6  sub     rsp, 20h
0x180003dca  mov     rdi, [rcx+18h]
0x180003dce  xor     r14d, r14d
0x180003dd1  movzx   eax, word ptr [rcx+20h]
0x180003dd5  mov     rsi, rcx
0x180003dd8  lea     rbp, [rax+rax*4]
0x180003ddc  shl     rbp, 4
0x180003de0  add     rbp, rdi
0x180003de3  cmp     rdi, rbp
0x180003de6  jz      short loc_180003E17
0x180003de8  add     rdi, 40h ; '@'
0x180003dec  mov     rbx, [rdi]
0x180003def  call    cs:__imp_GetProcessHeap
0x180003df5  mov     r8, rbx; lpMem
0x180003df8  xor     edx, edx; dwFlags
0x180003dfa  mov     rcx, rax; hHeap
0x180003dfd  call    cs:__imp_HeapFree
0x180003e03  mov     [rdi], r14
0x180003e06  mov     [rdi+8], r14
0x180003e0a  lea     rdi, [rdi+50h]
0x180003e0e  lea     rax, [rdi-40h]
0x180003e12  cmp     rax, rbp
0x180003e15  jnz     short loc_180003DEC
0x180003e17  mov     rbx, [rsi+18h]
0x180003e1b  call    cs:__imp_GetProcessHeap
0x180003e21  mov     r8, rbx; lpMem
0x180003e24  xor     edx, edx; dwFlags
0x180003e26  mov     rcx, rax; hHeap
0x180003e29  call    cs:__imp_HeapFree
0x180003e2f  mov     rbx, [rsp+38h+arg_8]
0x180003e34  mov     rbp, [rsp+38h+arg_10]
0x180003e39  mov     [rsi+20h], r14d
0x180003e3d  mov     [rsi+18h], r14
0x180003e41  add     rsp, 20h
0x180003e45  pop     r14
0x180003e47  pop     rdi
0x180003e48  pop     rsi
0x180003e49  retn
```
