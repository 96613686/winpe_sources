# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800186a0`
- end: `0x180018705`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800185dc`

## callees

- `0x1800186a0`
- `0x180018dec`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800186de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800186ca`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800186ca`

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
0x1800186a0  push    rbx
0x1800186a2  push    rbp
0x1800186a3  push    rsi
0x1800186a4  push    rdi
0x1800186a5  sub     rsp, 28h
0x1800186a9  lea     rbp, [rcx+50h]
0x1800186ad  mov     rdi, rcx
0x1800186b0  cmp     rcx, rbp
0x1800186b3  jz      short loc_1800186FB
0x1800186b5  mov     rsi, [rdi]
0x1800186b8  jmp     short loc_1800186EA
0x1800186ba  mov     rbx, rsi
0x1800186bd  mov     rsi, [rsi+8]
0x1800186c1  lea     rcx, [rbx+10h]; this
0x1800186c5  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x1800186ca  call    cs:__imp_GetProcessHeap
0x1800186d1  nop     dword ptr [rax+rax+00h]
0x1800186d6  mov     r8, rbx; lpMem
0x1800186d9  xor     edx, edx; dwFlags
0x1800186db  mov     rcx, rax; hHeap
0x1800186de  call    cs:__imp_HeapFree
0x1800186e5  nop     dword ptr [rax+rax+00h]
0x1800186ea  test    rsi, rsi
0x1800186ed  jnz     short loc_1800186BA
0x1800186ef  mov     [rdi], rsi
0x1800186f2  add     rdi, 8
0x1800186f6  cmp     rdi, rbp
0x1800186f9  jnz     short loc_1800186B5
0x1800186fb  add     rsp, 28h
0x1800186ff  pop     rdi
0x180018700  pop     rsi
0x180018701  pop     rbp
0x180018702  pop     rbx
0x180018703  retn
```
