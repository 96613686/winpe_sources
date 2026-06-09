# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180009270`
- end: `0x1800092ec`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ae14`

## callees

- `0x180009270`
- `0x180009500`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800092b9`
- `KERNEL32!HeapFree` at `0x1800092b9`
- `KERNEL32!GetProcessHeap` at `0x1800092a5`
- `KERNEL32!GetProcessHeap` at `0x1800092a5`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rdi
  __int64 *v2; // rbp
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1;
  v2 = a1 + 10;
  do
  {
    v3 = *v1;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v1++ = 0;
  }
  while ( v1 != v2 );
}

```

## disassembly

```asm
0x180009270  mov     [rsp+arg_0], rbx
0x180009275  mov     [rsp+arg_8], rbp
0x18000927a  mov     [rsp+arg_10], rsi
0x18000927f  push    rdi
0x180009280  sub     rsp, 20h
0x180009284  mov     rdi, rcx
0x180009287  lea     rbp, [rcx+50h]
0x18000928b  cmp     rcx, rbp
0x18000928e  jz      short loc_1800092D6
0x180009290  mov     rsi, [rdi]
0x180009293  jmp     short loc_1800092C5
0x180009295  mov     rbx, rsi
0x180009298  mov     rsi, [rsi+8]
0x18000929c  lea     rcx, [rbx+10h]; this
0x1800092a0  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x1800092a5  call    cs:__imp_GetProcessHeap
0x1800092ac  nop     dword ptr [rax+rax+00h]
0x1800092b1  mov     rcx, rax; hHeap
0x1800092b4  mov     r8, rbx; lpMem
0x1800092b7  xor     edx, edx; dwFlags
0x1800092b9  call    cs:__imp_HeapFree
0x1800092c0  nop     dword ptr [rax+rax+00h]
0x1800092c5  test    rsi, rsi
0x1800092c8  jnz     short loc_180009295
0x1800092ca  mov     [rdi], rsi
0x1800092cd  add     rdi, 8
0x1800092d1  cmp     rdi, rbp
0x1800092d4  jnz     short loc_180009290
0x1800092d6  mov     rbx, [rsp+28h+arg_0]
0x1800092db  mov     rbp, [rsp+28h+arg_8]
0x1800092e0  mov     rsi, [rsp+28h+arg_10]
0x1800092e5  add     rsp, 20h
0x1800092e9  pop     rdi
0x1800092ea  retn
```
