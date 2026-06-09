# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180009664`
- end: `0x1800096e0`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009028`

## callees

- `0x180009664`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009689`
- `KERNEL32!GetProcessHeap` at `0x1800096ba`
- `KERNEL32!GetProcessHeap` at `0x180009689`
- `KERNEL32!GetProcessHeap` at `0x1800096ba`
- `KERNEL32!HeapFree` at `0x180009697`
- `KERNEL32!HeapFree` at `0x1800096c8`
- `KERNEL32!HeapFree` at `0x180009697`
- `KERNEL32!HeapFree` at `0x1800096c8`

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
0x180009664  push    rbx
0x180009666  push    rbp
0x180009667  push    rsi
0x180009668  push    rdi
0x180009669  sub     rsp, 28h
0x18000966d  movzx   eax, word ptr [rcx+20h]
0x180009671  mov     rsi, rcx
0x180009674  mov     rdi, [rcx+18h]
0x180009678  lea     rbp, [rax+rax*4]
0x18000967c  shl     rbp, 4
0x180009680  add     rbp, rdi
0x180009683  jmp     short loc_1800096B1
0x180009685  mov     rbx, [rdi+40h]
0x180009689  call    cs:__imp_GetProcessHeap
0x18000968f  mov     r8, rbx; lpMem
0x180009692  xor     edx, edx; dwFlags
0x180009694  mov     rcx, rax; hHeap
0x180009697  call    cs:__imp_HeapFree
0x18000969d  mov     qword ptr [rdi+40h], 0
0x1800096a5  mov     qword ptr [rdi+48h], 0
0x1800096ad  add     rdi, 50h ; 'P'
0x1800096b1  cmp     rdi, rbp
0x1800096b4  jnz     short loc_180009685
0x1800096b6  mov     rbx, [rsi+18h]
0x1800096ba  call    cs:__imp_GetProcessHeap
0x1800096c0  mov     r8, rbx; lpMem
0x1800096c3  xor     edx, edx; dwFlags
0x1800096c5  mov     rcx, rax; hHeap
0x1800096c8  call    cs:__imp_HeapFree
0x1800096ce  xor     eax, eax
0x1800096d0  mov     [rsi+20h], eax
0x1800096d3  mov     [rsi+18h], rax
0x1800096d7  add     rsp, 28h
0x1800096db  pop     rdi
0x1800096dc  pop     rsi
0x1800096dd  pop     rbp
0x1800096de  pop     rbx
0x1800096df  retn
```
