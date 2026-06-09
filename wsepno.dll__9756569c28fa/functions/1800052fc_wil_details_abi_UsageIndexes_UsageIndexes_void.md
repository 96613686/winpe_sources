# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800052fc`
- end: `0x180005389`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f68`
- `0x1800093f0`
- `0x180009f00`
- `0x18000dda6`

## callees

- `0x1800052fc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000532e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005353`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000532e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005353`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005320`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000536a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005320`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005345`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000536a`

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
0x1800052fc  mov     [rsp+arg_0], rbx
0x180005301  push    rdi
0x180005302  sub     rsp, 20h
0x180005306  mov     rdi, [rcx+0B0h]
0x18000530d  mov     rbx, rcx
0x180005310  mov     qword ptr [rcx+0B0h], 0
0x18000531b  test    rdi, rdi
0x18000531e  jz      short loc_180005334
0x180005320  call    cs:__imp_GetProcessHeap
0x180005326  mov     r8, rdi; lpMem
0x180005329  xor     edx, edx; dwFlags
0x18000532b  mov     rcx, rax; hHeap
0x18000532e  call    cs:__imp_HeapFree
0x180005334  mov     rdi, [rbx+70h]
0x180005338  mov     qword ptr [rbx+70h], 0
0x180005340  test    rdi, rdi
0x180005343  jz      short loc_180005359
0x180005345  call    cs:__imp_GetProcessHeap
0x18000534b  mov     r8, rdi; lpMem
0x18000534e  xor     edx, edx; dwFlags
0x180005350  mov     rcx, rax; hHeap
0x180005353  call    cs:__imp_HeapFree
0x180005359  mov     rdi, [rbx+30h]
0x18000535d  mov     qword ptr [rbx+30h], 0
0x180005365  test    rdi, rdi
0x180005368  jz      short loc_18000537E
0x18000536a  call    cs:__imp_GetProcessHeap
0x180005370  mov     r8, rdi; lpMem
0x180005373  xor     edx, edx; dwFlags
0x180005375  mov     rcx, rax; hHeap
0x180005378  call    cs:__imp_HeapFree
0x18000537e  mov     rbx, [rsp+28h+arg_0]
0x180005383  add     rsp, 20h
0x180005387  pop     rdi
0x180005388  retn
```
