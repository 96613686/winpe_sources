# IpAttachIpsClient

- ea: `0x14018dd10`
- end: `0x14018e206`
- name: `IpAttachIpsClient`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140014a08`
- `0x1400f99d0`
- `0x140126284`
- `0x14012d708`
- `0x140154840`
- `0x14018dd10`
- `0x14018f618`
- `0x14018fd2c`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018dfae`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018dfae`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14018df65`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14018df65`
- `ntoskrnl!IoAllocateWorkItem` at `0x14018df30`
- `ntoskrnl!IoAllocateWorkItem` at `0x14018df30`
- `ntoskrnl!IoFreeWorkItem` at `0x14018dfc3`
- `ntoskrnl!IoFreeWorkItem` at `0x14018dfc3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018e162`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018e162`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018e01f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018e01f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018e156`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018e156`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018e031`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018e031`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dffe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018dffe`
- `ntoskrnl!ExAllocatePool2` at `0x14018dd87`
- `ntoskrnl!ExAllocatePool2` at `0x14018dd87`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018dfd8`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018dfd8`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14018defa`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14018defa`
- `NDIS!NdisFreeGenericObject` at `0x14018dfed`
- `NDIS!NdisFreeGenericObject` at `0x14018dfed`
- `NDIS!NdisAllocateGenericObject` at `0x14018de9c`
- `NDIS!NdisAllocateGenericObject` at `0x14018de9c`

## pseudocode

```c
__int64 __fastcall IpAttachIpsClient(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        _QWORD *a7)
{
  __int64 v7; // rsi
  __int64 Pool2; // rax
  __int64 v12; // r8
  _QWORD *v13; // rdi
  unsigned int v14; // ebx
  __int64 *v15; // r15
  unsigned __int16 v16; // cx
  char v17; // al
  char v18; // al
  PNDIS_GENERIC_OBJECT GenericObject; // rax
  __int64 v20; // r8
  const wchar_t *v21; // r9
  NDIS_HANDLE v22; // rax
  PIO_WORKITEM WorkItem; // rax
  PEX_RUNDOWN_REF_CACHE_AWARE CacheAwareRundownProtection; // rax
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v25; // rcx
  struct _IO_WORKITEM *v26; // rcx
  void *v27; // rcx
  struct _NDIS_GENERIC_OBJECT *v28; // rcx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  _NET_BUFFER_LIST_POOL_PARAMETERS Parameters; // [rsp+38h] [rbp-60h] BYREF
  int v34; // [rsp+48h] [rbp-50h]

  v7 = *(_QWORD *)(a3 + 32);
  v34 = 0;
  Parameters = 0;
  if ( v7 && *(_WORD *)v7 >= 2u )
  {
    Pool2 = ExAllocatePool2(64, 136, 1666404425);
    v13 = (_QWORD *)Pool2;
    if ( !Pool2 )
    {
      v14 = -1073741670;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
        McTemplateK0z_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          TCPIP_MEMORY_FAILURES,
          v12,
          L"IPS client (IPNG)");
      return v14;
    }
    *(_QWORD *)(Pool2 + 8) = Pool2;
    v15 = (__int64 *)(a2 - 19544);
    *(_QWORD *)Pool2 = Pool2;
    *(_DWORD *)(Pool2 + 24) = 1666404425;
    *(_QWORD *)(Pool2 + 16) = a2 - 19544;
    *(_QWORD *)(Pool2 + 80) = a5;
    *(_QWORD *)(Pool2 + 88) = a4;
    *(_QWORD *)(Pool2 + 112) = a1;
    *(_WORD *)(Pool2 + 60) = *(_WORD *)v7;
    *(_OWORD *)(Pool2 + 28) = *(_OWORD *)(v7 + 4);
    *(_OWORD *)(Pool2 + 44) = *(_OWORD *)(v7 + 20);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
    {
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids, Pool2 + 28);
    }
    v16 = *((_WORD *)v13 + 30);
    *((_BYTE *)v13 + 62) = *(_BYTE *)(v7 + 38);
    if ( v16 < 3u )
      v17 = 0;
    else
      v17 = *(_BYTE *)(v7 + 39);
    *((_BYTE *)v13 + 63) = v17;
    if ( v16 < 4u )
      v18 = 0;
    else
      v18 = *(_BYTE *)(v7 + 48);
    *((_BYTE *)v13 + 64) = v18;
    *((_BYTE *)v13 + 65) = *(_BYTE *)(v7 + 49);
    v13[16] = *(_QWORD *)(v7 + 40);
    GenericObject = NdisAllocateGenericObject(0, 0x6E535049u, 0);
    v13[12] = GenericObject;
    if ( !GenericObject )
    {
      v14 = -1073741670;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v21 = L"IPS client ndis pool (IPNG)";
LABEL_28:
        McTemplateK0z_EtwWriteTransfer(&MICROSOFT_TCPIP_PROVIDER_Context, TCPIP_MEMORY_FAILURES, v20, v21);
        goto LABEL_29;
      }
      goto LABEL_29;
    }
    Parameters.Header = (NDIS_OBJECT_HEADER)1311104;
    Parameters.fAllocateNetBuffer = 1;
    Parameters.ContextSize = *(_WORD *)(v7 + 36);
    Parameters.PoolTag = 1850953801;
    Parameters.ProtocolId = 2;
    v22 = NdisAllocateNetBufferListPool((NDIS_HANDLE)v13[12], &Parameters);
    v13[13] = v22;
    if ( !v22 )
    {
      v14 = -1073741670;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v21 = L"IPS client NBL pool (IPNG)";
        goto LABEL_28;
      }
LABEL_29:
      v25 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)v13[9];
      if ( v25 )
        ExFreeCacheAwareRundownProtection(v25);
      v26 = (struct _IO_WORKITEM *)v13[15];
      if ( v26 )
        IoFreeWorkItem(v26);
      v27 = (void *)v13[13];
      if ( v27 )
        NdisFreeNetBufferListPool(v27);
      v28 = (struct _NDIS_GENERIC_OBJECT *)v13[12];
      if ( v28 )
        NdisFreeGenericObject(v28);
      ExFreePoolWithTag(v13, 0);
      return v14;
    }
    WorkItem = IoAllocateWorkItem(IppDeviceObject);
    v13[15] = WorkItem;
    if ( !WorkItem )
    {
      v14 = -1073741670;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v21 = L"IPS client workitem (IPNG)";
        goto LABEL_28;
      }
      goto LABEL_29;
    }
    CacheAwareRundownProtection = ExAllocateCacheAwareRundownProtection((POOL_TYPE)512, 0x63535049u);
    v13[9] = CacheAwareRundownProtection;
    if ( !CacheAwareRundownProtection )
    {
      v14 = -1073741670;
      if ( SBYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v21 = L"IPS client rundown object (IPNG)";
        goto LABEL_28;
      }
      goto LABEL_29;
    }
    *a6 = v13;
    *a7 = *(_QWORD *)(a2 + 80);
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(a2 + 88, 0);
    v29 = (_QWORD *)(a2 + 96);
    v30 = *(_QWORD *)(a2 + 96);
    if ( *(_QWORD *)(v30 + 8) != a2 + 96 )
      __fastfail(3u);
    *v13 = v30;
    v13[1] = v29;
    *(_QWORD *)(v30 + 8) = v13;
    *v29 = v13;
    ++*(_DWORD *)(a2 + 112);
    if ( *((_BYTE *)v13 + 64) )
      goto LABEL_51;
    ++*(_DWORD *)(a2 + 120);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
    {
      WPP_SF_Sd(WPP_GLOBAL_Control->AttachedDevice, 12, *(_DWORD *)(a2 + 120), (_DWORD)v13 + 28, *(_DWORD *)(a2 + 120));
    }
    if ( *(_DWORD *)(a2 + 120) != 1 )
      goto LABEL_51;
    IppIpsNotifyNlClientsOnAllInterfaces(v13);
    if ( v15 == (__int64 *)&Ipv4Global )
    {
      v31 = 4;
    }
    else
    {
      if ( v15 != &Ipv6Global )
      {
LABEL_51:
        if ( !*((_BYTE *)v13 + 63) )
        {
          ++*(_DWORD *)(a2 + 116);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
            && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
          {
            WPP_SF_Sd(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              *(_DWORD *)(a2 + 116),
              (_DWORD)v13 + 28,
              *(_DWORD *)(a2 + 116));
          }
          if ( *(_DWORD *)(a2 + 116) == 1 )
          {
            IppIpsNotifyNlClientsOnAllInterfaces(v13);
            if ( v15 == (__int64 *)&Ipv4Global )
            {
              _interlockedbittestandset(&TcpipGlobalRscDisabledMask, 4u);
            }
            else if ( v15 == &Ipv6Global )
            {
              _interlockedbittestandset(&TcpipGlobalRscDisabledMask, 5u);
            }
          }
        }
        LOBYTE(v30) = 1;
        IppUpdateIpsServiceChainsForClient(v13, v30);
        ExReleasePushLockExclusiveEx(a2 + 88, 0);
        KeLeaveCriticalRegion();
        v14 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u
          && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
        {
          WPP_SF_S(
            WPP_GLOBAL_Control->AttachedDevice,
            14,
            WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids,
            (char *)v13 + 28);
        }
        return v14;
      }
      v31 = 5;
    }
    LOBYTE(v30) = 1;
    TcpipUpdateUroDisabledMask(v31, v30);
    goto LABEL_51;
  }
  v14 = -1073741811;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0x17u) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids, 3221225485LL);
  }
  return v14;
}

```

## disassembly

```asm
0x14018dd10  mov     [rsp+arg_0], rbx
0x14018dd15  push    rbp
0x14018dd16  push    rsi
0x14018dd17  push    rdi
0x14018dd18  push    r12
0x14018dd1a  push    r13
0x14018dd1c  push    r14
0x14018dd1e  push    r15
0x14018dd20  sub     rsp, 60h
0x14018dd24  mov     rax, cs:__security_cookie
0x14018dd2b  xor     rax, rsp
0x14018dd2e  mov     [rsp+98h+var_48], rax
0x14018dd33  mov     rax, [rsp+98h+arg_30]
0x14018dd3b  xorps   xmm0, xmm0
0x14018dd3e  mov     rsi, [r8+20h]
0x14018dd42  mov     rbp, r9
0x14018dd45  mov     r13, [rsp+98h+arg_28]
0x14018dd4d  mov     rbx, rdx
0x14018dd50  mov     [rsp+98h+var_68], rax
0x14018dd55  mov     r14, rcx
0x14018dd58  xor     eax, eax
0x14018dd5a  mov     [rsp+98h+var_50], eax
0x14018dd5e  movups  xmmword ptr [rsp+98h+Parameters.Header.Type], xmm0
0x14018dd63  test    rsi, rsi
0x14018dd66  jz      loc_14018E1A1
0x14018dd6c  cmp     word ptr [rsi], 2
0x14018dd70  jb      loc_14018E1A1
0x14018dd76  mov     r12d, 63535049h
0x14018dd7c  lea     ecx, [rax+40h]
0x14018dd7f  mov     r8d, r12d
0x14018dd82  mov     edx, 88h
0x14018dd87  call    cs:__imp_ExAllocatePool2
0x14018dd8e  nop     dword ptr [rax+rax+00h]
0x14018dd93  mov     rdi, rax
0x14018dd96  test    rax, rax
0x14018dd99  jnz     short loc_14018DDCB
0x14018dd9b  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14018dda1  mov     ebx, 0C000009Ah
0x14018dda6  jge     loc_14018E1DE
0x14018ddac  lea     r9, aIpsClientIpng; "IPS client (IPNG)"
0x14018ddb3  lea     rdx, TCPIP_MEMORY_FAILURES
0x14018ddba  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018ddc1  call    McTemplateK0z_EtwWriteTransfer
0x14018ddc6  jmp     loc_14018E1DE
0x14018ddcb  mov     [rax+8], rdi
0x14018ddcf  lea     r15, [rbx-4C58h]
0x14018ddd6  mov     [rax], rdi
0x14018ddd9  mov     [rax+18h], r12d
0x14018dddd  lea     r12, [rdi+1Ch]
0x14018dde1  mov     [rax+10h], r15
0x14018dde5  mov     rax, [rsp+98h+arg_20]
0x14018dded  mov     [rdi+50h], rax
0x14018ddf1  mov     [rdi+58h], rbp
0x14018ddf5  mov     [rdi+70h], r14
0x14018ddf9  movzx   eax, word ptr [rsi]
0x14018ddfc  mov     [rdi+3Ch], ax
0x14018de00  movups  xmm0, xmmword ptr [rsi+4]
0x14018de04  movups  xmmword ptr [r12], xmm0
0x14018de09  movups  xmm1, xmmword ptr [rsi+14h]
0x14018de0d  movups  xmmword ptr [r12+10h], xmm1
0x14018de13  mov     rcx, cs:WPP_GLOBAL_Control
0x14018de1a  lea     r14, WPP_GLOBAL_Control
0x14018de21  mov     edx, 4
0x14018de26  cmp     rcx, r14
0x14018de29  jz      short loc_14018DE54
0x14018de2b  cmp     [rcx+29h], dl
0x14018de2e  jb      short loc_14018DE54
0x14018de30  bt      dword ptr [rcx+2Ch], 17h
0x14018de35  jnb     short loc_14018DE54
0x14018de37  mov     rcx, [rcx+18h]
0x14018de3b  lea     r8, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids
0x14018de42  mov     edx, 0Bh
0x14018de47  mov     r9, r12
0x14018de4a  call    WPP_SF_S
0x14018de4f  mov     edx, 4
0x14018de54  mov     al, [rsi+26h]
0x14018de57  movzx   ecx, word ptr [rdi+3Ch]
0x14018de5b  mov     [rdi+3Eh], al
0x14018de5e  mov     eax, 3
0x14018de63  cmp     cx, ax
0x14018de66  jb      short loc_14018DE6D
0x14018de68  mov     al, [rsi+27h]
0x14018de6b  jmp     short loc_14018DE6F
0x14018de6d  xor     al, al
0x14018de6f  mov     [rdi+3Fh], al
0x14018de72  cmp     cx, dx
0x14018de75  jb      short loc_14018DE7C
0x14018de77  mov     al, [rsi+30h]
0x14018de7a  jmp     short loc_14018DE7E
0x14018de7c  xor     al, al
0x14018de7e  mov     [rdi+40h], al
0x14018de81  xor     r8d, r8d; Size
0x14018de84  mov     al, [rsi+31h]
0x14018de87  mov     edx, 6E535049h; Tag
0x14018de8c  mov     [rdi+41h], al
0x14018de8f  xor     ecx, ecx; DriverObject
0x14018de91  mov     rax, [rsi+28h]
0x14018de95  mov     [rdi+80h], rax
0x14018de9c  call    cs:__imp_NdisAllocateGenericObject
0x14018dea3  nop     dword ptr [rax+rax+00h]
0x14018dea8  mov     [rdi+60h], rax
0x14018deac  test    rax, rax
0x14018deaf  jnz     short loc_14018DECE
0x14018deb1  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14018deb7  mov     ebx, 0C000009Ah
0x14018debc  jge     loc_14018DFA5
0x14018dec2  lea     r9, aIpsClientNdisP; "IPS client ndis pool (IPNG)"
0x14018dec9  jmp     loc_14018DF92
0x14018dece  mov     dword ptr [rsp+98h+Parameters.Header.Type], 140180h
0x14018ded6  lea     rdx, [rsp+98h+Parameters]; Parameters
0x14018dedb  mov     [rsp+98h+Parameters.fAllocateNetBuffer], 1
0x14018dee0  movzx   eax, word ptr [rsi+24h]
0x14018dee4  mov     [rsp+98h+Parameters.ContextSize], ax
0x14018dee9  mov     [rsp+98h+Parameters.PoolTag], 6E535049h
0x14018def1  mov     [rsp+98h+Parameters.ProtocolId], 2
0x14018def6  mov     rcx, [rdi+60h]; NdisHandle
0x14018defa  call    cs:__imp_NdisAllocateNetBufferListPool
0x14018df01  nop     dword ptr [rax+rax+00h]
0x14018df06  mov     [rdi+68h], rax
0x14018df0a  test    rax, rax
0x14018df0d  jnz     short loc_14018DF29
0x14018df0f  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14018df15  mov     ebx, 0C000009Ah
0x14018df1a  jge     loc_14018DFA5
0x14018df20  lea     r9, aIpsClientNblPo; "IPS client NBL pool (IPNG)"
0x14018df27  jmp     short loc_14018DF92
0x14018df29  mov     rcx, cs:IppDeviceObject; DeviceObject
0x14018df30  call    cs:__imp_IoAllocateWorkItem
0x14018df37  nop     dword ptr [rax+rax+00h]
0x14018df3c  mov     [rdi+78h], rax
0x14018df40  test    rax, rax
0x14018df43  jnz     short loc_14018DF5B
0x14018df45  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14018df4b  mov     ebx, 0C000009Ah
0x14018df50  jge     short loc_14018DFA5
0x14018df52  lea     r9, aIpsClientWorki; "IPS client workitem (IPNG)"
0x14018df59  jmp     short loc_14018DF92
0x14018df5b  mov     edx, 63535049h; PoolTag
0x14018df60  mov     ecx, 200h; PoolType
0x14018df65  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14018df6c  nop     dword ptr [rax+rax+00h]
0x14018df71  mov     [rdi+48h], rax
0x14018df75  test    rax, rax
0x14018df78  jnz     loc_14018E00F
0x14018df7e  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, al
0x14018df84  mov     ebx, 0C000009Ah
0x14018df89  jge     short loc_14018DFA5
0x14018df8b  lea     r9, aIpsClientRundo; "IPS client rundown object (IPNG)"
0x14018df92  lea     rdx, TCPIP_MEMORY_FAILURES
0x14018df99  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018dfa0  call    McTemplateK0z_EtwWriteTransfer
0x14018dfa5  mov     rcx, [rdi+48h]; RunRefCacheAware
0x14018dfa9  test    rcx, rcx
0x14018dfac  jz      short loc_14018DFBA
0x14018dfae  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14018dfb5  nop     dword ptr [rax+rax+00h]
0x14018dfba  mov     rcx, [rdi+78h]; IoWorkItem
0x14018dfbe  test    rcx, rcx
0x14018dfc1  jz      short loc_14018DFCF
0x14018dfc3  call    cs:__imp_IoFreeWorkItem
0x14018dfca  nop     dword ptr [rax+rax+00h]
0x14018dfcf  mov     rcx, [rdi+68h]; PoolHandle
0x14018dfd3  test    rcx, rcx
0x14018dfd6  jz      short loc_14018DFE4
0x14018dfd8  call    cs:__imp_NdisFreeNetBufferListPool
0x14018dfdf  nop     dword ptr [rax+rax+00h]
0x14018dfe4  mov     rcx, [rdi+60h]; NdisObject
0x14018dfe8  test    rcx, rcx
0x14018dfeb  jz      short loc_14018DFF9
0x14018dfed  call    cs:__imp_NdisFreeGenericObject
0x14018dff4  nop     dword ptr [rax+rax+00h]
0x14018dff9  xor     edx, edx; Tag
0x14018dffb  mov     rcx, rdi; P
0x14018dffe  call    cs:__imp_ExFreePoolWithTag
0x14018e005  nop     dword ptr [rax+rax+00h]
0x14018e00a  jmp     loc_14018E1DE
0x14018e00f  mov     rdx, [rsp+98h+var_68]
0x14018e014  mov     [r13+0], rdi
0x14018e018  mov     rax, [rbx+50h]
0x14018e01c  mov     [rdx], rax
0x14018e01f  call    cs:__imp_KeEnterCriticalRegion
0x14018e026  nop     dword ptr [rax+rax+00h]
0x14018e02b  xor     edx, edx
0x14018e02d  lea     rcx, [rbx+58h]
0x14018e031  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14018e038  nop     dword ptr [rax+rax+00h]
0x14018e03d  lea     rax, [rbx+60h]
0x14018e041  mov     rdx, [rax]
0x14018e044  cmp     [rdx+8], rax
0x14018e048  jz      short loc_14018E051
0x14018e04a  mov     ecx, 3
0x14018e04f  int     29h; Win8: RtlFailFast(ecx)
0x14018e051  mov     [rdi], rdx
0x14018e054  lea     r13, Ipv6Global
0x14018e05b  mov     [rdi+8], rax
0x14018e05f  mov     [rdx+8], rdi
0x14018e063  mov     [rax], rdi
0x14018e066  inc     dword ptr [rbx+70h]
0x14018e069  cmp     byte ptr [rdi+40h], 0
0x14018e06d  jnz     short loc_14018E0D7
0x14018e06f  inc     dword ptr [rbx+78h]
0x14018e072  mov     r8d, [rbx+78h]
0x14018e076  mov     rcx, cs:WPP_GLOBAL_Control
0x14018e07d  cmp     rcx, r14
0x14018e080  jz      short loc_14018E0A5
0x14018e082  cmp     byte ptr [rcx+29h], 4
0x14018e086  jb      short loc_14018E0A5
0x14018e088  bt      dword ptr [rcx+2Ch], 17h
0x14018e08d  jnb     short loc_14018E0A5
0x14018e08f  mov     rcx, [rcx+18h]
0x14018e093  mov     edx, 0Ch
0x14018e098  mov     r9, r12
0x14018e09b  mov     [rsp+98h+var_78], r8d
0x14018e0a0  call    WPP_SF_Sd
0x14018e0a5  cmp     dword ptr [rbx+78h], 1
0x14018e0a9  jnz     short loc_14018E0D7
0x14018e0ab  mov     rcx, rdi
0x14018e0ae  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018e0b3  lea     rax, Ipv4Global
0x14018e0ba  cmp     r15, rax
0x14018e0bd  jnz     short loc_14018E0C6
0x14018e0bf  mov     ecx, 4
0x14018e0c4  jmp     short loc_14018E0D0
0x14018e0c6  cmp     r15, r13
0x14018e0c9  jnz     short loc_14018E0D7
0x14018e0cb  mov     ecx, 5
0x14018e0d0  mov     dl, 1
0x14018e0d2  call    TcpipUpdateUroDisabledMask
0x14018e0d7  cmp     byte ptr [rdi+3Fh], 0
0x14018e0db  jnz     short loc_14018E146
0x14018e0dd  inc     dword ptr [rbx+74h]
0x14018e0e0  mov     r8d, [rbx+74h]
0x14018e0e4  mov     rcx, cs:WPP_GLOBAL_Control
0x14018e0eb  cmp     rcx, r14
0x14018e0ee  jz      short loc_14018E113
0x14018e0f0  cmp     byte ptr [rcx+29h], 4
0x14018e0f4  jb      short loc_14018E113
0x14018e0f6  bt      dword ptr [rcx+2Ch], 17h
0x14018e0fb  jnb     short loc_14018E113
0x14018e0fd  mov     rcx, [rcx+18h]
0x14018e101  mov     edx, 0Dh
0x14018e106  mov     r9, r12
0x14018e109  mov     [rsp+98h+var_78], r8d
0x14018e10e  call    WPP_SF_Sd
0x14018e113  cmp     dword ptr [rbx+74h], 1
0x14018e117  jnz     short loc_14018E146
0x14018e119  mov     rcx, rdi
0x14018e11c  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018e121  lea     rax, Ipv4Global
0x14018e128  cmp     r15, rax
0x14018e12b  jnz     short loc_14018E138
0x14018e12d  lock bts cs:TcpipGlobalRscDisabledMask, 4
0x14018e136  jmp     short loc_14018E146
0x14018e138  cmp     r15, r13
0x14018e13b  jnz     short loc_14018E146
0x14018e13d  lock bts cs:TcpipGlobalRscDisabledMask, 5
0x14018e146  mov     dl, 1
0x14018e148  mov     rcx, rdi
0x14018e14b  call    IppUpdateIpsServiceChainsForClient
0x14018e150  xor     edx, edx
0x14018e152  lea     rcx, [rbx+58h]
0x14018e156  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14018e15d  nop     dword ptr [rax+rax+00h]
0x14018e162  call    cs:__imp_KeLeaveCriticalRegion
0x14018e169  nop     dword ptr [rax+rax+00h]
0x14018e16e  xor     ebx, ebx
0x14018e170  mov     rcx, cs:WPP_GLOBAL_Control
0x14018e177  cmp     rcx, r14
0x14018e17a  jz      short loc_14018E1DE
0x14018e17c  cmp     byte ptr [rcx+29h], 4
0x14018e180  jb      short loc_14018E1DE
0x14018e182  bt      dword ptr [rcx+2Ch], 17h
0x14018e187  jnb     short loc_14018E1DE
0x14018e189  mov     rcx, [rcx+18h]
0x14018e18d  lea     edx, [rbx+0Eh]
0x14018e190  mov     r9, r12
0x14018e193  lea     r8, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids
0x14018e19a  call    WPP_SF_S
0x14018e19f  jmp     short loc_14018E1DE
0x14018e1a1  mov     ebx, 0C000000Dh
0x14018e1a6  mov     rcx, cs:WPP_GLOBAL_Control
0x14018e1ad  lea     r14, WPP_GLOBAL_Control
0x14018e1b4  cmp     rcx, r14
0x14018e1b7  jz      short loc_14018E1DE
0x14018e1b9  cmp     byte ptr [rcx+29h], 2
0x14018e1bd  jb      short loc_14018E1DE
0x14018e1bf  bt      dword ptr [rcx+2Ch], 17h
0x14018e1c4  jnb     short loc_14018E1DE
0x14018e1c6  mov     rcx, [rcx+18h]
0x14018e1ca  lea     r8, WPP_5233970d56413ab48eace6095c9c2fb5_Traceguids
0x14018e1d1  mov     edx, 0Ah
0x14018e1d6  mov     r9d, ebx
0x14018e1d9  call    WPP_SF_d
0x14018e1de  mov     eax, ebx
0x14018e1e0  mov     rcx, [rsp+98h+var_48]
0x14018e1e5  xor     rcx, rsp; StackCookie
0x14018e1e8  call    __security_check_cookie
0x14018e1ed  mov     rbx, [rsp+98h+arg_0]
0x14018e1f5  add     rsp, 60h
0x14018e1f9  pop     r15
  ... truncated ...
```
