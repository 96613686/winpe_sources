# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180003528`
- end: `0x1800035a4`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009638`

## callees

- `0x180003528`
- `0x1800038d8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180003571`
- `KERNEL32!HeapFree` at `0x180003571`
- `KERNEL32!GetProcessHeap` at `0x18000355d`
- `KERNEL32!GetProcessHeap` at `0x18000355d`

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
0x180003528  mov     [rsp+arg_0], rbx
0x18000352d  mov     [rsp+arg_8], rbp
0x180003532  mov     [rsp+arg_10], rsi
0x180003537  push    rdi
0x180003538  sub     rsp, 20h
0x18000353c  lea     rbp, [rcx+50h]
0x180003540  mov     rdi, rcx
0x180003543  cmp     rcx, rbp
0x180003546  jz      short loc_18000358E
0x180003548  mov     rsi, [rdi]
0x18000354b  jmp     short loc_18000357D
0x18000354d  mov     rbx, rsi
0x180003550  mov     rsi, [rsi+8]
0x180003554  lea     rcx, [rbx+10h]; this
0x180003558  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000355d  call    cs:__imp_GetProcessHeap
0x180003564  nop     dword ptr [rax+rax+00h]
0x180003569  mov     r8, rbx; lpMem
0x18000356c  xor     edx, edx; dwFlags
0x18000356e  mov     rcx, rax; hHeap
0x180003571  call    cs:__imp_HeapFree
0x180003578  nop     dword ptr [rax+rax+00h]
0x18000357d  test    rsi, rsi
0x180003580  jnz     short loc_18000354D
0x180003582  mov     [rdi], rsi
0x180003585  add     rdi, 8
0x180003589  cmp     rdi, rbp
0x18000358c  jnz     short loc_180003548
0x18000358e  mov     rbx, [rsp+28h+arg_0]
0x180003593  mov     rbp, [rsp+28h+arg_8]
0x180003598  mov     rsi, [rsp+28h+arg_10]
0x18000359d  add     rsp, 20h
0x1800035a1  pop     rdi
0x1800035a2  retn
```
