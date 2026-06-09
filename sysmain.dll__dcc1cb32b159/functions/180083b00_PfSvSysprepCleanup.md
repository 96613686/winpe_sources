# PfSvSysprepCleanup

- ea: `0x180083b00`
- end: `0x180083f13`
- name: `PfSvSysprepCleanup`
- size: `1043`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18003bafc`
- `0x180049d6c`
- `0x1800569cc`
- `0x18005cb4c`
- `0x18005ec74`
- `0x180073e08`
- `0x180083234`
- `0x180083b00`
- `0x180083f1c`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x180083cf1`
- `ntdll!NtDeleteKey` at `0x180083cf1`
- `ntdll!RtlGetVersion` at `0x180083be2`
- `ntdll!RtlGetVersion` at `0x180083be2`
- `ntdll!NtOpenKey` at `0x180083d71`
- `ntdll!NtOpenKey` at `0x180083d71`
- `ntdll!RtlNtStatusToDosError` at `0x180083cf9`
- `ntdll!RtlNtStatusToDosError` at `0x180083cf9`
- `ntdll!NtClose` at `0x180083dec`
- `ntdll!NtClose` at `0x180083dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083ee2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180083ee2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180083e00`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180083e00`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083cd2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083d87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083d99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083dab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083dbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083dcf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083de1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083cd2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083d87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083d99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083dab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083dbd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083dcf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180083de1`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180083cbe`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180083cbe`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180083c56`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180083c56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083c73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180083c73`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180083ec6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180083ed4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180083ec6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180083ed4`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180083b8e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180083b8e`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180083bb8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180083bb8`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180083c24`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x180083c24`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180083c69`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x180083c69`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180083c36`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x180083c36`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180083ce6`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180083ce6`

## string_xrefs

- `0x180083e44`: `ReadyBoot`
- `0x180083d02`: `\Registry\Machine\System\CurrentControlSet\Services\RdyBoost\Parameters`
- `0x180083d92`: `ReadyBootVolumeUniqueId`
- `0x180083da4`: `ReadyBootPlanAge`
- `0x180083e6b`: `HybridDriveCacheRebalance`
- `0x180083e88`: `HybridDriveCachePrepopulate`
- `0x180083e9e`: `HybridDriveCachePrepopulate`

## pseudocode

```c
__int64 PfSvSysprepCleanup()
{
  SC_HANDLE v0; // rax
  SC_HANDLE v1; // rsi
  SC_HANDLE v2; // rbx
  unsigned int v3; // edi
  int v4; // eax
  HKEY v5; // rdi
  NTSTATUS v6; // eax
  const WCHAR *v7; // rax
  __int64 v8; // rcx
  HKEY v10; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  HANDLE KeyHandle; // [rsp+78h] [rbp-88h] BYREF
  __int128 v14; // [rsp+80h] [rbp-80h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+C0h] [rbp-40h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+E0h] [rbp-20h] BYREF
  char v18; // [rsp+1FAh] [rbp+FAh]
  WCHAR ValueName[264]; // [rsp+200h] [rbp+100h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  cchValueName = 0;
  v10 = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset_0(&VersionInformation, 0, 0x11Cu);
  hKey = 0;
  KeyHandle = 0;
  if ( (unsigned int)PfsAttachStateCtxStart(&KeyHandle, 0) )
    goto LABEL_31;
  v0 = OpenSCManagerW(0, 0, 0xF003Fu);
  v1 = v0;
  if ( v0 )
  {
    v2 = OpenServiceW(v0, L"Sysmain", 0xF003Fu);
    if ( v2 )
    {
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( RtlGetVersion(&VersionInformation) >= 0 && v18 == 1 )
        ChangeServiceConfigW(v2, 0xFFFFFFFF, 2u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0);
      if ( ControlService(v2, 1u, &ServiceStatus) )
      {
        v3 = 0;
        while ( ServiceStatus.dwCurrentState == 3 && v3 < 0x3A98 )
        {
          Sleep(0x3E8u);
          v3 += 1000;
          if ( !QueryServiceStatus(v2, &ServiceStatus) )
            goto LABEL_13;
        }
        goto LABEL_14;
      }
    }
  }
  else
  {
    v2 = 0;
  }
LABEL_13:
  GetLastError();
LABEL_14:
  v4 = PfSvServiceRegistryKeyGet(&hKey, 1);
  v5 = hKey;
  if ( !v4 )
  {
    do
      cchValueName = 260;
    while ( !RegEnumValueW(v5, 0, ValueName, &cchValueName, 0, 0, 0, 0) && !RegDeleteValueW(v5, ValueName) );
    RegDeleteKeyW(v5, L"DiskAssessment");
  }
  v6 = NtDeleteKey(KeyHandle);
  RtlNtStatusToDosError(v6);
  v14 = 0;
  v7 = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  v8 = 0x7FFF;
  while ( *v7 )
  {
    ++v7;
    if ( !--v8 )
      goto LABEL_23;
  }
  *((_QWORD *)&v14 + 1) = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\RdyBoost\\Parameters";
  LOWORD(v14) = -2 - 2 * v8;
  WORD1(v14) = -2 * v8;
LABEL_23:
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v14;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey((PHANDLE)&v10, 0xF003Fu, &ObjectAttributes) >= 0 )
  {
    RegDeleteValueW(v10, L"BootPlan");
    RegDeleteValueW(v10, L"ReadyBootVolumeUniqueId");
    RegDeleteValueW(v10, L"ReadyBootPlanAge");
    RegDeleteValueW(v10, L"LastBootPlanUserTime");
    RegDeleteValueW(v10, L"EffectivePends");
    RegDeleteValueW(v10, L"BootCountwithPends");
    NtClose(v10);
  }
  RegDeleteTreeW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\EMDMgmt");
  StringCbCopyW(ValueName, 0x208u, L"prefetch");
  PfSvSysprepDeleteDirHelper(ValueName);
  StringCbCatW(ValueName, 0x208u, L"\\");
  StringCbCatW(ValueName, 0x208u, L"ReadyBoot");
  LODWORD(hKey) = 0;
  PfTaskUpdateTaskSettings((__int64)L"HybridDriveCacheRebalance", (__int64)HbDrvTskSetEnabledCallback, (__int64)&hKey);
  LODWORD(hKey) = 0;
  PfTaskUpdateTaskSettings((__int64)L"HybridDriveCachePrepopulate", (__int64)HbDrvTskSetEnabledCallback, (__int64)&hKey);
  PfTaskUpdateTaskSettings(
    (__int64)L"HybridDriveCachePrepopulate",
    (__int64)HbDrvTskRestoreMaintenanceSettingsCallback,
    0);
  HbDrvDeleteState(v5);
  PfSvSysprepDeleteDirHelper(ValueName);
  if ( v2 )
    CloseServiceHandle(v2);
  if ( v1 )
    CloseServiceHandle(v1);
  if ( v5 )
    RegCloseKey(v5);
LABEL_31:
  PfsAttachStateCtxCleanup(&KeyHandle);
  return 0;
}

```

## disassembly

```asm
0x180083b00  push    rbp
0x180083b02  push    rbx
0x180083b03  push    rsi
0x180083b04  push    rdi
0x180083b05  push    r14
0x180083b07  push    r15
0x180083b09  lea     rbp, [rsp-328h]
0x180083b11  sub     rsp, 428h
0x180083b18  mov     rax, cs:__security_cookie
0x180083b1f  xor     rax, rsp
0x180083b22  mov     [rbp+350h+var_40], rax
0x180083b29  xorps   xmm0, xmm0
0x180083b2c  lea     rcx, [rbp+350h+VersionInformation]; void *
0x180083b30  xor     r15d, r15d
0x180083b33  mov     edi, 11Ch
0x180083b38  movups  xmmword ptr [rbp+350h+ServiceStatus.dwServiceType], xmm0
0x180083b3c  mov     r8d, edi; Size
0x180083b3f  xor     eax, eax
0x180083b41  movups  xmmword ptr [rbp+350h+ObjectAttributes.ObjectName], xmm0
0x180083b45  xor     edx, edx; Val
0x180083b47  mov     [rsp+450h+cchValueName], r15d
0x180083b4c  movups  xmmword ptr [rbp+350h+ServiceStatus.dwWin32ExitCode], xmm0
0x180083b50  mov     [rsp+450h+var_3F0], r15
0x180083b55  movups  xmmword ptr [rbp+350h+ObjectAttributes+1Ch], xmm0
0x180083b59  movups  [rbp+350h+var_3D0], xmm0
0x180083b5d  movups  xmmword ptr [rbp+350h+ObjectAttributes.Length], xmm0
0x180083b61  call    memset_0
0x180083b66  xor     edx, edx
0x180083b68  mov     [rsp+450h+hKey], r15
0x180083b6d  lea     rcx, [rsp+450h+KeyHandle]
0x180083b72  mov     [rsp+450h+KeyHandle], r15
0x180083b77  call    PfsAttachStateCtxStart
0x180083b7c  test    eax, eax
0x180083b7e  jnz     loc_180083EE8
0x180083b84  xor     edx, edx; lpDatabaseName
0x180083b86  xor     ecx, ecx; lpMachineName
0x180083b88  mov     r8d, 0F003Fh; dwDesiredAccess
0x180083b8e  call    cs:__imp_OpenSCManagerW
0x180083b94  lea     r14d, [r15+2]
0x180083b98  mov     rsi, rax
0x180083b9b  test    rax, rax
0x180083b9e  jnz     short loc_180083BA8
0x180083ba0  mov     ebx, r15d
0x180083ba3  jmp     loc_180083C73
0x180083ba8  mov     r8d, 0F003Fh; dwDesiredAccess
0x180083bae  lea     rdx, ServiceName; "Sysmain"
0x180083bb5  mov     rcx, rsi; hSCManager
0x180083bb8  call    cs:__imp_OpenServiceW
0x180083bbe  mov     rbx, rax
0x180083bc1  test    rax, rax
0x180083bc4  jz      loc_180083C73
0x180083bca  xor     edx, edx; Val
0x180083bcc  lea     rcx, [rbp+350h+VersionInformation.dwMajorVersion]; void *
0x180083bd0  mov     r8d, 118h; Size
0x180083bd6  call    memset_0
0x180083bdb  lea     rcx, [rbp+350h+VersionInformation]; lpVersionInformation
0x180083bdf  mov     [rbp+350h+VersionInformation.dwOSVersionInfoSize], edi
0x180083be2  call    cs:__imp_RtlGetVersion
0x180083be8  test    eax, eax
0x180083bea  js      short loc_180083C2A
0x180083bec  cmp     [rbp+350h+var_256], 1
0x180083bf3  jnz     short loc_180083C2A
0x180083bf5  mov     [rsp+450h+lpDisplayName], r15; lpDisplayName
0x180083bfa  or      edx, 0FFFFFFFFh; dwServiceType
0x180083bfd  mov     [rsp+450h+lpPassword], r15; lpPassword
0x180083c02  mov     r9d, edx; dwErrorControl
0x180083c05  mov     [rsp+450h+lpServiceStartName], r15; lpServiceStartName
0x180083c0a  mov     r8d, r14d; dwStartType
0x180083c0d  mov     [rsp+450h+lpDependencies], r15; lpDependencies
0x180083c12  mov     rcx, rbx; hService
0x180083c15  mov     [rsp+450h+lpdwTagId], r15; lpdwTagId
0x180083c1a  mov     [rsp+450h+lpLoadOrderGroup], r15; lpLoadOrderGroup
0x180083c1f  mov     [rsp+450h+lpBinaryPathName], r15; lpBinaryPathName
0x180083c24  call    cs:__imp_ChangeServiceConfigW
0x180083c2a  lea     r8, [rbp+350h+ServiceStatus]; lpServiceStatus
0x180083c2e  mov     edx, 1; dwControl
0x180083c33  mov     rcx, rbx; hService
0x180083c36  call    cs:__imp_ControlService
0x180083c3c  test    eax, eax
0x180083c3e  jz      short loc_180083C73
0x180083c40  mov     edi, r15d
0x180083c43  cmp     [rbp+350h+ServiceStatus.dwCurrentState], 3
0x180083c47  jnz     short loc_180083C79
0x180083c49  cmp     edi, 3A98h
0x180083c4f  jnb     short loc_180083C79
0x180083c51  mov     ecx, 3E8h; dwMilliseconds
0x180083c56  call    cs:__imp_Sleep
0x180083c5c  lea     rdx, [rbp+350h+ServiceStatus]; lpServiceStatus
0x180083c60  mov     rcx, rbx; hService
0x180083c63  add     edi, 3E8h
0x180083c69  call    cs:__imp_QueryServiceStatus
0x180083c6f  test    eax, eax
0x180083c71  jnz     short loc_180083C43
0x180083c73  call    cs:__imp_GetLastError
0x180083c79  mov     edx, 1
0x180083c7e  lea     rcx, [rsp+450h+hKey]
0x180083c83  call    PfSvServiceRegistryKeyGet
0x180083c88  mov     rdi, [rsp+450h+hKey]
0x180083c8d  test    eax, eax
0x180083c8f  jnz     short loc_180083CEC
0x180083c91  mov     [rsp+450h+lpDependencies], r15; lpcbData
0x180083c96  lea     r9, [rsp+450h+cchValueName]; lpcchValueName
0x180083c9b  mov     [rsp+450h+lpdwTagId], r15; lpData
0x180083ca0  lea     r8, [rbp+350h+ValueName]; lpValueName
0x180083ca7  mov     [rsp+450h+lpLoadOrderGroup], r15; lpType
0x180083cac  xor     edx, edx; dwIndex
0x180083cae  mov     rcx, rdi; hKey
0x180083cb1  mov     [rsp+450h+lpBinaryPathName], r15; lpReserved
0x180083cb6  mov     [rsp+450h+cchValueName], 104h
0x180083cbe  call    cs:__imp_RegEnumValueW
0x180083cc4  test    eax, eax
0x180083cc6  jnz     short loc_180083CDC
0x180083cc8  lea     rdx, [rbp+350h+ValueName]; lpValueName
0x180083ccf  mov     rcx, rdi; hKey
0x180083cd2  call    cs:__imp_RegDeleteValueW
0x180083cd8  test    eax, eax
0x180083cda  jz      short loc_180083C91
0x180083cdc  lea     rdx, aDiskassessment; "DiskAssessment"
0x180083ce3  mov     rcx, rdi; hKey
0x180083ce6  call    cs:__imp_RegDeleteKeyW
0x180083cec  mov     rcx, [rsp+450h+KeyHandle]; KeyHandle
0x180083cf1  call    cs:__imp_NtDeleteKey
0x180083cf7  mov     ecx, eax; Status
0x180083cf9  call    cs:__imp_RtlNtStatusToDosError
0x180083cff  xorps   xmm0, xmm0
0x180083d02  lea     rdx, aRegistryMachin_2; "\\Registry\\Machine\\System\\CurrentCon"...
0x180083d09  movups  [rbp+350h+var_3D0], xmm0
0x180083d0d  mov     rax, rdx
0x180083d10  mov     ecx, 7FFFh
0x180083d15  cmp     [rax], r15w
0x180083d19  jz      short loc_180083D26
0x180083d1b  add     rax, r14
0x180083d1e  sub     rcx, 1
0x180083d22  jnz     short loc_180083D15
0x180083d24  jmp     short loc_180083D41
0x180083d26  add     cx, cx
0x180083d29  mov     qword ptr [rbp+350h+var_3D0+8], rdx
0x180083d2d  mov     eax, 0FFFEh
0x180083d32  sub     ax, cx
0x180083d35  mov     word ptr [rbp+350h+var_3D0], ax
0x180083d39  add     ax, r14w
0x180083d3d  mov     word ptr [rbp+350h+var_3D0+2], ax
0x180083d41  lea     rax, [rbp+350h+var_3D0]
0x180083d45  mov     [rbp+350h+ObjectAttributes.Length], 30h ; '0'
0x180083d4c  xorps   xmm0, xmm0
0x180083d4f  mov     [rbp+350h+ObjectAttributes.ObjectName], rax
0x180083d53  lea     r8, [rbp+350h+ObjectAttributes]; ObjectAttributes
0x180083d57  mov     [rbp+350h+ObjectAttributes.RootDirectory], r15
0x180083d5b  mov     edx, 0F003Fh; DesiredAccess
0x180083d60  mov     [rbp+350h+ObjectAttributes.Attributes], 40h ; '@'
0x180083d67  lea     rcx, [rsp+450h+var_3F0]; KeyHandle
0x180083d6c  movdqu  xmmword ptr [rbp+350h+ObjectAttributes.SecurityDescriptor], xmm0
0x180083d71  call    cs:__imp_NtOpenKey
0x180083d77  test    eax, eax
0x180083d79  js      short loc_180083DF2
0x180083d7b  mov     rcx, [rsp+450h+var_3F0]; hKey
0x180083d80  lea     rdx, aBootplan; "BootPlan"
0x180083d87  call    cs:__imp_RegDeleteValueW
0x180083d8d  mov     rcx, [rsp+450h+var_3F0]; hKey
0x180083d92  lea     rdx, Value; "ReadyBootVolumeUniqueId"
0x180083d99  call    cs:__imp_RegDeleteValueW
0x180083d9f  mov     rcx, [rsp+450h+var_3F0]; hKey
0x180083da4  lea     rdx, aReadybootplana; "ReadyBootPlanAge"
0x180083dab  call    cs:__imp_RegDeleteValueW
0x180083db1  mov     rcx, [rsp+450h+var_3F0]; hKey
0x180083db6  lea     rdx, aLastbootplanus; "LastBootPlanUserTime"
0x180083dbd  call    cs:__imp_RegDeleteValueW
0x180083dc3  mov     rcx, [rsp+450h+var_3F0]; hKey
0x180083dc8  lea     rdx, aEffectivepends; "EffectivePends"
0x180083dcf  call    cs:__imp_RegDeleteValueW
0x180083dd5  mov     rcx, [rsp+450h+var_3F0]; hKey
0x180083dda  lea     rdx, aBootcountwithp; "BootCountwithPends"
0x180083de1  call    cs:__imp_RegDeleteValueW
0x180083de7  mov     rcx, [rsp+450h+var_3F0]; Handle
0x180083dec  call    cs:__imp_NtClose
0x180083df2  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180083df9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180083e00  call    cs:__imp_RegDeleteTreeW
0x180083e06  mov     r14d, 208h
0x180083e0c  lea     r8, aPrefetch; "prefetch"
0x180083e13  mov     edx, r14d; cbDest
0x180083e16  lea     rcx, [rbp+350h+ValueName]; pszDest
0x180083e1d  call    StringCbCopyW
0x180083e22  lea     rcx, [rbp+350h+ValueName]; pszSrc
0x180083e29  call    PfSvSysprepDeleteDirHelper
0x180083e2e  lea     r8, asc_1800BF1BC; "\\"
0x180083e35  mov     edx, r14d; cbDest
0x180083e38  lea     rcx, [rbp+350h+ValueName]; pszDest
0x180083e3f  call    StringCbCatW
0x180083e44  lea     r8, aReadyboot; "ReadyBoot"
0x180083e4b  mov     edx, r14d; cbDest
0x180083e4e  lea     rcx, [rbp+350h+ValueName]; pszDest
0x180083e55  call    StringCbCatW
0x180083e5a  lea     r8, [rsp+450h+hKey]
0x180083e5f  mov     dword ptr [rsp+450h+hKey], r15d
0x180083e64  lea     rdx, ?HbDrvTskSetEnabledCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskSetEnabledCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x180083e6b  lea     rcx, aHybriddrivecac_0; "HybridDriveCacheRebalance"
0x180083e72  call    PfTaskUpdateTaskSettings
0x180083e77  lea     r8, [rsp+450h+hKey]
0x180083e7c  mov     dword ptr [rsp+450h+hKey], r15d
0x180083e81  lea     rdx, ?HbDrvTskSetEnabledCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskSetEnabledCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x180083e88  lea     rcx, aHybriddrivecac; "HybridDriveCachePrepopulate"
0x180083e8f  call    PfTaskUpdateTaskSettings
0x180083e94  xor     r8d, r8d
0x180083e97  lea     rdx, ?HbDrvTskRestoreMaintenanceSettingsCallback@@YAJPEAUITaskSettings3@@PEAUIMaintenanceSettings@@PEAKPEAX@Z; HbDrvTskRestoreMaintenanceSettingsCallback(ITaskSettings3 *,IMaintenanceSettings *,ulong *,void *)
0x180083e9e  lea     rcx, aHybriddrivecac; "HybridDriveCachePrepopulate"
0x180083ea5  call    PfTaskUpdateTaskSettings
0x180083eaa  mov     rcx, rdi; hKey
0x180083ead  call    HbDrvDeleteState
0x180083eb2  lea     rcx, [rbp+350h+ValueName]; pszSrc
0x180083eb9  call    PfSvSysprepDeleteDirHelper
0x180083ebe  test    rbx, rbx
0x180083ec1  jz      short loc_180083ECC
0x180083ec3  mov     rcx, rbx; hSCObject
0x180083ec6  call    cs:__imp_CloseServiceHandle
0x180083ecc  test    rsi, rsi
0x180083ecf  jz      short loc_180083EDA
0x180083ed1  mov     rcx, rsi; hSCObject
0x180083ed4  call    cs:__imp_CloseServiceHandle
0x180083eda  test    rdi, rdi
0x180083edd  jz      short loc_180083EE8
0x180083edf  mov     rcx, rdi; hKey
0x180083ee2  call    cs:__imp_RegCloseKey
0x180083ee8  lea     rcx, [rsp+450h+KeyHandle]
0x180083eed  call    PfsAttachStateCtxCleanup
0x180083ef2  xor     eax, eax
0x180083ef4  mov     rcx, [rbp+350h+var_40]
0x180083efb  xor     rcx, rsp; StackCookie
0x180083efe  call    __security_check_cookie
0x180083f03  add     rsp, 428h
0x180083f0a  pop     r15
0x180083f0c  pop     r14
0x180083f0e  pop     rdi
0x180083f0f  pop     rsi
0x180083f10  pop     rbx
0x180083f11  pop     rbp
0x180083f12  retn
```
