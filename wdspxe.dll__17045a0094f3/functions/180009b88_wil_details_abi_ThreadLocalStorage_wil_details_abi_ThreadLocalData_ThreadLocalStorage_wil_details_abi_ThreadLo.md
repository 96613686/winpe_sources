# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180009b88`
- end: `0x180009c04`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e64c`

## callees

- `0x180009b88`
- `0x180009fe4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009bbd`
- `KERNEL32!GetProcessHeap` at `0x180009bbd`
- `KERNEL32!HeapFree` at `0x180009bd1`
- `KERNEL32!HeapFree` at `0x180009bd1`

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
0x180009b88  mov     [rsp+arg_0], rbx
0x180009b8d  mov     [rsp+arg_8], rbp
0x180009b92  mov     [rsp+arg_10], rsi
0x180009b97  push    rdi
0x180009b98  sub     rsp, 20h
0x180009b9c  lea     rbp, [rcx+50h]
0x180009ba0  mov     rdi, rcx
0x180009ba3  cmp     rcx, rbp
0x180009ba6  jz      short loc_180009BEE
0x180009ba8  mov     rsi, [rdi]
0x180009bab  jmp     short loc_180009BDD
0x180009bad  mov     rbx, rsi
0x180009bb0  mov     rsi, [rsi+8]
0x180009bb4  lea     rcx, [rbx+10h]; this
0x180009bb8  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180009bbd  call    cs:__imp_GetProcessHeap
0x180009bc4  nop     dword ptr [rax+rax+00h]
0x180009bc9  mov     r8, rbx; lpMem
0x180009bcc  xor     edx, edx; dwFlags
0x180009bce  mov     rcx, rax; hHeap
0x180009bd1  call    cs:__imp_HeapFree
0x180009bd8  nop     dword ptr [rax+rax+00h]
0x180009bdd  test    rsi, rsi
0x180009be0  jnz     short loc_180009BAD
0x180009be2  mov     [rdi], rsi
0x180009be5  add     rdi, 8
0x180009be9  cmp     rdi, rbp
0x180009bec  jnz     short loc_180009BA8
0x180009bee  mov     rbx, [rsp+28h+arg_0]
0x180009bf3  mov     rbp, [rsp+28h+arg_8]
0x180009bf8  mov     rsi, [rsp+28h+arg_10]
0x180009bfd  add     rsp, 20h
0x180009c01  pop     rdi
0x180009c02  retn
```
