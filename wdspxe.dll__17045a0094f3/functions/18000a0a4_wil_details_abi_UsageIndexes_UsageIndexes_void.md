# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x18000a0a4`
- end: `0x18000a14d`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009cb8`
- `0x18000d70c`
- `0x18000e7dc`

## callees

- `0x18000a0a4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000a0c5`
- `KERNEL32!GetProcessHeap` at `0x18000a0f3`
- `KERNEL32!GetProcessHeap` at `0x18000a121`
- `KERNEL32!GetProcessHeap` at `0x18000a0c5`
- `KERNEL32!GetProcessHeap` at `0x18000a0f3`
- `KERNEL32!GetProcessHeap` at `0x18000a121`
- `KERNEL32!HeapFree` at `0x18000a0d9`
- `KERNEL32!HeapFree` at `0x18000a107`
- `KERNEL32!HeapFree` at `0x18000a135`
- `KERNEL32!HeapFree` at `0x18000a0d9`
- `KERNEL32!HeapFree` at `0x18000a107`
- `KERNEL32!HeapFree` at `0x18000a135`

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
0x18000a0a4  mov     [rsp+arg_0], rbx
0x18000a0a9  push    rdi
0x18000a0aa  sub     rsp, 20h
0x18000a0ae  mov     rdi, [rcx+0B0h]
0x18000a0b5  mov     rbx, rcx
0x18000a0b8  and     qword ptr [rcx+0B0h], 0
0x18000a0c0  test    rdi, rdi
0x18000a0c3  jz      short loc_18000A0E5
0x18000a0c5  call    cs:__imp_GetProcessHeap
0x18000a0cc  nop     dword ptr [rax+rax+00h]
0x18000a0d1  mov     r8, rdi; lpMem
0x18000a0d4  xor     edx, edx; dwFlags
0x18000a0d6  mov     rcx, rax; hHeap
0x18000a0d9  call    cs:__imp_HeapFree
0x18000a0e0  nop     dword ptr [rax+rax+00h]
0x18000a0e5  mov     rdi, [rbx+70h]
0x18000a0e9  and     qword ptr [rbx+70h], 0
0x18000a0ee  test    rdi, rdi
0x18000a0f1  jz      short loc_18000A113
0x18000a0f3  call    cs:__imp_GetProcessHeap
0x18000a0fa  nop     dword ptr [rax+rax+00h]
0x18000a0ff  mov     r8, rdi; lpMem
0x18000a102  xor     edx, edx; dwFlags
0x18000a104  mov     rcx, rax; hHeap
0x18000a107  call    cs:__imp_HeapFree
0x18000a10e  nop     dword ptr [rax+rax+00h]
0x18000a113  mov     rdi, [rbx+30h]
0x18000a117  and     qword ptr [rbx+30h], 0
0x18000a11c  test    rdi, rdi
0x18000a11f  jz      short loc_18000A141
0x18000a121  call    cs:__imp_GetProcessHeap
0x18000a128  nop     dword ptr [rax+rax+00h]
0x18000a12d  mov     r8, rdi; lpMem
0x18000a130  xor     edx, edx; dwFlags
0x18000a132  mov     rcx, rax; hHeap
0x18000a135  call    cs:__imp_HeapFree
0x18000a13c  nop     dword ptr [rax+rax+00h]
0x18000a141  mov     rbx, [rsp+28h+arg_0]
0x18000a146  add     rsp, 20h
0x18000a14a  pop     rdi
0x18000a14b  retn
```
