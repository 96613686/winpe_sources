# FreeSstpCertNode

- ea: `0x1800031a0`
- end: `0x18000327a`
- name: `FreeSstpCertNode`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003150`

## callees

- `0x1800031a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000322e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003253`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800031e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003209`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000322e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003253`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000323c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003261`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800031f2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003217`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000323c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003261`

## pseudocode

```c
void __fastcall FreeSstpCertNode(_QWORD *a1)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rdi
  HANDLE v7; // rax
  void *v8; // rdi
  HANDLE v9; // rax
  void *v10; // rdi
  HANDLE v11; // rax

  if ( a1 )
  {
    v1 = (void *)a1[5];
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    v4 = (void *)a1[9];
    a1[5] = 0;
    if ( v4 )
    {
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
    }
    v6 = (void *)a1[7];
    a1[9] = 0;
    if ( v6 )
    {
      v7 = GetProcessHeap();
      HeapFree(v7, 0, v6);
    }
    v8 = (void *)a1[11];
    a1[7] = 0;
    if ( v8 )
    {
      v9 = GetProcessHeap();
      HeapFree(v9, 0, v8);
    }
    v10 = (void *)a1[3];
    a1[11] = 0;
    if ( v10 )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
    }
    a1[3] = 0;
  }
}

```

## disassembly

```asm
0x1800031a0  test    rcx, rcx
0x1800031a3  jz      locret_180003279
0x1800031a9  mov     [rsp+arg_0], rbx
0x1800031ae  push    rdi
0x1800031af  sub     rsp, 20h
0x1800031b3  mov     rdi, [rcx+28h]
0x1800031b7  mov     rbx, rcx
0x1800031ba  test    rdi, rdi
0x1800031bd  jz      short loc_1800031D3
0x1800031bf  call    cs:__imp_GetProcessHeap
0x1800031c5  mov     r8, rdi; lpMem
0x1800031c8  xor     edx, edx; dwFlags
0x1800031ca  mov     rcx, rax; hHeap
0x1800031cd  call    cs:__imp_HeapFree
0x1800031d3  mov     rdi, [rbx+48h]
0x1800031d7  mov     qword ptr [rbx+28h], 0
0x1800031df  test    rdi, rdi
0x1800031e2  jz      short loc_1800031F8
0x1800031e4  call    cs:__imp_GetProcessHeap
0x1800031ea  mov     r8, rdi; lpMem
0x1800031ed  xor     edx, edx; dwFlags
0x1800031ef  mov     rcx, rax; hHeap
0x1800031f2  call    cs:__imp_HeapFree
0x1800031f8  mov     rdi, [rbx+38h]
0x1800031fc  mov     qword ptr [rbx+48h], 0
0x180003204  test    rdi, rdi
0x180003207  jz      short loc_18000321D
0x180003209  call    cs:__imp_GetProcessHeap
0x18000320f  mov     r8, rdi; lpMem
0x180003212  xor     edx, edx; dwFlags
0x180003214  mov     rcx, rax; hHeap
0x180003217  call    cs:__imp_HeapFree
0x18000321d  mov     rdi, [rbx+58h]
0x180003221  mov     qword ptr [rbx+38h], 0
0x180003229  test    rdi, rdi
0x18000322c  jz      short loc_180003242
0x18000322e  call    cs:__imp_GetProcessHeap
0x180003234  mov     r8, rdi; lpMem
0x180003237  xor     edx, edx; dwFlags
0x180003239  mov     rcx, rax; hHeap
0x18000323c  call    cs:__imp_HeapFree
0x180003242  mov     rdi, [rbx+18h]
0x180003246  mov     qword ptr [rbx+58h], 0
0x18000324e  test    rdi, rdi
0x180003251  jz      short loc_180003267
0x180003253  call    cs:__imp_GetProcessHeap
0x180003259  mov     r8, rdi; lpMem
0x18000325c  xor     edx, edx; dwFlags
0x18000325e  mov     rcx, rax; hHeap
0x180003261  call    cs:__imp_HeapFree
0x180003267  mov     qword ptr [rbx+18h], 0
0x18000326f  mov     rbx, [rsp+28h+arg_0]
0x180003274  add     rsp, 20h
0x180003278  pop     rdi
0x180003279  retn
```
