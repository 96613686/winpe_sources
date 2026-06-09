# CGroupPolicy::SetDeviceSecurityAndRestart(void *,_SP_DEVINFO_DATA *,void *,ulong,int,CGroupPolicy::TriState,int *)

- ea: `0x180010e24`
- end: `0x180010f57`
- name: `?SetDeviceSecurityAndRestart@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@0KHW4TriState@1@PEAH@Z`
- size: `307`
- prototype: `__int64 __fastcall(__int64, void *, struct _SP_DEVINFO_DATA *, const BYTE *, DWORD, int, int, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000eda4`
- `0x18000f390`

## callees

- `0x180002fa0`
- `0x180010bc0`
- `0x180010e24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e9a`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x180010ef4`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x180010ef4`
- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x180010e8e`
- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x180010e8e`

## string_xrefs

- `0x180010e54`: `Will set security %p (%d)\n`
- `0x180010ea3`: `Failed (%d) to set security\n`
- `0x180010eb6`: `Set new security for the device\n`
- `0x180010f31`: `Will attempt to restart device\n`

## pseudocode

```c
__int64 __fastcall CGroupPolicy::SetDeviceSecurityAndRestart(
        __int64 a1,
        void *a2,
        struct _SP_DEVINFO_DATA *a3,
        const BYTE *a4,
        DWORD a5,
        int a6,
        int a7,
        int *a8)
{
  DWORD PropertyBufferSize; // edi
  unsigned __int64 v9; // rbx
  unsigned int v12; // ebx
  DWORD LastError; // eax
  DEVINST DevInst; // r8d
  CGroupPolicy *v16; // rcx
  ULONG pulStatus; // [rsp+50h] [rbp+8h] BYREF
  int v18; // [rsp+54h] [rbp+Ch]
  ULONG pulProblemNumber; // [rsp+68h] [rbp+20h] BYREF

  v18 = HIDWORD(a1);
  PropertyBufferSize = a5;
  v9 = (unsigned __int64)a4;
  pulStatus = 0;
  pulProblemNumber = 0;
  GPDebugPrintX(8, "Will set security %p (%d)\n", a4, a5);
  if ( v9 )
    v9 &= -(__int64)(PropertyBufferSize != 0);
  else
    PropertyBufferSize = 0;
  v12 = SetupDiSetDeviceRegistryPropertyW(a2, a3, 0x17u, (const BYTE *)v9, PropertyBufferSize);
  if ( !v12 )
  {
    LastError = GetLastError();
    GPDebugPrintX(2, "Failed (%d) to set security\n", LastError);
    return 0;
  }
  GPDebugPrintX(8, "Set new security for the device\n");
  if ( !a7 )
  {
    DevInst = a3->DevInst;
    pulStatus = 0;
    pulProblemNumber = 0;
    if ( CM_Get_DevNode_Status_Ex(&pulStatus, &pulProblemNumber, DevInst, 0, 0) || (pulStatus & 8) == 0 )
      goto LABEL_9;
LABEL_12:
    if ( a6 )
    {
      GPDebugPrintX(8, "Will attempt to restart device\n");
      CGroupPolicy::RestartDeviceWithNewAccessRights(v16, a2, a3, a8);
    }
    return v12;
  }
  if ( a7 == 2 )
    goto LABEL_12;
LABEL_9:
  GPDebugPrintX(8, "Device is not connected.\n");
  return v12;
}

```

## disassembly

```asm
0x180010e24  mov     rax, rsp
0x180010e27  mov     [rax+10h], rbx
0x180010e2b  mov     [rax+8], rcx
0x180010e2f  push    rbp
0x180010e30  push    rsi
0x180010e31  push    rdi
0x180010e32  sub     rsp, 30h
0x180010e36  mov     edi, [rsp+48h+arg_20]
0x180010e3a  mov     rbx, r9
0x180010e3d  mov     rsi, r8
0x180010e40  mov     dword ptr [rax+8], 0
0x180010e47  mov     rbp, rdx
0x180010e4a  mov     dword ptr [rax+20h], 0
0x180010e51  mov     r8, rbx
0x180010e54  lea     rdx, aWillSetSecurit; "Will set security %p (%d)\n"
0x180010e5b  mov     r9d, edi
0x180010e5e  mov     ecx, 8; unsigned int
0x180010e63  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010e68  test    rbx, rbx
0x180010e6b  jnz     short loc_180010E71
0x180010e6d  xor     edi, edi
0x180010e6f  jmp     short loc_180010E7B
0x180010e71  mov     eax, edi
0x180010e73  neg     eax
0x180010e75  sbb     rcx, rcx
0x180010e78  and     rbx, rcx
0x180010e7b  mov     r9, rbx; PropertyBuffer
0x180010e7e  mov     [rsp+48h+PropertyBufferSize], edi; PropertyBufferSize
0x180010e82  mov     r8d, 17h; Property
0x180010e88  mov     rdx, rsi; DeviceInfoData
0x180010e8b  mov     rcx, rbp; DeviceInfoSet
0x180010e8e  call    cs:__imp_SetupDiSetDeviceRegistryPropertyW
0x180010e94  mov     ebx, eax
0x180010e96  test    eax, eax
0x180010e98  jnz     short loc_180010EB6
0x180010e9a  call    cs:__imp_GetLastError
0x180010ea0  mov     r8d, eax
0x180010ea3  lea     rdx, aFailedDToSetSe; "Failed (%d) to set security\n"
0x180010eaa  lea     ecx, [rbx+2]; unsigned int
0x180010ead  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010eb2  xor     eax, eax
0x180010eb4  jmp     short loc_180010F18
0x180010eb6  lea     rdx, aSetNewSecurity; "Set new security for the device\n"
0x180010ebd  mov     ecx, 8; unsigned int
0x180010ec2  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010ec7  mov     eax, [rsp+48h+arg_30]
0x180010ece  test    eax, eax
0x180010ed0  jnz     short loc_180010F25
0x180010ed2  mov     r8d, [rsi+14h]; dnDevInst
0x180010ed6  lea     rdx, [rsp+48h+pulProblemNumber]; pulProblemNumber
0x180010edb  xor     r9d, r9d; ulFlags
0x180010ede  mov     [rsp+48h+pulStatus], eax
0x180010ee2  lea     rcx, [rsp+48h+pulStatus]; pulStatus
0x180010ee7  mov     [rsp+48h+pulProblemNumber], eax
0x180010eeb  mov     qword ptr [rsp+48h+PropertyBufferSize], 0; hMachine
0x180010ef4  call    cs:__imp_CM_Get_DevNode_Status_Ex
0x180010efa  test    eax, eax
0x180010efc  jnz     short loc_180010F05
0x180010efe  test    byte ptr [rsp+48h+pulStatus], 8
0x180010f03  jnz     short loc_180010F2A
0x180010f05  lea     rdx, aDeviceIsNotCon; "Device is not connected.\n"
0x180010f0c  mov     ecx, 8; unsigned int
0x180010f11  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010f16  mov     eax, ebx
0x180010f18  mov     rbx, [rsp+48h+arg_8]
0x180010f1d  add     rsp, 30h
0x180010f21  pop     rdi
0x180010f22  pop     rsi
0x180010f23  pop     rbp
0x180010f24  retn
0x180010f25  cmp     eax, 2
0x180010f28  jnz     short loc_180010F05
0x180010f2a  cmp     [rsp+48h+arg_28], 0
0x180010f2f  jz      short loc_180010F16
0x180010f31  lea     rdx, aWillAttemptToR; "Will attempt to restart device\n"
0x180010f38  mov     ecx, 8; unsigned int
0x180010f3d  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x180010f42  mov     r9, [rsp+48h+arg_38]; int *
0x180010f4a  mov     r8, rsi; struct _SP_DEVINFO_DATA *
0x180010f4d  mov     rdx, rbp; void *
0x180010f50  call    ?RestartDeviceWithNewAccessRights@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@PEAH@Z; CGroupPolicy::RestartDeviceWithNewAccessRights(void *,_SP_DEVINFO_DATA *,int *)
0x180010f55  jmp     short loc_180010F16
```
