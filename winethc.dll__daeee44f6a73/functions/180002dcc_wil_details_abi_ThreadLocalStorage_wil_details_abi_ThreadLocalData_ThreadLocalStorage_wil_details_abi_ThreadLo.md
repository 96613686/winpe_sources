# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002dcc`
- end: `0x180002e31`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000c08c`

## callees

- `0x180002dcc`
- `0x180003250`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002df6`
- `KERNEL32!GetProcessHeap` at `0x180002df6`
- `KERNEL32!HeapFree` at `0x180002e0a`
- `KERNEL32!HeapFree` at `0x180002e0a`

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
0x180002dcc  push    rbx
0x180002dce  push    rbp
0x180002dcf  push    rsi
0x180002dd0  push    rdi
0x180002dd1  sub     rsp, 28h
0x180002dd5  lea     rbp, [rcx+50h]
0x180002dd9  mov     rdi, rcx
0x180002ddc  cmp     rcx, rbp
0x180002ddf  jz      short loc_180002E27
0x180002de1  mov     rsi, [rdi]
0x180002de4  jmp     short loc_180002E16
0x180002de6  mov     rbx, rsi
0x180002de9  mov     rsi, [rsi+8]
0x180002ded  lea     rcx, [rbx+10h]; this
0x180002df1  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180002df6  call    cs:__imp_GetProcessHeap
0x180002dfd  nop     dword ptr [rax+rax+00h]
0x180002e02  mov     r8, rbx; lpMem
0x180002e05  xor     edx, edx; dwFlags
0x180002e07  mov     rcx, rax; hHeap
0x180002e0a  call    cs:__imp_HeapFree
0x180002e11  nop     dword ptr [rax+rax+00h]
0x180002e16  test    rsi, rsi
0x180002e19  jnz     short loc_180002DE6
0x180002e1b  mov     [rdi], rsi
0x180002e1e  add     rdi, 8
0x180002e22  cmp     rdi, rbp
0x180002e25  jnz     short loc_180002DE1
0x180002e27  add     rsp, 28h
0x180002e2b  pop     rdi
0x180002e2c  pop     rsi
0x180002e2d  pop     rbp
0x180002e2e  pop     rbx
0x180002e2f  retn
```
