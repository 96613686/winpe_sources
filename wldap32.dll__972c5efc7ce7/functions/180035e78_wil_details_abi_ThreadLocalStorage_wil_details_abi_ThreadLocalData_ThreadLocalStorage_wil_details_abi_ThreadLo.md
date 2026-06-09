# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180035e78`
- end: `0x180035edd`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180035e18`

## callees

- `0x180035e78`
- `0x18003641c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035ea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180035ea2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035eb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180035eb6`

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
0x180035e78  push    rbx
0x180035e7a  push    rbp
0x180035e7b  push    rsi
0x180035e7c  push    rdi
0x180035e7d  sub     rsp, 28h
0x180035e81  lea     rbp, [rcx+50h]
0x180035e85  mov     rdi, rcx
0x180035e88  cmp     rcx, rbp
0x180035e8b  jz      short loc_180035ED3
0x180035e8d  mov     rsi, [rdi]
0x180035e90  jmp     short loc_180035EC2
0x180035e92  mov     rbx, rsi
0x180035e95  mov     rsi, [rsi+8]
0x180035e99  lea     rcx, [rbx+10h]; this
0x180035e9d  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180035ea2  call    cs:__imp_GetProcessHeap
0x180035ea9  nop     dword ptr [rax+rax+00h]
0x180035eae  mov     r8, rbx; lpMem
0x180035eb1  xor     edx, edx; dwFlags
0x180035eb3  mov     rcx, rax; hHeap
0x180035eb6  call    cs:__imp_HeapFree
0x180035ebd  nop     dword ptr [rax+rax+00h]
0x180035ec2  test    rsi, rsi
0x180035ec5  jnz     short loc_180035E92
0x180035ec7  mov     [rdi], rsi
0x180035eca  add     rdi, 8
0x180035ece  cmp     rdi, rbp
0x180035ed1  jnz     short loc_180035E8D
0x180035ed3  add     rsp, 28h
0x180035ed7  pop     rdi
0x180035ed8  pop     rsi
0x180035ed9  pop     rbp
0x180035eda  pop     rbx
0x180035edb  retn
```
