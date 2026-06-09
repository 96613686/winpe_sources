# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180009704`
- end: `0x180009791`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000934c`
- `0x18000ccc0`
- `0x18000d784`

## callees

- `0x180009704`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009736`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000975b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009780`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009736`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000975b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009780`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009728`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000974d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009772`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009728`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000974d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009772`

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
0x180009704  mov     [rsp+arg_0], rbx
0x180009709  push    rdi
0x18000970a  sub     rsp, 20h
0x18000970e  mov     rdi, [rcx+0B0h]
0x180009715  mov     rbx, rcx
0x180009718  mov     qword ptr [rcx+0B0h], 0
0x180009723  test    rdi, rdi
0x180009726  jz      short loc_18000973C
0x180009728  call    cs:__imp_GetProcessHeap
0x18000972e  mov     r8, rdi; lpMem
0x180009731  xor     edx, edx; dwFlags
0x180009733  mov     rcx, rax; hHeap
0x180009736  call    cs:__imp_HeapFree
0x18000973c  mov     rdi, [rbx+70h]
0x180009740  mov     qword ptr [rbx+70h], 0
0x180009748  test    rdi, rdi
0x18000974b  jz      short loc_180009761
0x18000974d  call    cs:__imp_GetProcessHeap
0x180009753  mov     r8, rdi; lpMem
0x180009756  xor     edx, edx; dwFlags
0x180009758  mov     rcx, rax; hHeap
0x18000975b  call    cs:__imp_HeapFree
0x180009761  mov     rdi, [rbx+30h]
0x180009765  mov     qword ptr [rbx+30h], 0
0x18000976d  test    rdi, rdi
0x180009770  jz      short loc_180009786
0x180009772  call    cs:__imp_GetProcessHeap
0x180009778  mov     r8, rdi; lpMem
0x18000977b  xor     edx, edx; dwFlags
0x18000977d  mov     rcx, rax; hHeap
0x180009780  call    cs:__imp_HeapFree
0x180009786  mov     rbx, [rsp+28h+arg_0]
0x18000978b  add     rsp, 20h
0x18000978f  pop     rdi
0x180009790  retn
```
