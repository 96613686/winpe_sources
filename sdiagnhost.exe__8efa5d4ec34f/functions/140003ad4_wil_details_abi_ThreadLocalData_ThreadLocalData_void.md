# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003ad4`
- end: `0x140003b50`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003928`

## callees

- `0x140003ad4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x140003af9`
- `KERNEL32!GetProcessHeap` at `0x140003b2a`
- `KERNEL32!GetProcessHeap` at `0x140003af9`
- `KERNEL32!GetProcessHeap` at `0x140003b2a`
- `KERNEL32!HeapFree` at `0x140003b07`
- `KERNEL32!HeapFree` at `0x140003b38`
- `KERNEL32!HeapFree` at `0x140003b07`
- `KERNEL32!HeapFree` at `0x140003b38`

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
0x140003ad4  push    rbx
0x140003ad6  push    rbp
0x140003ad7  push    rsi
0x140003ad8  push    rdi
0x140003ad9  sub     rsp, 28h
0x140003add  movzx   eax, word ptr [rcx+20h]
0x140003ae1  mov     rsi, rcx
0x140003ae4  mov     rdi, [rcx+18h]
0x140003ae8  lea     rbp, [rax+rax*4]
0x140003aec  shl     rbp, 4
0x140003af0  add     rbp, rdi
0x140003af3  jmp     short loc_140003B21
0x140003af5  mov     rbx, [rdi+40h]
0x140003af9  call    cs:__imp_GetProcessHeap
0x140003aff  mov     r8, rbx; lpMem
0x140003b02  xor     edx, edx; dwFlags
0x140003b04  mov     rcx, rax; hHeap
0x140003b07  call    cs:__imp_HeapFree
0x140003b0d  mov     qword ptr [rdi+40h], 0
0x140003b15  mov     qword ptr [rdi+48h], 0
0x140003b1d  add     rdi, 50h ; 'P'
0x140003b21  cmp     rdi, rbp
0x140003b24  jnz     short loc_140003AF5
0x140003b26  mov     rbx, [rsi+18h]
0x140003b2a  call    cs:__imp_GetProcessHeap
0x140003b30  mov     r8, rbx; lpMem
0x140003b33  xor     edx, edx; dwFlags
0x140003b35  mov     rcx, rax; hHeap
0x140003b38  call    cs:__imp_HeapFree
0x140003b3e  xor     eax, eax
0x140003b40  mov     [rsi+20h], eax
0x140003b43  mov     [rsi+18h], rax
0x140003b47  add     rsp, 28h
0x140003b4b  pop     rdi
0x140003b4c  pop     rsi
0x140003b4d  pop     rbp
0x140003b4e  pop     rbx
0x140003b4f  retn
```
