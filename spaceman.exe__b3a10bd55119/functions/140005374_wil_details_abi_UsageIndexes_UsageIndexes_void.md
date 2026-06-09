# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140005374`
- end: `0x140005401`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fe8`
- `0x140007d6c`
- `0x140008820`

## callees

- `0x140005374`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400053f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005398`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400053bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400053e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005398`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400053bd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400053e2`

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
0x140005374  mov     [rsp+arg_0], rbx
0x140005379  push    rdi
0x14000537a  sub     rsp, 20h
0x14000537e  mov     rdi, [rcx+0B0h]
0x140005385  mov     rbx, rcx
0x140005388  mov     qword ptr [rcx+0B0h], 0
0x140005393  test    rdi, rdi
0x140005396  jz      short loc_1400053AC
0x140005398  call    cs:__imp_GetProcessHeap
0x14000539e  mov     r8, rdi; lpMem
0x1400053a1  xor     edx, edx; dwFlags
0x1400053a3  mov     rcx, rax; hHeap
0x1400053a6  call    cs:__imp_HeapFree
0x1400053ac  mov     rdi, [rbx+70h]
0x1400053b0  mov     qword ptr [rbx+70h], 0
0x1400053b8  test    rdi, rdi
0x1400053bb  jz      short loc_1400053D1
0x1400053bd  call    cs:__imp_GetProcessHeap
0x1400053c3  mov     r8, rdi; lpMem
0x1400053c6  xor     edx, edx; dwFlags
0x1400053c8  mov     rcx, rax; hHeap
0x1400053cb  call    cs:__imp_HeapFree
0x1400053d1  mov     rdi, [rbx+30h]
0x1400053d5  mov     qword ptr [rbx+30h], 0
0x1400053dd  test    rdi, rdi
0x1400053e0  jz      short loc_1400053F6
0x1400053e2  call    cs:__imp_GetProcessHeap
0x1400053e8  mov     r8, rdi; lpMem
0x1400053eb  xor     edx, edx; dwFlags
0x1400053ed  mov     rcx, rax; hHeap
0x1400053f0  call    cs:__imp_HeapFree
0x1400053f6  mov     rbx, [rsp+28h+arg_0]
0x1400053fb  add     rsp, 20h
0x1400053ff  pop     rdi
0x140005400  retn
```
