# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000c504`
- end: `0x14000c5c6`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400087d4`
- `0x14000b2bc`
- `0x14000bd70`

## callees

- `0x14000c504`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000c56b`
- `KERNEL32!HeapFree` at `0x14000c595`
- `KERNEL32!HeapFree` at `0x14000c56b`
- `KERNEL32!HeapFree` at `0x14000c595`
- `KERNEL32!GetProcessHeap` at `0x14000c55d`
- `KERNEL32!GetProcessHeap` at `0x14000c587`
- `KERNEL32!GetProcessHeap` at `0x14000c55d`
- `KERNEL32!GetProcessHeap` at `0x14000c587`

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
0x14000c504  push    rbx
0x14000c506  push    rbp
0x14000c507  push    rsi
0x14000c508  push    rdi
0x14000c509  sub     rsp, 48h
0x14000c50d  mov     rbp, [rcx+30h]
0x14000c511  mov     rbx, rdx
0x14000c514  movaps  [rsp+68h+var_38], xmm6
0x14000c519  mov     rdi, rcx
0x14000c51c  movups  xmm6, xmmword ptr [rcx+18h]
0x14000c520  movaps  [rsp+68h+var_48], xmm7
0x14000c525  movsd   xmm7, qword ptr [rcx+28h]
0x14000c52a  mov     qword ptr [rcx+30h], 0
0x14000c532  movups  xmm0, xmmword ptr [rdx+18h]
0x14000c536  movups  xmmword ptr [rcx+18h], xmm0
0x14000c53a  movsd   xmm1, qword ptr [rdx+28h]
0x14000c53f  movsd   qword ptr [rcx+28h], xmm1
0x14000c544  mov     rax, [rdx+30h]
0x14000c548  mov     qword ptr [rdx+30h], 0
0x14000c550  mov     rsi, [rcx+30h]
0x14000c554  mov     [rcx+30h], rax
0x14000c558  test    rsi, rsi
0x14000c55b  jz      short loc_14000C571
0x14000c55d  call    cs:__imp_GetProcessHeap
0x14000c563  mov     r8, rsi; lpMem
0x14000c566  xor     edx, edx; dwFlags
0x14000c568  mov     rcx, rax; hHeap
0x14000c56b  call    cs:__imp_HeapFree
0x14000c571  movups  xmmword ptr [rbx+18h], xmm6
0x14000c575  movsd   qword ptr [rbx+28h], xmm7
0x14000c57a  mov     rsi, [rbx+30h]
0x14000c57e  mov     [rbx+30h], rbp
0x14000c582  test    rsi, rsi
0x14000c585  jz      short loc_14000C59B
0x14000c587  call    cs:__imp_GetProcessHeap
0x14000c58d  mov     r8, rsi; lpMem
0x14000c590  xor     edx, edx; dwFlags
0x14000c592  mov     rcx, rax; hHeap
0x14000c595  call    cs:__imp_HeapFree
0x14000c59b  mov     al, [rbx+38h]
0x14000c59e  mov     cl, [rdi+38h]
0x14000c5a1  movaps  xmm6, [rsp+68h+var_38]
0x14000c5a6  movaps  xmm7, [rsp+68h+var_48]
0x14000c5ab  mov     [rdi+38h], al
0x14000c5ae  mov     al, [rbx+39h]
0x14000c5b1  mov     [rbx+38h], cl
0x14000c5b4  mov     cl, [rdi+39h]
0x14000c5b7  mov     [rdi+39h], al
0x14000c5ba  mov     [rbx+39h], cl
0x14000c5bd  add     rsp, 48h
0x14000c5c1  pop     rdi
0x14000c5c2  pop     rsi
0x14000c5c3  pop     rbp
0x14000c5c4  pop     rbx
0x14000c5c5  retn
```
