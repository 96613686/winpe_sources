# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800054ac`
- end: `0x18000551b`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005194`

## callees

- `0x180003db8`
- `0x1800054ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054ef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800054ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054e1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800054e1`

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
0x1800054ac  mov     [rsp+arg_0], rbx
0x1800054b1  mov     [rsp+arg_8], rbp
0x1800054b6  mov     [rsp+arg_10], rsi
0x1800054bb  push    rdi
0x1800054bc  sub     rsp, 20h
0x1800054c0  lea     rbp, [rcx+50h]
0x1800054c4  mov     rdi, rcx
0x1800054c7  cmp     rcx, rbp
0x1800054ca  jz      short loc_180005506
0x1800054cc  mov     rsi, [rdi]
0x1800054cf  jmp     short loc_1800054F5
0x1800054d1  mov     rbx, rsi
0x1800054d4  mov     rsi, [rsi+8]
0x1800054d8  lea     rcx, [rbx+10h]; this
0x1800054dc  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x1800054e1  call    cs:__imp_GetProcessHeap
0x1800054e7  mov     r8, rbx; lpMem
0x1800054ea  xor     edx, edx; dwFlags
0x1800054ec  mov     rcx, rax; hHeap
0x1800054ef  call    cs:__imp_HeapFree
0x1800054f5  test    rsi, rsi
0x1800054f8  jnz     short loc_1800054D1
0x1800054fa  mov     [rdi], rsi
0x1800054fd  add     rdi, 8
0x180005501  cmp     rdi, rbp
0x180005504  jnz     short loc_1800054CC
0x180005506  mov     rbx, [rsp+28h+arg_0]
0x18000550b  mov     rbp, [rsp+28h+arg_8]
0x180005510  mov     rsi, [rsp+28h+arg_10]
0x180005515  add     rsp, 20h
0x180005519  pop     rdi
0x18000551a  retn
```
