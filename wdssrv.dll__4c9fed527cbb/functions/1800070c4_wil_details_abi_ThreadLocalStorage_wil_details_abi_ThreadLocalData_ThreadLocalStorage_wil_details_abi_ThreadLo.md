# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800070c4`
- end: `0x180007140`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c490`

## callees

- `0x1800070c4`
- `0x1800076b0`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800070f9`
- `KERNEL32!GetProcessHeap` at `0x1800070f9`
- `KERNEL32!HeapFree` at `0x18000710d`
- `KERNEL32!HeapFree` at `0x18000710d`

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
0x1800070c4  mov     [rsp+arg_0], rbx
0x1800070c9  mov     [rsp+arg_8], rbp
0x1800070ce  mov     [rsp+arg_10], rsi
0x1800070d3  push    rdi
0x1800070d4  sub     rsp, 20h
0x1800070d8  lea     rbp, [rcx+50h]
0x1800070dc  mov     rdi, rcx
0x1800070df  cmp     rcx, rbp
0x1800070e2  jz      short loc_18000712A
0x1800070e4  mov     rsi, [rdi]
0x1800070e7  jmp     short loc_180007119
0x1800070e9  mov     rbx, rsi
0x1800070ec  mov     rsi, [rsi+8]
0x1800070f0  lea     rcx, [rbx+10h]; this
0x1800070f4  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x1800070f9  call    cs:__imp_GetProcessHeap
0x180007100  nop     dword ptr [rax+rax+00h]
0x180007105  mov     r8, rbx; lpMem
0x180007108  xor     edx, edx; dwFlags
0x18000710a  mov     rcx, rax; hHeap
0x18000710d  call    cs:__imp_HeapFree
0x180007114  nop     dword ptr [rax+rax+00h]
0x180007119  test    rsi, rsi
0x18000711c  jnz     short loc_1800070E9
0x18000711e  mov     [rdi], rsi
0x180007121  add     rdi, 8
0x180007125  cmp     rdi, rbp
0x180007128  jnz     short loc_1800070E4
0x18000712a  mov     rbx, [rsp+28h+arg_0]
0x18000712f  mov     rbp, [rsp+28h+arg_8]
0x180007134  mov     rsi, [rsp+28h+arg_10]
0x180007139  add     rsp, 20h
0x18000713d  pop     rdi
0x18000713e  retn
```
