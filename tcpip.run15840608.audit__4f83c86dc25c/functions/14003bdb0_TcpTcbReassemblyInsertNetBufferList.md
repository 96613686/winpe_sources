# TcpTcbReassemblyInsertNetBufferList

- ea: `0x14003bdb0`
- end: `0x14003c5f3`
- name: `TcpTcbReassemblyInsertNetBufferList`
- size: `2115`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID Entry, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003ba40`

## callees

- `0x1400148e0`
- `0x140014974`
- `0x14003bdb0`
- `0x14003cd70`
- `0x14003d220`
- `0x14003d498`
- `0x14003da04`
- `0x14003dca0`
- `0x14003dd94`
- `0x1400fe2a0`
- `0x14015f5a4`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003c356`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003c356`
- `ntoskrnl!ExAllocatePool3` at `0x14003bf76`
- `ntoskrnl!ExAllocatePool3` at `0x14003bfa9`
- `ntoskrnl!ExAllocatePool3` at `0x14003c0fa`
- `ntoskrnl!ExAllocatePool3` at `0x14003c130`
- `ntoskrnl!ExAllocatePool3` at `0x14003bf76`
- `ntoskrnl!ExAllocatePool3` at `0x14003bfa9`
- `ntoskrnl!ExAllocatePool3` at `0x14003c0fa`
- `ntoskrnl!ExAllocatePool3` at `0x14003c130`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c5b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c5b5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14003bfe5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14003c16f`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14003bfe5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x14003c16f`

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
      if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) != 0 )
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
      if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) == 0 )
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
    if ( (BYTE2(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) == 0 )
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
0x14003bdb0  mov     [rsp+arg_0], rbx
0x14003bdb5  mov     [rsp+arg_10], r8d
0x14003bdba  mov     [rsp+arg_8], rdx
0x14003bdbf  push    rbp
0x14003bdc0  push    rsi
0x14003bdc1  push    rdi
0x14003bdc2  push    r12
0x14003bdc4  push    r13
0x14003bdc6  push    r14
0x14003bdc8  push    r15
0x14003bdca  sub     rsp, 80h
0x14003bdd1  mov     rdi, [rsp+0B8h+arg_20]
0x14003bdd9  mov     rbx, rcx
0x14003bddc  mov     rsi, [rsp+0B8h+Entry]
0x14003bde4  xor     cl, cl
0x14003bde6  xor     r14d, r14d
0x14003bde9  mov     ebp, r9d
0x14003bdec  mov     r15d, r8d
0x14003bdef  mov     r13d, 30h ; '0'
0x14003bdf5  mov     r9d, 18h
0x14003bdfb  test    rdi, rdi
0x14003bdfe  jz      short loc_14003BE0F
0x14003be00  mov     eax, [rdi+14h]
0x14003be03  add     eax, [rdi+18h]
0x14003be06  cmp     eax, r8d
0x14003be09  jz      loc_14003BEB7
0x14003be0f  movzx   r12d, [rsp+0B8h+arg_30]
0x14003be18  test    rsi, rsi
0x14003be1b  jnz     loc_14003C248
0x14003be21  test    cl, cl
0x14003be23  jz      loc_14003C040
0x14003be29  mov     rdx, [rbx+3A8h]
0x14003be30  xor     ecx, ecx
0x14003be32  mov     r8, [rdx+10h]
0x14003be36  mov     rax, r8
0x14003be39  test    r8, r8
0x14003be3c  jz      short loc_14003BE54
0x14003be3e  cmp     rax, rdi
0x14003be41  jnz     short loc_14003BEA9
0x14003be43  test    rcx, rcx
0x14003be46  jnz     loc_14003C23B
0x14003be4c  mov     rax, [r8+8]
0x14003be50  mov     [rdx+10h], rax
0x14003be54  cmp     dword ptr [rdi+18h], 0
0x14003be58  jz      short loc_14003BE74
0x14003be5a  mov     rax, [rbx+3A8h]
0x14003be61  mov     rcx, [rax+10h]
0x14003be65  mov     [rdi+8], rcx
0x14003be69  mov     rax, [rbx+3A8h]
0x14003be70  mov     [rax+10h], rdi
0x14003be74  mov     dl, 1
0x14003be76  mov     rcx, rbx
0x14003be79  call    TcpTcbSetReassembly
0x14003be7e  test    byte ptr [rbx+308h], 20h
0x14003be85  jnz     loc_14003C5C3
0x14003be8b  xor     eax, eax
0x14003be8d  mov     rbx, [rsp+0B8h+arg_0]
0x14003be95  add     rsp, 80h
0x14003be9c  pop     r15
0x14003be9e  pop     r14
0x14003bea0  pop     r13
0x14003bea2  pop     r12
0x14003bea4  pop     rdi
0x14003bea5  pop     rsi
0x14003bea6  pop     rbp
0x14003bea7  retn
0x14003bea9  mov     rcx, rax
0x14003beac  mov     rax, [rax+8]
0x14003beb0  test    rax, rax
0x14003beb3  jnz     short loc_14003BE3E
0x14003beb5  jmp     short loc_14003BE54
0x14003beb7  test    ebp, ebp
0x14003beb9  jz      loc_14003C02C
0x14003bebf  test    rsi, rsi
0x14003bec2  jnz     loc_14003C377
0x14003bec8  mov     rdx, cs:ReassemblySize
0x14003becf  mov     r12, rbp
0x14003bed2  mov     rcx, cs:ReassemblyLimit
0x14003bed9  lea     rax, [rdx+rbp]
0x14003bedd  cmp     rax, rcx
0x14003bee0  ja      loc_14003C580
0x14003bee6  mov     rax, rcx
0x14003bee9  shr     rax, 6
0x14003beed  cmp     rdx, rax
0x14003bef0  jnb     loc_14003C3AC
0x14003bef6  mov     r8d, r13d
0x14003bef9  mov     r14, [rbx+3A8h]
0x14003bf00  movzx   r15d, word ptr [r14+20h]
0x14003bf05  cmp     r15d, r8d
0x14003bf08  ja      loc_14003C40A
0x14003bf0e  mov     eax, [r14+1Ch]
0x14003bf12  inc     eax
0x14003bf14  cmp     eax, r8d
0x14003bf17  jbe     short loc_14003BF36
0x14003bf19  mov     eax, [r14+1Ch]
0x14003bf1d  lea     ecx, [rax+r15*2]
0x14003bf21  lea     eax, [rcx+rcx*2]
0x14003bf24  shl     eax, 5
0x14003bf27  add     eax, 0E0h
0x14003bf2c  cmp     [r14+18h], eax
0x14003bf30  jb      loc_14003C51E
0x14003bf36  mov     r15d, [rsp+0B8h+arg_10]
0x14003bf3e  lea     r9, [rsp+0B8h+var_58]
0x14003bf43  mov     [rsp+0B8h+var_60], 0
0x14003bf4c  mov     edx, 18h
0x14003bf51  mov     [rsp+0B8h+var_50], 0
0x14003bf5a  mov     ecx, 40h ; '@'
0x14003bf5f  mov     [rsp+0B8h+var_58], 1
0x14003bf68  mov     r8d, 48526354h
0x14003bf6e  mov     dword ptr [rsp+0B8h+var_98], 1
0x14003bf76  call    cs:__imp_ExAllocatePool3
0x14003bf7d  nop     dword ptr [rax+rax+00h]
0x14003bf82  mov     r14, rax
0x14003bf85  test    rax, rax
0x14003bf88  jz      loc_14003C576
0x14003bf8e  lea     r9, [rsp+0B8h+var_58]
0x14003bf93  mov     dword ptr [rsp+0B8h+var_98], 1
0x14003bf9b  mov     r8d, 42526354h
0x14003bfa1  mov     rdx, r12
0x14003bfa4  mov     ecx, 42h ; 'B'
0x14003bfa9  call    cs:__imp_ExAllocatePool3
0x14003bfb0  nop     dword ptr [rax+rax+00h]
0x14003bfb5  mov     [r14+10h], rax
0x14003bfb9  test    rax, rax
0x14003bfbc  jz      loc_14003C5AD
0x14003bfc2  mov     rcx, [rsp+0B8h+arg_8]
0x14003bfca  lea     r8, [rsp+0B8h+var_60]
0x14003bfcf  mov     [rsp+0B8h+var_98], r8
0x14003bfd4  mov     r9, r12
0x14003bfd7  mov     r8, rax
0x14003bfda  mov     rcx, [rcx+8]
0x14003bfde  mov     edx, [rcx+10h]
0x14003bfe1  mov     rcx, [rcx+8]
0x14003bfe5  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14003bfec  nop     dword ptr [rax+rax+00h]
0x14003bff1  mov     qword ptr [r14], 0
0x14003bff8  mov     [r14+8], ebp
0x14003bffc  mov     rax, [rdi+28h]
0x14003c000  mov     [rax], r14
0x14003c003  add     [rdi+18h], ebp
0x14003c006  mov     [rdi+28h], r14
0x14003c00a  mov     rax, [rbx+3A8h]
0x14003c011  add     [rax+18h], ebp
0x14003c014  lock add cs:ReassemblySize, r12
0x14003c01c  mov     rax, [rbx+3A8h]
0x14003c023  mov     r9d, 18h
0x14003c029  inc     dword ptr [rax+1Ch]
0x14003c02c  movzx   r12d, [rsp+0B8h+arg_30]
0x14003c035  mov     cl, 1
0x14003c037  or      [rdi+10h], r12b
0x14003c03b  jmp     loc_14003BE18
0x14003c040  mov     rdx, cs:ReassemblySize
0x14003c047  mov     rcx, cs:ReassemblyLimit
0x14003c04e  lea     rax, [rdx+rbp]
0x14003c052  cmp     rax, rcx
0x14003c055  ja      loc_14003C527
0x14003c05b  mov     rax, rcx
0x14003c05e  shr     rax, 6
0x14003c062  cmp     rdx, rax
0x14003c065  jnb     loc_14003C3F4
0x14003c06b  mov     r12, [rbx+3A8h]
0x14003c072  movzx   eax, word ptr [r12+20h]
0x14003c078  mov     [rsp+0B8h+var_68], eax
0x14003c07c  inc     eax
0x14003c07e  mov     dword ptr [rsp+0B8h+arg_20], eax
0x14003c085  cmp     eax, r13d
0x14003c088  ja      loc_14003C4E2
0x14003c08e  mov     eax, [r12+1Ch]
0x14003c093  inc     eax
0x14003c095  cmp     eax, r13d
0x14003c098  jbe     short loc_14003C0BC
0x14003c09a  mov     eax, [r12+1Ch]
0x14003c09f  mov     ecx, [rsp+0B8h+var_68]
0x14003c0a3  lea     ecx, [rax+rcx*2]
0x14003c0a6  lea     eax, [rcx+rcx*2]
0x14003c0a9  shl     eax, 5
0x14003c0ac  add     eax, 0E0h
0x14003c0b1  cmp     [r12+18h], eax
0x14003c0b6  jb      loc_14003C560
0x14003c0bc  xor     r13d, r13d
0x14003c0bf  test    ebp, ebp
0x14003c0c1  jz      loc_14003C3C2
0x14003c0c7  lea     r9, [rsp+0B8h+var_48]
0x14003c0cc  mov     [rsp+0B8h+arg_20], r13
0x14003c0d4  mov     edx, 18h
0x14003c0d9  mov     [rsp+0B8h+var_40], r13
0x14003c0de  mov     ecx, 40h ; '@'
0x14003c0e3  mov     [rsp+0B8h+var_48], 1
0x14003c0ec  mov     r8d, 48526354h
0x14003c0f2  mov     dword ptr [rsp+0B8h+var_98], 1
0x14003c0fa  call    cs:__imp_ExAllocatePool3
0x14003c101  nop     dword ptr [rax+rax+00h]
0x14003c106  mov     r14, rax
0x14003c109  test    rax, rax
0x14003c10c  jz      loc_14003C576
0x14003c112  lea     r9, [rsp+0B8h+var_48]
0x14003c117  mov     dword ptr [rsp+0B8h+var_98], 1
0x14003c11f  mov     r8d, 42526354h
0x14003c125  mov     rdx, rbp
0x14003c128  mov     ecx, 42h ; 'B'
0x14003c12d  mov     r12, rbp
0x14003c130  call    cs:__imp_ExAllocatePool3
0x14003c137  nop     dword ptr [rax+rax+00h]
0x14003c13c  mov     [r14+10h], rax
0x14003c140  test    rax, rax
0x14003c143  jz      loc_14003C5AD
0x14003c149  mov     rcx, [rsp+0B8h+arg_8]
0x14003c151  lea     r8, [rsp+0B8h+arg_20]
0x14003c159  mov     [rsp+0B8h+var_98], r8
0x14003c15e  mov     r9, rbp
0x14003c161  mov     r8, rax
0x14003c164  mov     rcx, [rcx+8]
0x14003c168  mov     edx, [rcx+10h]
0x14003c16b  mov     rcx, [rcx+8]
0x14003c16f  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x14003c176  nop     dword ptr [rax+rax+00h]
0x14003c17b  mov     [r14], r13
0x14003c17e  mov     [r14+8], ebp
0x14003c182  mov     rcx, cs:ReassemblyPool
0x14003c189  call    PplAllocateFromLookasideList
0x14003c18e  mov     rdx, rax
0x14003c191  test    rax, rax
0x14003c194  jz      loc_14003C571
0x14003c19a  mov     [rax+8], r13
0x14003c19e  mov     [rax+10h], r13d
0x14003c1a2  mov     [rax+1Ch], r13d
0x14003c1a6  mov     [rax+14h], r15d
0x14003c1aa  mov     [rax+18h], ebp
0x14003c1ad  mov     [rax+20h], r14
0x14003c1b1  mov     [rax+28h], r14
0x14003c1b5  movzx   eax, [rsp+0B8h+arg_30]
0x14003c1bd  or      [rdx+10h], al
0x14003c1c0  mov     [rdx], rsi
0x14003c1c3  test    rdi, rdi
0x14003c1c6  jnz     loc_14003C3A4
0x14003c1cc  mov     rax, [rbx+3A8h]
0x14003c1d3  mov     [rax], rdx
0x14003c1d6  mov     rax, [rbx+3A8h]
0x14003c1dd  add     [rax+18h], ebp
0x14003c1e0  lock add cs:ReassemblySize, r12
0x14003c1e8  test    r14, r14
0x14003c1eb  jz      short loc_14003C1F7
0x14003c1ed  mov     rax, [rbx+3A8h]
0x14003c1f4  inc     dword ptr [rax+1Ch]
0x14003c1f7  mov     rax, [rbx+3A8h]
0x14003c1fe  inc     word ptr [rax+20h]
0x14003c202  cmp     dword ptr [rdx+18h], 0
0x14003c206  jz      short loc_14003C222
0x14003c208  mov     rax, [rbx+3A8h]
0x14003c20f  mov     rcx, [rax+10h]
0x14003c213  mov     [rdx+8], rcx
0x14003c217  mov     rax, [rbx+3A8h]
0x14003c21e  mov     [rax+10h], rdx
0x14003c222  test    rsi, rsi
0x14003c225  jnz     loc_14003BE74
0x14003c22b  mov     rax, [rbx+3A8h]
0x14003c232  mov     [rax+8], rdx
0x14003c236  jmp     loc_14003BE74
0x14003c23b  mov     rax, [rdi+8]
0x14003c23f  mov     [rcx+8], rax
0x14003c243  jmp     loc_14003BE54
0x14003c248  lea     eax, [r15+rbp]
0x14003c24c  cmp     eax, [rsi+14h]
0x14003c24f  jnz     loc_14003BE21
0x14003c255  test    cl, cl
0x14003c257  jz      loc_14003C474
0x14003c25d  mov     rax, [rsi]
0x14003c260  mov     rcx, [rdi+28h]
0x14003c264  mov     [rdi], rax
0x14003c267  mov     rax, [rsi+20h]
0x14003c26b  mov     [rcx], rax
0x14003c26e  xor     ecx, ecx
0x14003c270  mov     rax, [rsi+28h]
0x14003c274  mov     [rdi+28h], rax
0x14003c278  mov     eax, [rsi+18h]
0x14003c27b  add     [rdi+18h], eax
0x14003c27e  movzx   eax, byte ptr [rsi+10h]
0x14003c282  or      [rdi+10h], al
0x14003c285  mov     rdx, [rbx+3A8h]
0x14003c28c  mov     r8, [rdx+10h]
0x14003c290  mov     rax, r8
0x14003c293  test    r8, r8
0x14003c296  jz      short loc_14003C2B2
0x14003c298  cmp     rax, rdi
0x14003c29b  jnz     loc_14003C3CA
0x14003c2a1  test    rcx, rcx
0x14003c2a4  jnz     loc_14003C504
0x14003c2aa  mov     rax, [r8+8]
0x14003c2ae  mov     [rdx+10h], rax
0x14003c2b2  mov     rdx, [rbx+3A8h]
0x14003c2b9  xor     ecx, ecx
0x14003c2bb  mov     r8, [rdx+10h]
0x14003c2bf  mov     rax, r8
0x14003c2c2  test    r8, r8
0x14003c2c5  jz      short loc_14003C2E1
0x14003c2c7  cmp     rax, rsi
0x14003c2ca  jnz     loc_14003C3DF
0x14003c2d0  test    rcx, rcx
0x14003c2d3  jnz     loc_14003C511
0x14003c2d9  mov     rax, [r8+8]
  ... truncated ...
```
