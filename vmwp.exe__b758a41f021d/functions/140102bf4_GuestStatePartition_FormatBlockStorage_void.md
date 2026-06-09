# GuestStatePartition::FormatBlockStorage(void)

- ea: `0x140102bf4`
- end: `0x140102fb0`
- name: `?FormatBlockStorage@GuestStatePartition@@AEAAXXZ`
- size: `956`
- prototype: `void __fastcall(GuestStatePartition *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401a88e4`

## callees

- `0x1400691b4`
- `0x140102bf4`
- `0x140102fb8`
- `0x14010303c`
- `0x140115468`
- `0x14011ea40`
- `0x14011f6fc`
- `0x1401663b0`
- `0x1402cb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140102e8b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140102e8b`
- `RPCRT4!UuidCreate` at `0x140102e10`
- `RPCRT4!UuidCreate` at `0x140102e55`
- `RPCRT4!UuidCreate` at `0x140102e10`
- `RPCRT4!UuidCreate` at `0x140102e55`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall GuestStatePartition::FormatBlockStorage(GuestStatePartition *this)
{
  __int64 v2; // r14
  __int64 v3; // rdx
  __int64 v4; // rbx
  char *v5; // rdi
  __int64 v6; // rax
  char v7; // dl
  __int64 v8; // rax
  char v9; // dl
  __int64 v10; // r15
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // r12d
  __int64 v14; // r13
  unsigned __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // r14
  unsigned __int64 v18; // rbx
  char *v19; // rdi
  char *v20; // rax
  size_t v21; // rbx
  char *v22; // rdi
  UUID *v23; // rbx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // rcx
  _BYTE v27[2]; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v28[6]; // [rsp+42h] [rbp-27h] BYREF
  unsigned __int64 v29; // [rsp+48h] [rbp-21h]
  UUID Uuid; // [rsp+50h] [rbp-19h] BYREF
  void *v31[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+70h] [rbp+7h]

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 96LL))(*((_QWORD *)this + 1));
  v3 = *((unsigned int *)this + 8);
  v4 = v2 * v3;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v27[0] = 0;
  std::vector<enum gsl::byte>::vector<enum gsl::byte>(v31, v3, v27);
  v5 = (char *)v31[0];
  *((_BYTE *)v31[0] + 446) = 0;
  v6 = DiskStructs::Utilities::ChsAddressFromLba(v28, 1, v4);
  v7 = *(_BYTE *)(v6 + 2);
  *(_WORD *)(v5 + 447) = *(_WORD *)v6;
  v5[449] = v7;
  v5[450] = -18;
  *(_DWORD *)(v5 + 454) = 1;
  v8 = DiskStructs::Utilities::ChsAddressFromLba(v28, v2, v4);
  v9 = *(_BYTE *)(v8 + 2);
  *(_WORD *)(v5 + 451) = *(_WORD *)v8;
  v5[453] = v9;
  v10 = v2 - 1;
  v11 = -1;
  if ( (unsigned __int64)(v2 - 1) < 0xFFFFFFFF )
    v11 = v2 - 1;
  *(_DWORD *)(v5 + 458) = v11;
  *((_WORD *)v5 + 255) = -21931;
  (*(void (__fastcall **)(_QWORD, void *, _QWORD, _QWORD, int, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    v31[0],
    *((unsigned int *)this + 8),
    0,
    1,
    0);
  memset_0(v31[0], 0, (char *)v31[1] - (char *)v31[0]);
  v12 = *((_DWORD *)this + 8);
  v13 = -v12 & (v12 + 0x3FFF);
  v14 = v13 / v12;
  v15 = v2 - v14 - 1;
  v16 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 1) + 112LL))(
          *((_QWORD *)this + 1),
          v13 % v12)
      / v12;
  v17 = ~(v16 - 1) & ((unsigned int)v16 + v14 + 1);
  v29 = v15 - v15 % (unsigned int)v16 - 1;
  v27[0] = 0;
  v18 = v13 + *((_DWORD *)this + 8);
  v19 = (char *)v31[1];
  if ( v18 < (char *)v31[1] - (char *)v31[0] )
  {
    v20 = (char *)v31[0] + v18;
LABEL_9:
    v31[1] = v20;
    goto LABEL_10;
  }
  if ( v18 > (char *)v31[1] - (char *)v31[0] )
  {
    if ( v18 <= v32 - (unsigned __int64)v31[0] )
    {
      v21 = v18 - ((char *)v31[1] - (char *)v31[0]);
      memset_0(v31[1], 0, v21);
      v20 = &v19[v21];
      goto LABEL_9;
    }
    std::vector<unsigned char>::_Resize_reallocate<unsigned char>(v31, v13 + *((_DWORD *)this + 8), v27);
  }
LABEL_10:
  v22 = (char *)v31[0];
  *(_QWORD *)v31[0] = 0x5452415020494645LL;
  *((_DWORD *)v22 + 2) = 0x10000;
  *((_DWORD *)v22 + 3) = 92;
  *((_QWORD *)v22 + 3) = 1;
  *((_QWORD *)v22 + 4) = v10;
  *((_QWORD *)v22 + 5) = v17;
  *((_QWORD *)v22 + 6) = v29;
  Uuid = 0;
  UuidCreate(&Uuid);
  *(UUID *)(v22 + 56) = Uuid;
  *((_QWORD *)v22 + 9) = 2;
  *((_DWORD *)v22 + 20) = 128;
  *((_DWORD *)v22 + 21) = 128;
  v23 = (UUID *)((char *)v31[0] + *((unsigned int *)this + 8));
  *v23 = GPT_PARTITION_TYPE_GUEST_STATE;
  Uuid = 0;
  UuidCreate(&Uuid);
  v23[1] = Uuid;
  *(_QWORD *)&v23[2].Data1 = v17;
  *(_QWORD *)v23[2].Data4 = v29;
  _o_wcsncpy_s(v23[3].Data4, 36, L"Guest Runtime State Partition");
  *((_DWORD *)v22 + 22) = ComputeCrc32(v24, v23, v13);
  *((_DWORD *)v22 + 4) = ComputeCrc32(v25, v22, 0x5Cu);
  (*(void (__fastcall **)(_QWORD, void *, _QWORD, __int64, _DWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    v31[0],
    v13 + *((_DWORD *)this + 8),
    1,
    v14 + 1,
    0);
  v26 = *((_QWORD *)v22 + 3);
  *((_QWORD *)v22 + 3) = *((_QWORD *)v22 + 4);
  *((_QWORD *)v22 + 4) = v26;
  *((_QWORD *)v22 + 9) = v10 - v14;
  *((_DWORD *)v22 + 4) = ComputeCrc32(v26, v22, 0x5Cu);
  (*(void (__fastcall **)(_QWORD, void *, _QWORD, __int64, int, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    v31[0],
    *((unsigned int *)this + 8),
    v10,
    1,
    0);
  (*(void (__fastcall **)(_QWORD, char *, _QWORD, __int64, _DWORD, _QWORD))(**((_QWORD **)this + 1) + 128LL))(
    *((_QWORD *)this + 1),
    (char *)v31[0] + *((unsigned int *)this + 8),
    v13,
    v10 - v14,
    v14,
    0);
  *((_QWORD *)this + 2) = v17;
  *((_QWORD *)this + 3) = v29 - v17 + 1;
  std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(v31);
}

```

## disassembly

```asm
0x140102bf4  push    rbp
0x140102bf6  push    rbx
0x140102bf7  push    rsi
0x140102bf8  push    rdi
0x140102bf9  push    r12
0x140102bfb  push    r13
0x140102bfd  push    r14
0x140102bff  push    r15
0x140102c01  lea     rbp, [rsp-1Fh]
0x140102c06  sub     rsp, 88h
0x140102c0d  mov     rax, cs:__security_cookie
0x140102c14  xor     rax, rsp
0x140102c17  mov     [rbp+57h+var_48], rax
0x140102c1b  mov     rsi, rcx
0x140102c1e  mov     rcx, [rcx+8]
0x140102c22  mov     rax, [rcx]
0x140102c25  mov     rax, [rax+60h]
0x140102c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102c2e  mov     r14, rax
0x140102c31  mov     edx, [rsi+20h]
0x140102c34  mov     ebx, edx
0x140102c36  imul    rbx, rax
0x140102c3a  xorps   xmm0, xmm0
0x140102c3d  xor     eax, eax
0x140102c3f  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x140102c43  mov     [rbp+57h+var_50], rax
0x140102c47  xor     r12d, r12d
0x140102c4a  mov     [rbp+57h+var_80], r12b
0x140102c4e  lea     r8, [rbp+57h+var_80]
0x140102c52  lea     rcx, [rbp+57h+var_60]
0x140102c56  call    ??$?0V?$allocator@W4byte@gsl@@@std@@$0A@@?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBW4byte@gsl@@AEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,gsl::byte const &,std::allocator<gsl::byte> const &)
0x140102c5b  nop
0x140102c5c  mov     rdi, [rbp+57h+var_60]
0x140102c60  mov     [rdi+1BEh], r12b
0x140102c67  mov     r8, rbx
0x140102c6a  lea     r13d, [r12+1]
0x140102c6f  mov     edx, r13d
0x140102c72  lea     rcx, [rbp+57h+var_7E]
0x140102c76  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x140102c7b  movzx   ecx, word ptr [rax]
0x140102c7e  mov     dl, [rax+2]
0x140102c81  mov     [rdi+1BFh], cx
0x140102c88  mov     [rdi+1C1h], dl
0x140102c8e  mov     byte ptr [rdi+1C2h], 0EEh
0x140102c95  mov     [rdi+1C6h], r13d
0x140102c9c  mov     r8, rbx
0x140102c9f  mov     rdx, r14
0x140102ca2  lea     rcx, [rbp+57h+var_7E]
0x140102ca6  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x140102cab  movzx   ecx, word ptr [rax]
0x140102cae  mov     dl, [rax+2]
0x140102cb1  mov     [rdi+1C3h], cx
0x140102cb8  mov     [rdi+1C5h], dl
0x140102cbe  lea     r15, [r14-1]
0x140102cc2  mov     eax, 0FFFFFFFFh
0x140102cc7  cmp     r15, rax
0x140102cca  jnb     short loc_140102CCF
0x140102ccc  mov     eax, r15d
0x140102ccf  mov     [rdi+1CAh], eax
0x140102cd5  mov     word ptr [rdi+1FEh], 0AA55h
0x140102cde  mov     rcx, [rsi+8]
0x140102ce2  mov     rax, [rcx]
0x140102ce5  mov     [rsp+0C0h+var_98], r12
0x140102cea  mov     [rsp+0C0h+var_A0], r13d
0x140102cef  xor     r9d, r9d
0x140102cf2  mov     r8d, [rsi+20h]
0x140102cf6  mov     rdx, [rbp+57h+var_60]
0x140102cfa  mov     rax, [rax+80h]
0x140102d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102d06  mov     rcx, [rbp+57h+var_60]; void *
0x140102d0a  mov     r8, [rbp+57h+var_60+8]
0x140102d0e  sub     r8, rcx; Size
0x140102d11  xor     edx, edx; Val
0x140102d13  call    memset_0
0x140102d18  mov     ebx, [rsi+20h]
0x140102d1b  lea     r12d, [rbx+3FFFh]
0x140102d22  mov     eax, ebx
0x140102d24  neg     eax
0x140102d26  and     r12d, eax
0x140102d29  xor     edx, edx
0x140102d2b  mov     eax, r12d
0x140102d2e  div     ebx
0x140102d30  mov     r13d, eax
0x140102d33  sub     r14, r13
0x140102d36  lea     rdi, [r14-1]
0x140102d3a  mov     rcx, [rsi+8]
0x140102d3e  mov     rax, [rcx]
0x140102d41  mov     rax, [rax+70h]
0x140102d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102d4a  xor     edx, edx
0x140102d4c  div     ebx
0x140102d4e  mov     ecx, eax
0x140102d50  lea     r14, [r13+1]
0x140102d54  add     r14, rcx
0x140102d57  dec     rax
0x140102d5a  not     rax
0x140102d5d  and     r14, rax
0x140102d60  xor     edx, edx
0x140102d62  mov     rax, rdi
0x140102d65  div     rcx
0x140102d68  sub     rdi, rdx
0x140102d6b  lea     rax, [rdi-1]
0x140102d6f  mov     [rbp+57h+var_78], rax
0x140102d73  mov     [rbp+57h+var_80], 0
0x140102d77  mov     ebx, [rsi+20h]
0x140102d7a  add     ebx, r12d
0x140102d7d  mov     rdx, [rbp+57h+var_60]
0x140102d81  mov     rdi, [rbp+57h+var_60+8]
0x140102d85  mov     rcx, rdi
0x140102d88  sub     rcx, rdx
0x140102d8b  cmp     rbx, rcx
0x140102d8e  jnb     short loc_140102D96
0x140102d90  lea     rax, [rbx+rdx]
0x140102d94  jmp     short loc_140102DCA
0x140102d96  jbe     short loc_140102DCE
0x140102d98  mov     rax, [rbp+57h+var_50]
0x140102d9c  sub     rax, rdx
0x140102d9f  cmp     rbx, rax
0x140102da2  jbe     short loc_140102DB6
0x140102da4  lea     r8, [rbp+57h+var_80]
0x140102da8  mov     rdx, rbx
0x140102dab  lea     rcx, [rbp+57h+var_60]
0x140102daf  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x140102db4  jmp     short loc_140102DCE
0x140102db6  sub     rbx, rcx
0x140102db9  mov     r8, rbx; Size
0x140102dbc  xor     edx, edx; Val
0x140102dbe  mov     rcx, rdi; void *
0x140102dc1  call    memset_0
0x140102dc6  lea     rax, [rbx+rdi]
0x140102dca  mov     [rbp+57h+var_60+8], rax
0x140102dce  mov     rdi, [rbp+57h+var_60]
0x140102dd2  mov     rax, 5452415020494645h
0x140102ddc  mov     [rdi], rax
0x140102ddf  mov     dword ptr [rdi+8], 10000h
0x140102de6  mov     dword ptr [rdi+0Ch], 5Ch ; '\'
0x140102ded  mov     qword ptr [rdi+18h], 1
0x140102df5  mov     [rdi+20h], r15
0x140102df9  mov     [rdi+28h], r14
0x140102dfd  mov     rax, [rbp+57h+var_78]
0x140102e01  mov     [rdi+30h], rax
0x140102e05  xorps   xmm0, xmm0
0x140102e08  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x140102e0c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x140102e10  call    cs:__imp_UuidCreate
0x140102e17  nop     dword ptr [rax+rax+00h]
0x140102e1c  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x140102e20  movdqu  xmmword ptr [rdi+38h], xmm0
0x140102e25  mov     qword ptr [rdi+48h], 2
0x140102e2d  mov     eax, 80h
0x140102e32  mov     [rdi+50h], eax
0x140102e35  mov     [rdi+54h], eax
0x140102e38  mov     ebx, [rsi+20h]
0x140102e3b  add     rbx, [rbp+57h+var_60]
0x140102e3f  movups  xmm0, xmmword ptr cs:?GPT_PARTITION_TYPE_GUEST_STATE@@3U_GUID@@B.Data1; _GUID const GPT_PARTITION_TYPE_GUEST_STATE ...
0x140102e46  movdqu  xmmword ptr [rbx], xmm0
0x140102e4a  xorps   xmm0, xmm0
0x140102e4d  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x140102e51  lea     rcx, [rbp+57h+Uuid]; Uuid
0x140102e55  call    cs:__imp_UuidCreate
0x140102e5c  nop     dword ptr [rax+rax+00h]
0x140102e61  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x140102e65  movdqu  xmmword ptr [rbx+10h], xmm0
0x140102e6a  mov     [rbx+20h], r14
0x140102e6e  mov     rax, [rbp+57h+var_78]
0x140102e72  mov     [rbx+28h], rax
0x140102e76  lea     rcx, [rbx+38h]
0x140102e7a  mov     r9d, 1Eh
0x140102e80  lea     r8, ?GPT_PARTITION_NAME_GUEST_STATE@@3QBGB; "Guest Runtime State Partition"
0x140102e87  lea     edx, [r9+6]
0x140102e8b  call    cs:__imp__o_wcsncpy_s
0x140102e92  nop     dword ptr [rax+rax+00h]
0x140102e97  mov     r8d, r12d; unsigned int
0x140102e9a  mov     rdx, rbx; void *
0x140102e9d  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x140102ea2  mov     [rdi+58h], eax
0x140102ea5  mov     r8d, 5Ch ; '\'; unsigned int
0x140102eab  mov     rdx, rdi; void *
0x140102eae  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x140102eb3  mov     [rdi+10h], eax
0x140102eb6  mov     rcx, [rsi+8]
0x140102eba  mov     rdx, [rcx]
0x140102ebd  lea     r9d, [r13+1]
0x140102ec1  mov     r8d, [rsi+20h]
0x140102ec5  add     r8d, r12d
0x140102ec8  mov     rax, [rdx+80h]
0x140102ecf  mov     [rsp+0C0h+var_98], 0
0x140102ed8  mov     [rsp+0C0h+var_A0], r9d
0x140102edd  mov     r9d, 1
0x140102ee3  mov     rdx, [rbp+57h+var_60]
0x140102ee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102eec  mov     rbx, r15
0x140102eef  sub     rbx, r13
0x140102ef2  mov     rcx, [rdi+18h]; unsigned int
0x140102ef6  mov     rax, [rdi+20h]
0x140102efa  mov     [rdi+18h], rax
0x140102efe  mov     [rdi+20h], rcx
0x140102f02  mov     [rdi+48h], rbx
0x140102f06  mov     r8d, 5Ch ; '\'; unsigned int
0x140102f0c  mov     rdx, rdi; void *
0x140102f0f  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x140102f14  mov     [rdi+10h], eax
0x140102f17  mov     rcx, [rsi+8]
0x140102f1b  mov     rax, [rcx]
0x140102f1e  mov     [rsp+0C0h+var_98], 0
0x140102f27  mov     [rsp+0C0h+var_A0], 1
0x140102f2f  mov     r9, r15
0x140102f32  mov     r8d, [rsi+20h]
0x140102f36  mov     rdx, [rbp+57h+var_60]
0x140102f3a  mov     rax, [rax+80h]
0x140102f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102f46  mov     rcx, [rsi+8]
0x140102f4a  mov     rax, [rcx]
0x140102f4d  mov     edx, [rsi+20h]
0x140102f50  add     rdx, [rbp+57h+var_60]
0x140102f54  mov     [rsp+0C0h+var_98], 0
0x140102f5d  mov     [rsp+0C0h+var_A0], r13d
0x140102f62  mov     r9, rbx
0x140102f65  mov     r8d, r12d
0x140102f68  mov     rax, [rax+80h]
0x140102f6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140102f74  mov     [rsi+10h], r14
0x140102f78  mov     rax, [rbp+57h+var_78]
0x140102f7c  sub     rax, r14
0x140102f7f  inc     rax
0x140102f82  mov     [rsi+18h], rax
0x140102f86  lea     rcx, [rbp+57h+var_60]
0x140102f8a  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140102f8f  mov     rcx, [rbp+57h+var_48]
0x140102f93  xor     rcx, rsp; StackCookie
0x140102f96  call    __security_check_cookie
0x140102f9b  add     rsp, 88h
0x140102fa2  pop     r15
0x140102fa4  pop     r14
0x140102fa6  pop     r13
0x140102fa8  pop     r12
0x140102faa  pop     rdi
0x140102fab  pop     rsi
0x140102fac  pop     rbx
0x140102fad  pop     rbp
0x140102fae  retn
```
