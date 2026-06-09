# IpAttachIpsClient

- ea: `0x14018bf30`
- end: `0x14018c426`
- name: `IpAttachIpsClient`
- size: `1270`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14003fa24`
- `0x140053e98`
- `0x14011c5c4`
- `0x140123458`
- `0x140152820`
- `0x14018bf30`
- `0x14018d838`
- `0x14018df4c`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018c1ce`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14018c1ce`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14018c185`
- `ntoskrnl!ExAllocateCacheAwareRundownProtection` at `0x14018c185`
- `ntoskrnl!IoAllocateWorkItem` at `0x14018c150`
- `ntoskrnl!IoAllocateWorkItem` at `0x14018c150`
- `ntoskrnl!IoFreeWorkItem` at `0x14018c1e3`
- `ntoskrnl!IoFreeWorkItem` at `0x14018c1e3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018c382`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14018c382`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018c23f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14018c23f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018c376`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14018c376`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018c251`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14018c251`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018c21e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018c21e`
- `ntoskrnl!ExAllocatePool2` at `0x14018bfa7`
- `ntoskrnl!ExAllocatePool2` at `0x14018bfa7`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018c1f8`
- `NDIS!NdisFreeNetBufferListPool` at `0x14018c1f8`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14018c11a`
- `NDIS!NdisAllocateNetBufferListPool` at `0x14018c11a`
- `NDIS!NdisFreeGenericObject` at `0x14018c20d`
- `NDIS!NdisFreeGenericObject` at `0x14018c20d`
- `NDIS!NdisAllocateGenericObject` at `0x14018c0bc`
- `NDIS!NdisAllocateGenericObject` at `0x14018c0bc`

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
0x14018bf30  mov     [rsp+arg_0], rbx
0x14018bf35  push    rbp
0x14018bf36  push    rsi
0x14018bf37  push    rdi
0x14018bf38  push    r12
0x14018bf3a  push    r13
0x14018bf3c  push    r14
0x14018bf3e  push    r15
0x14018bf40  sub     rsp, 60h
0x14018bf44  mov     rax, cs:__security_cookie
0x14018bf4b  xor     rax, rsp
0x14018bf4e  mov     [rsp+98h+var_48], rax
0x14018bf53  mov     rax, [rsp+98h+arg_30]
0x14018bf5b  xorps   xmm0, xmm0
0x14018bf5e  mov     rsi, [r8+20h]
0x14018bf62  mov     rbp, r9
0x14018bf65  mov     r13, [rsp+98h+arg_28]
0x14018bf6d  mov     rbx, rdx
0x14018bf70  mov     [rsp+98h+var_68], rax
0x14018bf75  mov     r14, rcx
0x14018bf78  xor     eax, eax
0x14018bf7a  mov     [rsp+98h+var_50], eax
0x14018bf7e  movups  xmmword ptr [rsp+98h+Parameters.Header.Type], xmm0
0x14018bf83  test    rsi, rsi
0x14018bf86  jz      loc_14018C3C1
0x14018bf8c  cmp     word ptr [rsi], 2
0x14018bf90  jb      loc_14018C3C1
0x14018bf96  mov     r12d, 63535049h
0x14018bf9c  lea     ecx, [rax+40h]
0x14018bf9f  mov     r8d, r12d
0x14018bfa2  mov     edx, 88h
0x14018bfa7  call    cs:__imp_ExAllocatePool2
0x14018bfae  nop     dword ptr [rax+rax+00h]
0x14018bfb3  mov     rdi, rax
0x14018bfb6  test    rax, rax
0x14018bfb9  jnz     short loc_14018BFEB
0x14018bfbb  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018bfc1  mov     ebx, 0C000009Ah
0x14018bfc6  jge     loc_14018C3FE
0x14018bfcc  lea     r9, aIpsClientIpng; "IPS client (IPNG)"
0x14018bfd3  lea     rdx, TCPIP_MEMORY_FAILURES
0x14018bfda  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018bfe1  call    McTemplateK0z_EtwWriteTransfer
0x14018bfe6  jmp     loc_14018C3FE
0x14018bfeb  mov     [rax+8], rdi
0x14018bfef  lea     r15, [rbx-4C58h]
0x14018bff6  mov     [rax], rdi
0x14018bff9  mov     [rax+18h], r12d
0x14018bffd  lea     r12, [rdi+1Ch]
0x14018c001  mov     [rax+10h], r15
0x14018c005  mov     rax, [rsp+98h+arg_20]
0x14018c00d  mov     [rdi+50h], rax
0x14018c011  mov     [rdi+58h], rbp
0x14018c015  mov     [rdi+70h], r14
0x14018c019  movzx   eax, word ptr [rsi]
0x14018c01c  mov     [rdi+3Ch], ax
0x14018c020  movups  xmm0, xmmword ptr [rsi+4]
0x14018c024  movups  xmmword ptr [r12], xmm0
0x14018c029  movups  xmm1, xmmword ptr [rsi+14h]
0x14018c02d  movups  xmmword ptr [r12+10h], xmm1
0x14018c033  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c03a  lea     r14, WPP_GLOBAL_Control
0x14018c041  mov     edx, 4
0x14018c046  cmp     rcx, r14
0x14018c049  jz      short loc_14018C074
0x14018c04b  cmp     [rcx+29h], dl
0x14018c04e  jb      short loc_14018C074
0x14018c050  bt      dword ptr [rcx+2Ch], 17h
0x14018c055  jnb     short loc_14018C074
0x14018c057  mov     rcx, [rcx+18h]
0x14018c05b  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018c062  mov     edx, 0Bh
0x14018c067  mov     r9, r12
0x14018c06a  call    WPP_SF_S
0x14018c06f  mov     edx, 4
0x14018c074  mov     al, [rsi+26h]
0x14018c077  movzx   ecx, word ptr [rdi+3Ch]
0x14018c07b  mov     [rdi+3Eh], al
0x14018c07e  mov     eax, 3
0x14018c083  cmp     cx, ax
0x14018c086  jb      short loc_14018C08D
0x14018c088  mov     al, [rsi+27h]
0x14018c08b  jmp     short loc_14018C08F
0x14018c08d  xor     al, al
0x14018c08f  mov     [rdi+3Fh], al
0x14018c092  cmp     cx, dx
0x14018c095  jb      short loc_14018C09C
0x14018c097  mov     al, [rsi+30h]
0x14018c09a  jmp     short loc_14018C09E
0x14018c09c  xor     al, al
0x14018c09e  mov     [rdi+40h], al
0x14018c0a1  xor     r8d, r8d; Size
0x14018c0a4  mov     al, [rsi+31h]
0x14018c0a7  mov     edx, 6E535049h; Tag
0x14018c0ac  mov     [rdi+41h], al
0x14018c0af  xor     ecx, ecx; DriverObject
0x14018c0b1  mov     rax, [rsi+28h]
0x14018c0b5  mov     [rdi+80h], rax
0x14018c0bc  call    cs:__imp_NdisAllocateGenericObject
0x14018c0c3  nop     dword ptr [rax+rax+00h]
0x14018c0c8  mov     [rdi+60h], rax
0x14018c0cc  test    rax, rax
0x14018c0cf  jnz     short loc_14018C0EE
0x14018c0d1  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c0d7  mov     ebx, 0C000009Ah
0x14018c0dc  jge     loc_14018C1C5
0x14018c0e2  lea     r9, aIpsClientNdisP; "IPS client ndis pool (IPNG)"
0x14018c0e9  jmp     loc_14018C1B2
0x14018c0ee  mov     dword ptr [rsp+98h+Parameters.Header.Type], 140180h
0x14018c0f6  lea     rdx, [rsp+98h+Parameters]; Parameters
0x14018c0fb  mov     [rsp+98h+Parameters.fAllocateNetBuffer], 1
0x14018c100  movzx   eax, word ptr [rsi+24h]
0x14018c104  mov     [rsp+98h+Parameters.ContextSize], ax
0x14018c109  mov     [rsp+98h+Parameters.PoolTag], 6E535049h
0x14018c111  mov     [rsp+98h+Parameters.ProtocolId], 2
0x14018c116  mov     rcx, [rdi+60h]; NdisHandle
0x14018c11a  call    cs:__imp_NdisAllocateNetBufferListPool
0x14018c121  nop     dword ptr [rax+rax+00h]
0x14018c126  mov     [rdi+68h], rax
0x14018c12a  test    rax, rax
0x14018c12d  jnz     short loc_14018C149
0x14018c12f  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c135  mov     ebx, 0C000009Ah
0x14018c13a  jge     loc_14018C1C5
0x14018c140  lea     r9, aIpsClientNblPo; "IPS client NBL pool (IPNG)"
0x14018c147  jmp     short loc_14018C1B2
0x14018c149  mov     rcx, cs:IppDeviceObject; DeviceObject
0x14018c150  call    cs:__imp_IoAllocateWorkItem
0x14018c157  nop     dword ptr [rax+rax+00h]
0x14018c15c  mov     [rdi+78h], rax
0x14018c160  test    rax, rax
0x14018c163  jnz     short loc_14018C17B
0x14018c165  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c16b  mov     ebx, 0C000009Ah
0x14018c170  jge     short loc_14018C1C5
0x14018c172  lea     r9, aIpsClientWorki; "IPS client workitem (IPNG)"
0x14018c179  jmp     short loc_14018C1B2
0x14018c17b  mov     edx, 63535049h; PoolTag
0x14018c180  mov     ecx, 200h; PoolType
0x14018c185  call    cs:__imp_ExAllocateCacheAwareRundownProtection
0x14018c18c  nop     dword ptr [rax+rax+00h]
0x14018c191  mov     [rdi+48h], rax
0x14018c195  test    rax, rax
0x14018c198  jnz     loc_14018C22F
0x14018c19e  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+3, al
0x14018c1a4  mov     ebx, 0C000009Ah
0x14018c1a9  jge     short loc_14018C1C5
0x14018c1ab  lea     r9, aIpsClientRundo; "IPS client rundown object (IPNG)"
0x14018c1b2  lea     rdx, TCPIP_MEMORY_FAILURES
0x14018c1b9  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14018c1c0  call    McTemplateK0z_EtwWriteTransfer
0x14018c1c5  mov     rcx, [rdi+48h]; RunRefCacheAware
0x14018c1c9  test    rcx, rcx
0x14018c1cc  jz      short loc_14018C1DA
0x14018c1ce  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14018c1d5  nop     dword ptr [rax+rax+00h]
0x14018c1da  mov     rcx, [rdi+78h]; IoWorkItem
0x14018c1de  test    rcx, rcx
0x14018c1e1  jz      short loc_14018C1EF
0x14018c1e3  call    cs:__imp_IoFreeWorkItem
0x14018c1ea  nop     dword ptr [rax+rax+00h]
0x14018c1ef  mov     rcx, [rdi+68h]; PoolHandle
0x14018c1f3  test    rcx, rcx
0x14018c1f6  jz      short loc_14018C204
0x14018c1f8  call    cs:__imp_NdisFreeNetBufferListPool
0x14018c1ff  nop     dword ptr [rax+rax+00h]
0x14018c204  mov     rcx, [rdi+60h]; NdisObject
0x14018c208  test    rcx, rcx
0x14018c20b  jz      short loc_14018C219
0x14018c20d  call    cs:__imp_NdisFreeGenericObject
0x14018c214  nop     dword ptr [rax+rax+00h]
0x14018c219  xor     edx, edx; Tag
0x14018c21b  mov     rcx, rdi; P
0x14018c21e  call    cs:__imp_ExFreePoolWithTag
0x14018c225  nop     dword ptr [rax+rax+00h]
0x14018c22a  jmp     loc_14018C3FE
0x14018c22f  mov     rdx, [rsp+98h+var_68]
0x14018c234  mov     [r13+0], rdi
0x14018c238  mov     rax, [rbx+50h]
0x14018c23c  mov     [rdx], rax
0x14018c23f  call    cs:__imp_KeEnterCriticalRegion
0x14018c246  nop     dword ptr [rax+rax+00h]
0x14018c24b  xor     edx, edx
0x14018c24d  lea     rcx, [rbx+58h]
0x14018c251  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14018c258  nop     dword ptr [rax+rax+00h]
0x14018c25d  lea     rax, [rbx+60h]
0x14018c261  mov     rdx, [rax]
0x14018c264  cmp     [rdx+8], rax
0x14018c268  jz      short loc_14018C271
0x14018c26a  mov     ecx, 3
0x14018c26f  int     29h; Win8: RtlFailFast(ecx)
0x14018c271  mov     [rdi], rdx
0x14018c274  lea     r13, Ipv6Global
0x14018c27b  mov     [rdi+8], rax
0x14018c27f  mov     [rdx+8], rdi
0x14018c283  mov     [rax], rdi
0x14018c286  inc     dword ptr [rbx+70h]
0x14018c289  cmp     byte ptr [rdi+40h], 0
0x14018c28d  jnz     short loc_14018C2F7
0x14018c28f  inc     dword ptr [rbx+78h]
0x14018c292  mov     r8d, [rbx+78h]
0x14018c296  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c29d  cmp     rcx, r14
0x14018c2a0  jz      short loc_14018C2C5
0x14018c2a2  cmp     byte ptr [rcx+29h], 4
0x14018c2a6  jb      short loc_14018C2C5
0x14018c2a8  bt      dword ptr [rcx+2Ch], 17h
0x14018c2ad  jnb     short loc_14018C2C5
0x14018c2af  mov     rcx, [rcx+18h]
0x14018c2b3  mov     edx, 0Ch
0x14018c2b8  mov     r9, r12
0x14018c2bb  mov     [rsp+98h+var_78], r8d
0x14018c2c0  call    WPP_SF_Sd
0x14018c2c5  cmp     dword ptr [rbx+78h], 1
0x14018c2c9  jnz     short loc_14018C2F7
0x14018c2cb  mov     rcx, rdi
0x14018c2ce  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018c2d3  lea     rax, Ipv4Global
0x14018c2da  cmp     r15, rax
0x14018c2dd  jnz     short loc_14018C2E6
0x14018c2df  mov     ecx, 4
0x14018c2e4  jmp     short loc_14018C2F0
0x14018c2e6  cmp     r15, r13
0x14018c2e9  jnz     short loc_14018C2F7
0x14018c2eb  mov     ecx, 5
0x14018c2f0  mov     dl, 1
0x14018c2f2  call    TcpipUpdateUroDisabledMask
0x14018c2f7  cmp     byte ptr [rdi+3Fh], 0
0x14018c2fb  jnz     short loc_14018C366
0x14018c2fd  inc     dword ptr [rbx+74h]
0x14018c300  mov     r8d, [rbx+74h]
0x14018c304  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c30b  cmp     rcx, r14
0x14018c30e  jz      short loc_14018C333
0x14018c310  cmp     byte ptr [rcx+29h], 4
0x14018c314  jb      short loc_14018C333
0x14018c316  bt      dword ptr [rcx+2Ch], 17h
0x14018c31b  jnb     short loc_14018C333
0x14018c31d  mov     rcx, [rcx+18h]
0x14018c321  mov     edx, 0Dh
0x14018c326  mov     r9, r12
0x14018c329  mov     [rsp+98h+var_78], r8d
0x14018c32e  call    WPP_SF_Sd
0x14018c333  cmp     dword ptr [rbx+74h], 1
0x14018c337  jnz     short loc_14018C366
0x14018c339  mov     rcx, rdi
0x14018c33c  call    IppIpsNotifyNlClientsOnAllInterfaces
0x14018c341  lea     rax, Ipv4Global
0x14018c348  cmp     r15, rax
0x14018c34b  jnz     short loc_14018C358
0x14018c34d  lock bts cs:TcpipGlobalRscDisabledMask, 4
0x14018c356  jmp     short loc_14018C366
0x14018c358  cmp     r15, r13
0x14018c35b  jnz     short loc_14018C366
0x14018c35d  lock bts cs:TcpipGlobalRscDisabledMask, 5
0x14018c366  mov     dl, 1
0x14018c368  mov     rcx, rdi
0x14018c36b  call    IppUpdateIpsServiceChainsForClient
0x14018c370  xor     edx, edx
0x14018c372  lea     rcx, [rbx+58h]
0x14018c376  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14018c37d  nop     dword ptr [rax+rax+00h]
0x14018c382  call    cs:__imp_KeLeaveCriticalRegion
0x14018c389  nop     dword ptr [rax+rax+00h]
0x14018c38e  xor     ebx, ebx
0x14018c390  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c397  cmp     rcx, r14
0x14018c39a  jz      short loc_14018C3FE
0x14018c39c  cmp     byte ptr [rcx+29h], 4
0x14018c3a0  jb      short loc_14018C3FE
0x14018c3a2  bt      dword ptr [rcx+2Ch], 17h
0x14018c3a7  jnb     short loc_14018C3FE
0x14018c3a9  mov     rcx, [rcx+18h]
0x14018c3ad  lea     edx, [rbx+0Eh]
0x14018c3b0  mov     r9, r12
0x14018c3b3  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018c3ba  call    WPP_SF_S
0x14018c3bf  jmp     short loc_14018C3FE
0x14018c3c1  mov     ebx, 0C000000Dh
0x14018c3c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14018c3cd  lea     r14, WPP_GLOBAL_Control
0x14018c3d4  cmp     rcx, r14
0x14018c3d7  jz      short loc_14018C3FE
0x14018c3d9  cmp     byte ptr [rcx+29h], 2
0x14018c3dd  jb      short loc_14018C3FE
0x14018c3df  bt      dword ptr [rcx+2Ch], 17h
0x14018c3e4  jnb     short loc_14018C3FE
0x14018c3e6  mov     rcx, [rcx+18h]
0x14018c3ea  lea     r8, WPP_ac85ee5d021131934f4c5188022bc398_Traceguids
0x14018c3f1  mov     edx, 0Ah
0x14018c3f6  mov     r9d, ebx
0x14018c3f9  call    WPP_SF_d
0x14018c3fe  mov     eax, ebx
0x14018c400  mov     rcx, [rsp+98h+var_48]
0x14018c405  xor     rcx, rsp; StackCookie
0x14018c408  call    __security_check_cookie
0x14018c40d  mov     rbx, [rsp+98h+arg_0]
0x14018c415  add     rsp, 60h
0x14018c419  pop     r15
  ... truncated ...
```
