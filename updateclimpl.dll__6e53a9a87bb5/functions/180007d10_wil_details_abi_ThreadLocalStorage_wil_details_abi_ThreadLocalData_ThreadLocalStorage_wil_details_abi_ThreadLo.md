# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180007d10`
- end: `0x180007d7f`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800079ec`

## callees

- `0x1800064d0`
- `0x180007d10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d45`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007d45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d53`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007d53`

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
0x180007d10  mov     [rsp+arg_0], rbx
0x180007d15  mov     [rsp+arg_8], rbp
0x180007d1a  mov     [rsp+arg_10], rsi
0x180007d1f  push    rdi
0x180007d20  sub     rsp, 20h
0x180007d24  lea     rbp, [rcx+50h]
0x180007d28  mov     rdi, rcx
0x180007d2b  cmp     rcx, rbp
0x180007d2e  jz      short loc_180007D6A
0x180007d30  mov     rsi, [rdi]
0x180007d33  jmp     short loc_180007D59
0x180007d35  mov     rbx, rsi
0x180007d38  mov     rsi, [rsi+8]
0x180007d3c  lea     rcx, [rbx+10h]; this
0x180007d40  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180007d45  call    cs:__imp_GetProcessHeap
0x180007d4b  mov     r8, rbx; lpMem
0x180007d4e  xor     edx, edx; dwFlags
0x180007d50  mov     rcx, rax; hHeap
0x180007d53  call    cs:__imp_HeapFree
0x180007d59  test    rsi, rsi
0x180007d5c  jnz     short loc_180007D35
0x180007d5e  mov     [rdi], rsi
0x180007d61  add     rdi, 8
0x180007d65  cmp     rdi, rbp
0x180007d68  jnz     short loc_180007D30
0x180007d6a  mov     rbx, [rsp+28h+arg_0]
0x180007d6f  mov     rbp, [rsp+28h+arg_8]
0x180007d74  mov     rsi, [rsp+28h+arg_10]
0x180007d79  add     rsp, 20h
0x180007d7d  pop     rdi
0x180007d7e  retn
```
