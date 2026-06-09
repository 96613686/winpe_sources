# IppReceiveEspNbl

- ea: `0x140061cc0`
- end: `0x14006227a`
- name: `IppReceiveEspNbl`
- size: `1466`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140060a5c`
- `0x140194870`

## callees

- `0x140061cc0`
- `0x140062280`
- `0x140062890`
- `0x140062aa0`
- `0x1400632f0`
- `0x1401bf4d0`
- `0x1401bfa80`
- `0x1402743b0`
- `0x14027506c`
- `0x1402750ac`
- `0x1402754d0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140062222`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140062259`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140062222`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140062259`
- `NETIO!NetioAllocateMdl` at `0x140062140`
- `NETIO!NetioAllocateMdl` at `0x140062160`
- `NETIO!NetioAllocateMdl` at `0x14006217e`
- `NETIO!NetioAllocateMdl` at `0x14006219c`
- `NDIS!NdisGetDataBuffer` at `0x140061d9c`
- `NDIS!NdisGetDataBuffer` at `0x140061e53`
- `NDIS!NdisGetDataBuffer` at `0x140061faa`
- `NDIS!NdisGetDataBuffer` at `0x140062020`
- `NDIS!NdisGetDataBuffer` at `0x140061d9c`
- `NDIS!NdisGetDataBuffer` at `0x140061e53`
- `NDIS!NdisGetDataBuffer` at `0x140061faa`
- `NDIS!NdisGetDataBuffer` at `0x140062020`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400620d9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400620f5`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400620d9`
- `NDIS!NdisAdvanceNetBufferDataStart` at `0x1400620f5`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006214f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006216d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006218b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400621ae`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006214f`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006216d`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x14006218b`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400621ae`

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
0x140061cc0  mov     [rsp-8+arg_8], rbx
0x140061cc5  push    rbp
0x140061cc6  push    rsi
0x140061cc7  push    rdi
0x140061cc8  push    r12
0x140061cca  push    r13
0x140061ccc  push    r14
0x140061cce  push    r15
0x140061cd0  lea     rbp, [rsp-3E0h]
0x140061cd8  sub     rsp, 4E0h
0x140061cdf  mov     rax, cs:__security_cookie
0x140061ce6  xor     rax, rsp
0x140061ce9  mov     [rbp+410h+var_38], rax
0x140061cf0  mov     rbx, [rcx+8]
0x140061cf4  mov     r13, rcx
0x140061cf7  mov     rax, [rbp+410h+arg_30]
0x140061cfe  xor     ecx, ecx
0x140061d00  mov     r15, [rbp+410h+arg_20]
0x140061d07  xorps   xmm0, xmm0
0x140061d0a  mov     r12, [rbp+410h+arg_28]
0x140061d11  mov     esi, r8d
0x140061d14  mov     [rsp+510h+var_498], rax
0x140061d19  mov     r8d, 400h; Size
0x140061d1f  mov     rax, [rbp+410h+arg_38]
0x140061d26  mov     r14, r9
0x140061d29  mov     [rbp+410h+var_490], rax
0x140061d2d  mov     rax, [rbp+410h+arg_40]
0x140061d34  mov     [rbp+410h+var_488], rax
0x140061d38  xor     eax, eax
0x140061d3a  mov     [rsp+510h+var_4A4], dx
0x140061d3f  xor     edx, edx; Val
0x140061d41  mov     [rsp+510h+var_4B0], cx
0x140061d46  mov     [rsp+510h+var_49C], ecx
0x140061d4a  mov     [rsp+510h+var_4A8], ecx
0x140061d4e  mov     [rsp+510h+var_4AC], cx
0x140061d53  mov     [rsp+510h+BytesNeeded], ecx
0x140061d57  lea     rcx, [rbp+410h+var_480]; void *
0x140061d5b  mov     [rbp+410h+var_60], rax
0x140061d62  movups  [rbp+410h+Storage], xmm0
0x140061d69  movups  [rbp+410h+var_70], xmm0
0x140061d70  call    memset
0x140061d75  mov     edi, [rbx+18h]
0x140061d78  lea     r8, [rbp+410h+Storage]; Storage
0x140061d7f  mov     eax, 28h ; '('
0x140061d84  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061d8c  cmp     edi, eax
0x140061d8e  mov     r9d, 1; AlignMultiple
0x140061d94  mov     rcx, rbx; NetBuffer
0x140061d97  cmova   edi, eax
0x140061d9a  mov     edx, edi; BytesNeeded
0x140061d9c  call    cs:__imp_NdisGetDataBuffer
0x140061da3  nop     dword ptr [rax+rax+00h]
0x140061da8  mov     r8, rax
0x140061dab  test    rax, rax
0x140061dae  jz      loc_1400621DA
0x140061db4  lea     rax, [rsp+510h+var_4A8]
0x140061db9  mov     r9d, edi
0x140061dbc  mov     [rsp+510h+var_4B8], rax
0x140061dc1  mov     edx, esi
0x140061dc3  lea     rax, [rsp+510h+var_49C]
0x140061dc8  mov     rcx, r13
0x140061dcb  mov     [rsp+510h+var_4C0], rax
0x140061dd0  lea     rax, [rsp+510h+var_4B0]
0x140061dd5  mov     [rsp+510h+var_4C8], rax
0x140061dda  lea     rax, [rsp+510h+BytesNeeded]
0x140061ddf  mov     [rsp+510h+var_4D0], rax
0x140061de4  mov     eax, [rbx+18h]
0x140061de7  mov     [rsp+510h+var_4D8], r12
0x140061dec  mov     [rsp+510h+var_4E0], r15
0x140061df1  mov     qword ptr [rsp+510h+Priority], r14
0x140061df6  mov     [rsp+510h+AlignOffset], eax
0x140061dfa  call    IpSecEspInitInbound
0x140061dff  test    eax, eax
0x140061e01  js      loc_140062134
0x140061e07  mov     esi, [rsp+510h+BytesNeeded]
0x140061e0b  test    esi, esi
0x140061e0d  jz      loc_140062233
0x140061e13  mov     ecx, [rbx+18h]
0x140061e16  mov     edi, ecx
0x140061e18  sub     edi, esi
0x140061e1a  jz      short loc_140061E39
0x140061e1c  mov     rax, [rbx+8]
0x140061e20  mov     edx, [rbx+10h]
0x140061e23  add     edx, edi
0x140061e25  cmp     edx, [rax+28h]
0x140061e28  jnb     loc_1400620CE
0x140061e2e  add     [rbx+28h], edi
0x140061e31  sub     ecx, edi
0x140061e33  mov     [rbx+10h], edx
0x140061e36  mov     [rbx+18h], ecx
0x140061e39  mov     r9d, 1; AlignMultiple
0x140061e3f  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061e47  lea     r8, [rbp+410h+var_58]; Storage
0x140061e4e  mov     edx, esi; BytesNeeded
0x140061e50  mov     rcx, rbx; NetBuffer
0x140061e53  call    cs:__imp_NdisGetDataBuffer
0x140061e5a  nop     dword ptr [rax+rax+00h]
0x140061e5f  mov     ecx, [rbx+10h]
0x140061e62  mov     r15, rax
0x140061e65  cmp     ecx, edi
0x140061e67  jb      loc_140062140
0x140061e6d  sub     [rbx+28h], edi
0x140061e70  sub     ecx, edi
0x140061e72  add     [rbx+18h], edi
0x140061e75  mov     [rbx+10h], ecx
0x140061e78  sub     [rbx+18h], esi
0x140061e7b  add     [rbx+58h], esi
0x140061e7e  cmp     byte ptr [rsp+510h+var_4B0], 0
0x140061e83  jz      short loc_140061EE9
0x140061e85  mov     r14, [rbx+8]
0x140061e89  test    r14, r14
0x140061e8c  jz      loc_1400621DA
0x140061e92  test    byte ptr [r14+0Ah], 5
0x140061e97  mov     esi, [rbx+18h]
0x140061e9a  mov     r12d, [rbx+10h]
0x140061e9e  jz      loc_140062204
0x140061ea4  mov     rax, [r14+18h]
0x140061ea8  test    rax, rax
0x140061eab  jz      loc_1400621EA
0x140061eb1  mov     edi, [r14+28h]
0x140061eb5  lea     rdx, [rax+r12]
0x140061eb9  sub     edi, r12d
0x140061ebc  cmp     esi, edi
0x140061ebe  cmovb   edi, esi
0x140061ec1  mov     r8d, edi
0x140061ec4  mov     rcx, r13
0x140061ec7  call    IpSecEspAuthInbound
0x140061ecc  sub     esi, edi
0x140061ece  test    esi, esi
0x140061ed0  jnz     loc_140062106
0x140061ed6  mov     rdx, r15
0x140061ed9  mov     rcx, r13
0x140061edc  call    IpSecEspAuthCompleteInbound
0x140061ee1  test    eax, eax
0x140061ee3  js      loc_140062134
0x140061ee9  mov     r15d, [rsp+510h+var_4A8]
0x140061eee  lea     edi, [r15+8]
0x140061ef2  test    edi, edi
0x140061ef4  jz      short loc_140061F11
0x140061ef6  mov     rax, [rbx+8]
0x140061efa  mov     ecx, [rbx+10h]
0x140061efd  add     ecx, edi
0x140061eff  cmp     ecx, [rax+28h]
0x140061f02  jnb     loc_1400620EA
0x140061f08  add     [rbx+28h], edi
0x140061f0b  sub     [rbx+18h], edi
0x140061f0e  mov     [rbx+10h], ecx
0x140061f11  movzx   r14d, byte ptr [rsp+510h+var_4B0+1]
0x140061f17  mov     esi, [rbx+28h]
0x140061f1a  mov     edx, [rbx+18h]
0x140061f1d  mov     [rsp+510h+var_4A8], edi
0x140061f21  test    r14b, r14b
0x140061f24  jz      loc_1400621BF
0x140061f2a  mov     r9d, [rsp+510h+var_49C]
0x140061f2f  lea     rax, [rsp+510h+var_4A8]
0x140061f34  mov     qword ptr [rsp+510h+Priority], rax
0x140061f39  lea     rcx, IpSecEspDecryptInbound
0x140061f40  mov     [rsp+510h+AlignOffset], edx
0x140061f44  mov     r8, rbx
0x140061f47  mov     rdx, r13
0x140061f4a  call    IppEspProcessPacket
0x140061f4f  test    eax, eax
0x140061f51  js      loc_140062134
0x140061f57  mov     eax, [rbx+10h]
0x140061f5a  cmp     eax, 2
0x140061f5d  jb      loc_14006219C
0x140061f63  add     dword ptr [rbx+28h], 0FFFFFFFEh
0x140061f67  add     eax, 0FFFFFFFEh
0x140061f6a  add     dword ptr [rbx+18h], 2
0x140061f6e  mov     [rbx+10h], eax
0x140061f71  mov     r12d, [rsp+510h+var_4A8]
0x140061f76  add     r12d, 0FFFFFFFEh
0x140061f7a  lea     rdx, [rsp+510h+var_4AC]
0x140061f7f  mov     rcx, r13
0x140061f82  call    IPsecGetEspTrailerFromNblInfo
0x140061f87  test    al, al
0x140061f89  jnz     loc_1400621FA
0x140061f8f  mov     r9d, 1; AlignMultiple
0x140061f95  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140061f9d  lea     r8, [rsp+510h+var_4AC]; Storage
0x140061fa2  mov     edx, 2; BytesNeeded
0x140061fa7  mov     rcx, rbx; NetBuffer
0x140061faa  call    cs:__imp_NdisGetDataBuffer
0x140061fb1  nop     dword ptr [rax+rax+00h]
0x140061fb6  mov     rdi, rax
0x140061fb9  mov     r8d, [rbx+28h]
0x140061fbd  mov     edx, r8d
0x140061fc0  movzx   ecx, byte ptr [rdi]
0x140061fc3  sub     edx, esi
0x140061fc5  cmp     ecx, edx
0x140061fc7  ja      loc_1400621DA
0x140061fcd  mov     rax, [rsp+510h+var_498]
0x140061fd2  sub     r8w, si
0x140061fd6  add     r8w, 9
0x140061fdb  add     r8w, [rax]
0x140061fdf  mov     rax, [rbp+410h+var_490]
0x140061fe3  mov     [rax], r8w
0x140061fe7  movzx   edx, byte ptr [rdi]; DataOffsetDelta
0x140061fea  mov     eax, [rbx+10h]
0x140061fed  cmp     eax, edx
0x140061fef  jb      loc_140062160
0x140061ff5  sub     [rbx+28h], edx
0x140061ff8  sub     eax, edx
0x140061ffa  add     [rbx+18h], edx
0x140061ffd  mov     [rbx+10h], eax
0x140062000  movzx   edx, byte ptr [rdi]; BytesNeeded
0x140062003  sub     r12d, edx
0x140062006  test    r14b, r14b
0x140062009  jz      short loc_140062046
0x14006200b  mov     r9d, 1; AlignMultiple
0x140062011  mov     [rsp+510h+AlignOffset], 0; AlignOffset
0x140062019  lea     r8, [rbp+410h+var_480]; Storage
0x14006201d  mov     rcx, rbx; NetBuffer
0x140062020  call    cs:__imp_NdisGetDataBuffer
0x140062027  nop     dword ptr [rax+rax+00h]
0x14006202c  movzx   r8d, byte ptr [rdi]
0x140062030  mov     r9d, r12d
0x140062033  mov     rdx, rax
0x140062036  mov     rcx, r13
0x140062039  call    IpSecEspDecryptCompleteInbound
0x14006203e  test    eax, eax
0x140062040  js      loc_140062134
0x140062046  mov     edx, [rbx+28h]
0x140062049  mov     eax, [rbx+10h]
0x14006204c  sub     edx, esi; DataOffsetDelta
0x14006204e  cmp     eax, edx
0x140062050  jb      loc_14006217E
0x140062056  sub     eax, edx
0x140062058  mov     [rbx+28h], esi
0x14006205b  add     [rbx+18h], edx
0x14006205e  mov     [rbx+10h], eax
0x140062061  movzx   eax, byte ptr [rdi]
0x140062064  mov     r8, [rbp+410h+var_488]
0x140062068  add     eax, 2
0x14006206b  sub     [rbx+18h], eax
0x14006206e  add     [rbx+58h], eax
0x140062071  movzx   eax, byte ptr [rdi+1]
0x140062075  mov     rcx, [rsp+510h+var_498]
0x14006207a  mov     [r8], eax
0x14006207d  lea     eax, [r15+8]
0x140062081  add     [rcx], eax
0x140062083  mov     eax, 2
0x140062088  cmp     ax, [rsp+510h+var_4A4]
0x14006208d  jnz     short loc_1400620A3
0x14006208f  mov     ecx, [r8]
0x140062092  mov     rdx, r13
0x140062095  call    IPSecNsProcessInboundSecurePacket
0x14006209a  test    rax, rax
0x14006209d  jnz     loc_14006226A
0x1400620a3  mov     rcx, [rbp+410h+var_38]
0x1400620aa  xor     rcx, rsp; StackCookie
0x1400620ad  call    __security_check_cookie
0x1400620b2  mov     rbx, [rsp+510h+arg_8]
0x1400620ba  add     rsp, 4E0h
0x1400620c1  pop     r15
0x1400620c3  pop     r14
0x1400620c5  pop     r13
0x1400620c7  pop     r12
0x1400620c9  pop     rdi
0x1400620ca  pop     rsi
0x1400620cb  pop     rbp
0x1400620cc  retn
0x1400620ce  xor     r9d, r9d; FreeMdlHandler
0x1400620d1  xor     r8d, r8d; FreeMdl
0x1400620d4  mov     edx, edi; DataOffsetDelta
0x1400620d6  mov     rcx, rbx; NetBuffer
0x1400620d9  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400620e0  nop     dword ptr [rax+rax+00h]
0x1400620e5  jmp     loc_140061E39
0x1400620ea  xor     r9d, r9d; FreeMdlHandler
0x1400620ed  xor     r8d, r8d; FreeMdl
0x1400620f0  mov     edx, edi; DataOffsetDelta
0x1400620f2  mov     rcx, rbx; NetBuffer
0x1400620f5  call    cs:__imp_NdisAdvanceNetBufferDataStart
0x1400620fc  nop     dword ptr [rax+rax+00h]
0x140062101  jmp     loc_140061F11
0x140062106  mov     r14, [r14]
0x140062109  mov     edi, esi
0x14006210b  mov     eax, [r14+28h]
0x14006210f  cmp     esi, eax
0x140062111  cmovnb  edi, eax
0x140062114  test    byte ptr [r14+0Ah], 5
0x140062119  jz      loc_14006223B
0x14006211f  mov     rax, [r14+18h]
0x140062123  test    rax, rax
0x140062126  jz      loc_1400621EA
0x14006212c  mov     rdx, rax
0x14006212f  jmp     loc_140061EC1
0x140062134  mov     [r13+8Ch], eax
0x14006213b  jmp     loc_1400620A3
0x140062140  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140062147  xor     r8d, r8d; DataBackFill
0x14006214a  mov     edx, edi; DataOffsetDelta
0x14006214c  mov     rcx, rbx; NetBuffer
0x14006214f  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140062156  nop     dword ptr [rax+rax+00h]
0x14006215b  jmp     loc_140061E78
0x140062160  mov     r9, cs:__imp_NetioAllocateMdl; AllocateMdlHandler
0x140062167  xor     r8d, r8d; DataBackFill
0x14006216a  mov     rcx, rbx; NetBuffer
  ... truncated ...
```
