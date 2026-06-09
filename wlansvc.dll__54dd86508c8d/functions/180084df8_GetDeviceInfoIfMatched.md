# GetDeviceInfoIfMatched

- ea: `0x180084df8`
- end: `0x18008539e`
- name: `GetDeviceInfoIfMatched`
- size: `1446`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, unsigned __int16 *, LPBYTE)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009b2fc`

## callees

- `0x18000aa0c`
- `0x18000c5a0`
- `0x180019bd0`
- `0x180029ca0`
- `0x18002f450`
- `0x180084df8`
- `0x1800c6774`
- `0x180106340`
- `0x180107330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800852ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085320`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800852ff`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180085320`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085142`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180084ec1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180085142`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084ef7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085061`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008524e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800852e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180084ef7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180085061`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008524e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800852e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084ffb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180084ffb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085373`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085357`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180085373`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180084eb2`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x180084eb2`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180085134`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800851ac`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x180085134`
- `DEVOBJ!DevObjGetDeviceProperty` at `0x1800851ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085346`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180085346`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180084f87`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180084f87`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180084f18`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180084f18`

## pseudocode

```c
__int64 __fastcall GetDeviceInfoIfMatched(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        unsigned __int16 *a6,
        LPBYTE a7)
{
  __int64 lpData; // rdi
  __int64 v11; // r14
  DWORD LastError; // ebx
  HRESULT v13; // eax
  __int64 i; // rdx
  __int64 v15; // r8
  const IID *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rax
  HRESULT v19; // eax
  int v20; // eax
  LSTATUS v21; // eax
  __int16 v22; // cx
  DWORD v23; // esi
  __int64 v24; // rbx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  DWORD v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  int v36; // [rsp+48h] [rbp-B8h] BYREF
  LPOLESTR lpsz; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h]
  _DWORD *v39; // [rsp+60h] [rbp-A0h]
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  __int64 v41; // [rsp+70h] [rbp-90h]
  GUID pclsid; // [rsp+78h] [rbp-88h] BYREF
  DEVPROPKEY v43; // [rsp+88h] [rbp-78h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF

  Type = 0;
  cbData = 0;
  lpsz = 0;
  *a4 = 0;
  v39 = a4;
  v38 = a3;
  v41 = a2;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  pclsid = 0;
  lpData = AllocWLMem(0x258u);
  if ( !lpData )
  {
    v11 = -1;
LABEL_3:
    LastError = 14;
    goto LABEL_79;
  }
  v11 = DevObjOpenDevRegKey(a2, a3, 1);
  if ( v11 == -1 )
    goto LABEL_5;
  cbData = 600;
  LastError = RegQueryValueExW((HKEY)v11, L"NetCfgInstanceId", 0, &Type, (LPBYTE)lpData, &cbData);
  if ( LastError )
    goto LABEL_79;
  *(_WORD *)(lpData + 598) = 0;
  v13 = CLSIDFromString((LPCOLESTR)lpData, &pclsid);
  LastError = v13;
  if ( v13 < 0 )
  {
    if ( (v13 & 0x1FFF0000) == 0x70000 )
      LastError = (unsigned __int16)v13;
    if ( LastError )
      goto LABEL_79;
  }
  v16 = (const IID *)(a1 + 8);
  v17 = *(_QWORD *)(a1 + 8) - *(_QWORD *)&pclsid.Data1;
  if ( !v17 )
    v17 = *(_QWORD *)(a1 + 16) - *(_QWORD *)pclsid.Data4;
  LastError = 0;
  if ( v17 )
  {
    if ( !a1 || (v18 = *(_QWORD *)(a1 + 768)) == 0 || !*(_QWORD *)(v18 + 480) )
    {
LABEL_26:
      if ( *v39 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v16, i, v15);
      goto LABEL_79;
    }
    v19 = StringFromCLSID(v16, &lpsz);
    LastError = v19;
    if ( v19 < 0 )
    {
      if ( (v19 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v19;
      if ( LastError )
        goto LABEL_79;
    }
    v20 = StringCchPrintfW(SubKey, 0x104u, L"NetworkInterface\\%s", lpsz);
    LastError = v20;
    if ( v20 < 0 )
    {
      if ( (v20 & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)v20;
      if ( LastError )
        goto LABEL_79;
    }
    LastError = 0;
    if ( RegOpenKeyExW((HKEY)v11, SubKey, 0, 0x20019u, &phkResult) )
      goto LABEL_26;
  }
  if ( a5 )
  {
    *a5 = 0;
    cbData = 36;
    *(_OWORD *)lpData = 0;
    *(_OWORD *)(lpData + 16) = 0;
    *(_DWORD *)(lpData + 32) = 0;
    v21 = RegQueryValueExW((HKEY)v11, L"NetworkAddress", 0, &Type, (LPBYTE)lpData, &cbData);
    LastError = v21;
    if ( !v21 || v21 == 234 )
    {
      LastError = 0;
      v15 = 0;
      for ( i = 0; (unsigned int)i < 0x12; i = (unsigned int)(i + 1) )
      {
        v22 = *(_WORD *)(lpData + 2LL * (unsigned int)i);
        if ( !v22 )
          break;
        if ( (unsigned __int16)(v22 - 48) <= 9u
          || (unsigned __int16)(v22 - 65) <= 5u
          || (unsigned __int16)(v22 - 97) <= 5u )
        {
          v15 = (unsigned int)(v15 + 1);
        }
        else if ( v22 != 45 )
        {
          goto LABEL_45;
        }
      }
      if ( (unsigned int)v15 >= 6 )
        *a5 = 1;
    }
    else
    {
      if ( v21 != 2 )
        goto LABEL_79;
      LastError = 0;
    }
  }
LABEL_45:
  v23 = 600;
  if ( !a6 )
    goto LABEL_61;
  cbData = 600;
  v43 = DEVPKEY_Device_HardwareIds;
  v36 = 0;
  memset_0(a6, 0, 0x258u);
  v24 = v41;
  if ( (unsigned int)DevObjGetDeviceProperty(v41, v38, &v43, &v36, a6, 600, &cbData, 0) )
    goto LABEL_59;
  if ( GetLastError() != 122 )
  {
    LastError = 0;
    *a6 = 0;
LABEL_60:
    a6[299] = 0;
LABEL_61:
    if ( a7 )
    {
      cbData = 600;
      v28 = 600;
      if ( v23 < 0x258 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(600, i, v15);
        v28 = cbData;
      }
      memset_0(a7, 0, v28);
      v29 = RegQueryValueExW((HKEY)v11, L"DriverVersion", 0, 0, a7, &cbData);
      if ( v29
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 105)
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 13, &WPP_ddf81be17d3f38632d423248857aa840_Traceguids, v29);
      }
      *((_WORD *)a7 + 299) = 0;
    }
    cbData = 600;
    memset_0((void *)lpData, 0, 0x258u);
    if ( cbData > v23 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v31, v30, v32);
    *(_DWORD *)(a1 + 2264) = 1;
    if ( !RegQueryValueExW((HKEY)v11, L"DeviceRadioMode", 0, &Type, (LPBYTE)lpData, &cbData) && Type == 1 )
    {
      if ( (unsigned int)_o__wcsicmp(lpData, L"XOR") )
      {
        if ( !(unsigned int)_o__wcsicmp(lpData, L"Scan-While") )
          *(_DWORD *)(a1 + 2264) = 4;
      }
      else
      {
        *(_DWORD *)(a1 + 2264) = 2;
      }
    }
    *v39 = 1;
    goto LABEL_79;
  }
  if ( cbData <= 0x258 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v25, i, v15);
  FreeWLMem(lpData);
  v23 = cbData;
  lpData = AllocWLMem(cbData);
  if ( !lpData )
    goto LABEL_3;
  if ( !(unsigned int)DevObjGetDeviceProperty(v24, v38, &v43, &v36, lpData, cbData, 0, 0) )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_79;
  }
  v26 = StringCchCopyW(a6, 0x12Cu, (const unsigned __int16 *)lpData);
  LastError = v26;
  if ( v26 >= 0 )
    goto LABEL_57;
  if ( (v26 & 0x1FFF0000) == 0x70000 )
    LastError = (unsigned __int16)v26;
  if ( !LastError )
  {
LABEL_57:
    if ( v36 != 8210 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v27, i, v15);
LABEL_59:
    LastError = 0;
    goto LABEL_60;
  }
LABEL_79:
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(phkResult);
  if ( lpData )
    FreeWLMem(lpData);
  if ( v11 != -1 )
    RegCloseKey((HKEY)v11);
  return LastError;
}

```

## disassembly

```asm
0x180084df8  push    rbp
0x180084dfa  push    rbx
0x180084dfb  push    rsi
0x180084dfc  push    rdi
0x180084dfd  push    r12
0x180084dff  push    r13
0x180084e01  push    r14
0x180084e03  push    r15
0x180084e05  lea     rbp, [rsp-1C8h]
0x180084e0d  sub     rsp, 2C8h
0x180084e14  mov     rax, cs:__security_cookie
0x180084e1b  xor     rax, rsp
0x180084e1e  mov     [rbp+200h+var_50], rax
0x180084e25  mov     rsi, [rbp+200h+arg_20]
0x180084e2c  mov     r15, rcx
0x180084e2f  mov     r12, [rbp+200h+arg_28]
0x180084e36  xor     ecx, ecx
0x180084e38  mov     r13, [rbp+200h+arg_30]
0x180084e3f  xorps   xmm0, xmm0
0x180084e42  mov     [rsp+300h+Type], ecx
0x180084e46  mov     r14, r8
0x180084e49  mov     [rsp+300h+cbData], ecx
0x180084e4d  mov     rbx, rdx
0x180084e50  mov     [rsp+300h+lpsz], rcx
0x180084e55  mov     [r9], ecx
0x180084e58  mov     ecx, 258h; dwBytes
0x180084e5d  mov     [rsp+300h+var_2A0], r9
0x180084e62  mov     [rsp+300h+var_2A8], r8
0x180084e67  mov     [rsp+300h+var_290], rdx
0x180084e6c  mov     [rsp+300h+phkResult], 0FFFFFFFFFFFFFFFFh
0x180084e75  movups  xmmword ptr [rsp+300h+pclsid.Data1], xmm0
0x180084e7a  call    AllocWLMem
0x180084e7f  mov     rdi, rax
0x180084e82  test    rax, rax
0x180084e85  jnz     short loc_180084E95
0x180084e87  or      r14, 0FFFFFFFFFFFFFFFFh
0x180084e8b  mov     ebx, 0Eh
0x180084e90  jmp     loc_18008533C
0x180084e95  xor     r9d, r9d
0x180084e98  mov     dword ptr [rsp+300h+lpcbData], 20019h
0x180084ea0  mov     rdx, r14
0x180084ea3  mov     dword ptr [rsp+300h+lpData], 2
0x180084eab  mov     rcx, rbx
0x180084eae  lea     r8d, [r9+1]
0x180084eb2  call    cs:__imp_DevObjOpenDevRegKey
0x180084eb8  mov     r14, rax
0x180084ebb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180084ebf  jnz     short loc_180084ECE
0x180084ec1  call    cs:__imp_GetLastError
0x180084ec7  mov     ebx, eax
0x180084ec9  jmp     loc_18008533C
0x180084ece  lea     rax, [rsp+300h+cbData]
0x180084ed3  mov     [rsp+300h+cbData], 258h
0x180084edb  mov     [rsp+300h+lpcbData], rax; lpcbData
0x180084ee0  lea     r9, [rsp+300h+Type]; lpType
0x180084ee5  xor     r8d, r8d; lpReserved
0x180084ee8  mov     [rsp+300h+lpData], rdi; lpData
0x180084eed  lea     rdx, aNetcfginstance; "NetCfgInstanceId"
0x180084ef4  mov     rcx, r14; hKey
0x180084ef7  call    cs:__imp_RegQueryValueExW
0x180084efd  xor     ecx, ecx
0x180084eff  mov     ebx, eax
0x180084f01  test    eax, eax
0x180084f03  jnz     loc_18008533C
0x180084f09  mov     [rdi+256h], cx
0x180084f10  lea     rdx, [rsp+300h+pclsid]; pclsid
0x180084f15  mov     rcx, rdi; lpsz
0x180084f18  call    cs:__imp_CLSIDFromString
0x180084f1e  mov     ebx, eax
0x180084f20  test    eax, eax
0x180084f22  jns     short loc_180084F3B
0x180084f24  and     eax, 1FFF0000h
0x180084f29  cmp     eax, 70000h
0x180084f2e  jnz     short loc_180084F33
0x180084f30  movzx   ebx, bx
0x180084f33  test    ebx, ebx
0x180084f35  jnz     loc_18008533C
0x180084f3b  lea     rcx, [r15+8]; rclsid
0x180084f3f  mov     rax, [rcx]
0x180084f42  sub     rax, qword ptr [rsp+300h+pclsid.Data1]
0x180084f47  jnz     short loc_180084F51
0x180084f49  mov     rax, [rcx+8]
0x180084f4d  sub     rax, qword ptr [rbp+200h+pclsid.Data4]
0x180084f51  xor     ebx, ebx
0x180084f53  test    rax, rax
0x180084f56  jz      loc_18008501E
0x180084f5c  test    r15, r15
0x180084f5f  jz      loc_180085007
0x180084f65  mov     rax, [r15+300h]
0x180084f6c  test    rax, rax
0x180084f6f  jz      loc_180085007
0x180084f75  cmp     [rax+1E0h], rbx
0x180084f7c  jz      loc_180085007
0x180084f82  lea     rdx, [rsp+300h+lpsz]; lplpsz
0x180084f87  call    cs:__imp_StringFromCLSID
0x180084f8d  mov     ebx, eax
0x180084f8f  test    eax, eax
0x180084f91  jns     short loc_180084FAA
0x180084f93  and     eax, 1FFF0000h
0x180084f98  cmp     eax, 70000h
0x180084f9d  jnz     short loc_180084FA2
0x180084f9f  movzx   ebx, bx
0x180084fa2  test    ebx, ebx
0x180084fa4  jnz     loc_18008533C
0x180084faa  mov     r9, [rsp+300h+lpsz]
0x180084faf  lea     r8, aNetworkinterfa; "NetworkInterface\\%s"
0x180084fb6  mov     edx, 104h; unsigned __int64
0x180084fbb  lea     rcx, [rbp+200h+SubKey]; unsigned __int16 *
0x180084fbf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180084fc4  mov     ebx, eax
0x180084fc6  test    eax, eax
0x180084fc8  jns     short loc_180084FE1
0x180084fca  and     eax, 1FFF0000h
0x180084fcf  cmp     eax, 70000h
0x180084fd4  jnz     short loc_180084FD9
0x180084fd6  movzx   ebx, bx
0x180084fd9  test    ebx, ebx
0x180084fdb  jnz     loc_18008533C
0x180084fe1  lea     rax, [rsp+300h+phkResult]
0x180084fe6  mov     r9d, 20019h; samDesired
0x180084fec  xor     r8d, r8d; ulOptions
0x180084fef  mov     [rsp+300h+lpData], rax; phkResult
0x180084ff4  lea     rdx, [rbp+200h+SubKey]; lpSubKey
0x180084ff8  mov     rcx, r14; hKey
0x180084ffb  call    cs:__imp_RegOpenKeyExW
0x180085001  xor     ebx, ebx
0x180085003  test    eax, eax
0x180085005  jz      short loc_18008501E
0x180085007  mov     rax, [rsp+300h+var_2A0]
0x18008500c  cmp     [rax], ebx
0x18008500e  jz      loc_18008533C
0x180085014  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180085019  jmp     loc_18008533C
0x18008501e  test    rsi, rsi
0x180085021  jz      loc_1800850CE
0x180085027  mov     [rsi], ebx
0x180085029  lea     r9, [rsp+300h+Type]; lpType
0x18008502e  mov     [rsp+300h+cbData], 24h ; '$'
0x180085036  lea     rdx, aNetworkaddress; "NetworkAddress"
0x18008503d  xorps   xmm0, xmm0
0x180085040  xor     eax, eax
0x180085042  movups  xmmword ptr [rdi], xmm0
0x180085045  xor     r8d, r8d; lpReserved
0x180085048  mov     rcx, r14; hKey
0x18008504b  movups  xmmword ptr [rdi+10h], xmm0
0x18008504f  mov     [rdi+20h], eax
0x180085052  lea     rax, [rsp+300h+cbData]
0x180085057  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18008505c  mov     [rsp+300h+lpData], rdi; lpData
0x180085061  call    cs:__imp_RegQueryValueExW
0x180085067  mov     ebx, eax
0x180085069  test    eax, eax
0x18008506b  jz      short loc_180085081
0x18008506d  cmp     eax, 0EAh
0x180085072  jz      short loc_180085081
0x180085074  cmp     eax, 2
0x180085077  jnz     loc_18008533C
0x18008507d  xor     ebx, ebx
0x18008507f  jmp     short loc_1800850CE
0x180085081  xor     ebx, ebx
0x180085083  mov     r8d, ebx
0x180085086  mov     edx, ebx
0x180085088  cmp     edx, 12h
0x18008508b  jnb     short loc_1800850C2
0x18008508d  mov     eax, edx
0x18008508f  movzx   ecx, word ptr [rdi+rax*2]
0x180085093  test    cx, cx
0x180085096  jz      short loc_1800850C2
0x180085098  lea     eax, [rcx-30h]
0x18008509b  cmp     ax, 9
0x18008509f  jbe     short loc_1800850BB
0x1800850a1  lea     eax, [rcx-41h]
0x1800850a4  cmp     ax, 5
0x1800850a8  jbe     short loc_1800850BB
0x1800850aa  lea     eax, [rcx-61h]
0x1800850ad  cmp     ax, 5
0x1800850b1  jbe     short loc_1800850BB
0x1800850b3  cmp     cx, 2Dh ; '-'
0x1800850b7  jz      short loc_1800850BE
0x1800850b9  jmp     short loc_1800850CE
0x1800850bb  inc     r8d
0x1800850be  inc     edx
0x1800850c0  jmp     short loc_180085088
0x1800850c2  cmp     r8d, 6
0x1800850c6  jb      short loc_1800850CE
0x1800850c8  mov     dword ptr [rsi], 1
0x1800850ce  mov     ecx, 258h
0x1800850d3  mov     esi, ecx
0x1800850d5  test    r12, r12
0x1800850d8  jz      loc_180085206
0x1800850de  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_HardwareIds.fmtid.Data1
0x1800850e5  mov     eax, cs:DEVPKEY_Device_HardwareIds.pid
0x1800850eb  mov     r8d, ecx; Size
0x1800850ee  mov     [rsp+300h+cbData], ecx
0x1800850f2  xor     edx, edx; Val
0x1800850f4  mov     rcx, r12; void *
0x1800850f7  mov     [rbp+200h+var_268], eax
0x1800850fa  movups  [rbp+200h+var_278], xmm0
0x1800850fe  mov     [rsp+300h+var_2B8], ebx
0x180085102  call    memset_0
0x180085107  mov     rdx, [rsp+300h+var_2A8]
0x18008510c  lea     rax, [rsp+300h+cbData]
0x180085111  mov     [rsp+300h+var_2C8], ebx
0x180085115  lea     r9, [rsp+300h+var_2B8]
0x18008511a  mov     rbx, [rsp+300h+var_290]
0x18008511f  lea     r8, [rbp+200h+var_278]
0x180085123  mov     [rsp+300h+var_2D0], rax
0x180085128  mov     rcx, rbx
0x18008512b  mov     dword ptr [rsp+300h+lpcbData], esi
0x18008512f  mov     [rsp+300h+lpData], r12
0x180085134  call    cs:__imp_DevObjGetDeviceProperty
0x18008513a  test    eax, eax
0x18008513c  jnz     loc_1800851F6
0x180085142  call    cs:__imp_GetLastError
0x180085148  cmp     eax, 7Ah ; 'z'
0x18008514b  jz      short loc_180085159
0x18008514d  xor     ebx, ebx
0x18008514f  mov     [r12], bx
0x180085154  jmp     loc_1800851F8
0x180085159  cmp     [rsp+300h+cbData], esi
0x18008515d  ja      short loc_180085164
0x18008515f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180085164  mov     rcx, rdi
0x180085167  call    FreeWLMem
0x18008516c  mov     esi, [rsp+300h+cbData]
0x180085170  mov     ecx, esi; dwBytes
0x180085172  call    AllocWLMem
0x180085177  xor     ecx, ecx
0x180085179  mov     rdi, rax
0x18008517c  test    rax, rax
0x18008517f  jz      loc_180084E8B
0x180085185  mov     eax, [rsp+300h+cbData]
0x180085189  lea     r9, [rsp+300h+var_2B8]
0x18008518e  mov     rdx, [rsp+300h+var_2A8]
0x180085193  lea     r8, [rbp+200h+var_278]
0x180085197  mov     [rsp+300h+var_2C8], ecx
0x18008519b  mov     [rsp+300h+var_2D0], rcx
0x1800851a0  mov     rcx, rbx
0x1800851a3  mov     dword ptr [rsp+300h+lpcbData], eax
0x1800851a7  mov     [rsp+300h+lpData], rdi
0x1800851ac  call    cs:__imp_DevObjGetDeviceProperty
0x1800851b2  test    eax, eax
0x1800851b4  jz      loc_180084EC1
0x1800851ba  mov     r8, rdi; unsigned __int16 *
0x1800851bd  mov     edx, 12Ch; unsigned __int64
0x1800851c2  mov     rcx, r12; unsigned __int16 *
0x1800851c5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800851ca  mov     ebx, eax
0x1800851cc  test    eax, eax
0x1800851ce  jns     short loc_1800851E7
0x1800851d0  and     eax, 1FFF0000h
0x1800851d5  cmp     eax, 70000h
0x1800851da  jnz     short loc_1800851DF
0x1800851dc  movzx   ebx, bx
0x1800851df  test    ebx, ebx
0x1800851e1  jnz     loc_18008533C
0x1800851e7  cmp     [rsp+300h+var_2B8], 2012h
0x1800851ef  jz      short loc_1800851F6
0x1800851f1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800851f6  xor     ebx, ebx
0x1800851f8  mov     [r12+256h], bx
0x180085201  mov     ecx, 258h
0x180085206  test    r13, r13
0x180085209  jz      loc_180085297
0x18008520f  mov     [rsp+300h+cbData], ecx
0x180085213  mov     eax, ecx
0x180085215  cmp     esi, ecx
0x180085217  jnb     short loc_180085222
0x180085219  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008521e  mov     eax, [rsp+300h+cbData]
0x180085222  mov     r8d, eax; Size
0x180085225  xor     edx, edx; Val
0x180085227  mov     rcx, r13; void *
0x18008522a  call    memset_0
0x18008522f  lea     rax, [rsp+300h+cbData]
0x180085234  xor     r9d, r9d; lpType
0x180085237  mov     [rsp+300h+lpcbData], rax; lpcbData
0x18008523c  lea     rdx, aDriverversion; "DriverVersion"
0x180085243  xor     r8d, r8d; lpReserved
0x180085246  mov     [rsp+300h+lpData], r13; lpData
0x18008524b  mov     rcx, r14; hKey
0x18008524e  call    cs:__imp_RegQueryValueExW
0x180085254  test    eax, eax
0x180085256  jz      short loc_18008528F
0x180085258  mov     rcx, cs:WPP_GLOBAL_Control
0x18008525f  lea     rdx, WPP_GLOBAL_Control
0x180085266  cmp     rcx, rdx
0x180085269  jz      short loc_18008528F
0x18008526b  cmp     byte ptr [rcx+69h], 1
0x18008526f  jb      short loc_18008528F
0x180085271  test    byte ptr [rcx+6Ch], 1
0x180085275  jz      short loc_18008528F
0x180085277  mov     rcx, [rcx+60h]
0x18008527b  lea     r8, WPP_ddf81be17d3f38632d423248857aa840_Traceguids
0x180085282  mov     edx, 0Dh
0x180085287  mov     r9d, eax
0x18008528a  call    WPP_SF_d
0x18008528f  mov     [r13+256h], bx
0x180085297  mov     eax, 258h
0x18008529c  xor     edx, edx; Val
  ... truncated ...
```
