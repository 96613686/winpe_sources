# VmmsSynthFcManager::CleanupVmLunPnp(_GUID const &)

- ea: `0x14035cbf8`
- end: `0x14035cf2a`
- name: `?CleanupVmLunPnp@VmmsSynthFcManager@@SAJAEBU_GUID@@@Z`
- size: `818`
- prototype: `__int64 __fastcall(GUID *rguid)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400fa6b0`
- `0x14035d914`
- `0x14063b7f0`

## callees

- `0x14035cbf8`
- `0x1404828e0`
- `0x1404835a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14035ccb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14035cd04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14035cd4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14035ccb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14035cd04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14035cd4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035cd7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035cd94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035ce06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035ce1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035cd7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035cd94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035ce06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14035ce1c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14035ce81`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14035ce81`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14035cec4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14035cec4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14035cef8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14035cef8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14035cc86`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x14035cc86`
- `DEVOBJ!DevObjUninstallDevice` at `0x14035cf17`
- `DEVOBJ!DevObjUninstallDevice` at `0x14035cf17`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x14035ce4c`
- `DEVOBJ!DevObjOpenDevRegKey` at `0x14035ce4c`
- `DEVOBJ!DevObjGetClassDevs` at `0x14035ccf4`
- `DEVOBJ!DevObjGetClassDevs` at `0x14035ccf4`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14035cd3a`
- `DEVOBJ!DevObjEnumDeviceInfo` at `0x14035cd3a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14035cd6a`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x14035cd6a`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14035cca5`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x14035cca5`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14035cde9`
- `api-ms-win-devices-config-l1-1-1!CM_Get_DevNode_Status` at `0x14035cde9`

## pseudocode

```c
__int64 __fastcall VmmsSynthFcManager::CleanupVmLunPnp(GUID *rguid)
{
  __int64 DeviceInfoList; // rax
  __int64 v3; // rsi
  signed int LastError; // ebx
  __int64 v5; // rdi
  unsigned int i; // ebx
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  ULONG pulProblemNumber; // [rsp+40h] [rbp-C0h] BYREF
  ULONG pulStatus; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v13; // [rsp+48h] [rbp-B8h] BYREF
  DEVINST dnDevInst[4]; // [rsp+58h] [rbp-A8h]
  __int128 v15; // [rsp+68h] [rbp-98h]
  OLECHAR sz[64]; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v18[526]; // [rsp+102h] [rbp+2h] BYREF

  pulStatus = 0;
  Type = 0;
  *(_WORD *)Data = 0;
  memset_0(v18, 0, 0x206u);
  cbData = 0;
  pulProblemNumber = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v13 = 0;
  *(_OWORD *)dnDevInst = 0;
  v15 = 0;
  StringFromGUID2(rguid, sz, 64);
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v3 = DeviceInfoList;
  if ( DeviceInfoList == -1 )
  {
    LastError = GetLastError();
  }
  else
  {
    v5 = -1;
    if ( (unsigned int)DevObjGetClassDevs(DeviceInfoList, &GUID_DEVINTERFACE_VMLUN, 0, 16, 0, 0) )
    {
      for ( i = 0; ; ++i )
      {
        v13 = 0;
        LODWORD(v13) = 48;
        *(_OWORD *)dnDevInst = 0;
        v15 = 0;
        if ( (unsigned int)DevObjEnumDeviceInfo(v3, i, &v13) )
        {
          if ( CM_Get_DevNode_Status(&pulStatus, &pulProblemNumber, dnDevInst[1], 0) == 13 )
          {
            if ( v5 != -1 )
              RegCloseKey((HKEY)v5);
            if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
            {
              RegCloseKey(hKey);
              hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
            }
            v5 = DevObjOpenDevRegKey(v3, &v13, 1);
            if ( v5 != -1 && !RegOpenKeyExW((HKEY)v5, L"VirtualMachine", 0, 0x20019u, &hKey) )
            {
              cbData = 520;
              if ( !RegQueryValueExW(hKey, L"VmId", 0, &Type, Data, &cbData)
                && Type == 1
                && CompareStringW(0x7Fu, 1u, (PCNZWCH)Data, -1, sz, -1) == 2 )
              {
                DevObjUninstallDevice(v3, &v13, 0, 0);
              }
            }
          }
        }
        else if ( GetLastError() == 259 )
        {
          LastError = 0;
          goto LABEL_9;
        }
      }
    }
    LastError = GetLastError();
LABEL_9:
    DevObjDestroyDeviceInfoList(v3);
    if ( v5 != -1 )
      RegCloseKey((HKEY)v5);
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x14035cbf8  mov     [rsp-8+arg_8], rbx
0x14035cbfd  mov     [rsp-8+arg_10], rsi
0x14035cc02  push    rbp
0x14035cc03  push    rdi
0x14035cc04  push    r15
0x14035cc06  lea     rbp, [rsp-220h]
0x14035cc0e  sub     rsp, 320h
0x14035cc15  mov     rax, cs:__security_cookie
0x14035cc1c  xor     rax, rsp
0x14035cc1f  mov     [rbp+230h+var_20], rax
0x14035cc26  mov     rbx, rcx
0x14035cc29  mov     [rsp+330h+pulStatus], 0
0x14035cc31  xor     eax, eax
0x14035cc33  mov     [rsp+330h+Type], 0
0x14035cc3b  lea     rcx, [rbp+230h+var_22E]; void *
0x14035cc3f  mov     word ptr [rbp+230h+Data], ax
0x14035cc43  xor     edx, edx; Val
0x14035cc45  mov     r8d, 206h; Size
0x14035cc4b  call    memset_0
0x14035cc50  xorps   xmm0, xmm0
0x14035cc53  mov     [rsp+330h+cbData], 0
0x14035cc5b  or      r15, 0FFFFFFFFFFFFFFFFh
0x14035cc5f  mov     [rsp+330h+pulProblemNumber], 0
0x14035cc67  lea     rdx, [rbp+230h+sz]; lpsz
0x14035cc6b  mov     [rsp+330h+hKey], r15
0x14035cc70  mov     rcx, rbx; rguid
0x14035cc73  movups  [rsp+330h+var_2E8], xmm0
0x14035cc78  lea     r8d, [r15+41h]; cchMax
0x14035cc7c  movups  xmmword ptr [rsp+330h+dnDevInst], xmm0
0x14035cc81  movups  [rsp+330h+var_2C8], xmm0
0x14035cc86  call    cs:__imp_StringFromGUID2
0x14035cc8d  nop     dword ptr [rax+rax+00h]
0x14035cc92  xor     r9d, r9d
0x14035cc95  mov     [rsp+330h+phkResult], 0
0x14035cc9e  xor     r8d, r8d
0x14035cca1  xor     edx, edx
0x14035cca3  xor     ecx, ecx
0x14035cca5  call    cs:__imp_DevObjCreateDeviceInfoList
0x14035ccac  nop     dword ptr [rax+rax+00h]
0x14035ccb1  mov     rsi, rax
0x14035ccb4  cmp     rax, r15
0x14035ccb7  jnz     short loc_14035CCCC
0x14035ccb9  call    cs:__imp_GetLastError
0x14035ccc0  nop     dword ptr [rax+rax+00h]
0x14035ccc5  mov     ebx, eax
0x14035ccc7  jmp     loc_14035CD8A
0x14035cccc  mov     [rsp+330h+lpcbData], 0
0x14035ccd5  lea     rdx, GUID_DEVINTERFACE_VMLUN
0x14035ccdc  mov     r9d, 10h
0x14035cce2  mov     [rsp+330h+phkResult], 0
0x14035cceb  xor     r8d, r8d
0x14035ccee  mov     rcx, rsi
0x14035ccf1  mov     rdi, r15
0x14035ccf4  call    cs:__imp_DevObjGetClassDevs
0x14035ccfb  nop     dword ptr [rax+rax+00h]
0x14035cd00  test    eax, eax
0x14035cd02  jnz     short loc_14035CD14
0x14035cd04  call    cs:__imp_GetLastError
0x14035cd0b  nop     dword ptr [rax+rax+00h]
0x14035cd10  mov     ebx, eax
0x14035cd12  jmp     short loc_14035CD67
0x14035cd14  xor     ebx, ebx
0x14035cd16  xorps   xmm0, xmm0
0x14035cd19  lea     r8, [rsp+330h+var_2E8]
0x14035cd1e  movups  [rsp+330h+var_2E8], xmm0
0x14035cd23  mov     edx, ebx
0x14035cd25  mov     dword ptr [rsp+330h+var_2E8], 30h ; '0'
0x14035cd2d  mov     rcx, rsi
0x14035cd30  movups  xmmword ptr [rsp+330h+dnDevInst], xmm0
0x14035cd35  movups  [rsp+330h+var_2C8], xmm0
0x14035cd3a  call    cs:__imp_DevObjEnumDeviceInfo
0x14035cd41  nop     dword ptr [rax+rax+00h]
0x14035cd46  test    eax, eax
0x14035cd48  jnz     loc_14035CDD7
0x14035cd4e  call    cs:__imp_GetLastError
0x14035cd55  nop     dword ptr [rax+rax+00h]
0x14035cd5a  cmp     eax, 103h
0x14035cd5f  jnz     loc_14035CF23
0x14035cd65  xor     ebx, ebx
0x14035cd67  mov     rcx, rsi
0x14035cd6a  call    cs:__imp_DevObjDestroyDeviceInfoList
0x14035cd71  nop     dword ptr [rax+rax+00h]
0x14035cd76  cmp     rdi, r15
0x14035cd79  jz      short loc_14035CD8A
0x14035cd7b  mov     rcx, rdi; hKey
0x14035cd7e  call    cs:__imp_RegCloseKey
0x14035cd85  nop     dword ptr [rax+rax+00h]
0x14035cd8a  mov     rcx, [rsp+330h+hKey]; hKey
0x14035cd8f  cmp     rcx, r15
0x14035cd92  jz      short loc_14035CDA0
0x14035cd94  call    cs:__imp_RegCloseKey
0x14035cd9b  nop     dword ptr [rax+rax+00h]
0x14035cda0  test    ebx, ebx
0x14035cda2  jle     short loc_14035CDAD
0x14035cda4  movzx   ebx, bx
0x14035cda7  or      ebx, 80070000h
0x14035cdad  mov     eax, ebx
0x14035cdaf  mov     rcx, [rbp+230h+var_20]
0x14035cdb6  xor     rcx, rsp; StackCookie
0x14035cdb9  call    __security_check_cookie
0x14035cdbe  lea     r11, [rsp+330h+var_10]
0x14035cdc6  mov     rbx, [r11+28h]
0x14035cdca  mov     rsi, [r11+30h]
0x14035cdce  mov     rsp, r11
0x14035cdd1  pop     r15
0x14035cdd3  pop     rdi
0x14035cdd4  pop     rbp
0x14035cdd5  retn
0x14035cdd7  mov     r8d, [rsp+330h+dnDevInst+4]; dnDevInst
0x14035cddc  lea     rdx, [rsp+330h+pulProblemNumber]; pulProblemNumber
0x14035cde1  xor     r9d, r9d; ulFlags
0x14035cde4  lea     rcx, [rsp+330h+pulStatus]; pulStatus
0x14035cde9  call    cs:__imp_CM_Get_DevNode_Status
0x14035cdf0  nop     dword ptr [rax+rax+00h]
0x14035cdf5  cmp     eax, 0Dh
0x14035cdf8  jnz     loc_14035CF23
0x14035cdfe  cmp     rdi, r15
0x14035ce01  jz      short loc_14035CE12
0x14035ce03  mov     rcx, rdi; hKey
0x14035ce06  call    cs:__imp_RegCloseKey
0x14035ce0d  nop     dword ptr [rax+rax+00h]
0x14035ce12  mov     rcx, [rsp+330h+hKey]; hKey
0x14035ce17  cmp     rcx, r15
0x14035ce1a  jz      short loc_14035CE2D
0x14035ce1c  call    cs:__imp_RegCloseKey
0x14035ce23  nop     dword ptr [rax+rax+00h]
0x14035ce28  mov     [rsp+330h+hKey], r15
0x14035ce2d  xor     r9d, r9d
0x14035ce30  mov     dword ptr [rsp+330h+lpcbData], 20019h
0x14035ce38  lea     rdx, [rsp+330h+var_2E8]
0x14035ce3d  mov     dword ptr [rsp+330h+phkResult], 1
0x14035ce45  mov     rcx, rsi
0x14035ce48  lea     r8d, [r9+1]
0x14035ce4c  call    cs:__imp_DevObjOpenDevRegKey
0x14035ce53  nop     dword ptr [rax+rax+00h]
0x14035ce58  mov     rdi, rax
0x14035ce5b  cmp     rax, r15
0x14035ce5e  jz      loc_14035CF23
0x14035ce64  lea     rax, [rsp+330h+hKey]
0x14035ce69  mov     r9d, 20019h; samDesired
0x14035ce6f  xor     r8d, r8d; ulOptions
0x14035ce72  mov     [rsp+330h+phkResult], rax; phkResult
0x14035ce77  lea     rdx, SubKey; "VirtualMachine"
0x14035ce7e  mov     rcx, rdi; hKey
0x14035ce81  call    cs:__imp_RegOpenKeyExW
0x14035ce88  nop     dword ptr [rax+rax+00h]
0x14035ce8d  test    eax, eax
0x14035ce8f  jnz     loc_14035CF23
0x14035ce95  mov     rcx, [rsp+330h+hKey]; hKey
0x14035ce9a  lea     rax, [rsp+330h+cbData]
0x14035ce9f  mov     [rsp+330h+lpcbData], rax; lpcbData
0x14035cea4  lea     r9, [rsp+330h+Type]; lpType
0x14035cea9  lea     rax, [rbp+230h+Data]
0x14035cead  mov     [rsp+330h+cbData], 208h
0x14035ceb5  xor     r8d, r8d; lpReserved
0x14035ceb8  mov     [rsp+330h+phkResult], rax; lpData
0x14035cebd  lea     rdx, aVmid_0; "VmId"
0x14035cec4  call    cs:__imp_RegQueryValueExW
0x14035cecb  nop     dword ptr [rax+rax+00h]
0x14035ced0  test    eax, eax
0x14035ced2  jnz     short loc_14035CF23
0x14035ced4  cmp     [rsp+330h+Type], 1
0x14035ced9  jnz     short loc_14035CF23
0x14035cedb  mov     edx, 1; dwCmpFlags
0x14035cee0  mov     dword ptr [rsp+330h+lpcbData], r15d; cchCount2
0x14035cee5  lea     rax, [rbp+230h+sz]
0x14035cee9  mov     r9d, r15d; cchCount1
0x14035ceec  lea     r8, [rbp+230h+Data]; lpString1
0x14035cef0  mov     [rsp+330h+phkResult], rax; lpString2
0x14035cef5  lea     ecx, [rdx+7Eh]; Locale
0x14035cef8  call    cs:__imp_CompareStringW
0x14035ceff  nop     dword ptr [rax+rax+00h]
0x14035cf04  cmp     eax, 2
0x14035cf07  jnz     short loc_14035CF23
0x14035cf09  xor     r9d, r9d
0x14035cf0c  lea     rdx, [rsp+330h+var_2E8]
0x14035cf11  xor     r8d, r8d
0x14035cf14  mov     rcx, rsi
0x14035cf17  call    cs:__imp_DevObjUninstallDevice
0x14035cf1e  nop     dword ptr [rax+rax+00h]
0x14035cf23  inc     ebx
0x14035cf25  jmp     loc_14035CD16
```
