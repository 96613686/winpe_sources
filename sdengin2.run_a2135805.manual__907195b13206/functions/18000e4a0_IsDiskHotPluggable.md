# IsDiskHotPluggable

- ea: `0x18000e4a0`
- end: `0x18000e8cf`
- name: `IsDiskHotPluggable`
- size: `1071`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180010800`

## callees

- `0x18000e4a0`
- `0x180072e08`
- `0x180072f14`
- `0x1800935fc`
- `0x1800cf5c0`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000e6ca`
- `KERNEL32!CreateFileW` at `0x18000e6ca`
- `KERNEL32!GetLastError` at `0x18000e5f5`
- `KERNEL32!GetLastError` at `0x18000e5f5`
- `KERNEL32!CloseHandle` at `0x18000e69b`
- `KERNEL32!CloseHandle` at `0x18000e6e6`
- `KERNEL32!CloseHandle` at `0x18000e874`
- `KERNEL32!CloseHandle` at `0x18000e69b`
- `KERNEL32!CloseHandle` at `0x18000e6e6`
- `KERNEL32!CloseHandle` at `0x18000e874`
- `KERNEL32!DeviceIoControl` at `0x18000e741`
- `KERNEL32!DeviceIoControl` at `0x18000e741`
- `ole32!CoTaskMemFree` at `0x18000e5be`
- `ole32!CoTaskMemFree` at `0x18000e849`
- `ole32!CoTaskMemFree` at `0x18000e5be`
- `ole32!CoTaskMemFree` at `0x18000e849`
- `ole32!CoTaskMemAlloc` at `0x18000e625`
- `ole32!CoTaskMemAlloc` at `0x18000e625`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000e548`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000e548`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000e590`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000e590`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e5e9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e66d`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e5e9`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e66d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000e858`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000e858`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000e7a6`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000e7a6`

## pseudocode

```c
__int64 __fastcall IsDiskHotPluggable(int a1, _DWORD *a2)
{
  __int64 v4; // rcx
  HDEVINFO ClassDevsW; // r14
  __int64 v6; // rbx
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v7; // rdi
  DWORD i; // r12d
  __int64 v9; // rcx
  __int64 v10; // rcx
  HANDLE FileW; // r15
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int16 v15; // ax
  __int16 v16; // ax
  unsigned int LastFailureAsHRESULT; // edi
  DWORD RequiredSize; // [rsp+40h] [rbp-89h] BYREF
  DWORD BytesReturned; // [rsp+44h] [rbp-85h] BYREF
  BYTE PropertyBuffer[8]; // [rsp+48h] [rbp-81h] BYREF
  int v22; // [rsp+50h] [rbp-79h] BYREF
  __int16 v23; // [rsp+54h] [rbp-75h]
  __int16 v24; // [rsp+56h] [rbp-73h]
  __int64 OutBuffer; // [rsp+88h] [rbp-41h] BYREF
  int v26; // [rsp+90h] [rbp-39h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+98h] [rbp-31h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+B8h] [rbp-11h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "IsDiskHotPluggable", 0x288u, 1u);
  *(_DWORD *)PropertyBuffer = 1;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  RequiredSize = 0;
  OutBuffer = 0;
  v26 = 0;
  BytesReturned = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInterfaceData.cbSize = 32;
  if ( !a2 )
  {
    LastFailureAsHRESULT = -2147024809;
    v22 = -2147024809;
    v24 = 670;
    goto LABEL_36;
  }
  *a2 = 0;
  v22 = 0;
  v23 = 670;
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
  if ( ClassDevsW == (HDEVINFO)-1LL )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v4);
    v22 = LastFailureAsHRESULT;
    v24 = 676;
    goto LABEL_36;
  }
  v6 = -1;
  v7 = 0;
  v22 = 0;
  v23 = 676;
  for ( i = 0; ; ++i )
  {
    if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVINTERFACE_DISK, i, &DeviceInterfaceData) )
    {
      v22 = -2130706378;
      v16 = 743;
LABEL_30:
      v24 = v16;
      if ( !v7 )
        goto LABEL_32;
      goto LABEL_31;
    }
    memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
    DeviceInfoData.cbSize = 32;
    if ( v7 )
    {
      CoTaskMemFree(v7);
      v7 = 0;
    }
    SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, 0, 0, &RequiredSize, 0);
    if ( GetLastError() != 122 || !RequiredSize )
    {
      v22 = GetLastFailureAsHRESULT(v9);
      v16 = 697;
      goto LABEL_30;
    }
    v22 = 0;
    v23 = 697;
    v7 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)CoTaskMemAlloc(RequiredSize);
    if ( !v7 )
    {
      v22 = -2147024882;
      v24 = 700;
      goto LABEL_32;
    }
    v22 = 0;
    v23 = 700;
    v7->cbSize = 8;
    if ( !SetupDiGetDeviceInterfaceDetailW(ClassDevsW, &DeviceInterfaceData, v7, RequiredSize, 0, &DeviceInfoData) )
    {
      v22 = GetLastFailureAsHRESULT(v10);
      v15 = 712;
      goto LABEL_26;
    }
    v22 = 0;
    v23 = 712;
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      CloseHandle((HANDLE)v6);
      v6 = -1;
    }
    FileW = CreateFileW(v7->DevicePath, 0, 3u, 0, 3u, 0, 0);
    v12 = v6 - 1;
    if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)v6);
    v6 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v22 = GetLastFailureAsHRESULT(v12);
      v15 = 722;
      goto LABEL_26;
    }
    v22 = 0;
    v23 = 722;
    if ( !DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &BytesReturned, 0) )
    {
      v22 = GetLastFailureAsHRESULT(v13);
      v15 = 731;
      goto LABEL_26;
    }
    v22 = 0;
    v23 = 731;
    if ( HIDWORD(OutBuffer) == a1 )
      break;
  }
  v23 = 743;
  if ( !SetupDiGetDeviceRegistryPropertyW(ClassDevsW, &DeviceInfoData, 0x1Fu, 0, PropertyBuffer, 4u, &BytesReturned) )
  {
    v22 = GetLastFailureAsHRESULT(v14);
    v15 = 751;
LABEL_26:
    v24 = v15;
    goto LABEL_31;
  }
  v22 = 0;
  v23 = 751;
  *a2 = 0;
  if ( *(_DWORD *)PropertyBuffer != 1 )
    *a2 = 1;
LABEL_31:
  CoTaskMemFree(v7);
LABEL_32:
  SetupDiDestroyDeviceInfoList(ClassDevsW);
  LastFailureAsHRESULT = v22;
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
LABEL_36:
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v22);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x18000e4a0  push    rbp
0x18000e4a2  push    rbx
0x18000e4a3  push    rsi
0x18000e4a4  push    rdi
0x18000e4a5  push    r12
0x18000e4a7  push    r13
0x18000e4a9  push    r14
0x18000e4ab  push    r15
0x18000e4ad  lea     rbp, [rsp-1Fh]
0x18000e4b2  sub     rsp, 0E8h
0x18000e4b9  mov     rax, cs:__security_cookie
0x18000e4c0  xor     rax, rsp
0x18000e4c3  mov     [rbp+57h+var_48], rax
0x18000e4c7  mov     rsi, rdx
0x18000e4ca  mov     r13d, ecx
0x18000e4cd  mov     ebx, 1
0x18000e4d2  mov     r9d, ebx; unsigned __int16
0x18000e4d5  mov     r8d, 288h; unsigned __int16
0x18000e4db  lea     rdx, aIsdiskhotplugg; "IsDiskHotPluggable"
0x18000e4e2  lea     rcx, [rbp+57h+var_D0]; this
0x18000e4e6  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e4eb  mov     dword ptr [rsp+120h+PropertyBuffer], ebx
0x18000e4ef  xorps   xmm0, xmm0
0x18000e4f2  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x18000e4f6  movups  xmmword ptr [rbp+57h+var_88.ClassGuid.Data4+4], xmm0
0x18000e4fa  xor     r15d, r15d
0x18000e4fd  mov     [rsp+120h+RequiredSize], r15d
0x18000e502  xor     eax, eax
0x18000e504  mov     [rbp+57h+OutBuffer], rax
0x18000e508  mov     [rbp+57h+var_90], eax
0x18000e50b  mov     [rsp+120h+BytesReturned], r15d
0x18000e510  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm0
0x18000e514  movups  xmmword ptr [rbp+57h+var_68.InterfaceClassGuid.Data4+4], xmm0
0x18000e518  mov     [rbp+57h+var_68.cbSize], 20h ; ' '
0x18000e51f  mov     eax, 29Eh
0x18000e524  test    rsi, rsi
0x18000e527  jz      loc_18000E897
0x18000e52d  mov     [rsi], r15d
0x18000e530  mov     [rbp+57h+var_D0], r15d
0x18000e534  mov     [rbp+57h+var_CC], ax
0x18000e538  lea     r9d, [rbx+11h]; Flags
0x18000e53c  xor     r8d, r8d; hwndParent
0x18000e53f  xor     edx, edx; Enumerator
0x18000e541  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x18000e548  call    cs:__imp_SetupDiGetClassDevsW
0x18000e54f  nop     dword ptr [rax+rax+00h]
0x18000e554  mov     r14, rax
0x18000e557  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e55b  jz      loc_18000E882
0x18000e561  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e565  mov     edi, r15d
0x18000e568  mov     [rbp+57h+var_D0], r15d
0x18000e56c  mov     ecx, 2A4h
0x18000e571  mov     [rbp+57h+var_CC], cx
0x18000e575  mov     r12d, r15d
0x18000e578  lea     rax, [rbp+57h+var_68]
0x18000e57c  mov     [rsp+120h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000e581  mov     r9d, r12d; MemberIndex
0x18000e584  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x18000e58b  xor     edx, edx; DeviceInfoData
0x18000e58d  mov     rcx, r14; DeviceInfoSet
0x18000e590  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000e597  nop     dword ptr [rax+rax+00h]
0x18000e59c  test    eax, eax
0x18000e59e  jz      loc_18000E831
0x18000e5a4  xorps   xmm0, xmm0
0x18000e5a7  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x18000e5ab  movups  xmmword ptr [rbp+57h+var_88.ClassGuid.Data4+4], xmm0
0x18000e5af  mov     [rbp+57h+var_88.cbSize], 20h ; ' '
0x18000e5b6  test    rdi, rdi
0x18000e5b9  jz      short loc_18000E5CD
0x18000e5bb  mov     rcx, rdi; pv
0x18000e5be  call    cs:__imp_CoTaskMemFree
0x18000e5c5  nop     dword ptr [rax+rax+00h]
0x18000e5ca  mov     rdi, r15
0x18000e5cd  mov     [rsp+120h+DeviceInfoData], r15; DeviceInfoData
0x18000e5d2  lea     rax, [rsp+120h+RequiredSize]
0x18000e5d7  mov     [rsp+120h+DeviceInterfaceData], rax; RequiredSize
0x18000e5dc  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18000e5df  xor     r8d, r8d; DeviceInterfaceDetailData
0x18000e5e2  lea     rdx, [rbp+57h+var_68]; DeviceInterfaceData
0x18000e5e6  mov     rcx, r14; DeviceInfoSet
0x18000e5e9  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000e5f0  nop     dword ptr [rax+rax+00h]
0x18000e5f5  call    cs:__imp_GetLastError
0x18000e5fc  nop     dword ptr [rax+rax+00h]
0x18000e601  cmp     eax, 7Ah ; 'z'
0x18000e604  jnz     loc_18000E822
0x18000e60a  mov     eax, [rsp+120h+RequiredSize]
0x18000e60e  test    eax, eax
0x18000e610  jz      loc_18000E822
0x18000e616  mov     [rbp+57h+var_D0], r15d
0x18000e61a  mov     ecx, 2B9h
0x18000e61f  mov     [rbp+57h+var_CC], cx
0x18000e623  mov     ecx, eax; cb
0x18000e625  call    cs:__imp_CoTaskMemAlloc
0x18000e62c  nop     dword ptr [rax+rax+00h]
0x18000e631  mov     rdi, rax
0x18000e634  test    rax, rax
0x18000e637  mov     eax, 2BCh
0x18000e63c  jz      loc_18000E815
0x18000e642  mov     [rbp+57h+var_D0], r15d
0x18000e646  mov     [rbp+57h+var_CC], ax
0x18000e64a  mov     dword ptr [rdi], 8
0x18000e650  lea     rax, [rbp+57h+var_88]
0x18000e654  mov     [rsp+120h+DeviceInfoData], rax; DeviceInfoData
0x18000e659  mov     [rsp+120h+DeviceInterfaceData], r15; RequiredSize
0x18000e65e  mov     r9d, [rsp+120h+RequiredSize]; DeviceInterfaceDetailDataSize
0x18000e663  mov     r8, rdi; DeviceInterfaceDetailData
0x18000e666  lea     rdx, [rbp+57h+var_68]; DeviceInterfaceData
0x18000e66a  mov     rcx, r14; DeviceInfoSet
0x18000e66d  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000e674  nop     dword ptr [rax+rax+00h]
0x18000e679  test    eax, eax
0x18000e67b  jz      loc_18000E802
0x18000e681  mov     [rbp+57h+var_D0], r15d
0x18000e685  mov     eax, 2C8h
0x18000e68a  mov     [rbp+57h+var_CC], ax
0x18000e68e  lea     rax, [rbx-1]
0x18000e692  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e696  ja      short loc_18000E6AB
0x18000e698  mov     rcx, rbx; hObject
0x18000e69b  call    cs:__imp_CloseHandle
0x18000e6a2  nop     dword ptr [rax+rax+00h]
0x18000e6a7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e6ab  lea     rcx, [rdi+4]; lpFileName
0x18000e6af  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x18000e6b4  mov     dword ptr [rsp+120h+DeviceInfoData], r15d; dwFlagsAndAttributes
0x18000e6b9  mov     eax, 3
0x18000e6be  mov     dword ptr [rsp+120h+DeviceInterfaceData], eax; dwCreationDisposition
0x18000e6c2  xor     r9d, r9d; lpSecurityAttributes
0x18000e6c5  mov     r8d, eax; dwShareMode
0x18000e6c8  xor     edx, edx; dwDesiredAccess
0x18000e6ca  call    cs:__imp_CreateFileW
0x18000e6d1  nop     dword ptr [rax+rax+00h]
0x18000e6d6  mov     r15, rax
0x18000e6d9  lea     rcx, [rbx-1]
0x18000e6dd  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e6e1  ja      short loc_18000E6F2
0x18000e6e3  mov     rcx, rbx; hObject
0x18000e6e6  call    cs:__imp_CloseHandle
0x18000e6ed  nop     dword ptr [rax+rax+00h]
0x18000e6f2  mov     rbx, r15
0x18000e6f5  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000e6f9  jz      loc_18000E7F3
0x18000e6ff  mov     [rbp+57h+var_D0], 0
0x18000e706  mov     eax, 2D2h
0x18000e70b  mov     [rbp+57h+var_CC], ax
0x18000e70f  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x18000e718  lea     rax, [rsp+120h+BytesReturned]
0x18000e71d  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x18000e722  mov     dword ptr [rsp+120h+DeviceInfoData], 0Ch; nOutBufferSize
0x18000e72a  lea     rax, [rbp+57h+OutBuffer]
0x18000e72e  mov     [rsp+120h+DeviceInterfaceData], rax; lpOutBuffer
0x18000e733  xor     r9d, r9d; nInBufferSize
0x18000e736  xor     r8d, r8d; lpInBuffer
0x18000e739  mov     edx, 2D1080h; dwIoControlCode
0x18000e73e  mov     rcx, r15; hDevice
0x18000e741  call    cs:__imp_DeviceIoControl
0x18000e748  nop     dword ptr [rax+rax+00h]
0x18000e74d  xor     r15d, r15d
0x18000e750  test    eax, eax
0x18000e752  jz      loc_18000E7E4
0x18000e758  mov     [rbp+57h+var_D0], r15d
0x18000e75c  mov     eax, 2DBh
0x18000e761  mov     [rbp+57h+var_CC], ax
0x18000e765  cmp     dword ptr [rbp+57h+OutBuffer+4], r13d
0x18000e769  jz      short loc_18000E773
0x18000e76b  inc     r12d
0x18000e76e  jmp     loc_18000E578
0x18000e773  mov     eax, 2E7h
0x18000e778  mov     [rbp+57h+var_CC], ax
0x18000e77c  lea     rax, [rsp+120h+BytesReturned]
0x18000e781  mov     [rsp+120h+hTemplateFile], rax; RequiredSize
0x18000e786  mov     dword ptr [rsp+120h+DeviceInfoData], 4; PropertyBufferSize
0x18000e78e  lea     rax, [rsp+120h+PropertyBuffer]
0x18000e793  mov     [rsp+120h+DeviceInterfaceData], rax; PropertyBuffer
0x18000e798  xor     r9d, r9d; PropertyRegDataType
0x18000e79b  lea     r8d, [r9+1Fh]; Property
0x18000e79f  lea     rdx, [rbp+57h+var_88]; DeviceInfoData
0x18000e7a3  mov     rcx, r14; DeviceInfoSet
0x18000e7a6  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x18000e7ad  nop     dword ptr [rax+rax+00h]
0x18000e7b2  test    eax, eax
0x18000e7b4  jnz     short loc_18000E7C5
0x18000e7b6  call    GetLastFailureAsHRESULT
0x18000e7bb  mov     [rbp+57h+var_D0], eax
0x18000e7be  mov     eax, 2EFh
0x18000e7c3  jmp     short loc_18000E80F
0x18000e7c5  mov     [rbp+57h+var_D0], r15d
0x18000e7c9  mov     eax, 2EFh
0x18000e7ce  mov     [rbp+57h+var_CC], ax
0x18000e7d2  mov     [rsi], r15d
0x18000e7d5  cmp     dword ptr [rsp+120h+PropertyBuffer], 1
0x18000e7da  jz      short loc_18000E846
0x18000e7dc  mov     dword ptr [rsi], 1
0x18000e7e2  jmp     short loc_18000E846
0x18000e7e4  call    GetLastFailureAsHRESULT
0x18000e7e9  mov     [rbp+57h+var_D0], eax
0x18000e7ec  mov     eax, 2DBh
0x18000e7f1  jmp     short loc_18000E80F
0x18000e7f3  call    GetLastFailureAsHRESULT
0x18000e7f8  mov     [rbp+57h+var_D0], eax
0x18000e7fb  mov     eax, 2D2h
0x18000e800  jmp     short loc_18000E80F
0x18000e802  call    GetLastFailureAsHRESULT
0x18000e807  mov     [rbp+57h+var_D0], eax
0x18000e80a  mov     eax, 2C8h
0x18000e80f  mov     [rbp+57h+var_CA], ax
0x18000e813  jmp     short loc_18000E846
0x18000e815  mov     [rbp+57h+var_D0], 8007000Eh
0x18000e81c  mov     [rbp+57h+var_CA], ax
0x18000e820  jmp     short loc_18000E855
0x18000e822  call    GetLastFailureAsHRESULT
0x18000e827  mov     [rbp+57h+var_D0], eax
0x18000e82a  mov     eax, 2B9h
0x18000e82f  jmp     short loc_18000E83D
0x18000e831  mov     [rbp+57h+var_D0], 81000036h
0x18000e838  mov     eax, 2E7h
0x18000e83d  mov     [rbp+57h+var_CA], ax
0x18000e841  test    rdi, rdi
0x18000e844  jz      short loc_18000E855
0x18000e846  mov     rcx, rdi; pv
0x18000e849  call    cs:__imp_CoTaskMemFree
0x18000e850  nop     dword ptr [rax+rax+00h]
0x18000e855  mov     rcx, r14; DeviceInfoSet
0x18000e858  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000e85f  nop     dword ptr [rax+rax+00h]
0x18000e864  mov     edi, [rbp+57h+var_D0]
0x18000e867  lea     rax, [rbx-1]
0x18000e86b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e86f  ja      short loc_18000E8A3
0x18000e871  mov     rcx, rbx; hObject
0x18000e874  call    cs:__imp_CloseHandle
0x18000e87b  nop     dword ptr [rax+rax+00h]
0x18000e880  jmp     short loc_18000E8A3
0x18000e882  call    GetLastFailureAsHRESULT
0x18000e887  mov     edi, eax
0x18000e889  mov     [rbp+57h+var_D0], eax
0x18000e88c  mov     ecx, 2A4h
0x18000e891  mov     [rbp+57h+var_CA], cx
0x18000e895  jmp     short loc_18000E8A3
0x18000e897  mov     edi, 80070057h
0x18000e89c  mov     [rbp+57h+var_D0], edi
0x18000e89f  mov     [rbp+57h+var_CA], ax
0x18000e8a3  lea     rcx, [rbp+57h+var_D0]; this
0x18000e8a7  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e8ac  mov     eax, edi
0x18000e8ae  mov     rcx, [rbp+57h+var_48]
0x18000e8b2  xor     rcx, rsp; StackCookie
0x18000e8b5  call    __security_check_cookie
0x18000e8ba  add     rsp, 0E8h
0x18000e8c1  pop     r15
0x18000e8c3  pop     r14
0x18000e8c5  pop     r13
0x18000e8c7  pop     r12
0x18000e8c9  pop     rdi
0x18000e8ca  pop     rsi
0x18000e8cb  pop     rbx
0x18000e8cc  pop     rbp
0x18000e8cd  retn
```
