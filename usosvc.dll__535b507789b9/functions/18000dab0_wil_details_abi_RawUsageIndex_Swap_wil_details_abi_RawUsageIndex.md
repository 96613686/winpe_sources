# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000dab0`
- end: `0x18000db72`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae54`
- `0x18000c954`
- `0x18000d35c`

## callees

- `0x18000dab0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db09`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db17`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db41`

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
0x18000dab0  push    rbx
0x18000dab2  push    rbp
0x18000dab3  push    rsi
0x18000dab4  push    rdi
0x18000dab5  sub     rsp, 48h
0x18000dab9  mov     rbp, [rcx+30h]
0x18000dabd  mov     rbx, rdx
0x18000dac0  movaps  [rsp+68h+var_38], xmm6
0x18000dac5  mov     rdi, rcx
0x18000dac8  movups  xmm6, xmmword ptr [rcx+18h]
0x18000dacc  movaps  [rsp+68h+var_48], xmm7
0x18000dad1  movsd   xmm7, qword ptr [rcx+28h]
0x18000dad6  mov     qword ptr [rcx+30h], 0
0x18000dade  movups  xmm0, xmmword ptr [rdx+18h]
0x18000dae2  movups  xmmword ptr [rcx+18h], xmm0
0x18000dae6  movsd   xmm1, qword ptr [rdx+28h]
0x18000daeb  movsd   qword ptr [rcx+28h], xmm1
0x18000daf0  mov     rax, [rdx+30h]
0x18000daf4  mov     qword ptr [rdx+30h], 0
0x18000dafc  mov     rsi, [rcx+30h]
0x18000db00  mov     [rcx+30h], rax
0x18000db04  test    rsi, rsi
0x18000db07  jz      short loc_18000DB1D
0x18000db09  call    cs:__imp_GetProcessHeap
0x18000db0f  mov     r8, rsi; lpMem
0x18000db12  xor     edx, edx; dwFlags
0x18000db14  mov     rcx, rax; hHeap
0x18000db17  call    cs:__imp_HeapFree
0x18000db1d  movups  xmmword ptr [rbx+18h], xmm6
0x18000db21  movsd   qword ptr [rbx+28h], xmm7
0x18000db26  mov     rsi, [rbx+30h]
0x18000db2a  mov     [rbx+30h], rbp
0x18000db2e  test    rsi, rsi
0x18000db31  jz      short loc_18000DB47
0x18000db33  call    cs:__imp_GetProcessHeap
0x18000db39  mov     r8, rsi; lpMem
0x18000db3c  xor     edx, edx; dwFlags
0x18000db3e  mov     rcx, rax; hHeap
0x18000db41  call    cs:__imp_HeapFree
0x18000db47  mov     al, [rbx+38h]
0x18000db4a  mov     cl, [rdi+38h]
0x18000db4d  movaps  xmm6, [rsp+68h+var_38]
0x18000db52  movaps  xmm7, [rsp+68h+var_48]
0x18000db57  mov     [rdi+38h], al
0x18000db5a  mov     al, [rbx+39h]
0x18000db5d  mov     [rbx+38h], cl
0x18000db60  mov     cl, [rdi+39h]
0x18000db63  mov     [rdi+39h], al
0x18000db66  mov     [rbx+39h], cl
0x18000db69  add     rsp, 48h
0x18000db6d  pop     rdi
0x18000db6e  pop     rsi
0x18000db6f  pop     rbp
0x18000db70  pop     rbx
0x18000db71  retn
```
