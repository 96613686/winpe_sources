# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180003998`
- end: `0x180003a41`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `169`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035ac`
- `0x180008c2c`
- `0x1800097c8`

## callees

- `0x180003998`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800039cd`
- `KERNEL32!HeapFree` at `0x1800039fb`
- `KERNEL32!HeapFree` at `0x180003a29`
- `KERNEL32!HeapFree` at `0x1800039cd`
- `KERNEL32!HeapFree` at `0x1800039fb`
- `KERNEL32!HeapFree` at `0x180003a29`
- `KERNEL32!GetProcessHeap` at `0x1800039b9`
- `KERNEL32!GetProcessHeap` at `0x1800039e7`
- `KERNEL32!GetProcessHeap` at `0x180003a15`
- `KERNEL32!GetProcessHeap` at `0x1800039b9`
- `KERNEL32!GetProcessHeap` at `0x1800039e7`
- `KERNEL32!GetProcessHeap` at `0x180003a15`

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
0x180003998  mov     [rsp+arg_0], rbx
0x18000399d  push    rdi
0x18000399e  sub     rsp, 20h
0x1800039a2  mov     rdi, [rcx+0B0h]
0x1800039a9  mov     rbx, rcx
0x1800039ac  and     qword ptr [rcx+0B0h], 0
0x1800039b4  test    rdi, rdi
0x1800039b7  jz      short loc_1800039D9
0x1800039b9  call    cs:__imp_GetProcessHeap
0x1800039c0  nop     dword ptr [rax+rax+00h]
0x1800039c5  mov     r8, rdi; lpMem
0x1800039c8  xor     edx, edx; dwFlags
0x1800039ca  mov     rcx, rax; hHeap
0x1800039cd  call    cs:__imp_HeapFree
0x1800039d4  nop     dword ptr [rax+rax+00h]
0x1800039d9  mov     rdi, [rbx+70h]
0x1800039dd  and     qword ptr [rbx+70h], 0
0x1800039e2  test    rdi, rdi
0x1800039e5  jz      short loc_180003A07
0x1800039e7  call    cs:__imp_GetProcessHeap
0x1800039ee  nop     dword ptr [rax+rax+00h]
0x1800039f3  mov     r8, rdi; lpMem
0x1800039f6  xor     edx, edx; dwFlags
0x1800039f8  mov     rcx, rax; hHeap
0x1800039fb  call    cs:__imp_HeapFree
0x180003a02  nop     dword ptr [rax+rax+00h]
0x180003a07  mov     rdi, [rbx+30h]
0x180003a0b  and     qword ptr [rbx+30h], 0
0x180003a10  test    rdi, rdi
0x180003a13  jz      short loc_180003A35
0x180003a15  call    cs:__imp_GetProcessHeap
0x180003a1c  nop     dword ptr [rax+rax+00h]
0x180003a21  mov     r8, rdi; lpMem
0x180003a24  xor     edx, edx; dwFlags
0x180003a26  mov     rcx, rax; hHeap
0x180003a29  call    cs:__imp_HeapFree
0x180003a30  nop     dword ptr [rax+rax+00h]
0x180003a35  mov     rbx, [rsp+28h+arg_0]
0x180003a3a  add     rsp, 20h
0x180003a3e  pop     rdi
0x180003a3f  retn
```
