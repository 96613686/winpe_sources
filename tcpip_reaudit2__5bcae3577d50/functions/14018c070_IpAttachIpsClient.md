# IpAttachIpsClient

- ea: `0x14018c070`
- end: `0x14018c566`
- name: `IpAttachIpsClient`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14003fcc4`
- `0x140054138`
- `0x14011c704`
- `0x140123598`
- `0x140152960`
- `0x14018c070`
- `0x14018d978`
- `0x14018e08c`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018c30e`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018c30e`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14018c2c5`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14018c2c5`
- `ntoskrnl!IoAllocateWorkItem` at `0x14018c290`
- `ntoskrnl!IoAllocateWorkItem` at `0x14018c290`
- `ntoskrnl!IoFreeWorkItem` at `0x14018c323`
- `ntoskrnl!IoFreeWorkItem` at `0x14018c323`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018c4c2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018c4c2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018c37f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018c37f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018c4b6`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018c4b6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018c391`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018c391`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018c35e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018c35e`
- `ntoskrnl!ExAllocatePool2` at `0x14018c0e7`
- `ntoskrnl!ExAllocatePool2` at `0x14018c0e7`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018c338`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018c338`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14018c25a`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14018c25a`
- `NDIS!NdisFreeGenericObject` at `0x14018c34d`
- `NDIS!NdisFreeGenericObject` at `0x14018c34d`
- `NDIS!NdisAllocateGenericObject` at `0x14018c1fc`
- `NDIS!NdisAllocateGenericObject` at `0x14018c1fc`

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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
      WPP_SF_S(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids, Pool2 + 28);
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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
      if ( SBYTE3(WPP_MAIN_CB.Reserved) < 0 )
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
            WPP_ac85ee5d021131934f4c5188022bc398_Traceguids,
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids, 3221225485LL);
  }
  return v14;
}

```

## disassembly

```asm
0x14018c070  mov     [rsp+arg_0], rbx
0x14018c075  push    rbp
0x14018c076  push    rsi
0x14018c077  push    rdi
0x14018c078  push    r12
0x14018c07a  push    r13
0x14018c07c  push    r14
0x14018c07e  push    r15
0x14018c080  sub     rsp, 60h
0x14018c084  mov     rax, cs:__security_cookie
0x14018c08b  xor     rax, rsp
0x14018c08e  mov     [rsp+98h+var_48], rax
0x14018c093  mov     rax, [rsp+98h+arg_30]
0x14018c09b  xorps   xmm0, xmm0
0x14018c09e  mov     rsi, [r8+20h]
0x14018c0a2  mov     rbp, r9
0x14018c0a5  mov     r13, [rsp+98h+arg_28]
0x14018c0ad  mov     rbx, rdx
0x14018c0b0  mov     [rsp+98h+var_68], rax
0x14018c0b5  mov     r14, rcx
0x14018c0b8  xor     eax, eax
0x14018c0ba  mov     [rsp+98h+var_50], eax
0x14018c0be  movups  xmmword ptr [rsp+98h+Parameters.Header.Type], xmm0
0x14018c0c3  test    rsi, rsi
0x14018c0c6  jz      loc_14018C501
0x14018c0cc  cmp     word ptr [rsi], 2
0x14018c0d0  jb      loc_14018C501
0x14018c0d6  mov     r12d, 63535049h
0x14018c0dc  lea     ecx, [rax+40h]
0x14018c0df  mov     r8d, r12d
0x14018c0e2  mov     edx, 88h
0x14018c0e7  call    cs:__imp_ExAllocatePool2
0x14018c0ee  nop     dword ptr [rax+rax+00h]
0x14018c0f3  mov     rdi, rax
0x14018c0f6  test    rax, rax
0x14018c0f9  jnz     short loc_14018C12B
0x14018c0fb  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c101  mov     ebx, 0C000009Ah
0x14018c106  jge     loc_14018C53E
0x14018c10c  lea     r9, aIpsClientIpng; "IPS client (IPNG)"
0x14018c113  lea     rdx, TCPIP_MEMORY_FAILURES
0x14018c11a  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018c121  call    McTemplateK0z_EtwWriteTransfer
0x14018c126  jmp     loc_14018C53E
0x14018c12b  mov     [rax+8], rdi
0x14018c12f  lea     r15, [rbx-4C58h]
0x14018c136  mov     [rax], rdi
0x14018c139  mov     [rax+18h], r12d
0x14018c13d  lea     r12, [rdi+1Ch]
0x14018c141  mov     [rax+10h], r15
0x14018c145  mov     rax, [rsp+98h+arg_20]
0x14018c14d  mov     [rdi+50h], rax
0x14018c151  mov     [rdi+58h], rbp
0x14018c155  mov     [rdi+70h], r14
0x14018c159  movzx   eax, word ptr [rsi]
0x14018c15c  mov     [rdi+3Ch], ax
0x14018c160  movups  xmm0, xmmword ptr [rsi+4]
0x14018c164  movups  xmmword ptr [r12], xmm0
0x14018c169  movups  xmm1, xmmword ptr [rsi+14h]
0x14018c16d  movups  xmmword ptr [r12+10h], xmm1
0x14018c173  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c17a  lea     r14, WPP_GLOBAL_Control
0x14018c181  mov     edx, 4
0x14018c186  cmp     rcx, r14
0x14018c189  jz      short loc_14018C1B4
0x14018c18b  cmp     [rcx+29h], dl
0x14018c18e  jb      short loc_14018C1B4
0x14018c190  bt      dword ptr [rcx+2Ch], 17h
0x14018c195  jnb     short loc_14018C1B4
0x14018c197  mov     rcx, [rcx+18h]
0x14018c19b  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018c1a2  mov     edx, 0Bh
0x14018c1a7  mov     r9, r12
0x14018c1aa  call    WPP_SF_S
0x14018c1af  mov     edx, 4
0x14018c1b4  mov     al, [rsi+26h]
0x14018c1b7  movzx   ecx, word ptr [rdi+3Ch]
0x14018c1bb  mov     [rdi+3Eh], al
0x14018c1be  mov     eax, 3
0x14018c1c3  cmp     cx, ax
0x14018c1c6  jb      short loc_14018C1CD
0x14018c1c8  mov     al, [rsi+27h]
0x14018c1cb  jmp     short loc_14018C1CF
0x14018c1cd  xor     al, al
0x14018c1cf  mov     [rdi+3Fh], al
0x14018c1d2  cmp     cx, dx
0x14018c1d5  jb      short loc_14018C1DC
0x14018c1d7  mov     al, [rsi+30h]
0x14018c1da  jmp     short loc_14018C1DE
0x14018c1dc  xor     al, al
0x14018c1de  mov     [rdi+40h], al
0x14018c1e1  xor     r8d, r8d; Size
0x14018c1e4  mov     al, [rsi+31h]
0x14018c1e7  mov     edx, 6E535049h; Tag
0x14018c1ec  mov     [rdi+41h], al
0x14018c1ef  xor     ecx, ecx; DriverObject
0x14018c1f1  mov     rax, [rsi+28h]
0x14018c1f5  mov     [rdi+80h], rax
0x14018c1fc  call    cs:__imp_NdisAllocateGenericObject
0x14018c203  nop     dword ptr [rax+rax+00h]
0x14018c208  mov     [rdi+60h], rax
0x14018c20c  test    rax, rax
0x14018c20f  jnz     short loc_14018C22E
0x14018c211  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c217  mov     ebx, 0C000009Ah
0x14018c21c  jge     loc_14018C305
0x14018c222  lea     r9, aIpsClientNdisP; "IPS client ndis pool (IPNG)"
0x14018c229  jmp     loc_14018C2F2
0x14018c22e  mov     dword ptr [rsp+98h+Parameters.Header.Type], 140180h
0x14018c236  lea     rdx, [rsp+98h+Parameters]; Parameters
0x14018c23b  mov     [rsp+98h+Parameters.fAllocateNetBuffer], 1
0x14018c240  movzx   eax, word ptr [rsi+24h]
0x14018c244  mov     [rsp+98h+Parameters.ContextSize], ax
0x14018c249  mov     [rsp+98h+Parameters.PoolTag], 6E535049h
0x14018c251  mov     [rsp+98h+Parameters.ProtocolId], 2
0x14018c256  mov     rcx, [rdi+60h]; NdisHandle
0x14018c25a  call    cs:__imp_NdisAllocateNetBufferListPool
0x14018c261  nop     dword ptr [rax+rax+00h]
0x14018c266  mov     [rdi+68h], rax
0x14018c26a  test    rax, rax
0x14018c26d  jnz     short loc_14018C289
0x14018c26f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c275  mov     ebx, 0C000009Ah
0x14018c27a  jge     loc_14018C305
0x14018c280  lea     r9, aIpsClientNblPo; "IPS client NBL pool (IPNG)"
0x14018c287  jmp     short loc_14018C2F2
0x14018c289  mov     rcx, cs:IppDeviceObject; DeviceObject
0x14018c290  call    cs:__imp_IoAllocateWorkItem
0x14018c297  nop     dword ptr [rax+rax+00h]
0x14018c29c  mov     [rdi+78h], rax
0x14018c2a0  test    rax, rax
0x14018c2a3  jnz     short loc_14018C2BB
0x14018c2a5  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c2ab  mov     ebx, 0C000009Ah
0x14018c2b0  jge     short loc_14018C305
0x14018c2b2  lea     r9, aIpsClientWorki; "IPS client workitem (IPNG)"
0x14018c2b9  jmp     short loc_14018C2F2
0x14018c2bb  mov     edx, 63535049h; PoolTag
0x14018c2c0  mov     ecx, 200h; PoolType
0x14018c2c5  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14018c2cc  nop     dword ptr [rax+rax+00h]
0x14018c2d1  mov     [rdi+48h], rax
0x14018c2d5  test    rax, rax
0x14018c2d8  jnz     loc_14018C36F
0x14018c2de  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c2e4  mov     ebx, 0C000009Ah
0x14018c2e9  jge     short loc_14018C305
0x14018c2eb  lea     r9, aIpsClientRundo; "IPS client rundown object (IPNG)"
0x14018c2f2  lea     rdx, TCPIP_MEMORY_FAILURES
0x14018c2f9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018c300  call    McTemplateK0z_EtwWriteTransfer
0x14018c305  mov     rcx, [rdi+48h]; RunRefCacheAware
0x14018c309  test    rcx, rcx
0x14018c30c  jz      short loc_14018C31A
0x14018c30e  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14018c315  nop     dword ptr [rax+rax+00h]
0x14018c31a  mov     rcx, [rdi+78h]; IoWorkItem
0x14018c31e  test    rcx, rcx
0x14018c321  jz      short loc_14018C32F
0x14018c323  call    cs:__imp_IoFreeWorkItem
0x14018c32a  nop     dword ptr [rax+rax+00h]
0x14018c32f  mov     rcx, [rdi+68h]; PoolHandle
0x14018c333  test    rcx, rcx
0x14018c336  jz      short loc_14018C344
0x14018c338  call    cs:__imp_NdisFreeNetBufferListPool
0x14018c33f  nop     dword ptr [rax+rax+00h]
0x14018c344  mov     rcx, [rdi+60h]; NdisObject
0x14018c348  test    rcx, rcx
0x14018c34b  jz      short loc_14018C359
0x14018c34d  call    cs:__imp_NdisFreeGenericObject
0x14018c354  nop     dword ptr [rax+rax+00h]
0x14018c359  xor     edx, edx; Tag
0x14018c35b  mov     rcx, rdi; P
0x14018c35e  call    cs:__imp_ExFreePoolWithTag
0x14018c365  nop     dword ptr [rax+rax+00h]
0x14018c36a  jmp     loc_14018C53E
0x14018c36f  mov     rdx, [rsp+98h+var_68]
0x14018c374  mov     [r13+0], rdi
0x14018c378  mov     rax, [rbx+50h]
0x14018c37c  mov     [rdx], rax
0x14018c37f  call    cs:__imp_KeEnterCriticalRegion
0x14018c386  nop     dword ptr [rax+rax+00h]
0x14018c38b  xor     edx, edx
0x14018c38d  lea     rcx, [rbx+58h]
0x14018c391  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14018c398  nop     dword ptr [rax+rax+00h]
0x14018c39d  lea     rax, [rbx+60h]
0x14018c3a1  mov     rdx, [rax]
0x14018c3a4  cmp     [rdx+8], rax
0x14018c3a8  jz      short loc_14018C3B1
0x14018c3aa  mov     ecx, 3
0x14018c3af  int     29h; Win8: RtlFailFast(ecx)
0x14018c3b1  mov     [rdi], rdx
0x14018c3b4  lea     r13, Ipv6Global
0x14018c3bb  mov     [rdi+8], rax
0x14018c3bf  mov     [rdx+8], rdi
0x14018c3c3  mov     [rax], rdi
0x14018c3c6  inc     dword ptr [rbx+70h]
0x14018c3c9  cmp     byte ptr [rdi+40h], 0
0x14018c3cd  jnz     short loc_14018C437
0x14018c3cf  inc     dword ptr [rbx+78h]
0x14018c3d2  mov     r8d, [rbx+78h]
0x14018c3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c3dd  cmp     rcx, r14
0x14018c3e0  jz      short loc_14018C405
0x14018c3e2  cmp     byte ptr [rcx+29h], 4
0x14018c3e6  jb      short loc_14018C405
0x14018c3e8  bt      dword ptr [rcx+2Ch], 17h
0x14018c3ed  jnb     short loc_14018C405
0x14018c3ef  mov     rcx, [rcx+18h]
0x14018c3f3  mov     edx, 0Ch
0x14018c3f8  mov     r9, r12
0x14018c3fb  mov     [rsp+98h+var_78], r8d
0x14018c400  call    WPP_SF_Sd
0x14018c405  cmp     dword ptr [rbx+78h], 1
0x14018c409  jnz     short loc_14018C437
0x14018c40b  mov     rcx, rdi
0x14018c40e  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018c413  lea     rax, Ipv4Global
0x14018c41a  cmp     r15, rax
0x14018c41d  jnz     short loc_14018C426
0x14018c41f  mov     ecx, 4
0x14018c424  jmp     short loc_14018C430
0x14018c426  cmp     r15, r13
0x14018c429  jnz     short loc_14018C437
0x14018c42b  mov     ecx, 5
0x14018c430  mov     dl, 1
0x14018c432  call    TcpipUpdateUroDisabledMask
0x14018c437  cmp     byte ptr [rdi+3Fh], 0
0x14018c43b  jnz     short loc_14018C4A6
0x14018c43d  inc     dword ptr [rbx+74h]
0x14018c440  mov     r8d, [rbx+74h]
0x14018c444  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c44b  cmp     rcx, r14
0x14018c44e  jz      short loc_14018C473
0x14018c450  cmp     byte ptr [rcx+29h], 4
0x14018c454  jb      short loc_14018C473
0x14018c456  bt      dword ptr [rcx+2Ch], 17h
0x14018c45b  jnb     short loc_14018C473
0x14018c45d  mov     rcx, [rcx+18h]
0x14018c461  mov     edx, 0Dh
0x14018c466  mov     r9, r12
0x14018c469  mov     [rsp+98h+var_78], r8d
0x14018c46e  call    WPP_SF_Sd
0x14018c473  cmp     dword ptr [rbx+74h], 1
0x14018c477  jnz     short loc_14018C4A6
0x14018c479  mov     rcx, rdi
0x14018c47c  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018c481  lea     rax, Ipv4Global
0x14018c488  cmp     r15, rax
0x14018c48b  jnz     short loc_14018C498
0x14018c48d  lock bts cs:TcpipGlobalRscDisabledMask, 4
0x14018c496  jmp     short loc_14018C4A6
0x14018c498  cmp     r15, r13
0x14018c49b  jnz     short loc_14018C4A6
0x14018c49d  lock bts cs:TcpipGlobalRscDisabledMask, 5
0x14018c4a6  mov     dl, 1
0x14018c4a8  mov     rcx, rdi
0x14018c4ab  call    IppUpdateIpsServiceChainsForClient
0x14018c4b0  xor     edx, edx
0x14018c4b2  lea     rcx, [rbx+58h]
0x14018c4b6  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14018c4bd  nop     dword ptr [rax+rax+00h]
0x14018c4c2  call    cs:__imp_KeLeaveCriticalRegion
0x14018c4c9  nop     dword ptr [rax+rax+00h]
0x14018c4ce  xor     ebx, ebx
0x14018c4d0  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c4d7  cmp     rcx, r14
0x14018c4da  jz      short loc_14018C53E
0x14018c4dc  cmp     byte ptr [rcx+29h], 4
0x14018c4e0  jb      short loc_14018C53E
0x14018c4e2  bt      dword ptr [rcx+2Ch], 17h
0x14018c4e7  jnb     short loc_14018C53E
0x14018c4e9  mov     rcx, [rcx+18h]
0x14018c4ed  lea     edx, [rbx+0Eh]
0x14018c4f0  mov     r9, r12
0x14018c4f3  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018c4fa  call    WPP_SF_S
0x14018c4ff  jmp     short loc_14018C53E
0x14018c501  mov     ebx, 0C000000Dh
0x14018c506  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c50d  lea     r14, WPP_GLOBAL_Control
0x14018c514  cmp     rcx, r14
0x14018c517  jz      short loc_14018C53E
0x14018c519  cmp     byte ptr [rcx+29h], 2
0x14018c51d  jb      short loc_14018C53E
0x14018c51f  bt      dword ptr [rcx+2Ch], 17h
0x14018c524  jnb     short loc_14018C53E
0x14018c526  mov     rcx, [rcx+18h]
0x14018c52a  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018c531  mov     edx, 0Ah
0x14018c536  mov     r9d, ebx
0x14018c539  call    WPP_SF_d
0x14018c53e  mov     eax, ebx
0x14018c540  mov     rcx, [rsp+98h+var_48]
0x14018c545  xor     rcx, rsp; StackCookie
0x14018c548  call    __security_check_cookie
0x14018c54d  mov     rbx, [rsp+98h+arg_0]
0x14018c555  add     rsp, 60h
0x14018c559  pop     r15
  ... truncated ...
```
