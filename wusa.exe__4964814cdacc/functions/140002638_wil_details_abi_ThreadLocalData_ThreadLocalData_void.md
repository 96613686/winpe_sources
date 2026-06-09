# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002638`
- end: `0x1400026b4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000256c`

## callees

- `0x140002638`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000266b`
- `KERNEL32!HeapFree` at `0x14000269c`
- `KERNEL32!HeapFree` at `0x14000266b`
- `KERNEL32!HeapFree` at `0x14000269c`
- `KERNEL32!GetProcessHeap` at `0x14000265d`
- `KERNEL32!GetProcessHeap` at `0x14000268e`
- `KERNEL32!GetProcessHeap` at `0x14000265d`
- `KERNEL32!GetProcessHeap` at `0x14000268e`

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
0x140002638  push    rbx
0x14000263a  push    rbp
0x14000263b  push    rsi
0x14000263c  push    rdi
0x14000263d  sub     rsp, 28h
0x140002641  movzx   eax, word ptr [rcx+20h]
0x140002645  mov     rsi, rcx
0x140002648  mov     rdi, [rcx+18h]
0x14000264c  lea     rbp, [rax+rax*4]
0x140002650  shl     rbp, 4
0x140002654  add     rbp, rdi
0x140002657  jmp     short loc_140002685
0x140002659  mov     rbx, [rdi+40h]
0x14000265d  call    cs:__imp_GetProcessHeap
0x140002663  mov     r8, rbx; lpMem
0x140002666  xor     edx, edx; dwFlags
0x140002668  mov     rcx, rax; hHeap
0x14000266b  call    cs:__imp_HeapFree
0x140002671  mov     qword ptr [rdi+40h], 0
0x140002679  mov     qword ptr [rdi+48h], 0
0x140002681  add     rdi, 50h ; 'P'
0x140002685  cmp     rdi, rbp
0x140002688  jnz     short loc_140002659
0x14000268a  mov     rbx, [rsi+18h]
0x14000268e  call    cs:__imp_GetProcessHeap
0x140002694  mov     r8, rbx; lpMem
0x140002697  xor     edx, edx; dwFlags
0x140002699  mov     rcx, rax; hHeap
0x14000269c  call    cs:__imp_HeapFree
0x1400026a2  xor     eax, eax
0x1400026a4  mov     [rsi+20h], eax
0x1400026a7  mov     [rsi+18h], rax
0x1400026ab  add     rsp, 28h
0x1400026af  pop     rdi
0x1400026b0  pop     rsi
0x1400026b1  pop     rbp
0x1400026b2  pop     rbx
0x1400026b3  retn
```
