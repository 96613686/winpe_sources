# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180007658`
- end: `0x1800076bd`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075c4`

## callees

- `0x180007658`
- `0x1800079dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007682`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007682`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007696`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007696`

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
0x180007658  push    rbx
0x18000765a  push    rbp
0x18000765b  push    rsi
0x18000765c  push    rdi
0x18000765d  sub     rsp, 28h
0x180007661  lea     rbp, [rcx+50h]
0x180007665  mov     rdi, rcx
0x180007668  cmp     rcx, rbp
0x18000766b  jz      short loc_1800076B3
0x18000766d  mov     rsi, [rdi]
0x180007670  jmp     short loc_1800076A2
0x180007672  mov     rbx, rsi
0x180007675  mov     rsi, [rsi+8]
0x180007679  lea     rcx, [rbx+10h]; this
0x18000767d  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180007682  call    cs:__imp_GetProcessHeap
0x180007689  nop     dword ptr [rax+rax+00h]
0x18000768e  mov     r8, rbx; lpMem
0x180007691  xor     edx, edx; dwFlags
0x180007693  mov     rcx, rax; hHeap
0x180007696  call    cs:__imp_HeapFree
0x18000769d  nop     dword ptr [rax+rax+00h]
0x1800076a2  test    rsi, rsi
0x1800076a5  jnz     short loc_180007672
0x1800076a7  mov     [rdi], rsi
0x1800076aa  add     rdi, 8
0x1800076ae  cmp     rdi, rbp
0x1800076b1  jnz     short loc_18000766D
0x1800076b3  add     rsp, 28h
0x1800076b7  pop     rdi
0x1800076b8  pop     rsi
0x1800076b9  pop     rbp
0x1800076ba  pop     rbx
0x1800076bb  retn
```
