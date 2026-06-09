# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x140009770`
- end: `0x140009832`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004fe8`
- `0x140007d6c`
- `0x140008820`

## callees

- `0x140009770`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400097d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009801`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400097d7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140009801`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097f3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400097f3`

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
0x140009770  push    rbx
0x140009772  push    rbp
0x140009773  push    rsi
0x140009774  push    rdi
0x140009775  sub     rsp, 48h
0x140009779  mov     rbp, [rcx+30h]
0x14000977d  mov     rbx, rdx
0x140009780  movaps  [rsp+68h+var_38], xmm6
0x140009785  mov     rdi, rcx
0x140009788  movups  xmm6, xmmword ptr [rcx+18h]
0x14000978c  movaps  [rsp+68h+var_48], xmm7
0x140009791  movsd   xmm7, qword ptr [rcx+28h]
0x140009796  mov     qword ptr [rcx+30h], 0
0x14000979e  movups  xmm0, xmmword ptr [rdx+18h]
0x1400097a2  movups  xmmword ptr [rcx+18h], xmm0
0x1400097a6  movsd   xmm1, qword ptr [rdx+28h]
0x1400097ab  movsd   qword ptr [rcx+28h], xmm1
0x1400097b0  mov     rax, [rdx+30h]
0x1400097b4  mov     qword ptr [rdx+30h], 0
0x1400097bc  mov     rsi, [rcx+30h]
0x1400097c0  mov     [rcx+30h], rax
0x1400097c4  test    rsi, rsi
0x1400097c7  jz      short loc_1400097DD
0x1400097c9  call    cs:__imp_GetProcessHeap
0x1400097cf  mov     r8, rsi; lpMem
0x1400097d2  xor     edx, edx; dwFlags
0x1400097d4  mov     rcx, rax; hHeap
0x1400097d7  call    cs:__imp_HeapFree
0x1400097dd  movups  xmmword ptr [rbx+18h], xmm6
0x1400097e1  movsd   qword ptr [rbx+28h], xmm7
0x1400097e6  mov     rsi, [rbx+30h]
0x1400097ea  mov     [rbx+30h], rbp
0x1400097ee  test    rsi, rsi
0x1400097f1  jz      short loc_140009807
0x1400097f3  call    cs:__imp_GetProcessHeap
0x1400097f9  mov     r8, rsi; lpMem
0x1400097fc  xor     edx, edx; dwFlags
0x1400097fe  mov     rcx, rax; hHeap
0x140009801  call    cs:__imp_HeapFree
0x140009807  mov     al, [rbx+38h]
0x14000980a  mov     cl, [rdi+38h]
0x14000980d  movaps  xmm6, [rsp+68h+var_38]
0x140009812  movaps  xmm7, [rsp+68h+var_48]
0x140009817  mov     [rdi+38h], al
0x14000981a  mov     al, [rbx+39h]
0x14000981d  mov     [rbx+38h], cl
0x140009820  mov     cl, [rdi+39h]
0x140009823  mov     [rdi+39h], al
0x140009826  mov     [rbx+39h], cl
0x140009829  add     rsp, 48h
0x14000982d  pop     rdi
0x14000982e  pop     rsi
0x14000982f  pop     rbp
0x140009830  pop     rbx
0x140009831  retn
```
