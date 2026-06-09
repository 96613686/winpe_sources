# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180007584`
- end: `0x1800075e9`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007524`

## callees

- `0x180007584`
- `0x180007bb4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075c2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075ae`

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
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
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
0x180007584  push    rbx
0x180007586  push    rbp
0x180007587  push    rsi
0x180007588  push    rdi
0x180007589  sub     rsp, 28h
0x18000758d  lea     rbp, [rcx+50h]
0x180007591  mov     rdi, rcx
0x180007594  cmp     rcx, rbp
0x180007597  jz      short loc_1800075DF
0x180007599  mov     rsi, [rdi]
0x18000759c  jmp     short loc_1800075CE
0x18000759e  mov     rbx, rsi
0x1800075a1  mov     rsi, [rsi+8]
0x1800075a5  lea     rcx, [rbx+10h]; this
0x1800075a9  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x1800075ae  call    cs:__imp_GetProcessHeap
0x1800075b5  nop     dword ptr [rax+rax+00h]
0x1800075ba  mov     r8, rbx; lpMem
0x1800075bd  xor     edx, edx; dwFlags
0x1800075bf  mov     rcx, rax; hHeap
0x1800075c2  call    cs:__imp_HeapFree
0x1800075c9  nop     dword ptr [rax+rax+00h]
0x1800075ce  test    rsi, rsi
0x1800075d1  jnz     short loc_18000759E
0x1800075d3  mov     [rdi], rsi
0x1800075d6  add     rdi, 8
0x1800075da  cmp     rdi, rbp
0x1800075dd  jnz     short loc_180007599
0x1800075df  add     rsp, 28h
0x1800075e3  pop     rdi
0x1800075e4  pop     rsi
0x1800075e5  pop     rbp
0x1800075e6  pop     rbx
0x1800075e7  retn
```
