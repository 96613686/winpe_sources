# GuestStatePartition::FormatBlockStorage(void)

- ea: `0x140111704`
- end: `0x140111ac0`
- name: `?FormatBlockStorage@GuestStatePartition@@AEAAXXZ`
- size: `956`
- prototype: `void __fastcall(GuestStatePartition *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1401b9804`

## callees

- `0x14005e804`
- `0x140111704`
- `0x140111ac8`
- `0x140111b4c`
- `0x140124728`
- `0x140132960`
- `0x14013361c`
- `0x140177d70`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14011199b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14011199b`
- `RPCRT4!UuidCreate` at `0x140111920`
- `RPCRT4!UuidCreate` at `0x140111965`
- `RPCRT4!UuidCreate` at `0x140111920`
- `RPCRT4!UuidCreate` at `0x140111965`

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
0x140111704  push    rbp
0x140111706  push    rbx
0x140111707  push    rsi
0x140111708  push    rdi
0x140111709  push    r12
0x14011170b  push    r13
0x14011170d  push    r14
0x14011170f  push    r15
0x140111711  lea     rbp, [rsp-1Fh]
0x140111716  sub     rsp, 88h
0x14011171d  mov     rax, cs:__security_cookie
0x140111724  xor     rax, rsp
0x140111727  mov     [rbp+57h+var_48], rax
0x14011172b  mov     rsi, rcx
0x14011172e  mov     rcx, [rcx+8]
0x140111732  mov     rax, [rcx]
0x140111735  mov     rax, [rax+60h]
0x140111739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011173e  mov     r14, rax
0x140111741  mov     edx, [rsi+20h]
0x140111744  mov     ebx, edx
0x140111746  imul    rbx, rax
0x14011174a  xorps   xmm0, xmm0
0x14011174d  xor     eax, eax
0x14011174f  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x140111753  mov     [rbp+57h+var_50], rax
0x140111757  xor     r12d, r12d
0x14011175a  mov     [rbp+57h+var_80], r12b
0x14011175e  lea     r8, [rbp+57h+var_80]
0x140111762  lea     rcx, [rbp+57h+var_60]
0x140111766  call    ??$?0V?$allocator@W4byte@gsl@@@std@@$0A@@?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBW4byte@gsl@@AEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,gsl::byte const &,std::allocator<gsl::byte> const &)
0x14011176b  nop
0x14011176c  mov     rdi, [rbp+57h+var_60]
0x140111770  mov     [rdi+1BEh], r12b
0x140111777  mov     r8, rbx
0x14011177a  lea     r13d, [r12+1]
0x14011177f  mov     edx, r13d
0x140111782  lea     rcx, [rbp+57h+var_7E]
0x140111786  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x14011178b  movzx   ecx, word ptr [rax]
0x14011178e  mov     dl, [rax+2]
0x140111791  mov     [rdi+1BFh], cx
0x140111798  mov     [rdi+1C1h], dl
0x14011179e  mov     byte ptr [rdi+1C2h], 0EEh
0x1401117a5  mov     [rdi+1C6h], r13d
0x1401117ac  mov     r8, rbx
0x1401117af  mov     rdx, r14
0x1401117b2  lea     rcx, [rbp+57h+var_7E]
0x1401117b6  call    ?ChsAddressFromLba@Utilities@DiskStructs@@YA?AU_CHS_ADDRESS@@_K0@Z; DiskStructs::Utilities::ChsAddressFromLba(unsigned __int64,unsigned __int64)
0x1401117bb  movzx   ecx, word ptr [rax]
0x1401117be  mov     dl, [rax+2]
0x1401117c1  mov     [rdi+1C3h], cx
0x1401117c8  mov     [rdi+1C5h], dl
0x1401117ce  lea     r15, [r14-1]
0x1401117d2  mov     eax, 0FFFFFFFFh
0x1401117d7  cmp     r15, rax
0x1401117da  jnb     short loc_1401117DF
0x1401117dc  mov     eax, r15d
0x1401117df  mov     [rdi+1CAh], eax
0x1401117e5  mov     word ptr [rdi+1FEh], 0AA55h
0x1401117ee  mov     rcx, [rsi+8]
0x1401117f2  mov     rax, [rcx]
0x1401117f5  mov     [rsp+0C0h+var_98], r12
0x1401117fa  mov     [rsp+0C0h+var_A0], r13d
0x1401117ff  xor     r9d, r9d
0x140111802  mov     r8d, [rsi+20h]
0x140111806  mov     rdx, [rbp+57h+var_60]
0x14011180a  mov     rax, [rax+80h]
0x140111811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140111816  mov     rcx, [rbp+57h+var_60]; void *
0x14011181a  mov     r8, [rbp+57h+var_60+8]
0x14011181e  sub     r8, rcx; Size
0x140111821  xor     edx, edx; Val
0x140111823  call    memset_0
0x140111828  mov     ebx, [rsi+20h]
0x14011182b  lea     r12d, [rbx+3FFFh]
0x140111832  mov     eax, ebx
0x140111834  neg     eax
0x140111836  and     r12d, eax
0x140111839  xor     edx, edx
0x14011183b  mov     eax, r12d
0x14011183e  div     ebx
0x140111840  mov     r13d, eax
0x140111843  sub     r14, r13
0x140111846  lea     rdi, [r14-1]
0x14011184a  mov     rcx, [rsi+8]
0x14011184e  mov     rax, [rcx]
0x140111851  mov     rax, [rax+70h]
0x140111855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14011185a  xor     edx, edx
0x14011185c  div     ebx
0x14011185e  mov     ecx, eax
0x140111860  lea     r14, [r13+1]
0x140111864  add     r14, rcx
0x140111867  dec     rax
0x14011186a  not     rax
0x14011186d  and     r14, rax
0x140111870  xor     edx, edx
0x140111872  mov     rax, rdi
0x140111875  div     rcx
0x140111878  sub     rdi, rdx
0x14011187b  lea     rax, [rdi-1]
0x14011187f  mov     [rbp+57h+var_78], rax
0x140111883  mov     [rbp+57h+var_80], 0
0x140111887  mov     ebx, [rsi+20h]
0x14011188a  add     ebx, r12d
0x14011188d  mov     rdx, [rbp+57h+var_60]
0x140111891  mov     rdi, [rbp+57h+var_60+8]
0x140111895  mov     rcx, rdi
0x140111898  sub     rcx, rdx
0x14011189b  cmp     rbx, rcx
0x14011189e  jnb     short loc_1401118A6
0x1401118a0  lea     rax, [rbx+rdx]
0x1401118a4  jmp     short loc_1401118DA
0x1401118a6  jbe     short loc_1401118DE
0x1401118a8  mov     rax, [rbp+57h+var_50]
0x1401118ac  sub     rax, rdx
0x1401118af  cmp     rbx, rax
0x1401118b2  jbe     short loc_1401118C6
0x1401118b4  lea     r8, [rbp+57h+var_80]
0x1401118b8  mov     rdx, rbx
0x1401118bb  lea     rcx, [rbp+57h+var_60]
0x1401118bf  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x1401118c4  jmp     short loc_1401118DE
0x1401118c6  sub     rbx, rcx
0x1401118c9  mov     r8, rbx; Size
0x1401118cc  xor     edx, edx; Val
0x1401118ce  mov     rcx, rdi; void *
0x1401118d1  call    memset_0
0x1401118d6  lea     rax, [rbx+rdi]
0x1401118da  mov     [rbp+57h+var_60+8], rax
0x1401118de  mov     rdi, [rbp+57h+var_60]
0x1401118e2  mov     rax, 5452415020494645h
0x1401118ec  mov     [rdi], rax
0x1401118ef  mov     dword ptr [rdi+8], 10000h
0x1401118f6  mov     dword ptr [rdi+0Ch], 5Ch ; '\'
0x1401118fd  mov     qword ptr [rdi+18h], 1
0x140111905  mov     [rdi+20h], r15
0x140111909  mov     [rdi+28h], r14
0x14011190d  mov     rax, [rbp+57h+var_78]
0x140111911  mov     [rdi+30h], rax
0x140111915  xorps   xmm0, xmm0
0x140111918  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x14011191c  lea     rcx, [rbp+57h+Uuid]; Uuid
0x140111920  call    cs:__imp_UuidCreate
0x140111927  nop     dword ptr [rax+rax+00h]
0x14011192c  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x140111930  movdqu  xmmword ptr [rdi+38h], xmm0
0x140111935  mov     qword ptr [rdi+48h], 2
0x14011193d  mov     eax, 80h
0x140111942  mov     [rdi+50h], eax
0x140111945  mov     [rdi+54h], eax
0x140111948  mov     ebx, [rsi+20h]
0x14011194b  add     rbx, [rbp+57h+var_60]
0x14011194f  movups  xmm0, xmmword ptr cs:?GPT_PARTITION_TYPE_GUEST_STATE@@3U_GUID@@B.Data1; _GUID const GPT_PARTITION_TYPE_GUEST_STATE ...
0x140111956  movdqu  xmmword ptr [rbx], xmm0
0x14011195a  xorps   xmm0, xmm0
0x14011195d  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x140111961  lea     rcx, [rbp+57h+Uuid]; Uuid
0x140111965  call    cs:__imp_UuidCreate
0x14011196c  nop     dword ptr [rax+rax+00h]
0x140111971  movaps  xmm0, xmmword ptr [rbp+57h+Uuid.Data1]
0x140111975  movdqu  xmmword ptr [rbx+10h], xmm0
0x14011197a  mov     [rbx+20h], r14
0x14011197e  mov     rax, [rbp+57h+var_78]
0x140111982  mov     [rbx+28h], rax
0x140111986  lea     rcx, [rbx+38h]
0x14011198a  mov     r9d, 1Eh
0x140111990  lea     r8, ?GPT_PARTITION_NAME_GUEST_STATE@@3QBGB; "Guest Runtime State Partition"
0x140111997  lea     edx, [r9+6]
0x14011199b  call    cs:__imp__o_wcsncpy_s
0x1401119a2  nop     dword ptr [rax+rax+00h]
0x1401119a7  mov     r8d, r12d; unsigned int
0x1401119aa  mov     rdx, rbx; void *
0x1401119ad  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x1401119b2  mov     [rdi+58h], eax
0x1401119b5  mov     r8d, 5Ch ; '\'; unsigned int
0x1401119bb  mov     rdx, rdi; void *
0x1401119be  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x1401119c3  mov     [rdi+10h], eax
0x1401119c6  mov     rcx, [rsi+8]
0x1401119ca  mov     rdx, [rcx]
0x1401119cd  lea     r9d, [r13+1]
0x1401119d1  mov     r8d, [rsi+20h]
0x1401119d5  add     r8d, r12d
0x1401119d8  mov     rax, [rdx+80h]
0x1401119df  mov     [rsp+0C0h+var_98], 0
0x1401119e8  mov     [rsp+0C0h+var_A0], r9d
0x1401119ed  mov     r9d, 1
0x1401119f3  mov     rdx, [rbp+57h+var_60]
0x1401119f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1401119fc  mov     rbx, r15
0x1401119ff  sub     rbx, r13
0x140111a02  mov     rcx, [rdi+18h]; unsigned int
0x140111a06  mov     rax, [rdi+20h]
0x140111a0a  mov     [rdi+18h], rax
0x140111a0e  mov     [rdi+20h], rcx
0x140111a12  mov     [rdi+48h], rbx
0x140111a16  mov     r8d, 5Ch ; '\'; unsigned int
0x140111a1c  mov     rdx, rdi; void *
0x140111a1f  call    ?ComputeCrc32@@YAKKPEBXK@Z; ComputeCrc32(ulong,void const *,ulong)
0x140111a24  mov     [rdi+10h], eax
0x140111a27  mov     rcx, [rsi+8]
0x140111a2b  mov     rax, [rcx]
0x140111a2e  mov     [rsp+0C0h+var_98], 0
0x140111a37  mov     [rsp+0C0h+var_A0], 1
0x140111a3f  mov     r9, r15
0x140111a42  mov     r8d, [rsi+20h]
0x140111a46  mov     rdx, [rbp+57h+var_60]
0x140111a4a  mov     rax, [rax+80h]
0x140111a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140111a56  mov     rcx, [rsi+8]
0x140111a5a  mov     rax, [rcx]
0x140111a5d  mov     edx, [rsi+20h]
0x140111a60  add     rdx, [rbp+57h+var_60]
0x140111a64  mov     [rsp+0C0h+var_98], 0
0x140111a6d  mov     [rsp+0C0h+var_A0], r13d
0x140111a72  mov     r9, rbx
0x140111a75  mov     r8d, r12d
0x140111a78  mov     rax, [rax+80h]
0x140111a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140111a84  mov     [rsi+10h], r14
0x140111a88  mov     rax, [rbp+57h+var_78]
0x140111a8c  sub     rax, r14
0x140111a8f  inc     rax
0x140111a92  mov     [rsi+18h], rax
0x140111a96  lea     rcx, [rbp+57h+var_60]
0x140111a9a  call    ?_Tidy@?$vector@T_VID_VSM_MBP_PERMISSIONS@@V?$allocator@T_VID_VSM_MBP_PERMISSIONS@@@std@@@std@@AEAAXXZ; std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(void)
0x140111a9f  mov     rcx, [rbp+57h+var_48]
0x140111aa3  xor     rcx, rsp; StackCookie
0x140111aa6  call    __security_check_cookie
0x140111aab  add     rsp, 88h
0x140111ab2  pop     r15
0x140111ab4  pop     r14
0x140111ab6  pop     r13
0x140111ab8  pop     r12
0x140111aba  pop     rdi
0x140111abb  pop     rsi
0x140111abc  pop     rbx
0x140111abd  pop     rbp
0x140111abe  retn
```
