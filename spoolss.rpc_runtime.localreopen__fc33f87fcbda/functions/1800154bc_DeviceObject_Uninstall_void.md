# DeviceObject::Uninstall(void)

- ea: `0x1800154bc`
- end: `0x180015728`
- name: `?Uninstall@DeviceObject@@QEAAJXZ`
- size: `620`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001329c`
- `0x180015730`

## callees

- `0x180005680`
- `0x18000c4c0`
- `0x1800154bc`
- `0x18001587c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800154e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001553b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001553b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800155e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800156b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800154f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800154f3`
- `CFGMGR32!SwDeviceClose` at `0x1800155a9`
- `CFGMGR32!SwDeviceClose` at `0x1800155a9`
- `CFGMGR32!SwDeviceSetAttributes` at `0x18001559a`
- `CFGMGR32!SwDeviceSetAttributes` at `0x18001559a`
- `CFGMGR32!SwDeviceSetLifetime` at `0x18001555a`
- `CFGMGR32!SwDeviceSetLifetime` at `0x18001555a`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180015625`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x180015625`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800156a8`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800156a8`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180015700`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180015700`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1800155ce`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1800155ce`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18001568f`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18001568f`

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
0x1800154bc  push    rbp
0x1800154be  push    rbx
0x1800154bf  push    rsi
0x1800154c0  push    rdi
0x1800154c1  push    r14
0x1800154c3  push    r15
0x1800154c5  mov     rbp, rsp
0x1800154c8  sub     rsp, 78h
0x1800154cc  mov     rax, cs:__security_cookie
0x1800154d3  xor     rax, rsp
0x1800154d6  mov     [rbp+var_10], rax
0x1800154da  mov     r14, rcx
0x1800154dd  xor     ebx, ebx
0x1800154df  add     rcx, 30h ; '0'; lpCriticalSection
0x1800154e3  call    cs:__imp_EnterCriticalSection
0x1800154ea  nop     dword ptr [rax+rax+00h]
0x1800154ef  inc     dword ptr [r14+5Ch]
0x1800154f3  call    cs:__imp_GetCurrentThreadId
0x1800154fa  nop     dword ptr [rax+rax+00h]
0x1800154ff  mov     [r14+58h], eax
0x180015503  cmp     dword ptr [r14+18h], 2
0x180015508  jnz     short loc_180015514
0x18001550a  xor     esi, esi
0x18001550c  lea     eax, [rbx+3]
0x18001550f  xor     r15b, r15b
0x180015512  jmp     short loc_180015524
0x180015514  mov     rsi, [r14+10h]
0x180015518  mov     r15b, 1
0x18001551b  mov     [r14+10h], rbx
0x18001551f  mov     eax, 4
0x180015524  mov     [r14+18h], eax
0x180015528  add     dword ptr [r14+5Ch], 0FFFFFFFFh
0x18001552d  mov     eax, [r14+5Ch]
0x180015531  jnz     short loc_180015537
0x180015533  mov     [r14+58h], ebx
0x180015537  lea     rcx, [r14+30h]; lpCriticalSection
0x18001553b  call    cs:__imp_LeaveCriticalSection
0x180015542  nop     dword ptr [rax+rax+00h]
0x180015547  test    r15b, r15b
0x18001554a  jz      loc_18001570C
0x180015550  test    rsi, rsi
0x180015553  jz      short loc_1800155B5
0x180015555  xor     edx, edx
0x180015557  mov     rcx, rsi
0x18001555a  call    cs:__imp_SwDeviceSetLifetime
0x180015561  nop     dword ptr [rax+rax+00h]
0x180015566  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x18001556d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180015572  test    al, al
0x180015574  jz      short loc_1800155A6
0x180015576  lea     r8, aWindowsprotect; "WindowsProtectedPrintMode"
0x18001557d  mov     [rbp+var_48], 0FFFFFFFF80000002h
0x180015585  lea     rcx, [rbp+var_48]; HKEY *
0x180015589  call    ?_GetRegDwordValueNoThrow@WindowsProtectedPrintHelpers@PrintCore@@CAKAEBQEAUHKEY__@@PEBG1@Z; PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(HKEY__ * const &,ushort const *,ushort const *)
0x18001558e  test    eax, eax
0x180015590  jz      short loc_1800155A6
0x180015592  mov     edx, 1
0x180015597  mov     rcx, rsi
0x18001559a  call    cs:__imp_SwDeviceSetAttributes
0x1800155a1  nop     dword ptr [rax+rax+00h]
0x1800155a6  mov     rcx, rsi
0x1800155a9  call    cs:__imp_SwDeviceClose
0x1800155b0  nop     dword ptr [rax+rax+00h]
0x1800155b5  xorps   xmm0, xmm0
0x1800155b8  xor     r9d, r9d; Reserved
0x1800155bb  xor     r8d, r8d; MachineName
0x1800155be  xor     edx, edx; hwndParent
0x1800155c0  xor     ecx, ecx; ClassGuid
0x1800155c2  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x1800155c6  movups  xmmword ptr [rbp+var_30.ClassGuid.Data4+4], xmm0
0x1800155ca  movups  xmmword ptr [rbp+ClassInstallParams.cbSize], xmm0
0x1800155ce  call    cs:__imp_SetupDiCreateDeviceInfoListExW
0x1800155d5  nop     dword ptr [rax+rax+00h]
0x1800155da  mov     rdi, rax
0x1800155dd  mov     r15d, 80070000h
0x1800155e3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800155e7  jnz     short loc_180015605
0x1800155e9  call    cs:__imp_GetLastError
0x1800155f0  nop     dword ptr [rax+rax+00h]
0x1800155f5  mov     ebx, eax
0x1800155f7  test    eax, eax
0x1800155f9  jle     short loc_180015601
0x1800155fb  movzx   ebx, ax
0x1800155fe  or      ebx, r15d
0x180015601  test    ebx, ebx
0x180015603  jnz     short loc_18001564D
0x180015605  mov     rdx, [r14+28h]; DeviceInstanceId
0x180015609  lea     rax, [rbp+var_30]
0x18001560d  mov     r9d, 2; OpenFlags
0x180015613  mov     [rsp+78h+DeviceInfoData], rax; DeviceInfoData
0x180015618  xor     r8d, r8d; hwndParent
0x18001561b  mov     [rbp+var_30.cbSize], 20h ; ' '
0x180015622  mov     rcx, rdi; DeviceInfoSet
0x180015625  call    cs:__imp_SetupDiOpenDeviceInfoW
0x18001562c  nop     dword ptr [rax+rax+00h]
0x180015631  test    eax, eax
0x180015633  jnz     short loc_180015669
0x180015635  call    cs:__imp_GetLastError
0x18001563c  nop     dword ptr [rax+rax+00h]
0x180015641  mov     ebx, eax
0x180015643  test    eax, eax
0x180015645  jle     short loc_18001564D
0x180015647  movzx   ebx, ax
0x18001564a  or      ebx, r15d
0x18001564d  cmp     ebx, 0E000020Bh
0x180015653  jz      loc_1800156DC
0x180015659  cmp     ebx, 8007000Dh
0x18001565f  jz      short loc_1800156DC
0x180015661  test    ebx, ebx
0x180015663  js      loc_1800156EA
0x180015669  mov     esi, 5
0x18001566e  mov     [rbp+ClassInstallParams.cbSize], 8
0x180015675  lea     r8, [rbp+ClassInstallParams]; ClassInstallParams
0x180015679  mov     [rbp+ClassInstallParams.InstallFunction], esi
0x18001567c  lea     rdx, [rbp+var_30]; DeviceInfoData
0x180015680  mov     qword ptr [rbp+ClassInstallParams.cbSize+8], 1
0x180015688  mov     rcx, rdi; DeviceInfoSet
0x18001568b  lea     r9d, [rsi+0Bh]; ClassInstallParamsSize
0x18001568f  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180015696  nop     dword ptr [rax+rax+00h]
0x18001569b  test    eax, eax
0x18001569d  jz      short loc_1800156B8
0x18001569f  lea     r8, [rbp+var_30]; DeviceInfoData
0x1800156a3  mov     rdx, rdi; DeviceInfoSet
0x1800156a6  mov     ecx, esi; InstallFunction
0x1800156a8  call    cs:__imp_SetupDiCallClassInstaller
0x1800156af  nop     dword ptr [rax+rax+00h]
0x1800156b4  test    eax, eax
0x1800156b6  jnz     short loc_1800156EA
0x1800156b8  call    cs:__imp_GetLastError
0x1800156bf  nop     dword ptr [rax+rax+00h]
0x1800156c4  mov     ecx, 0E0000000h
0x1800156c9  mov     ebx, eax
0x1800156cb  and     eax, ecx
0x1800156cd  cmp     eax, ecx
0x1800156cf  jnz     short loc_1800156E0
0x1800156d1  movzx   ebx, bx
0x1800156d4  or      ebx, 800F0000h
0x1800156da  jmp     short loc_1800156EA
0x1800156dc  xor     ebx, ebx
0x1800156de  jmp     short loc_1800156EA
0x1800156e0  test    ebx, ebx
0x1800156e2  jle     short loc_1800156EA
0x1800156e4  movzx   ebx, bx
0x1800156e7  or      ebx, r15d
0x1800156ea  xor     eax, eax
0x1800156ec  cmp     ebx, 0E000020Bh
0x1800156f2  cmovnz  eax, ebx
0x1800156f5  mov     ebx, eax
0x1800156f7  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800156fb  jz      short loc_18001570C
0x1800156fd  mov     rcx, rdi; DeviceInfoSet
0x180015700  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180015707  nop     dword ptr [rax+rax+00h]
0x18001570c  mov     eax, ebx
0x18001570e  mov     rcx, [rbp+var_10]
0x180015712  xor     rcx, rsp; StackCookie
0x180015715  call    __security_check_cookie
0x18001571a  add     rsp, 78h
0x18001571e  pop     r15
0x180015720  pop     r14
0x180015722  pop     rdi
0x180015723  pop     rsi
0x180015724  pop     rbx
0x180015725  pop     rbp
0x180015726  retn
```
