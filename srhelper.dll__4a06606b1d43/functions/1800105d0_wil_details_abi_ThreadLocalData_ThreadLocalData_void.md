# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800105d0`
- end: `0x18001064c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010144`

## callees

- `0x1800105d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010603`
- `KERNEL32!HeapFree` at `0x180010634`
- `KERNEL32!HeapFree` at `0x180010603`
- `KERNEL32!HeapFree` at `0x180010634`
- `KERNEL32!GetProcessHeap` at `0x1800105f5`
- `KERNEL32!GetProcessHeap` at `0x180010626`
- `KERNEL32!GetProcessHeap` at `0x1800105f5`
- `KERNEL32!GetProcessHeap` at `0x180010626`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800105d0  push    rbx
0x1800105d2  push    rbp
0x1800105d3  push    rsi
0x1800105d4  push    rdi
0x1800105d5  sub     rsp, 28h
0x1800105d9  movzx   eax, word ptr [rcx+20h]
0x1800105dd  mov     rsi, rcx
0x1800105e0  mov     rdi, [rcx+18h]
0x1800105e4  lea     rbp, [rax+rax*4]
0x1800105e8  shl     rbp, 4
0x1800105ec  add     rbp, rdi
0x1800105ef  jmp     short loc_18001061D
0x1800105f1  mov     rbx, [rdi+40h]
0x1800105f5  call    cs:__imp_GetProcessHeap
0x1800105fb  mov     r8, rbx; lpMem
0x1800105fe  xor     edx, edx; dwFlags
0x180010600  mov     rcx, rax; hHeap
0x180010603  call    cs:__imp_HeapFree
0x180010609  mov     qword ptr [rdi+40h], 0
0x180010611  mov     qword ptr [rdi+48h], 0
0x180010619  add     rdi, 50h ; 'P'
0x18001061d  cmp     rdi, rbp
0x180010620  jnz     short loc_1800105F1
0x180010622  mov     rbx, [rsi+18h]
0x180010626  call    cs:__imp_GetProcessHeap
0x18001062c  mov     r8, rbx; lpMem
0x18001062f  xor     edx, edx; dwFlags
0x180010631  mov     rcx, rax; hHeap
0x180010634  call    cs:__imp_HeapFree
0x18001063a  xor     eax, eax
0x18001063c  mov     [rsi+20h], eax
0x18001063f  mov     [rsi+18h], rax
0x180010643  add     rsp, 28h
0x180010647  pop     rdi
0x180010648  pop     rsi
0x180010649  pop     rbp
0x18001064a  pop     rbx
0x18001064b  retn
```
