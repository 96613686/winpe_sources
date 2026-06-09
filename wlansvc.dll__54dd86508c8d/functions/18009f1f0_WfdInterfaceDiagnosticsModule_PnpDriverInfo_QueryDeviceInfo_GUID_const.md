# WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDeviceInfo(_GUID const &)

- ea: `0x18009f1f0`
- end: `0x18009f620`
- name: `?QueryDeviceInfo@PnpDriverInfo@WfdInterfaceDiagnosticsModule@@AEAAXAEBU_GUID@@@Z`
- size: `1072`
- prototype: `void __fastcall(WfdInterfaceDiagnosticsModule::PnpDriverInfo *__hidden this, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801f0290`

## callees

- `0x18000aa0c`
- `0x180011b98`
- `0x18009f1f0`
- `0x1800a5a98`
- `0x1800b3da0`
- `0x1800b3ea0`
- `0x1800b3ff0`
- `0x1800b40e8`
- `0x1800bd620`
- `0x180106340`
- `0x180107330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f285`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f2f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009f5b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009f435`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009f435`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f3eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f576`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f3eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009f576`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18009f381`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x18009f381`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18009f585`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x18009f585`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18009f355`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x18009f355`
- `DEVOBJ!DevObjGetClassDevs` at `0x18009f2e8`
- `DEVOBJ!DevObjGetClassDevs` at `0x18009f2e8`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18009f271`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x18009f271`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18009f4c9`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18009f4c9`

## string_xrefs

- `0x18009f297`: `DevObjCreateDeviceInfoList failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDeviceInfo(
        WfdInterfaceDiagnosticsModule::PnpDriverInfo *this,
        const struct _GUID *a2)
{
  void *DeviceInfoList; // rax
  void *v5; // rbx
  signed int LastError; // eax
  signed int v7; // eax
  HKEY v8; // rdi
  unsigned int i; // r15d
  __int64 v10; // rax
  HKEY v11; // rsi
  DWORD v12; // eax
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  HKEY v16; // rcx
  __int64 v17; // rax
  signed int v18; // eax
  DWORD Type; // [rsp+30h] [rbp-89h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-85h] BYREF
  void *v21; // [rsp+38h] [rbp-81h] BYREF
  __int64 v22; // [rsp+40h] [rbp-79h]
  void *v23; // [rsp+48h] [rbp-71h]
  GUID iid; // [rsp+50h] [rbp-69h] BYREF
  _OWORD v25[3]; // [rsp+60h] [rbp-59h] BYREF
  OLECHAR Data[38]; // [rsp+90h] [rbp-29h] BYREF
  __int16 v27; // [rsp+DCh] [rbp+23h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
  {
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_2222ea3dedc832ba560939e1a0f845a2_Traceguids, a2);
  }
  DeviceInfoList = (void *)DevObjCreateDeviceInfoList(&GUID_DEVCLASS_NET, 0, 0, 0, 0);
  v5 = DeviceInfoList;
  v21 = DeviceInfoList;
  if ( DeviceInfoList == (void *)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WFDSvc::CWFDSvcException::Throw(
      LastError,
      "WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDeviceInfo",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacediagnostics\\src\\wfdinterfacediagnosticsdriverinfo.cpp",
      0x75u,
      L"DevObjCreateDeviceInfoList failed");
  }
  v23 = DeviceInfoList;
  if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVCLASS_NET, 0, 2, 0, 0) )
  {
    v7 = GetLastError();
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    WFDSvc::CWFDSvcException::Throw(
      v7,
      "WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDeviceInfo",
      "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacediagnostics\\src\\wfdinterfacediagnosticsdriverinfo.cpp",
      0x7Eu,
      L"DevObjGetClassDevs failed");
  }
  v8 = 0;
  v22 = 0;
  memset(v25, 0, sizeof(v25));
  LODWORD(v25[0]) = 48;
  for ( i = 0; ; ++i )
  {
    if ( !(unsigned int)DevObjEnumDeviceInfo(v5, i, v25) )
    {
      v18 = GetLastError();
      if ( v18 == 259 )
        WFDSvc::CWFDSvcException::Throw(
          -2147024637,
          "WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDeviceInfo",
          "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacediagnostics\\src\\wfdinterfacediagnosticsdriverinfo.cpp",
          0xBDu,
          L"Device not found");
      if ( v18 > 0 )
        v18 = (unsigned __int16)v18 | 0x80070000;
      WFDSvc::CWFDSvcException::Throw(
        v18,
        "WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDeviceInfo",
        "onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\wfdinterfacediagnostics\\src\\wfdinterfacediagnosticsdriverinfo.cpp",
        0xC1u,
        L"DevObjEnumDeviceInfo failed");
    }
    v10 = DevObjOpenDevRegKey(v5, v25, 1);
    v11 = (HKEY)v10;
    if ( v10 == -1 )
    {
      v12 = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v14 = 11;
LABEL_20:
        v15 = v12;
LABEL_21:
        WPP_SF_d(v13[12], v14, WPP_2222ea3dedc832ba560939e1a0f845a2_Traceguids, v15);
        continue;
      }
      continue;
    }
    v16 = v8;
    v8 = (HKEY)v10;
    v22 = v10;
    if ( v16 )
      RegCloseKey(v16);
    memset_0(Data, 0, 0x4Eu);
    Type = 0;
    cbData = 78;
    v12 = RegQueryValueExW(v11, L"NetCfgInstanceId", 0, &Type, (LPBYTE)Data, &cbData);
    if ( v12 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v14 = 12;
        goto LABEL_20;
      }
      continue;
    }
    v15 = Type;
    if ( Type != 1 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        v14 = 13;
        goto LABEL_21;
      }
      continue;
    }
    v27 = 0;
    iid = 0;
    if ( IIDFromString(Data, &iid) < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 2u
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_DS(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          14,
          (unsigned int)WPP_2222ea3dedc832ba560939e1a0f845a2_Traceguids,
          0,
          (__int64)Data);
      }
      continue;
    }
    v17 = *(_QWORD *)&iid.Data1 - *(_QWORD *)&a2->Data1;
    if ( *(_QWORD *)&iid.Data1 == *(_QWORD *)&a2->Data1 )
      v17 = *(_QWORD *)iid.Data4 - *(_QWORD *)a2->Data4;
    if ( !v17 )
      break;
  }
  WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryHardwareId(this, &v21, (struct _DO_DEVINFO_DATA *)v25);
  WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryFriendlyName(this, &v21, (struct _DO_DEVINFO_DATA *)v25);
  WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDriverVersion(this, v11);
  WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDriverDate(this, v11);
  if ( v11 )
    RegCloseKey(v11);
  if ( v5 )
    DevObjDestroyDeviceInfoList(v5);
}

```

## disassembly

```asm
0x18009f1f0  mov     [rsp-8+arg_10], rbx
0x18009f1f5  mov     [rsp-8+arg_18], rsi
0x18009f1fa  push    rbp
0x18009f1fb  push    rdi
0x18009f1fc  push    r12
0x18009f1fe  push    r14
0x18009f200  push    r15
0x18009f202  lea     rbp, [rsp-37h]
0x18009f207  sub     rsp, 0F0h
0x18009f20e  mov     rax, cs:__security_cookie
0x18009f215  xor     rax, rsp
0x18009f218  mov     [rbp+57h+var_30], rax
0x18009f21c  mov     r12, rdx
0x18009f21f  mov     r14, rcx
0x18009f222  lea     rax, WPP_GLOBAL_Control
0x18009f229  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f230  cmp     rcx, rax
0x18009f233  jz      short loc_18009F259
0x18009f235  cmp     byte ptr [rcx+69h], 4
0x18009f239  jb      short loc_18009F259
0x18009f23b  test    byte ptr [rcx+6Ch], 1
0x18009f23f  jz      short loc_18009F259
0x18009f241  mov     edx, 0Ah
0x18009f246  mov     r9, r12
0x18009f249  lea     r8, WPP_2222ea3dedc832ba560939e1a0f845a2_Traceguids
0x18009f250  mov     rcx, [rcx+60h]
0x18009f254  call    WPP_SF__guid_
0x18009f259  mov     [rsp+110h+lpData], 0
0x18009f262  xor     r9d, r9d
0x18009f265  xor     r8d, r8d
0x18009f268  xor     edx, edx
0x18009f26a  lea     rcx, GUID_DEVCLASS_NET
0x18009f271  call    cs:__imp_DevObjCreateDeviceInfoList
0x18009f277  mov     rbx, rax
0x18009f27a  mov     [rsp+110h+var_D8], rax
0x18009f27f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009f283  jnz     short loc_18009F2BF
0x18009f285  call    cs:__imp_GetLastError
0x18009f28b  test    eax, eax
0x18009f28d  jle     short loc_18009F297
0x18009f28f  movzx   eax, ax
0x18009f292  or      eax, 80070000h
0x18009f297  lea     rcx, aDevobjcreatede_0; "DevObjCreateDeviceInfoList failed"
0x18009f29e  mov     [rsp+110h+lpData], rcx; unsigned __int16 *
0x18009f2a3  mov     r9d, 75h ; 'u'; unsigned int
0x18009f2a9  lea     r8, aOnecoreuapNetW_24; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18009f2b0  lea     rdx, aWfdinterfacedi_1; "WfdInterfaceDiagnosticsModule::PnpDrive"...
0x18009f2b7  mov     ecx, eax; int
0x18009f2b9  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18009f2bf  mov     [rbp+57h+var_C8], rbx
0x18009f2c3  mov     [rsp+110h+lpcbData], 0
0x18009f2cc  mov     [rsp+110h+lpData], 0
0x18009f2d5  mov     r9d, 2
0x18009f2db  xor     r8d, r8d
0x18009f2de  lea     rdx, GUID_DEVCLASS_NET
0x18009f2e5  mov     rcx, rbx
0x18009f2e8  call    cs:__imp_DevObjGetClassDevs
0x18009f2ee  test    eax, eax
0x18009f2f0  jnz     short loc_18009F32C
0x18009f2f2  call    cs:__imp_GetLastError
0x18009f2f8  test    eax, eax
0x18009f2fa  jle     short loc_18009F304
0x18009f2fc  movzx   eax, ax
0x18009f2ff  or      eax, 80070000h
0x18009f304  lea     rcx, aDevobjgetclass_0; "DevObjGetClassDevs failed"
0x18009f30b  mov     [rsp+110h+lpData], rcx; unsigned __int16 *
0x18009f310  mov     r9d, 7Eh ; '~'; unsigned int
0x18009f316  lea     r8, aOnecoreuapNetW_24; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18009f31d  lea     rdx, aWfdinterfacedi_1; "WfdInterfaceDiagnosticsModule::PnpDrive"...
0x18009f324  mov     ecx, eax; int
0x18009f326  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18009f32c  xor     edi, edi
0x18009f32e  mov     [rbp+57h+var_D0], rdi
0x18009f332  xorps   xmm0, xmm0
0x18009f335  movups  [rbp+57h+var_B0], xmm0
0x18009f339  movups  [rbp+57h+var_A0], xmm0
0x18009f33d  movups  [rbp+57h+var_90], xmm0
0x18009f341  mov     dword ptr [rbp+57h+var_B0], 30h ; '0'
0x18009f348  xor     r15d, r15d
0x18009f34b  lea     r8, [rbp+57h+var_B0]
0x18009f34f  mov     edx, r15d
0x18009f352  mov     rcx, rbx
0x18009f355  call    cs:__imp_DevObjEnumDeviceInfo
0x18009f35b  test    eax, eax
0x18009f35d  jz      loc_18009F5B3
0x18009f363  mov     dword ptr [rsp+110h+lpcbData], 20019h
0x18009f36b  mov     dword ptr [rsp+110h+lpData], 2
0x18009f373  xor     r9d, r9d
0x18009f376  lea     r8d, [r9+1]
0x18009f37a  lea     rdx, [rbp+57h+var_B0]
0x18009f37e  mov     rcx, rbx
0x18009f381  call    cs:__imp_DevObjOpenDevRegKey
0x18009f387  mov     rsi, rax
0x18009f38a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18009f38e  jnz     short loc_18009F3DC
0x18009f390  call    cs:__imp_GetLastError
0x18009f396  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f39d  lea     rdx, WPP_GLOBAL_Control
0x18009f3a4  cmp     rcx, rdx
0x18009f3a7  jz      loc_18009F52D
0x18009f3ad  cmp     byte ptr [rcx+69h], 2
0x18009f3b1  jb      loc_18009F52D
0x18009f3b7  test    byte ptr [rcx+6Ch], 1
0x18009f3bb  jz      loc_18009F52D
0x18009f3c1  lea     edx, [rsi+0Ch]
0x18009f3c4  mov     r9d, eax
0x18009f3c7  lea     r8, WPP_2222ea3dedc832ba560939e1a0f845a2_Traceguids
0x18009f3ce  mov     rcx, [rcx+60h]
0x18009f3d2  call    WPP_SF_d
0x18009f3d7  jmp     loc_18009F52D
0x18009f3dc  mov     rcx, rdi; hKey
0x18009f3df  mov     rdi, rsi
0x18009f3e2  mov     [rbp+57h+var_D0], rsi
0x18009f3e6  test    rcx, rcx
0x18009f3e9  jz      short loc_18009F3F1
0x18009f3eb  call    cs:__imp_RegCloseKey
0x18009f3f1  xor     edx, edx; Val
0x18009f3f3  lea     r8d, [rdx+4Eh]; Size
0x18009f3f7  lea     rcx, [rbp+57h+Data]; void *
0x18009f3fb  call    memset_0
0x18009f400  mov     [rsp+110h+Type], 0
0x18009f408  mov     [rsp+110h+cbData], 4Eh ; 'N'
0x18009f410  lea     rax, [rsp+110h+cbData]
0x18009f415  mov     [rsp+110h+lpcbData], rax; lpcbData
0x18009f41a  lea     rax, [rbp+57h+Data]
0x18009f41e  mov     [rsp+110h+lpData], rax; lpData
0x18009f423  lea     r9, [rsp+110h+Type]; lpType
0x18009f428  xor     r8d, r8d; lpReserved
0x18009f42b  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x18009f432  mov     rcx, rsi; hKey
0x18009f435  call    cs:__imp_RegQueryValueExW
0x18009f43b  test    eax, eax
0x18009f43d  jz      short loc_18009F474
0x18009f43f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f446  lea     rdx, WPP_GLOBAL_Control
0x18009f44d  cmp     rcx, rdx
0x18009f450  jz      loc_18009F52D
0x18009f456  cmp     byte ptr [rcx+69h], 2
0x18009f45a  jb      loc_18009F52D
0x18009f460  test    byte ptr [rcx+6Ch], 1
0x18009f464  jz      loc_18009F52D
0x18009f46a  mov     edx, 0Ch
0x18009f46f  jmp     loc_18009F3C4
0x18009f474  mov     r9d, [rsp+110h+Type]
0x18009f479  cmp     r9d, 1
0x18009f47d  jz      short loc_18009F4B4
0x18009f47f  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f486  lea     rax, WPP_GLOBAL_Control
0x18009f48d  cmp     rcx, rax
0x18009f490  jz      loc_18009F52D
0x18009f496  cmp     byte ptr [rcx+69h], 2
0x18009f49a  jb      loc_18009F52D
0x18009f4a0  test    byte ptr [rcx+6Ch], 1
0x18009f4a4  jz      loc_18009F52D
0x18009f4aa  mov     edx, 0Dh
0x18009f4af  jmp     loc_18009F3C7
0x18009f4b4  xor     eax, eax
0x18009f4b6  mov     [rbp+57h+var_34], ax
0x18009f4ba  xorps   xmm0, xmm0
0x18009f4bd  movups  xmmword ptr [rbp+57h+iid.Data1], xmm0
0x18009f4c1  lea     rdx, [rbp+57h+iid]; lpiid
0x18009f4c5  lea     rcx, [rbp+57h+Data]; lpsz
0x18009f4c9  call    cs:__imp_IIDFromString
0x18009f4cf  test    eax, eax
0x18009f4d1  jns     short loc_18009F515
0x18009f4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f4da  lea     rax, WPP_GLOBAL_Control
0x18009f4e1  cmp     rcx, rax
0x18009f4e4  jz      short loc_18009F52D
0x18009f4e6  cmp     byte ptr [rcx+69h], 2
0x18009f4ea  jb      short loc_18009F52D
0x18009f4ec  test    byte ptr [rcx+6Ch], 1
0x18009f4f0  jz      short loc_18009F52D
0x18009f4f2  mov     edx, 0Eh
0x18009f4f7  lea     rax, [rbp+57h+Data]
0x18009f4fb  mov     [rsp+110h+lpData], rax
0x18009f500  xor     r9d, r9d
0x18009f503  lea     r8, WPP_2222ea3dedc832ba560939e1a0f845a2_Traceguids
0x18009f50a  mov     rcx, [rcx+60h]
0x18009f50e  call    WPP_SF_DS
0x18009f513  jmp     short loc_18009F52D
0x18009f515  mov     rax, qword ptr [rbp+57h+iid.Data1]
0x18009f519  sub     rax, [r12]
0x18009f51d  jnz     short loc_18009F528
0x18009f51f  mov     rax, qword ptr [rbp+57h+iid.Data4]
0x18009f523  sub     rax, [r12+8]
0x18009f528  test    rax, rax
0x18009f52b  jz      short loc_18009F535
0x18009f52d  inc     r15d
0x18009f530  jmp     loc_18009F34B
0x18009f535  lea     r8, [rbp+57h+var_B0]; struct _DO_DEVINFO_DATA *
0x18009f539  lea     rdx, [rsp+110h+var_D8]; void **
0x18009f53e  mov     rcx, r14; this
0x18009f541  call    ?QueryHardwareId@PnpDriverInfo@WfdInterfaceDiagnosticsModule@@AEAAXAEAPEAXAEAU_DO_DEVINFO_DATA@@@Z; WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryHardwareId(void * &,_DO_DEVINFO_DATA &)
0x18009f546  lea     r8, [rbp+57h+var_B0]; struct _DO_DEVINFO_DATA *
0x18009f54a  lea     rdx, [rsp+110h+var_D8]; void **
0x18009f54f  mov     rcx, r14; this
0x18009f552  call    ?QueryFriendlyName@PnpDriverInfo@WfdInterfaceDiagnosticsModule@@AEAAXAEAPEAXAEAU_DO_DEVINFO_DATA@@@Z; WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryFriendlyName(void * &,_DO_DEVINFO_DATA &)
0x18009f557  mov     rdx, rsi; HKEY
0x18009f55a  mov     rcx, r14; this
0x18009f55d  call    ?QueryDriverVersion@PnpDriverInfo@WfdInterfaceDiagnosticsModule@@AEAAXPEAUHKEY__@@@Z; WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDriverVersion(HKEY__ *)
0x18009f562  mov     rdx, rsi; HKEY
0x18009f565  mov     rcx, r14; this
0x18009f568  call    ?QueryDriverDate@PnpDriverInfo@WfdInterfaceDiagnosticsModule@@AEAAXPEAUHKEY__@@@Z; WfdInterfaceDiagnosticsModule::PnpDriverInfo::QueryDriverDate(HKEY__ *)
0x18009f56d  nop
0x18009f56e  test    rsi, rsi
0x18009f571  jz      short loc_18009F57D
0x18009f573  mov     rcx, rsi; hKey
0x18009f576  call    cs:__imp_RegCloseKey
0x18009f57c  nop
0x18009f57d  test    rbx, rbx
0x18009f580  jz      short loc_18009F58B
0x18009f582  mov     rcx, rbx
0x18009f585  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18009f58b  mov     rcx, [rbp+57h+var_30]
0x18009f58f  xor     rcx, rsp; StackCookie
0x18009f592  call    __security_check_cookie
0x18009f597  lea     r11, [rsp+110h+var_20]
0x18009f59f  mov     rbx, [r11+40h]
0x18009f5a3  mov     rsi, [r11+48h]
0x18009f5a7  mov     rsp, r11
0x18009f5aa  pop     r15
0x18009f5ac  pop     r14
0x18009f5ae  pop     r12
0x18009f5b0  pop     rdi
0x18009f5b1  pop     rbp
0x18009f5b2  retn
0x18009f5b3  call    cs:__imp_GetLastError
0x18009f5b9  nop
0x18009f5ba  cmp     eax, 103h
0x18009f5bf  jnz     short loc_18009F5EC
0x18009f5c1  lea     rax, aDeviceNotFound; "Device not found"
0x18009f5c8  mov     [rsp+110h+lpData], rax; unsigned __int16 *
0x18009f5cd  mov     r9d, 0BDh; unsigned int
0x18009f5d3  lea     r8, aOnecoreuapNetW_24; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18009f5da  lea     rdx, aWfdinterfacedi_1; "WfdInterfaceDiagnosticsModule::PnpDrive"...
0x18009f5e1  mov     ecx, 80070103h; int
0x18009f5e6  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
0x18009f5ec  test    eax, eax
0x18009f5ee  jle     short loc_18009F5F8
0x18009f5f0  movzx   eax, ax
0x18009f5f3  or      eax, 80070000h
0x18009f5f8  lea     rcx, aDevobjenumdevi; "DevObjEnumDeviceInfo failed"
0x18009f5ff  mov     [rsp+110h+lpData], rcx; unsigned __int16 *
0x18009f604  mov     r9d, 0C1h; unsigned int
0x18009f60a  lea     r8, aOnecoreuapNetW_24; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18009f611  lea     rdx, aWfdinterfacedi_1; "WfdInterfaceDiagnosticsModule::PnpDrive"...
0x18009f618  mov     ecx, eax; int
0x18009f61a  call    ?Throw@CWFDSvcException@WFDSvc@@SAXJPEBD0KPEBG@Z; WFDSvc::CWFDSvcException::Throw(long,char const *,char const *,ulong,ushort const *)
```
