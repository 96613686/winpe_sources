# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180023f28`
- end: `0x180023f8d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800270a4`

## callees

- `0x180023f28`
- `0x180024658`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180023f66`
- `KERNEL32!HeapFree` at `0x180023f66`
- `KERNEL32!GetProcessHeap` at `0x180023f52`
- `KERNEL32!GetProcessHeap` at `0x180023f52`

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
0x180023f28  push    rbx
0x180023f2a  push    rbp
0x180023f2b  push    rsi
0x180023f2c  push    rdi
0x180023f2d  sub     rsp, 28h
0x180023f31  lea     rbp, [rcx+50h]
0x180023f35  mov     rdi, rcx
0x180023f38  cmp     rcx, rbp
0x180023f3b  jz      short loc_180023F83
0x180023f3d  mov     rsi, [rdi]
0x180023f40  jmp     short loc_180023F72
0x180023f42  mov     rbx, rsi
0x180023f45  mov     rsi, [rsi+8]
0x180023f49  lea     rcx, [rbx+10h]; this
0x180023f4d  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180023f52  call    cs:__imp_GetProcessHeap
0x180023f59  nop     dword ptr [rax+rax+00h]
0x180023f5e  mov     r8, rbx; lpMem
0x180023f61  xor     edx, edx; dwFlags
0x180023f63  mov     rcx, rax; hHeap
0x180023f66  call    cs:__imp_HeapFree
0x180023f6d  nop     dword ptr [rax+rax+00h]
0x180023f72  test    rsi, rsi
0x180023f75  jnz     short loc_180023F42
0x180023f77  mov     [rdi], rsi
0x180023f7a  add     rdi, 8
0x180023f7e  cmp     rdi, rbp
0x180023f81  jnz     short loc_180023F3D
0x180023f83  add     rsp, 28h
0x180023f87  pop     rdi
0x180023f88  pop     rsi
0x180023f89  pop     rbp
0x180023f8a  pop     rbx
0x180023f8b  retn
```
