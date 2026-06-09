# CGroupPolicy::ApplyGroupPolicyForDevices(_GUID *,_ACL *,void *,ulong,int,int,int,int *)

- ea: `0x18000eda4`
- end: `0x18000f388`
- name: `?ApplyGroupPolicyForDevices@CGroupPolicy@@IEAAXPEAU_GUID@@PEAU_ACL@@PEAXKHHHPEAH@Z`
- size: `1508`
- prototype: `void __fastcall(CGroupPolicy *this, struct _GUID *, struct _ACL *, void *, DWORD, int, int, int, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fc24`
- `0x1800106e0`

## callees

- `0x180002fa0`
- `0x1800097d0`
- `0x18000eda4`
- `0x18000fb7c`
- `0x180010644`
- `0x180010e24`
- `0x180014048`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ef3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f0e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f29a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f30a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f347`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f24c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f24c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f17f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000f17f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f106`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f106`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f1ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f1e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f2ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000efa8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f1ad`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f1e9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f2ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000ee46`
- `api-ms-win-security-sddl-l1-1-0!ConvertSecurityDescriptorToStringSecurityDescriptorW` at `0x18000ee46`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000f217`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18000f217`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x18000f018`
- `SETUPAPI!CM_Get_DevNode_Status_Ex` at `0x18000f018`
- `SETUPAPI!SetupDiSetClassPropertyW` at `0x18000ee88`
- `SETUPAPI!SetupDiSetClassPropertyW` at `0x18000ee88`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000efe7`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x18000efe7`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000efc1`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000efc1`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000f0a9`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000f0a9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f0d9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f13e`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f0d9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000f13e`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000f33f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000f33f`

## string_xrefs

- `0x18000f197`: `CreateFile failed (%d) for %ws\n\n`
- `0x18000ee92`: `Unknown security descriptor`
- `0x18000eefc`: `Successfully applied security descriptor <%ws> to device setup class GUID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\n`
- `0x18000ef47`: `Failed (%d) to apply security descriptor <%ws> to device setup class GUID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\n`
- `0x18000f221`: `SetSecurityInfo for device succeeded\n`
- `0x18000f238`: `SetSecurityInfo for device Failed %d\n`

## pseudocode

```c
void __fastcall CGroupPolicy::ApplyGroupPolicyForDevices(
        CGroupPolicy *this,
        struct _GUID *a2,
        struct _ACL *a3,
        void *a4,
        DWORD a5,
        int a6,
        int a7,
        int a8,
        int *a9)
{
  PACL v10; // rsi
  GUID v11; // xmm0
  const struct _GUID *v12; // rdi
  BOOL v13; // eax
  ULONG v14; // edx
  LPWSTR v15; // rsi
  int v16; // r8d
  int v17; // r9d
  int v18; // r10d
  int v19; // r11d
  ULONG Data3; // ebx
  int v21; // r14d
  int v22; // r15d
  int v23; // r13d
  DWORD Data2; // ebx
  unsigned int Data1; // edi
  DWORD LastError; // eax
  HDEVINFO ClassDevsW; // rbx
  DWORD i; // edi
  CGroupPolicy *v29; // rcx
  __int64 v30; // rcx
  int v31; // r13d
  DWORD v32; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v33; // rax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v34; // rsi
  const WCHAR *DevicePath; // r14
  HANDLE FileW; // r15
  DWORD v37; // eax
  __int64 v38; // rcx
  DWORD v39; // eax
  DWORD v40; // eax
  char *v41; // rdx
  unsigned int v42; // ecx
  DWORD v43; // eax
  DWORD v44; // eax
  DWORD v45; // eax
  PULONG StringSecurityDescriptorLen; // [rsp+20h] [rbp-E0h]
  DWORD Flags[2]; // [rsp+28h] [rbp-D8h]
  int v48; // [rsp+80h] [rbp-80h]
  int v49; // [rsp+80h] [rbp-80h]
  ULONG pulStatus; // [rsp+84h] [rbp-7Ch] BYREF
  DWORD RequiredSize; // [rsp+88h] [rbp-78h] BYREF
  ULONG pulProblemNumber; // [rsp+8Ch] [rbp-74h] BYREF
  LPWSTR StringSecurityDescriptor; // [rsp+90h] [rbp-70h] BYREF
  PACL pDacl; // [rsp+98h] [rbp-68h]
  ULONG v55; // [rsp+A0h] [rbp-60h] BYREF
  int v56; // [rsp+A4h] [rbp-5Ch]
  int v57; // [rsp+A8h] [rbp-58h]
  int v58; // [rsp+ACh] [rbp-54h]
  int *v59; // [rsp+B0h] [rbp-50h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+B8h] [rbp-48h] BYREF
  GUID ClassGuid; // [rsp+D8h] [rbp-28h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+E8h] [rbp-18h] BYREF

  pDacl = a3;
  v59 = a9;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  v10 = a3;
  RequiredSize = 0;
  v11 = *a2;
  StringSecurityDescriptor = 0;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v55 = 0;
  ClassGuid = v11;
  v12 = CGroupPolicy::MapDevInterfaceGUIDToDevClassGUID(this, a2);
  if ( v12 && a8 )
  {
    if ( !ConvertSecurityDescriptorToStringSecurityDescriptorW(a4, 1u, 4u, &StringSecurityDescriptor, &v55) )
      StringSecurityDescriptor = 0;
    if ( a4 )
      v13 = SetupDiSetClassPropertyW(v12, &DEVPKEY_DeviceClass_Security, 0x13u, (const PBYTE)a4, a5, 1u);
    else
      v13 = SetupDiSetClassPropertyW(v12, &DEVPKEY_DeviceClass_Security, 0, 0, 0, 1u);
    v14 = v12->Data4[4];
    v15 = L"Unknown security descriptor";
    v16 = v12->Data4[3];
    v17 = v12->Data4[2];
    v18 = v12->Data4[1];
    v19 = v12->Data4[0];
    Data3 = v12->Data3;
    v21 = v12->Data4[7];
    v22 = v12->Data4[6];
    v23 = v12->Data4[5];
    pulStatus = v14;
    v48 = v16;
    v56 = v17;
    v57 = v18;
    v58 = v19;
    pulProblemNumber = Data3;
    if ( v13 )
    {
      if ( StringSecurityDescriptor )
        v15 = StringSecurityDescriptor;
      Flags[0] = Data3;
      LODWORD(StringSecurityDescriptorLen) = v12->Data2;
      GPDebugPrintX(
        8u,
        "Successfully applied security descriptor <%ws> to device setup class GUID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\n",
        v15,
        v12->Data1,
        StringSecurityDescriptorLen,
        *(_QWORD *)Flags,
        v19,
        v18,
        v17,
        v16,
        v14,
        v23,
        v22,
        v21);
    }
    else
    {
      Data2 = v12->Data2;
      Data1 = v12->Data1;
      if ( StringSecurityDescriptor )
        v15 = StringSecurityDescriptor;
      LastError = GetLastError();
      Flags[0] = Data2;
      LODWORD(StringSecurityDescriptorLen) = Data1;
      GPDebugPrintX(
        2u,
        "Failed (%d) to apply security descriptor <%ws> to device setup class GUID {%08x-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}\n",
        LastError,
        v15,
        StringSecurityDescriptorLen,
        *(_QWORD *)Flags,
        pulProblemNumber,
        v58,
        v57,
        v56,
        v48,
        pulStatus,
        v23,
        v22,
        v21);
    }
    if ( StringSecurityDescriptor )
      LocalFree(StringSecurityDescriptor);
    v10 = pDacl;
  }
  ClassDevsW = SetupDiGetClassDevsW(&ClassGuid, 0, 0, 0x10u);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    v45 = GetLastError();
    GPDebugPrintX(2u, "SetupDiGetClassDevs failed. Error %d\n", v45);
    return;
  }
  for ( i = 0; ; ++i )
  {
    DeviceInfoData.cbSize = 32;
    if ( !SetupDiEnumDeviceInfo(ClassDevsW, i, &DeviceInfoData) )
      break;
    pulStatus = 0;
    pulProblemNumber = 0;
    v49 = 1;
    if ( !CM_Get_DevNode_Status_Ex(&pulStatus, &pulProblemNumber, DeviceInfoData.DevInst, 0, 0) && (pulStatus & 8) != 0 )
    {
      v49 = 2;
      if ( a6 )
      {
        if ( v10 )
          WPDLibLogDeviceAccessEnforcementForUserSessions(v29, ClassDevsW, &DeviceInfoData, v10, a7);
      }
    }
    if ( a8 && CGroupPolicy::CheckIfSecurityShouldBeSet(v29, ClassDevsW, &DeviceInfoData, (unsigned __int8 *)a4, a5) )
    {
      v31 = 1;
      if ( v10 )
      {
        DeviceInterfaceData.cbSize = 32;
        if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &ClassGuid, i, &DeviceInterfaceData) )
        {
          v43 = GetLastError();
          if ( v43 == 259 )
          {
            v41 = "Enumerated all interfaces successfully\n";
LABEL_53:
            v42 = 8;
            goto LABEL_47;
          }
          GPDebugPrintX(2u, "SetupDiEnumDeviceInterfaces failed (%d) for index %d\n", v43, i);
          goto LABEL_55;
        }
        DeviceInfoData.cbSize = 32;
        if ( SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
          goto LABEL_46;
        v32 = GetLastError();
        if ( v32 != 122 || !RequiredSize )
        {
          GPDebugPrintX(2u, "SetupDiGetDeviceInterfaceDetail failed (%d)\n", v32);
          goto LABEL_55;
        }
        v33 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)LocalAlloc(0x40u, RequiredSize);
        v34 = v33;
        if ( !v33 )
        {
LABEL_46:
          v41 = "Failed to allocate memory for device detail\n";
          v42 = 2;
LABEL_47:
          GPDebugPrintX(v42, v41);
          goto LABEL_55;
        }
        DevicePath = v33->DevicePath;
        v33->cbSize = 8;
        v33->DevicePath[0] = 0;
        if ( !SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, v33, RequiredSize, 0, 0) )
        {
          v40 = GetLastError();
          GPDebugPrintX(2u, "SetupDiGetDeviceInterfaceDetail failed (%d) for index %d\n", v40, i);
          LocalFree(v34);
          goto LABEL_55;
        }
        GPDebugPrintX(8u, "Device interface name %ws\n", DevicePath);
        FileW = CreateFileW(DevicePath, 0x1F01FFu, 3u, 0, 3u, 0, 0);
        if ( FileW == (HANDLE)-1LL )
        {
          v37 = GetLastError();
          GPDebugPrintX(2u, "CreateFile failed (%d) for %ws\n\n", v37, DevicePath);
          LocalFree(v34);
          CGroupPolicy::SetDeviceSecurityAndRestart(v38, ClassDevsW, &DeviceInfoData, a4, a5, 1, v49, v59);
LABEL_42:
          AccessCode = 2;
          goto LABEL_43;
        }
        LocalFree(v34);
        v39 = SetSecurityInfo(FileW, SE_FILE_OBJECT, 4u, 0, 0, pDacl, 0);
        if ( v39 )
        {
          GPDebugPrintX(2u, "SetSecurityInfo for device Failed %d\n", v39);
        }
        else
        {
          GPDebugPrintX(8u, "SetSecurityInfo for device succeeded\n");
          v31 = 0;
        }
        CloseHandle(FileW);
      }
      CGroupPolicy::SetDeviceSecurityAndRestart(v30, ClassDevsW, &DeviceInfoData, a4, a5, v31, v49, v59);
      if ( !v31 )
        goto LABEL_43;
      goto LABEL_42;
    }
LABEL_43:
    v10 = pDacl;
  }
  v44 = GetLastError();
  if ( v44 == 259 )
  {
    v41 = "Enumerated all devices successfully\n";
    goto LABEL_53;
  }
  GPDebugPrintX(2u, "SetupDiEnumDeviceInfo failed (%d) for index %d\n", v44, i);
LABEL_55:
  SetupDiDestroyDeviceInfoList(ClassDevsW);
}

```

## disassembly

```asm
0x18000eda4  mov     [rsp-8+arg_0], rbx
0x18000eda9  push    rbp
0x18000edaa  push    rsi
0x18000edab  push    rdi
0x18000edac  push    r12
0x18000edae  push    r13
0x18000edb0  push    r14
0x18000edb2  push    r15
0x18000edb4  lea     rbp, [rsp-10h]
0x18000edb9  sub     rsp, 110h
0x18000edc0  mov     rax, cs:__security_cookie
0x18000edc7  xor     rax, rsp
0x18000edca  mov     [rbp+40h+var_38], rax
0x18000edce  mov     rax, [rbp+40h+arg_40]
0x18000edd5  xorps   xmm0, xmm0
0x18000edd8  xor     r15d, r15d
0x18000eddb  mov     [rbp+40h+pDacl], r8
0x18000eddf  xorps   xmm1, xmm1
0x18000ede2  mov     [rbp+40h+var_90], rax
0x18000ede6  movups  xmmword ptr [rbp+40h+DeviceInterfaceData.cbSize], xmm0
0x18000edea  mov     r12, r9
0x18000eded  mov     rsi, r8
0x18000edf0  movups  xmmword ptr [rbp+40h+DeviceInterfaceData.InterfaceClassGuid.Data4+4], xmm0
0x18000edf4  mov     [rbp+40h+RequiredSize], r15d
0x18000edf8  movups  xmm0, xmmword ptr [rdx]
0x18000edfb  mov     [rbp+40h+StringSecurityDescriptor], r15
0x18000edff  movups  xmmword ptr [rbp+40h+DeviceInfoData.cbSize], xmm1
0x18000ee03  mov     [rbp+40h+var_A0], r15d
0x18000ee07  movdqu  xmmword ptr [rbp+40h+ClassGuid.Data1], xmm0
0x18000ee0c  movups  xmmword ptr [rbp+40h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x18000ee10  call    ?MapDevInterfaceGUIDToDevClassGUID@CGroupPolicy@@IEAAPEBU_GUID@@PEAU2@@Z; CGroupPolicy::MapDevInterfaceGUIDToDevClassGUID(_GUID *)
0x18000ee15  mov     rdi, rax
0x18000ee18  test    rax, rax
0x18000ee1b  jz      loc_18000EFB2
0x18000ee21  cmp     [rbp+40h+arg_38], r15d
0x18000ee28  jz      loc_18000EFB2
0x18000ee2e  lea     rax, [rbp+40h+var_A0]
0x18000ee32  mov     rcx, r12; SecurityDescriptor
0x18000ee35  lea     r9, [rbp+40h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18000ee39  mov     [rsp+140h+StringSecurityDescriptorLen], rax; StringSecurityDescriptorLen
0x18000ee3e  lea     edx, [r15+1]; RequestedStringSDRevision
0x18000ee42  lea     r8d, [r15+4]; SecurityInformation
0x18000ee46  call    cs:__imp_ConvertSecurityDescriptorToStringSecurityDescriptorW
0x18000ee4c  test    eax, eax
0x18000ee4e  jnz     short loc_18000EE54
0x18000ee50  mov     [rbp+40h+StringSecurityDescriptor], r15
0x18000ee54  mov     [rsp+140h+Flags], 1; Flags
0x18000ee5c  lea     rdx, DEVPKEY_DeviceClass_Security; PropertyKey
0x18000ee63  mov     rcx, rdi; ClassGuid
0x18000ee66  test    r12, r12
0x18000ee69  jz      short loc_18000EE7D
0x18000ee6b  mov     eax, [rbp+40h+arg_20]
0x18000ee6e  mov     r9, r12
0x18000ee71  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], eax
0x18000ee75  mov     r8d, 13h
0x18000ee7b  jmp     short loc_18000EE88
0x18000ee7d  xor     r9d, r9d; PropertyBuffer
0x18000ee80  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], r15d; PropertyBufferSize
0x18000ee85  xor     r8d, r8d; PropertyType
0x18000ee88  call    cs:__imp_SetupDiSetClassPropertyW
0x18000ee8e  movzx   edx, byte ptr [rdi+0Ch]
0x18000ee92  lea     rsi, aUnknownSecurit; "Unknown security descriptor"
0x18000ee99  movzx   r8d, byte ptr [rdi+0Bh]
0x18000ee9e  test    eax, eax
0x18000eea0  movzx   r9d, byte ptr [rdi+0Ah]
0x18000eea5  movzx   r10d, byte ptr [rdi+9]
0x18000eeaa  movzx   r11d, byte ptr [rdi+8]
0x18000eeaf  movzx   ebx, word ptr [rdi+6]
0x18000eeb3  mov     rax, [rbp+40h+StringSecurityDescriptor]
0x18000eeb7  movzx   r14d, byte ptr [rdi+0Fh]
0x18000eebc  movzx   r15d, byte ptr [rdi+0Eh]
0x18000eec1  movzx   r13d, byte ptr [rdi+0Dh]
0x18000eec6  mov     [rbp+40h+pulStatus], edx
0x18000eec9  mov     [rbp+40h+var_C0], r8d
0x18000eecd  mov     [rbp+40h+var_9C], r9d
0x18000eed1  mov     [rbp+40h+var_98], r10d
0x18000eed5  mov     [rbp+40h+var_94], r11d
0x18000eed9  mov     [rbp+40h+pulProblemNumber], ebx
0x18000eedc  jz      short loc_18000EF31
0x18000eede  movzx   ecx, word ptr [rdi+4]
0x18000eee2  test    rax, rax
0x18000eee5  mov     [rsp+140h+var_D8], r14d
0x18000eeea  mov     [rsp+140h+var_E0], r15d
0x18000eeef  cmovnz  rsi, rax
0x18000eef3  mov     [rsp+140h+var_E8], r13d
0x18000eef8  mov     [rsp+140h+var_F0], edx
0x18000eefc  lea     rdx, aSuccessfullyAp; "Successfully applied security descripto"...
0x18000ef03  mov     [rsp+140h+var_F8], r8d
0x18000ef08  mov     r8, rsi
0x18000ef0b  mov     [rsp+140h+var_100], r9d
0x18000ef10  mov     r9d, [rdi]
0x18000ef13  mov     dword ptr [rsp+140h+var_108], r10d
0x18000ef18  mov     dword ptr [rsp+140h+hTemplateFile], r11d
0x18000ef1d  mov     [rsp+140h+Flags], ebx
0x18000ef21  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], ecx
0x18000ef25  mov     ecx, 8; unsigned int
0x18000ef2a  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000ef2f  jmp     short loc_18000EF9C
0x18000ef31  movzx   ebx, word ptr [rdi+4]
0x18000ef35  test    rax, rax
0x18000ef38  mov     edi, [rdi]
0x18000ef3a  cmovnz  rsi, rax
0x18000ef3e  call    cs:__imp_GetLastError
0x18000ef44  mov     ecx, [rbp+40h+pulStatus]
0x18000ef47  lea     rdx, aFailedDToApply; "Failed (%d) to apply security descripto"...
0x18000ef4e  mov     [rsp+140h+var_D0], r14d
0x18000ef53  mov     r9, rsi
0x18000ef56  mov     [rsp+140h+var_D8], r15d
0x18000ef5b  mov     r8d, eax
0x18000ef5e  mov     [rsp+140h+var_E0], r13d
0x18000ef63  mov     [rsp+140h+var_E8], ecx
0x18000ef67  mov     ecx, [rbp+40h+var_C0]
0x18000ef6a  mov     [rsp+140h+var_F0], ecx
0x18000ef6e  mov     ecx, [rbp+40h+var_9C]
0x18000ef71  mov     [rsp+140h+var_F8], ecx
0x18000ef75  mov     ecx, [rbp+40h+var_98]
0x18000ef78  mov     [rsp+140h+var_100], ecx
0x18000ef7c  mov     ecx, [rbp+40h+var_94]
0x18000ef7f  mov     dword ptr [rsp+140h+var_108], ecx
0x18000ef83  mov     ecx, [rbp+40h+pulProblemNumber]
0x18000ef86  mov     dword ptr [rsp+140h+hTemplateFile], ecx
0x18000ef8a  mov     ecx, 2; unsigned int
0x18000ef8f  mov     [rsp+140h+Flags], ebx
0x18000ef93  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], edi
0x18000ef97  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000ef9c  mov     rcx, [rbp+40h+StringSecurityDescriptor]; hMem
0x18000efa0  xor     r15d, r15d
0x18000efa3  test    rcx, rcx
0x18000efa6  jz      short loc_18000EFAE
0x18000efa8  call    cs:__imp_LocalFree
0x18000efae  mov     rsi, [rbp+40h+pDacl]
0x18000efb2  mov     r9d, 10h; Flags
0x18000efb8  lea     rcx, [rbp+40h+ClassGuid]; ClassGuid
0x18000efbc  xor     r8d, r8d; hwndParent
0x18000efbf  xor     edx, edx; Enumerator
0x18000efc1  call    cs:__imp_SetupDiGetClassDevsW
0x18000efc7  mov     rbx, rax
0x18000efca  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000efce  jz      loc_18000F347
0x18000efd4  mov     edi, r15d
0x18000efd7  lea     r8, [rbp+40h+DeviceInfoData]; DeviceInfoData
0x18000efdb  mov     [rbp+40h+DeviceInfoData.cbSize], 20h ; ' '
0x18000efe2  mov     edx, edi; MemberIndex
0x18000efe4  mov     rcx, rbx; DeviceInfoSet
0x18000efe7  call    cs:__imp_SetupDiEnumDeviceInfo
0x18000efed  test    eax, eax
0x18000efef  jz      loc_18000F30A
0x18000eff5  mov     r8d, [rbp+40h+DeviceInfoData.DevInst]; dnDevInst
0x18000eff9  lea     rdx, [rbp+40h+pulProblemNumber]; pulProblemNumber
0x18000effd  xor     r9d, r9d; ulFlags
0x18000f000  mov     [rbp+40h+pulStatus], r15d
0x18000f004  lea     rcx, [rbp+40h+pulStatus]; pulStatus
0x18000f008  mov     [rbp+40h+pulProblemNumber], r15d
0x18000f00c  mov     [rbp+40h+var_C0], 1
0x18000f013  mov     [rsp+140h+StringSecurityDescriptorLen], r15; hMachine
0x18000f018  call    cs:__imp_CM_Get_DevNode_Status_Ex
0x18000f01e  test    eax, eax
0x18000f020  jnz     short loc_18000F053
0x18000f022  test    byte ptr [rbp+40h+pulStatus], 8
0x18000f026  jz      short loc_18000F053
0x18000f028  mov     [rbp+40h+var_C0], 2
0x18000f02f  cmp     [rbp+40h+arg_28], r15d
0x18000f033  jz      short loc_18000F053
0x18000f035  test    rsi, rsi
0x18000f038  jz      short loc_18000F053
0x18000f03a  mov     eax, [rbp+40h+arg_30]
0x18000f040  lea     r8, [rbp+40h+DeviceInfoData]
0x18000f044  mov     r9, rsi
0x18000f047  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], eax
0x18000f04b  mov     rdx, rbx
0x18000f04e  call    WPDLibLogDeviceAccessEnforcementForUserSessions
0x18000f053  cmp     [rbp+40h+arg_38], r15d
0x18000f05a  jz      loc_18000F28F
0x18000f060  mov     eax, [rbp+40h+arg_20]
0x18000f063  lea     r8, [rbp+40h+DeviceInfoData]; struct _SP_DEVINFO_DATA *
0x18000f067  mov     r9, r12; unsigned __int8 *
0x18000f06a  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], eax; unsigned int
0x18000f06e  mov     rdx, rbx; void *
0x18000f071  call    ?CheckIfSecurityShouldBeSet@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@PEAEK@Z; CGroupPolicy::CheckIfSecurityShouldBeSet(void *,_SP_DEVINFO_DATA *,uchar *,ulong)
0x18000f076  test    eax, eax
0x18000f078  jz      loc_18000F28F
0x18000f07e  mov     r13d, 1
0x18000f084  test    rsi, rsi
0x18000f087  jz      loc_18000F255
0x18000f08d  lea     rax, [rbp+40h+DeviceInterfaceData]
0x18000f091  mov     [rbp+40h+DeviceInterfaceData.cbSize], 20h ; ' '
0x18000f098  mov     r9d, edi; MemberIndex
0x18000f09b  mov     [rsp+140h+StringSecurityDescriptorLen], rax; DeviceInterfaceData
0x18000f0a0  lea     r8, [rbp+40h+ClassGuid]; InterfaceClassGuid
0x18000f0a4  xor     edx, edx; DeviceInfoData
0x18000f0a6  mov     rcx, rbx; DeviceInfoSet
0x18000f0a9  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000f0af  test    eax, eax
0x18000f0b1  jz      loc_18000F2EB
0x18000f0b7  lea     rax, [rbp+40h+RequiredSize]
0x18000f0bb  mov     qword ptr [rsp+140h+Flags], r15; DeviceInfoData
0x18000f0c0  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18000f0c3  mov     [rsp+140h+StringSecurityDescriptorLen], rax; RequiredSize
0x18000f0c8  xor     r8d, r8d; DeviceInterfaceDetailData
0x18000f0cb  mov     [rbp+40h+DeviceInfoData.cbSize], 20h ; ' '
0x18000f0d2  lea     rdx, [rbp+40h+DeviceInterfaceData]; DeviceInterfaceData
0x18000f0d6  mov     rcx, rbx; DeviceInfoSet
0x18000f0d9  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000f0df  test    eax, eax
0x18000f0e1  jnz     loc_18000F2D8
0x18000f0e7  call    cs:__imp_GetLastError
0x18000f0ed  cmp     eax, 7Ah ; 'z'
0x18000f0f0  jnz     loc_18000F2C2
0x18000f0f6  mov     ecx, [rbp+40h+RequiredSize]
0x18000f0f9  test    ecx, ecx
0x18000f0fb  jz      loc_18000F2C2
0x18000f101  mov     edx, ecx; uBytes
0x18000f103  lea     ecx, [rax-3Ah]; uFlags
0x18000f106  call    cs:__imp_LocalAlloc
0x18000f10c  mov     rsi, rax
0x18000f10f  test    rax, rax
0x18000f112  jz      loc_18000F2D8
0x18000f118  lea     r14, [rax+4]
0x18000f11c  mov     dword ptr [rax], 8
0x18000f122  mov     [r14], r15w
0x18000f126  lea     rdx, [rbp+40h+DeviceInterfaceData]; DeviceInterfaceData
0x18000f12a  mov     r9d, [rbp+40h+RequiredSize]; DeviceInterfaceDetailDataSize
0x18000f12e  mov     r8, rax; DeviceInterfaceDetailData
0x18000f131  mov     qword ptr [rsp+140h+Flags], r15; DeviceInfoData
0x18000f136  mov     rcx, rbx; DeviceInfoSet
0x18000f139  mov     [rsp+140h+StringSecurityDescriptorLen], r15; RequiredSize
0x18000f13e  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000f144  test    eax, eax
0x18000f146  jz      loc_18000F29A
0x18000f14c  mov     r8, r14
0x18000f14f  lea     rdx, aDeviceInterfac; "Device interface name %ws\n"
0x18000f156  lea     ecx, [r13+7]; unsigned int
0x18000f15a  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f15f  lea     eax, [r13+2]
0x18000f163  mov     [rsp+140h+hTemplateFile], r15; hTemplateFile
0x18000f168  mov     r8d, eax; dwShareMode
0x18000f16b  mov     [rsp+140h+Flags], r15d; dwFlagsAndAttributes
0x18000f170  xor     r9d, r9d; lpSecurityAttributes
0x18000f173  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], eax; dwCreationDisposition
0x18000f177  mov     edx, 1F01FFh; dwDesiredAccess
0x18000f17c  mov     rcx, r14; lpFileName
0x18000f17f  call    cs:__imp_CreateFileW
0x18000f185  mov     r15, rax
0x18000f188  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f18c  jnz     short loc_18000F1E6
0x18000f18e  call    cs:__imp_GetLastError
0x18000f194  mov     r9, r14
0x18000f197  lea     rdx, aCreatefileFail; "CreateFile failed (%d) for %ws\n\n"
0x18000f19e  mov     r8d, eax
0x18000f1a1  lea     ecx, [r13+1]; unsigned int
0x18000f1a5  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f1aa  mov     rcx, rsi; hMem
0x18000f1ad  call    cs:__imp_LocalFree
0x18000f1b3  mov     rax, [rbp+40h+var_90]
0x18000f1b7  lea     r8, [rbp+40h+DeviceInfoData]
0x18000f1bb  mov     [rsp+140h+var_108], rax
0x18000f1c0  mov     r9, r12
0x18000f1c3  mov     eax, [rbp+40h+var_C0]
0x18000f1c6  mov     rdx, rbx
0x18000f1c9  mov     dword ptr [rsp+140h+hTemplateFile], eax
0x18000f1cd  mov     eax, [rbp+40h+arg_20]
0x18000f1d0  mov     [rsp+140h+Flags], r13d
0x18000f1d5  mov     dword ptr [rsp+140h+StringSecurityDescriptorLen], eax
0x18000f1d9  call    ?SetDeviceSecurityAndRestart@CGroupPolicy@@IEAAHPEAXPEAU_SP_DEVINFO_DATA@@0KHW4TriState@1@PEAH@Z; CGroupPolicy::SetDeviceSecurityAndRestart(void *,_SP_DEVINFO_DATA *,void *,ulong,int,CGroupPolicy::TriState,int *)
0x18000f1de  xor     r15d, r15d
0x18000f1e1  jmp     loc_18000F285
0x18000f1e6  mov     rcx, rsi; hMem
0x18000f1e9  call    cs:__imp_LocalFree
0x18000f1ef  mov     rax, [rbp+40h+pDacl]
0x18000f1f3  xor     r9d, r9d; psidOwner
0x18000f1f6  mov     [rsp+140h+hTemplateFile], 0; pSacl
0x18000f1ff  mov     edx, r13d; ObjectType
0x18000f202  mov     qword ptr [rsp+140h+Flags], rax; pDacl
0x18000f207  mov     rcx, r15; handle
0x18000f20a  mov     [rsp+140h+StringSecurityDescriptorLen], 0; psidGroup
0x18000f213  lea     r8d, [r9+4]; SecurityInfo
0x18000f217  call    cs:__imp_SetSecurityInfo
0x18000f21d  test    eax, eax
0x18000f21f  jnz     short loc_18000F235
0x18000f221  lea     rdx, aSetsecurityinf_1; "SetSecurityInfo for device succeeded\n"
0x18000f228  lea     ecx, [rax+8]; unsigned int
0x18000f22b  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f230  xor     r13d, r13d
0x18000f233  jmp     short loc_18000F249
0x18000f235  mov     r8d, eax
0x18000f238  lea     rdx, aSetsecurityinf_2; "SetSecurityInfo for device Failed %d\n"
0x18000f23f  mov     ecx, 2; unsigned int
0x18000f244  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000f249  mov     rcx, r15; hObject
0x18000f24c  call    cs:__imp_CloseHandle
0x18000f252  xor     r15d, r15d
0x18000f255  mov     rax, [rbp+40h+var_90]
0x18000f259  lea     r8, [rbp+40h+DeviceInfoData]
0x18000f25d  mov     [rsp+140h+var_108], rax
0x18000f262  mov     r9, r12
0x18000f265  mov     eax, [rbp+40h+var_C0]
0x18000f268  mov     rdx, rbx
0x18000f26b  mov     dword ptr [rsp+140h+hTemplateFile], eax
0x18000f26f  mov     eax, [rbp+40h+arg_20]
0x18000f272  mov     [rsp+140h+Flags], r13d
  ... truncated ...
```
