# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x140008b24`
- end: `0x140008bb1`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400087d4`
- `0x14000b2bc`
- `0x14000bd70`

## callees

- `0x140008b24`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140008b56`
- `KERNEL32!HeapFree` at `0x140008b7b`
- `KERNEL32!HeapFree` at `0x140008ba0`
- `KERNEL32!HeapFree` at `0x140008b56`
- `KERNEL32!HeapFree` at `0x140008b7b`
- `KERNEL32!HeapFree` at `0x140008ba0`
- `KERNEL32!GetProcessHeap` at `0x140008b48`
- `KERNEL32!GetProcessHeap` at `0x140008b6d`
- `KERNEL32!GetProcessHeap` at `0x140008b92`
- `KERNEL32!GetProcessHeap` at `0x140008b48`
- `KERNEL32!GetProcessHeap` at `0x140008b6d`
- `KERNEL32!GetProcessHeap` at `0x140008b92`

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
0x140008b24  mov     [rsp+arg_0], rbx
0x140008b29  push    rdi
0x140008b2a  sub     rsp, 20h
0x140008b2e  mov     rdi, [rcx+0B0h]
0x140008b35  mov     rbx, rcx
0x140008b38  mov     qword ptr [rcx+0B0h], 0
0x140008b43  test    rdi, rdi
0x140008b46  jz      short loc_140008B5C
0x140008b48  call    cs:__imp_GetProcessHeap
0x140008b4e  mov     r8, rdi; lpMem
0x140008b51  xor     edx, edx; dwFlags
0x140008b53  mov     rcx, rax; hHeap
0x140008b56  call    cs:__imp_HeapFree
0x140008b5c  mov     rdi, [rbx+70h]
0x140008b60  mov     qword ptr [rbx+70h], 0
0x140008b68  test    rdi, rdi
0x140008b6b  jz      short loc_140008B81
0x140008b6d  call    cs:__imp_GetProcessHeap
0x140008b73  mov     r8, rdi; lpMem
0x140008b76  xor     edx, edx; dwFlags
0x140008b78  mov     rcx, rax; hHeap
0x140008b7b  call    cs:__imp_HeapFree
0x140008b81  mov     rdi, [rbx+30h]
0x140008b85  mov     qword ptr [rbx+30h], 0
0x140008b8d  test    rdi, rdi
0x140008b90  jz      short loc_140008BA6
0x140008b92  call    cs:__imp_GetProcessHeap
0x140008b98  mov     r8, rdi; lpMem
0x140008b9b  xor     edx, edx; dwFlags
0x140008b9d  mov     rcx, rax; hHeap
0x140008ba0  call    cs:__imp_HeapFree
0x140008ba6  mov     rbx, [rsp+28h+arg_0]
0x140008bab  add     rsp, 20h
0x140008baf  pop     rdi
0x140008bb0  retn
```
