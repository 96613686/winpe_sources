# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000dfd0`
- end: `0x18000e092`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000934c`
- `0x18000ccc0`
- `0x18000d784`

## callees

- `0x18000dfd0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e037`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e061`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e037`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000e061`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e053`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e029`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000e053`

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
0x18000dfd0  push    rbx
0x18000dfd2  push    rbp
0x18000dfd3  push    rsi
0x18000dfd4  push    rdi
0x18000dfd5  sub     rsp, 48h
0x18000dfd9  mov     rbp, [rcx+30h]
0x18000dfdd  mov     rbx, rdx
0x18000dfe0  movaps  [rsp+68h+var_38], xmm6
0x18000dfe5  mov     rdi, rcx
0x18000dfe8  movups  xmm6, xmmword ptr [rcx+18h]
0x18000dfec  movaps  [rsp+68h+var_48], xmm7
0x18000dff1  movsd   xmm7, qword ptr [rcx+28h]
0x18000dff6  mov     qword ptr [rcx+30h], 0
0x18000dffe  movups  xmm0, xmmword ptr [rdx+18h]
0x18000e002  movups  xmmword ptr [rcx+18h], xmm0
0x18000e006  movsd   xmm1, qword ptr [rdx+28h]
0x18000e00b  movsd   qword ptr [rcx+28h], xmm1
0x18000e010  mov     rax, [rdx+30h]
0x18000e014  mov     qword ptr [rdx+30h], 0
0x18000e01c  mov     rsi, [rcx+30h]
0x18000e020  mov     [rcx+30h], rax
0x18000e024  test    rsi, rsi
0x18000e027  jz      short loc_18000E03D
0x18000e029  call    cs:__imp_GetProcessHeap
0x18000e02f  mov     r8, rsi; lpMem
0x18000e032  xor     edx, edx; dwFlags
0x18000e034  mov     rcx, rax; hHeap
0x18000e037  call    cs:__imp_HeapFree
0x18000e03d  movups  xmmword ptr [rbx+18h], xmm6
0x18000e041  movsd   qword ptr [rbx+28h], xmm7
0x18000e046  mov     rsi, [rbx+30h]
0x18000e04a  mov     [rbx+30h], rbp
0x18000e04e  test    rsi, rsi
0x18000e051  jz      short loc_18000E067
0x18000e053  call    cs:__imp_GetProcessHeap
0x18000e059  mov     r8, rsi; lpMem
0x18000e05c  xor     edx, edx; dwFlags
0x18000e05e  mov     rcx, rax; hHeap
0x18000e061  call    cs:__imp_HeapFree
0x18000e067  mov     al, [rbx+38h]
0x18000e06a  mov     cl, [rdi+38h]
0x18000e06d  movaps  xmm6, [rsp+68h+var_38]
0x18000e072  movaps  xmm7, [rsp+68h+var_48]
0x18000e077  mov     [rdi+38h], al
0x18000e07a  mov     al, [rbx+39h]
0x18000e07d  mov     [rbx+38h], cl
0x18000e080  mov     cl, [rdi+39h]
0x18000e083  mov     [rdi+39h], al
0x18000e086  mov     [rbx+39h], cl
0x18000e089  add     rsp, 48h
0x18000e08d  pop     rdi
0x18000e08e  pop     rsi
0x18000e08f  pop     rbp
0x18000e090  pop     rbx
0x18000e091  retn
```
