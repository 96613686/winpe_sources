# CAdapter::~CAdapter(void)

- ea: `0x1800834c4`
- end: `0x180083552`
- name: `??1CAdapter@@QEAA@XZ`
- size: `142`
- prototype: `void __fastcall(CAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x18007ddc8`

## callees

- `0x1800834c4`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1800834d8`
- `KERNEL32!GetProcessHeap` at `0x180083504`
- `KERNEL32!GetProcessHeap` at `0x180083526`
- `KERNEL32!GetProcessHeap` at `0x1800834d8`
- `KERNEL32!GetProcessHeap` at `0x180083504`
- `KERNEL32!GetProcessHeap` at `0x180083526`
- `KERNEL32!HeapFree` at `0x180083512`
- `KERNEL32!HeapFree` at `0x180083534`
- `KERNEL32!HeapFree` at `0x180083512`
- `KERNEL32!HeapFree` at `0x180083534`
- `KERNEL32!HeapSize` at `0x1800834e6`
- `KERNEL32!HeapSize` at `0x1800834e6`
- `ole32!CoTaskMemFree` at `0x180083543`
- `ole32!CoTaskMemFree` at `0x180083543`

## pseudocode

```c
void __fastcall CAdapter::~CAdapter(CAdapter *this)
{
  const void *v1; // rdi
  HANDLE ProcessHeap; // rax
  unsigned int v4; // eax
  __int64 v5; // rdi
  unsigned int i; // esi
  void *v7; // rbp
  HANDLE v8; // rax
  void *v9; // rdi
  HANDLE v10; // rax
  void *v11; // rcx

  v1 = *(const void **)this;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    v4 = HeapSize(ProcessHeap, 0, v1);
    v5 = 0;
    for ( i = v4 >> 3; (unsigned int)v5 < i; v5 = (unsigned int)(v5 + 1) )
    {
      v7 = *(void **)(*(_QWORD *)this + 8 * v5);
      if ( v7 )
      {
        v8 = GetProcessHeap();
        HeapFree(v8, 0, v7);
      }
    }
  }
  v9 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
  }
  v11 = (void *)*((_QWORD *)this + 3);
  if ( v11 )
    CoTaskMemFree(v11);
}

```

## disassembly

```asm
0x1800834c4  push    rbx
0x1800834c6  push    rbp
0x1800834c7  push    rsi
0x1800834c8  push    rdi
0x1800834c9  sub     rsp, 28h
0x1800834cd  mov     rdi, [rcx]
0x1800834d0  mov     rbx, rcx
0x1800834d3  test    rdi, rdi
0x1800834d6  jz      short loc_18008351E
0x1800834d8  call    cs:__imp_GetProcessHeap
0x1800834de  mov     r8, rdi; lpMem
0x1800834e1  xor     edx, edx; dwFlags
0x1800834e3  mov     rcx, rax; hHeap
0x1800834e6  call    cs:__imp_HeapSize
0x1800834ec  mov     rsi, rax
0x1800834ef  xor     edi, edi
0x1800834f1  shr     esi, 3
0x1800834f4  test    esi, esi
0x1800834f6  jz      short loc_18008351E
0x1800834f8  mov     rcx, [rbx]
0x1800834fb  mov     rbp, [rcx+rdi*8]
0x1800834ff  test    rbp, rbp
0x180083502  jz      short loc_180083518
0x180083504  call    cs:__imp_GetProcessHeap
0x18008350a  mov     r8, rbp; lpMem
0x18008350d  xor     edx, edx; dwFlags
0x18008350f  mov     rcx, rax; hHeap
0x180083512  call    cs:__imp_HeapFree
0x180083518  inc     edi
0x18008351a  cmp     edi, esi
0x18008351c  jb      short loc_1800834F8
0x18008351e  mov     rdi, [rbx]
0x180083521  test    rdi, rdi
0x180083524  jz      short loc_18008353A
0x180083526  call    cs:__imp_GetProcessHeap
0x18008352c  mov     r8, rdi; lpMem
0x18008352f  xor     edx, edx; dwFlags
0x180083531  mov     rcx, rax; hHeap
0x180083534  call    cs:__imp_HeapFree
0x18008353a  mov     rcx, [rbx+18h]; pv
0x18008353e  test    rcx, rcx
0x180083541  jz      short loc_180083549
0x180083543  call    cs:__imp_CoTaskMemFree
0x180083549  add     rsp, 28h
0x18008354d  pop     rdi
0x18008354e  pop     rsi
0x18008354f  pop     rbp
0x180083550  pop     rbx
0x180083551  retn
```
