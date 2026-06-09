# wil::details_abi::RawUsageIndex::Swap(wil::details_abi::RawUsageIndex &)

- ea: `0x18000af14`
- end: `0x18000b000`
- name: `?Swap@RawUsageIndex@details_abi@wil@@QEAAXAEAV123@@Z`
- size: `236`
- prototype: `void __fastcall(wil::details_abi::RawUsageIndex *__hidden this, struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035ac`
- `0x180008c2c`
- `0x1800097c8`

## callees

- `0x18000af14`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000af85`
- `KERNEL32!HeapFree` at `0x18000afc6`
- `KERNEL32!HeapFree` at `0x18000af85`
- `KERNEL32!HeapFree` at `0x18000afc6`
- `KERNEL32!GetProcessHeap` at `0x18000af71`
- `KERNEL32!GetProcessHeap` at `0x18000afb2`
- `KERNEL32!GetProcessHeap` at `0x18000af71`
- `KERNEL32!GetProcessHeap` at `0x18000afb2`

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
0x18000af14  mov     rax, rsp
0x18000af17  mov     [rax+10h], rbx
0x18000af1b  mov     [rax+18h], rbp
0x18000af1f  mov     [rax+20h], rsi
0x18000af23  push    rdi
0x18000af24  sub     rsp, 30h
0x18000af28  movups  xmm0, xmmword ptr [rcx+18h]
0x18000af2c  mov     rbx, rdx
0x18000af2f  mov     rdi, rcx
0x18000af32  movups  xmmword ptr [rax-18h], xmm0
0x18000af36  movsd   xmm0, qword ptr [rcx+28h]
0x18000af3b  movsd   qword ptr [rax+8], xmm0
0x18000af40  mov     rbp, [rcx+30h]
0x18000af44  and     qword ptr [rcx+30h], 0
0x18000af49  movups  xmm0, xmmword ptr [rdx+18h]
0x18000af4d  movups  xmmword ptr [rcx+18h], xmm0
0x18000af51  movsd   xmm1, qword ptr [rdx+28h]
0x18000af56  movsd   qword ptr [rcx+28h], xmm1
0x18000af5b  mov     rax, [rdx+30h]
0x18000af5f  and     qword ptr [rdx+30h], 0
0x18000af64  mov     rsi, [rcx+30h]
0x18000af68  mov     [rcx+30h], rax
0x18000af6c  test    rsi, rsi
0x18000af6f  jz      short loc_18000AF91
0x18000af71  call    cs:__imp_GetProcessHeap
0x18000af78  nop     dword ptr [rax+rax+00h]
0x18000af7d  mov     r8, rsi; lpMem
0x18000af80  xor     edx, edx; dwFlags
0x18000af82  mov     rcx, rax; hHeap
0x18000af85  call    cs:__imp_HeapFree
0x18000af8c  nop     dword ptr [rax+rax+00h]
0x18000af91  movups  xmm0, [rsp+38h+var_18]
0x18000af96  movups  xmmword ptr [rbx+18h], xmm0
0x18000af9a  movsd   xmm0, [rsp+38h+arg_0]
0x18000afa0  movsd   qword ptr [rbx+28h], xmm0
0x18000afa5  mov     rsi, [rbx+30h]
0x18000afa9  mov     [rbx+30h], rbp
0x18000afad  test    rsi, rsi
0x18000afb0  jz      short loc_18000AFD2
0x18000afb2  call    cs:__imp_GetProcessHeap
0x18000afb9  nop     dword ptr [rax+rax+00h]
0x18000afbe  mov     r8, rsi; lpMem
0x18000afc1  xor     edx, edx; dwFlags
0x18000afc3  mov     rcx, rax; hHeap
0x18000afc6  call    cs:__imp_HeapFree
0x18000afcd  nop     dword ptr [rax+rax+00h]
0x18000afd2  mov     al, [rbx+38h]
0x18000afd5  mov     cl, [rdi+38h]
0x18000afd8  mov     rbp, [rsp+38h+arg_10]
0x18000afdd  mov     rsi, [rsp+38h+arg_18]
0x18000afe2  mov     [rdi+38h], al
0x18000afe5  mov     al, [rbx+39h]
0x18000afe8  mov     [rbx+38h], cl
0x18000afeb  mov     cl, [rdi+39h]
0x18000afee  mov     [rdi+39h], al
0x18000aff1  mov     [rbx+39h], cl
0x18000aff4  mov     rbx, [rsp+38h+arg_8]
0x18000aff9  add     rsp, 30h
0x18000affd  pop     rdi
0x18000affe  retn
```
