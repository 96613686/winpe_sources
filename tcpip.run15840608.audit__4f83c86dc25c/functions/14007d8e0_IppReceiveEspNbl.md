# IppReceiveEspNbl

- ea: `0x14007d8e0`
- end: `0x14007de9a`
- name: `IppReceiveEspNbl`
- size: `1466`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14007f42c`
- `0x140196510`

## callees

- `0x14007d8e0`
- `0x14007dea0`
- `0x14007e4b0`
- `0x14007e6c0`
- `0x14007ef10`
- `0x1401c0fd0`
- `0x1401c1580`
- `0x14027872c`
- `0x1402793dc`
- `0x14027941c`
- `0x140279840`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007de42`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007de79`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007de42`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007de79`
- `NETIO!NetioAllocateMdl` at `0x14007dd60`
- `NETIO!NetioAllocateMdl` at `0x14007dd80`
- `NETIO!NetioAllocateMdl` at `0x14007dd9e`
- `NETIO!NetioAllocateMdl` at `0x14007ddbc`
- `NDIS!NdisGetDataBuffer` at `0x14007d9bc`
- `NDIS!NdisGetDataBuffer` at `0x14007da73`
- `NDIS!NdisGetDataBuffer` at `0x14007dbca`
- `NDIS!NdisGetDataBuffer` at `0x14007dc40`
- `NDIS!NdisGetDataBuffer` at `0x14007d9bc`
- `NDIS!NdisGetDataBuffer` at `0x14007da73`
- `NDIS!NdisGetDataBuffer` at `0x14007dbca`
- `NDIS!NdisGetDataBuffer` at `0x14007dc40`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14007dcf9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14007dd15`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14007dcf9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x14007dd15`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007dd6f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007dd8d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007ddab`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007ddce`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007dd6f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007dd8d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007ddab`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14007ddce`

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
0x14007d8e0  mov     [rsp-8+arg_8], rbx
0x14007d8e5  push    rbp
0x14007d8e6  push    rsi
0x14007d8e7  push    rdi
0x14007d8e8  push    r12
0x14007d8ea  push    r13
0x14007d8ec  push    r14
0x14007d8ee  push    r15
0x14007d8f0  lea     rbp, [rsp-3E0h]
0x14007d8f8  sub     rsp, 4E0h
0x14007d8ff  mov     rax, cs:__security_cookie
0x14007d906  xor     rax, rsp
0x14007d909  mov     [rbp+410h+var_38], rax
0x14007d910  mov     rbx, [rcx+8]
0x14007d914  mov     r13, rcx
0x14007d917  mov     rax, [rbp+410h+arg_30]
0x14007d91e  xor     ecx, ecx
0x14007d920  mov     r15, [rbp+410h+arg_20]
0x14007d927  xorps   xmm0, xmm0
0x14007d92a  mov     r12, [rbp+410h+arg_28]
0x14007d931  mov     esi, r8d
0x14007d934  mov     [rsp+510h+var_498], rax
0x14007d939  mov     r8d, 400h; Size
0x14007d93f  mov     rax, [rbp+410h+arg_38]
0x14007d946  mov     r14, r9
0x14007d949  mov     [rbp+410h+var_490], rax
0x14007d94d  mov     rax, [rbp+410h+arg_40]
0x14007d954  mov     [rbp+410h+var_488], rax
0x14007d958  xor     eax, eax
0x14007d95a  mov     [rsp+510h+var_4A4], dx
0x14007d95f  xor     edx, edx; Val
0x14007d961  mov     [rsp+510h+var_4B0], cx
0x14007d966  mov     [rsp+510h+var_49C], ecx
0x14007d96a  mov     [rsp+510h+var_4A8], ecx
0x14007d96e  mov     [rsp+510h+var_4AC], cx
0x14007d973  mov     [rsp+510h+BytesNeeded], ecx
0x14007d977  lea     rcx, [rbp+410h+var_480]; void *
0x14007d97b  mov     [rbp+410h+var_60], rax
0x14007d982  movups  [rbp+410h+Storage], xmm0
0x14007d989  movups  [rbp+410h+var_70], xmm0
0x14007d990  call    memset
0x14007d995  mov     edi, [rbx+18h]
0x14007d998  lea     r8, [rbp+410h+Storage]; Storage
0x14007d99f  mov     eax, 28h ; '('
0x14007d9a4  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x14007d9ac  cmp     edi, eax
0x14007d9ae  mov     r9d, 1; AlignMultiple
0x14007d9b4  mov     rcx, rbx; NetBuffer
0x14007d9b7  cmova   edi, eax
0x14007d9ba  mov     edx, edi; BytesNeeded
0x14007d9bc  call    cs:__imp_NdisGetDataBuffer
0x14007d9c3  nop     dword ptr [rax+rax+00h]
0x14007d9c8  mov     r8, rax
0x14007d9cb  test    rax, rax
0x14007d9ce  jz      loc_14007DDFA
0x14007d9d4  lea     rax, [rsp+510h+var_4A8]
0x14007d9d9  mov     r9d, edi
0x14007d9dc  mov     [rsp+510h+var_4B8], rax
0x14007d9e1  mov     edx, esi
0x14007d9e3  lea     rax, [rsp+510h+var_49C]
0x14007d9e8  mov     rcx, r13
0x14007d9eb  mov     [rsp+510h+var_4C0], rax
0x14007d9f0  lea     rax, [rsp+510h+var_4B0]
0x14007d9f5  mov     [rsp+510h+var_4C8], rax
0x14007d9fa  lea     rax, [rsp+510h+BytesNeeded]
0x14007d9ff  mov     [rsp+510h+var_4D0], rax
0x14007da04  mov     eax, [rbx+18h]
0x14007da07  mov     [rsp+510h+var_4D8], r12
0x14007da0c  mov     [rsp+510h+var_4E0], r15
0x14007da11  mov     qword ptr [rsp+510h+Priority], r14
0x14007da16  mov     [rsp+510h+AlignOffset], eax
0x14007da1a  call    IpSecEspInitInbound
0x14007da1f  test    eax, eax
0x14007da21  js      loc_14007DD54
0x14007da27  mov     esi, [rsp+510h+BytesNeeded]
0x14007da2b  test    esi, esi
0x14007da2d  jz      loc_14007DE53
0x14007da33  mov     ecx, [rbx+18h]
0x14007da36  mov     edi, ecx
0x14007da38  sub     edi, esi
0x14007da3a  jz      short loc_14007DA59
0x14007da3c  mov     rax, [rbx+8]
0x14007da40  mov     edx, [rbx+10h]
0x14007da43  add     edx, edi
0x14007da45  cmp     edx, [rax+28h]
0x14007da48  jnb     loc_14007DCEE
0x14007da4e  add     [rbx+28h], edi
0x14007da51  sub     ecx, edi
0x14007da53  mov     [rbx+10h], edx
0x14007da56  mov     [rbx+18h], ecx
0x14007da59  mov     r9d, 1; AlignMultiple
0x14007da5f  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x14007da67  lea     r8, [rbp+410h+var_58]; Storage
0x14007da6e  mov     edx, esi; BytesNeeded
0x14007da70  mov     rcx, rbx; NetBuffer
0x14007da73  call    cs:__imp_NdisGetDataBuffer
0x14007da7a  nop     dword ptr [rax+rax+00h]
0x14007da7f  mov     ecx, [rbx+10h]
0x14007da82  mov     r15, rax
0x14007da85  cmp     ecx, edi
0x14007da87  jb      loc_14007DD60
0x14007da8d  sub     [rbx+28h], edi
0x14007da90  sub     ecx, edi
0x14007da92  add     [rbx+18h], edi
0x14007da95  mov     [rbx+10h], ecx
0x14007da98  sub     [rbx+18h], esi
0x14007da9b  add     [rbx+58h], esi
0x14007da9e  cmp     byte ptr [rsp+510h+var_4B0], 0
0x14007daa3  jz      short loc_14007DB09
0x14007daa5  mov     r14, [rbx+8]
0x14007daa9  test    r14, r14
0x14007daac  jz      loc_14007DDFA
0x14007dab2  test    byte ptr [r14+0Ah], 5
0x14007dab7  mov     esi, [rbx+18h]
0x14007daba  mov     r12d, [rbx+10h]
0x14007dabe  jz      loc_14007DE24
0x14007dac4  mov     rax, [r14+18h]
0x14007dac8  test    rax, rax
0x14007dacb  jz      loc_14007DE0A
0x14007dad1  mov     edi, [r14+28h]
0x14007dad5  lea     rdx, [rax+r12]
0x14007dad9  sub     edi, r12d
0x14007dadc  cmp     esi, edi
0x14007dade  cmovb   edi, esi
0x14007dae1  mov     r8d, edi
0x14007dae4  mov     rcx, r13
0x14007dae7  call    IpSecEspAuthInbound
0x14007daec  sub     esi, edi
0x14007daee  test    esi, esi
0x14007daf0  jnz     loc_14007DD26
0x14007daf6  mov     rdx, r15
0x14007daf9  mov     rcx, r13
0x14007dafc  call    IpSecEspAuthCompleteInbound
0x14007db01  test    eax, eax
0x14007db03  js      loc_14007DD54
0x14007db09  mov     r15d, [rsp+510h+var_4A8]
0x14007db0e  lea     edi, [r15+8]
0x14007db12  test    edi, edi
0x14007db14  jz      short loc_14007DB31
0x14007db16  mov     rax, [rbx+8]
0x14007db1a  mov     ecx, [rbx+10h]
0x14007db1d  add     ecx, edi
0x14007db1f  cmp     ecx, [rax+28h]
0x14007db22  jnb     loc_14007DD0A
0x14007db28  add     [rbx+28h], edi
0x14007db2b  sub     [rbx+18h], edi
0x14007db2e  mov     [rbx+10h], ecx
0x14007db31  movzx   r14d, byte ptr [rsp+510h+var_4B0+1]
0x14007db37  mov     esi, [rbx+28h]
0x14007db3a  mov     edx, [rbx+18h]
0x14007db3d  mov     [rsp+510h+var_4A8], edi
0x14007db41  test    r14b, r14b
0x14007db44  jz      loc_14007DDDF
0x14007db4a  mov     r9d, [rsp+510h+var_49C]
0x14007db4f  lea     rax, [rsp+510h+var_4A8]
0x14007db54  mov     qword ptr [rsp+510h+Priority], rax
0x14007db59  lea     rcx, IpSecEspDecryptInbound
0x14007db60  mov     [rsp+510h+AlignOffset], edx
0x14007db64  mov     r8, rbx
0x14007db67  mov     rdx, r13
0x14007db6a  call    IppEspProcessPacket
0x14007db6f  test    eax, eax
0x14007db71  js      loc_14007DD54
0x14007db77  mov     eax, [rbx+10h]
0x14007db7a  cmp     eax, 2
0x14007db7d  jb      loc_14007DDBC
0x14007db83  add     dword ptr [rbx+28h], 0FFFFFFFEh
0x14007db87  add     eax, 0FFFFFFFEh
0x14007db8a  add     dword ptr [rbx+18h], 2
0x14007db8e  mov     [rbx+10h], eax
0x14007db91  mov     r12d, [rsp+510h+var_4A8]
0x14007db96  add     r12d, 0FFFFFFFEh
0x14007db9a  lea     rdx, [rsp+510h+var_4AC]
0x14007db9f  mov     rcx, r13
0x14007dba2  call    IPsecGetEspTrailerFromNblInfo
0x14007dba7  test    al, al
0x14007dba9  jnz     loc_14007DE1A
0x14007dbaf  mov     r9d, 1; AlignMultiple
0x14007dbb5  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x14007dbbd  lea     r8, [rsp+510h+var_4AC]; Storage
0x14007dbc2  mov     edx, 2; BytesNeeded
0x14007dbc7  mov     rcx, rbx; NetBuffer
0x14007dbca  call    cs:__imp_NdisGetDataBuffer
0x14007dbd1  nop     dword ptr [rax+rax+00h]
0x14007dbd6  mov     rdi, rax
0x14007dbd9  mov     r8d, [rbx+28h]
0x14007dbdd  mov     edx, r8d
0x14007dbe0  movzx   ecx, byte ptr [rdi]
0x14007dbe3  sub     edx, esi
0x14007dbe5  cmp     ecx, edx
0x14007dbe7  ja      loc_14007DDFA
0x14007dbed  mov     rax, [rsp+510h+var_498]
0x14007dbf2  sub     r8w, si
0x14007dbf6  add     r8w, 9
0x14007dbfb  add     r8w, [rax]
0x14007dbff  mov     rax, [rbp+410h+var_490]
0x14007dc03  mov     [rax], r8w
0x14007dc07  movzx   edx, byte ptr [rdi]; DataOffsetDelta
0x14007dc0a  mov     eax, [rbx+10h]
0x14007dc0d  cmp     eax, edx
0x14007dc0f  jb      loc_14007DD80
0x14007dc15  sub     [rbx+28h], edx
0x14007dc18  sub     eax, edx
0x14007dc1a  add     [rbx+18h], edx
0x14007dc1d  mov     [rbx+10h], eax
0x14007dc20  movzx   edx, byte ptr [rdi]; BytesNeeded
0x14007dc23  sub     r12d, edx
0x14007dc26  test    r14b, r14b
0x14007dc29  jz      short loc_14007DC66
0x14007dc2b  mov     r9d, 1; AlignMultiple
0x14007dc31  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x14007dc39  lea     r8, [rbp+410h+var_480]; Storage
0x14007dc3d  mov     rcx, rbx; NetBuffer
0x14007dc40  call    cs:__imp_NdisGetDataBuffer
0x14007dc47  nop     dword ptr [rax+rax+00h]
0x14007dc4c  movzx   r8d, byte ptr [rdi]
0x14007dc50  mov     r9d, r12d
0x14007dc53  mov     rdx, rax
0x14007dc56  mov     rcx, r13
0x14007dc59  call    IpSecEspDecryptCompleteInbound
0x14007dc5e  test    eax, eax
0x14007dc60  js      loc_14007DD54
0x14007dc66  mov     edx, [rbx+28h]
0x14007dc69  mov     eax, [rbx+10h]
0x14007dc6c  sub     edx, esi; DataOffsetDelta
0x14007dc6e  cmp     eax, edx
0x14007dc70  jb      loc_14007DD9E
0x14007dc76  sub     eax, edx
0x14007dc78  mov     [rbx+28h], esi
0x14007dc7b  add     [rbx+18h], edx
0x14007dc7e  mov     [rbx+10h], eax
0x14007dc81  movzx   eax, byte ptr [rdi]
0x14007dc84  mov     r8, [rbp+410h+var_488]
0x14007dc88  add     eax, 2
0x14007dc8b  sub     [rbx+18h], eax
0x14007dc8e  add     [rbx+58h], eax
0x14007dc91  movzx   eax, byte ptr [rdi+1]
0x14007dc95  mov     rcx, [rsp+510h+var_498]
0x14007dc9a  mov     [r8], eax
0x14007dc9d  lea     eax, [r15+8]
0x14007dca1  add     [rcx], eax
0x14007dca3  mov     eax, 2
0x14007dca8  cmp     ax, [rsp+510h+var_4A4]
0x14007dcad  jnz     short loc_14007DCC3
0x14007dcaf  mov     ecx, [r8]
0x14007dcb2  mov     rdx, r13
0x14007dcb5  call    IPSecNsProcessInboundSecurePacket
0x14007dcba  test    rax, rax
0x14007dcbd  jnz     loc_14007DE8A
0x14007dcc3  mov     rcx, [rbp+410h+var_38]
0x14007dcca  xor     rcx, rsp; StackCookie
0x14007dccd  call    __security_check_cookie
0x14007dcd2  mov     rbx, [rsp+510h+arg_8]
0x14007dcda  add     rsp, 4E0h
0x14007dce1  pop     r15
0x14007dce3  pop     r14
0x14007dce5  pop     r13
0x14007dce7  pop     r12
0x14007dce9  pop     rdi
0x14007dcea  pop     rsi
0x14007dceb  pop     rbp
0x14007dcec  retn
0x14007dcee  xor     r9d, r9d; FreeMdlHandler
0x14007dcf1  xor     r8d, r8d; FreeMdl
0x14007dcf4  mov     edx, edi; DataOffsetDelta
0x14007dcf6  mov     rcx, rbx; NetBuffer
0x14007dcf9  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14007dd00  nop     dword ptr [rax+rax+00h]
0x14007dd05  jmp     loc_14007DA59
0x14007dd0a  xor     r9d, r9d; FreeMdlHandler
0x14007dd0d  xor     r8d, r8d; FreeMdl
0x14007dd10  mov     edx, edi; DataOffsetDelta
0x14007dd12  mov     rcx, rbx; NetBuffer
0x14007dd15  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x14007dd1c  nop     dword ptr [rax+rax+00h]
0x14007dd21  jmp     loc_14007DB31
0x14007dd26  mov     r14, [r14]
0x14007dd29  mov     edi, esi
0x14007dd2b  mov     eax, [r14+28h]
0x14007dd2f  cmp     esi, eax
0x14007dd31  cmovnb  edi, eax
0x14007dd34  test    byte ptr [r14+0Ah], 5
0x14007dd39  jz      loc_14007DE5B
0x14007dd3f  mov     rax, [r14+18h]
0x14007dd43  test    rax, rax
0x14007dd46  jz      loc_14007DE0A
0x14007dd4c  mov     rdx, rax
0x14007dd4f  jmp     loc_14007DAE1
0x14007dd54  mov     [r13+8Ch], eax
0x14007dd5b  jmp     loc_14007DCC3
0x14007dd60  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14007dd67  xor     r8d, r8d; DataBackFill
0x14007dd6a  mov     edx, edi; DataOffsetDelta
0x14007dd6c  mov     rcx, rbx; NetBuffer
0x14007dd6f  call    cs:__imp_NdisRetreatNetBufferDataStart
0x14007dd76  nop     dword ptr [rax+rax+00h]
0x14007dd7b  jmp     loc_14007DA98
0x14007dd80  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x14007dd87  xor     r8d, r8d; DataBackFill
0x14007dd8a  mov     rcx, rbx; NetBuffer
  ... truncated ...
```
