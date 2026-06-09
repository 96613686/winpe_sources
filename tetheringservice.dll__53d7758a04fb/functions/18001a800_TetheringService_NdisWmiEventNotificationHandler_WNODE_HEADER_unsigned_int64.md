# TetheringService::NdisWmiEventNotificationHandler(_WNODE_HEADER *,unsigned __int64)

- ea: `0x18001a800`
- end: `0x18001aae1`
- name: `?NdisWmiEventNotificationHandler@TetheringService@@CAXPEAU_WNODE_HEADER@@_K@Z`
- size: `737`
- prototype: `void __fastcall(struct _WNODE_HEADER *, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180002590`
- `0x180002ffa`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x1800132c8`
- `0x18001a800`
- `0x18001acb4`
- `0x18001ff08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001a8e0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001a8e0`
- `RPCRT4!UuidFromStringW` at `0x18001a900`
- `RPCRT4!UuidFromStringW` at `0x18001a900`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18001a937`
- `IPHLPAPI!ConvertInterfaceLuidToIndex` at `0x18001a937`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001a91e`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18001a91e`

## pseudocode

```c
void __fastcall TetheringService::NdisWmiEventNotificationHandler(struct _WNODE_HEADER *a1, __int64 a2)
{
  TetheringServiceTelemetry *v4; // rcx
  __int64 Version; // rsi
  __int64 v6; // rdx
  __int64 v7; // rcx
  char *v8; // rax
  NTSTATUS SharedInterfaceIndices; // eax
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rdx
  ULONG InterfaceIndex; // [rsp+20h] [rbp-59h] BYREF
  unsigned int v15; // [rsp+24h] [rbp-55h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-51h] BYREF
  NET_LUID InterfaceLuid; // [rsp+30h] [rbp-49h] BYREF
  UUID Uuid; // [rsp+38h] [rbp-41h] BYREF
  unsigned __int16 StringUuid[8]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v20; // [rsp+60h] [rbp-19h]
  __int128 v21; // [rsp+70h] [rbp-9h]
  __int128 v22; // [rsp+80h] [rbp+7h]
  __int64 v23; // [rsp+90h] [rbp+17h]

  if ( !a2 )
    return;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 358, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)&a1->Guid.Data1 != *(_QWORD *)&GUID_NDIS_NOTIFY_ADAPTER_REMOVAL.Data1
    || *(_QWORD *)a1->Guid.Data4 != *(_QWORD *)GUID_NDIS_NOTIFY_ADAPTER_REMOVAL.Data4 )
  {
    goto LABEL_45;
  }
  Version = a1[1].Version;
  if ( *(_WORD *)((char *)&a1->BufferSize + Version) != 92 )
  {
    if ( v4 == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)v4 + 28) & 8) == 0 )
      goto LABEL_45;
    v12 = 364;
LABEL_43:
    WPP_SF_(*((_QWORD *)v4 + 2), v12, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    goto LABEL_44;
  }
  memset_0(StringUuid, 0, 0x4Au);
  v8 = (char *)&a1->TimeStamp.QuadPart + Version + 4;
  if ( v8 )
  {
    *(_OWORD *)StringUuid = *(_OWORD *)v8;
    v20 = *((_OWORD *)v8 + 1);
    v21 = *((_OWORD *)v8 + 2);
    v22 = *((_OWORD *)v8 + 3);
    v23 = *((_QWORD *)v8 + 8);
  }
  else
  {
    *(_DWORD *)_o__errno(v7, v6) = 22;
    invalid_parameter_noinfo();
  }
  Uuid = 0;
  if ( UuidFromStringW(StringUuid, &Uuid) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_45;
    v12 = 363;
    goto LABEL_43;
  }
  InterfaceLuid.Value = 0;
  SharedInterfaceIndices = ConvertInterfaceGuidToLuid(&Uuid, &InterfaceLuid);
  if ( SharedInterfaceIndices )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_45;
    v13 = 362;
LABEL_30:
    WPP_SF_d(
      *((_QWORD *)v4 + 2),
      v13,
      &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
      (unsigned int)SharedInterfaceIndices);
LABEL_44:
    v4 = WPP_GLOBAL_Control;
LABEL_45:
    if ( v4 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)v4 + 2), 365, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
    return;
  }
  InterfaceIndex = 0;
  SharedInterfaceIndices = ConvertInterfaceLuidToIndex(&InterfaceLuid, &InterfaceIndex);
  if ( SharedInterfaceIndices )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_45;
    v13 = 361;
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 359, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, InterfaceIndex);
  }
  v15 = 0;
  v16 = 0;
  SharedInterfaceIndices = InterfaceMgr::GetSharedInterfaceIndices((InterfaceMgr *)(a2 + 352), &v15, &v16);
  if ( SharedInterfaceIndices < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
      return;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_45;
    v13 = 360;
    goto LABEL_30;
  }
  if ( InterfaceIndex != v15 )
  {
    if ( InterfaceIndex == v16 )
      TetheringService::NotifyPrivateConnectionDown((TetheringService *)a2);
    goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 298, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
  }
  TetheringService::StopSharingAsync(a2, 3, v10, v11);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_45;
    v12 = 299;
    goto LABEL_43;
  }
}

```

## disassembly

```asm
0x18001a800  test    rdx, rdx
0x18001a803  jz      locret_18001AAE0
0x18001a809  mov     [rsp-8+arg_10], rbx
0x18001a80e  push    rbp
0x18001a80f  push    rsi
0x18001a810  push    rdi
0x18001a811  push    r12
0x18001a813  push    r14
0x18001a815  lea     rbp, [rsp-37h]
0x18001a81a  sub     rsp, 0B0h
0x18001a821  mov     rax, cs:__security_cookie
0x18001a828  xor     rax, rsp
0x18001a82b  mov     [rbp+57h+var_30], rax
0x18001a82f  mov     rdi, rdx
0x18001a832  mov     rbx, rcx
0x18001a835  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a83c  lea     r14, WPP_GLOBAL_Control
0x18001a843  lea     r12, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001a84a  cmp     rcx, r14
0x18001a84d  jz      short loc_18001A86D
0x18001a84f  test    byte ptr [rcx+1Ch], 8
0x18001a853  jz      short loc_18001A86D
0x18001a855  mov     rcx, [rcx+10h]
0x18001a859  mov     edx, 166h
0x18001a85e  mov     r8, r12
0x18001a861  call    WPP_SF_
0x18001a866  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a86d  mov     rax, [rbx+18h]
0x18001a871  cmp     rax, qword ptr cs:GUID_NDIS_NOTIFY_ADAPTER_REMOVAL.Data1
0x18001a878  jnz     loc_18001AAA2
0x18001a87e  mov     rax, [rbx+20h]
0x18001a882  cmp     rax, qword ptr cs:GUID_NDIS_NOTIFY_ADAPTER_REMOVAL.Data4
0x18001a889  jnz     loc_18001AAA2
0x18001a88f  mov     esi, [rbx+38h]
0x18001a892  cmp     word ptr [rsi+rbx], 5Ch ; '\'
0x18001a897  jnz     loc_18001AA7F
0x18001a89d  xor     edx, edx; Val
0x18001a89f  lea     rcx, [rbp+57h+StringUuid]; void *
0x18001a8a3  lea     r8d, [rdx+4Ah]; Size
0x18001a8a7  call    memset_0
0x18001a8ac  lea     rax, [rbx+14h]
0x18001a8b0  add     rax, rsi
0x18001a8b3  jz      short loc_18001A8E0
0x18001a8b5  movups  xmm0, xmmword ptr [rax]
0x18001a8b8  movaps  xmmword ptr [rbp+57h+StringUuid], xmm0
0x18001a8bc  movups  xmm1, xmmword ptr [rax+10h]
0x18001a8c0  movaps  [rbp+57h+var_70], xmm1
0x18001a8c4  movups  xmm0, xmmword ptr [rax+20h]
0x18001a8c8  movaps  [rbp+57h+var_60], xmm0
0x18001a8cc  movups  xmm1, xmmword ptr [rax+30h]
0x18001a8d0  movaps  [rbp+57h+var_50], xmm1
0x18001a8d4  movsd   xmm0, qword ptr [rax+40h]
0x18001a8d9  movsd   [rbp+57h+var_40], xmm0
0x18001a8de  jmp     short loc_18001A8F1
0x18001a8e0  call    cs:__imp__o__errno
0x18001a8e6  mov     dword ptr [rax], 16h
0x18001a8ec  call    _invalid_parameter_noinfo
0x18001a8f1  xorps   xmm0, xmm0
0x18001a8f4  lea     rdx, [rbp+57h+Uuid]; Uuid
0x18001a8f8  lea     rcx, [rbp+57h+StringUuid]; StringUuid
0x18001a8fc  movups  xmmword ptr [rbp+57h+Uuid.Data1], xmm0
0x18001a900  call    cs:__imp_UuidFromStringW
0x18001a906  test    eax, eax
0x18001a908  jnz     loc_18001AA66
0x18001a90e  lea     rdx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18001a912  mov     qword ptr [rbp+57h+InterfaceLuid], 0
0x18001a91a  lea     rcx, [rbp+57h+Uuid]; InterfaceGuid
0x18001a91e  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18001a924  test    eax, eax
0x18001a926  jnz     loc_18001AA4D
0x18001a92c  lea     rdx, [rbp+57h+InterfaceIndex]; InterfaceIndex
0x18001a930  mov     [rbp+57h+InterfaceIndex], eax
0x18001a933  lea     rcx, [rbp+57h+InterfaceLuid]; InterfaceLuid
0x18001a937  call    cs:__imp_ConvertInterfaceLuidToIndex
0x18001a93d  test    eax, eax
0x18001a93f  jnz     loc_18001AA34
0x18001a945  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a94c  cmp     rcx, r14
0x18001a94f  jz      short loc_18001A96C
0x18001a951  test    byte ptr [rcx+1Ch], 8
0x18001a955  jz      short loc_18001A96C
0x18001a957  mov     r9d, [rbp+57h+InterfaceIndex]
0x18001a95b  mov     edx, 167h
0x18001a960  mov     rcx, [rcx+10h]
0x18001a964  mov     r8, r12
0x18001a967  call    WPP_SF_d
0x18001a96c  lea     rcx, [rdi+160h]; this
0x18001a973  mov     [rbp+57h+var_AC], 0
0x18001a97a  lea     r8, [rbp+57h+var_A8]; unsigned int *
0x18001a97e  mov     [rbp+57h+var_A8], 0
0x18001a985  lea     rdx, [rbp+57h+var_AC]; unsigned int *
0x18001a989  call    ?GetSharedInterfaceIndices@InterfaceMgr@@QEAAJPEAK0@Z; InterfaceMgr::GetSharedInterfaceIndices(ulong *,ulong *)
0x18001a98e  test    eax, eax
0x18001a990  js      short loc_18001AA04
0x18001a992  mov     eax, [rbp+57h+InterfaceIndex]
0x18001a995  cmp     eax, [rbp+57h+var_AC]
0x18001a998  jnz     short loc_18001A9EE
0x18001a99a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9a1  cmp     rcx, r14
0x18001a9a4  jz      short loc_18001A9BD
0x18001a9a6  test    byte ptr [rcx+1Ch], 8
0x18001a9aa  jz      short loc_18001A9BD
0x18001a9ac  mov     rcx, [rcx+10h]
0x18001a9b0  mov     edx, 12Ah
0x18001a9b5  mov     r8, r12
0x18001a9b8  call    WPP_SF_
0x18001a9bd  mov     edx, 3
0x18001a9c2  mov     rcx, rdi
0x18001a9c5  call    ?StopSharingAsync@TetheringService@@AEAAJW4StopReason@1@@Z; TetheringService::StopSharingAsync(TetheringService::StopReason)
0x18001a9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9d1  cmp     rcx, r14
0x18001a9d4  jz      loc_18001AABE
0x18001a9da  test    byte ptr [rcx+1Ch], 8
0x18001a9de  jz      loc_18001AAA2
0x18001a9e4  mov     edx, 12Bh
0x18001a9e9  jmp     loc_18001AA8F
0x18001a9ee  cmp     eax, [rbp+57h+var_A8]
0x18001a9f1  jnz     loc_18001AA9B
0x18001a9f7  mov     rcx, rdi; this
0x18001a9fa  call    ?NotifyPrivateConnectionDown@TetheringService@@QEAAXXZ; TetheringService::NotifyPrivateConnectionDown(void)
0x18001a9ff  jmp     loc_18001AA9B
0x18001aa04  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa0b  cmp     rcx, r14
0x18001aa0e  jz      loc_18001AABE
0x18001aa14  test    byte ptr [rcx+1Ch], 1
0x18001aa18  jz      loc_18001AAA2
0x18001aa1e  mov     edx, 168h
0x18001aa23  mov     rcx, [rcx+10h]
0x18001aa27  mov     r9d, eax
0x18001aa2a  mov     r8, r12
0x18001aa2d  call    WPP_SF_d
0x18001aa32  jmp     short loc_18001AA9B
0x18001aa34  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa3b  cmp     rcx, r14
0x18001aa3e  jz      short loc_18001AABE
0x18001aa40  test    byte ptr [rcx+1Ch], 1
0x18001aa44  jz      short loc_18001AAA2
0x18001aa46  mov     edx, 169h
0x18001aa4b  jmp     short loc_18001AA23
0x18001aa4d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa54  cmp     rcx, r14
0x18001aa57  jz      short loc_18001AABE
0x18001aa59  test    byte ptr [rcx+1Ch], 1
0x18001aa5d  jz      short loc_18001AAA2
0x18001aa5f  mov     edx, 16Ah
0x18001aa64  jmp     short loc_18001AA23
0x18001aa66  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa6d  cmp     rcx, r14
0x18001aa70  jz      short loc_18001AABE
0x18001aa72  test    byte ptr [rcx+1Ch], 1
0x18001aa76  jz      short loc_18001AAA2
0x18001aa78  mov     edx, 16Bh
0x18001aa7d  jmp     short loc_18001AA8F
0x18001aa7f  cmp     rcx, r14
0x18001aa82  jz      short loc_18001AABE
0x18001aa84  test    byte ptr [rcx+1Ch], 8
0x18001aa88  jz      short loc_18001AAA2
0x18001aa8a  mov     edx, 16Ch
0x18001aa8f  mov     rcx, [rcx+10h]
0x18001aa93  mov     r8, r12
0x18001aa96  call    WPP_SF_
0x18001aa9b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaa2  cmp     rcx, r14
0x18001aaa5  jz      short loc_18001AABE
0x18001aaa7  test    byte ptr [rcx+1Ch], 8
0x18001aaab  jz      short loc_18001AABE
0x18001aaad  mov     rcx, [rcx+10h]
0x18001aab1  mov     edx, 16Dh
0x18001aab6  mov     r8, r12
0x18001aab9  call    WPP_SF_
0x18001aabe  mov     rcx, [rbp+57h+var_30]
0x18001aac2  xor     rcx, rsp; StackCookie
0x18001aac5  call    __security_check_cookie
0x18001aaca  mov     rbx, [rsp+0D0h+arg_10]
0x18001aad2  add     rsp, 0B0h
0x18001aad9  pop     r14
0x18001aadb  pop     r12
0x18001aadd  pop     rdi
0x18001aade  pop     rsi
0x18001aadf  pop     rbp
0x18001aae0  retn
```
