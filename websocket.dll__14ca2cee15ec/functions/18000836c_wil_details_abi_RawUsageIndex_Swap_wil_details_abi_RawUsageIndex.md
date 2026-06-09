# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000836c`
- end: `0x18000842e`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003914`
- `0x180006f20`
- `0x1800079d0`

## callees

- `0x18000836c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083ef`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083ef`

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
0x18000836c  push    rbx
0x18000836e  push    rbp
0x18000836f  push    rsi
0x180008370  push    rdi
0x180008371  sub     rsp, 48h
0x180008375  mov     rbp, [rcx+30h]
0x180008379  mov     rbx, rdx
0x18000837c  movaps  [rsp+68h+var_38], xmm6
0x180008381  mov     rdi, rcx
0x180008384  movups  xmm6, xmmword ptr [rcx+18h]
0x180008388  movaps  [rsp+68h+var_48], xmm7
0x18000838d  movsd   xmm7, qword ptr [rcx+28h]
0x180008392  mov     qword ptr [rcx+30h], 0
0x18000839a  movups  xmm0, xmmword ptr [rdx+18h]
0x18000839e  movups  xmmword ptr [rcx+18h], xmm0
0x1800083a2  movsd   xmm1, qword ptr [rdx+28h]
0x1800083a7  movsd   qword ptr [rcx+28h], xmm1
0x1800083ac  mov     rax, [rdx+30h]
0x1800083b0  mov     qword ptr [rdx+30h], 0
0x1800083b8  mov     rsi, [rcx+30h]
0x1800083bc  mov     [rcx+30h], rax
0x1800083c0  test    rsi, rsi
0x1800083c3  jz      short loc_1800083D9
0x1800083c5  call    cs:__imp_GetProcessHeap
0x1800083cb  mov     r8, rsi; lpMem
0x1800083ce  xor     edx, edx; dwFlags
0x1800083d0  mov     rcx, rax; hHeap
0x1800083d3  call    cs:__imp_HeapFree
0x1800083d9  movups  xmmword ptr [rbx+18h], xmm6
0x1800083dd  movsd   qword ptr [rbx+28h], xmm7
0x1800083e2  mov     rsi, [rbx+30h]
0x1800083e6  mov     [rbx+30h], rbp
0x1800083ea  test    rsi, rsi
0x1800083ed  jz      short loc_180008403
0x1800083ef  call    cs:__imp_GetProcessHeap
0x1800083f5  mov     r8, rsi; lpMem
0x1800083f8  xor     edx, edx; dwFlags
0x1800083fa  mov     rcx, rax; hHeap
0x1800083fd  call    cs:__imp_HeapFree
0x180008403  mov     al, [rbx+38h]
0x180008406  mov     cl, [rdi+38h]
0x180008409  movaps  xmm6, [rsp+68h+var_38]
0x18000840e  movaps  xmm7, [rsp+68h+var_48]
0x180008413  mov     [rdi+38h], al
0x180008416  mov     al, [rbx+39h]
0x180008419  mov     [rbx+38h], cl
0x18000841c  mov     cl, [rdi+39h]
0x18000841f  mov     [rdi+39h], al
0x180008422  mov     [rbx+39h], cl
0x180008425  add     rsp, 48h
0x180008429  pop     rdi
0x18000842a  pop     rsi
0x18000842b  pop     rbp
0x18000842c  pop     rbx
0x18000842d  retn
```
