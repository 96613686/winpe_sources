# TcpTcbReassemblyInsertNetBufferList

- ea: `0x14008f7f0`
- end: `0x140090033`
- name: `TcpTcbReassemblyInsertNetBufferList`
- size: `2115`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID Entry, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008f480`

## callees

- `0x140053d70`
- `0x140053e04`
- `0x14008f7f0`
- `0x1400907b0`
- `0x140090c60`
- `0x140090ed8`
- `0x140091444`
- `0x1400916e0`
- `0x1400917d4`
- `0x1400f62b0`
- `0x14015d6d4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008fd96`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14008fd96`
- `ntoskrnl!ExAllocatePool3` at `0x14008f9b6`
- `ntoskrnl!ExAllocatePool3` at `0x14008f9e9`
- `ntoskrnl!ExAllocatePool3` at `0x14008fb3a`
- `ntoskrnl!ExAllocatePool3` at `0x14008fb70`
- `ntoskrnl!ExAllocatePool3` at `0x14008f9b6`
- `ntoskrnl!ExAllocatePool3` at `0x14008f9e9`
- `ntoskrnl!ExAllocatePool3` at `0x14008fb3a`
- `ntoskrnl!ExAllocatePool3` at `0x14008fb70`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fff5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008fff5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14008fa25`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14008fbaf`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14008fa25`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14008fbaf`

## pseudocode

```c
__int64 __fastcall TcpTcbReassemblyInsertNetBufferList(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        _DWORD *Entry,
        char a7)
{
  __int64 v7; // rdi
  _DWORD *v9; // rsi
  char v10; // cl
  _QWORD *Pool3; // r14
  unsigned __int64 v12; // rbp
  int v13; // r15d
  unsigned int v14; // r13d
  __int64 v15; // r9
  char v16; // r12
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // rax
  unsigned __int64 v22; // r12
  __int64 v23; // r14
  unsigned int v24; // r15d
  __int64 v25; // rax
  __int64 v26; // r12
  unsigned __int64 v27; // r12
  __int64 v28; // rax
  __int64 v29; // rax
  _QWORD *v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rax
  __int64 v35; // rdx
  _QWORD *v36; // rcx
  _QWORD *v37; // r8
  _QWORD *v38; // rax
  __int64 v39; // rax
  char *v40; // rcx
  char *v41; // rdi
  _QWORD *HeaderData; // rax
  unsigned __int8 v43; // al
  unsigned int v44; // eax
  __int64 v45; // rdx
  int v46; // [rsp+50h] [rbp-68h]
  __int64 v47; // [rsp+58h] [rbp-60h] BYREF
  _QWORD v48[2]; // [rsp+60h] [rbp-58h] BYREF
  _QWORD v49[9]; // [rsp+70h] [rbp-48h] BYREF
  int v51; // [rsp+D0h] [rbp+18h]

  v51 = a3;
  v7 = a5;
  v9 = Entry;
  v10 = 0;
  Pool3 = 0;
  v12 = a4;
  v13 = a3;
  v14 = 48;
  v15 = 24;
  if ( a5 && *(_DWORD *)(a5 + 24) + *(_DWORD *)(a5 + 20) == (_DWORD)a3 )
  {
    if ( !(_DWORD)v12 )
    {
LABEL_28:
      v16 = a7;
      v10 = 1;
      *(_BYTE *)(v7 + 16) |= a7;
      goto LABEL_4;
    }
    if ( Entry && (_DWORD)a3 + (_DWORD)v12 == Entry[5] )
    {
      if ( !(unsigned __int8)TcpTcbReassemblyCheckQuota(a1, 0xFFFFFFFFLL, a3, (unsigned int)v12) )
        return 3221225626LL;
      v22 = v12;
      goto LABEL_25;
    }
    v22 = v12;
    if ( ReassemblySize + v12 > ReassemblyLimit )
    {
      _InterlockedIncrement((_DWORD *)&SecurityRod + 1);
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 1) != 0 )
        McTemplateK0qqqqqq_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_REASSEMBLY_LIMIT_VIOLATION,
          a3,
          0,
          SBYTE4(SecurityRod),
          0,
          0,
          0,
          0);
      return 3221225626LL;
    }
    if ( ReassemblySize >= (unsigned __int64)ReassemblyLimit >> 6 )
    {
      a3 = 6;
      if ( ReassemblySize < (unsigned __int64)ReassemblyLimit >> 4 )
        a3 = 24;
    }
    else
    {
      a3 = 48;
    }
    v23 = *(_QWORD *)(a1 + 936);
    v24 = *(unsigned __int16 *)(v23 + 32);
    if ( v24 > (unsigned int)a3 )
    {
      if ( (unsigned __int16)v24 > (unsigned __int8)TcpComputeLogarithm(
                                                      *(unsigned int *)(a1 + 544),
                                                      ReassemblySize,
                                                      a3,
                                                      24) )
        goto LABEL_81;
    }
    else if ( *(_DWORD *)(v23 + 28) + 1 <= (unsigned int)a3 )
    {
LABEL_24:
      v13 = v51;
LABEL_25:
      v47 = 0;
      v48[1] = 0;
      v48[0] = 1;
      Pool3 = (_QWORD *)ExAllocatePool3(64, 24, 1213358932, v48, 1);
      if ( !Pool3 )
        return 3221225495LL;
      v25 = ExAllocatePool3(66, v22, 1112695636, v48, 1);
      Pool3[2] = v25;
      if ( !v25 )
        goto LABEL_101;
      RtlCopyMdlToKernelBuffer(
        *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
        *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL),
        v25,
        v22,
        &v47);
      *Pool3 = 0;
      *((_DWORD *)Pool3 + 2) = v12;
      **(_QWORD **)(v7 + 40) = Pool3;
      *(_DWORD *)(v7 + 24) += v12;
      *(_QWORD *)(v7 + 40) = Pool3;
      *(_DWORD *)(*(_QWORD *)(a1 + 936) + 24LL) += v12;
      _InterlockedAdd64(&ReassemblySize, v22);
      v15 = 24;
      ++*(_DWORD *)(*(_QWORD *)(a1 + 936) + 28LL);
      goto LABEL_28;
    }
    if ( *(_DWORD *)(v23 + 24) < 96 * (*(_DWORD *)(v23 + 28) + 2 * v24) + 224 && (int)v12 < 96 )
      goto LABEL_92;
    goto LABEL_24;
  }
  v16 = a7;
LABEL_4:
  if ( !v9 || v13 + (_DWORD)v12 != v9[5] )
  {
    if ( v10 )
    {
      v17 = *(_QWORD *)(a1 + 936);
      v18 = 0;
      v19 = *(_QWORD *)(v17 + 16);
      v20 = v19;
      if ( v19 )
      {
        while ( v20 != v7 )
        {
          v18 = v20;
          v20 = *(_QWORD *)(v20 + 8);
          if ( !v20 )
            goto LABEL_10;
        }
        if ( v18 )
          *(_QWORD *)(v18 + 8) = *(_QWORD *)(v7 + 8);
        else
          *(_QWORD *)(v17 + 16) = *(_QWORD *)(v19 + 8);
      }
LABEL_10:
      if ( *(_DWORD *)(v7 + 24) )
      {
        *(_QWORD *)(v7 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 936) + 16LL);
        *(_QWORD *)(*(_QWORD *)(a1 + 936) + 16LL) = v7;
      }
      goto LABEL_12;
    }
    if ( ReassemblySize + v12 <= ReassemblyLimit )
    {
      if ( ReassemblySize >= (unsigned __int64)ReassemblyLimit >> 6 )
      {
        v14 = 6;
        if ( ReassemblySize < (unsigned __int64)ReassemblyLimit >> 4 )
          v14 = 24;
      }
      v26 = *(_QWORD *)(a1 + 936);
      v46 = *(unsigned __int16 *)(v26 + 32);
      LODWORD(a5) = v46 + 1;
      if ( v46 + 1 <= v14 )
      {
        if ( *(_DWORD *)(v26 + 28) + 1 <= v14 )
        {
LABEL_34:
          if ( !(_DWORD)v12 )
          {
            v27 = v12;
            goto LABEL_38;
          }
          a5 = 0;
          v49[1] = 0;
          v49[0] = 1;
          Pool3 = (_QWORD *)ExAllocatePool3(64, 24, 1213358932, v49, 1);
          if ( !Pool3 )
            return 3221225495LL;
          v27 = v12;
          v28 = ExAllocatePool3(66, v12, 1112695636, v49, 1);
          Pool3[2] = v28;
          if ( v28 )
          {
            RtlCopyMdlToKernelBuffer(
              *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL),
              *(unsigned int *)(*(_QWORD *)(a2 + 8) + 16LL),
              v28,
              v12,
              &a5);
            *Pool3 = 0;
            *((_DWORD *)Pool3 + 2) = v12;
LABEL_38:
            v29 = PplAllocateFromLookasideList(ReassemblyPool);
            v17 = v29;
            if ( v29 )
            {
              *(_QWORD *)(v29 + 8) = 0;
              *(_DWORD *)(v29 + 16) = 0;
              *(_DWORD *)(v29 + 28) = 0;
              *(_DWORD *)(v29 + 20) = v13;
              *(_DWORD *)(v29 + 24) = v12;
              *(_QWORD *)(v29 + 32) = Pool3;
              *(_QWORD *)(v29 + 40) = Pool3;
              *(_BYTE *)(v29 + 16) |= a7;
              *(_QWORD *)v29 = v9;
              if ( v7 )
                *(_QWORD *)v7 = v29;
              else
                **(_QWORD **)(a1 + 936) = v29;
              *(_DWORD *)(*(_QWORD *)(a1 + 936) + 24LL) += v12;
              _InterlockedAdd64(&ReassemblySize, v27);
              if ( Pool3 )
                ++*(_DWORD *)(*(_QWORD *)(a1 + 936) + 28LL);
              ++*(_WORD *)(*(_QWORD *)(a1 + 936) + 32LL);
              if ( *(_DWORD *)(v29 + 24) )
              {
                *(_QWORD *)(v29 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 936) + 16LL);
                *(_QWORD *)(*(_QWORD *)(a1 + 936) + 16LL) = v29;
              }
              if ( !v9 )
                *(_QWORD *)(*(_QWORD *)(a1 + 936) + 8LL) = v29;
              goto LABEL_12;
            }
            if ( Pool3 )
              TcpTcbReassemblyFreeHeaderData(Pool3);
            return 3221225495LL;
          }
LABEL_101:
          ExFreePoolWithTag(Pool3, 0x48526354u);
          return 3221225495LL;
        }
        goto LABEL_33;
      }
      v43 = TcpComputeLogarithm(*(unsigned int *)(a1 + 544), ReassemblySize, a3, 24);
      if ( (unsigned int)a5 <= v43 )
      {
LABEL_33:
        if ( *(_DWORD *)(v26 + 24) >= (unsigned int)(96 * (*(_DWORD *)(v26 + 28) + 2 * v46) + 224) || (int)v12 >= 288 )
          goto LABEL_34;
      }
LABEL_81:
      _InterlockedIncrement((_DWORD *)&SecurityRod + 1);
      if ( (BYTE2(WPP_MAIN_CB.Reserved) & 1) == 0 )
        return 3221225626LL;
LABEL_82:
      McTemplateK0qqqqqq_EtwWriteTransfer(
        (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
        (unsigned int)TCP_REASSEMBLY_LIMIT_VIOLATION,
        a3,
        0,
        SBYTE4(SecurityRod),
        0,
        0,
        0,
        0);
      return 3221225626LL;
    }
LABEL_92:
    _InterlockedIncrement((_DWORD *)&SecurityRod + 1);
    if ( (BYTE2(WPP_MAIN_CB.Reserved) & 1) == 0 )
      return 3221225626LL;
    goto LABEL_82;
  }
  if ( v10 )
  {
    v30 = *(_QWORD **)(v7 + 40);
    *(_QWORD *)v7 = *(_QWORD *)v9;
    *v30 = *((_QWORD *)v9 + 4);
    v31 = 0;
    *(_QWORD *)(v7 + 40) = *((_QWORD *)v9 + 5);
    *(_DWORD *)(v7 + 24) += v9[6];
    *(_BYTE *)(v7 + 16) |= *((_BYTE *)v9 + 16);
    v32 = *(_QWORD *)(a1 + 936);
    v33 = *(_QWORD *)(v32 + 16);
    v34 = v33;
    if ( v33 )
    {
      while ( v34 != v7 )
      {
        v31 = v34;
        v34 = *(_QWORD *)(v34 + 8);
        if ( !v34 )
          goto LABEL_54;
      }
      if ( v31 )
        *(_QWORD *)(v31 + 8) = *(_QWORD *)(v7 + 8);
      else
        *(_QWORD *)(v32 + 16) = *(_QWORD *)(v33 + 8);
    }
LABEL_54:
    v35 = *(_QWORD *)(a1 + 936);
    v36 = 0;
    v37 = *(_QWORD **)(v35 + 16);
    v38 = v37;
    if ( v37 )
    {
      while ( v38 != (_QWORD *)v9 )
      {
        v36 = v38;
        v38 = (_QWORD *)v38[1];
        if ( !v38 )
          goto LABEL_58;
      }
      if ( v36 )
        v36[1] = *((_QWORD *)v9 + 1);
      else
        *(_QWORD *)(v35 + 16) = v37[1];
    }
LABEL_58:
    if ( *(_DWORD *)(v7 + 24) )
    {
      *(_QWORD *)(v7 + 8) = *(_QWORD *)(*(_QWORD *)(a1 + 936) + 16LL);
      *(_QWORD *)(*(_QWORD *)(a1 + 936) + 16LL) = v7;
    }
    v39 = *(_QWORD *)(a1 + 936);
    if ( *(_DWORD **)(v39 + 8) == v9 )
      *(_QWORD *)(v39 + 8) = v7;
    v40 = (char *)ReassemblyPool;
    *((_QWORD *)v9 + 5) = 0;
    *((_QWORD *)v9 + 4) = 0;
    v41 = &v40[128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1)];
    if ( !v41[176] )
      PplpLazyInitializeLookasideList(v40, v41 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v41 + 64), v9);
    --*(_WORD *)(*(_QWORD *)(a1 + 936) + 32LL);
    goto LABEL_12;
  }
  if ( !(unsigned __int8)TcpTcbReassemblyCheckQuota(a1, 0, a3, (unsigned int)v12) )
    return 3221225626LL;
  HeaderData = (_QWORD *)TcpTcbReassemblyAllocateHeaderData(a2, (unsigned int)v12);
  if ( !HeaderData )
    return 3221225495LL;
  *HeaderData = *((_QWORD *)v9 + 4);
  v9[6] += v12;
  *((_BYTE *)v9 + 16) |= v16;
  *((_QWORD *)v9 + 4) = HeaderData;
  v9[5] = v13;
  *(_DWORD *)(*(_QWORD *)(a1 + 936) + 24LL) += v12;
  _InterlockedAdd64(&ReassemblySize, v12);
  ++*(_DWORD *)(*(_QWORD *)(a1 + 936) + 28LL);
  TcpTcbReassemblyReinsertSackBlock(a1, v9);
LABEL_12:
  LOBYTE(v17) = 1;
  TcpTcbSetReassembly(a1, v17, v19, v15);
  if ( (*(_BYTE *)(a1 + 776) & 0x20) != 0 )
  {
    v44 = TcpTcbTotalReassembly(a1);
    v45 = *(_QWORD *)(*(_QWORD *)(a1 + 928) + 40LL);
    if ( *(_DWORD *)(v45 + 32) < v44 )
      *(_DWORD *)(v45 + 32) = v44;
  }
  return 0;
}

```

## disassembly

```asm
0x14008f7f0  mov     [rsp+arg_0], rbx
0x14008f7f5  mov     [rsp+arg_10], r8d
0x14008f7fa  mov     [rsp+arg_8], rdx
0x14008f7ff  push    rbp
0x14008f800  push    rsi
0x14008f801  push    rdi
0x14008f802  push    r12
0x14008f804  push    r13
0x14008f806  push    r14
0x14008f808  push    r15
0x14008f80a  sub     rsp, 80h
0x14008f811  mov     rdi, [rsp+0B8h+arg_20]
0x14008f819  mov     rbx, rcx
0x14008f81c  mov     rsi, [rsp+0B8h+Entry]
0x14008f824  xor     cl, cl
0x14008f826  xor     r14d, r14d
0x14008f829  mov     ebp, r9d
0x14008f82c  mov     r15d, r8d
0x14008f82f  mov     r13d, 30h ; '0'
0x14008f835  mov     r9d, 18h
0x14008f83b  test    rdi, rdi
0x14008f83e  jz      short loc_14008F84F
0x14008f840  mov     eax, [rdi+14h]
0x14008f843  add     eax, [rdi+18h]
0x14008f846  cmp     eax, r8d
0x14008f849  jz      loc_14008F8F7
0x14008f84f  movzx   r12d, [rsp+0B8h+arg_30]
0x14008f858  test    rsi, rsi
0x14008f85b  jnz     loc_14008FC88
0x14008f861  test    cl, cl
0x14008f863  jz      loc_14008FA80
0x14008f869  mov     rdx, [rbx+3A8h]
0x14008f870  xor     ecx, ecx
0x14008f872  mov     r8, [rdx+10h]
0x14008f876  mov     rax, r8
0x14008f879  test    r8, r8
0x14008f87c  jz      short loc_14008F894
0x14008f87e  cmp     rax, rdi
0x14008f881  jnz     short loc_14008F8E9
0x14008f883  test    rcx, rcx
0x14008f886  jnz     loc_14008FC7B
0x14008f88c  mov     rax, [r8+8]
0x14008f890  mov     [rdx+10h], rax
0x14008f894  cmp     dword ptr [rdi+18h], 0
0x14008f898  jz      short loc_14008F8B4
0x14008f89a  mov     rax, [rbx+3A8h]
0x14008f8a1  mov     rcx, [rax+10h]
0x14008f8a5  mov     [rdi+8], rcx
0x14008f8a9  mov     rax, [rbx+3A8h]
0x14008f8b0  mov     [rax+10h], rdi
0x14008f8b4  mov     dl, 1
0x14008f8b6  mov     rcx, rbx
0x14008f8b9  call    TcpTcbSetReassembly
0x14008f8be  test    byte ptr [rbx+308h], 20h
0x14008f8c5  jnz     loc_140090003
0x14008f8cb  xor     eax, eax
0x14008f8cd  mov     rbx, [rsp+0B8h+arg_0]
0x14008f8d5  add     rsp, 80h
0x14008f8dc  pop     r15
0x14008f8de  pop     r14
0x14008f8e0  pop     r13
0x14008f8e2  pop     r12
0x14008f8e4  pop     rdi
0x14008f8e5  pop     rsi
0x14008f8e6  pop     rbp
0x14008f8e7  retn
0x14008f8e9  mov     rcx, rax
0x14008f8ec  mov     rax, [rax+8]
0x14008f8f0  test    rax, rax
0x14008f8f3  jnz     short loc_14008F87E
0x14008f8f5  jmp     short loc_14008F894
0x14008f8f7  test    ebp, ebp
0x14008f8f9  jz      loc_14008FA6C
0x14008f8ff  test    rsi, rsi
0x14008f902  jnz     loc_14008FDB7
0x14008f908  mov     rdx, cs:ReassemblySize
0x14008f90f  mov     r12, rbp
0x14008f912  mov     rcx, cs:ReassemblyLimit
0x14008f919  lea     rax, [rdx+rbp]
0x14008f91d  cmp     rax, rcx
0x14008f920  ja      loc_14008FFC0
0x14008f926  mov     rax, rcx
0x14008f929  shr     rax, 6
0x14008f92d  cmp     rdx, rax
0x14008f930  jnb     loc_14008FDEC
0x14008f936  mov     r8d, r13d
0x14008f939  mov     r14, [rbx+3A8h]
0x14008f940  movzx   r15d, word ptr [r14+20h]
0x14008f945  cmp     r15d, r8d
0x14008f948  ja      loc_14008FE4A
0x14008f94e  mov     eax, [r14+1Ch]
0x14008f952  inc     eax
0x14008f954  cmp     eax, r8d
0x14008f957  jbe     short loc_14008F976
0x14008f959  mov     eax, [r14+1Ch]
0x14008f95d  lea     ecx, [rax+r15*2]
0x14008f961  lea     eax, [rcx+rcx*2]
0x14008f964  shl     eax, 5
0x14008f967  add     eax, 0E0h
0x14008f96c  cmp     [r14+18h], eax
0x14008f970  jb      loc_14008FF5E
0x14008f976  mov     r15d, [rsp+0B8h+arg_10]
0x14008f97e  lea     r9, [rsp+0B8h+var_58]
0x14008f983  mov     [rsp+0B8h+var_60], 0
0x14008f98c  mov     edx, 18h
0x14008f991  mov     [rsp+0B8h+var_50], 0
0x14008f99a  mov     ecx, 40h ; '@'
0x14008f99f  mov     [rsp+0B8h+var_58], 1
0x14008f9a8  mov     r8d, 48526354h
0x14008f9ae  mov     dword ptr [rsp+0B8h+var_98], 1
0x14008f9b6  call    cs:__imp_ExAllocatePool3
0x14008f9bd  nop     dword ptr [rax+rax+00h]
0x14008f9c2  mov     r14, rax
0x14008f9c5  test    rax, rax
0x14008f9c8  jz      loc_14008FFB6
0x14008f9ce  lea     r9, [rsp+0B8h+var_58]
0x14008f9d3  mov     dword ptr [rsp+0B8h+var_98], 1
0x14008f9db  mov     r8d, 42526354h
0x14008f9e1  mov     rdx, r12
0x14008f9e4  mov     ecx, 42h ; 'B'
0x14008f9e9  call    cs:__imp_ExAllocatePool3
0x14008f9f0  nop     dword ptr [rax+rax+00h]
0x14008f9f5  mov     [r14+10h], rax
0x14008f9f9  test    rax, rax
0x14008f9fc  jz      loc_14008FFED
0x14008fa02  mov     rcx, [rsp+0B8h+arg_8]
0x14008fa0a  lea     r8, [rsp+0B8h+var_60]
0x14008fa0f  mov     [rsp+0B8h+var_98], r8
0x14008fa14  mov     r9, r12
0x14008fa17  mov     r8, rax
0x14008fa1a  mov     rcx, [rcx+8]
0x14008fa1e  mov     edx, [rcx+10h]
0x14008fa21  mov     rcx, [rcx+8]
0x14008fa25  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14008fa2c  nop     dword ptr [rax+rax+00h]
0x14008fa31  mov     qword ptr [r14], 0
0x14008fa38  mov     [r14+8], ebp
0x14008fa3c  mov     rax, [rdi+28h]
0x14008fa40  mov     [rax], r14
0x14008fa43  add     [rdi+18h], ebp
0x14008fa46  mov     [rdi+28h], r14
0x14008fa4a  mov     rax, [rbx+3A8h]
0x14008fa51  add     [rax+18h], ebp
0x14008fa54  lock add cs:ReassemblySize, r12
0x14008fa5c  mov     rax, [rbx+3A8h]
0x14008fa63  mov     r9d, 18h
0x14008fa69  inc     dword ptr [rax+1Ch]
0x14008fa6c  movzx   r12d, [rsp+0B8h+arg_30]
0x14008fa75  mov     cl, 1
0x14008fa77  or      [rdi+10h], r12b
0x14008fa7b  jmp     loc_14008F858
0x14008fa80  mov     rdx, cs:ReassemblySize
0x14008fa87  mov     rcx, cs:ReassemblyLimit
0x14008fa8e  lea     rax, [rdx+rbp]
0x14008fa92  cmp     rax, rcx
0x14008fa95  ja      loc_14008FF67
0x14008fa9b  mov     rax, rcx
0x14008fa9e  shr     rax, 6
0x14008faa2  cmp     rdx, rax
0x14008faa5  jnb     loc_14008FE34
0x14008faab  mov     r12, [rbx+3A8h]
0x14008fab2  movzx   eax, word ptr [r12+20h]
0x14008fab8  mov     [rsp+0B8h+var_68], eax
0x14008fabc  inc     eax
0x14008fabe  mov     dword ptr [rsp+0B8h+arg_20], eax
0x14008fac5  cmp     eax, r13d
0x14008fac8  ja      loc_14008FF22
0x14008face  mov     eax, [r12+1Ch]
0x14008fad3  inc     eax
0x14008fad5  cmp     eax, r13d
0x14008fad8  jbe     short loc_14008FAFC
0x14008fada  mov     eax, [r12+1Ch]
0x14008fadf  mov     ecx, [rsp+0B8h+var_68]
0x14008fae3  lea     ecx, [rax+rcx*2]
0x14008fae6  lea     eax, [rcx+rcx*2]
0x14008fae9  shl     eax, 5
0x14008faec  add     eax, 0E0h
0x14008faf1  cmp     [r12+18h], eax
0x14008faf6  jb      loc_14008FFA0
0x14008fafc  xor     r13d, r13d
0x14008faff  test    ebp, ebp
0x14008fb01  jz      loc_14008FE02
0x14008fb07  lea     r9, [rsp+0B8h+var_48]
0x14008fb0c  mov     [rsp+0B8h+arg_20], r13
0x14008fb14  mov     edx, 18h
0x14008fb19  mov     [rsp+0B8h+var_40], r13
0x14008fb1e  mov     ecx, 40h ; '@'
0x14008fb23  mov     [rsp+0B8h+var_48], 1
0x14008fb2c  mov     r8d, 48526354h
0x14008fb32  mov     dword ptr [rsp+0B8h+var_98], 1
0x14008fb3a  call    cs:__imp_ExAllocatePool3
0x14008fb41  nop     dword ptr [rax+rax+00h]
0x14008fb46  mov     r14, rax
0x14008fb49  test    rax, rax
0x14008fb4c  jz      loc_14008FFB6
0x14008fb52  lea     r9, [rsp+0B8h+var_48]
0x14008fb57  mov     dword ptr [rsp+0B8h+var_98], 1
0x14008fb5f  mov     r8d, 42526354h
0x14008fb65  mov     rdx, rbp
0x14008fb68  mov     ecx, 42h ; 'B'
0x14008fb6d  mov     r12, rbp
0x14008fb70  call    cs:__imp_ExAllocatePool3
0x14008fb77  nop     dword ptr [rax+rax+00h]
0x14008fb7c  mov     [r14+10h], rax
0x14008fb80  test    rax, rax
0x14008fb83  jz      loc_14008FFED
0x14008fb89  mov     rcx, [rsp+0B8h+arg_8]
0x14008fb91  lea     r8, [rsp+0B8h+arg_20]
0x14008fb99  mov     [rsp+0B8h+var_98], r8
0x14008fb9e  mov     r9, rbp
0x14008fba1  mov     r8, rax
0x14008fba4  mov     rcx, [rcx+8]
0x14008fba8  mov     edx, [rcx+10h]
0x14008fbab  mov     rcx, [rcx+8]
0x14008fbaf  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14008fbb6  nop     dword ptr [rax+rax+00h]
0x14008fbbb  mov     [r14], r13
0x14008fbbe  mov     [r14+8], ebp
0x14008fbc2  mov     rcx, cs:ReassemblyPool
0x14008fbc9  call    PplAllocateFromLookasideList
0x14008fbce  mov     rdx, rax
0x14008fbd1  test    rax, rax
0x14008fbd4  jz      loc_14008FFB1
0x14008fbda  mov     [rax+8], r13
0x14008fbde  mov     [rax+10h], r13d
0x14008fbe2  mov     [rax+1Ch], r13d
0x14008fbe6  mov     [rax+14h], r15d
0x14008fbea  mov     [rax+18h], ebp
0x14008fbed  mov     [rax+20h], r14
0x14008fbf1  mov     [rax+28h], r14
0x14008fbf5  movzx   eax, [rsp+0B8h+arg_30]
0x14008fbfd  or      [rdx+10h], al
0x14008fc00  mov     [rdx], rsi
0x14008fc03  test    rdi, rdi
0x14008fc06  jnz     loc_14008FDE4
0x14008fc0c  mov     rax, [rbx+3A8h]
0x14008fc13  mov     [rax], rdx
0x14008fc16  mov     rax, [rbx+3A8h]
0x14008fc1d  add     [rax+18h], ebp
0x14008fc20  lock add cs:ReassemblySize, r12
0x14008fc28  test    r14, r14
0x14008fc2b  jz      short loc_14008FC37
0x14008fc2d  mov     rax, [rbx+3A8h]
0x14008fc34  inc     dword ptr [rax+1Ch]
0x14008fc37  mov     rax, [rbx+3A8h]
0x14008fc3e  inc     word ptr [rax+20h]
0x14008fc42  cmp     dword ptr [rdx+18h], 0
0x14008fc46  jz      short loc_14008FC62
0x14008fc48  mov     rax, [rbx+3A8h]
0x14008fc4f  mov     rcx, [rax+10h]
0x14008fc53  mov     [rdx+8], rcx
0x14008fc57  mov     rax, [rbx+3A8h]
0x14008fc5e  mov     [rax+10h], rdx
0x14008fc62  test    rsi, rsi
0x14008fc65  jnz     loc_14008F8B4
0x14008fc6b  mov     rax, [rbx+3A8h]
0x14008fc72  mov     [rax+8], rdx
0x14008fc76  jmp     loc_14008F8B4
0x14008fc7b  mov     rax, [rdi+8]
0x14008fc7f  mov     [rcx+8], rax
0x14008fc83  jmp     loc_14008F894
0x14008fc88  lea     eax, [r15+rbp]
0x14008fc8c  cmp     eax, [rsi+14h]
0x14008fc8f  jnz     loc_14008F861
0x14008fc95  test    cl, cl
0x14008fc97  jz      loc_14008FEB4
0x14008fc9d  mov     rax, [rsi]
0x14008fca0  mov     rcx, [rdi+28h]
0x14008fca4  mov     [rdi], rax
0x14008fca7  mov     rax, [rsi+20h]
0x14008fcab  mov     [rcx], rax
0x14008fcae  xor     ecx, ecx
0x14008fcb0  mov     rax, [rsi+28h]
0x14008fcb4  mov     [rdi+28h], rax
0x14008fcb8  mov     eax, [rsi+18h]
0x14008fcbb  add     [rdi+18h], eax
0x14008fcbe  movzx   eax, byte ptr [rsi+10h]
0x14008fcc2  or      [rdi+10h], al
0x14008fcc5  mov     rdx, [rbx+3A8h]
0x14008fccc  mov     r8, [rdx+10h]
0x14008fcd0  mov     rax, r8
0x14008fcd3  test    r8, r8
0x14008fcd6  jz      short loc_14008FCF2
0x14008fcd8  cmp     rax, rdi
0x14008fcdb  jnz     loc_14008FE0A
0x14008fce1  test    rcx, rcx
0x14008fce4  jnz     loc_14008FF44
0x14008fcea  mov     rax, [r8+8]
0x14008fcee  mov     [rdx+10h], rax
0x14008fcf2  mov     rdx, [rbx+3A8h]
0x14008fcf9  xor     ecx, ecx
0x14008fcfb  mov     r8, [rdx+10h]
0x14008fcff  mov     rax, r8
0x14008fd02  test    r8, r8
0x14008fd05  jz      short loc_14008FD21
0x14008fd07  cmp     rax, rsi
0x14008fd0a  jnz     loc_14008FE1F
0x14008fd10  test    rcx, rcx
0x14008fd13  jnz     loc_14008FF51
0x14008fd19  mov     rax, [r8+8]
  ... truncated ...
```
