# TcpTcbReassemblyInsertNetBufferList

- ea: `0x1400906a0`
- end: `0x140090ee3`
- name: `TcpTcbReassemblyInsertNetBufferList`
- size: `2115`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, PVOID Entry, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140090330`

## callees

- `0x140054010`
- `0x1400540a4`
- `0x1400906a0`
- `0x140091660`
- `0x140091b10`
- `0x140091d88`
- `0x1400922f4`
- `0x140092590`
- `0x140092684`
- `0x1400f61a0`
- `0x14015d814`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140090c46`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140090c46`
- `ntoskrnl!ExAllocatePool3` at `0x140090866`
- `ntoskrnl!ExAllocatePool3` at `0x140090899`
- `ntoskrnl!ExAllocatePool3` at `0x1400909ea`
- `ntoskrnl!ExAllocatePool3` at `0x140090a20`
- `ntoskrnl!ExAllocatePool3` at `0x140090866`
- `ntoskrnl!ExAllocatePool3` at `0x140090899`
- `ntoskrnl!ExAllocatePool3` at `0x1400909ea`
- `ntoskrnl!ExAllocatePool3` at `0x140090a20`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090ea5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090ea5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400908d5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140090a5f`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x1400908d5`
- `NETIO!RtlCopyMdlToKernelBuffer` at `0x140090a5f`

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
          (unsigned int)&TCP_REASSEMBLY_LIMIT_VIOLATION,
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
        (unsigned int)&TCP_REASSEMBLY_LIMIT_VIOLATION,
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
0x1400906a0  mov     [rsp+arg_0], rbx
0x1400906a5  mov     [rsp+arg_10], r8d
0x1400906aa  mov     [rsp+arg_8], rdx
0x1400906af  push    rbp
0x1400906b0  push    rsi
0x1400906b1  push    rdi
0x1400906b2  push    r12
0x1400906b4  push    r13
0x1400906b6  push    r14
0x1400906b8  push    r15
0x1400906ba  sub     rsp, 80h
0x1400906c1  mov     rdi, [rsp+0B8h+arg_20]
0x1400906c9  mov     rbx, rcx
0x1400906cc  mov     rsi, [rsp+0B8h+Entry]
0x1400906d4  xor     cl, cl
0x1400906d6  xor     r14d, r14d
0x1400906d9  mov     ebp, r9d
0x1400906dc  mov     r15d, r8d
0x1400906df  mov     r13d, 30h ; '0'
0x1400906e5  mov     r9d, 18h
0x1400906eb  test    rdi, rdi
0x1400906ee  jz      short loc_1400906FF
0x1400906f0  mov     eax, [rdi+14h]
0x1400906f3  add     eax, [rdi+18h]
0x1400906f6  cmp     eax, r8d
0x1400906f9  jz      loc_1400907A7
0x1400906ff  movzx   r12d, [rsp+0B8h+arg_30]
0x140090708  test    rsi, rsi
0x14009070b  jnz     loc_140090B38
0x140090711  test    cl, cl
0x140090713  jz      loc_140090930
0x140090719  mov     rdx, [rbx+3A8h]
0x140090720  xor     ecx, ecx
0x140090722  mov     r8, [rdx+10h]
0x140090726  mov     rax, r8
0x140090729  test    r8, r8
0x14009072c  jz      short loc_140090744
0x14009072e  cmp     rax, rdi
0x140090731  jnz     short loc_140090799
0x140090733  test    rcx, rcx
0x140090736  jnz     loc_140090B2B
0x14009073c  mov     rax, [r8+8]
0x140090740  mov     [rdx+10h], rax
0x140090744  cmp     dword ptr [rdi+18h], 0
0x140090748  jz      short loc_140090764
0x14009074a  mov     rax, [rbx+3A8h]
0x140090751  mov     rcx, [rax+10h]
0x140090755  mov     [rdi+8], rcx
0x140090759  mov     rax, [rbx+3A8h]
0x140090760  mov     [rax+10h], rdi
0x140090764  mov     dl, 1
0x140090766  mov     rcx, rbx
0x140090769  call    TcpTcbSetReassembly
0x14009076e  test    byte ptr [rbx+308h], 20h
0x140090775  jnz     loc_140090EB3
0x14009077b  xor     eax, eax
0x14009077d  mov     rbx, [rsp+0B8h+arg_0]
0x140090785  add     rsp, 80h
0x14009078c  pop     r15
0x14009078e  pop     r14
0x140090790  pop     r13
0x140090792  pop     r12
0x140090794  pop     rdi
0x140090795  pop     rsi
0x140090796  pop     rbp
0x140090797  retn
0x140090799  mov     rcx, rax
0x14009079c  mov     rax, [rax+8]
0x1400907a0  test    rax, rax
0x1400907a3  jnz     short loc_14009072E
0x1400907a5  jmp     short loc_140090744
0x1400907a7  test    ebp, ebp
0x1400907a9  jz      loc_14009091C
0x1400907af  test    rsi, rsi
0x1400907b2  jnz     loc_140090C67
0x1400907b8  mov     rdx, cs:ReassemblySize
0x1400907bf  mov     r12, rbp
0x1400907c2  mov     rcx, cs:ReassemblyLimit
0x1400907c9  lea     rax, [rdx+rbp]
0x1400907cd  cmp     rax, rcx
0x1400907d0  ja      loc_140090E70
0x1400907d6  mov     rax, rcx
0x1400907d9  shr     rax, 6
0x1400907dd  cmp     rdx, rax
0x1400907e0  jnb     loc_140090C9C
0x1400907e6  mov     r8d, r13d
0x1400907e9  mov     r14, [rbx+3A8h]
0x1400907f0  movzx   r15d, word ptr [r14+20h]
0x1400907f5  cmp     r15d, r8d
0x1400907f8  ja      loc_140090CFA
0x1400907fe  mov     eax, [r14+1Ch]
0x140090802  inc     eax
0x140090804  cmp     eax, r8d
0x140090807  jbe     short loc_140090826
0x140090809  mov     eax, [r14+1Ch]
0x14009080d  lea     ecx, [rax+r15*2]
0x140090811  lea     eax, [rcx+rcx*2]
0x140090814  shl     eax, 5
0x140090817  add     eax, 0E0h
0x14009081c  cmp     [r14+18h], eax
0x140090820  jb      loc_140090E0E
0x140090826  mov     r15d, [rsp+0B8h+arg_10]
0x14009082e  lea     r9, [rsp+0B8h+var_58]
0x140090833  mov     [rsp+0B8h+var_60], 0
0x14009083c  mov     edx, 18h
0x140090841  mov     [rsp+0B8h+var_50], 0
0x14009084a  mov     ecx, 40h ; '@'
0x14009084f  mov     [rsp+0B8h+var_58], 1
0x140090858  mov     r8d, 48526354h
0x14009085e  mov     dword ptr [rsp+0B8h+var_98], 1
0x140090866  call    cs:__imp_ExAllocatePool3
0x14009086d  nop     dword ptr [rax+rax+00h]
0x140090872  mov     r14, rax
0x140090875  test    rax, rax
0x140090878  jz      loc_140090E66
0x14009087e  lea     r9, [rsp+0B8h+var_58]
0x140090883  mov     dword ptr [rsp+0B8h+var_98], 1
0x14009088b  mov     r8d, 42526354h
0x140090891  mov     rdx, r12
0x140090894  mov     ecx, 42h ; 'B'
0x140090899  call    cs:__imp_ExAllocatePool3
0x1400908a0  nop     dword ptr [rax+rax+00h]
0x1400908a5  mov     [r14+10h], rax
0x1400908a9  test    rax, rax
0x1400908ac  jz      loc_140090E9D
0x1400908b2  mov     rcx, [rsp+0B8h+arg_8]
0x1400908ba  lea     r8, [rsp+0B8h+var_60]
0x1400908bf  mov     [rsp+0B8h+var_98], r8
0x1400908c4  mov     r9, r12
0x1400908c7  mov     r8, rax
0x1400908ca  mov     rcx, [rcx+8]
0x1400908ce  mov     edx, [rcx+10h]
0x1400908d1  mov     rcx, [rcx+8]
0x1400908d5  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x1400908dc  nop     dword ptr [rax+rax+00h]
0x1400908e1  mov     qword ptr [r14], 0
0x1400908e8  mov     [r14+8], ebp
0x1400908ec  mov     rax, [rdi+28h]
0x1400908f0  mov     [rax], r14
0x1400908f3  add     [rdi+18h], ebp
0x1400908f6  mov     [rdi+28h], r14
0x1400908fa  mov     rax, [rbx+3A8h]
0x140090901  add     [rax+18h], ebp
0x140090904  lock add cs:ReassemblySize, r12
0x14009090c  mov     rax, [rbx+3A8h]
0x140090913  mov     r9d, 18h
0x140090919  inc     dword ptr [rax+1Ch]
0x14009091c  movzx   r12d, [rsp+0B8h+arg_30]
0x140090925  mov     cl, 1
0x140090927  or      [rdi+10h], r12b
0x14009092b  jmp     loc_140090708
0x140090930  mov     rdx, cs:ReassemblySize
0x140090937  mov     rcx, cs:ReassemblyLimit
0x14009093e  lea     rax, [rdx+rbp]
0x140090942  cmp     rax, rcx
0x140090945  ja      loc_140090E17
0x14009094b  mov     rax, rcx
0x14009094e  shr     rax, 6
0x140090952  cmp     rdx, rax
0x140090955  jnb     loc_140090CE4
0x14009095b  mov     r12, [rbx+3A8h]
0x140090962  movzx   eax, word ptr [r12+20h]
0x140090968  mov     [rsp+0B8h+var_68], eax
0x14009096c  inc     eax
0x14009096e  mov     dword ptr [rsp+0B8h+arg_20], eax
0x140090975  cmp     eax, r13d
0x140090978  ja      loc_140090DD2
0x14009097e  mov     eax, [r12+1Ch]
0x140090983  inc     eax
0x140090985  cmp     eax, r13d
0x140090988  jbe     short loc_1400909AC
0x14009098a  mov     eax, [r12+1Ch]
0x14009098f  mov     ecx, [rsp+0B8h+var_68]
0x140090993  lea     ecx, [rax+rcx*2]
0x140090996  lea     eax, [rcx+rcx*2]
0x140090999  shl     eax, 5
0x14009099c  add     eax, 0E0h
0x1400909a1  cmp     [r12+18h], eax
0x1400909a6  jb      loc_140090E50
0x1400909ac  xor     r13d, r13d
0x1400909af  test    ebp, ebp
0x1400909b1  jz      loc_140090CB2
0x1400909b7  lea     r9, [rsp+0B8h+var_48]
0x1400909bc  mov     [rsp+0B8h+arg_20], r13
0x1400909c4  mov     edx, 18h
0x1400909c9  mov     [rsp+0B8h+var_40], r13
0x1400909ce  mov     ecx, 40h ; '@'
0x1400909d3  mov     [rsp+0B8h+var_48], 1
0x1400909dc  mov     r8d, 48526354h
0x1400909e2  mov     dword ptr [rsp+0B8h+var_98], 1
0x1400909ea  call    cs:__imp_ExAllocatePool3
0x1400909f1  nop     dword ptr [rax+rax+00h]
0x1400909f6  mov     r14, rax
0x1400909f9  test    rax, rax
0x1400909fc  jz      loc_140090E66
0x140090a02  lea     r9, [rsp+0B8h+var_48]
0x140090a07  mov     dword ptr [rsp+0B8h+var_98], 1
0x140090a0f  mov     r8d, 42526354h
0x140090a15  mov     rdx, rbp
0x140090a18  mov     ecx, 42h ; 'B'
0x140090a1d  mov     r12, rbp
0x140090a20  call    cs:__imp_ExAllocatePool3
0x140090a27  nop     dword ptr [rax+rax+00h]
0x140090a2c  mov     [r14+10h], rax
0x140090a30  test    rax, rax
0x140090a33  jz      loc_140090E9D
0x140090a39  mov     rcx, [rsp+0B8h+arg_8]
0x140090a41  lea     r8, [rsp+0B8h+arg_20]
0x140090a49  mov     [rsp+0B8h+var_98], r8
0x140090a4e  mov     r9, rbp
0x140090a51  mov     r8, rax
0x140090a54  mov     rcx, [rcx+8]
0x140090a58  mov     edx, [rcx+10h]
0x140090a5b  mov     rcx, [rcx+8]
0x140090a5f  call    cs:__imp_RtlCopyMdlToKernelBuffer
0x140090a66  nop     dword ptr [rax+rax+00h]
0x140090a6b  mov     [r14], r13
0x140090a6e  mov     [r14+8], ebp
0x140090a72  mov     rcx, cs:ReassemblyPool
0x140090a79  call    PplAllocateFromLookasideList
0x140090a7e  mov     rdx, rax
0x140090a81  test    rax, rax
0x140090a84  jz      loc_140090E61
0x140090a8a  mov     [rax+8], r13
0x140090a8e  mov     [rax+10h], r13d
0x140090a92  mov     [rax+1Ch], r13d
0x140090a96  mov     [rax+14h], r15d
0x140090a9a  mov     [rax+18h], ebp
0x140090a9d  mov     [rax+20h], r14
0x140090aa1  mov     [rax+28h], r14
0x140090aa5  movzx   eax, [rsp+0B8h+arg_30]
0x140090aad  or      [rdx+10h], al
0x140090ab0  mov     [rdx], rsi
0x140090ab3  test    rdi, rdi
0x140090ab6  jnz     loc_140090C94
0x140090abc  mov     rax, [rbx+3A8h]
0x140090ac3  mov     [rax], rdx
0x140090ac6  mov     rax, [rbx+3A8h]
0x140090acd  add     [rax+18h], ebp
0x140090ad0  lock add cs:ReassemblySize, r12
0x140090ad8  test    r14, r14
0x140090adb  jz      short loc_140090AE7
0x140090add  mov     rax, [rbx+3A8h]
0x140090ae4  inc     dword ptr [rax+1Ch]
0x140090ae7  mov     rax, [rbx+3A8h]
0x140090aee  inc     word ptr [rax+20h]
0x140090af2  cmp     dword ptr [rdx+18h], 0
0x140090af6  jz      short loc_140090B12
0x140090af8  mov     rax, [rbx+3A8h]
0x140090aff  mov     rcx, [rax+10h]
0x140090b03  mov     [rdx+8], rcx
0x140090b07  mov     rax, [rbx+3A8h]
0x140090b0e  mov     [rax+10h], rdx
0x140090b12  test    rsi, rsi
0x140090b15  jnz     loc_140090764
0x140090b1b  mov     rax, [rbx+3A8h]
0x140090b22  mov     [rax+8], rdx
0x140090b26  jmp     loc_140090764
0x140090b2b  mov     rax, [rdi+8]
0x140090b2f  mov     [rcx+8], rax
0x140090b33  jmp     loc_140090744
0x140090b38  lea     eax, [r15+rbp]
0x140090b3c  cmp     eax, [rsi+14h]
0x140090b3f  jnz     loc_140090711
0x140090b45  test    cl, cl
0x140090b47  jz      loc_140090D64
0x140090b4d  mov     rax, [rsi]
0x140090b50  mov     rcx, [rdi+28h]
0x140090b54  mov     [rdi], rax
0x140090b57  mov     rax, [rsi+20h]
0x140090b5b  mov     [rcx], rax
0x140090b5e  xor     ecx, ecx
0x140090b60  mov     rax, [rsi+28h]
0x140090b64  mov     [rdi+28h], rax
0x140090b68  mov     eax, [rsi+18h]
0x140090b6b  add     [rdi+18h], eax
0x140090b6e  movzx   eax, byte ptr [rsi+10h]
0x140090b72  or      [rdi+10h], al
0x140090b75  mov     rdx, [rbx+3A8h]
0x140090b7c  mov     r8, [rdx+10h]
0x140090b80  mov     rax, r8
0x140090b83  test    r8, r8
0x140090b86  jz      short loc_140090BA2
0x140090b88  cmp     rax, rdi
0x140090b8b  jnz     loc_140090CBA
0x140090b91  test    rcx, rcx
0x140090b94  jnz     loc_140090DF4
0x140090b9a  mov     rax, [r8+8]
0x140090b9e  mov     [rdx+10h], rax
0x140090ba2  mov     rdx, [rbx+3A8h]
0x140090ba9  xor     ecx, ecx
0x140090bab  mov     r8, [rdx+10h]
0x140090baf  mov     rax, r8
0x140090bb2  test    r8, r8
0x140090bb5  jz      short loc_140090BD1
0x140090bb7  cmp     rax, rsi
0x140090bba  jnz     loc_140090CCF
0x140090bc0  test    rcx, rcx
0x140090bc3  jnz     loc_140090E01
0x140090bc9  mov     rax, [r8+8]
  ... truncated ...
```
