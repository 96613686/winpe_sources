# VMX_PHYSICAL_DISK::ReadToc(void)

- ea: `0x140032930`
- end: `0x14003309d`
- name: `?ReadToc@VMX_PHYSICAL_DISK@@AEAAXXZ`
- size: `1901`
- prototype: `void __fastcall(VMX_PHYSICAL_DISK *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14003261c`

## callees

- `0x140005f80`
- `0x140005fb0`
- `0x140009f54`
- `0x140009f7c`
- `0x140009fa4`
- `0x14001bb80`
- `0x14001be80`
- `0x140032930`
- `0x140043654`
- `0x140045c98`
- `0x140045ce0`
- `0x140045ddc`
- `0x1400465b0`
- `0x140046ac4`
- `0x140046dcc`
- `0x140047e38`
- `0x140048fa0`
- `0x14004a3c8`
- `0x14004a464`
- `0x14004a520`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140032a91`
- `ntoskrnl!ExAllocatePool2` at `0x140032aea`
- `ntoskrnl!ExAllocatePool2` at `0x140032a91`
- `ntoskrnl!ExAllocatePool2` at `0x140032aea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032e9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003306e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032e77`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032e9c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140033056`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003306e`
- `ntoskrnl!RtlCompareMemory` at `0x140032b90`
- `ntoskrnl!RtlCompareMemory` at `0x140032c4c`
- `ntoskrnl!RtlCompareMemory` at `0x140032ed5`
- `ntoskrnl!RtlCompareMemory` at `0x140032b90`
- `ntoskrnl!RtlCompareMemory` at `0x140032c4c`
- `ntoskrnl!RtlCompareMemory` at `0x140032ed5`

## pseudocode

```c
void __fastcall VMX_PHYSICAL_DISK::ReadToc(VMX_PHYSICAL_DISK *this)
{
  __int64 v1; // rax
  unsigned __int8 *v3; // r13
  _QWORD *v4; // rax
  unsigned int *v5; // rdi
  _QWORD *v6; // rax
  unsigned __int64 v7; // rdx
  __int64 v8; // r8
  int v9; // eax
  int v10; // ecx
  int v11; // eax
  int v12; // ecx
  __int64 v13; // rax
  unsigned __int64 v14; // r12
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // rax
  int v17; // ecx
  unsigned __int64 v18; // rax
  int v19; // ecx
  void *Pool2; // rax
  void *v21; // rbx
  const void *v22; // rdx
  __int64 v23; // rdx
  void *v24; // rax
  void *v25; // rbx
  const void *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  int Sectors; // eax
  unsigned __int8 *v30; // rsi
  int v31; // ebx
  unsigned int v32; // eax
  int v33; // r9d
  int v34; // eax
  void *v35; // r12
  unsigned int v36; // ebx
  unsigned __int8 *v37; // rcx
  unsigned int v38; // r8d
  __int64 v39; // rax
  unsigned __int64 v40; // r12
  unsigned __int64 v41; // rdx
  unsigned int *v42; // rax
  unsigned int *v43; // rbx
  unsigned __int64 v44; // rax
  unsigned __int64 v45; // r13
  struct VMX_TOC_ENTRY *v46; // rdx
  SIZE_T v47; // rax
  unsigned __int8 *v48; // rcx
  unsigned int v49; // eax
  int v50; // r9d
  VMX_CONFIG_COPY *v51; // rbx
  __int64 v52; // rsi
  VMX_CONFIG_COPY *v53; // rax
  VMX_LOG_COPY *v54; // rsi
  __int64 v55; // r15
  VMX_LOG_COPY *v56; // rax
  unsigned int v57; // edx
  void *Source1; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int8 *v59; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int64 v60; // [rsp+30h] [rbp-28h]
  _OWORD v61[2]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int Length; // [rsp+A0h] [rbp+48h]
  int v63; // [rsp+A8h] [rbp+50h]
  unsigned int v64; // [rsp+B0h] [rbp+58h]
  void *Source2; // [rsp+B8h] [rbp+60h] BYREF

  v1 = *((_QWORD *)this + 2);
  Source1 = 0;
  Source2 = 0;
  Length = *(_DWORD *)(v1 + 36);
  v3 = 0;
  v61[0] = 0;
  v4 = VMX_ALLOCATED_OBJECT::operator new(0x48u, 0x102u, 0x63546D56u);
  v5 = (unsigned int *)v4;
  if ( v4 )
  {
    *v4 = 0;
    v4[1] = 0;
    v4[2] = 0;
    v6 = v4 + 3;
    v6[1] = v6;
    *v6 = v6;
    *((_QWORD *)v5 + 6) = v5 + 10;
    *((_QWORD *)v5 + 5) = v5 + 10;
    *((_QWORD *)v5 + 8) = v5 + 14;
    *((_QWORD *)v5 + 7) = v5 + 14;
    if ( (int)VMX_BITMAP::SetCount((VMX_BITMAP *)v61, *(_DWORD *)(*((_QWORD *)this + 11) + 160LL)) < 0 )
      goto LABEL_65;
    v8 = *((_QWORD *)&v61[0] + 1);
    v7 = (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 11) + 24LL) >> 5;
    v9 = 1 << *(_DWORD *)(*((_QWORD *)this + 11) + 24LL);
    v10 = *(_DWORD *)(*((_QWORD *)&v61[0] + 1) + 4 * v7);
    if ( (v10 & v9) != 0
      || (*(_DWORD *)(*((_QWORD *)&v61[0] + 1) + 4 * v7) = v9 | v10,
          v7 = (unsigned __int64)*(unsigned int *)(*((_QWORD *)this + 11) + 32LL) >> 5,
          v11 = 1 << *(_DWORD *)(*((_QWORD *)this + 11) + 32LL),
          v12 = *(_DWORD *)(v8 + 4 * v7),
          (v12 & v11) != 0) )
    {
LABEL_65:
      VMX_TOC::`scalar deleting destructor'((VMX_TOC *)v5, v7);
    }
    else
    {
      *(_DWORD *)(v8 + 4 * v7) = v11 | v12;
      v13 = *((_QWORD *)this + 11);
      v14 = *(_QWORD *)(v13 + 168);
      v15 = *(_QWORD *)(v13 + 176);
      while ( v14 || v15 )
      {
        v16 = (unsigned __int64)(unsigned int)v14 >> 5;
        LODWORD(v7) = 1 << v14;
        v17 = *(_DWORD *)(v8 + 4 * v16);
        if ( (v17 & (1 << v14)) != 0 )
          goto LABEL_65;
        *(_DWORD *)(v8 + 4 * v16) = v7 | v17;
        LODWORD(v7) = 1 << v15;
        v18 = (unsigned __int64)(unsigned int)v15 >> 5;
        v19 = *(_DWORD *)(v8 + 4 * v18);
        if ( (v19 & (1 << v15)) != 0 )
          goto LABEL_65;
        *(_DWORD *)(v8 + 4 * v18) = v7 | v19;
        Pool2 = (void *)ExAllocatePool2(258, 8LL * (*v5 + 1), 538996054);
        v21 = Pool2;
        if ( !Pool2 )
          goto LABEL_65;
        v22 = (const void *)*((_QWORD *)v5 + 1);
        if ( v22 )
        {
          memmove(Pool2, v22, 8LL * *v5);
          ExFreePoolWithTag(*((PVOID *)v5 + 1), 0);
        }
        v23 = *v5 + 1;
        *((_QWORD *)v5 + 1) = v21;
        v24 = (void *)ExAllocatePool2(258, 8 * v23, 538996054);
        v25 = v24;
        if ( !v24 )
          goto LABEL_65;
        v26 = (const void *)*((_QWORD *)v5 + 2);
        if ( v26 )
        {
          memmove(v24, v26, 8LL * *v5);
          ExFreePoolWithTag(*((PVOID *)v5 + 2), 0);
        }
        v27 = *v5;
        v28 = *((_QWORD *)v5 + 1);
        *((_QWORD *)v5 + 2) = v25;
        *(_QWORD *)(v28 + 8 * v27) = v14;
        *(_QWORD *)(*((_QWORD *)v5 + 2) + 8LL * (*v5)++) = v15;
        Sectors = VMX_PHYSICAL_DISK::ReadSectors(
                    this,
                    v14 + *(_QWORD *)(*((_QWORD *)this + 11) + 152LL),
                    1u,
                    (unsigned __int8 **)&Source1);
        v30 = (unsigned __int8 *)Source1;
        v31 = Sectors;
        if ( Sectors >= 0 )
        {
          if ( RtlCompareMemory(Source1, &qword_14001FBE0, 8u) == 8
            && (v3 = v30 + 12,
                VmxpCheckSum(v30, 8u),
                v32 = VmxpCheckSum(v30 + 12, Length - 12),
                v32 + v33 + (v32 + v33) / 0xFFFFFFFF == (v30[11] | ((v30[10] | (((v30[8] << 8) | v30[9]) << 8)) << 8))) )
          {
            v3 = v30 + 20;
          }
          else
          {
            v31 = -1073741823;
          }
        }
        else if ( Sectors == -1073741670 )
        {
          goto LABEL_65;
        }
        v34 = VMX_PHYSICAL_DISK::ReadSectors(
                this,
                v15 + *(_QWORD *)(*((_QWORD *)this + 11) + 152LL),
                1u,
                (unsigned __int8 **)&Source2);
        v63 = v34;
        if ( v31 < 0 )
        {
          if ( v30 )
          {
            ExFreePoolWithTag(v30, 0);
            v34 = v63;
          }
          if ( v34 < 0 )
            goto LABEL_65;
          v30 = (unsigned __int8 *)Source2;
          Source1 = Source2;
          Source2 = 0;
          v47 = RtlCompareMemory(Source1, &qword_14001FBE0, 8u);
          v48 = v30;
          if ( v47 != 8 )
            goto LABEL_64;
          VmxpCheckSum(v30, 8u);
          v36 = Length;
          v49 = VmxpCheckSum(v30 + 12, Length - 12);
          if ( v49 + v50 + (v49 + v50) / 0xFFFFFFFF != (v30[11] | ((v30[10] | ((v30[9] | (v30[8] << 8)) << 8)) << 8)) )
            goto LABEL_62;
          v3 = v30 + 20;
          VMX_PHYSICAL_DISK::WriteSectors(this, v14 + *(_QWORD *)(*((_QWORD *)this + 11) + 152LL), 1u, v30);
        }
        else
        {
          v35 = Source2;
          if ( v34 < 0 || RtlCompareMemory(v30, Source2, Length) != Length )
            VMX_PHYSICAL_DISK::WriteSectors(this, v15 + *(_QWORD *)(*((_QWORD *)this + 11) + 152LL), 1u, v30);
          if ( v35 )
          {
            ExFreePoolWithTag(v35, 0);
            Source2 = 0;
          }
          v36 = Length;
        }
        v37 = v3 + 8;
        v38 = v3[8];
        v39 = v3[7];
        v40 = (v3[6]
             | ((v3[5] | ((v3[4] | ((v3[3] | ((v3[2] | ((v3[1] | ((unsigned __int64)*v3 << 8)) << 8)) << 8)) << 8)) << 8)) << 8)) << 8;
        v3 += 16;
        v14 = v39 | v40;
        v59 = v3;
        v41 = *(_QWORD *)(*((_QWORD *)this + 11) + 160LL);
        if ( v14 >= v41
          || (v15 = v37[7]
                  | ((v37[6]
                    | ((v37[5]
                      | ((v37[4] | ((v37[3] | ((v37[2] | ((((unsigned __int64)v38 << 8) | v37[1]) << 8)) << 8)) << 8)) << 8)) << 8)) << 8),
              v15 >= v41)
          || v14 == v15 && v14 )
        {
LABEL_62:
          v48 = v30;
LABEL_64:
          ExFreePoolWithTag(v48, 0);
          goto LABEL_65;
        }
        v60 = (unsigned __int64)&v30[v36];
        if ( (unsigned __int64)v3 < v60 )
        {
          while ( *v3 )
          {
            v42 = (unsigned int *)VMX_ALLOCATED_OBJECT::operator new(0x40u, 0x102u, 0x65546D56u);
            v43 = v42;
            if ( !v42 )
              goto LABEL_62;
            memset(v42, 0, 0x40u);
            if ( (int)VMX_TOC_ENTRY::Unformat((VMX_TOC_ENTRY *)v43, &v59, (int)v60 - (int)v3) < 0
              || (v44 = *((_QWORD *)v43 + 5), v44 > 0xFFFFFFFF)
              || (v45 = *((_QWORD *)v43 + 6), v45 > 0xFFFFFFFF)
              || v45 + v44 > 0xFFFFFFFF
              || (v64 = v43[10], VMX_BITMAP::CountResetBitsForward((VMX_BITMAP *)v61, v64, v45) < v45) )
            {
              ExFreePoolWithTag(v30, 0);
              VMX_ALLOCATED_OBJECT::operator delete(v43);
              goto LABEL_65;
            }
            VMX_BITMAP::SetBitsRange((VMX_BITMAP *)v61, v64, v45);
            VMX_TOC::InsertEntry((VMX_TOC *)v5, (struct VMX_TOC_ENTRY *)v43);
            if ( (int)VMX_TOC::InsertEntryInCopy((VMX_TOC *)v5, v46) < 0 )
              goto LABEL_62;
            v3 = v59;
            if ( (unsigned __int64)v59 >= v60 )
              break;
          }
        }
        ExFreePoolWithTag(v30, 0);
        v8 = *((_QWORD *)&v61[0] + 1);
      }
      if ( (int)VMX_TOC::CheckCopies((VMX_TOC *)v5) < 0 )
        goto LABEL_65;
      v51 = 0;
      v52 = *((_QWORD *)v5 + 5);
      if ( (unsigned int *)v52 != v5 + 10 && (*(_BYTE *)(*(_QWORD *)(v52 + 16) + 18LL) & 8) == 0 )
      {
        v53 = (VMX_CONFIG_COPY *)VMX_ALLOCATED_OBJECT::operator new(0x28u, 0x102u, 0x63436D56u);
        v51 = v53;
        if ( !v53 )
          goto LABEL_65;
        *((_QWORD *)v53 + 2) = 0;
        *((_QWORD *)v53 + 3) = 0;
        *((_QWORD *)v53 + 4) = 0;
        *(_QWORD *)v53 = this;
        *((_QWORD *)v53 + 1) = v52;
        VMX_CONFIG_COPY::ReadHeader(v53);
      }
      v54 = 0;
      v55 = *((_QWORD *)v5 + 7);
      if ( (unsigned int *)v55 != v5 + 14 && (*(_BYTE *)(*(_QWORD *)(v55 + 16) + 18LL) & 8) == 0 )
      {
        v56 = (VMX_LOG_COPY *)VMX_ALLOCATED_OBJECT::operator new(0x30u, 0x42u, 0x634C6D56u);
        v54 = v56;
        if ( !v56 )
          goto LABEL_65;
        *(_OWORD *)v56 = 0;
        *((_OWORD *)v56 + 1) = 0;
        *((_OWORD *)v56 + 2) = 0;
        if ( (int)VMX_LOG_COPY::Initialize(v56, this, (struct VMX_COPY *)v55) < 0 )
        {
          VMX_LOG_COPY::`scalar deleting destructor'(v54, v57);
          goto LABEL_65;
        }
      }
      *((_QWORD *)this + 12) = v5;
      *((_QWORD *)this + 13) = v51;
      *((_QWORD *)this + 14) = v54;
    }
  }
  VMX_BITMAP::~VMX_BITMAP((VMX_BITMAP *)v61);
}

```

## disassembly

```asm
0x140032930  push    rbp
0x140032932  push    rbx
0x140032933  push    rsi
0x140032934  push    rdi
0x140032935  push    r12
0x140032937  push    r13
0x140032939  push    r14
0x14003293b  push    r15
0x14003293d  mov     rbp, rsp
0x140032940  sub     rsp, 58h
0x140032944  mov     rax, [rcx+10h]
0x140032948  xor     esi, esi
0x14003294a  mov     r14, rcx
0x14003294d  mov     [rbp+Source1], rsi
0x140032951  xorps   xmm0, xmm0
0x140032954  mov     [rbp+Source2], rsi
0x140032958  mov     edx, 102h; unsigned __int64
0x14003295d  mov     r8d, 63546D56h; unsigned int
0x140032963  mov     ebx, [rax+24h]
0x140032966  lea     ecx, [rsi+48h]; unsigned __int64
0x140032969  mov     dword ptr [rbp+Length], ebx
0x14003296c  mov     r13d, esi
0x14003296f  movups  [rbp+var_20], xmm0
0x140032973  call    ??2VMX_ALLOCATED_OBJECT@@SAPEAX_K0K@Z; VMX_ALLOCATED_OBJECT::operator new(unsigned __int64,unsigned __int64,ulong)
0x140032978  mov     rdi, rax
0x14003297b  test    rax, rax
0x14003297e  jz      loc_140033082
0x140032984  mov     [rax], rsi
0x140032987  lea     rcx, [rbp+var_20]; this
0x14003298b  mov     [rax+8], rsi
0x14003298f  mov     [rax+10h], rsi
0x140032993  add     rax, 18h
0x140032997  mov     [rax+8], rax
0x14003299b  mov     [rax], rax
0x14003299e  lea     rax, [rdi+28h]
0x1400329a2  mov     [rax+8], rax
0x1400329a6  mov     [rax], rax
0x1400329a9  lea     rax, [rdi+38h]
0x1400329ad  mov     [rax+8], rax
0x1400329b1  mov     [rax], rax
0x1400329b4  mov     rdx, [r14+58h]
0x1400329b8  mov     edx, [rdx+0A0h]; unsigned int
0x1400329be  call    ?SetCount@VMX_BITMAP@@QEAAJK@Z; VMX_BITMAP::SetCount(ulong)
0x1400329c3  test    eax, eax
0x1400329c5  js      loc_14003307A
0x1400329cb  mov     rax, [r14+58h]
0x1400329cf  lea     r9d, [rsi+1]
0x1400329d3  mov     r8, qword ptr [rbp+var_20+8]
0x1400329d7  mov     edx, [rax+18h]
0x1400329da  mov     eax, r9d
0x1400329dd  mov     ecx, edx
0x1400329df  shr     rdx, 5
0x1400329e3  shl     eax, cl
0x1400329e5  mov     ecx, [r8+rdx*4]
0x1400329e9  test    eax, ecx
0x1400329eb  jnz     loc_14003307A
0x1400329f1  or      ecx, eax
0x1400329f3  mov     [r8+rdx*4], ecx
0x1400329f7  mov     rax, [r14+58h]
0x1400329fb  mov     edx, [rax+20h]
0x1400329fe  mov     eax, r9d
0x140032a01  mov     ecx, edx
0x140032a03  shr     rdx, 5
0x140032a07  shl     eax, cl
0x140032a09  mov     ecx, [r8+rdx*4]
0x140032a0d  test    eax, ecx
0x140032a0f  jnz     loc_14003307A
0x140032a15  or      ecx, eax
0x140032a17  mov     [r8+rdx*4], ecx
0x140032a1b  mov     rax, [r14+58h]
0x140032a1f  mov     r12, [rax+0A8h]
0x140032a26  mov     r15, [rax+0B0h]
0x140032a2d  test    r12, r12
0x140032a30  jnz     short loc_140032A3B
0x140032a32  test    r15, r15
0x140032a35  jz      loc_140032F70
0x140032a3b  mov     ecx, r12d
0x140032a3e  mov     eax, r12d
0x140032a41  shr     rax, 5
0x140032a45  mov     edx, r9d
0x140032a48  shl     edx, cl
0x140032a4a  mov     ecx, [r8+rax*4]
0x140032a4e  test    edx, ecx
0x140032a50  jnz     loc_14003307A
0x140032a56  or      ecx, edx
0x140032a58  mov     edx, r9d
0x140032a5b  mov     [r8+rax*4], ecx
0x140032a5f  mov     ecx, r15d
0x140032a62  shl     edx, cl
0x140032a64  mov     eax, r15d
0x140032a67  shr     rax, 5
0x140032a6b  mov     ecx, [r8+rax*4]
0x140032a6f  test    edx, ecx
0x140032a71  jnz     loc_14003307A
0x140032a77  or      ecx, edx
0x140032a79  mov     [r8+rax*4], ecx
0x140032a7d  mov     ecx, 102h
0x140032a82  mov     edx, [rdi]
0x140032a84  mov     r8d, 20206D56h
0x140032a8a  add     edx, r9d
0x140032a8d  shl     rdx, 3
0x140032a91  call    cs:__imp_ExAllocatePool2
0x140032a98  nop     dword ptr [rax+rax+00h]
0x140032a9d  mov     rbx, rax
0x140032aa0  test    rax, rax
0x140032aa3  jz      loc_14003307A
0x140032aa9  mov     rdx, [rdi+8]; Src
0x140032aad  test    rdx, rdx
0x140032ab0  jz      short loc_140032AD3
0x140032ab2  mov     r8d, [rdi]
0x140032ab5  mov     rcx, rax; void *
0x140032ab8  shl     r8, 3; Size
0x140032abc  call    memmove
0x140032ac1  mov     rcx, [rdi+8]; P
0x140032ac5  xor     edx, edx; Tag
0x140032ac7  call    cs:__imp_ExFreePoolWithTag
0x140032ace  nop     dword ptr [rax+rax+00h]
0x140032ad3  mov     edx, [rdi]
0x140032ad5  mov     ecx, 102h
0x140032ada  inc     edx
0x140032adc  mov     [rdi+8], rbx
0x140032ae0  shl     rdx, 3
0x140032ae4  mov     r8d, 20206D56h
0x140032aea  call    cs:__imp_ExAllocatePool2
0x140032af1  nop     dword ptr [rax+rax+00h]
0x140032af6  mov     rbx, rax
0x140032af9  test    rax, rax
0x140032afc  jz      loc_14003307A
0x140032b02  mov     rdx, [rdi+10h]; Src
0x140032b06  test    rdx, rdx
0x140032b09  jz      short loc_140032B2C
0x140032b0b  mov     r8d, [rdi]
0x140032b0e  mov     rcx, rax; void *
0x140032b11  shl     r8, 3; Size
0x140032b15  call    memmove
0x140032b1a  mov     rcx, [rdi+10h]; P
0x140032b1e  xor     edx, edx; Tag
0x140032b20  call    cs:__imp_ExFreePoolWithTag
0x140032b27  nop     dword ptr [rax+rax+00h]
0x140032b2c  mov     ecx, [rdi]
0x140032b2e  lea     r9, [rbp+Source1]; unsigned __int8 **
0x140032b32  mov     rax, [rdi+8]
0x140032b36  mov     r8d, 1; unsigned int
0x140032b3c  mov     [rdi+10h], rbx
0x140032b40  mov     [rax+rcx*8], r12
0x140032b44  mov     ecx, [rdi]
0x140032b46  mov     rax, [rdi+10h]
0x140032b4a  mov     [rax+rcx*8], r15
0x140032b4e  mov     rcx, r14; this
0x140032b51  inc     dword ptr [rdi]
0x140032b53  mov     rax, [r14+58h]
0x140032b57  mov     rdx, [rax+98h]
0x140032b5e  add     rdx, r12; unsigned __int64
0x140032b61  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x140032b66  mov     rsi, [rbp+Source1]
0x140032b6a  mov     ebx, eax
0x140032b6c  test    eax, eax
0x140032b6e  jns     short loc_140032B80
0x140032b70  cmp     eax, 0C000009Ah
0x140032b75  jz      loc_14003307A
0x140032b7b  jmp     loc_140032C0D
0x140032b80  mov     r8d, 8; Length
0x140032b86  lea     rdx, qword_14001FBE0; Source2
0x140032b8d  mov     rcx, rsi; Source1
0x140032b90  call    cs:__imp_RtlCompareMemory
0x140032b97  nop     dword ptr [rax+rax+00h]
0x140032b9c  cmp     rax, 8
0x140032ba0  jz      short loc_140032BA9
0x140032ba2  mov     ebx, 0C0000001h
0x140032ba7  jmp     short loc_140032C0D
0x140032ba9  mov     edx, 8; unsigned int
0x140032bae  lea     r13, [rsi+0Ch]
0x140032bb2  mov     rcx, rsi; unsigned __int8 *
0x140032bb5  call    ?VmxpCheckSum@@YAKPEAEK@Z; VmxpCheckSum(uchar *,ulong)
0x140032bba  mov     edx, dword ptr [rbp+Length]
0x140032bbd  lea     rcx, [rsi+0Ch]; unsigned __int8 *
0x140032bc1  add     edx, 0FFFFFFF4h; unsigned int
0x140032bc4  mov     r9d, eax
0x140032bc7  call    ?VmxpCheckSum@@YAKPEAEK@Z; VmxpCheckSum(uchar *,ulong)
0x140032bcc  movzx   r8d, byte ptr [rsi+9]
0x140032bd1  xor     edx, edx
0x140032bd3  lea     ecx, [rax+r9]
0x140032bd7  movzx   eax, byte ptr [rsi+8]
0x140032bdb  shl     eax, 8
0x140032bde  mov     r9d, 0FFFFFFFFh
0x140032be4  or      r8d, eax
0x140032be7  movzx   eax, byte ptr [rsi+0Ah]
0x140032beb  shl     r8d, 8
0x140032bef  or      r8d, eax
0x140032bf2  movzx   eax, byte ptr [rsi+0Bh]
0x140032bf6  shl     r8d, 8
0x140032bfa  or      r8d, eax
0x140032bfd  mov     eax, ecx
0x140032bff  div     r9d
0x140032c02  add     eax, ecx
0x140032c04  cmp     eax, r8d
0x140032c07  jnz     short loc_140032BA2
0x140032c09  lea     r13, [rsi+14h]
0x140032c0d  mov     rax, [r14+58h]
0x140032c11  lea     r9, [rbp+Source2]; unsigned __int8 **
0x140032c15  mov     r8d, 1; unsigned int
0x140032c1b  mov     rcx, r14; this
0x140032c1e  mov     rdx, [rax+98h]
0x140032c25  add     rdx, r15; unsigned __int64
0x140032c28  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x140032c2d  mov     [rbp+arg_8], eax
0x140032c30  test    ebx, ebx
0x140032c32  js      loc_140032E92
0x140032c38  mov     r12, [rbp+Source2]
0x140032c3c  test    eax, eax
0x140032c3e  js      short loc_140032C5D
0x140032c40  mov     ebx, dword ptr [rbp+Length]
0x140032c43  mov     rdx, r12; Source2
0x140032c46  mov     r8d, ebx; Length
0x140032c49  mov     rcx, rsi; Source1
0x140032c4c  call    cs:__imp_RtlCompareMemory
0x140032c53  nop     dword ptr [rax+rax+00h]
0x140032c58  cmp     rax, rbx
0x140032c5b  jz      short loc_140032C7C
0x140032c5d  mov     rax, [r14+58h]
0x140032c61  mov     r9, rsi; unsigned __int8 *
0x140032c64  mov     r8d, 1; unsigned int
0x140032c6a  mov     rcx, r14; this
0x140032c6d  mov     rdx, [rax+98h]
0x140032c74  add     rdx, r15; unsigned __int64
0x140032c77  call    ?WriteSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAE@Z; VMX_PHYSICAL_DISK::WriteSectors(unsigned __int64,ulong,uchar *)
0x140032c7c  test    r12, r12
0x140032c7f  jz      short loc_140032C9A
0x140032c81  xor     edx, edx; Tag
0x140032c83  mov     rcx, r12; P
0x140032c86  call    cs:__imp_ExFreePoolWithTag
0x140032c8d  nop     dword ptr [rax+rax+00h]
0x140032c92  mov     [rbp+Source2], 0
0x140032c9a  mov     ebx, dword ptr [rbp+Length]
0x140032c9d  movzx   eax, byte ptr [r13+1]
0x140032ca2  lea     rcx, [r13+8]
0x140032ca6  movzx   r12d, byte ptr [r13+0]
0x140032cab  movzx   r8d, byte ptr [r13+8]
0x140032cb0  shl     r12, 8
0x140032cb4  or      r12, rax
0x140032cb7  movzx   eax, byte ptr [r13+2]
0x140032cbc  shl     r12, 8
0x140032cc0  or      r12, rax
0x140032cc3  movzx   eax, byte ptr [r13+3]
0x140032cc8  shl     r12, 8
0x140032ccc  or      r12, rax
0x140032ccf  movzx   eax, byte ptr [r13+4]
0x140032cd4  shl     r12, 8
0x140032cd8  or      r12, rax
0x140032cdb  movzx   eax, byte ptr [r13+5]
0x140032ce0  shl     r12, 8
0x140032ce4  or      r12, rax
0x140032ce7  movzx   eax, byte ptr [r13+6]
0x140032cec  shl     r12, 8
0x140032cf0  or      r12, rax
0x140032cf3  movzx   eax, byte ptr [r13+7]
0x140032cf8  shl     r12, 8
0x140032cfc  add     r13, 10h
0x140032d00  or      r12, rax
0x140032d03  mov     [rbp+var_30], r13
0x140032d07  mov     rax, [r14+58h]
0x140032d0b  mov     rdx, [rax+0A0h]
0x140032d12  cmp     r12, rdx
0x140032d15  jnb     loc_14003304A
0x140032d1b  movzx   r15d, byte ptr [rcx+1]
0x140032d20  mov     eax, r8d
0x140032d23  shl     rax, 8
0x140032d27  or      r15, rax
0x140032d2a  movzx   eax, byte ptr [rcx+2]
0x140032d2e  shl     r15, 8
0x140032d32  or      r15, rax
0x140032d35  movzx   eax, byte ptr [rcx+3]
0x140032d39  shl     r15, 8
0x140032d3d  or      r15, rax
0x140032d40  movzx   eax, byte ptr [rcx+4]
0x140032d44  shl     r15, 8
0x140032d48  or      r15, rax
0x140032d4b  movzx   eax, byte ptr [rcx+5]
0x140032d4f  shl     r15, 8
0x140032d53  or      r15, rax
0x140032d56  movzx   eax, byte ptr [rcx+6]
0x140032d5a  shl     r15, 8
0x140032d5e  or      r15, rax
0x140032d61  movzx   eax, byte ptr [rcx+7]
0x140032d65  shl     r15, 8
0x140032d69  or      r15, rax
0x140032d6c  cmp     r15, rdx
0x140032d6f  jnb     loc_14003304A
0x140032d75  cmp     r12, r15
0x140032d78  jnz     short loc_140032D83
0x140032d7a  test    r12, r12
0x140032d7d  jnz     loc_14003304A
0x140032d83  mov     eax, ebx
0x140032d85  add     rax, rsi
0x140032d88  mov     [rbp+var_28], rax
0x140032d8c  cmp     r13, rax
0x140032d8f  jnb     loc_140032E72
0x140032d95  cmp     byte ptr [r13+0], 0
0x140032d9a  jz      loc_140032E72
0x140032da0  mov     edx, 102h; unsigned __int64
  ... truncated ...
```
