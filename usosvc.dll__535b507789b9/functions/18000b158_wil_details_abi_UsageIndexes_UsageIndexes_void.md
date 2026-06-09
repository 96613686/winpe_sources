# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x18000b158`
- end: `0x18000b1e5`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae54`
- `0x18000c954`
- `0x18000d35c`
- `0x18000e89f`

## callees

- `0x18000b158`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b17c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b17c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b1c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b18a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b18a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b1d4`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax

  v1 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
  }
  v4 = (void *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
  }
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v6 )
  {
    v7 = GetProcessHeap();
    HeapFree(v7, 0, v6);
  }
}

```

## disassembly

```asm
0x18000b158  mov     [rsp+arg_0], rbx
0x18000b15d  push    rdi
0x18000b15e  sub     rsp, 20h
0x18000b162  mov     rdi, [rcx+0B0h]
0x18000b169  mov     rbx, rcx
0x18000b16c  mov     qword ptr [rcx+0B0h], 0
0x18000b177  test    rdi, rdi
0x18000b17a  jz      short loc_18000B190
0x18000b17c  call    cs:__imp_GetProcessHeap
0x18000b182  mov     r8, rdi; lpMem
0x18000b185  xor     edx, edx; dwFlags
0x18000b187  mov     rcx, rax; hHeap
0x18000b18a  call    cs:__imp_HeapFree
0x18000b190  mov     rdi, [rbx+70h]
0x18000b194  mov     qword ptr [rbx+70h], 0
0x18000b19c  test    rdi, rdi
0x18000b19f  jz      short loc_18000B1B5
0x18000b1a1  call    cs:__imp_GetProcessHeap
0x18000b1a7  mov     r8, rdi; lpMem
0x18000b1aa  xor     edx, edx; dwFlags
0x18000b1ac  mov     rcx, rax; hHeap
0x18000b1af  call    cs:__imp_HeapFree
0x18000b1b5  mov     rdi, [rbx+30h]
0x18000b1b9  mov     qword ptr [rbx+30h], 0
0x18000b1c1  test    rdi, rdi
0x18000b1c4  jz      short loc_18000B1DA
0x18000b1c6  call    cs:__imp_GetProcessHeap
0x18000b1cc  mov     r8, rdi; lpMem
0x18000b1cf  xor     edx, edx; dwFlags
0x18000b1d1  mov     rcx, rax; hHeap
0x18000b1d4  call    cs:__imp_HeapFree
0x18000b1da  mov     rbx, [rsp+28h+arg_0]
0x18000b1df  add     rsp, 20h
0x18000b1e3  pop     rdi
0x18000b1e4  retn
```
