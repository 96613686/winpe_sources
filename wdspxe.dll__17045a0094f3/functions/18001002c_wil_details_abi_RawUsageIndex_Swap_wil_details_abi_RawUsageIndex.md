# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18001002c`
- end: `0x180010118`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `236`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009cb8`
- `0x18000d70c`
- `0x18000e7dc`

## callees

- `0x18001002c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180010089`
- `KERNEL32!GetProcessHeap` at `0x1800100ca`
- `KERNEL32!GetProcessHeap` at `0x180010089`
- `KERNEL32!GetProcessHeap` at `0x1800100ca`
- `KERNEL32!HeapFree` at `0x18001009d`
- `KERNEL32!HeapFree` at `0x1800100de`
- `KERNEL32!HeapFree` at `0x18001009d`
- `KERNEL32!HeapFree` at `0x1800100de`

## pseudocode

```c
void __fastcall wil::details_abi::RawUsageIndex::Swap(
        wil::details_abi::RawUsageIndex *this,
        struct wil::details_abi::RawUsageIndex *a2)
{
  __int64 v4; // rbp
  __int64 v5; // rax
  void *v6; // rsi
  HANDLE ProcessHeap; // rax
  void *v8; // rsi
  HANDLE v9; // rax
  char v10; // cl
  char v11; // al
  char v12; // cl
  __int128 v13; // [rsp+20h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp+8h]

  v13 = *(_OWORD *)((char *)this + 24);
  v14 = *((_QWORD *)this + 5);
  v4 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  *(_OWORD *)((char *)this + 24) = *(_OWORD *)((char *)a2 + 24);
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 5);
  v5 = *((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = 0;
  v6 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v5;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  *(_OWORD *)((char *)a2 + 24) = v13;
  *((_QWORD *)a2 + 5) = v14;
  v8 = (void *)*((_QWORD *)a2 + 6);
  *((_QWORD *)a2 + 6) = v4;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = *((_BYTE *)a2 + 56);
  v11 = *((_BYTE *)a2 + 57);
  *((_BYTE *)a2 + 56) = v10;
  v12 = *((_BYTE *)this + 57);
  *((_BYTE *)this + 57) = v11;
  *((_BYTE *)a2 + 57) = v12;
}

```

## disassembly

```asm
0x18001002c  mov     rax, rsp
0x18001002f  mov     [rax+10h], rbx
0x180010033  mov     [rax+18h], rbp
0x180010037  mov     [rax+20h], rsi
0x18001003b  push    rdi
0x18001003c  sub     rsp, 30h
0x180010040  movups  xmm0, xmmword ptr [rcx+18h]
0x180010044  mov     rbx, rdx
0x180010047  mov     rdi, rcx
0x18001004a  movups  xmmword ptr [rax-18h], xmm0
0x18001004e  movsd   xmm0, qword ptr [rcx+28h]
0x180010053  movsd   qword ptr [rax+8], xmm0
0x180010058  mov     rbp, [rcx+30h]
0x18001005c  and     qword ptr [rcx+30h], 0
0x180010061  movups  xmm0, xmmword ptr [rdx+18h]
0x180010065  movups  xmmword ptr [rcx+18h], xmm0
0x180010069  movsd   xmm1, qword ptr [rdx+28h]
0x18001006e  movsd   qword ptr [rcx+28h], xmm1
0x180010073  mov     rax, [rdx+30h]
0x180010077  and     qword ptr [rdx+30h], 0
0x18001007c  mov     rsi, [rcx+30h]
0x180010080  mov     [rcx+30h], rax
0x180010084  test    rsi, rsi
0x180010087  jz      short loc_1800100A9
0x180010089  call    cs:__imp_GetProcessHeap
0x180010090  nop     dword ptr [rax+rax+00h]
0x180010095  mov     r8, rsi; lpMem
0x180010098  xor     edx, edx; dwFlags
0x18001009a  mov     rcx, rax; hHeap
0x18001009d  call    cs:__imp_HeapFree
0x1800100a4  nop     dword ptr [rax+rax+00h]
0x1800100a9  movups  xmm0, [rsp+38h+var_18]
0x1800100ae  movups  xmmword ptr [rbx+18h], xmm0
0x1800100b2  movsd   xmm0, [rsp+38h+arg_0]
0x1800100b8  movsd   qword ptr [rbx+28h], xmm0
0x1800100bd  mov     rsi, [rbx+30h]
0x1800100c1  mov     [rbx+30h], rbp
0x1800100c5  test    rsi, rsi
0x1800100c8  jz      short loc_1800100EA
0x1800100ca  call    cs:__imp_GetProcessHeap
0x1800100d1  nop     dword ptr [rax+rax+00h]
0x1800100d6  mov     r8, rsi; lpMem
0x1800100d9  xor     edx, edx; dwFlags
0x1800100db  mov     rcx, rax; hHeap
0x1800100de  call    cs:__imp_HeapFree
0x1800100e5  nop     dword ptr [rax+rax+00h]
0x1800100ea  mov     al, [rbx+38h]
0x1800100ed  mov     cl, [rdi+38h]
0x1800100f0  mov     rbp, [rsp+38h+arg_10]
0x1800100f5  mov     rsi, [rsp+38h+arg_18]
0x1800100fa  mov     [rdi+38h], al
0x1800100fd  mov     al, [rbx+39h]
0x180010100  mov     [rbx+38h], cl
0x180010103  mov     cl, [rdi+39h]
0x180010106  mov     [rdi+39h], al
0x180010109  mov     [rbx+39h], cl
0x18001010c  mov     rbx, [rsp+38h+arg_8]
0x180010111  add     rsp, 30h
0x180010115  pop     rdi
0x180010116  retn
```
