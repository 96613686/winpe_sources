# MbaeUpdater::UpdateNetworkAccountState(_MBAE_NETWORK_INFO *,bool *)

- ea: `0x1800b9de8`
- end: `0x1800ba2e0`
- name: `?UpdateNetworkAccountState@MbaeUpdater@@QEAAJPEAU_MBAE_NETWORK_INFO@@PEA_N@Z`
- size: `1272`
- prototype: `__int64 __fastcall(MbaeUpdater *this, OLECHAR *, bool *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b7b58`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180016c50`
- `0x180019f24`
- `0x180074758`
- `0x1800b8384`
- `0x1800b8d10`
- `0x1800b9de8`
- `0x1800ba320`
- `0x1800ba45c`
- `0x1800baa3c`
- `0x1800bac0c`
- `0x1800bada8`
- `0x1800bb148`
- `0x1800bb4f8`
- `0x1800bb580`
- `0x1800bbd74`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x1800b9f2c`
- `ntdll!RtlPublishWnfStateData` at `0x1800ba23a`
- `ntdll!RtlPublishWnfStateData` at `0x1800b9f2c`
- `ntdll!RtlPublishWnfStateData` at `0x1800ba23a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba01c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba025`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba02e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba29c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba2a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba2b0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba01c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba025`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba02e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba29c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba2a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba2b0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800ba174`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800ba174`
- `MobileNetworking!BindNetworkInterfaceIdToAccountId` at `0x1800ba1f0`
- `MobileNetworking!BindNetworkInterfaceIdToAccountId` at `0x1800ba1f0`

## string_xrefs

- `0x1800b9e3a`: `MbaeUpdater::_CheckInitialized`
- `0x1800b9e25`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800b9ef3`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800b9f4c`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800ba001`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800ba07c`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800ba09e`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800ba0d6`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800ba273`: `MbaeUpdater::UpdateNetworkAccountState`
- `0x1800ba193`: `NetworkDeviceInstanceId (%ws), NetworkDeviceInterfacePath (%ws), NetworkDeviceContainerId (%S)`

## pseudocode

```c
__int64 __fastcall MbaeUpdater::UpdateNetworkAccountState(MbaeUpdater *this, OLECHAR *a2, bool *a3)
{
  MbaeUpdater *v4; // rbx
  int MbnInterfaceInfo; // r14d
  unsigned int v6; // r12d
  unsigned __int16 *v7; // r13
  unsigned __int16 *v8; // rbx
  unsigned __int16 *v9; // rsi
  unsigned __int16 *v10; // rdi
  int v11; // eax
  int v12; // edx
  int v13; // ecx
  unsigned int v14; // ebx
  int v15; // eax
  MbaeUpdater *v16; // rcx
  char *v17; // rbx
  __int64 v19; // rdx
  MbaeUpdater *v20; // r12
  MbaeUpdater *v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  unsigned int v25; // edx
  struct _GUID *v26; // [rsp+20h] [rbp-B9h]
  char v27; // [rsp+40h] [rbp-99h]
  unsigned int v28; // [rsp+44h] [rbp-95h] BYREF
  unsigned int v29; // [rsp+48h] [rbp-91h] BYREF
  unsigned __int16 *v30; // [rsp+50h] [rbp-89h] BYREF
  bool *v31; // [rsp+58h] [rbp-81h]
  BSTR v32; // [rsp+60h] [rbp-79h] BYREF
  BSTR bstrString; // [rsp+68h] [rbp-71h] BYREF
  BSTR v34; // [rsp+70h] [rbp-69h] BYREF
  unsigned __int16 *v35; // [rsp+78h] [rbp-61h] BYREF
  MbaeUpdater *v36; // [rsp+80h] [rbp-59h]
  GUID rguid; // [rsp+88h] [rbp-51h] BYREF
  OLECHAR sz[40]; // [rsp+A0h] [rbp-39h] BYREF

  v31 = a3;
  v4 = Block;
  v36 = Block;
  WwanLog::Enter("MbaeUpdater::UpdateNetworkAccountState");
  WwanLog::Verbose("MbaeUpdater::_CheckInitialized", 0, &String1);
  v27 = *(_BYTE *)v4;
  MbnInterfaceInfo = *(_BYTE *)v4 == 0 ? 0x8007139F : 0;
  v29 = 0;
  v6 = 0;
  v28 = 0;
  v30 = 0;
  v7 = 0;
  v35 = 0;
  v8 = 0;
  v34 = 0;
  v9 = 0;
  v32 = 0;
  v10 = 0;
  bstrString = 0;
  rguid = 0;
  *v31 = 0;
  if ( *((_BYTE *)a2 + 902) )
  {
    if ( (Microsoft_Windows_WWAN_SVC_EVENTSEnableBits & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(0, MbaeUpdaterSimRemovalDetected, a2 + 8);
    v11 = ReleaseBindingDeviceNodes(a2 + 8);
    v14 = v11;
    if ( v11 >= 0 )
    {
      *((_BYTE *)a2 + 902) = 0;
      *v31 = 1;
      v15 = RtlPublishWnfStateData(WNF_MBAE_ACCOUNT_PARSED, 0, 0, 0, 0);
      if ( v15 )
      {
        v14 = v15 | 0x10000000;
        WwanLog::Error(
          "MbaeUpdater::UpdateNetworkAccountState",
          0,
          L"Failed to publish WNF_MBAE_ACCOUNT_PARSED, hr = 0x%8x",
          v15 | 0x10000000u);
      }
    }
    else
    {
      if ( (byte_1801528C3 & 1) != 0 )
        McTemplateU0zqd_EventWriteTransfer(v13, v12, (_DWORD)a2 + 16, v11, v11);
      LODWORD(v26) = v14;
      WwanLog::Error(
        "MbaeUpdater::UpdateNetworkAccountState",
        0,
        L"Error handling SIM removal from device bound to network interface (%ws), hr = 0x%8x",
        a2 + 8,
        v26);
    }
    goto LABEL_15;
  }
  MbaeUpdater::_SetProviderIdAndName(0, (struct _MBAE_NETWORK_INFO *)a2);
  if ( v27 )
  {
    MbnInterfaceInfo = MbaeUpdater::_GetMbnInterfaceInfo(
                         v16,
                         (struct _MBAE_NETWORK_INFO *)a2,
                         (enum MbaeUpdater::ACCOUNT_PROVIDER_TYPE *)&v29,
                         (enum MbaeUpdater::ACCOUNT_IDENTIFIER *)&v28,
                         (const unsigned __int16 **)&v30,
                         (const unsigned __int16 **)&v35);
    v6 = v28;
    v7 = v35;
  }
  if ( MbnInterfaceInfo < 0 )
    goto LABEL_36;
  v17 = (char *)(a2 + 154);
  if ( !(unsigned int)MbaeUpdater::_CheckCriticalInterfaceProperties(
                        (unsigned __int64)(a2 + 176) & -(__int64)(*((_BYTE *)a2 + 350) != 0),
                        v29,
                        a2 + 8,
                        (unsigned __int64)(a2 + 154) & -(__int64)(*((_BYTE *)a2 + 306) != 0),
                        v30,
                        v7,
                        (unsigned __int64)(a2 + 176) & -(__int64)(*((_BYTE *)a2 + 350) != 0),
                        *((_QWORD *)a2 + 33)) )
  {
    WwanLog::Error(
      "MbaeUpdater::UpdateNetworkAccountState",
      0,
      L"_CheckCriticalInterfaceProperties failed, skip this network");
    v14 = 0;
LABEL_15:
    SysFreeString(0);
    SysFreeString(0);
    SysFreeString(0);
    return v14;
  }
  WwanLog::Verbose(
    "MbaeUpdater::UpdateNetworkAccountState",
    0,
    L"NetworkInterfaceId (%ws), EffectiveProviderId (%ws)             EffectiveSubscriberId (%ws), ProviderName (%ws)",
    a2 + 8,
    v30,
    v7,
    *((_QWORD *)a2 + 33));
  if ( *((_BYTE *)a2 + 306) )
    WwanLog::Verbose("MbaeUpdater::UpdateNetworkAccountState", 0, L"SimIccId (%ws)", a2 + 154);
  if ( *((_BYTE *)a2 + 350) )
    WwanLog::Verbose("MbaeUpdater::UpdateNetworkAccountState", 0, L"MobileEquipmentId (%ws)", a2 + 176);
  if ( v6 != 2 )
  {
    if ( v6 == 1 )
    {
      v17 = (char *)v7;
    }
    else
    {
      v17 = 0;
      if ( v6 == 3 )
        v17 = (char *)(a2 + 176);
    }
  }
  WwanLog::Verbose("MbaeUpdater::UpdateNetworkAccountState", 0, L" AccountIdentifier (%d), AccountIdKey (%ws)", v6, v17);
  WwanLog::Verbose("MbaeUpdater::UpdateNetworkAccountState", 0, L"AccountIdentifier (%d), AccountIdKey (%ws)", v6, v17);
  v19 = v6;
  v20 = v36;
  MbnInterfaceInfo = MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice(v36, v19, v17, &v34);
  v8 = v34;
  if ( MbnInterfaceInfo < 0 )
    goto LABEL_36;
  WwanLog::Verbose("MbaeUpdater::UpdateNetworkAccountState", 0, L"NetworkAccountId (%ws)", v34);
  MbnInterfaceInfo = MbaeDevNode::GetDeviceInfoForNetworkInterfaceId(
                       a2 + 8,
                       (struct ATL::CComBSTR *)&v32,
                       (struct ATL::CComBSTR *)&bstrString,
                       &rguid);
  if ( MbnInterfaceInfo < 0 )
  {
    v9 = v32;
    v10 = bstrString;
    goto LABEL_36;
  }
  memset_0(sz, 0, 0x4Eu);
  StringFromGUID2(&rguid, sz, 39);
  v10 = bstrString;
  v9 = v32;
  WwanLog::Verbose(
    "MbaeUpdater::UpdateNetworkAccountState",
    0,
    L"NetworkDeviceInstanceId (%ws), NetworkDeviceInterfacePath (%ws), NetworkDeviceContainerId (%S)",
    v32,
    bstrString,
    sz);
  MbnInterfaceInfo = MbaeUpdater::_CreateDevNodes(v21, (struct _MBAE_NETWORK_INFO *)a2, v8, v9, &rguid);
  if ( MbnInterfaceInfo < 0 )
    goto LABEL_36;
  MbnInterfaceInfo = MbaeUpdater::_UpdatePropertyBag(v20, (struct _MBAE_NETWORK_INFO *)a2, v8, v10);
  if ( MbnInterfaceInfo < 0 )
    goto LABEL_36;
  v22 = BindNetworkInterfaceIdToAccountId(v8, a2 + 8, a2 + 154);
  MbnInterfaceInfo = v22;
  if ( v22 < 0 )
  {
    if ( (byte_1801528C3 & 1) != 0 )
      McTemplateU0qd_EventWriteTransfer(v23, MbaeUpdaterErrorUpdatingMbaeData, (unsigned int)v22, (unsigned int)v22);
    goto LABEL_36;
  }
  *v31 = 1;
  v24 = RtlPublishWnfStateData(WNF_MBAE_ACCOUNT_PARSED, 0, 0, 0, 0);
  if ( v24 )
  {
    MbnInterfaceInfo = v24 | 0x10000000;
    WwanLog::Error(
      "MbaeUpdater::UpdateNetworkAccountState",
      0,
      L"Failed to publish WNF_MBAE_ACCOUNT_PARSED, hr = 0x%8x",
      v24 | 0x10000000u);
    if ( MbnInterfaceInfo < 0 )
    {
LABEL_36:
      v25 = (unsigned __int16)MbnInterfaceInfo;
      if ( (MbnInterfaceInfo & 0x1FFF0000) != 0x70000 )
        v25 = MbnInterfaceInfo;
      goto LABEL_38;
    }
  }
  v25 = 0;
LABEL_38:
  WwanLog::ExitWithStatus("MbaeUpdater::UpdateNetworkAccountState", v25);
  SysFreeString(v10);
  SysFreeString(v9);
  SysFreeString(v8);
  return (unsigned int)MbnInterfaceInfo;
}

```

## disassembly

```asm
0x1800b9de8  mov     [rsp-8+arg_0], rbx
0x1800b9ded  push    rbp
0x1800b9dee  push    rsi
0x1800b9def  push    rdi
0x1800b9df0  push    r12
0x1800b9df2  push    r13
0x1800b9df4  push    r14
0x1800b9df6  push    r15
0x1800b9df8  lea     rbp, [rsp-27h]
0x1800b9dfd  sub     rsp, 100h
0x1800b9e04  mov     rax, cs:__security_cookie
0x1800b9e0b  xor     rax, rsp
0x1800b9e0e  mov     [rbp+57h+var_40], rax
0x1800b9e12  mov     [rsp+130h+var_D8], r8
0x1800b9e17  mov     r15, rdx
0x1800b9e1a  mov     rbx, cs:Block
0x1800b9e21  mov     [rbp+57h+var_B0], rbx
0x1800b9e25  lea     rcx, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800b9e2c  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800b9e31  lea     r8, String1; unsigned __int16 *
0x1800b9e38  xor     edx, edx; struct _GUID *
0x1800b9e3a  lea     rcx, aMbaeupdaterChe_0; "MbaeUpdater::_CheckInitialized"
0x1800b9e41  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800b9e46  mov     al, [rbx]
0x1800b9e48  mov     [rsp+130h+var_F0], al
0x1800b9e4c  neg     al
0x1800b9e4e  sbb     r14d, r14d
0x1800b9e51  not     r14d
0x1800b9e54  and     r14d, 8007139Fh
0x1800b9e5b  xor     ecx, ecx; this
0x1800b9e5d  mov     [rsp+130h+var_E8], ecx
0x1800b9e61  mov     r12d, ecx
0x1800b9e64  mov     [rsp+130h+var_EC], ecx
0x1800b9e68  mov     [rsp+130h+var_E0], rcx
0x1800b9e6d  mov     r13d, ecx
0x1800b9e70  mov     [rbp+57h+var_B8], rcx
0x1800b9e74  mov     ebx, ecx
0x1800b9e76  mov     [rbp+57h+var_C0], rcx
0x1800b9e7a  mov     esi, ecx
0x1800b9e7c  mov     [rbp+57h+var_D0], rcx
0x1800b9e80  mov     edi, ecx
0x1800b9e82  mov     [rbp+57h+bstrString], rcx
0x1800b9e86  xorps   xmm0, xmm0
0x1800b9e89  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800b9e8d  mov     rax, [rsp+130h+var_D8]
0x1800b9e92  mov     [rax], cl
0x1800b9e94  cmp     [r15+386h], cl
0x1800b9e9b  jz      loc_1800B9F5D
0x1800b9ea1  lea     rdi, [r15+10h]
0x1800b9ea5  test    cs:Microsoft_Windows_WWAN_SVC_EVENTSEnableBits, 4
0x1800b9eac  jz      short loc_1800B9EBD
0x1800b9eae  mov     r8, rdi
0x1800b9eb1  lea     rdx, MbaeUpdaterSimRemovalDetected
0x1800b9eb8  call    McTemplateU0z_EventWriteTransfer
0x1800b9ebd  mov     rcx, rdi; lpsz
0x1800b9ec0  call    ?ReleaseBindingDeviceNodes@@YAJPEBG@Z; ReleaseBindingDeviceNodes(ushort const *)
0x1800b9ec5  mov     ebx, eax
0x1800b9ec7  test    eax, eax
0x1800b9ec9  jns     short loc_1800B9F04
0x1800b9ecb  test    cs:byte_1801528C3, 1
0x1800b9ed2  jz      short loc_1800B9EE3
0x1800b9ed4  mov     dword ptr [rsp+130h+var_110], eax
0x1800b9ed8  mov     r9d, eax
0x1800b9edb  mov     r8, rdi
0x1800b9ede  call    McTemplateU0zqd_EventWriteTransfer
0x1800b9ee3  mov     dword ptr [rsp+130h+var_110], ebx
0x1800b9ee7  mov     r9, rdi
0x1800b9eea  lea     r8, aErrorHandlingS; "Error handling SIM removal from device "...
0x1800b9ef1  xor     edx, edx; struct _GUID *
0x1800b9ef3  lea     rcx, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800b9efa  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b9eff  jmp     loc_1800BA01A
0x1800b9f04  mov     byte ptr [r15+386h], 0
0x1800b9f0c  mov     rax, [rsp+130h+var_D8]
0x1800b9f11  mov     byte ptr [rax], 1
0x1800b9f14  mov     [rsp+130h+var_110], 0
0x1800b9f1d  xor     r9d, r9d
0x1800b9f20  xor     r8d, r8d
0x1800b9f23  xor     edx, edx
0x1800b9f25  mov     rcx, cs:WNF_MBAE_ACCOUNT_PARSED
0x1800b9f2c  call    cs:__imp_RtlPublishWnfStateData
0x1800b9f32  test    eax, eax
0x1800b9f34  jz      loc_1800BA01A
0x1800b9f3a  mov     ebx, eax
0x1800b9f3c  bts     ebx, 1Ch
0x1800b9f40  mov     r9d, ebx
0x1800b9f43  lea     r8, aFailedToPublis_4; "Failed to publish WNF_MBAE_ACCOUNT_PARS"...
0x1800b9f4a  xor     edx, edx; struct _GUID *
0x1800b9f4c  lea     rcx, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800b9f53  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b9f58  jmp     loc_1800BA01A
0x1800b9f5d  mov     rdx, r15; struct _MBAE_NETWORK_INFO *
0x1800b9f60  call    ?_SetProviderIdAndName@MbaeUpdater@@AEAAXPEAU_MBAE_NETWORK_INFO@@@Z; MbaeUpdater::_SetProviderIdAndName(_MBAE_NETWORK_INFO *)
0x1800b9f65  cmp     [rsp+130h+var_F0], 0
0x1800b9f6a  jz      short loc_1800B9F9D
0x1800b9f6c  lea     rax, [rbp+57h+var_B8]
0x1800b9f70  mov     [rsp+130h+var_108], rax; unsigned __int16 **
0x1800b9f75  lea     rax, [rsp+130h+var_E0]
0x1800b9f7a  mov     [rsp+130h+var_110], rax; unsigned __int16 **
0x1800b9f7f  lea     r9, [rsp+130h+var_EC]; enum MbaeUpdater::ACCOUNT_IDENTIFIER *
0x1800b9f84  lea     r8, [rsp+130h+var_E8]; enum MbaeUpdater::ACCOUNT_PROVIDER_TYPE *
0x1800b9f89  mov     rdx, r15; struct _MBAE_NETWORK_INFO *
0x1800b9f8c  call    ?_GetMbnInterfaceInfo@MbaeUpdater@@AEAAJPEAU_MBAE_NETWORK_INFO@@PEAW4ACCOUNT_PROVIDER_TYPE@1@PEAW4ACCOUNT_IDENTIFIER@1@PEAPEBG3@Z; MbaeUpdater::_GetMbnInterfaceInfo(_MBAE_NETWORK_INFO *,MbaeUpdater::ACCOUNT_PROVIDER_TYPE *,MbaeUpdater::ACCOUNT_IDENTIFIER *,ushort const * *,ushort const * *)
0x1800b9f91  mov     r14d, eax
0x1800b9f94  mov     r12d, [rsp+130h+var_EC]
0x1800b9f99  mov     r13, [rbp+57h+var_B8]
0x1800b9f9d  test    r14d, r14d
0x1800b9fa0  js      loc_1800BA273
0x1800b9fa6  lea     r14, [r15+160h]
0x1800b9fad  lea     rbx, [r15+134h]
0x1800b9fb4  lea     r8, [r15+10h]
0x1800b9fb8  mov     al, [r15+15Eh]
0x1800b9fbf  neg     al
0x1800b9fc1  sbb     rcx, rcx
0x1800b9fc4  and     rcx, r14
0x1800b9fc7  mov     al, [r15+132h]
0x1800b9fce  neg     al
0x1800b9fd0  sbb     r9, r9
0x1800b9fd3  and     r9, rbx
0x1800b9fd6  mov     rax, [r15+108h]
0x1800b9fdd  mov     [rsp+130h+var_F8], rax
0x1800b9fe2  mov     [rsp+130h+var_100], rcx
0x1800b9fe7  mov     [rsp+130h+var_108], r13
0x1800b9fec  mov     rax, [rsp+130h+var_E0]
0x1800b9ff1  mov     [rsp+130h+var_110], rax
0x1800b9ff6  mov     edx, [rsp+130h+var_E8]
0x1800b9ffa  call    ?_CheckCriticalInterfaceProperties@MbaeUpdater@@AEAAHW4ACCOUNT_PROVIDER_TYPE@1@PEBG11111@Z; MbaeUpdater::_CheckCriticalInterfaceProperties(MbaeUpdater::ACCOUNT_PROVIDER_TYPE,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800b9fff  xor     edx, edx; struct _GUID *
0x1800ba001  lea     rcx, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800ba008  test    eax, eax
0x1800ba00a  jnz     short loc_1800BA03B
0x1800ba00c  lea     r8, aCheckcriticali; "_CheckCriticalInterfaceProperties faile"...
0x1800ba013  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ba018  xor     ebx, ebx
0x1800ba01a  xor     ecx, ecx; bstrString
0x1800ba01c  call    cs:__imp_SysFreeString
0x1800ba022  nop
0x1800ba023  xor     ecx, ecx; bstrString
0x1800ba025  call    cs:__imp_SysFreeString
0x1800ba02b  nop
0x1800ba02c  xor     ecx, ecx; bstrString
0x1800ba02e  call    cs:__imp_SysFreeString
0x1800ba034  mov     eax, ebx
0x1800ba036  jmp     loc_1800BA2B9
0x1800ba03b  mov     rax, [r15+108h]
0x1800ba042  mov     [rsp+130h+var_100], rax
0x1800ba047  mov     [rsp+130h+var_108], r13
0x1800ba04c  mov     rax, [rsp+130h+var_E0]
0x1800ba051  mov     [rsp+130h+var_110], rax
0x1800ba056  lea     r9, [r15+10h]
0x1800ba05a  lea     r8, aNetworkinterfa; "NetworkInterfaceId (%ws), EffectiveProv"...
0x1800ba061  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba066  cmp     byte ptr [r15+132h], 0
0x1800ba06e  jz      short loc_1800BA088
0x1800ba070  mov     r9, rbx
0x1800ba073  lea     r8, aSimiccidWs; "SimIccId (%ws)"
0x1800ba07a  xor     edx, edx; struct _GUID *
0x1800ba07c  lea     rcx, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800ba083  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba088  cmp     byte ptr [r15+15Eh], 0
0x1800ba090  jz      short loc_1800BA0AA
0x1800ba092  mov     r9, r14
0x1800ba095  lea     r8, aMobileequipmen; "MobileEquipmentId (%ws)"
0x1800ba09c  xor     edx, edx; struct _GUID *
0x1800ba09e  lea     rcx, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800ba0a5  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba0aa  cmp     r12d, 2
0x1800ba0ae  jz      short loc_1800BA0C5
0x1800ba0b0  cmp     r12d, 1
0x1800ba0b4  jnz     short loc_1800BA0BB
0x1800ba0b6  mov     rbx, r13
0x1800ba0b9  jmp     short loc_1800BA0C5
0x1800ba0bb  xor     ebx, ebx
0x1800ba0bd  cmp     r12d, 3
0x1800ba0c1  cmovz   rbx, r14
0x1800ba0c5  mov     [rsp+130h+var_110], rbx
0x1800ba0ca  mov     r9d, r12d
0x1800ba0cd  lea     r8, aAccountidentif; " AccountIdentifier (%d), AccountIdKey ("...
0x1800ba0d4  xor     edx, edx; struct _GUID *
0x1800ba0d6  lea     r13, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800ba0dd  mov     rcx, r13; char *
0x1800ba0e0  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba0e5  mov     [rsp+130h+var_110], rbx
0x1800ba0ea  mov     r9d, r12d
0x1800ba0ed  lea     r8, aAccountidentif_0; "AccountIdentifier (%d), AccountIdKey (%"...
0x1800ba0f4  xor     edx, edx; struct _GUID *
0x1800ba0f6  mov     rcx, r13; char *
0x1800ba0f9  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba0fe  lea     r9, [rbp+57h+var_C0]
0x1800ba102  mov     r8, rbx
0x1800ba105  mov     edx, r12d
0x1800ba108  mov     r12, [rbp+57h+var_B0]
0x1800ba10c  mov     rcx, r12
0x1800ba10f  call    ?_GetNewOrExistingAccountIdForNetworkDevice@MbaeUpdater@@AEAAJW4ACCOUNT_IDENTIFIER@1@PEBGPEAVCComBSTR@ATL@@@Z; MbaeUpdater::_GetNewOrExistingAccountIdForNetworkDevice(MbaeUpdater::ACCOUNT_IDENTIFIER,ushort const *,ATL::CComBSTR *)
0x1800ba114  mov     r14d, eax
0x1800ba117  mov     rbx, [rbp+57h+var_C0]
0x1800ba11b  test    eax, eax
0x1800ba11d  js      loc_1800BA27A
0x1800ba123  mov     r9, rbx
0x1800ba126  lea     r8, aNetworkaccount_0; "NetworkAccountId (%ws)"
0x1800ba12d  xor     edx, edx; struct _GUID *
0x1800ba12f  mov     rcx, r13; char *
0x1800ba132  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba137  lea     rcx, [r15+10h]; unsigned __int16 *
0x1800ba13b  lea     r9, [rbp+57h+rguid]; struct _GUID *
0x1800ba13f  lea     r8, [rbp+57h+bstrString]; struct ATL::CComBSTR *
0x1800ba143  lea     rdx, [rbp+57h+var_D0]; struct ATL::CComBSTR *
0x1800ba147  call    ?GetDeviceInfoForNetworkInterfaceId@MbaeDevNode@@SAJPEBGPEAVCComBSTR@ATL@@1PEAU_GUID@@@Z; MbaeDevNode::GetDeviceInfoForNetworkInterfaceId(ushort const *,ATL::CComBSTR *,ATL::CComBSTR *,_GUID *)
0x1800ba14c  mov     r14d, eax
0x1800ba14f  test    eax, eax
0x1800ba151  js      loc_1800BA269
0x1800ba157  xor     edx, edx; Val
0x1800ba159  lea     r8d, [rdx+4Eh]; Size
0x1800ba15d  lea     rcx, [rbp+57h+sz]; void *
0x1800ba161  call    memset_0
0x1800ba166  mov     r8d, 27h ; '''; cchMax
0x1800ba16c  lea     rdx, [rbp+57h+sz]; lpsz
0x1800ba170  lea     rcx, [rbp+57h+rguid]; rguid
0x1800ba174  call    cs:__imp_StringFromGUID2
0x1800ba17a  lea     rax, [rbp+57h+sz]
0x1800ba17e  mov     [rsp+130h+var_108], rax
0x1800ba183  mov     rdi, [rbp+57h+bstrString]
0x1800ba187  mov     [rsp+130h+var_110], rdi
0x1800ba18c  mov     rsi, [rbp+57h+var_D0]
0x1800ba190  mov     r9, rsi
0x1800ba193  lea     r8, aNetworkdevicei; "NetworkDeviceInstanceId (%ws), NetworkD"...
0x1800ba19a  xor     edx, edx; struct _GUID *
0x1800ba19c  mov     rcx, r13; char *
0x1800ba19f  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800ba1a4  lea     rax, [rbp+57h+rguid]
0x1800ba1a8  mov     [rsp+130h+var_110], rax; struct _GUID *
0x1800ba1ad  mov     r9, rsi; unsigned __int16 *
0x1800ba1b0  mov     r8, rbx; unsigned __int16 *
0x1800ba1b3  mov     rdx, r15; struct _MBAE_NETWORK_INFO *
0x1800ba1b6  call    ?_CreateDevNodes@MbaeUpdater@@AEAAJPEAU_MBAE_NETWORK_INFO@@PEBG1AEBU_GUID@@@Z; MbaeUpdater::_CreateDevNodes(_MBAE_NETWORK_INFO *,ushort const *,ushort const *,_GUID const &)
0x1800ba1bb  mov     r14d, eax
0x1800ba1be  test    eax, eax
0x1800ba1c0  js      loc_1800BA27A
0x1800ba1c6  mov     r9, rdi; unsigned __int16 *
0x1800ba1c9  mov     r8, rbx; unsigned __int16 *
0x1800ba1cc  mov     rdx, r15; struct _MBAE_NETWORK_INFO *
0x1800ba1cf  mov     rcx, r12; this
0x1800ba1d2  call    ?_UpdatePropertyBag@MbaeUpdater@@AEAAJPEAU_MBAE_NETWORK_INFO@@PEBG1@Z; MbaeUpdater::_UpdatePropertyBag(_MBAE_NETWORK_INFO *,ushort const *,ushort const *)
0x1800ba1d7  mov     r14d, eax
0x1800ba1da  test    eax, eax
0x1800ba1dc  js      loc_1800BA27A
0x1800ba1e2  lea     r8, [r15+134h]
0x1800ba1e9  lea     rdx, [r15+10h]
0x1800ba1ed  mov     rcx, rbx
0x1800ba1f0  call    cs:__imp_BindNetworkInterfaceIdToAccountId
0x1800ba1f6  mov     r14d, eax
0x1800ba1f9  test    eax, eax
0x1800ba1fb  jns     short loc_1800BA21A
0x1800ba1fd  test    cs:byte_1801528C3, 1
0x1800ba204  jz      short loc_1800BA27A
0x1800ba206  mov     r9d, eax
0x1800ba209  mov     r8d, eax
0x1800ba20c  lea     rdx, MbaeUpdaterErrorUpdatingMbaeData
0x1800ba213  call    McTemplateU0qd_EventWriteTransfer
0x1800ba218  jmp     short loc_1800BA27A
0x1800ba21a  mov     rax, [rsp+130h+var_D8]
0x1800ba21f  mov     byte ptr [rax], 1
0x1800ba222  mov     [rsp+130h+var_110], 0
0x1800ba22b  xor     r9d, r9d
0x1800ba22e  xor     r8d, r8d
0x1800ba231  xor     edx, edx
0x1800ba233  mov     rcx, cs:WNF_MBAE_ACCOUNT_PARSED
0x1800ba23a  call    cs:__imp_RtlPublishWnfStateData
0x1800ba240  test    eax, eax
0x1800ba242  jz      short loc_1800BA265
0x1800ba244  mov     r14d, eax
0x1800ba247  bts     r14d, 1Ch
0x1800ba24c  mov     r9d, r14d
0x1800ba24f  lea     r8, aFailedToPublis_4; "Failed to publish WNF_MBAE_ACCOUNT_PARS"...
0x1800ba256  xor     edx, edx; struct _GUID *
0x1800ba258  mov     rcx, r13; char *
0x1800ba25b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800ba260  test    r14d, r14d
0x1800ba263  js      short loc_1800BA27A
0x1800ba265  xor     edx, edx
0x1800ba267  jmp     short loc_1800BA290
0x1800ba269  mov     rsi, [rbp+57h+var_D0]
0x1800ba26d  mov     rdi, [rbp+57h+bstrString]
0x1800ba271  jmp     short loc_1800BA27A
0x1800ba273  lea     r13, aMbaeupdaterUpd_1; "MbaeUpdater::UpdateNetworkAccountState"
0x1800ba27a  mov     eax, r14d
0x1800ba27d  and     eax, 1FFF0000h
0x1800ba282  cmp     eax, 70000h
0x1800ba287  movzx   edx, r14w
0x1800ba28b  jz      short loc_1800BA290
0x1800ba28d  mov     edx, r14d; unsigned int
0x1800ba290  mov     rcx, r13; char *
0x1800ba293  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800ba298  nop
0x1800ba299  mov     rcx, rdi; bstrString
0x1800ba29c  call    cs:__imp_SysFreeString
0x1800ba2a2  nop
0x1800ba2a3  mov     rcx, rsi; bstrString
0x1800ba2a6  call    cs:__imp_SysFreeString
0x1800ba2ac  nop
  ... truncated ...
```
