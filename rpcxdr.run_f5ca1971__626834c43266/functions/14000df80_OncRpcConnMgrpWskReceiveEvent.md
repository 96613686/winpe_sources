# OncRpcConnMgrpWskReceiveEvent

- ea: `0x14000df80`
- end: `0x14000e8d1`
- name: `OncRpcConnMgrpWskReceiveEvent`
- size: `2385`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x140001020`
- `0x140001340`
- `0x1400020c0`
- `0x140002104`
- `0x1400021e8`
- `0x140002974`
- `0x140002b30`
- `0x140005794`
- `0x140006798`
- `0x140008034`
- `0x14000d7a4`
- `0x14000d828`
- `0x14000d894`
- `0x14000dec0`
- `0x14000df80`
- `0x14000eee0`
- `0x14000ef3c`
- `0x14000ef88`
- `0x14000f04c`
- `0x14000f0c0`
- `0x14000fabc`
- `0x14000fce4`
- `0x140015640`
- `0x140015680`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x14000e466`
- `ntoskrnl!EtwEventEnabled` at `0x14000e466`
- `ntoskrnl!EtwWrite` at `0x14000e4b0`
- `ntoskrnl!EtwWrite` at `0x14000e4b0`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskReceiveEvent(
        __int64 a1,
        __int64 a2,
        ULONGLONG a3,
        unsigned __int64 a4,
        unsigned __int64 *a5)
{
  int v5; // ebx
  unsigned __int64 v6; // r12
  ULONGLONG v8; // r14
  unsigned __int64 v10; // r13
  __int64 v11; // rax
  unsigned __int64 v12; // rsi
  unsigned __int32 v13; // eax
  unsigned __int64 v14; // r14
  __int64 v15; // r13
  int v16; // ebx
  char v17; // si
  unsigned __int64 v19; // rdx
  __int64 v20; // rsi
  unsigned __int64 v21; // rbx
  int v22; // eax
  unsigned int CurrentAllocationLengthRemaining; // eax
  int v24; // r9d
  __int64 v25; // r15
  __int64 v26; // r13
  __int64 *v27; // rbx
  int v28; // eax
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // r8
  __int64 v32; // r8
  __int64 v33; // r10
  __int64 v34; // rbx
  unsigned __int64 v35; // r9
  int v36; // eax
  unsigned int v37; // eax
  __int64 v38; // r10
  unsigned int v39; // r11d
  __int64 v40; // r8
  _QWORD *v41; // rax
  int v42; // r8d
  __int64 v43; // rcx
  int v44; // r15d
  __int64 v45; // rax
  unsigned int v46; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v47; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int64 v48; // [rsp+50h] [rbp-30h]
  __int64 v49; // [rsp+58h] [rbp-28h]
  unsigned __int64 *v50; // [rsp+60h] [rbp-20h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-18h] BYREF

  v5 = 0;
  v6 = 0;
  UserData.Ptr = a3;
  v50 = a5;
  v8 = a3;
  v46 = 0;
  v10 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 22, a3, a4);
  if ( !v8 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids);
    v5 = -1073741285;
  }
  while ( 1 )
  {
    if ( v5 < 0 )
      goto LABEL_35;
    if ( v6 >= a4 )
      goto LABEL_129;
    v11 = *(unsigned int *)(a1 + 168);
    v12 = v10;
    if ( 4 - v11 < v10 )
      v12 = 4 - v11;
    v5 = OncRpcConnMgrpWskCopyIndicationListToBuffer(v8, v6, v12, (int)a1 + (int)v11 + 172, 4 - v11);
    if ( v5 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_iiid(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, a3, v6, v12, *(unsigned int *)(a1 + 168), v5);
    }
    *(_DWORD *)(a1 + 168) += v12;
    v6 += v12;
    if ( *(_DWORD *)(a1 + 168) < 4u )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 25, a3, *(unsigned int *)(a1 + 168));
      if ( v5 < 0 )
      {
LABEL_35:
        v17 = 0;
        goto LABEL_36;
      }
      goto LABEL_129;
    }
    v13 = _byteswap_ulong(*(_DWORD *)(a1 + 172));
    v14 = v13;
    *(_DWORD *)(a1 + 168) = 0;
    a3 = (unsigned int)dword_14001A3EC;
    LODWORD(v14) = v13 & 0x7FFFFFFF;
    if ( v14 >= (unsigned int)dword_14001A3EC )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_ii(
          WPP_GLOBAL_Control->AttachedDevice,
          26,
          (unsigned int)dword_14001A3EC,
          v14,
          (unsigned int)dword_14001A3EC);
      goto LABEL_34;
    }
    v10 -= v12;
    v48 = v10;
    v49 = v13 >> 31;
    if ( v14 )
      break;
    LODWORD(v8) = UserData.Ptr;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids);
  }
  v15 = a1 + 160;
  if ( !*(_QWORD *)(a1 + 160) )
  {
    v16 = OncRpcWiMgrpSrvWorkItemAlloc(0, a1, a1 + 160);
    if ( v16 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        28,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)v16);
    }
    if ( v16 == -1073741756 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, a1);
      v17 = 1;
      v5 = -1073741285;
      goto LABEL_36;
    }
    if ( v16 < 0 )
    {
LABEL_34:
      v5 = -1073741285;
      goto LABEL_35;
    }
    *(_QWORD *)(a1 + 144) = 0;
    *(_BYTE *)(a1 + 152) = 0;
    *(_DWORD *)(a1 + 156) = 0;
  }
  LogOncrpcEvent(&ONCRPC_EVENT_WSK_INDICATION, (LPCGUID)(*(_QWORD *)v15 + 2444LL));
  v19 = *(_QWORD *)(a1 + 144);
  v20 = *(_QWORD *)v15 + 128LL;
  v47 = v20;
  v21 = ((unsigned int)dword_14001A3F4 - v19) & -(__int64)(v19 < (unsigned int)dword_14001A3F4);
  if ( !byte_14001A3FC
    && *(_QWORD *)(a1 + 120)
    && !*(_BYTE *)(a1 + 152)
    && v14 > (unsigned int)dword_14001A3F8
    && v21
    && v48 > v21 )
  {
    if ( (unsigned int)OncRpcBufMgrGetCurrentAllocationLengthRemaining(v20) < v21 )
    {
      v22 = OncRpcBufMgrAllocate((unsigned int)&v47, v21, 16, 0, 0);
      if ( v22 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            30,
            WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
            (unsigned int)v22);
        }
        goto LABEL_57;
      }
      v20 = v47;
    }
    CurrentAllocationLengthRemaining = OncRpcBufMgrGetCurrentAllocationLengthRemaining(v20);
    OncRpcConnMgrpWskCopyIndicationListToBuffer(UserData.Ptr, v6, v21, v24, CurrentAllocationLengthRemaining);
    v25 = *(_QWORD *)(v20 + 40);
    if ( v25 )
      v26 = *(_QWORD *)(v25 + 64);
    else
      v26 = 0;
    *(_QWORD *)(v25 + 64) += v21;
    v27 = (__int64 *)(a1 + 160);
    if ( !(unsigned __int8)OncRpcMsgIsEligibleForPayLoadIndication(*(_QWORD *)(a1 + 160) + 96LL, a1 + 156) )
    {
      *(_QWORD *)(v25 + 64) = v26;
      v15 = a1 + 160;
      goto LABEL_93;
    }
    *(_BYTE *)(a1 + 152) = 1;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids);
    v28 = OncRpcMsgDecodeHeader(*v27 + 96);
    v30 = (unsigned int)v28;
    if ( v28 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          32,
          WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
          (unsigned int)v28);
      v5 = 0;
    }
    else
    {
      if ( RegHandle && EtwEventEnabled(RegHandle, &ONCRPC_EVENT_NFS_SERVER_INDICATION) )
      {
        v31 = *v27;
        *(_QWORD *)&UserData.Size = 4;
        UserData.Ptr = v31 + 356;
        EtwWrite(RegHandle, &ONCRPC_EVENT_NFS_SERVER_INDICATION, (LPCGUID)(v31 + 2444), 1u, &UserData);
      }
      v5 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *, __int64))(a1 + 120))(a1, *v27 + 96, &v46, v30);
    }
    *(_QWORD *)(v25 + 64) = v26;
    v15 = a1 + 160;
    *(_DWORD *)(*(_QWORD *)(a1 + 160) + 352LL) &= ~1u;
    if ( v5 == -1073741285 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids);
LABEL_58:
      v17 = 0;
LABEL_36:
      if ( *(_QWORD *)(a1 + 160) )
      {
        OncRpcWiMgrSrvWorkItemFree();
        *(_QWORD *)(a1 + 160) = 0;
      }
      if ( !v17 && *(_DWORD *)(a1 + 80) != 5 )
        OncRpcConnMgrpConnectionDisconnectBySystem(a1);
      goto LABEL_41;
    }
    if ( v5 == -1073741802 )
    {
      if ( (unsigned __int64)(v46 + *(_DWORD *)(a1 + 156)) >= *(_QWORD *)(a1 + 144)
        && *(_QWORD *)(v20 + 40) == OncRpcBufMgrGetNextBufferDescriptor(v20, v25) )
      {
        *(_QWORD *)(a1 + 144) = v32;
        *(_QWORD *)(v25 + 64) += v32 - v33;
        v6 += v32 - v33;
        v14 -= v32 - v33;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        {
          WPP_SF_iiii(WPP_GLOBAL_Control->AttachedDevice);
        }
      }
      else
      {
        v46 = 0;
      }
      goto LABEL_93;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_di(WPP_GLOBAL_Control->AttachedDevice, 35, v29, (unsigned int)v5, v46);
    if ( v46 )
    {
LABEL_57:
      v5 = -1073741285;
      goto LABEL_58;
    }
  }
LABEL_93:
  if ( (unsigned int)OncRpcBufMgrGetCurrentAllocationLengthRemaining(v20) )
    v34 = *(_QWORD *)(v20 + 40);
  else
    v34 = 0;
  v35 = v14 + *(_QWORD *)(a1 + 144);
  if ( v35 > (unsigned int)dword_14001A3F0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_ii(
        WPP_GLOBAL_Control->AttachedDevice,
        36,
        (unsigned int)dword_14001A3F0,
        v35,
        (unsigned int)dword_14001A3F0);
    goto LABEL_57;
  }
  if ( (unsigned int)OncRpcBufMgrGetCurrentAllocationLengthRemaining(v20) < v14 )
  {
    v36 = OncRpcBufMgrGetCurrentAllocationLengthRemaining(v20);
    if ( (int)OncRpcBufMgrAllocate((unsigned int)&v47, (int)v14 - v36, 0, 0, 0) < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      {
        v37 = OncRpcBufMgrGetCurrentAllocationLengthRemaining(v47);
        WPP_SF_di(*(_QWORD *)(v38 + 24), 37, v40, v39, v14 - v37);
      }
      goto LABEL_57;
    }
    v20 = v47;
  }
  if ( !v34 )
    v34 = *(_QWORD *)(v20 + 40);
  v41 = (_QWORD *)OncRpcConnMgrpWskBuildMdlForRemainingBuffer(v34);
  v43 = *(_QWORD *)(v20 + 40);
  v44 = (int)v41;
  if ( v34 != v43 )
    *v41 = OncRpcConnMgrpWskBuildMdlForRemainingBuffer(v43);
  v45 = *(_QWORD *)(v20 + 48);
  if ( !v45 )
  {
    v45 = OncRpcConnMgrpWskCompletionContextAlloc();
    if ( !v45 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids);
      goto LABEL_57;
    }
  }
  *(_BYTE *)(v45 + 32) = v49;
  *(_QWORD *)(v45 + 8) = v34;
  *(_QWORD *)(v45 + 48) = OncRpcConnMgrpConnectionReceivePostIrpCompletionCallback;
  *(_QWORD *)(v45 + 16) = v20;
  *(_QWORD *)(v45 + 24) = v14;
  *(_QWORD *)(v45 + 56) = a1;
  v5 = OncRpcConnMgrpWskReceive(a1, v44, v42, v14, v45);
  if ( v5 == 259 )
  {
    v5 = 0;
  }
  else if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        39,
        WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids,
        (unsigned int)v5);
    *(_QWORD *)v15 = 0;
    goto LABEL_57;
  }
LABEL_129:
  *v50 = v6;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    return (unsigned int)v5;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_i(WPP_GLOBAL_Control->AttachedDevice, 40, a3, v6);
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids, (unsigned int)v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14000df80  mov     [rsp-38h+arg_8], rbx
0x14000df85  push    rbp
0x14000df86  push    rsi
0x14000df87  push    rdi
0x14000df88  push    r12
0x14000df8a  push    r13
0x14000df8c  push    r14
0x14000df8e  push    r15
0x14000df90  mov     rbp, rsp
0x14000df93  sub     rsp, 80h
0x14000df9a  mov     rax, cs:__security_cookie
0x14000dfa1  xor     rax, rsp
0x14000dfa4  mov     [rbp+var_8], rax
0x14000dfa8  mov     rax, [rbp+arg_20]
0x14000dfac  xor     ebx, ebx
0x14000dfae  xor     r12d, r12d
0x14000dfb1  mov     [rbp+var_18.Ptr], r8
0x14000dfb5  xor     sil, sil
0x14000dfb8  mov     [rbp+var_20], rax
0x14000dfbc  mov     [rbp+var_40], sil
0x14000dfc0  mov     r15, r9
0x14000dfc3  mov     r14, r8
0x14000dfc6  mov     [rbp+var_3C], ebx
0x14000dfc9  mov     rdi, rcx
0x14000dfcc  mov     r13, r9
0x14000dfcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfd6  lea     r9, WPP_GLOBAL_Control
0x14000dfdd  cmp     rcx, r9
0x14000dfe0  jz      short loc_14000DFFF
0x14000dfe2  mov     eax, [rcx+2Ch]
0x14000dfe5  test    al, 1
0x14000dfe7  jz      short loc_14000DFFF
0x14000dfe9  mov     rcx, [rcx+18h]
0x14000dfed  lea     edx, [rbx+16h]
0x14000dff0  mov     r9, r13
0x14000dff3  call    WPP_SF_i
0x14000dff8  lea     r9, WPP_GLOBAL_Control
0x14000dfff  test    r14, r14
0x14000e002  jnz     short loc_14000E030
0x14000e004  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e00b  cmp     rcx, r9
0x14000e00e  jz      short loc_14000E02B
0x14000e010  mov     eax, [rcx+2Ch]
0x14000e013  test    al, 10h
0x14000e015  jz      short loc_14000E02B
0x14000e017  mov     rcx, [rcx+18h]
0x14000e01b  lea     edx, [r14+17h]
0x14000e01f  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e026  call    WPP_SF_
0x14000e02b  mov     ebx, 0C000021Bh
0x14000e030  test    ebx, ebx
0x14000e032  js      loc_14000E1F8
0x14000e038  cmp     r12, r15
0x14000e03b  jnb     loc_14000E892
0x14000e041  mov     eax, [rdi+0A8h]
0x14000e047  mov     ecx, 4
0x14000e04c  sub     rcx, rax
0x14000e04f  mov     rsi, r13
0x14000e052  cmp     rcx, r13
0x14000e055  mov     [rsp+80h+UserData], rcx
0x14000e05a  mov     rdx, r12
0x14000e05d  cmovb   rsi, rcx
0x14000e061  lea     r9, [rax+0ACh]
0x14000e068  mov     r8, rsi
0x14000e06b  add     r9, rdi
0x14000e06e  mov     rcx, r14
0x14000e071  call    OncRpcConnMgrpWskCopyIndicationListToBuffer
0x14000e076  mov     ebx, eax
0x14000e078  mov     r14d, eax
0x14000e07b  test    eax, eax
0x14000e07d  jns     short loc_14000E0BA
0x14000e07f  mov     rdx, cs:WPP_GLOBAL_Control
0x14000e086  lea     r9, WPP_GLOBAL_Control
0x14000e08d  cmp     rdx, r9
0x14000e090  jz      short loc_14000E0C1
0x14000e092  mov     ecx, [rdx+2Ch]
0x14000e095  test    cl, 10h
0x14000e098  jz      short loc_14000E0C1
0x14000e09a  mov     eax, [rdi+0A8h]
0x14000e0a0  mov     r9, r12
0x14000e0a3  mov     rcx, [rdx+18h]
0x14000e0a7  mov     dword ptr [rsp+80h+var_50], ebx
0x14000e0ab  mov     [rsp+80h+var_58], rax
0x14000e0b0  mov     [rsp+80h+UserData], rsi
0x14000e0b5  call    WPP_SF_iiid
0x14000e0ba  lea     r9, WPP_GLOBAL_Control
0x14000e0c1  add     [rdi+0A8h], esi
0x14000e0c7  add     r12, rsi
0x14000e0ca  mov     edx, [rdi+0A8h]
0x14000e0d0  cmp     edx, 4
0x14000e0d3  jb      loc_14000E865
0x14000e0d9  mov     eax, [rdi+0ACh]
0x14000e0df  bswap   eax
0x14000e0e1  mov     r14d, eax
0x14000e0e4  mov     dword ptr [rdi+0A8h], 0
0x14000e0ee  mov     r8d, cs:dword_14001A3EC
0x14000e0f5  btr     r14d, 1Fh
0x14000e0fa  cmp     r14, r8
0x14000e0fd  jnb     loc_14000E82F
0x14000e103  sub     r13, rsi
0x14000e106  shr     eax, 1Fh
0x14000e109  mov     [rbp+var_30], r13
0x14000e10d  mov     [rbp+var_28], rax
0x14000e111  test    r14, r14
0x14000e114  jnz     short loc_14000E14F
0x14000e116  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e11d  mov     r14, [rbp+var_18.Ptr]
0x14000e121  cmp     rcx, r9
0x14000e124  jz      loc_14000E030
0x14000e12a  mov     eax, [rcx+2Ch]
0x14000e12d  test    al, 10h
0x14000e12f  jz      loc_14000E030
0x14000e135  mov     rcx, [rcx+18h]
0x14000e139  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e140  mov     edx, 1Bh
0x14000e145  call    WPP_SF_
0x14000e14a  jmp     loc_14000E030
0x14000e14f  lea     r13, [rdi+0A0h]
0x14000e156  cmp     qword ptr [r13+0], 0
0x14000e15b  jnz     loc_14000E2A3
0x14000e161  mov     r8, r13
0x14000e164  mov     rdx, rdi
0x14000e167  xor     ecx, ecx
0x14000e169  call    OncRpcWiMgrpSrvWorkItemAlloc
0x14000e16e  mov     ebx, eax
0x14000e170  test    eax, eax
0x14000e172  jns     short loc_14000E1A7
0x14000e174  mov     rax, cs:WPP_GLOBAL_Control
0x14000e17b  lea     rdx, WPP_GLOBAL_Control
0x14000e182  cmp     rax, rdx
0x14000e185  jz      short loc_14000E1AE
0x14000e187  mov     ecx, [rax+2Ch]
0x14000e18a  test    cl, 10h
0x14000e18d  jz      short loc_14000E1AE
0x14000e18f  mov     rcx, [rax+18h]
0x14000e193  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e19a  mov     edx, 1Ch
0x14000e19f  mov     r9d, ebx
0x14000e1a2  call    WPP_SF_d
0x14000e1a7  lea     rdx, WPP_GLOBAL_Control
0x14000e1ae  cmp     ebx, 0C0000044h
0x14000e1b4  jnz     short loc_14000E1EB
0x14000e1b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e1bd  cmp     rcx, rdx
0x14000e1c0  jz      short loc_14000E1E1
0x14000e1c2  mov     eax, [rcx+2Ch]
0x14000e1c5  test    al, 10h
0x14000e1c7  jz      short loc_14000E1E1
0x14000e1c9  mov     rcx, [rcx+18h]
0x14000e1cd  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e1d4  mov     edx, 1Dh
0x14000e1d9  mov     r9, rdi
0x14000e1dc  call    WPP_SF_q
0x14000e1e1  mov     sil, 1
0x14000e1e4  mov     ebx, 0C000021Bh
0x14000e1e9  jmp     short loc_14000E1FC
0x14000e1eb  test    ebx, ebx
0x14000e1ed  jns     loc_14000E287
0x14000e1f3  mov     ebx, 0C000021Bh
0x14000e1f8  mov     sil, [rbp+var_40]
0x14000e1fc  lea     r15, WPP_GLOBAL_Control
0x14000e203  mov     rcx, [rdi+0A0h]
0x14000e20a  test    rcx, rcx
0x14000e20d  jz      short loc_14000E21F
0x14000e20f  call    OncRpcWiMgrSrvWorkItemFree
0x14000e214  mov     qword ptr [rdi+0A0h], 0
0x14000e21f  test    sil, sil
0x14000e222  jnz     short loc_14000E232
0x14000e224  cmp     dword ptr [rdi+50h], 5
0x14000e228  jz      short loc_14000E232
0x14000e22a  mov     rcx, rdi
0x14000e22d  call    OncRpcConnMgrpConnectionDisconnectBySystem
0x14000e232  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e239  cmp     rcx, r15
0x14000e23c  jz      short loc_14000E25D
0x14000e23e  mov     eax, [rcx+2Ch]
0x14000e241  test    al, 1
0x14000e243  jz      short loc_14000E25D
0x14000e245  mov     rcx, [rcx+18h]
0x14000e249  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e250  mov     edx, 29h ; ')'
0x14000e255  mov     r9d, ebx
0x14000e258  call    WPP_SF_d
0x14000e25d  mov     eax, ebx
0x14000e25f  mov     rcx, [rbp+var_8]
0x14000e263  xor     rcx, rsp; StackCookie
0x14000e266  call    __security_check_cookie
0x14000e26b  mov     rbx, [rsp+80h+arg_8]
0x14000e273  add     rsp, 80h
0x14000e27a  pop     r15
0x14000e27c  pop     r14
0x14000e27e  pop     r13
0x14000e280  pop     r12
0x14000e282  pop     rdi
0x14000e283  pop     rsi
0x14000e284  pop     rbp
0x14000e285  retn
0x14000e287  mov     qword ptr [rdi+90h], 0
0x14000e292  mov     byte ptr [rdi+98h], 0
0x14000e299  mov     dword ptr [rdi+9Ch], 0
0x14000e2a3  mov     rdx, [r13+0]
0x14000e2a7  lea     rcx, ONCRPC_EVENT_WSK_INDICATION; EventDescriptor
0x14000e2ae  add     rdx, 98Ch; ActivityId
0x14000e2b5  call    LogOncrpcEvent
0x14000e2ba  mov     ecx, cs:dword_14001A3F4
0x14000e2c0  mov     rdx, [rdi+90h]
0x14000e2c7  mov     eax, ecx
0x14000e2c9  mov     rsi, [r13+0]
0x14000e2cd  sub     rax, rdx
0x14000e2d0  sub     rsi, 0FFFFFFFFFFFFFF80h
0x14000e2d4  cmp     rdx, rcx
0x14000e2d7  mov     [rbp+var_38], rsi
0x14000e2db  sbb     rbx, rbx
0x14000e2de  and     rbx, rax
0x14000e2e1  cmp     cs:byte_14001A3FC, 0
0x14000e2e8  jnz     loc_14000E644
0x14000e2ee  cmp     qword ptr [rdi+78h], 0
0x14000e2f3  jz      loc_14000E644
0x14000e2f9  cmp     byte ptr [rdi+98h], 0
0x14000e300  jnz     loc_14000E644
0x14000e306  mov     eax, cs:dword_14001A3F8
0x14000e30c  cmp     r14, rax
0x14000e30f  jbe     loc_14000E644
0x14000e315  test    rbx, rbx
0x14000e318  jz      loc_14000E644
0x14000e31e  cmp     [rbp+var_30], rbx
0x14000e322  jbe     loc_14000E644
0x14000e328  mov     rcx, rsi
0x14000e32b  call    OncRpcBufMgrGetCurrentAllocationLengthRemaining
0x14000e330  mov     r9d, eax
0x14000e333  cmp     r9, rbx
0x14000e336  jnb     short loc_14000E39D
0x14000e338  xor     r9d, r9d
0x14000e33b  mov     [rsp+80h+UserData], 0
0x14000e344  mov     edx, ebx
0x14000e346  lea     rcx, [rbp+var_38]
0x14000e34a  lea     r8d, [r9+10h]
0x14000e34e  call    OncRpcBufMgrAllocate
0x14000e353  test    eax, eax
0x14000e355  jns     short loc_14000E399
0x14000e357  mov     r10, cs:WPP_GLOBAL_Control
0x14000e35e  lea     r15, WPP_GLOBAL_Control
0x14000e365  cmp     r10, r15
0x14000e368  jz      short loc_14000E38B
0x14000e36a  mov     ecx, [r10+2Ch]
0x14000e36e  test    cl, 10h
0x14000e371  jz      short loc_14000E38B
0x14000e373  mov     rcx, [r10+18h]
0x14000e377  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e37e  mov     edx, 1Eh
0x14000e383  mov     r9d, eax
0x14000e386  call    WPP_SF_d
0x14000e38b  mov     ebx, 0C000021Bh
0x14000e390  mov     sil, [rbp+var_40]
0x14000e394  jmp     loc_14000E203
0x14000e399  mov     rsi, [rbp+var_38]
0x14000e39d  mov     rax, [rsi+28h]
0x14000e3a1  test    rax, rax
0x14000e3a4  jnz     short loc_14000E3AB
0x14000e3a6  xor     r9d, r9d
0x14000e3a9  jmp     short loc_14000E3AF
0x14000e3ab  mov     r9, [rax+40h]
0x14000e3af  mov     rcx, rsi
0x14000e3b2  call    OncRpcBufMgrGetCurrentAllocationLengthRemaining
0x14000e3b7  mov     rcx, [rbp+var_18.Ptr]
0x14000e3bb  mov     r8, rbx
0x14000e3be  mov     r10d, eax
0x14000e3c1  mov     rdx, r12
0x14000e3c4  mov     [rsp+80h+UserData], r10
0x14000e3c9  call    OncRpcConnMgrpWskCopyIndicationListToBuffer
0x14000e3ce  mov     r15, [rsi+28h]
0x14000e3d2  test    r15, r15
0x14000e3d5  jnz     short loc_14000E3DC
0x14000e3d7  xor     r13d, r13d
0x14000e3da  jmp     short loc_14000E3E0
0x14000e3dc  mov     r13, [r15+40h]
0x14000e3e0  add     [r15+40h], rbx
0x14000e3e4  lea     rdx, [rdi+9Ch]
0x14000e3eb  lea     rbx, [rdi+0A0h]
0x14000e3f2  mov     rcx, [rbx]
0x14000e3f5  add     rcx, 60h ; '`'
0x14000e3f9  call    OncRpcMsgIsEligibleForPayLoadIndication
0x14000e3fe  test    al, al
0x14000e400  jz      loc_14000E639
0x14000e406  mov     byte ptr [rdi+98h], 1
0x14000e40d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e414  lea     rax, WPP_GLOBAL_Control
0x14000e41b  cmp     rcx, rax
0x14000e41e  jz      short loc_14000E43C
0x14000e420  mov     eax, [rcx+2Ch]
0x14000e423  test    al, 10h
0x14000e425  jz      short loc_14000E43C
0x14000e427  mov     rcx, [rcx+18h]
0x14000e42b  lea     r8, WPP_ea71b91709de3d359d9afa6debb6deb4_Traceguids
0x14000e432  mov     edx, 1Fh
0x14000e437  call    WPP_SF_
0x14000e43c  mov     rcx, [rbx]
0x14000e43f  add     rcx, 60h ; '`'
0x14000e443  call    OncRpcMsgDecodeHeader
0x14000e448  mov     r9d, eax
  ... truncated ...
```
