# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000bdfc`
- end: `0x18000be61`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bd9c`

## callees

- `0x18000bdfc`
- `0x18000c724`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be3a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000be3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be26`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000be26`

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
0x18000bdfc  push    rbx
0x18000bdfe  push    rbp
0x18000bdff  push    rsi
0x18000be00  push    rdi
0x18000be01  sub     rsp, 28h
0x18000be05  lea     rbp, [rcx+50h]
0x18000be09  mov     rdi, rcx
0x18000be0c  cmp     rcx, rbp
0x18000be0f  jz      short loc_18000BE57
0x18000be11  mov     rsi, [rdi]
0x18000be14  jmp     short loc_18000BE46
0x18000be16  mov     rbx, rsi
0x18000be19  mov     rsi, [rsi+8]
0x18000be1d  lea     rcx, [rbx+10h]; this
0x18000be21  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x18000be26  call    cs:__imp_GetProcessHeap
0x18000be2d  nop     dword ptr [rax+rax+00h]
0x18000be32  mov     r8, rbx; lpMem
0x18000be35  xor     edx, edx; dwFlags
0x18000be37  mov     rcx, rax; hHeap
0x18000be3a  call    cs:__imp_HeapFree
0x18000be41  nop     dword ptr [rax+rax+00h]
0x18000be46  test    rsi, rsi
0x18000be49  jnz     short loc_18000BE16
0x18000be4b  mov     [rdi], rsi
0x18000be4e  add     rdi, 8
0x18000be52  cmp     rdi, rbp
0x18000be55  jnz     short loc_18000BE11
0x18000be57  add     rsp, 28h
0x18000be5b  pop     rdi
0x18000be5c  pop     rsi
0x18000be5d  pop     rbp
0x18000be5e  pop     rbx
0x18000be5f  retn
```
