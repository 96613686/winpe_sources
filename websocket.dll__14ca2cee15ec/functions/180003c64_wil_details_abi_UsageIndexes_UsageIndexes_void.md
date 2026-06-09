# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003c64`
- end: `0x180003cf1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003914`
- `0x180006f20`
- `0x1800079d0`

## callees

- `0x180003c64`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ce0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003c96`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003cbb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003ce0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003c88`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cad`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003cd2`

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
0x180003c64  mov     [rsp+arg_0], rbx
0x180003c69  push    rdi
0x180003c6a  sub     rsp, 20h
0x180003c6e  mov     rdi, [rcx+0B0h]
0x180003c75  mov     rbx, rcx
0x180003c78  mov     qword ptr [rcx+0B0h], 0
0x180003c83  test    rdi, rdi
0x180003c86  jz      short loc_180003C9C
0x180003c88  call    cs:__imp_GetProcessHeap
0x180003c8e  mov     r8, rdi; lpMem
0x180003c91  xor     edx, edx; dwFlags
0x180003c93  mov     rcx, rax; hHeap
0x180003c96  call    cs:__imp_HeapFree
0x180003c9c  mov     rdi, [rbx+70h]
0x180003ca0  mov     qword ptr [rbx+70h], 0
0x180003ca8  test    rdi, rdi
0x180003cab  jz      short loc_180003CC1
0x180003cad  call    cs:__imp_GetProcessHeap
0x180003cb3  mov     r8, rdi; lpMem
0x180003cb6  xor     edx, edx; dwFlags
0x180003cb8  mov     rcx, rax; hHeap
0x180003cbb  call    cs:__imp_HeapFree
0x180003cc1  mov     rdi, [rbx+30h]
0x180003cc5  mov     qword ptr [rbx+30h], 0
0x180003ccd  test    rdi, rdi
0x180003cd0  jz      short loc_180003CE6
0x180003cd2  call    cs:__imp_GetProcessHeap
0x180003cd8  mov     r8, rdi; lpMem
0x180003cdb  xor     edx, edx; dwFlags
0x180003cdd  mov     rcx, rax; hHeap
0x180003ce0  call    cs:__imp_HeapFree
0x180003ce6  mov     rbx, [rsp+28h+arg_0]
0x180003ceb  add     rsp, 20h
0x180003cef  pop     rdi
0x180003cf0  retn
```
