# SrvNetBuildNetname

- ea: `0x14004fbf0`
- end: `0x1400501c0`
- name: `SrvNetBuildNetname`
- size: `1488`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140005ba0`

## callees

- `0x140005e10`
- `0x140007c60`
- `0x140007ec0`
- `0x140009580`
- `0x14001389c`
- `0x140015790`
- `0x14002a3e0`
- `0x14002a540`
- `0x14002a840`
- `0x14004fbf0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14004fe41`
- `ntoskrnl!ObfDereferenceObject` at `0x14004fec3`
- `ntoskrnl!ObfDereferenceObject` at `0x14004fe41`
- `ntoskrnl!ObfDereferenceObject` at `0x14004fec3`
- `ntoskrnl!IoWMIOpenBlock` at `0x14004fe23`
- `ntoskrnl!IoWMIOpenBlock` at `0x14004fea5`
- `ntoskrnl!IoWMIOpenBlock` at `0x14004fe23`
- `ntoskrnl!IoWMIOpenBlock` at `0x14004fea5`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x14004ffe4`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x140050022`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x1400575af`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x140057617`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x14004ffe4`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x140050022`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x1400575af`
- `ntoskrnl!IoWMIQuerySingleInstance` at `0x140057617`
- `ntoskrnl!ExAllocatePool2` at `0x140057589`
- `ntoskrnl!ExAllocatePool2` at `0x1400575f1`
- `ntoskrnl!ExAllocatePool2` at `0x140057589`
- `ntoskrnl!ExAllocatePool2` at `0x1400575f1`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004fe08`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004fe8a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004fe08`
- `ntoskrnl!RtlInitUnicodeString` at `0x14004fe8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400575cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057634`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400575cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057634`
- `NETIO!FreeMibTable` at `0x14005010e`
- `NETIO!FreeMibTable` at `0x14005010e`
- `NETIO!ConvertInterfaceIndexToLuid` at `0x14004fd9d`
- `NETIO!ConvertInterfaceIndexToLuid` at `0x14004fd9d`
- `NETIO!GetUnicastIpAddressTable` at `0x14004fc5c`
- `NETIO!GetUnicastIpAddressTable` at `0x14004fc5c`
- `NETIO!GetIfEntry2` at `0x14004fdb4`
- `NETIO!GetIfEntry2` at `0x14004fdb4`

## pseudocode

```c
__int64 __fastcall SrvNetBuildNetname(__int64 *a1, unsigned int *a2)
{
  unsigned int *v2; // r12
  __int64 *v3; // r15
  NTSTATUS UnicastIpAddressTable; // eax
  unsigned int v5; // ebx
  PMIB_UNICASTIPADDRESS_TABLE v6; // rdx
  __int64 v7; // rbx
  __int64 i; // rdi
  unsigned int v9; // ebx
  __int64 PoolWithTag; // rax
  __int64 v11; // r14
  __int64 v12; // rsi
  _DWORD *v13; // r13
  size_t v14; // r8
  __int64 v15; // rdx
  MIB_UNICASTIPADDRESS_ROW *v16; // rdx
  NET_IFINDEX v17; // r15d
  NET_LUID *v18; // rax
  struct _MIB_IF_ROW2 *v19; // rbx
  int v20; // r14d
  int v21; // r14d
  bool v22; // r12
  ULONG64 TransmitLinkSpeed; // r14
  bool v24; // r15
  __int64 v25; // rax
  NTSTATUS v26; // eax
  NTSTATUS v27; // eax
  unsigned int *Pool2; // rax
  unsigned int *v30; // r15
  unsigned int *v31; // rax
  unsigned int *v32; // r15
  char v33; // [rsp+28h] [rbp-E0h]
  ULONG InOutBufferSize; // [rsp+2Ch] [rbp-DCh] BYREF
  __int64 v35; // [rsp+30h] [rbp-D8h]
  PVOID DataBlockObject; // [rsp+38h] [rbp-D0h] BYREF
  PMIB_UNICASTIPADDRESS_TABLE Table; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int DestinationString; // [rsp+48h] [rbp-C0h]
  NTSTATUS DestinationString_4; // [rsp+4Ch] [rbp-BCh]
  struct _UNICODE_STRING DestinationString_8; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+60h] [rbp-A8h]
  __int64 *v42; // [rsp+68h] [rbp-A0h]
  _QWORD Guid[3]; // [rsp+70h] [rbp-98h] BYREF
  _DWORD v44[128]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE OutBuffer[56]; // [rsp+288h] [rbp+180h] BYREF
  int v46; // [rsp+2C0h] [rbp+1B8h]

  v2 = a2;
  v3 = a1;
  Guid[0] = a2;
  v42 = a1;
  HIDWORD(Guid[1]) = 0;
  memset(v44, 0, sizeof(v44));
  Table = 0;
  UnicastIpAddressTable = GetUnicastIpAddressTable(0, &Table);
  DestinationString_4 = UnicastIpAddressTable;
  v5 = UnicastIpAddressTable;
  if ( UnicastIpAddressTable < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        55,
        WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids,
        (unsigned int)UnicastIpAddressTable);
    }
    goto LABEL_49;
  }
  v6 = Table;
  v7 = 0;
  for ( i = 0; (unsigned int)v7 < Table->NumEntries; v7 = (unsigned int)(v7 + 1) )
  {
    if ( !(unsigned __int8)SrvNetSkipAddress(&v6->Table[v7]) )
    {
      v44[i] = v7;
      i = (unsigned int)(i + 1);
      if ( (unsigned int)i >= 0x80 )
        break;
    }
    v6 = Table;
  }
  v9 = 152 * i + 26;
  DestinationString = v9;
  PoolWithTag = SrvNetAllocatePoolWithTag(64, v9, 1717719884);
  v41 = PoolWithTag;
  v11 = PoolWithTag;
  if ( !PoolWithTag )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids);
    }
    v5 = -1073741670;
    goto LABEL_49;
  }
  v12 = PoolWithTag + 24;
  v13 = 0;
  if ( !(_DWORD)i )
    goto LABEL_31;
  do
  {
    i = (unsigned int)(i - 1);
    v14 = 16;
    v15 = (unsigned int)v44[i];
    *(_DWORD *)(v12 + 4) = Table->Table[v15].InterfaceIndex;
    v16 = &Table->Table[v15];
    if ( v16->Address.Ipv4.sin_family != 2 )
      v14 = 28;
    if ( v16->Address.Ipv4.sin_family == 23 )
      v16->Address.Ipv6.sin6_scope_id = 0;
    memmove((void *)(v12 + 24), v16, v14);
    v17 = *(_DWORD *)(v12 + 4);
    LODWORD(v35) = v17;
    v18 = (NET_LUID *)SrvNetAllocatePoolWithTag(64, 1352, 1717719884);
    v19 = (struct _MIB_IF_ROW2 *)v18;
    if ( v18 )
    {
      if ( !ConvertInterfaceIndexToLuid(v17, v18) && !GetIfEntry2(v19) )
      {
        v33 = 0;
        *(GUID *)&Guid[1] = GUID_NDIS_RSS_ENABLED;
        v20 = 0;
        DataBlockObject = 0;
        DestinationString_8 = 0;
        InOutBufferSize = 264;
        RtlInitUnicodeString(&DestinationString_8, v19->Description);
        if ( !IoWMIOpenBlock((LPCGUID)&Guid[1], 1u, &DataBlockObject) )
        {
          v26 = IoWMIQuerySingleInstance(DataBlockObject, &DestinationString_8, &InOutBufferSize, OutBuffer);
          if ( v26 )
          {
            if ( v26 == -1073741789 )
            {
              Pool2 = (unsigned int *)ExAllocatePool2(66, InOutBufferSize, 1717719884);
              v30 = Pool2;
              if ( Pool2 )
              {
                IoWMIQuerySingleInstance(DataBlockObject, &DestinationString_8, &InOutBufferSize, Pool2);
                v20 = *((unsigned __int8 *)v30 + v30[14]);
                ExFreePoolWithTag(v30, 0x6662534Cu);
              }
              v17 = v35;
            }
          }
          else
          {
            v20 = (unsigned __int8)OutBuffer[v46];
          }
        }
        if ( DataBlockObject )
          ObfDereferenceObject(DataBlockObject);
        if ( v20 )
          v33 = 1;
        DataBlockObject = 0;
        InOutBufferSize = 264;
        *(GUID *)&Guid[1] = GUID_NDIS_NDK_STATE;
        v21 = 0;
        DestinationString_8 = 0;
        RtlInitUnicodeString(&DestinationString_8, v19->Description);
        if ( !IoWMIOpenBlock((LPCGUID)&Guid[1], 1u, &DataBlockObject) )
        {
          v27 = IoWMIQuerySingleInstance(DataBlockObject, &DestinationString_8, &InOutBufferSize, OutBuffer);
          if ( v27 )
          {
            if ( v27 == -1073741789 )
            {
              v31 = (unsigned int *)ExAllocatePool2(66, InOutBufferSize, 1717719884);
              v32 = v31;
              if ( v31 )
              {
                IoWMIQuerySingleInstance(DataBlockObject, &DestinationString_8, &InOutBufferSize, v31);
                v21 = *((unsigned __int8 *)v32 + v32[14]);
                ExFreePoolWithTag(v32, 0x6662534Cu);
              }
              v17 = v35;
            }
          }
          else
          {
            v21 = (unsigned __int8)OutBuffer[v46];
          }
        }
        if ( DataBlockObject )
          ObfDereferenceObject(DataBlockObject);
        v22 = v21 != 0;
        TransmitLinkSpeed = v19->TransmitLinkSpeed;
        v24 = (unsigned __int8)SrvNetQueryLbfoTeamCapability(v17) != 0;
        SrvNetWskNotifyCleanupProviderContext(v19);
        if ( v33 || v24 )
          *(_DWORD *)(v12 + 8) |= 1u;
        if ( v22 )
          *(_DWORD *)(v12 + 8) |= 2u;
        *(_QWORD *)(v12 + 16) = TransmitLinkSpeed;
        goto LABEL_27;
      }
      SrvNetWskNotifyCleanupProviderContext(v19);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids);
    }
LABEL_27:
    if ( v13 )
      *v13 = 152;
    v13 = (_DWORD *)v12;
    v12 += 152;
  }
  while ( (_DWORD)i );
  v11 = v41;
  v9 = DestinationString;
  v3 = v42;
  v2 = (unsigned int *)Guid[0];
LABEL_31:
  *(_DWORD *)(v11 + 16) = 1;
  *(_DWORD *)v11 = 131074;
  *(_QWORD *)(v11 + 8) = v12;
  *(_DWORD *)(v11 + 20) = v12 - v11 - 24;
  memmove((void *)v12, L"*", 2u);
  v25 = *(_QWORD *)(v11 + 8);
  if ( v25 )
    v25 -= v11;
  *(_QWORD *)(v11 + 8) = v25;
  *v2 = v9;
  v5 = DestinationString_4;
  *v3 = v11;
LABEL_49:
  if ( Table )
    FreeMibTable(Table);
  return v5;
}

```

## disassembly

```asm
0x14004fbf0  mov     r11, rsp
0x14004fbf3  push    rbp
0x14004fbf4  push    rbx
0x14004fbf5  lea     rbp, [r11-2D8h]
0x14004fbfc  sub     rsp, 3C8h
0x14004fc03  mov     rax, cs:__security_cookie
0x14004fc0a  xor     rax, rsp
0x14004fc0d  mov     [rbp+2D0h+var_40], rax
0x14004fc14  mov     [r11+18h], rsi
0x14004fc18  xor     eax, eax
0x14004fc1a  mov     [r11-20h], r12
0x14004fc1e  mov     r8d, 200h; Size
0x14004fc24  mov     [r11-38h], r15
0x14004fc28  mov     r12, rdx
0x14004fc2b  mov     r15, rcx
0x14004fc2e  mov     qword ptr [rsp+3D0h+Guid], rdx
0x14004fc33  mov     [rsp+3D0h+var_370], rcx
0x14004fc38  xor     edx, edx; Val
0x14004fc3a  lea     rcx, [rbp+2D0h+var_350]; void *
0x14004fc3e  mov     dword ptr [rsp+3D0h+Guid+0Ch], eax
0x14004fc42  mov     esi, 2
0x14004fc47  call    memset
0x14004fc4c  xor     ecx, ecx; Family
0x14004fc4e  mov     [rsp+3D0h+Table], 0
0x14004fc57  lea     rdx, [rsp+3D0h+Table]; Table
0x14004fc5c  call    cs:__imp_GetUnicastIpAddressTable
0x14004fc63  nop     dword ptr [rax+rax+00h]
0x14004fc68  mov     dword ptr [rsp+3D0h+DestinationString+4], eax
0x14004fc6c  mov     ebx, eax
0x14004fc6e  test    eax, eax
0x14004fc70  js      loc_140050091
0x14004fc76  mov     rdx, [rsp+3D0h+Table]
0x14004fc7b  xor     ebx, ebx
0x14004fc7d  mov     [rsp+3C0h], rdi
0x14004fc85  xor     edi, edi
0x14004fc87  mov     [rsp+3D0h+var_28], r14
0x14004fc8f  cmp     [rdx], ebx
0x14004fc91  jbe     short loc_14004FCC7
0x14004fc93  nop     dword ptr [rax+00h]
0x14004fc97  nop     word ptr [rax+rax+00000000h]
0x14004fca0  add     rdx, 8
0x14004fca4  lea     rcx, [rbx+rbx*4]
0x14004fca8  shl     rcx, 4
0x14004fcac  add     rcx, rdx
0x14004fcaf  call    SrvNetSkipAddress
0x14004fcb4  test    al, al
0x14004fcb6  jz      loc_14004FFB7
0x14004fcbc  mov     rdx, [rsp+3D0h+Table]
0x14004fcc1  inc     ebx
0x14004fcc3  cmp     ebx, [rdx]
0x14004fcc5  jb      short loc_14004FCA0
0x14004fcc7  imul    ecx, edi, 98h
0x14004fccd  lea     ebx, [rsi+18h]
0x14004fcd0  mov     r8d, 6662534Ch
0x14004fcd6  add     ebx, ecx
0x14004fcd8  mov     ecx, 40h ; '@'
0x14004fcdd  mov     edx, ebx
0x14004fcdf  mov     dword ptr [rsp+3D0h+DestinationString.Length], ebx
0x14004fce3  call    SrvNetAllocatePoolWithTag
0x14004fce8  mov     [rsp+3D0h+var_378], rax
0x14004fced  mov     r14, rax
0x14004fcf0  test    rax, rax
0x14004fcf3  jz      loc_140050136
0x14004fcf9  mov     [rsp+3D0h+var_20], r13
0x14004fd01  lea     rsi, [rax+18h]
0x14004fd05  xor     r13d, r13d
0x14004fd08  test    edi, edi
0x14004fd0a  jz      loc_14004FF63
0x14004fd10  lea     r14, WPP_GLOBAL_Control
0x14004fd17  mov     r9d, 1Ch
0x14004fd1d  nop     dword ptr [rax]
0x14004fd20  mov     rax, [rsp+3D0h+Table]
0x14004fd25  dec     edi
0x14004fd27  mov     r8d, 10h
0x14004fd2d  mov     ecx, [rbp+rdi*4+2D0h+var_350]
0x14004fd31  lea     rdx, [rcx+rcx*4]
0x14004fd35  shl     rdx, 4
0x14004fd39  mov     ecx, [rdx+rax+30h]
0x14004fd3d  mov     [rsi+4], ecx
0x14004fd40  mov     rax, [rsp+3D0h+Table]
0x14004fd45  add     rax, 8
0x14004fd49  add     rdx, rax; Src
0x14004fd4c  movzx   eax, word ptr [rdx]
0x14004fd4f  cmp     ax, 2
0x14004fd53  cmovnz  r8, r9; Size
0x14004fd57  cmp     ax, 17h
0x14004fd5b  jnz     short loc_14004FD64
0x14004fd5d  mov     dword ptr [rdx+18h], 0
0x14004fd64  lea     rcx, [rsi+18h]; void *
0x14004fd68  call    memmove
0x14004fd6d  mov     r15d, [rsi+4]
0x14004fd71  mov     edx, 548h
0x14004fd76  mov     ecx, 40h ; '@'
0x14004fd7b  mov     dword ptr [rsp+3D0h+var_3A8], r15d
0x14004fd80  mov     r8d, 6662534Ch
0x14004fd86  call    SrvNetAllocatePoolWithTag
0x14004fd8b  mov     rbx, rax
0x14004fd8e  test    rax, rax
0x14004fd91  jz      loc_140050052
0x14004fd97  mov     rdx, rax; InterfaceLuid
0x14004fd9a  mov     ecx, r15d; InterfaceIndex
0x14004fd9d  call    cs:__imp_ConvertInterfaceIndexToLuid
0x14004fda4  nop     dword ptr [rax+rax+00h]
0x14004fda9  test    eax, eax
0x14004fdab  jnz     loc_14005004A
0x14004fdb1  mov     rcx, rbx; Row
0x14004fdb4  call    cs:__imp_GetIfEntry2
0x14004fdbb  nop     dword ptr [rax+rax+00h]
0x14004fdc0  test    eax, eax
0x14004fdc2  jnz     loc_14005004A
0x14004fdc8  movups  xmm0, xmmword ptr cs:GUID_NDIS_RSS_ENABLED.Data1
0x14004fdcf  lea     rdx, [rbx+21Eh]; SourceString
0x14004fdd6  mov     byte ptr [rsp+3D0h+var_3B0], al
0x14004fdda  lea     rcx, [rsp+3D0h+DestinationString.Buffer]; DestinationString
0x14004fddf  mov     byte ptr [rsp+3D0h+var_3B0+1], al
0x14004fde3  movups  xmmword ptr [rsp+3D0h+Guid+8], xmm0
0x14004fde8  mov     byte ptr [rsp+3D0h+var_3B0+2], al
0x14004fdec  xor     r14d, r14d
0x14004fdef  xorps   xmm0, xmm0
0x14004fdf2  mov     [rsp+3D0h+DataBlockObject], 0
0x14004fdfb  movups  xmmword ptr [rsp+3D0h+DestinationString.Buffer], xmm0
0x14004fe00  mov     [rsp+3D0h+InOutBufferSize], 108h
0x14004fe08  call    cs:__imp_RtlInitUnicodeString
0x14004fe0f  nop     dword ptr [rax+rax+00h]
0x14004fe14  lea     r8, [rsp+3D0h+DataBlockObject]; DataBlockObject
0x14004fe19  mov     edx, 1; DesiredAccess
0x14004fe1e  lea     rcx, [rsp+3D0h+Guid+8]; Guid
0x14004fe23  call    cs:__imp_IoWMIOpenBlock
0x14004fe2a  nop     dword ptr [rax+rax+00h]
0x14004fe2f  test    eax, eax
0x14004fe31  jz      loc_14004FFCE
0x14004fe37  mov     rcx, [rsp+3D0h+DataBlockObject]; Object
0x14004fe3c  test    rcx, rcx
0x14004fe3f  jz      short loc_14004FE4D
0x14004fe41  call    cs:__imp_ObfDereferenceObject
0x14004fe48  nop     dword ptr [rax+rax+00h]
0x14004fe4d  test    r14d, r14d
0x14004fe50  jnz     loc_14005019D
0x14004fe56  movups  xmm0, xmmword ptr cs:GUID_NDIS_NDK_STATE.Data1
0x14004fe5d  lea     rdx, [rbx+21Eh]; SourceString
0x14004fe64  mov     [rsp+3D0h+DataBlockObject], 0
0x14004fe6d  lea     rcx, [rsp+3D0h+DestinationString.Buffer]; DestinationString
0x14004fe72  mov     [rsp+3D0h+InOutBufferSize], 108h
0x14004fe7a  movups  xmmword ptr [rsp+3D0h+Guid+8], xmm0
0x14004fe7f  xor     r14d, r14d
0x14004fe82  xorps   xmm0, xmm0
0x14004fe85  movups  xmmword ptr [rsp+3D0h+DestinationString.Buffer], xmm0
0x14004fe8a  call    cs:__imp_RtlInitUnicodeString
0x14004fe91  nop     dword ptr [rax+rax+00h]
0x14004fe96  lea     r8, [rsp+3D0h+DataBlockObject]; DataBlockObject
0x14004fe9b  mov     edx, 1; DesiredAccess
0x14004fea0  lea     rcx, [rsp+3D0h+Guid+8]; Guid
0x14004fea5  call    cs:__imp_IoWMIOpenBlock
0x14004feac  nop     dword ptr [rax+rax+00h]
0x14004feb1  test    eax, eax
0x14004feb3  jz      loc_14005000C
0x14004feb9  mov     rcx, [rsp+3D0h+DataBlockObject]; Object
0x14004febe  test    rcx, rcx
0x14004fec1  jz      short loc_14004FECF
0x14004fec3  call    cs:__imp_ObfDereferenceObject
0x14004feca  nop     dword ptr [rax+rax+00h]
0x14004fecf  test    r14d, r14d
0x14004fed2  jnz     loc_1400501A7
0x14004fed8  movzx   r12d, byte ptr [rsp+3D0h+var_3B0+1]
0x14004fede  mov     r14, [rbx+4A8h]
0x14004fee5  mov     ecx, r15d; InterfaceIndex
0x14004fee8  call    SrvNetQueryLbfoTeamCapability
0x14004feed  test    al, al
0x14004feef  jnz     loc_1400501AF
0x14004fef5  movzx   r15d, byte ptr [rsp+3D0h+var_3B0+2]
0x14004fefb  mov     rcx, rbx
0x14004fefe  call    SrvNetWskNotifyCleanupProviderContext
0x14004ff03  cmp     byte ptr [rsp+3D0h+var_3B0], 0
0x14004ff08  jnz     loc_140050170
0x14004ff0e  test    r15b, r15b
0x14004ff11  jnz     loc_140050170
0x14004ff17  test    r12b, r12b
0x14004ff1a  jnz     loc_1400501B7
0x14004ff20  mov     [rsi+10h], r14
0x14004ff24  lea     r14, WPP_GLOBAL_Control
0x14004ff2b  test    r13, r13
0x14004ff2e  jz      short loc_14004FF38
0x14004ff30  mov     dword ptr [r13+0], 98h
0x14004ff38  mov     r13, rsi
0x14004ff3b  mov     r9d, 1Ch
0x14004ff41  add     rsi, 98h
0x14004ff48  test    edi, edi
0x14004ff4a  jnz     loc_14004FD20
0x14004ff50  mov     r14, [rsp+3D0h+var_378]
0x14004ff55  mov     ebx, dword ptr [rsp+3D0h+DestinationString.Length]
0x14004ff59  mov     r15, [rsp+3D0h+var_370]
0x14004ff5e  mov     r12, qword ptr [rsp+3D0h+Guid]
0x14004ff63  mov     eax, esi
0x14004ff65  mov     dword ptr [r14+10h], 1
0x14004ff6d  sub     eax, r14d
0x14004ff70  mov     dword ptr [r14], 20002h
0x14004ff77  sub     eax, 18h
0x14004ff7a  mov     [r14+8], rsi
0x14004ff7e  mov     [r14+14h], eax
0x14004ff82  lea     rdx, Buf2; "*"
0x14004ff89  mov     eax, 2
0x14004ff8e  mov     rcx, rsi; void *
0x14004ff91  movzx   r8d, ax; Size
0x14004ff95  call    memmove
0x14004ff9a  mov     rax, [r14+8]
0x14004ff9e  mov     r13, [rsp+3D0h+var_20]
0x14004ffa6  test    rax, rax
0x14004ffa9  jz      loc_1400500CD
0x14004ffaf  sub     rax, r14
0x14004ffb2  jmp     loc_1400500CD
0x14004ffb7  mov     [rbp+rdi*4+2D0h+var_350], ebx
0x14004ffbb  inc     edi
0x14004ffbd  cmp     edi, 80h
0x14004ffc3  jb      loc_14004FCBC
0x14004ffc9  jmp     loc_14004FCC7
0x14004ffce  mov     rcx, [rsp+3D0h+DataBlockObject]; DataBlockObject
0x14004ffd3  lea     r9, [rbp+2D0h+OutBuffer]; OutBuffer
0x14004ffda  lea     r8, [rsp+3D0h+InOutBufferSize]; InOutBufferSize
0x14004ffdf  lea     rdx, [rsp+3D0h+DestinationString.Buffer]; InstanceName
0x14004ffe4  call    cs:__imp_IoWMIQuerySingleInstance
0x14004ffeb  nop     dword ptr [rax+rax+00h]
0x14004fff0  test    eax, eax
0x14004fff2  jnz     loc_140050150
0x14004fff8  mov     eax, [rbp+2D0h+var_118]
0x14004fffe  movzx   r14d, [rbp+rax+2D0h+OutBuffer]
0x140050007  jmp     loc_14004FE37
0x14005000c  mov     rcx, [rsp+3D0h+DataBlockObject]; DataBlockObject
0x140050011  lea     r9, [rbp+2D0h+OutBuffer]; OutBuffer
0x140050018  lea     r8, [rsp+3D0h+InOutBufferSize]; InOutBufferSize
0x14005001d  lea     rdx, [rsp+3D0h+DestinationString.Buffer]; InstanceName
0x140050022  call    cs:__imp_IoWMIQuerySingleInstance
0x140050029  nop     dword ptr [rax+rax+00h]
0x14005002e  test    eax, eax
0x140050030  jnz     loc_140050160
0x140050036  mov     eax, [rbp+2D0h+var_118]
0x14005003c  movzx   r14d, [rbp+rax+2D0h+OutBuffer]
0x140050045  jmp     loc_14004FEB9
0x14005004a  mov     rcx, rbx
0x14005004d  call    SrvNetWskNotifyCleanupProviderContext
0x140050052  mov     rcx, cs:WPP_GLOBAL_Control
0x140050059  cmp     rcx, r14
0x14005005c  jz      loc_14004FF2B
0x140050062  mov     eax, [rcx+2Ch]
0x140050065  test    al, 10h
0x140050067  jz      loc_14004FF2B
0x14005006d  cmp     byte ptr [rcx+29h], 1
0x140050071  jb      loc_14004FF2B
0x140050077  mov     rcx, [rcx+18h]
0x14005007b  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x140050082  mov     edx, 39h ; '9'
0x140050087  call    WPP_SF_
0x14005008c  jmp     loc_14004FF2B
0x140050091  mov     rcx, cs:WPP_GLOBAL_Control
0x140050098  lea     rdx, WPP_GLOBAL_Control
0x14005009f  cmp     rcx, rdx
0x1400500a2  jz      short loc_1400500EC
0x1400500a4  test    dword ptr [rcx+2Ch], 2000h
0x1400500ab  jz      short loc_1400500EC
0x1400500ad  cmp     byte ptr [rcx+29h], 1
0x1400500b1  jb      short loc_1400500EC
0x1400500b3  mov     rcx, [rcx+18h]
0x1400500b7  lea     r8, WPP_2f093813b8de3a1fa94938d92bffe8bb_Traceguids
0x1400500be  mov     edx, 37h ; '7'
0x1400500c3  mov     r9d, eax
0x1400500c6  call    WPP_SF_d
0x1400500cb  jmp     short loc_1400500EC
0x1400500cd  mov     [r14+8], rax
0x1400500d1  mov     [r12], ebx
0x1400500d5  mov     ebx, dword ptr [rsp+3D0h+DestinationString+4]
0x1400500d9  mov     [r15], r14
0x1400500dc  mov     rdi, [rsp+3C0h]
0x1400500e4  mov     r14, [rsp+3D0h+var_28]
0x1400500ec  mov     rcx, [rsp+3D0h+Table]; Memory
0x1400500f1  mov     r15, [rsp+3D0h+var_30]
0x1400500f9  mov     r12, [rsp+3D0h+var_18]
0x140050101  mov     rsi, [rsp+3D0h+arg_10]
0x140050109  test    rcx, rcx
0x14005010c  jz      short loc_14005011A
0x14005010e  call    cs:__imp_FreeMibTable
0x140050115  nop     dword ptr [rax+rax+00h]
0x14005011a  mov     eax, ebx
0x14005011c  mov     rcx, [rbp+2D0h+var_40]
0x140050123  xor     rcx, rsp; StackCookie
0x140050126  call    __security_check_cookie
0x14005012b  add     rsp, 3C8h
0x140050132  pop     rbx
0x140050133  pop     rbp
0x140050134  retn
0x140050136  mov     rcx, cs:WPP_GLOBAL_Control
0x14005013d  lea     rdx, WPP_GLOBAL_Control
0x140050144  cmp     rcx, rdx
0x140050147  jnz     short loc_140050179
0x140050149  mov     ebx, 0C000009Ah
0x14005014e  jmp     short loc_1400500DC
0x140050150  cmp     eax, 0C0000023h
0x140050155  jnz     loc_14004FE37
0x14005015b  jmp     loc_14005757A
0x140050160  cmp     eax, 0C0000023h
0x140050165  jnz     loc_14004FEB9
0x14005016b  jmp     loc_1400575E2
  ... truncated ...
```
