# DeviceObject::Uninstall(void)

- ea: `0x180013c58`
- end: `0x180013e67`
- name: `?Uninstall@DeviceObject@@QEAAJXZ`
- size: `527`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011b94`
- `0x180013e70`

## callees

- `0x180005320`
- `0x18000bb44`
- `0x180013c58`
- `0x180013fa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013c7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ccb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013d9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013e04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013c89`
- `CFGMGR32!SwDeviceClose` at `0x180013d27`
- `CFGMGR32!SwDeviceClose` at `0x180013d27`
- `CFGMGR32!SwDeviceSetAttributes` at `0x180013d1e`
- `CFGMGR32!SwDeviceSetAttributes` at `0x180013d1e`
- `CFGMGR32!SwDeviceSetLifetime` at `0x180013ce4`
- `CFGMGR32!SwDeviceSetLifetime` at `0x180013ce4`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180013d91`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180013d91`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180013dfa`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180013dfa`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180013e46`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180013e46`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x180013d46`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x180013d46`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180013de7`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180013de7`

## pseudocode

```c
__int64 __fastcall DeviceObject::Uninstall(DeviceObject *this)
{
  signed int v2; // ebx
  __int64 v3; // rsi
  int v4; // eax
  char v5; // r15
  const unsigned __int16 *v7; // rdx
  HDEVINFO DeviceInfoList; // rdi
  signed int LastError; // eax
  const WCHAR *v10; // rdx
  signed int v11; // eax
  signed int v12; // eax
  HKEY v14; // [rsp+30h] [rbp-48h] BYREF
  _SP_CLASSINSTALL_HEADER ClassInstallParams[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+48h] [rbp-30h] BYREF

  v2 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  ++*((_DWORD *)this + 23);
  *((_DWORD *)this + 22) = GetCurrentThreadId();
  if ( *((_DWORD *)this + 6) == 2 )
  {
    v3 = 0;
    v4 = 3;
    v5 = 0;
  }
  else
  {
    v3 = *((_QWORD *)this + 2);
    v5 = 1;
    *((_QWORD *)this + 2) = 0;
    v4 = 4;
  }
  *((_DWORD *)this + 6) = v4;
  if ( (*((_DWORD *)this + 23))-- == 1 )
    *((_DWORD *)this + 22) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  if ( v5 )
  {
    if ( v3 )
    {
      SwDeviceSetLifetime(v3, 0);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
      {
        v14 = HKEY_LOCAL_MACHINE;
        if ( PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(&v14, v7, L"WindowsProtectedPrintMode") )
          SwDeviceSetAttributes(v3, 1);
      }
      SwDeviceClose(v3);
    }
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    *(_OWORD *)&ClassInstallParams[0].cbSize = 0;
    DeviceInfoList = SetupDiCreateDeviceInfoListExW(0, 0, 0, 0);
    if ( DeviceInfoList != (HDEVINFO)-1LL )
      goto LABEL_16;
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( !v2 )
    {
LABEL_16:
      v10 = (const WCHAR *)*((_QWORD *)this + 5);
      DeviceInfoData.cbSize = 32;
      if ( SetupDiOpenDeviceInfoW(DeviceInfoList, v10, 0, 2u, &DeviceInfoData) )
      {
LABEL_22:
        ClassInstallParams[0].cbSize = 8;
        ClassInstallParams[0].InstallFunction = 5;
        ClassInstallParams[1] = (_SP_CLASSINSTALL_HEADER)1LL;
        if ( !SetupDiSetClassInstallParamsW(DeviceInfoList, &DeviceInfoData, ClassInstallParams, 0x10u)
          || !SetupDiCallClassInstaller(5u, DeviceInfoList, &DeviceInfoData) )
        {
          v2 = GetLastError();
          if ( (v2 & 0xE0000000) == 0xE0000000 )
          {
            v2 = (unsigned __int16)v2 | 0x800F0000;
          }
          else if ( v2 > 0 )
          {
            v2 = (unsigned __int16)v2 | 0x80070000;
          }
        }
        goto LABEL_29;
      }
      v11 = GetLastError();
      v2 = v11;
      if ( v11 > 0 )
        v2 = (unsigned __int16)v11 | 0x80070000;
    }
    if ( v2 == -536870389 || v2 == -2147024883 )
    {
      v2 = 0;
    }
    else if ( v2 >= 0 )
    {
      goto LABEL_22;
    }
LABEL_29:
    v12 = 0;
    if ( v2 != -536870389 )
      v12 = v2;
    v2 = v12;
    if ( DeviceInfoList != (HDEVINFO)-1LL )
      SetupDiDestroyDeviceInfoList(DeviceInfoList);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180013c58  push    rbp
0x180013c5a  push    rbx
0x180013c5b  push    rsi
0x180013c5c  push    rdi
0x180013c5d  push    r14
0x180013c5f  push    r15
0x180013c61  mov     rbp, rsp
0x180013c64  sub     rsp, 78h
0x180013c68  mov     rax, cs:__security_cookie
0x180013c6f  xor     rax, rsp
0x180013c72  mov     [rbp+var_10], rax
0x180013c76  mov     r14, rcx
0x180013c79  xor     ebx, ebx
0x180013c7b  add     rcx, 30h ; '0'; lpCriticalSection
0x180013c7f  call    cs:__imp_EnterCriticalSection
0x180013c85  inc     dword ptr [r14+5Ch]
0x180013c89  call    cs:__imp_GetCurrentThreadId
0x180013c8f  mov     [r14+58h], eax
0x180013c93  cmp     dword ptr [r14+18h], 2
0x180013c98  jnz     short loc_180013CA4
0x180013c9a  xor     esi, esi
0x180013c9c  lea     eax, [rbx+3]
0x180013c9f  xor     r15b, r15b
0x180013ca2  jmp     short loc_180013CB4
0x180013ca4  mov     rsi, [r14+10h]
0x180013ca8  mov     r15b, 1
0x180013cab  mov     [r14+10h], rbx
0x180013caf  mov     eax, 4
0x180013cb4  mov     [r14+18h], eax
0x180013cb8  add     dword ptr [r14+5Ch], 0FFFFFFFFh
0x180013cbd  mov     eax, [r14+5Ch]
0x180013cc1  jnz     short loc_180013CC7
0x180013cc3  mov     [r14+58h], ebx
0x180013cc7  lea     rcx, [r14+30h]; lpCriticalSection
0x180013ccb  call    cs:__imp_LeaveCriticalSection
0x180013cd1  test    r15b, r15b
0x180013cd4  jz      loc_180013E4C
0x180013cda  test    rsi, rsi
0x180013cdd  jz      short loc_180013D2D
0x180013cdf  xor     edx, edx
0x180013ce1  mov     rcx, rsi
0x180013ce4  call    cs:__imp_SwDeviceSetLifetime
0x180013cea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180013cf1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180013cf6  test    al, al
0x180013cf8  jz      short loc_180013D24
0x180013cfa  lea     r8, aWindowsprotect; "WindowsProtectedPrintMode"
0x180013d01  mov     [rbp+var_48], 0FFFFFFFF80000002h
0x180013d09  lea     rcx, [rbp+var_48]; HKEY *
0x180013d0d  call    ?_GetRegDwordValueNoThrow@WindowsProtectedPrintHelpers@PrintCore@@CAKAEBQEAUHKEY__@@PEBG1@Z; PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(HKEY__ * const &,ushort const *,ushort const *)
0x180013d12  test    eax, eax
0x180013d14  jz      short loc_180013D24
0x180013d16  mov     edx, 1
0x180013d1b  mov     rcx, rsi
0x180013d1e  call    cs:__imp_SwDeviceSetAttributes
0x180013d24  mov     rcx, rsi
0x180013d27  call    cs:__imp_SwDeviceClose
0x180013d2d  xorps   xmm0, xmm0
0x180013d30  xor     r9d, r9d; Reserved
0x180013d33  xor     r8d, r8d; MachineName
0x180013d36  xor     edx, edx; hwndParent
0x180013d38  xor     ecx, ecx; ClassGuid
0x180013d3a  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x180013d3e  movups  xmmword ptr [rbp+var_30.ClassGuid.Data4+4], xmm0
0x180013d42  movups  xmmword ptr [rbp+ClassInstallParams.cbSize], xmm0
0x180013d46  call    cs:__imp_SetupDiCreateDeviceInfoListExW
0x180013d4c  mov     rdi, rax
0x180013d4f  mov     r15d, 80070000h
0x180013d55  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013d59  jnz     short loc_180013D71
0x180013d5b  call    cs:__imp_GetLastError
0x180013d61  mov     ebx, eax
0x180013d63  test    eax, eax
0x180013d65  jle     short loc_180013D6D
0x180013d67  movzx   ebx, ax
0x180013d6a  or      ebx, r15d
0x180013d6d  test    ebx, ebx
0x180013d6f  jnz     short loc_180013DAD
0x180013d71  mov     rdx, [r14+28h]; DeviceInstanceId
0x180013d75  lea     rax, [rbp+var_30]
0x180013d79  mov     r9d, 2; OpenFlags
0x180013d7f  mov     [rsp+78h+DeviceInfoData], rax; DeviceInfoData
0x180013d84  xor     r8d, r8d; hwndParent
0x180013d87  mov     [rbp+var_30.cbSize], 20h ; ' '
0x180013d8e  mov     rcx, rdi; DeviceInfoSet
0x180013d91  call    cs:__imp_SetupDiOpenDeviceInfoW
0x180013d97  test    eax, eax
0x180013d99  jnz     short loc_180013DC1
0x180013d9b  call    cs:__imp_GetLastError
0x180013da1  mov     ebx, eax
0x180013da3  test    eax, eax
0x180013da5  jle     short loc_180013DAD
0x180013da7  movzx   ebx, ax
0x180013daa  or      ebx, r15d
0x180013dad  cmp     ebx, 0E000020Bh
0x180013db3  jz      short loc_180013E22
0x180013db5  cmp     ebx, 8007000Dh
0x180013dbb  jz      short loc_180013E22
0x180013dbd  test    ebx, ebx
0x180013dbf  js      short loc_180013E30
0x180013dc1  mov     esi, 5
0x180013dc6  mov     [rbp+ClassInstallParams.cbSize], 8
0x180013dcd  lea     r8, [rbp+ClassInstallParams]; ClassInstallParams
0x180013dd1  mov     [rbp+ClassInstallParams.InstallFunction], esi
0x180013dd4  lea     rdx, [rbp+var_30]; DeviceInfoData
0x180013dd8  mov     qword ptr [rbp+ClassInstallParams.cbSize+8], 1
0x180013de0  mov     rcx, rdi; DeviceInfoSet
0x180013de3  lea     r9d, [rsi+0Bh]; ClassInstallParamsSize
0x180013de7  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180013ded  test    eax, eax
0x180013def  jz      short loc_180013E04
0x180013df1  lea     r8, [rbp+var_30]; DeviceInfoData
0x180013df5  mov     rdx, rdi; DeviceInfoSet
0x180013df8  mov     ecx, esi; InstallFunction
0x180013dfa  call    cs:__imp_SetupDiCallClassInstaller
0x180013e00  test    eax, eax
0x180013e02  jnz     short loc_180013E30
0x180013e04  call    cs:__imp_GetLastError
0x180013e0a  mov     ecx, 0E0000000h
0x180013e0f  mov     ebx, eax
0x180013e11  and     eax, ecx
0x180013e13  cmp     eax, ecx
0x180013e15  jnz     short loc_180013E26
0x180013e17  movzx   ebx, bx
0x180013e1a  or      ebx, 800F0000h
0x180013e20  jmp     short loc_180013E30
0x180013e22  xor     ebx, ebx
0x180013e24  jmp     short loc_180013E30
0x180013e26  test    ebx, ebx
0x180013e28  jle     short loc_180013E30
0x180013e2a  movzx   ebx, bx
0x180013e2d  or      ebx, r15d
0x180013e30  xor     eax, eax
0x180013e32  cmp     ebx, 0E000020Bh
0x180013e38  cmovnz  eax, ebx
0x180013e3b  mov     ebx, eax
0x180013e3d  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180013e41  jz      short loc_180013E4C
0x180013e43  mov     rcx, rdi; DeviceInfoSet
0x180013e46  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180013e4c  mov     eax, ebx
0x180013e4e  mov     rcx, [rbp+var_10]
0x180013e52  xor     rcx, rsp; StackCookie
0x180013e55  call    __security_check_cookie
0x180013e5a  add     rsp, 78h
0x180013e5e  pop     r15
0x180013e60  pop     r14
0x180013e62  pop     rdi
0x180013e63  pop     rsi
0x180013e64  pop     rbx
0x180013e65  pop     rbp
0x180013e66  retn
```
