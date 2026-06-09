# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000a0d8`
- end: `0x18000a147`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009dc0`

## callees

- `0x180009428`
- `0x18000a0d8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a10d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a10d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a11b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a11b`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x18000a0d8  mov     [rsp+arg_0], rbx
0x18000a0dd  mov     [rsp+arg_8], rbp
0x18000a0e2  mov     [rsp+arg_10], rsi
0x18000a0e7  push    rdi
0x18000a0e8  sub     rsp, 20h
0x18000a0ec  lea     rbp, [rcx+50h]
0x18000a0f0  mov     rdi, rcx
0x18000a0f3  cmp     rcx, rbp
0x18000a0f6  jz      short loc_18000A132
0x18000a0f8  mov     rsi, [rdi]
0x18000a0fb  jmp     short loc_18000A121
0x18000a0fd  mov     rbx, rsi
0x18000a100  mov     rsi, [rsi+8]
0x18000a104  lea     rcx, [rbx+10h]; this
0x18000a108  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000a10d  call    cs:__imp_GetProcessHeap
0x18000a113  mov     r8, rbx; lpMem
0x18000a116  xor     edx, edx; dwFlags
0x18000a118  mov     rcx, rax; hHeap
0x18000a11b  call    cs:__imp_HeapFree
0x18000a121  test    rsi, rsi
0x18000a124  jnz     short loc_18000A0FD
0x18000a126  mov     [rdi], rsi
0x18000a129  add     rdi, 8
0x18000a12d  cmp     rdi, rbp
0x18000a130  jnz     short loc_18000A0F8
0x18000a132  mov     rbx, [rsp+28h+arg_0]
0x18000a137  mov     rbp, [rsp+28h+arg_8]
0x18000a13c  mov     rsi, [rsp+28h+arg_10]
0x18000a141  add     rsp, 20h
0x18000a145  pop     rdi
0x18000a146  retn
```
