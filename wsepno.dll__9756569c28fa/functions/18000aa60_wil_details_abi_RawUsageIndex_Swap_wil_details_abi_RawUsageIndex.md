# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000aa60`
- end: `0x18000ab22`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f68`
- `0x1800093f0`
- `0x180009f00`

## callees

- `0x18000aa60`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aac7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aaf1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aac7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000aaf1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aab9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aae3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aab9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000aae3`

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
0x18000aa60  push    rbx
0x18000aa62  push    rbp
0x18000aa63  push    rsi
0x18000aa64  push    rdi
0x18000aa65  sub     rsp, 48h
0x18000aa69  mov     rbp, [rcx+30h]
0x18000aa6d  mov     rbx, rdx
0x18000aa70  movaps  [rsp+68h+var_38], xmm6
0x18000aa75  mov     rdi, rcx
0x18000aa78  movups  xmm6, xmmword ptr [rcx+18h]
0x18000aa7c  movaps  [rsp+68h+var_48], xmm7
0x18000aa81  movsd   xmm7, qword ptr [rcx+28h]
0x18000aa86  mov     qword ptr [rcx+30h], 0
0x18000aa8e  movups  xmm0, xmmword ptr [rdx+18h]
0x18000aa92  movups  xmmword ptr [rcx+18h], xmm0
0x18000aa96  movsd   xmm1, qword ptr [rdx+28h]
0x18000aa9b  movsd   qword ptr [rcx+28h], xmm1
0x18000aaa0  mov     rax, [rdx+30h]
0x18000aaa4  mov     qword ptr [rdx+30h], 0
0x18000aaac  mov     rsi, [rcx+30h]
0x18000aab0  mov     [rcx+30h], rax
0x18000aab4  test    rsi, rsi
0x18000aab7  jz      short loc_18000AACD
0x18000aab9  call    cs:__imp_GetProcessHeap
0x18000aabf  mov     r8, rsi; lpMem
0x18000aac2  xor     edx, edx; dwFlags
0x18000aac4  mov     rcx, rax; hHeap
0x18000aac7  call    cs:__imp_HeapFree
0x18000aacd  movups  xmmword ptr [rbx+18h], xmm6
0x18000aad1  movsd   qword ptr [rbx+28h], xmm7
0x18000aad6  mov     rsi, [rbx+30h]
0x18000aada  mov     [rbx+30h], rbp
0x18000aade  test    rsi, rsi
0x18000aae1  jz      short loc_18000AAF7
0x18000aae3  call    cs:__imp_GetProcessHeap
0x18000aae9  mov     r8, rsi; lpMem
0x18000aaec  xor     edx, edx; dwFlags
0x18000aaee  mov     rcx, rax; hHeap
0x18000aaf1  call    cs:__imp_HeapFree
0x18000aaf7  mov     al, [rbx+38h]
0x18000aafa  mov     cl, [rdi+38h]
0x18000aafd  movaps  xmm6, [rsp+68h+var_38]
0x18000ab02  movaps  xmm7, [rsp+68h+var_48]
0x18000ab07  mov     [rdi+38h], al
0x18000ab0a  mov     al, [rbx+39h]
0x18000ab0d  mov     [rbx+38h], cl
0x18000ab10  mov     cl, [rdi+39h]
0x18000ab13  mov     [rdi+39h], al
0x18000ab16  mov     [rbx+39h], cl
0x18000ab19  add     rsp, 48h
0x18000ab1d  pop     rdi
0x18000ab1e  pop     rsi
0x18000ab1f  pop     rbp
0x18000ab20  pop     rbx
0x18000ab21  retn
```
