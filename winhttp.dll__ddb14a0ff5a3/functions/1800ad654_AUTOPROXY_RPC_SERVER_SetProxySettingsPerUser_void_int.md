# AUTOPROXY_RPC_SERVER::SetProxySettingsPerUser(void *,int)

- ea: `0x1800ad654`
- end: `0x1800ad9b1`
- name: `?SetProxySettingsPerUser@AUTOPROXY_RPC_SERVER@@AEAAJPEAXH@Z`
- size: `861`
- prototype: `int(AUTOPROXY_RPC_SERVER *__hidden this, void *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ade70`

## callees

- `0x180005670`
- `0x180006084`
- `0x180058f80`
- `0x180099128`
- `0x1800a1d10`
- `0x1800a2660`
- `0x1800ad654`
- `0x1800cf58c`
- `0x1800db6b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad8a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ad8a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad942`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad942`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ad850`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ad850`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ad8de`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ad8de`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ad7f5`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800ad7f5`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800ad7c2`
- `ntdll!RtlGetPersistedStateLocation` at `0x1800ad7c2`
- `RPCRT4!RpcImpersonateClient` at `0x1800ad76d`
- `RPCRT4!RpcImpersonateClient` at `0x1800ad76d`
- `RPCRT4!RpcRevertToSelf` at `0x1800ad952`
- `RPCRT4!RpcRevertToSelf` at `0x1800ad952`

## pseudocode

```c
__int64 __fastcall AUTOPROXY_RPC_SERVER::SetProxySettingsPerUser(AUTOPROXY_RPC_SERVER *this, void *a2, int a3)
{
  AUTOPROXY_RPC_SERVER *v4; // rsi
  int v6; // r14d
  signed int v7; // ebx
  unsigned int v8; // edi
  RPC_STATUS v9; // eax
  int PersistedStateLocation; // eax
  LSTATUS v11; // eax
  unsigned int *v12; // r8
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  int v15; // eax
  CRpcWatchDog *v16; // rcx
  WCHAR *dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+58h] [rbp-A8h] BYREF
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  _BYTE v22[40]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[69]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v24[390]; // [rsp+11Ah] [rbp+1Ah] BYREF

  v4 = g_pRpcSrv;
  wcscpy(SubKey, L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\Interneettings");
  v6 = 0;
  memset_0(v24, 0, 0x17Eu);
  hkey = 0;
  pvData = 0;
  pcbData = 0;
  AutoRpcWatchDog::AutoRpcWatchDog((AutoRpcWatchDog *)v22);
  if ( (xmmword_180107A60 & 0x20) != 0 )
  {
    LODWORD(dwOptions) = a3;
    WPP_SF_qD(1029, 85, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, a2);
  }
  if ( !*((_DWORD *)v4 + 21) )
  {
    v7 = -2146685199;
LABEL_5:
    v8 = v7;
    goto LABEL_28;
  }
  v9 = RpcImpersonateClient(a2);
  v7 = v9;
  if ( v9 > 0 )
    v7 = (unsigned __int16)v9 | 0x80070000;
  if ( v7 < 0 )
    goto LABEL_5;
  dwOptions = SubKey;
  v6 = 1;
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"InternetSettingsPolicies",
                             0,
                             L"SOFTWARE\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings",
                             0);
  v7 = HRESULT_FROM_NTSTATUS(PersistedStateLocation);
  if ( v7 < 0 )
    goto LABEL_5;
  if ( !a3 )
  {
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hkey, 0);
    v7 = v13;
    if ( v13 > 0 )
      v7 = (unsigned __int16)v13 | 0x80070000;
    if ( v7 < 0 || !RegGetValueW(hkey, 0, L"ProxySettingsPerUser", 0x18u, 0, &pvData, &pcbData) && !pvData )
      goto LABEL_5;
    pvData = 0;
    v14 = RegSetValueExW(hkey, L"ProxySettingsPerUser", 0, 4u, (const BYTE *)&pvData, 4u);
    v7 = v14;
    if ( v14 > 0 )
      v7 = (unsigned __int16)v14 | 0x80070000;
    v8 = v7;
    if ( v7 < 0 )
      goto LABEL_28;
LABEL_25:
    v15 = CWxGlobalCounters::Increment((PSRWLOCK)(*((_QWORD *)v4 + 37) + 8LL), 0, v12);
    if ( v15 < 0 && (xmmword_180107A60 & 0x20) != 0 )
      WPP_SF_d(1029, 86, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v15, dwOptions);
    goto LABEL_28;
  }
  v11 = RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"ProxySettingsPerUser");
  if ( v11 == 2 )
    goto LABEL_5;
  if ( v11 > 0 )
    v7 = (unsigned __int16)v11 | 0x80070000;
  else
    v7 = v11;
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_25;
LABEL_28:
  v16 = (CRpcWatchDog *)hkey;
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( v6 )
    RpcRevertToSelf();
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 87, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v7, dwOptions);
  CRpcWatchDog::RemoveEntry(v16, (struct _WatchDogEntry *)v22);
  return v8;
}

```

## disassembly

```asm
0x1800ad654  mov     [rsp-8+arg_0], rbx
0x1800ad659  mov     [rsp-8+arg_10], rsi
0x1800ad65e  push    rbp
0x1800ad65f  push    rdi
0x1800ad660  push    r12
0x1800ad662  push    r14
0x1800ad664  push    r15
0x1800ad666  lea     rbp, [rsp-1B0h]
0x1800ad66e  sub     rsp, 2B0h
0x1800ad675  mov     rax, cs:__security_cookie
0x1800ad67c  xor     rax, rsp
0x1800ad67f  mov     [rbp+1D0h+var_30], rax
0x1800ad686  movaps  xmm0, xmmword ptr cs:aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800ad68d  lea     rcx, [rbp+1D0h+var_1B6]; void *
0x1800ad691  movaps  xmm1, xmmword ptr cs:aSoftwarePolici+10h; "\\Policies\\Microsoft\\Windows\\Current"...
0x1800ad698  mov     edi, r8d
0x1800ad69b  mov     rsi, cs:?g_pRpcSrv@@3PEAVAUTOPROXY_RPC_SERVER@@EA; AUTOPROXY_RPC_SERVER * g_pRpcSrv
0x1800ad6a2  mov     rbx, rdx
0x1800ad6a5  movups  xmmword ptr [rbp+1D0h+SubKey], xmm0
0x1800ad6a9  xor     r15d, r15d
0x1800ad6ac  xor     edx, edx; Val
0x1800ad6ae  movaps  xmm0, xmmword ptr cs:aSoftwarePolici+20h; "s\\Microsoft\\Windows\\CurrentVersion\\"...
0x1800ad6b5  mov     r8d, 17Eh; Size
0x1800ad6bb  movups  [rbp+1D0h+var_220], xmm0
0x1800ad6bf  mov     r14d, r15d
0x1800ad6c2  mov     [rsp+2D0h+var_27C], r15d
0x1800ad6c7  movaps  xmm0, xmmword ptr cs:aSoftwarePolici+40h; "ows\\CurrentVersion\\Internet Settings"
0x1800ad6ce  movups  [rbp+1D0h+var_230], xmm1
0x1800ad6d2  movaps  xmm1, xmmword ptr cs:aSoftwarePolici+30h; "oft\\Windows\\CurrentVersion\\Internet "...
0x1800ad6d9  movups  [rbp+1D0h+var_200], xmm0
0x1800ad6dd  movaps  xmm0, xmmword ptr cs:aSoftwarePolici+60h; "on\\Internet Settings"
0x1800ad6e4  movups  [rbp+1D0h+var_210], xmm1
0x1800ad6e8  movaps  xmm1, xmmword ptr cs:aSoftwarePolici+50h; "entVersion\\Internet Settings"
0x1800ad6ef  movups  [rbp+1D0h+var_1E0], xmm0
0x1800ad6f3  movups  xmm0, xmmword ptr cs:aSoftwarePolici+7Ah; "ettings"
0x1800ad6fa  movups  [rbp+1D0h+var_1F0], xmm1
0x1800ad6fe  movaps  xmm1, xmmword ptr cs:aSoftwarePolici+70h; "net Settings"
0x1800ad705  movups  [rbp+1D0h+var_1D0], xmm1
0x1800ad709  movups  [rbp+1D0h+var_1D0+0Ah], xmm0
0x1800ad70d  call    memset_0
0x1800ad712  lea     rcx, [rsp+2D0h+var_268]; this
0x1800ad717  mov     [rsp+2D0h+hkey], r15
0x1800ad71c  mov     [rsp+2D0h+pvData], r15d
0x1800ad721  mov     [rsp+2D0h+pcbData], r15d
0x1800ad726  call    ??0AutoRpcWatchDog@@QEAA@XZ; AutoRpcWatchDog::AutoRpcWatchDog(void)
0x1800ad72b  test    byte ptr cs:xmmword_180107A60, 20h
0x1800ad732  jz      short loc_1800AD750
0x1800ad734  lea     edx, [r15+55h]
0x1800ad738  mov     [rsp+2D0h+dwOptions], edi
0x1800ad73c  mov     ecx, 405h
0x1800ad741  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x1800ad748  mov     r9, rbx
0x1800ad74b  call    WPP_SF_qD
0x1800ad750  cmp     [rsi+54h], r15d
0x1800ad754  jnz     short loc_1800AD76A
0x1800ad756  mov     ebx, 800C2EF1h
0x1800ad75b  mov     [rsp+2D0h+var_27C], 896h
0x1800ad763  mov     edi, ebx
0x1800ad765  jmp     loc_1800AD938
0x1800ad76a  mov     rcx, rbx; BindingHandle
0x1800ad76d  call    cs:__imp_RpcImpersonateClient
0x1800ad773  mov     ebx, eax
0x1800ad775  mov     r12d, 80070000h
0x1800ad77b  test    eax, eax
0x1800ad77d  jle     short loc_1800AD785
0x1800ad77f  movzx   ebx, ax
0x1800ad782  or      ebx, r12d
0x1800ad785  test    ebx, ebx
0x1800ad787  jns     short loc_1800AD793
0x1800ad789  mov     [rsp+2D0h+var_27C], 89Ch
0x1800ad791  jmp     short loc_1800AD763
0x1800ad793  mov     [rsp+2D0h+lpSecurityAttributes], r15
0x1800ad798  lea     rax, [rbp+1D0h+SubKey]
0x1800ad79c  mov     [rsp+2D0h+samDesired], 208h
0x1800ad7a4  lea     r8, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x1800ad7ab  xor     r9d, r9d
0x1800ad7ae  mov     qword ptr [rsp+2D0h+dwOptions], rax
0x1800ad7b3  xor     edx, edx
0x1800ad7b5  lea     rcx, aInternetsettin_1; "InternetSettingsPolicies"
0x1800ad7bc  mov     r14d, 1
0x1800ad7c2  call    cs:__imp_RtlGetPersistedStateLocation
0x1800ad7c8  mov     ecx, eax; int
0x1800ad7ca  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x1800ad7cf  mov     ebx, eax
0x1800ad7d1  test    eax, eax
0x1800ad7d3  jns     short loc_1800AD7DF
0x1800ad7d5  mov     [rsp+2D0h+var_27C], 8A9h
0x1800ad7dd  jmp     short loc_1800AD763
0x1800ad7df  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x1800ad7e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ad7ea  test    edi, edi
0x1800ad7ec  jz      short loc_1800AD829
0x1800ad7ee  lea     r8, aProxysettingsp; "ProxySettingsPerUser"
0x1800ad7f5  call    cs:__imp_RegDeleteKeyValueW
0x1800ad7fb  cmp     eax, 2
0x1800ad7fe  jz      loc_1800AD763
0x1800ad804  test    eax, eax
0x1800ad806  jg      short loc_1800AD80C
0x1800ad808  mov     ebx, eax
0x1800ad80a  jmp     short loc_1800AD812
0x1800ad80c  movzx   ebx, ax
0x1800ad80f  or      ebx, r12d
0x1800ad812  mov     edi, ebx
0x1800ad814  test    ebx, ebx
0x1800ad816  jns     loc_1800AD900
0x1800ad81c  mov     [rsp+2D0h+var_27C], 8BFh
0x1800ad824  jmp     loc_1800AD938
0x1800ad829  mov     [rsp+2D0h+lpdwDisposition], r15; lpdwDisposition
0x1800ad82e  lea     rax, [rsp+2D0h+hkey]
0x1800ad833  mov     [rsp+2D0h+phkResult], rax; phkResult
0x1800ad838  xor     r9d, r9d; lpClass
0x1800ad83b  mov     [rsp+2D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800ad840  xor     r8d, r8d; Reserved
0x1800ad843  mov     [rsp+2D0h+samDesired], 2001Fh; samDesired
0x1800ad84b  mov     [rsp+2D0h+dwOptions], r15d; dwOptions
0x1800ad850  call    cs:__imp_RegCreateKeyExW
0x1800ad856  mov     ebx, eax
0x1800ad858  test    eax, eax
0x1800ad85a  jle     short loc_1800AD862
0x1800ad85c  movzx   ebx, ax
0x1800ad85f  or      ebx, r12d
0x1800ad862  test    ebx, ebx
0x1800ad864  jns     short loc_1800AD873
0x1800ad866  mov     [rsp+2D0h+var_27C], 8CFh
0x1800ad86e  jmp     loc_1800AD763
0x1800ad873  mov     rcx, [rsp+2D0h+hkey]; hkey
0x1800ad878  lea     rax, [rsp+2D0h+pcbData]
0x1800ad87d  mov     [rsp+2D0h+lpSecurityAttributes], rax; pcbData
0x1800ad882  lea     r8, aProxysettingsp; "ProxySettingsPerUser"
0x1800ad889  lea     rax, [rsp+2D0h+pvData]
0x1800ad88e  mov     r9d, 18h; dwFlags
0x1800ad894  mov     qword ptr [rsp+2D0h+samDesired], rax; pvData
0x1800ad899  xor     edx, edx; lpSubKey
0x1800ad89b  mov     qword ptr [rsp+2D0h+dwOptions], r15; pdwType
0x1800ad8a0  call    cs:__imp_RegGetValueW
0x1800ad8a6  test    eax, eax
0x1800ad8a8  jnz     short loc_1800AD8B5
0x1800ad8aa  cmp     [rsp+2D0h+pvData], r15d
0x1800ad8af  jz      loc_1800AD763
0x1800ad8b5  mov     rcx, [rsp+2D0h+hkey]; hKey
0x1800ad8ba  lea     rax, [rsp+2D0h+pvData]
0x1800ad8bf  mov     r9d, 4; dwType
0x1800ad8c5  mov     [rsp+2D0h+pvData], r15d
0x1800ad8ca  mov     [rsp+2D0h+samDesired], r9d; cbData
0x1800ad8cf  lea     rdx, aProxysettingsp; "ProxySettingsPerUser"
0x1800ad8d6  xor     r8d, r8d; Reserved
0x1800ad8d9  mov     qword ptr [rsp+2D0h+dwOptions], rax; lpData
0x1800ad8de  call    cs:__imp_RegSetValueExW
0x1800ad8e4  mov     ebx, eax
0x1800ad8e6  test    eax, eax
0x1800ad8e8  jle     short loc_1800AD8F0
0x1800ad8ea  movzx   ebx, ax
0x1800ad8ed  or      ebx, r12d
0x1800ad8f0  mov     edi, ebx
0x1800ad8f2  test    ebx, ebx
0x1800ad8f4  jns     short loc_1800AD900
0x1800ad8f6  mov     [rsp+2D0h+var_27C], 8E7h
0x1800ad8fe  jmp     short loc_1800AD938
0x1800ad900  mov     rcx, [rsi+128h]
0x1800ad907  xor     edx, edx; unsigned int
0x1800ad909  add     rcx, 8; SRWLock
0x1800ad90d  call    ?Increment@CWxGlobalCounters@@QEAAJKPEAK@Z; CWxGlobalCounters::Increment(ulong,ulong *)
0x1800ad912  test    eax, eax
0x1800ad914  jns     short loc_1800AD938
0x1800ad916  test    byte ptr cs:xmmword_180107A60, 20h
0x1800ad91d  jz      short loc_1800AD938
0x1800ad91f  mov     edx, 56h ; 'V'
0x1800ad924  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x1800ad92b  mov     ecx, 405h
0x1800ad930  mov     r9d, eax
0x1800ad933  call    WPP_SF_d
0x1800ad938  mov     rcx, [rsp+2D0h+hkey]; hKey
0x1800ad93d  test    rcx, rcx
0x1800ad940  jz      short loc_1800AD94D
0x1800ad942  call    cs:__imp_RegCloseKey
0x1800ad948  mov     [rsp+2D0h+hkey], r15
0x1800ad94d  test    r14d, r14d
0x1800ad950  jz      short loc_1800AD958
0x1800ad952  call    cs:__imp_RpcRevertToSelf
0x1800ad958  test    byte ptr cs:xmmword_180107A60, 20h
0x1800ad95f  jz      short loc_1800AD97A
0x1800ad961  mov     edx, 57h ; 'W'
0x1800ad966  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x1800ad96d  mov     ecx, 405h
0x1800ad972  mov     r9d, ebx
0x1800ad975  call    WPP_SF_d
0x1800ad97a  lea     rdx, [rsp+2D0h+var_268]; struct _WatchDogEntry *
0x1800ad97f  call    ?RemoveEntry@CRpcWatchDog@@QEAAXPEAU_WatchDogEntry@@@Z; CRpcWatchDog::RemoveEntry(_WatchDogEntry *)
0x1800ad984  mov     eax, edi
0x1800ad986  mov     rcx, [rbp+1D0h+var_30]
0x1800ad98d  xor     rcx, rsp; StackCookie
0x1800ad990  call    __security_check_cookie
0x1800ad995  lea     r11, [rsp+2D0h+var_20]
0x1800ad99d  mov     rbx, [r11+30h]
0x1800ad9a1  mov     rsi, [r11+40h]
0x1800ad9a5  mov     rsp, r11
0x1800ad9a8  pop     r15
0x1800ad9aa  pop     r14
0x1800ad9ac  pop     r12
0x1800ad9ae  pop     rdi
0x1800ad9af  pop     rbp
0x1800ad9b0  retn
```
