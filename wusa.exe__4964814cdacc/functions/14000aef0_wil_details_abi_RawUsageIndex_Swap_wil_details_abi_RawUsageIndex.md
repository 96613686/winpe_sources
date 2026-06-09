# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x14000aef0`
- end: `0x14000afb2`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `194`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004f94`
- `0x140009700`
- `0x14000a0ac`

## callees

- `0x14000aef0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000af57`
- `KERNEL32!HeapFree` at `0x14000af81`
- `KERNEL32!HeapFree` at `0x14000af57`
- `KERNEL32!HeapFree` at `0x14000af81`
- `KERNEL32!GetProcessHeap` at `0x14000af49`
- `KERNEL32!GetProcessHeap` at `0x14000af73`
- `KERNEL32!GetProcessHeap` at `0x14000af49`
- `KERNEL32!GetProcessHeap` at `0x14000af73`

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
0x14000aef0  push    rbx
0x14000aef2  push    rbp
0x14000aef3  push    rsi
0x14000aef4  push    rdi
0x14000aef5  sub     rsp, 48h
0x14000aef9  mov     rbp, [rcx+30h]
0x14000aefd  mov     rbx, rdx
0x14000af00  movaps  [rsp+68h+var_38], xmm6
0x14000af05  mov     rdi, rcx
0x14000af08  movups  xmm6, xmmword ptr [rcx+18h]
0x14000af0c  movaps  [rsp+68h+var_48], xmm7
0x14000af11  movsd   xmm7, qword ptr [rcx+28h]
0x14000af16  mov     qword ptr [rcx+30h], 0
0x14000af1e  movups  xmm0, xmmword ptr [rdx+18h]
0x14000af22  movups  xmmword ptr [rcx+18h], xmm0
0x14000af26  movsd   xmm1, qword ptr [rdx+28h]
0x14000af2b  movsd   qword ptr [rcx+28h], xmm1
0x14000af30  mov     rax, [rdx+30h]
0x14000af34  mov     qword ptr [rdx+30h], 0
0x14000af3c  mov     rsi, [rcx+30h]
0x14000af40  mov     [rcx+30h], rax
0x14000af44  test    rsi, rsi
0x14000af47  jz      short loc_14000AF5D
0x14000af49  call    cs:__imp_GetProcessHeap
0x14000af4f  mov     r8, rsi; lpMem
0x14000af52  xor     edx, edx; dwFlags
0x14000af54  mov     rcx, rax; hHeap
0x14000af57  call    cs:__imp_HeapFree
0x14000af5d  movups  xmmword ptr [rbx+18h], xmm6
0x14000af61  movsd   qword ptr [rbx+28h], xmm7
0x14000af66  mov     rsi, [rbx+30h]
0x14000af6a  mov     [rbx+30h], rbp
0x14000af6e  test    rsi, rsi
0x14000af71  jz      short loc_14000AF87
0x14000af73  call    cs:__imp_GetProcessHeap
0x14000af79  mov     r8, rsi; lpMem
0x14000af7c  xor     edx, edx; dwFlags
0x14000af7e  mov     rcx, rax; hHeap
0x14000af81  call    cs:__imp_HeapFree
0x14000af87  mov     al, [rbx+38h]
0x14000af8a  mov     cl, [rdi+38h]
0x14000af8d  movaps  xmm6, [rsp+68h+var_38]
0x14000af92  movaps  xmm7, [rsp+68h+var_48]
0x14000af97  mov     [rdi+38h], al
0x14000af9a  mov     al, [rbx+39h]
0x14000af9d  mov     [rbx+38h], cl
0x14000afa0  mov     cl, [rdi+39h]
0x14000afa3  mov     [rdi+39h], al
0x14000afa6  mov     [rbx+39h], cl
0x14000afa9  add     rsp, 48h
0x14000afad  pop     rdi
0x14000afae  pop     rsi
0x14000afaf  pop     rbp
0x14000afb0  pop     rbx
0x14000afb1  retn
```
