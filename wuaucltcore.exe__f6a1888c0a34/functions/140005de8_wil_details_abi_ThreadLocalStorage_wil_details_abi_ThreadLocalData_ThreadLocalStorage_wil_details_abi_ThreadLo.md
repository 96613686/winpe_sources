# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140005de8`
- end: `0x140005e57`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005ad0`

## callees

- `0x1400044b8`
- `0x140005de8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140005e2b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005e1d`

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
0x140005de8  mov     [rsp+arg_0], rbx
0x140005ded  mov     [rsp+arg_8], rbp
0x140005df2  mov     [rsp+arg_10], rsi
0x140005df7  push    rdi
0x140005df8  sub     rsp, 20h
0x140005dfc  lea     rbp, [rcx+50h]
0x140005e00  mov     rdi, rcx
0x140005e03  cmp     rcx, rbp
0x140005e06  jz      short loc_140005E42
0x140005e08  mov     rsi, [rdi]
0x140005e0b  jmp     short loc_140005E31
0x140005e0d  mov     rbx, rsi
0x140005e10  mov     rsi, [rsi+8]
0x140005e14  lea     rcx, [rbx+10h]; this
0x140005e18  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x140005e1d  call    cs:__imp_GetProcessHeap
0x140005e23  mov     r8, rbx; lpMem
0x140005e26  xor     edx, edx; dwFlags
0x140005e28  mov     rcx, rax; hHeap
0x140005e2b  call    cs:__imp_HeapFree
0x140005e31  test    rsi, rsi
0x140005e34  jnz     short loc_140005E0D
0x140005e36  mov     [rdi], rsi
0x140005e39  add     rdi, 8
0x140005e3d  cmp     rdi, rbp
0x140005e40  jnz     short loc_140005E08
0x140005e42  mov     rbx, [rsp+28h+arg_0]
0x140005e47  mov     rbp, [rsp+28h+arg_8]
0x140005e4c  mov     rsi, [rsp+28h+arg_10]
0x140005e51  add     rsp, 20h
0x140005e55  pop     rdi
0x140005e56  retn
```
