# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003be0`
- end: `0x180003c5c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003608`

## callees

- `0x180003be0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c13`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c44`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c36`

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
0x180003be0  push    rbx
0x180003be2  push    rbp
0x180003be3  push    rsi
0x180003be4  push    rdi
0x180003be5  sub     rsp, 28h
0x180003be9  movzx   eax, word ptr [rcx+20h]
0x180003bed  mov     rsi, rcx
0x180003bf0  mov     rdi, [rcx+18h]
0x180003bf4  lea     rbp, [rax+rax*4]
0x180003bf8  shl     rbp, 4
0x180003bfc  add     rbp, rdi
0x180003bff  jmp     short loc_180003C2D
0x180003c01  mov     rbx, [rdi+40h]
0x180003c05  call    cs:__imp_GetProcessHeap
0x180003c0b  mov     r8, rbx; lpMem
0x180003c0e  xor     edx, edx; dwFlags
0x180003c10  mov     rcx, rax; hHeap
0x180003c13  call    cs:__imp_HeapFree
0x180003c19  mov     qword ptr [rdi+40h], 0
0x180003c21  mov     qword ptr [rdi+48h], 0
0x180003c29  add     rdi, 50h ; 'P'
0x180003c2d  cmp     rdi, rbp
0x180003c30  jnz     short loc_180003C01
0x180003c32  mov     rbx, [rsi+18h]
0x180003c36  call    cs:__imp_GetProcessHeap
0x180003c3c  mov     r8, rbx; lpMem
0x180003c3f  xor     edx, edx; dwFlags
0x180003c41  mov     rcx, rax; hHeap
0x180003c44  call    cs:__imp_HeapFree
0x180003c4a  xor     eax, eax
0x180003c4c  mov     [rsi+20h], eax
0x180003c4f  mov     [rsi+18h], rax
0x180003c53  add     rsp, 28h
0x180003c57  pop     rdi
0x180003c58  pop     rsi
0x180003c59  pop     rbp
0x180003c5a  pop     rbx
0x180003c5b  retn
```
