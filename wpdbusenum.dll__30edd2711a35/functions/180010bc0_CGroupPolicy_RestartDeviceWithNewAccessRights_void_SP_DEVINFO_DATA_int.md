# CGroupPolicy::RestartDeviceWithNewAccessRights(void *,_SP_DEVINFO_DATA *,int *)

- ea: `0x180010bc0`
- end: `0x180010d6d`
- name: `?RestartDeviceWithNewAccessRights@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@PEAH@Z`
- size: `429`
- prototype: `__int64 __fastcall(CGroupPolicy *this, void *, struct _SP_DEVINFO_DATA *, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180010d74`
- `0x180010e24`

## callees

- `0x180002fa0`
- `0x1800097d0`
- `0x18000a192`
- `0x180010bc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ccc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010c9b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010ccc`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180010d3f`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180010d3f`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180010cc2`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180010cc2`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x180010c1d`
- `SETUPAPI!CMP_WaitNoPendingInstallEvents` at `0x180010c1d`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180010c91`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180010c91`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180010c62`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180010c62`

## string_xrefs

- `0x180010cd2`: `Failed (%d) to get install params\n`
- `0x180010ceb`: `START: Install flag 0x%08x, flagex 0x%08x\n`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::RestartDeviceWithNewAccessRights(
        CGroupPolicy *this,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        int *a4)
{
  int v7; // esi
  DWORD v8; // eax
  DWORD LastError; // eax
  DWORD v10; // eax
  DWORD Flags; // ecx
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+20h] [rbp-E0h] BYREF
  int ClassInstallParams_8; // [rsp+28h] [rbp-D8h]
  __int64 ClassInstallParams_12; // [rsp+2Ch] [rbp-D4h]
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+40h] [rbp-C0h] BYREF

  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  v7 = 0;
  CMP_WaitNoPendingInstallEvents(0xFFFFFFFF);
  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  ClassInstallParams.cbSize = 8;
  ClassInstallParams_12 = 2;
  ClassInstallParams.InstallFunction = 18;
  ClassInstallParams_8 = 3;
  if ( SetupDiSetClassInstallParamsW(a2, a3, &ClassInstallParams, 0x14u) )
  {
    if ( SetupDiCallClassInstaller(0x12u, a2, a3) )
    {
      v7 = 1;
    }
    else
    {
      LastError = GetLastError();
      GPDebugPrintX(2, "Failed (%d) to restart the device\n", LastError);
    }
  }
  else
  {
    v8 = GetLastError();
    GPDebugPrintX(2, "Failed (%d) to set stop params\n", v8);
  }
  DeviceInstallParams.cbSize = 584;
  if ( SetupDiGetDeviceInstallParamsW(a2, a3, &DeviceInstallParams) )
  {
    GPDebugPrintX(
      2,
      "START: Install flag 0x%08x, flagex 0x%08x\n",
      DeviceInstallParams.Flags,
      DeviceInstallParams.FlagsEx);
    Flags = DeviceInstallParams.Flags;
    if ( (DeviceInstallParams.Flags & 0x180) != 0 )
      *a4 = 1;
    if ( v7 )
      return 1;
    DeviceInstallParams.Flags = Flags | 0x80;
    GPDebugPrintX(2, "Device needs to be restarted\n");
    SetupDiSetDeviceInstallParamsW(a2, a3, &DeviceInstallParams);
  }
  else
  {
    v10 = GetLastError();
    GPDebugPrintX(2, "Failed (%d) to get install params\n", v10);
  }
  return 0;
}

```

## disassembly

```asm
0x180010bc0  mov     [rsp-8+arg_0], rbx
0x180010bc5  push    rbp
0x180010bc6  push    rsi
0x180010bc7  push    rdi
0x180010bc8  push    r14
0x180010bca  push    r15
0x180010bcc  lea     rbp, [rsp-1A0h]
0x180010bd4  sub     rsp, 2A0h
0x180010bdb  mov     rax, cs:__security_cookie
0x180010be2  xor     rax, rsp
0x180010be5  mov     [rbp+1C0h+var_30], rax
0x180010bec  mov     rdi, r8
0x180010bef  lea     rcx, [rsp+2C0h+DeviceInstallParams]; void *
0x180010bf4  mov     rbx, rdx
0x180010bf7  xorps   xmm0, xmm0
0x180010bfa  xor     eax, eax
0x180010bfc  mov     r15d, 248h
0x180010c02  mov     r8d, r15d; Size
0x180010c05  mov     [rsp+2C0h+var_290], eax
0x180010c09  xor     edx, edx; Val
0x180010c0b  mov     r14, r9
0x180010c0e  movups  xmmword ptr [rsp+2C0h+ClassInstallParams.cbSize], xmm0
0x180010c13  call    memset_0
0x180010c18  or      ecx, 0FFFFFFFFh; dwTimeout
0x180010c1b  xor     esi, esi
0x180010c1d  call    cs:__imp_CMP_WaitNoPendingInstallEvents
0x180010c23  mov     r8d, r15d; Size
0x180010c26  lea     rcx, [rsp+2C0h+DeviceInstallParams]; void *
0x180010c2b  xor     edx, edx; Val
0x180010c2d  call    memset_0
0x180010c32  lea     r15d, [rsi+2]
0x180010c36  mov     [rsp+2C0h+ClassInstallParams.cbSize], 8
0x180010c3e  lea     r9d, [rsi+14h]; ClassInstallParamsSize
0x180010c42  mov     qword ptr [rsp+2C0h+ClassInstallParams.InstallFunction+8], r15
0x180010c47  lea     r8, [rsp+2C0h+ClassInstallParams]; ClassInstallParams
0x180010c4c  mov     [rsp+2C0h+ClassInstallParams.InstallFunction], 12h
0x180010c54  mov     rdx, rdi; DeviceInfoData
0x180010c57  mov     [rsp+2C0h+ClassInstallParams.cbSize+8], 3
0x180010c5f  mov     rcx, rbx; DeviceInfoSet
0x180010c62  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180010c68  test    eax, eax
0x180010c6a  jnz     short loc_180010C86
0x180010c6c  call    cs:__imp_GetLastError
0x180010c72  lea     rdx, aFailedDToSetSt; "Failed (%d) to set stop params\n"
0x180010c79  mov     r8d, eax
0x180010c7c  mov     ecx, r15d; unsigned int
0x180010c7f  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010c84  jmp     short loc_180010CAF
0x180010c86  mov     r8, rdi; DeviceInfoData
0x180010c89  mov     rdx, rbx; DeviceInfoSet
0x180010c8c  mov     ecx, 12h; InstallFunction
0x180010c91  call    cs:__imp_SetupDiCallClassInstaller
0x180010c97  test    eax, eax
0x180010c99  jnz     short loc_180010CAA
0x180010c9b  call    cs:__imp_GetLastError
0x180010ca1  lea     rdx, aFailedDToResta; "Failed (%d) to restart the device\n"
0x180010ca8  jmp     short loc_180010C79
0x180010caa  mov     esi, 1
0x180010caf  lea     r8, [rsp+2C0h+DeviceInstallParams]; DeviceInstallParams
0x180010cb4  mov     [rsp+2C0h+DeviceInstallParams.cbSize], 248h
0x180010cbc  mov     rdx, rdi; DeviceInfoData
0x180010cbf  mov     rcx, rbx; DeviceInfoSet
0x180010cc2  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x180010cc8  test    eax, eax
0x180010cca  jnz     short loc_180010CE6
0x180010ccc  call    cs:__imp_GetLastError
0x180010cd2  lea     rdx, aFailedDToGetIn; "Failed (%d) to get install params\n"
0x180010cd9  mov     ecx, r15d; unsigned int
0x180010cdc  mov     r8d, eax
0x180010cdf  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010ce4  jmp     short loc_180010D45
0x180010ce6  mov     r9d, [rsp+2C0h+DeviceInstallParams.FlagsEx]
0x180010ceb  lea     rdx, aStartInstallFl; "START: Install flag 0x%08x, flagex 0x%0"...
0x180010cf2  mov     r8d, [rsp+2C0h+DeviceInstallParams.Flags]
0x180010cf7  mov     ecx, r15d; unsigned int
0x180010cfa  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010cff  mov     ecx, [rsp+2C0h+DeviceInstallParams.Flags]
0x180010d03  test    ecx, 180h
0x180010d09  jz      short loc_180010D12
0x180010d0b  mov     dword ptr [r14], 1
0x180010d12  test    esi, esi
0x180010d14  jz      short loc_180010D1D
0x180010d16  mov     eax, 1
0x180010d1b  jmp     short loc_180010D47
0x180010d1d  bts     ecx, 7
0x180010d21  lea     rdx, aDeviceNeedsToB; "Device needs to be restarted\n"
0x180010d28  mov     [rsp+2C0h+DeviceInstallParams.Flags], ecx
0x180010d2c  mov     ecx, r15d; unsigned int
0x180010d2f  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010d34  lea     r8, [rsp+2C0h+DeviceInstallParams]; DeviceInstallParams
0x180010d39  mov     rdx, rdi; DeviceInfoData
0x180010d3c  mov     rcx, rbx; DeviceInfoSet
0x180010d3f  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180010d45  xor     eax, eax
0x180010d47  mov     rcx, [rbp+1C0h+var_30]
0x180010d4e  xor     rcx, rsp; StackCookie
0x180010d51  call    __security_check_cookie
0x180010d56  mov     rbx, [rsp+2C0h+arg_0]
0x180010d5e  add     rsp, 2A0h
0x180010d65  pop     r15
0x180010d67  pop     r14
0x180010d69  pop     rdi
0x180010d6a  pop     rsi
0x180010d6b  pop     rbp
0x180010d6c  retn
```
