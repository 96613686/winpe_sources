# SrvNetAllocateEndpointCommon

- ea: `0x140042864`
- end: `0x140043056`
- name: `SrvNetAllocateEndpointCommon`
- size: `2034`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140051778`

## callees

- `0x140007c60`
- `0x140007ec0`
- `0x14000ce00`
- `0x14000d800`
- `0x14000e784`
- `0x14000ec20`
- `0x140010394`
- `0x14001389c`
- `0x140015790`
- `0x140015c14`
- `0x140015c80`
- `0x140016384`
- `0x1400163d8`
- `0x1400167b0`
- `0x140016c84`
- `0x14001efa4`
- `0x14001f728`
- `0x14002a3e0`
- `0x14002a540`
- `0x14002a840`
- `0x140042864`
- `0x140045788`
- `0x140046198`
- `0x1400475bc`
- `0x1400495ac`

## import_xrefs

- `ntoskrnl!RtlDeleteHashTable` at `0x140042ac9`
- `ntoskrnl!RtlDeleteHashTable` at `0x140042ac9`
- `ntoskrnl!KeInitializeSpinLock` at `0x140042ade`
- `ntoskrnl!KeInitializeSpinLock` at `0x140042ade`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140042e05`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140042e05`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042dba`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140042dba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140042d9e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140042d9e`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140042a04`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140042a7c`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140042a04`
- `ntoskrnl!RtlCreateHashTableEx` at `0x140042a7c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140042df9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140042df9`

## pseudocode

```c
__int64 __fastcall SrvNetAllocateEndpointCommon(
        unsigned __int16 *a1,
        const void **a2,
        const void **a3,
        _OWORD *a4,
        char a5,
        char a6,
        int a7,
        unsigned int a8,
        __int16 *a9,
        __int64 a10)
{
  __int16 DefaultPortForTransportType; // di
  int v12; // r8d
  const void **v13; // r10
  const void **v14; // r11
  int v15; // r9d
  unsigned int v17; // r12d
  __int64 PoolWithTag; // rax
  __int64 v19; // r8
  __int64 v20; // rbx
  struct _RTL_DYNAMIC_HASH_TABLE *v21; // r13
  _OWORD *v22; // rax
  const void **v23; // rdx
  void *v24; // rcx
  __int16 v25; // ax
  const void **v26; // rdx
  void *v27; // rcx
  __int16 v28; // ax
  int v29; // eax
  int v30; // eax
  int v31; // edi
  int Listener; // eax
  unsigned int i; // edi
  __int64 *v34; // rdx
  PERESOURCE v35; // rdx
  PVOID *p_Reserved2; // rax
  PERESOURCE *Address; // rcx
  __int64 v38; // rdx
  int v39; // edx
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // [rsp+50h] [rbp-B0h] BYREF
  const void **v42; // [rsp+58h] [rbp-A8h]
  const void **v43; // [rsp+60h] [rbp-A0h]
  _OWORD *v44; // [rsp+68h] [rbp-98h]
  __int64 v45; // [rsp+70h] [rbp-90h]
  _QWORD v46[16]; // [rsp+80h] [rbp-80h] BYREF

  v45 = a10;
  v44 = a4;
  v43 = a3;
  v42 = a2;
  DefaultPortForTransportType = SrvNetGetDefaultPortForTransportType(a8);
  if ( a9 )
  {
    if ( *((unsigned __int8 *)a9 + 2) != a8 )
      __int2c();
    DefaultPortForTransportType = *a9;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    LOBYTE(v12) = a5 != 0 ? 89 : 78;
    WPP_SF_ZZZDcc(
      WPP_GLOBAL_Control->AttachedDevice,
      17,
      v12,
      (_DWORD)a1,
      (__int64)v13,
      (__int64)v14,
      a7,
      v12,
      a6 != 0 ? 89 : 78);
    v13 = v42;
    v14 = v43;
  }
  v15 = SrvNetEnabledTransports;
  if ( !_bittest(&v15, a8) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_8d73355e5e233ce540e4603b97b45138_Traceguids,
        (unsigned int)SrvNetEnabledTransports);
    }
    return 3221225506LL;
  }
  v17 = 0;
  PoolWithTag = SrvNetAllocatePoolWithTag(
                  64,
                  *(unsigned __int16 *)v13 + *a1 + 448LL + *(unsigned __int16 *)v14,
                  1717719884);
  v20 = PoolWithTag;
  if ( !PoolWithTag )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids);
    }
    v31 = -1073741670;
    goto LABEL_86;
  }
  v21 = (struct _RTL_DYNAMIC_HASH_TABLE *)(PoolWithTag + 288);
  v41 = PoolWithTag + 288;
  if ( a5 )
  {
    if ( !(unsigned __int8)RtlCreateHashTableEx(&v41, 128, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, v20);
      }
LABEL_22:
      SrvNetWskNotifyCleanupProviderContext(v20);
      return 3221225626LL;
    }
    v41 = v20 + 328;
    if ( !(unsigned __int8)RtlCreateHashTableEx(&v41, 128, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, v20);
      }
      RtlDeleteHashTable(v21);
      goto LABEL_22;
    }
  }
  KeInitializeSpinLock((PKSPIN_LOCK)(v20 + 24));
  *(_QWORD *)(v20 + 216) = v20 + 208;
  *(_QWORD *)(v20 + 208) = v20 + 208;
  *(_QWORD *)(v20 + 232) = v20 + 224;
  *(_QWORD *)(v20 + 224) = v20 + 224;
  *(_QWORD *)(v20 + 248) = v20 + 240;
  *(_QWORD *)(v20 + 240) = v20 + 240;
  *(_QWORD *)(v20 + 264) = v20 + 256;
  *(_QWORD *)(v20 + 256) = v20 + 256;
  *(_QWORD *)(v20 + 280) = v20 + 272;
  *(_QWORD *)(v20 + 272) = v20 + 272;
  *(_WORD *)(v20 + 145) = 0;
  *(_DWORD *)(v20 + 16) = 1;
  *(_DWORD *)(v20 + 124) = a8;
  *(_QWORD *)(v20 + 368) = a9;
  *(_DWORD *)(v20 + 172) = SrvNetMaxConnections;
  *(_DWORD *)(v20 + 160) = SrvNetMinFreeConnections;
  *(_DWORD *)(v20 + 164) = SrvNetMaxFreeConnections;
  *(_DWORD *)(v20 + 156) = a7;
  *(_DWORD *)(v20 + 180) = SrvNetMaxUnAuthenticatedConnections;
  *(_BYTE *)(v20 + 120) = a5;
  v22 = v44;
  *(_BYTE *)(v20 + 121) = a6;
  *(_OWORD *)(v20 + 128) = *v22;
  *(_BYTE *)(v20 + 144) = 0;
  LOWORD(v22) = *a1;
  *(_WORD *)(v20 + 74) = *a1;
  *(_WORD *)(v20 + 72) = (_WORD)v22;
  *(_QWORD *)(v20 + 80) = v20 + 448;
  memmove((void *)(v20 + 448), *((const void **)a1 + 1), *a1);
  v23 = v42;
  v24 = (void *)(*(_QWORD *)(v20 + 80) + *(unsigned __int16 *)(v20 + 72));
  v25 = *(_WORD *)v42;
  *(_WORD *)(v20 + 90) = *(_WORD *)v42;
  *(_WORD *)(v20 + 88) = v25;
  *(_QWORD *)(v20 + 96) = v24;
  memmove(v24, v23[1], *(unsigned __int16 *)v23);
  v26 = v43;
  v27 = (void *)(*(_QWORD *)(v20 + 96) + *(unsigned __int16 *)(v20 + 88));
  v28 = *(_WORD *)v43;
  *(_WORD *)(v20 + 106) = *(_WORD *)v43;
  *(_WORD *)(v20 + 104) = v28;
  *(_QWORD *)(v20 + 112) = v27;
  memmove(v27, v26[1], *(unsigned __int16 *)v26);
  if ( !*(_DWORD *)(v20 + 180) )
  {
    v29 = SrvNetCalculateMaxUnAuthenticatedConnections(v20);
    if ( v29 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          21,
          WPP_8d73355e5e233ce540e4603b97b45138_Traceguids,
          (unsigned int)v29);
      }
      *(_DWORD *)(v20 + 180) = 10;
    }
  }
  switch ( a8 )
  {
    case 1u:
      if ( !a6 )
      {
        memset(v46, 0, sizeof(v46));
        LOWORD(v46[0]) = 23;
        HIDWORD(v46[0]) = 0;
        memset(&v46[1], 0, 20);
        WORD1(v46[0]) = __ROR2__(DefaultPortForTransportType, 8);
        v30 = SrvNetWskOpenListenSocket(v20, v46);
        v31 = v30;
        if ( v30 >= 0 )
        {
          SrvNetSetInterfaceEndpoint(v20);
          goto LABEL_51;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_8d73355e5e233ce540e4603b97b45138_Traceguids,
            (unsigned int)v30);
        }
        goto LABEL_65;
      }
      v31 = 0;
LABEL_50:
      if ( v31 >= 0 )
      {
LABEL_51:
        if ( !*(_BYTE *)(v20 + 121) )
        {
          for ( i = 0; i < *(_DWORD *)(v20 + 160); ++i )
            SrvNetAllocateConnection(v20);
        }
        if ( v45 )
        {
          SrvNetReferenceEndpoint(v20);
          *v34 = v20;
        }
        if ( a9 )
          SrvNetReferenceListenerRuleEntry(a9);
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite((PERESOURCE)((char *)SrvNetDeviceExtension + 288), 1u);
        v35 = SrvNetDeviceExtension;
        p_Reserved2 = &SrvNetDeviceExtension[3].Reserved2;
        Address = (PERESOURCE *)SrvNetDeviceExtension[3].Address;
        if ( *Address != (PERESOURCE)&SrvNetDeviceExtension[3].Reserved2 )
          __fastfail(3u);
        *(_QWORD *)(v20 + 8) = Address;
        *(_QWORD *)v20 = p_Reserved2;
        *Address = (PERESOURCE)v20;
        p_Reserved2[1] = (PVOID)v20;
        ExReleaseResourceLite((PERESOURCE)((char *)v35 + 288));
        KeLeaveCriticalRegion();
        SrvNetReferenceDriver();
        LOBYTE(v38) = 1;
        SrvNetNotifyClientsOfEndpoint(v20, v38);
        v31 = 0;
        goto LABEL_70;
      }
      goto LABEL_65;
    case 2u:
      Listener = SrvNetRdmaCreateListener(v20, a1);
      v17 = *(_DWORD *)(v20 + 48);
LABEL_49:
      v31 = Listener;
      goto LABEL_50;
    case 4u:
      Listener = SrvNetQUICListenerOpen(v20, a1);
      goto LABEL_49;
  }
  v31 = -1073741811;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    goto LABEL_69;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, a8, -1073741811);
LABEL_65:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, a8, v31);
  }
LABEL_69:
  SrvNetWskNotifyCleanupProviderContext(v20);
  if ( v31 < 0 )
  {
LABEL_86:
    v40 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        27,
        WPP_8d73355e5e233ce540e4603b97b45138_Traceguids,
        (unsigned int)v31);
    }
    if ( a8 == 2 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100000) != 0 )
      McTemplateK0qd_EtwWriteTransfer(v40, SRV2_EVENT_RDMA_ENDPOINT_ALLOCATION_FAILURE, v19, v17, v31);
    goto LABEL_93;
  }
LABEL_70:
  if ( a5 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&SrvNetDeviceExtension[4].ExclusiveWaiters);
  }
  else if ( a6 )
  {
    _InterlockedIncrement((volatile signed __int32 *)&SrvNetDeviceExtension[4].ExclusiveWaiters + 1);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, a1);
  }
  if ( a8 == 2 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
    McTemplateK0qqhzr2_EtwWriteTransfer(*a1 >> 1, v39, v19, 1, v17, *a1 >> 1, *((_QWORD *)a1 + 1));
LABEL_93:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids, (unsigned int)v31);
  }
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x140042864  mov     [rsp-8+arg_18], rbx
0x140042869  push    rbp
0x14004286a  push    rsi
0x14004286b  push    rdi
0x14004286c  push    r12
0x14004286e  push    r13
0x140042870  push    r14
0x140042872  push    r15
0x140042874  lea     rbp, [rsp-10h]
0x140042879  sub     rsp, 110h
0x140042880  mov     rax, cs:__security_cookie
0x140042887  xor     rax, rsp
0x14004288a  mov     [rbp+40h+var_40], rax
0x14004288e  mov     rax, [rbp+40h+arg_48]
0x140042895  mov     r14, rcx
0x140042898  mov     esi, [rbp+40h+arg_38]
0x14004289e  mov     r11, r8
0x1400428a1  mov     r15, [rbp+40h+arg_40]
0x1400428a8  mov     ecx, esi
0x1400428aa  mov     [rsp+140h+var_D0], rax
0x1400428af  mov     r10, rdx
0x1400428b2  mov     [rsp+140h+var_D8], r9
0x1400428b7  mov     [rsp+140h+var_E0], r8
0x1400428bc  mov     [rsp+140h+var_E8], rdx
0x1400428c1  call    SrvNetGetDefaultPortForTransportType
0x1400428c6  movzx   edi, ax
0x1400428c9  test    r15, r15
0x1400428cc  jz      short loc_1400428DD
0x1400428ce  movzx   eax, byte ptr [r15+2]
0x1400428d3  cmp     eax, esi
0x1400428d5  jz      short loc_1400428D9
0x1400428d7  int     2Ch; Windows NT - assertion failure
0x1400428d9  movzx   edi, word ptr [r15]
0x1400428dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400428e4  lea     rax, WPP_GLOBAL_Control
0x1400428eb  mov     r13d, 100h
0x1400428f1  cmp     rcx, rax
0x1400428f4  jz      short loc_140042962
0x1400428f6  test    [rcx+2Ch], r13d
0x1400428fa  jz      short loc_14004295B
0x1400428fc  cmp     byte ptr [rcx+29h], 2
0x140042900  jb      short loc_14004295B
0x140042902  mov     al, [rbp+40h+arg_28]
0x140042905  mov     edx, 11h
0x14004290a  mov     rcx, [rcx+18h]
0x14004290e  neg     al
0x140042910  mov     al, [rbp+40h+arg_20]
0x140042913  sbb     r9b, r9b
0x140042916  and     r9b, 0Bh
0x14004291a  add     r9b, 4Eh ; 'N'
0x14004291e  mov     [rsp+140h+var_100], r9b
0x140042923  neg     al
0x140042925  mov     eax, [rbp+40h+arg_30]
0x14004292b  mov     r9, r14
0x14004292e  sbb     r8b, r8b
0x140042931  and     r8b, 0Bh
0x140042935  add     r8b, 4Eh ; 'N'
0x140042939  mov     [rsp+140h+var_108], r8b
0x14004293e  mov     dword ptr [rsp+140h+var_110], eax
0x140042942  mov     [rsp+140h+var_118], r11
0x140042947  mov     [rsp+140h+var_120], r10
0x14004294c  call    WPP_SF_ZZZDcc
0x140042951  mov     r10, [rsp+140h+var_E8]
0x140042956  mov     r11, [rsp+140h+var_E0]
0x14004295b  lea     rax, WPP_GLOBAL_Control
0x140042962  mov     r9d, cs:SrvNetEnabledTransports
0x140042969  bt      r9d, esi
0x14004296d  jb      short loc_1400429A6
0x14004296f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140042976  cmp     rcx, rax
0x140042979  jz      short loc_14004299C
0x14004297b  test    [rcx+2Ch], r13d
0x14004297f  jz      short loc_14004299C
0x140042981  cmp     byte ptr [rcx+29h], 2
0x140042985  jb      short loc_14004299C
0x140042987  mov     rcx, [rcx+18h]
0x14004298b  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140042992  mov     edx, 12h
0x140042997  call    WPP_SF_d
0x14004299c  mov     eax, 0C0000022h
0x1400429a1  jmp     loc_14004302E
0x1400429a6  movzx   ecx, word ptr [r14]
0x1400429aa  xor     r12d, r12d
0x1400429ad  movzx   eax, word ptr [r10]
0x1400429b1  add     rcx, 1C0h
0x1400429b8  movzx   edx, word ptr [r11]
0x1400429bc  add     rcx, rax
0x1400429bf  add     rdx, rcx
0x1400429c2  mov     r8d, 6662534Ch
0x1400429c8  lea     ecx, [r12+40h]
0x1400429cd  call    SrvNetAllocatePoolWithTag
0x1400429d2  mov     rbx, rax
0x1400429d5  test    rax, rax
0x1400429d8  jz      loc_140042F59
0x1400429de  lea     r13, [rax+120h]
0x1400429e5  mov     [rsp+140h+var_F0], r13
0x1400429ea  cmp     [rbp+40h+arg_20], r12b
0x1400429ee  jz      loc_140042ADA
0x1400429f4  xor     r9d, r9d
0x1400429f7  lea     rcx, [rsp+140h+var_F0]
0x1400429fc  xor     r8d, r8d
0x1400429ff  mov     edx, 80h
0x140042a04  call    cs:__imp_RtlCreateHashTableEx
0x140042a0b  nop     dword ptr [rax+rax+00h]
0x140042a10  test    al, al
0x140042a12  jnz     short loc_140042A60
0x140042a14  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140042a1b  lea     rax, WPP_GLOBAL_Control
0x140042a22  cmp     rcx, rax
0x140042a25  jz      short loc_140042A4E
0x140042a27  test    dword ptr [rcx+2Ch], 100h
0x140042a2e  jz      short loc_140042A4E
0x140042a30  cmp     byte ptr [rcx+29h], 1
0x140042a34  jb      short loc_140042A4E
0x140042a36  mov     rcx, [rcx+18h]
0x140042a3a  lea     edx, [r12+13h]
0x140042a3f  mov     r9, rbx
0x140042a42  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140042a49  call    WPP_SF_q
0x140042a4e  mov     rcx, rbx
0x140042a51  call    SrvNetWskNotifyCleanupProviderContext
0x140042a56  mov     eax, 0C000009Ah
0x140042a5b  jmp     loc_14004302E
0x140042a60  lea     rax, [rbx+148h]
0x140042a67  xor     r9d, r9d
0x140042a6a  xor     r8d, r8d
0x140042a6d  mov     [rsp+140h+var_F0], rax
0x140042a72  mov     edx, 80h
0x140042a77  lea     rcx, [rsp+140h+var_F0]
0x140042a7c  call    cs:__imp_RtlCreateHashTableEx
0x140042a83  nop     dword ptr [rax+rax+00h]
0x140042a88  test    al, al
0x140042a8a  jnz     short loc_140042ADA
0x140042a8c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140042a93  lea     rax, WPP_GLOBAL_Control
0x140042a9a  cmp     rcx, rax
0x140042a9d  jz      short loc_140042AC6
0x140042a9f  test    dword ptr [rcx+2Ch], 100h
0x140042aa6  jz      short loc_140042AC6
0x140042aa8  cmp     byte ptr [rcx+29h], 1
0x140042aac  jb      short loc_140042AC6
0x140042aae  mov     rcx, [rcx+18h]
0x140042ab2  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140042ab9  mov     edx, 14h
0x140042abe  mov     r9, rbx
0x140042ac1  call    WPP_SF_q
0x140042ac6  mov     rcx, r13; HashTable
0x140042ac9  call    cs:__imp_RtlDeleteHashTable
0x140042ad0  nop     dword ptr [rax+rax+00h]
0x140042ad5  jmp     loc_140042A4E
0x140042ada  lea     rcx, [rbx+18h]; SpinLock
0x140042ade  call    cs:__imp_KeInitializeSpinLock
0x140042ae5  nop     dword ptr [rax+rax+00h]
0x140042aea  mov     r13b, [rbp+40h+arg_28]
0x140042aee  lea     rax, [rbx+0D0h]
0x140042af5  mov     [rax+8], rax
0x140042af9  xor     ecx, ecx
0x140042afb  mov     [rax], rax
0x140042afe  lea     rax, [rbx+0E0h]
0x140042b05  mov     [rax+8], rax
0x140042b09  mov     [rax], rax
0x140042b0c  lea     rax, [rbx+0F0h]
0x140042b13  mov     [rax+8], rax
0x140042b17  mov     [rax], rax
0x140042b1a  lea     rax, [rbx+100h]
0x140042b21  mov     [rax+8], rax
0x140042b25  mov     [rax], rax
0x140042b28  lea     rax, [rbx+110h]
0x140042b2f  mov     [rax+8], rax
0x140042b33  mov     [rax], rax
0x140042b36  mov     [rbx+91h], cx
0x140042b3d  mov     dword ptr [rbx+10h], 1
0x140042b44  mov     [rbx+7Ch], esi
0x140042b47  mov     [rbx+170h], r15
0x140042b4e  mov     eax, cs:SrvNetMaxConnections
0x140042b54  mov     [rbx+0ACh], eax
0x140042b5a  mov     eax, cs:SrvNetMinFreeConnections
0x140042b60  mov     [rbx+0A0h], eax
0x140042b66  mov     eax, cs:SrvNetMaxFreeConnections
0x140042b6c  mov     [rbx+0A4h], eax
0x140042b72  mov     eax, [rbp+40h+arg_30]
0x140042b78  mov     [rbx+9Ch], eax
0x140042b7e  mov     eax, cs:SrvNetMaxUnAuthenticatedConnections
0x140042b84  mov     [rbx+0B4h], eax
0x140042b8a  mov     al, [rbp+40h+arg_20]
0x140042b8d  mov     [rbx+78h], al
0x140042b90  mov     rax, [rsp+140h+var_D8]
0x140042b95  mov     [rbx+79h], r13b
0x140042b99  movups  xmm0, xmmword ptr [rax]
0x140042b9c  movdqu  xmmword ptr [rbx+80h], xmm0
0x140042ba4  mov     [rbx+90h], cl
0x140042baa  lea     rcx, [rbx+1C0h]; void *
0x140042bb1  movzx   eax, word ptr [r14]
0x140042bb5  mov     [rbx+4Ah], ax
0x140042bb9  mov     [rbx+48h], ax
0x140042bbd  mov     [rbx+50h], rcx
0x140042bc1  movzx   r8d, word ptr [r14]; Size
0x140042bc5  mov     rdx, [r14+8]; Src
0x140042bc9  call    memmove
0x140042bce  mov     rdx, [rsp+140h+var_E8]
0x140042bd3  movzx   ecx, word ptr [rbx+48h]
0x140042bd7  add     rcx, [rbx+50h]; void *
0x140042bdb  movzx   eax, word ptr [rdx]
0x140042bde  mov     [rbx+5Ah], ax
0x140042be2  mov     [rbx+58h], ax
0x140042be6  mov     [rbx+60h], rcx
0x140042bea  movzx   r8d, word ptr [rdx]; Size
0x140042bee  mov     rdx, [rdx+8]; Src
0x140042bf2  call    memmove
0x140042bf7  mov     rdx, [rsp+140h+var_E0]
0x140042bfc  movzx   ecx, word ptr [rbx+58h]
0x140042c00  add     rcx, [rbx+60h]; void *
0x140042c04  movzx   eax, word ptr [rdx]
0x140042c07  mov     [rbx+6Ah], ax
0x140042c0b  mov     [rbx+68h], ax
0x140042c0f  mov     [rbx+70h], rcx
0x140042c13  movzx   r8d, word ptr [rdx]; Size
0x140042c17  mov     rdx, [rdx+8]; Src
0x140042c1b  call    memmove
0x140042c20  cmp     [rbx+0B4h], r12d
0x140042c27  jnz     short loc_140042C79
0x140042c29  mov     rcx, rbx
0x140042c2c  call    SrvNetCalculateMaxUnAuthenticatedConnections
0x140042c31  test    eax, eax
0x140042c33  jns     short loc_140042C79
0x140042c35  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140042c3c  lea     rdx, WPP_GLOBAL_Control
0x140042c43  cmp     rcx, rdx
0x140042c46  jz      short loc_140042C6F
0x140042c48  test    dword ptr [rcx+2Ch], 100h
0x140042c4f  jz      short loc_140042C6F
0x140042c51  cmp     byte ptr [rcx+29h], 1
0x140042c55  jb      short loc_140042C6F
0x140042c57  mov     rcx, [rcx+18h]
0x140042c5b  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140042c62  mov     edx, 15h
0x140042c67  mov     r9d, eax
0x140042c6a  call    WPP_SF_d
0x140042c6f  mov     dword ptr [rbx+0B4h], 0Ah
0x140042c79  cmp     esi, 1
0x140042c7c  jnz     loc_140042D26
0x140042c82  test    r13b, r13b
0x140042c85  jnz     loc_140042D22
0x140042c8b  xor     edx, edx; Val
0x140042c8d  lea     r8d, [rsi+7Fh]; Size
0x140042c91  lea     rcx, [rbp+40h+var_C0]; void *
0x140042c95  call    memset
0x140042c9a  lea     edx, [rsi+16h]
0x140042c9d  ror     di, 8
0x140042ca1  mov     [rbp+40h+var_C0], dx
0x140042ca5  xorps   xmm0, xmm0
0x140042ca8  lea     rdx, [rbp+40h+var_C0]
0x140042cac  mov     [rbp+40h+var_BC], r12d
0x140042cb0  mov     rcx, rbx
0x140042cb3  mov     [rbp+40h+var_A8], r12d
0x140042cb7  movups  [rbp+40h+var_B8], xmm0
0x140042cbb  mov     [rbp+40h+var_BE], di
0x140042cbf  call    SrvNetWskOpenListenSocket
0x140042cc4  mov     edi, eax
0x140042cc6  test    eax, eax
0x140042cc8  js      short loc_140042CD7
0x140042cca  mov     rcx, rbx
0x140042ccd  call    SrvNetSetInterfaceEndpoint
0x140042cd2  jmp     loc_140042D5A
0x140042cd7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140042cde  lea     r15, WPP_GLOBAL_Control
0x140042ce5  cmp     rcx, r15
0x140042ce8  jz      loc_140042E71
0x140042cee  test    dword ptr [rcx+2Ch], 100h
0x140042cf5  jz      loc_140042E71
0x140042cfb  cmp     byte ptr [rcx+29h], 1
0x140042cff  jb      loc_140042E71
0x140042d05  mov     rcx, [rcx+18h]
0x140042d09  lea     r8, WPP_8d73355e5e233ce540e4603b97b45138_Traceguids
0x140042d10  mov     edx, 16h
0x140042d15  mov     r9d, eax
0x140042d18  call    WPP_SF_d
0x140042d1d  jmp     loc_140042E71
0x140042d22  xor     edi, edi
0x140042d24  jmp     short loc_140042D52
0x140042d26  cmp     esi, 2
0x140042d29  jnz     short loc_140042D3C
0x140042d2b  mov     rdx, r14
0x140042d2e  mov     rcx, rbx
0x140042d31  call    SrvNetRdmaCreateListener
0x140042d36  mov     r12d, [rbx+30h]
0x140042d3a  jmp     short loc_140042D50
0x140042d3c  cmp     esi, 4
0x140042d3f  jnz     loc_140042E27
0x140042d45  mov     rdx, r14
0x140042d48  mov     rcx, rbx
0x140042d4b  call    SrvNetQUICListenerOpen
0x140042d50  mov     edi, eax
0x140042d52  test    edi, edi
0x140042d54  js      loc_140042E6A
0x140042d5a  cmp     byte ptr [rbx+79h], 0
0x140042d5e  jnz     short loc_140042D7C
0x140042d60  xor     edi, edi
0x140042d62  cmp     [rbx+0A0h], edi
0x140042d68  jbe     short loc_140042D7C
  ... truncated ...
```
