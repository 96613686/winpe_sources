# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003250`
- end: `0x1800032e5`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dcc`

## callees

- `0x180003250`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003275`
- `KERNEL32!GetProcessHeap` at `0x1800032b2`
- `KERNEL32!GetProcessHeap` at `0x180003275`
- `KERNEL32!GetProcessHeap` at `0x1800032b2`
- `KERNEL32!HeapFree` at `0x180003289`
- `KERNEL32!HeapFree` at `0x1800032c6`
- `KERNEL32!HeapFree` at `0x180003289`
- `KERNEL32!HeapFree` at `0x1800032c6`

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
0x180003250  push    rbx
0x180003252  push    rbp
0x180003253  push    rsi
0x180003254  push    rdi
0x180003255  sub     rsp, 28h
0x180003259  movzx   eax, word ptr [rcx+20h]
0x18000325d  mov     rsi, rcx
0x180003260  mov     rdi, [rcx+18h]
0x180003264  lea     rbp, [rax+rax*4]
0x180003268  shl     rbp, 4
0x18000326c  add     rbp, rdi
0x18000326f  jmp     short loc_1800032A9
0x180003271  mov     rbx, [rdi+40h]
0x180003275  call    cs:__imp_GetProcessHeap
0x18000327c  nop     dword ptr [rax+rax+00h]
0x180003281  mov     r8, rbx; lpMem
0x180003284  xor     edx, edx; dwFlags
0x180003286  mov     rcx, rax; hHeap
0x180003289  call    cs:__imp_HeapFree
0x180003290  nop     dword ptr [rax+rax+00h]
0x180003295  mov     qword ptr [rdi+40h], 0
0x18000329d  mov     qword ptr [rdi+48h], 0
0x1800032a5  add     rdi, 50h ; 'P'
0x1800032a9  cmp     rdi, rbp
0x1800032ac  jnz     short loc_180003271
0x1800032ae  mov     rbx, [rsi+18h]
0x1800032b2  call    cs:__imp_GetProcessHeap
0x1800032b9  nop     dword ptr [rax+rax+00h]
0x1800032be  mov     r8, rbx; lpMem
0x1800032c1  xor     edx, edx; dwFlags
0x1800032c3  mov     rcx, rax; hHeap
0x1800032c6  call    cs:__imp_HeapFree
0x1800032cd  nop     dword ptr [rax+rax+00h]
0x1800032d2  xor     eax, eax
0x1800032d4  mov     [rsi+20h], eax
0x1800032d7  mov     [rsi+18h], rax
0x1800032db  add     rsp, 28h
0x1800032df  pop     rdi
0x1800032e0  pop     rsi
0x1800032e1  pop     rbp
0x1800032e2  pop     rbx
0x1800032e3  retn
```
