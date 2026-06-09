# MbaeDevNode::GetDeviceInfoForNetworkInterfaceId(ushort const *,ATL::CComBSTR *,ATL::CComBSTR *,_GUID *)

- ea: `0x1800bbd74`
- end: `0x1800bc1b5`
- name: `?GetDeviceInfoForNetworkInterfaceId@MbaeDevNode@@SAJPEBGPEAVCComBSTR@ATL@@1PEAU_GUID@@@Z`
- size: `1089`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct ATL::CComBSTR *, struct ATL::CComBSTR *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b9de8`

## callees

- `0x1800085d0`
- `0x180012300`
- `0x180016c50`
- `0x180019f24`
- `0x180074758`
- `0x180074cec`
- `0x1800bbd74`
- `0x1800bc1bc`
- `0x1800bc318`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bbfc0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800bbfc0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bbde9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bbdf6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bbde9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800bbdf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbe70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbe28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbe70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bbf1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc06f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc0c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc113`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc0b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bc0b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbf7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bbf7a`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800bc065`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800bc065`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800bbede`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x1800bbede`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800bc109`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x1800bc109`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800bbf0b`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x1800bbf0b`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800bbe66`
- `DEVOBJ!DevObjGetClassDevs` at `0x1800bbe66`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800bbe19`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x1800bbe19`

## string_xrefs

- `0x1800bbe3d`: `DevObjCreateDeviceInfoList failed, hr = 0x%8x`
- `0x1800bbf32`: `DevObjOpenDevRegKey failed, hr = 0x%8x`
- `0x1800bc00d`: `DeviceInstanceId (%ws), DeviceInterfacePath(%ws) for NetworkInterfaceId (%ws)`

## pseudocode

```c
__int64 __fastcall MbaeDevNode::GetDeviceInfoForNetworkInterfaceId(
        const unsigned __int16 *a1,
        BSTR *a2,
        struct ATL::CComBSTR *a3,
        struct _GUID *a4)
{
  __int64 DeviceInfoList; // rax
  void *v9; // rdi
  signed int LastError; // eax
  signed int DeviceInstanceIdForNetworkDevice; // ebx
  signed int v12; // eax
  unsigned int v13; // esi
  char v14; // r14
  HKEY v15; // r12
  signed int v16; // eax
  LSTATUS v17; // eax
  struct ATL::CComBSTR *v18; // r14
  signed int v19; // eax
  DWORD v20; // eax
  bool v21; // sf
  signed int v22; // eax
  unsigned int v23; // edx
  LPBYTE lpData; // [rsp+20h] [rbp-B9h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-B1h]
  DWORD cbData; // [rsp+40h] [rbp-99h] BYREF
  int v28; // [rsp+44h] [rbp-95h] BYREF
  struct ATL::CComBSTR *v29; // [rsp+48h] [rbp-91h]
  struct _GUID *v30; // [rsp+50h] [rbp-89h]
  int v31; // [rsp+58h] [rbp-81h] BYREF
  __int128 v32; // [rsp+5Ch] [rbp-7Dh]
  BYTE v33[28]; // [rsp+6Ch] [rbp-6Dh] BYREF
  BYTE Data[80]; // [rsp+90h] [rbp-49h] BYREF

  v30 = a4;
  v29 = a3;
  WwanLog::Enter("MbaeDevNode::GetDeviceInfoForNetworkInterfaceId");
  if ( !a1 || !*a1 || !a2 || !a3 )
  {
    DeviceInstanceIdForNetworkDevice = -2147024809;
    WwanLog::Error(
      "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
      0,
      L"Invalid parameters, hr = 0x%8x",
      2147942487LL);
    WwanLog::Exit("MbaeDevNode::GetDeviceInfoForNetworkInterfaceId");
    return (unsigned int)DeviceInstanceIdForNetworkDevice;
  }
  SysFreeString(*a2);
  *a2 = 0;
  SysFreeString(*(BSTR *)a3);
  *(_QWORD *)a3 = 0;
  *a4 = GUID_NULL;
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v9 = (void *)DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
    DeviceInstanceIdForNetworkDevice = LastError;
    if ( LastError > 0 )
      DeviceInstanceIdForNetworkDevice = (unsigned __int16)LastError | 0x80070000;
    WwanLog::Error(
      "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
      0,
      L"DevObjCreateDeviceInfoList failed, hr = 0x%8x",
      (unsigned int)DeviceInstanceIdForNetworkDevice);
  }
  else
  {
    DeviceInstanceIdForNetworkDevice = 0;
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_NET, 0, 16, 0, 0) )
      goto LABEL_14;
    v12 = GetLastError();
    DeviceInstanceIdForNetworkDevice = v12;
    if ( v12 > 0 )
      DeviceInstanceIdForNetworkDevice = (unsigned __int16)v12 | 0x80070000;
    WwanLog::Error(
      "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
      0,
      L"DevObjGetClassDevs failed, hr = 0x%8x",
      (unsigned int)DeviceInstanceIdForNetworkDevice);
  }
  if ( DeviceInstanceIdForNetworkDevice >= 0 )
  {
LABEL_14:
    v31 = 48;
    memset(v33, 0, sizeof(v33));
    v13 = 0;
    v14 = 1;
    cbData = 0;
    v32 = 0;
    while ( v13 < 0x3E8 )
    {
      if ( !(unsigned int)DevObjEnumDeviceInfo(v9, v13, &v31) )
      {
        v20 = GetLastError();
        DeviceInstanceIdForNetworkDevice = 0;
        if ( v20 != 259 )
          DeviceInstanceIdForNetworkDevice = v20;
        v21 = DeviceInstanceIdForNetworkDevice < 0;
        if ( DeviceInstanceIdForNetworkDevice > 0 )
        {
          DeviceInstanceIdForNetworkDevice = (unsigned __int16)DeviceInstanceIdForNetworkDevice | 0x80070000;
          v21 = DeviceInstanceIdForNetworkDevice < 0;
        }
        if ( v21 )
          WwanLog::Error(
            "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
            0,
            L"DevObjEnumDeviceInfo failed, hr = 0x%8x",
            (unsigned int)DeviceInstanceIdForNetworkDevice);
        break;
      }
      LODWORD(lpcbData) = 131097;
      LODWORD(lpData) = 2;
      v15 = (HKEY)DevObjOpenDevRegKey(v9, &v31, 1);
      if ( v15 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        v16 = GetLastError();
        DeviceInstanceIdForNetworkDevice = v16;
        if ( v16 > 0 )
          DeviceInstanceIdForNetworkDevice = (unsigned __int16)v16 | 0x80070000;
        WwanLog::Error(
          "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
          0,
          L"DevObjOpenDevRegKey failed, hr = 0x%8x",
          (unsigned int)DeviceInstanceIdForNetworkDevice,
          lpData,
          lpcbData);
      }
      if ( DeviceInstanceIdForNetworkDevice >= 0 )
      {
        cbData = 80;
        v17 = RegQueryValueExW(v15, L"NetCfgInstanceId", 0, 0, Data, &cbData);
        if ( v17 )
        {
          if ( v17 > 0 )
            DeviceInstanceIdForNetworkDevice = (unsigned __int16)v17 | 0x80070000;
          else
            DeviceInstanceIdForNetworkDevice = v17;
          WwanLog::Error(
            "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
            0,
            L"RegQueryValueEx failed, hr = 0x%8x",
            (unsigned int)DeviceInstanceIdForNetworkDevice);
        }
        else if ( !(unsigned int)_o__wcsnicmp(Data, a1, 40) )
        {
          DeviceInstanceIdForNetworkDevice = MbaeDevNode::_GetDeviceInstanceIdForNetworkDevice(
                                               v9,
                                               (struct _DO_DEVINFO_DATA *)&v31,
                                               (struct ATL::CComBSTR *)a2);
          if ( DeviceInstanceIdForNetworkDevice >= 0 )
          {
            v18 = v29;
            DeviceInstanceIdForNetworkDevice = MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice(
                                                 v9,
                                                 (struct _DO_DEVINFO_DATA *)&v31,
                                                 v29,
                                                 a1);
            if ( DeviceInstanceIdForNetworkDevice >= 0 )
            {
              WwanLog::Verbose(
                "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
                0,
                L"DeviceInstanceId (%ws), DeviceInterfacePath(%ws) for NetworkInterfaceId (%ws)",
                *a2,
                *(_QWORD *)v18,
                a1);
              v28 = 0;
              if ( (unsigned int)DevObjGetDeviceProperty(v9, &v31, &DEVPKEY_Device_ContainerId, &v28, v30, 16, 0, 0) )
              {
                if ( v28 != 13 )
                  DeviceInstanceIdForNetworkDevice = -2147418113;
              }
              else
              {
                v19 = GetLastError();
                DeviceInstanceIdForNetworkDevice = v19;
                if ( v19 > 0 )
                  DeviceInstanceIdForNetworkDevice = (unsigned __int16)v19 | 0x80070000;
                WwanLog::Error(
                  "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
                  0,
                  L"DevObjGetDeviceProperty failed, hr = 0x%8x",
                  (unsigned int)DeviceInstanceIdForNetworkDevice);
              }
            }
          }
          v14 = 0;
        }
        RegCloseKey(v15);
      }
      if ( !v14 )
        break;
      ++v13;
    }
  }
  if ( v9 != (void *)-1LL && !(unsigned int)DevObjDestroyDeviceInfoList(v9) )
  {
    v22 = GetLastError();
    DeviceInstanceIdForNetworkDevice = v22;
    if ( v22 > 0 )
      DeviceInstanceIdForNetworkDevice = (unsigned __int16)v22 | 0x80070000;
    WwanLog::Error(
      "MbaeDevNode::GetDeviceInfoForNetworkInterfaceId",
      0,
      L"DevObjDestroyDeviceInfoList failed, hr = 0x%8x",
      (unsigned int)DeviceInstanceIdForNetworkDevice,
      lpData);
  }
  if ( DeviceInstanceIdForNetworkDevice < 0 )
  {
    v23 = (unsigned __int16)DeviceInstanceIdForNetworkDevice;
    if ( (DeviceInstanceIdForNetworkDevice & 0x1FFF0000) != 0x70000 )
      v23 = DeviceInstanceIdForNetworkDevice;
  }
  else
  {
    v23 = 0;
  }
  WwanLog::ExitWithStatus("MbaeDevNode::GetDeviceInfoForNetworkInterfaceId", v23);
  return (unsigned int)DeviceInstanceIdForNetworkDevice;
}

```

## disassembly

```asm
0x1800bbd74  push    rbp
0x1800bbd76  push    rbx
0x1800bbd77  push    rsi
0x1800bbd78  push    rdi
0x1800bbd79  push    r12
0x1800bbd7b  push    r13
0x1800bbd7d  push    r14
0x1800bbd7f  push    r15
0x1800bbd81  lea     rbp, [rsp-1Fh]
0x1800bbd86  sub     rsp, 0F8h
0x1800bbd8d  mov     rax, cs:__security_cookie
0x1800bbd94  xor     rax, rsp
0x1800bbd97  mov     [rbp+57h+var_50], rax
0x1800bbd9b  mov     rbx, r8
0x1800bbd9e  mov     [rsp+130h+var_E0], r9
0x1800bbda3  mov     r15, rcx
0x1800bbda6  mov     [rsp+130h+var_E8], rbx
0x1800bbdab  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bbdb2  mov     rdi, r9
0x1800bbdb5  mov     r13, rdx
0x1800bbdb8  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x1800bbdbd  xor     r12d, r12d
0x1800bbdc0  test    r15, r15
0x1800bbdc3  jz      loc_1800BC16A
0x1800bbdc9  cmp     [r15], r12w
0x1800bbdcd  jz      loc_1800BC16A
0x1800bbdd3  test    r13, r13
0x1800bbdd6  jz      loc_1800BC16A
0x1800bbddc  test    rbx, rbx
0x1800bbddf  jz      loc_1800BC16A
0x1800bbde5  mov     rcx, [r13+0]; bstrString
0x1800bbde9  call    cs:__imp_SysFreeString
0x1800bbdef  mov     [r13+0], r12
0x1800bbdf3  mov     rcx, [rbx]; bstrString
0x1800bbdf6  call    cs:__imp_SysFreeString
0x1800bbdfc  mov     [rbx], r12
0x1800bbdff  xor     r9d, r9d
0x1800bbe02  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800bbe09  xor     r8d, r8d
0x1800bbe0c  mov     [rsp+130h+lpData], r12
0x1800bbe11  xor     edx, edx
0x1800bbe13  xor     ecx, ecx
0x1800bbe15  movdqu  xmmword ptr [rdi], xmm0
0x1800bbe19  call    cs:__imp_DevObjCreateDeviceInfoList
0x1800bbe1f  mov     rdi, rax
0x1800bbe22  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bbe26  jnz     short loc_1800BBE46
0x1800bbe28  call    cs:__imp_GetLastError
0x1800bbe2e  mov     ebx, eax
0x1800bbe30  test    eax, eax
0x1800bbe32  jle     short loc_1800BBE3D
0x1800bbe34  movzx   ebx, ax
0x1800bbe37  or      ebx, 80070000h
0x1800bbe3d  lea     r8, aDevobjcreatede_0; "DevObjCreateDeviceInfoList failed, hr ="...
0x1800bbe44  jmp     short loc_1800BBE8C
0x1800bbe46  mov     [rsp+130h+lpcbData], r12
0x1800bbe4b  lea     rdx, GUID_DEVINTERFACE_NET
0x1800bbe52  mov     r9d, 10h
0x1800bbe58  mov     [rsp+130h+lpData], r12
0x1800bbe5d  xor     r8d, r8d
0x1800bbe60  mov     rcx, rdi
0x1800bbe63  mov     ebx, r12d
0x1800bbe66  call    cs:__imp_DevObjGetClassDevs
0x1800bbe6c  test    eax, eax
0x1800bbe6e  jnz     short loc_1800BBEA6
0x1800bbe70  call    cs:__imp_GetLastError
0x1800bbe76  mov     ebx, eax
0x1800bbe78  test    eax, eax
0x1800bbe7a  jle     short loc_1800BBE85
0x1800bbe7c  movzx   ebx, ax
0x1800bbe7f  or      ebx, 80070000h
0x1800bbe85  lea     r8, aDevobjgetclass_1; "DevObjGetClassDevs failed, hr = 0x%8x"
0x1800bbe8c  mov     rdx, r12; struct _GUID *
0x1800bbe8f  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bbe96  mov     r9d, ebx
0x1800bbe99  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bbe9e  test    ebx, ebx
0x1800bbea0  js      loc_1800BC100
0x1800bbea6  xorps   xmm0, xmm0
0x1800bbea9  mov     [rsp+130h+var_D8], 30h ; '0'
0x1800bbeb1  movups  xmmword ptr [rbp+57h+var_C4], xmm0
0x1800bbeb5  mov     esi, r12d
0x1800bbeb8  mov     r14b, 1
0x1800bbebb  movups  xmmword ptr [rbp+57h+var_C4+0Ch], xmm0
0x1800bbebf  mov     [rsp+130h+cbData], r12d
0x1800bbec4  movups  [rbp+57h+var_D4], xmm0
0x1800bbec8  cmp     esi, 3E8h
0x1800bbece  jnb     loc_1800BC100
0x1800bbed4  lea     r8, [rsp+130h+var_D8]
0x1800bbed9  mov     edx, esi
0x1800bbedb  mov     rcx, rdi
0x1800bbede  call    cs:__imp_DevObjEnumDeviceInfo
0x1800bbee4  test    eax, eax
0x1800bbee6  jz      loc_1800BC0C6
0x1800bbeec  xor     r9d, r9d
0x1800bbeef  mov     dword ptr [rsp+130h+lpcbData], 20019h
0x1800bbef7  lea     rdx, [rsp+130h+var_D8]
0x1800bbefc  mov     dword ptr [rsp+130h+lpData], 2
0x1800bbf04  mov     rcx, rdi
0x1800bbf07  lea     r8d, [r9+1]
0x1800bbf0b  call    cs:__imp_DevObjOpenDevRegKey
0x1800bbf11  mov     r12, rax
0x1800bbf14  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bbf18  jnz     short loc_1800BBF47
0x1800bbf1a  call    cs:__imp_GetLastError
0x1800bbf20  mov     ebx, eax
0x1800bbf22  test    eax, eax
0x1800bbf24  jle     short loc_1800BBF2F
0x1800bbf26  movzx   ebx, ax
0x1800bbf29  or      ebx, 80070000h
0x1800bbf2f  mov     r9d, ebx
0x1800bbf32  lea     r8, aDevobjopendevr; "DevObjOpenDevRegKey failed, hr = 0x%8x"
0x1800bbf39  xor     edx, edx; struct _GUID *
0x1800bbf3b  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bbf42  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bbf47  test    ebx, ebx
0x1800bbf49  js      loc_1800BC0B7
0x1800bbf4f  lea     rax, [rsp+130h+cbData]
0x1800bbf54  mov     [rsp+130h+cbData], 50h ; 'P'
0x1800bbf5c  mov     [rsp+130h+lpcbData], rax; lpcbData
0x1800bbf61  lea     rdx, ValueName; "NetCfgInstanceId"
0x1800bbf68  lea     rax, [rbp+57h+Data]
0x1800bbf6c  xor     r9d, r9d; lpType
0x1800bbf6f  xor     r8d, r8d; lpReserved
0x1800bbf72  mov     [rsp+130h+lpData], rax; lpData
0x1800bbf77  mov     rcx, r12; hKey
0x1800bbf7a  call    cs:__imp_RegQueryValueExW
0x1800bbf80  test    eax, eax
0x1800bbf82  jz      short loc_1800BBFB3
0x1800bbf84  jg      short loc_1800BBF8A
0x1800bbf86  mov     ebx, eax
0x1800bbf88  jmp     short loc_1800BBF93
0x1800bbf8a  movzx   ebx, ax
0x1800bbf8d  or      ebx, 80070000h
0x1800bbf93  mov     r9d, ebx
0x1800bbf96  lea     r8, aRegqueryvaluee_2; "RegQueryValueEx failed, hr = 0x%8x"
0x1800bbf9d  xor     edx, edx; struct _GUID *
0x1800bbf9f  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bbfa6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bbfab  test    ebx, ebx
0x1800bbfad  js      loc_1800BC0AE
0x1800bbfb3  mov     r8d, 28h ; '('
0x1800bbfb9  lea     rcx, [rbp+57h+Data]
0x1800bbfbd  mov     rdx, r15
0x1800bbfc0  call    cs:__imp__o__wcsnicmp
0x1800bbfc6  test    eax, eax
0x1800bbfc8  jnz     loc_1800BC0AE
0x1800bbfce  mov     r8, r13; struct ATL::CComBSTR *
0x1800bbfd1  lea     rdx, [rsp+130h+var_D8]; struct _DO_DEVINFO_DATA *
0x1800bbfd6  mov     rcx, rdi; void *
0x1800bbfd9  call    ?_GetDeviceInstanceIdForNetworkDevice@MbaeDevNode@@KAJPEAXPEAU_DO_DEVINFO_DATA@@PEAVCComBSTR@ATL@@@Z; MbaeDevNode::_GetDeviceInstanceIdForNetworkDevice(void *,_DO_DEVINFO_DATA *,ATL::CComBSTR *)
0x1800bbfde  mov     ebx, eax
0x1800bbfe0  test    eax, eax
0x1800bbfe2  js      loc_1800BC0AB
0x1800bbfe8  mov     r14, [rsp+130h+var_E8]
0x1800bbfed  lea     rdx, [rsp+130h+var_D8]; struct _DO_DEVINFO_DATA *
0x1800bbff2  mov     r8, r14; struct ATL::CComBSTR *
0x1800bbff5  mov     r9, r15; unsigned __int16 *
0x1800bbff8  mov     rcx, rdi; void *
0x1800bbffb  call    ?_GetDeviceInterfacePathForNetworkDevice@MbaeDevNode@@KAJPEAXPEAU_DO_DEVINFO_DATA@@PEAVCComBSTR@ATL@@PEBG@Z; MbaeDevNode::_GetDeviceInterfacePathForNetworkDevice(void *,_DO_DEVINFO_DATA *,ATL::CComBSTR *,ushort const *)
0x1800bc000  mov     ebx, eax
0x1800bc002  test    eax, eax
0x1800bc004  js      loc_1800BC0AB
0x1800bc00a  mov     rax, [r14]
0x1800bc00d  lea     r8, aDeviceinstance_0; "DeviceInstanceId (%ws), DeviceInterface"...
0x1800bc014  mov     r9, [r13+0]
0x1800bc018  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc01f  mov     [rsp+130h+lpcbData], r15
0x1800bc024  xor     edx, edx; struct _GUID *
0x1800bc026  mov     [rsp+130h+lpData], rax
0x1800bc02b  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x1800bc030  xor     eax, eax
0x1800bc032  lea     r9, [rsp+130h+var_EC]
0x1800bc037  mov     [rsp+130h+var_F8], eax
0x1800bc03b  lea     r8, DEVPKEY_Device_ContainerId
0x1800bc042  mov     [rsp+130h+var_100], rax
0x1800bc047  lea     rdx, [rsp+130h+var_D8]
0x1800bc04c  mov     [rsp+130h+var_EC], eax
0x1800bc050  mov     rcx, rdi
0x1800bc053  mov     rax, [rsp+130h+var_E0]
0x1800bc058  mov     dword ptr [rsp+130h+lpcbData], 10h
0x1800bc060  mov     [rsp+130h+lpData], rax
0x1800bc065  call    cs:__imp_DevObjGetDeviceProperty
0x1800bc06b  test    eax, eax
0x1800bc06d  jnz     short loc_1800BC09E
0x1800bc06f  call    cs:__imp_GetLastError
0x1800bc075  mov     ebx, eax
0x1800bc077  test    eax, eax
0x1800bc079  jle     short loc_1800BC084
0x1800bc07b  movzx   ebx, ax
0x1800bc07e  or      ebx, 80070000h
0x1800bc084  mov     r9d, ebx
0x1800bc087  lea     r8, aDevobjgetdevic_2; "DevObjGetDeviceProperty failed, hr = 0x"...
0x1800bc08e  xor     edx, edx; struct _GUID *
0x1800bc090  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc097  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc09c  jmp     short loc_1800BC0AB
0x1800bc09e  cmp     [rsp+130h+var_EC], 0Dh
0x1800bc0a3  mov     eax, 8000FFFFh
0x1800bc0a8  cmovnz  ebx, eax
0x1800bc0ab  xor     r14b, r14b
0x1800bc0ae  mov     rcx, r12; hKey
0x1800bc0b1  call    cs:__imp_RegCloseKey
0x1800bc0b7  xor     r12d, r12d
0x1800bc0ba  test    r14b, r14b
0x1800bc0bd  jz      short loc_1800BC100
0x1800bc0bf  inc     esi
0x1800bc0c1  jmp     loc_1800BBEC8
0x1800bc0c6  call    cs:__imp_GetLastError
0x1800bc0cc  cmp     eax, 103h
0x1800bc0d1  mov     ebx, r12d
0x1800bc0d4  cmovnz  ebx, eax
0x1800bc0d7  test    ebx, ebx
0x1800bc0d9  jle     short loc_1800BC0E6
0x1800bc0db  movzx   ebx, bx
0x1800bc0de  or      ebx, 80070000h
0x1800bc0e4  test    ebx, ebx
0x1800bc0e6  jns     short loc_1800BC100
0x1800bc0e8  mov     r9d, ebx
0x1800bc0eb  lea     r8, aDevobjenumdevi; "DevObjEnumDeviceInfo failed, hr = 0x%8x"
0x1800bc0f2  xor     edx, edx; struct _GUID *
0x1800bc0f4  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc0fb  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc100  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bc104  jz      short loc_1800BC140
0x1800bc106  mov     rcx, rdi
0x1800bc109  call    cs:__imp_DevObjDestroyDeviceInfoList
0x1800bc10f  test    eax, eax
0x1800bc111  jnz     short loc_1800BC140
0x1800bc113  call    cs:__imp_GetLastError
0x1800bc119  mov     ebx, eax
0x1800bc11b  test    eax, eax
0x1800bc11d  jle     short loc_1800BC128
0x1800bc11f  movzx   ebx, ax
0x1800bc122  or      ebx, 80070000h
0x1800bc128  mov     r9d, ebx
0x1800bc12b  lea     r8, aDevobjdestroyd; "DevObjDestroyDeviceInfoList failed, hr "...
0x1800bc132  xor     edx, edx; struct _GUID *
0x1800bc134  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc13b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc140  test    ebx, ebx
0x1800bc142  js      short loc_1800BC149
0x1800bc144  mov     edx, r12d
0x1800bc147  jmp     short loc_1800BC15C
0x1800bc149  mov     eax, ebx
0x1800bc14b  movzx   edx, bx
0x1800bc14e  and     eax, 1FFF0000h
0x1800bc153  cmp     eax, 70000h
0x1800bc158  jz      short loc_1800BC15C
0x1800bc15a  mov     edx, ebx; unsigned int
0x1800bc15c  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc163  call    ?ExitWithStatus@WwanLog@@SAXPEBDK@Z; WwanLog::ExitWithStatus(char const *,ulong)
0x1800bc168  jmp     short loc_1800BC193
0x1800bc16a  mov     ebx, 80070057h
0x1800bc16f  lea     r8, aInvalidParamet_4; "Invalid parameters, hr = 0x%8x"
0x1800bc176  mov     r9d, ebx
0x1800bc179  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc180  xor     edx, edx; struct _GUID *
0x1800bc182  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800bc187  lea     rcx, aMbaedevnodeGet; "MbaeDevNode::GetDeviceInfoForNetworkInt"...
0x1800bc18e  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x1800bc193  mov     eax, ebx
0x1800bc195  mov     rcx, [rbp+57h+var_50]
0x1800bc199  xor     rcx, rsp; StackCookie
0x1800bc19c  call    __security_check_cookie
0x1800bc1a1  add     rsp, 0F8h
0x1800bc1a8  pop     r15
0x1800bc1aa  pop     r14
0x1800bc1ac  pop     r13
0x1800bc1ae  pop     r12
0x1800bc1b0  pop     rdi
0x1800bc1b1  pop     rsi
0x1800bc1b2  pop     rbx
0x1800bc1b3  pop     rbp
0x1800bc1b4  retn
```
