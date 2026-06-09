# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000a5c0`
- end: `0x14000a682`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140008574`
- `0x1400097cc`
- `0x14000a168`

## callees

- `0x14000a5c0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a627`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a651`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a627`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a643`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a619`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000a643`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::Swap(
        wil::details_abi::RawUsageIndex *this,
        struct wil::details_abi::RawUsageIndex *a2)
{
  __int64 v2; // rbp
  __int128 v5; // xmm6
  __int64 v6; // xmm7_8
  __int64 v7; // rax
  void *v8; // rsi
  HANDLE ProcessHeap; // rax
  void *v10; // rsi
  HANDLE v11; // rax
  char v12; // cl
  char v13; // al
  char v14; // cl

  v2 = *((_QWORD *)this + 6);
  v5 = *(_OWORD *)((char *)this + 24);
  v6 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  v7 = *((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = 0;
  v8 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v7;
  if ( v8 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v8);
  }
  *(_OWORD *)((char *)a2 + 24) = v5;
  *((_QWORD *)a2 + 5) = v6;
  v10 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v2;
  if ( v10 )
  {
    v11 = GetProcessHeap();
    HeapFree(v11, 0, v10);
  }
  v12 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  v13 = *((_BYTE *)a2 + 57);
  *((_BYTE *)a2 + 56) = v12;
  v14 = *((_BYTE *)this + 57);
  *((_BYTE *)this + 57) = v13;
  *((_BYTE *)a2 + 57) = v14;
}

```

## disassembly

```asm
0x14000a5c0  push    rbx
0x14000a5c2  push    rbp
0x14000a5c3  push    rsi
0x14000a5c4  push    rdi
0x14000a5c5  sub     rsp, 48h
0x14000a5c9  mov     rbp, [rcx+30h]
0x14000a5cd  mov     rbx, rdx
0x14000a5d0  movaps  [rsp+68h+var_38], xmm6
0x14000a5d5  mov     rdi, rcx
0x14000a5d8  movups  xmm6, xmmword ptr [rcx+18h]
0x14000a5dc  movaps  [rsp+68h+var_48], xmm7
0x14000a5e1  movsd   xmm7, qword ptr [rcx+28h]
0x14000a5e6  mov     qword ptr [rcx+30h], 0
0x14000a5ee  movups  xmm0, xmmword ptr [rdx+18h]
0x14000a5f2  movups  xmmword ptr [rcx+18h], xmm0
0x14000a5f6  movsd   xmm1, qword ptr [rdx+28h]
0x14000a5fb  movsd   qword ptr [rcx+28h], xmm1
0x14000a600  mov     rax, [rdx+30h]
0x14000a604  mov     qword ptr [rdx+30h], 0
0x14000a60c  mov     rsi, [rcx+30h]
0x14000a610  mov     [rcx+30h], rax
0x14000a614  test    rsi, rsi
0x14000a617  jz      short loc_14000A62D
0x14000a619  call    cs:__imp_GetProcessHeap
0x14000a61f  mov     r8, rsi; lpMem
0x14000a622  xor     edx, edx; dwFlags
0x14000a624  mov     rcx, rax; hHeap
0x14000a627  call    cs:__imp_HeapFree
0x14000a62d  movups  xmmword ptr [rbx+18h], xmm6
0x14000a631  movsd   qword ptr [rbx+28h], xmm7
0x14000a636  mov     rsi, [rbx+30h]
0x14000a63a  mov     [rbx+30h], rbp
0x14000a63e  test    rsi, rsi
0x14000a641  jz      short loc_14000A657
0x14000a643  call    cs:__imp_GetProcessHeap
0x14000a649  mov     r8, rsi; lpMem
0x14000a64c  xor     edx, edx; dwFlags
0x14000a64e  mov     rcx, rax; hHeap
0x14000a651  call    cs:__imp_HeapFree
0x14000a657  mov     al, [rbx+38h]
0x14000a65a  mov     cl, [rdi+38h]
0x14000a65d  movaps  xmm6, [rsp+68h+var_38]
0x14000a662  movaps  xmm7, [rsp+68h+var_48]
0x14000a667  mov     [rdi+38h], al
0x14000a66a  mov     al, [rbx+39h]
0x14000a66d  mov     [rbx+38h], cl
0x14000a670  mov     cl, [rdi+39h]
0x14000a673  mov     [rdi+39h], al
0x14000a676  mov     [rbx+39h], cl
0x14000a679  add     rsp, 48h
0x14000a67d  pop     rdi
0x14000a67e  pop     rsi
0x14000a67f  pop     rbp
0x14000a680  pop     rbx
0x14000a681  retn
```
