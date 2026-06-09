# IppReceiveEspNbl

- ea: `0x140061a20`
- end: `0x140061fda`
- name: `IppReceiveEspNbl`
- size: `1466`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400607bc`
- `0x140194730`

## callees

- `0x140061a20`
- `0x140061fe0`
- `0x1400625f0`
- `0x140062800`
- `0x140063050`
- `0x1401bf390`
- `0x1401bf940`
- `0x1402743b0`
- `0x14027506c`
- `0x1402750ac`
- `0x1402754d0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140061f82`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140061fb9`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140061f82`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140061fb9`
- `NETIO!NetioAllocateMdl` at `0x140061ea0`
- `NETIO!NetioAllocateMdl` at `0x140061ec0`
- `NETIO!NetioAllocateMdl` at `0x140061ede`
- `NETIO!NetioAllocateMdl` at `0x140061efc`
- `NDIS!NdisGetDataBuffer` at `0x140061afc`
- `NDIS!NdisGetDataBuffer` at `0x140061bb3`
- `NDIS!NdisGetDataBuffer` at `0x140061d0a`
- `NDIS!NdisGetDataBuffer` at `0x140061d80`
- `NDIS!NdisGetDataBuffer` at `0x140061afc`
- `NDIS!NdisGetDataBuffer` at `0x140061bb3`
- `NDIS!NdisGetDataBuffer` at `0x140061d0a`
- `NDIS!NdisGetDataBuffer` at `0x140061d80`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140061e39`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140061e55`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140061e39`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x140061e55`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061eaf`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061ecd`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061eeb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061f0e`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061eaf`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061ecd`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061eeb`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140061f0e`

## pseudocode

```c
int __fastcall IppReceiveEspNbl(
        __int64 a1,
        __int16 a2,
        int a3,
        __int64 a4,
        unsigned int *a5,
        __int64 a6,
        _WORD *a7,
        _WORD *a8,
        __int64 a9)
{
  __int64 v9; // rbx
  ULONG v13; // edi
  unsigned int *DataBuffer; // rax
  ULONG v15; // esi
  int v16; // ecx
  ULONG v17; // edi
  ULONG v18; // edx
  unsigned int v19; // ecx
  unsigned int *v20; // r15
  struct _MDL *v21; // r14
  unsigned int v22; // esi
  __int64 v23; // r12
  unsigned int *v24; // rdx
  unsigned int ByteCount; // edi
  ULONG v26; // r15d
  ULONG v27; // edi
  ULONG v28; // ecx
  char v29; // r14
  int v30; // esi
  int v31; // edx
  unsigned int v32; // eax
  ULONG v33; // r12d
  unsigned int *v34; // rdi
  int v35; // r8d
  ULONG v36; // edx
  unsigned int v37; // eax
  ULONG v38; // edx
  ULONG v39; // r12d
  PVOID v40; // rax
  unsigned int v41; // eax
  ULONG v42; // edx
  _DWORD *v43; // r8
  int v44; // eax
  _DWORD *v45; // rcx
  __int16 v47; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v48[2]; // [rsp+64h] [rbp-9Ch] BYREF
  ULONG v49; // [rsp+68h] [rbp-98h] BYREF
  __int16 v50; // [rsp+6Ch] [rbp-94h]
  ULONG BytesNeeded; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v52; // [rsp+74h] [rbp-8Ch] BYREF
  _WORD *v53; // [rsp+78h] [rbp-88h]
  _WORD *v54; // [rsp+80h] [rbp-80h]
  __int64 v55; // [rsp+88h] [rbp-78h]
  _BYTE v56[1024]; // [rsp+90h] [rbp-70h] BYREF
  _OWORD Storage[2]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v58; // [rsp+4B0h] [rbp+3B0h]
  char v59[32]; // [rsp+4B8h] [rbp+3B8h] BYREF

  v9 = *(_QWORD *)(a1 + 8);
  v53 = a7;
  v54 = a8;
  v55 = a9;
  v50 = a2;
  v47 = 0;
  v52 = 0;
  v49 = 0;
  v48[0] = 0;
  BytesNeeded = 0;
  v58 = 0;
  memset(Storage, 0, sizeof(Storage));
  memset(v56, 0, sizeof(v56));
  v13 = *(_DWORD *)(v9 + 24);
  if ( v13 > 0x28 )
    v13 = 40;
  DataBuffer = (unsigned int *)NdisGetDataBuffer((PNET_BUFFER)v9, v13, Storage, 1u, 0);
  if ( !DataBuffer )
    goto LABEL_56;
  LODWORD(DataBuffer) = IpSecEspInitInbound(
                          a1,
                          a3,
                          DataBuffer,
                          v13,
                          *(_DWORD *)(v9 + 24),
                          a4,
                          a5,
                          a6,
                          &BytesNeeded,
                          (__int64)&v47,
                          (__int64)&v52,
                          &v49);
  if ( (int)DataBuffer < 0 )
    goto LABEL_50;
  v15 = BytesNeeded;
  if ( BytesNeeded )
  {
    v16 = *(_DWORD *)(v9 + 24);
    v17 = v16 - BytesNeeded;
    if ( v16 != BytesNeeded )
    {
      v18 = v17 + *(_DWORD *)(v9 + 16);
      if ( v18 >= *(_DWORD *)(*(_QWORD *)(v9 + 8) + 40LL) )
      {
        NdisAdvanceNetBufferDataStart((PNET_BUFFER)v9, v17, 0, 0);
      }
      else
      {
        *(_DWORD *)(v9 + 40) += v17;
        *(_DWORD *)(v9 + 16) = v18;
        *(_DWORD *)(v9 + 24) = v16 - v17;
      }
    }
    DataBuffer = (unsigned int *)NdisGetDataBuffer((PNET_BUFFER)v9, v15, v59, 1u, 0);
    v19 = *(_DWORD *)(v9 + 16);
    v20 = DataBuffer;
    if ( v19 < v17 )
    {
      LODWORD(DataBuffer) = NdisRetreatNetBufferDataStart((PNET_BUFFER)v9, v17, 0, NetioAllocateMdl);
    }
    else
    {
      *(_DWORD *)(v9 + 40) -= v17;
      *(_DWORD *)(v9 + 24) += v17;
      *(_DWORD *)(v9 + 16) = v19 - v17;
    }
    *(_DWORD *)(v9 + 24) -= v15;
    *(_DWORD *)(v9 + 88) += v15;
  }
  else
  {
    v20 = 0;
  }
  if ( (_BYTE)v47 )
  {
    v21 = *(struct _MDL **)(v9 + 8);
    if ( !v21 )
    {
LABEL_56:
      *(_DWORD *)(a1 + 140) = -1073741285;
      return (int)DataBuffer;
    }
    v22 = *(_DWORD *)(v9 + 24);
    v23 = *(unsigned int *)(v9 + 16);
    if ( (v21->MdlFlags & 5) != 0 )
      DataBuffer = (unsigned int *)v21->MappedSystemVa;
    else
      DataBuffer = (unsigned int *)MmMapLockedPagesSpecifyCache(v21, 0, MmCached, 0, 0, 0x40000000u);
    if ( !DataBuffer )
    {
LABEL_57:
      *(_DWORD *)(a1 + 140) = -1073741670;
      return (int)DataBuffer;
    }
    v24 = (unsigned int *)((char *)DataBuffer + v23);
    ByteCount = v21->ByteCount - v23;
    if ( v22 < ByteCount )
      ByteCount = v22;
    while ( 1 )
    {
      IpSecEspAuthInbound(a1, v24, ByteCount);
      v22 -= ByteCount;
      if ( !v22 )
        break;
      v21 = v21->Next;
      ByteCount = v22;
      if ( v22 >= v21->ByteCount )
        ByteCount = v21->ByteCount;
      if ( (v21->MdlFlags & 5) != 0 )
        DataBuffer = (unsigned int *)v21->MappedSystemVa;
      else
        DataBuffer = (unsigned int *)MmMapLockedPagesSpecifyCache(v21, 0, MmCached, 0, 0, 0x40000000u);
      if ( !DataBuffer )
        goto LABEL_57;
      v24 = DataBuffer;
    }
    LODWORD(DataBuffer) = IpSecEspAuthCompleteInbound(a1, v20);
    if ( (int)DataBuffer < 0 )
      goto LABEL_50;
  }
  v26 = v49;
  v27 = v49 + 8;
  if ( v49 != -8 )
  {
    v28 = v27 + *(_DWORD *)(v9 + 16);
    if ( v28 >= *(_DWORD *)(*(_QWORD *)(v9 + 8) + 40LL) )
    {
      NdisAdvanceNetBufferDataStart((PNET_BUFFER)v9, v27, 0, 0);
    }
    else
    {
      *(_DWORD *)(v9 + 40) += v27;
      *(_DWORD *)(v9 + 24) -= v27;
      *(_DWORD *)(v9 + 16) = v28;
    }
  }
  v29 = HIBYTE(v47);
  v30 = *(_DWORD *)(v9 + 40);
  v31 = *(_DWORD *)(v9 + 24);
  v49 = v27;
  if ( !HIBYTE(v47) )
  {
    NetioAdvanceNetBuffer(v9, (unsigned int)(v31 - 2));
    v33 = v27 + *(_DWORD *)(v9 + 24) - 2;
    goto LABEL_29;
  }
  LODWORD(DataBuffer) = IppEspProcessPacket(IpSecEspDecryptInbound, a1, v9, v52, v31, &v49);
  if ( (int)DataBuffer < 0 )
  {
LABEL_50:
    *(_DWORD *)(a1 + 140) = (_DWORD)DataBuffer;
    return (int)DataBuffer;
  }
  v32 = *(_DWORD *)(v9 + 16);
  if ( v32 < 2 )
  {
    NdisRetreatNetBufferDataStart((PNET_BUFFER)v9, 2u, 0, NetioAllocateMdl);
  }
  else
  {
    *(_DWORD *)(v9 + 40) -= 2;
    *(_DWORD *)(v9 + 24) += 2;
    *(_DWORD *)(v9 + 16) = v32 - 2;
  }
  v33 = v49 - 2;
LABEL_29:
  LODWORD(DataBuffer) = IPsecGetEspTrailerFromNblInfo(a1, v48);
  if ( (_BYTE)DataBuffer )
  {
    v34 = (unsigned int *)v48;
  }
  else
  {
    DataBuffer = (unsigned int *)NdisGetDataBuffer((PNET_BUFFER)v9, 2u, v48, 1u, 0);
    v34 = DataBuffer;
  }
  v35 = *(_DWORD *)(v9 + 40);
  if ( *(unsigned __int8 *)v34 > (unsigned int)(v35 - v30) )
    goto LABEL_56;
  *v54 = *v53 + v35 - v30 + 9;
  v36 = *(unsigned __int8 *)v34;
  v37 = *(_DWORD *)(v9 + 16);
  if ( v37 < v36 )
  {
    NdisRetreatNetBufferDataStart((PNET_BUFFER)v9, v36, 0, NetioAllocateMdl);
  }
  else
  {
    *(_DWORD *)(v9 + 40) -= v36;
    *(_DWORD *)(v9 + 24) += v36;
    *(_DWORD *)(v9 + 16) = v37 - v36;
  }
  v38 = *(unsigned __int8 *)v34;
  v39 = v33 - v38;
  if ( v29 )
  {
    v40 = NdisGetDataBuffer((PNET_BUFFER)v9, v38, v56, 1u, 0);
    LODWORD(DataBuffer) = IpSecEspDecryptCompleteInbound(a1, v40, *(unsigned __int8 *)v34, v39);
    if ( (int)DataBuffer < 0 )
      goto LABEL_50;
  }
  v41 = *(_DWORD *)(v9 + 16);
  v42 = *(_DWORD *)(v9 + 40) - v30;
  if ( v41 < v42 )
  {
    NdisRetreatNetBufferDataStart((PNET_BUFFER)v9, v42, 0, NetioAllocateMdl);
  }
  else
  {
    *(_DWORD *)(v9 + 40) = v30;
    *(_DWORD *)(v9 + 24) += v42;
    *(_DWORD *)(v9 + 16) = v41 - v42;
  }
  v43 = (_DWORD *)v55;
  v44 = *(unsigned __int8 *)v34 + 2;
  *(_DWORD *)(v9 + 24) -= v44;
  *(_DWORD *)(v9 + 88) += v44;
  v45 = v53;
  *v43 = *((unsigned __int8 *)v34 + 1);
  *v45 += v26 + 8;
  LODWORD(DataBuffer) = 2;
  if ( v50 == 2 )
  {
    DataBuffer = (unsigned int *)IPSecNsProcessInboundSecurePacket((unsigned int)*v43, a1);
    if ( DataBuffer )
      *(_DWORD *)(a1 + 140) = -1073741823;
  }
  return (int)DataBuffer;
}

```

## disassembly

```asm
0x140061a20  mov     [rsp-8+arg_8], rbx
0x140061a25  push    rbp
0x140061a26  push    rsi
0x140061a27  push    rdi
0x140061a28  push    r12
0x140061a2a  push    r13
0x140061a2c  push    r14
0x140061a2e  push    r15
0x140061a30  lea     rbp, [rsp-3E0h]
0x140061a38  sub     rsp, 4E0h
0x140061a3f  mov     rax, cs:__security_cookie
0x140061a46  xor     rax, rsp
0x140061a49  mov     [rbp+410h+var_38], rax
0x140061a50  mov     rbx, [rcx+8]
0x140061a54  mov     r13, rcx
0x140061a57  mov     rax, [rbp+410h+arg_30]
0x140061a5e  xor     ecx, ecx
0x140061a60  mov     r15, [rbp+410h+arg_20]
0x140061a67  xorps   xmm0, xmm0
0x140061a6a  mov     r12, [rbp+410h+arg_28]
0x140061a71  mov     esi, r8d
0x140061a74  mov     [rsp+510h+var_498], rax
0x140061a79  mov     r8d, 400h; Size
0x140061a7f  mov     rax, [rbp+410h+arg_38]
0x140061a86  mov     r14, r9
0x140061a89  mov     [rbp+410h+var_490], rax
0x140061a8d  mov     rax, [rbp+410h+arg_40]
0x140061a94  mov     [rbp+410h+var_488], rax
0x140061a98  xor     eax, eax
0x140061a9a  mov     [rsp+510h+var_4A4], dx
0x140061a9f  xor     edx, edx; Val
0x140061aa1  mov     [rsp+510h+var_4B0], cx
0x140061aa6  mov     [rsp+510h+var_49C], ecx
0x140061aaa  mov     [rsp+510h+var_4A8], ecx
0x140061aae  mov     [rsp+510h+var_4AC], cx
0x140061ab3  mov     [rsp+510h+BytesNeeded], ecx
0x140061ab7  lea     rcx, [rbp+410h+var_480]; void *
0x140061abb  mov     [rbp+410h+var_60], rax
0x140061ac2  movups  [rbp+410h+Storage], xmm0
0x140061ac9  movups  [rbp+410h+var_70], xmm0
0x140061ad0  call    memset
0x140061ad5  mov     edi, [rbx+18h]
0x140061ad8  lea     r8, [rbp+410h+Storage]; Storage
0x140061adf  mov     eax, 28h ; '('
0x140061ae4  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061aec  cmp     edi, eax
0x140061aee  mov     r9d, 1; AlignMultiple
0x140061af4  mov     rcx, rbx; NetBuffer
0x140061af7  cmova   edi, eax
0x140061afa  mov     edx, edi; BytesNeeded
0x140061afc  call    cs:__imp_NdisGetDataBuffer
0x140061b03  nop     dword ptr [rax+rax+00h]
0x140061b08  mov     r8, rax
0x140061b0b  test    rax, rax
0x140061b0e  jz      loc_140061F3A
0x140061b14  lea     rax, [rsp+510h+var_4A8]
0x140061b19  mov     r9d, edi
0x140061b1c  mov     [rsp+510h+var_4B8], rax
0x140061b21  mov     edx, esi
0x140061b23  lea     rax, [rsp+510h+var_49C]
0x140061b28  mov     rcx, r13
0x140061b2b  mov     [rsp+510h+var_4C0], rax
0x140061b30  lea     rax, [rsp+510h+var_4B0]
0x140061b35  mov     [rsp+510h+var_4C8], rax
0x140061b3a  lea     rax, [rsp+510h+BytesNeeded]
0x140061b3f  mov     [rsp+510h+var_4D0], rax
0x140061b44  mov     eax, [rbx+18h]
0x140061b47  mov     [rsp+510h+var_4D8], r12
0x140061b4c  mov     [rsp+510h+var_4E0], r15
0x140061b51  mov     qword ptr [rsp+510h+Priority], r14
0x140061b56  mov     [rsp+510h+AlignOffset], eax
0x140061b5a  call    IpSecEspInitInbound
0x140061b5f  test    eax, eax
0x140061b61  js      loc_140061E94
0x140061b67  mov     esi, [rsp+510h+BytesNeeded]
0x140061b6b  test    esi, esi
0x140061b6d  jz      loc_140061F93
0x140061b73  mov     ecx, [rbx+18h]
0x140061b76  mov     edi, ecx
0x140061b78  sub     edi, esi
0x140061b7a  jz      short loc_140061B99
0x140061b7c  mov     rax, [rbx+8]
0x140061b80  mov     edx, [rbx+10h]
0x140061b83  add     edx, edi
0x140061b85  cmp     edx, [rax+28h]
0x140061b88  jnb     loc_140061E2E
0x140061b8e  add     [rbx+28h], edi
0x140061b91  sub     ecx, edi
0x140061b93  mov     [rbx+10h], edx
0x140061b96  mov     [rbx+18h], ecx
0x140061b99  mov     r9d, 1; AlignMultiple
0x140061b9f  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061ba7  lea     r8, [rbp+410h+var_58]; Storage
0x140061bae  mov     edx, esi; BytesNeeded
0x140061bb0  mov     rcx, rbx; NetBuffer
0x140061bb3  call    cs:__imp_NdisGetDataBuffer
0x140061bba  nop     dword ptr [rax+rax+00h]
0x140061bbf  mov     ecx, [rbx+10h]
0x140061bc2  mov     r15, rax
0x140061bc5  cmp     ecx, edi
0x140061bc7  jb      loc_140061EA0
0x140061bcd  sub     [rbx+28h], edi
0x140061bd0  sub     ecx, edi
0x140061bd2  add     [rbx+18h], edi
0x140061bd5  mov     [rbx+10h], ecx
0x140061bd8  sub     [rbx+18h], esi
0x140061bdb  add     [rbx+58h], esi
0x140061bde  cmp     byte ptr [rsp+510h+var_4B0], 0
0x140061be3  jz      short loc_140061C49
0x140061be5  mov     r14, [rbx+8]
0x140061be9  test    r14, r14
0x140061bec  jz      loc_140061F3A
0x140061bf2  test    byte ptr [r14+0Ah], 5
0x140061bf7  mov     esi, [rbx+18h]
0x140061bfa  mov     r12d, [rbx+10h]
0x140061bfe  jz      loc_140061F64
0x140061c04  mov     rax, [r14+18h]
0x140061c08  test    rax, rax
0x140061c0b  jz      loc_140061F4A
0x140061c11  mov     edi, [r14+28h]
0x140061c15  lea     rdx, [rax+r12]
0x140061c19  sub     edi, r12d
0x140061c1c  cmp     esi, edi
0x140061c1e  cmovb   edi, esi
0x140061c21  mov     r8d, edi
0x140061c24  mov     rcx, r13
0x140061c27  call    IpSecEspAuthInbound
0x140061c2c  sub     esi, edi
0x140061c2e  test    esi, esi
0x140061c30  jnz     loc_140061E66
0x140061c36  mov     rdx, r15
0x140061c39  mov     rcx, r13
0x140061c3c  call    IpSecEspAuthCompleteInbound
0x140061c41  test    eax, eax
0x140061c43  js      loc_140061E94
0x140061c49  mov     r15d, [rsp+510h+var_4A8]
0x140061c4e  lea     edi, [r15+8]
0x140061c52  test    edi, edi
0x140061c54  jz      short loc_140061C71
0x140061c56  mov     rax, [rbx+8]
0x140061c5a  mov     ecx, [rbx+10h]
0x140061c5d  add     ecx, edi
0x140061c5f  cmp     ecx, [rax+28h]
0x140061c62  jnb     loc_140061E4A
0x140061c68  add     [rbx+28h], edi
0x140061c6b  sub     [rbx+18h], edi
0x140061c6e  mov     [rbx+10h], ecx
0x140061c71  movzx   r14d, byte ptr [rsp+510h+var_4B0+1]
0x140061c77  mov     esi, [rbx+28h]
0x140061c7a  mov     edx, [rbx+18h]
0x140061c7d  mov     [rsp+510h+var_4A8], edi
0x140061c81  test    r14b, r14b
0x140061c84  jz      loc_140061F1F
0x140061c8a  mov     r9d, [rsp+510h+var_49C]
0x140061c8f  lea     rax, [rsp+510h+var_4A8]
0x140061c94  mov     qword ptr [rsp+510h+Priority], rax
0x140061c99  lea     rcx, IpSecEspDecryptInbound
0x140061ca0  mov     [rsp+510h+AlignOffset], edx
0x140061ca4  mov     r8, rbx
0x140061ca7  mov     rdx, r13
0x140061caa  call    IppEspProcessPacket
0x140061caf  test    eax, eax
0x140061cb1  js      loc_140061E94
0x140061cb7  mov     eax, [rbx+10h]
0x140061cba  cmp     eax, 2
0x140061cbd  jb      loc_140061EFC
0x140061cc3  add     dword ptr [rbx+28h], 0FFFFFFFEh
0x140061cc7  add     eax, 0FFFFFFFEh
0x140061cca  add     dword ptr [rbx+18h], 2
0x140061cce  mov     [rbx+10h], eax
0x140061cd1  mov     r12d, [rsp+510h+var_4A8]
0x140061cd6  add     r12d, 0FFFFFFFEh
0x140061cda  lea     rdx, [rsp+510h+var_4AC]
0x140061cdf  mov     rcx, r13
0x140061ce2  call    IPsecGetEspTrailerFromNblInfo
0x140061ce7  test    al, al
0x140061ce9  jnz     loc_140061F5A
0x140061cef  mov     r9d, 1; AlignMultiple
0x140061cf5  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061cfd  lea     r8, [rsp+510h+var_4AC]; Storage
0x140061d02  mov     edx, 2; BytesNeeded
0x140061d07  mov     rcx, rbx; NetBuffer
0x140061d0a  call    cs:__imp_NdisGetDataBuffer
0x140061d11  nop     dword ptr [rax+rax+00h]
0x140061d16  mov     rdi, rax
0x140061d19  mov     r8d, [rbx+28h]
0x140061d1d  mov     edx, r8d
0x140061d20  movzx   ecx, byte ptr [rdi]
0x140061d23  sub     edx, esi
0x140061d25  cmp     ecx, edx
0x140061d27  ja      loc_140061F3A
0x140061d2d  mov     rax, [rsp+510h+var_498]
0x140061d32  sub     r8w, si
0x140061d36  add     r8w, 9
0x140061d3b  add     r8w, [rax]
0x140061d3f  mov     rax, [rbp+410h+var_490]
0x140061d43  mov     [rax], r8w
0x140061d47  movzx   edx, byte ptr [rdi]; DataOffsetDelta
0x140061d4a  mov     eax, [rbx+10h]
0x140061d4d  cmp     eax, edx
0x140061d4f  jb      loc_140061EC0
0x140061d55  sub     [rbx+28h], edx
0x140061d58  sub     eax, edx
0x140061d5a  add     [rbx+18h], edx
0x140061d5d  mov     [rbx+10h], eax
0x140061d60  movzx   edx, byte ptr [rdi]; BytesNeeded
0x140061d63  sub     r12d, edx
0x140061d66  test    r14b, r14b
0x140061d69  jz      short loc_140061DA6
0x140061d6b  mov     r9d, 1; AlignMultiple
0x140061d71  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061d79  lea     r8, [rbp+410h+var_480]; Storage
0x140061d7d  mov     rcx, rbx; NetBuffer
0x140061d80  call    cs:__imp_NdisGetDataBuffer
0x140061d87  nop     dword ptr [rax+rax+00h]
0x140061d8c  movzx   r8d, byte ptr [rdi]
0x140061d90  mov     r9d, r12d
0x140061d93  mov     rdx, rax
0x140061d96  mov     rcx, r13
0x140061d99  call    IpSecEspDecryptCompleteInbound
0x140061d9e  test    eax, eax
0x140061da0  js      loc_140061E94
0x140061da6  mov     edx, [rbx+28h]
0x140061da9  mov     eax, [rbx+10h]
0x140061dac  sub     edx, esi; DataOffsetDelta
0x140061dae  cmp     eax, edx
0x140061db0  jb      loc_140061EDE
0x140061db6  sub     eax, edx
0x140061db8  mov     [rbx+28h], esi
0x140061dbb  add     [rbx+18h], edx
0x140061dbe  mov     [rbx+10h], eax
0x140061dc1  movzx   eax, byte ptr [rdi]
0x140061dc4  mov     r8, [rbp+410h+var_488]
0x140061dc8  add     eax, 2
0x140061dcb  sub     [rbx+18h], eax
0x140061dce  add     [rbx+58h], eax
0x140061dd1  movzx   eax, byte ptr [rdi+1]
0x140061dd5  mov     rcx, [rsp+510h+var_498]
0x140061dda  mov     [r8], eax
0x140061ddd  lea     eax, [r15+8]
0x140061de1  add     [rcx], eax
0x140061de3  mov     eax, 2
0x140061de8  cmp     ax, [rsp+510h+var_4A4]
0x140061ded  jnz     short loc_140061E03
0x140061def  mov     ecx, [r8]
0x140061df2  mov     rdx, r13
0x140061df5  call    IPSecNsProcessInboundSecurePacket
0x140061dfa  test    rax, rax
0x140061dfd  jnz     loc_140061FCA
0x140061e03  mov     rcx, [rbp+410h+var_38]
0x140061e0a  xor     rcx, rsp; StackCookie
0x140061e0d  call    __security_check_cookie
0x140061e12  mov     rbx, [rsp+510h+arg_8]
0x140061e1a  add     rsp, 4E0h
0x140061e21  pop     r15
0x140061e23  pop     r14
0x140061e25  pop     r13
0x140061e27  pop     r12
0x140061e29  pop     rdi
0x140061e2a  pop     rsi
0x140061e2b  pop     rbp
0x140061e2c  retn
0x140061e2e  xor     r9d, r9d; FreeMdlHandler
0x140061e31  xor     r8d, r8d; FreeMdl
0x140061e34  mov     edx, edi; DataOffsetDelta
0x140061e36  mov     rcx, rbx; NetBuffer
0x140061e39  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140061e40  nop     dword ptr [rax+rax+00h]
0x140061e45  jmp     loc_140061B99
0x140061e4a  xor     r9d, r9d; FreeMdlHandler
0x140061e4d  xor     r8d, r8d; FreeMdl
0x140061e50  mov     edx, edi; DataOffsetDelta
0x140061e52  mov     rcx, rbx; NetBuffer
0x140061e55  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x140061e5c  nop     dword ptr [rax+rax+00h]
0x140061e61  jmp     loc_140061C71
0x140061e66  mov     r14, [r14]
0x140061e69  mov     edi, esi
0x140061e6b  mov     eax, [r14+28h]
0x140061e6f  cmp     esi, eax
0x140061e71  cmovnb  edi, eax
0x140061e74  test    byte ptr [r14+0Ah], 5
0x140061e79  jz      loc_140061F9B
0x140061e7f  mov     rax, [r14+18h]
0x140061e83  test    rax, rax
0x140061e86  jz      loc_140061F4A
0x140061e8c  mov     rdx, rax
0x140061e8f  jmp     loc_140061C21
0x140061e94  mov     [r13+8Ch], eax
0x140061e9b  jmp     loc_140061E03
0x140061ea0  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140061ea7  xor     r8d, r8d; DataBackFill
0x140061eaa  mov     edx, edi; DataOffsetDelta
0x140061eac  mov     rcx, rbx; NetBuffer
0x140061eaf  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140061eb6  nop     dword ptr [rax+rax+00h]
0x140061ebb  jmp     loc_140061BD8
0x140061ec0  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140061ec7  xor     r8d, r8d; DataBackFill
0x140061eca  mov     rcx, rbx; NetBuffer
  ... truncated ...
```
