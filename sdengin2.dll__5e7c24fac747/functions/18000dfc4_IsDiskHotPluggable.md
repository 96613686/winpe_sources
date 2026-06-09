# IsDiskHotPluggable

- ea: `0x18000dfc4`
- end: `0x18000e398`
- name: `IsDiskHotPluggable`
- size: `980`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180010180`

## callees

- `0x18000dfc4`
- `0x18006fe84`
- `0x18006ff8c`
- `0x18008f5d0`
- `0x1800c9830`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18000e1be`
- `KERNEL32!CreateFileW` at `0x18000e1be`
- `KERNEL32!GetLastError` at `0x18000e101`
- `KERNEL32!GetLastError` at `0x18000e101`
- `KERNEL32!CloseHandle` at `0x18000e195`
- `KERNEL32!CloseHandle` at `0x18000e1d4`
- `KERNEL32!CloseHandle` at `0x18000e344`
- `KERNEL32!CloseHandle` at `0x18000e195`
- `KERNEL32!CloseHandle` at `0x18000e1d4`
- `KERNEL32!CloseHandle` at `0x18000e344`
- `KERNEL32!DeviceIoControl` at `0x18000e229`
- `KERNEL32!DeviceIoControl` at `0x18000e229`
- `ole32!CoTaskMemFree` at `0x18000e0d6`
- `ole32!CoTaskMemFree` at `0x18000e325`
- `ole32!CoTaskMemFree` at `0x18000e0d6`
- `ole32!CoTaskMemFree` at `0x18000e325`
- `ole32!CoTaskMemAlloc` at `0x18000e12b`
- `ole32!CoTaskMemAlloc` at `0x18000e12b`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000e06c`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x18000e06c`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000e0ae`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x18000e0ae`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e0fb`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e16d`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e0fb`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x18000e16d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000e32e`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18000e32e`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000e288`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x18000e288`

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

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v22, "IsDiskHotPluggable", 648, 1);
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
0x18000dfc4  push    rbp
0x18000dfc6  push    rbx
0x18000dfc7  push    rsi
0x18000dfc8  push    rdi
0x18000dfc9  push    r12
0x18000dfcb  push    r13
0x18000dfcd  push    r14
0x18000dfcf  push    r15
0x18000dfd1  lea     rbp, [rsp-1Fh]
0x18000dfd6  sub     rsp, 0E8h
0x18000dfdd  mov     rax, cs:__security_cookie
0x18000dfe4  xor     rax, rsp
0x18000dfe7  mov     [rbp+57h+var_48], rax
0x18000dfeb  mov     rsi, rdx
0x18000dfee  mov     r13d, ecx
0x18000dff1  mov     ebx, 1
0x18000dff6  mov     r9d, ebx; unsigned __int16
0x18000dff9  mov     r8d, 288h; unsigned __int16
0x18000dfff  lea     rdx, aIsdiskhotplugg; "IsDiskHotPluggable"
0x18000e006  lea     rcx, [rbp+57h+var_D0]; this
0x18000e00a  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x18000e00f  mov     dword ptr [rsp+120h+PropertyBuffer], ebx
0x18000e013  xorps   xmm0, xmm0
0x18000e016  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x18000e01a  movups  xmmword ptr [rbp+57h+var_88.ClassGuid.Data4+4], xmm0
0x18000e01e  xor     r15d, r15d
0x18000e021  mov     [rsp+120h+RequiredSize], r15d
0x18000e026  xor     eax, eax
0x18000e028  mov     [rbp+57h+OutBuffer], rax
0x18000e02c  mov     [rbp+57h+var_90], eax
0x18000e02f  mov     [rsp+120h+BytesReturned], r15d
0x18000e034  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm0
0x18000e038  movups  xmmword ptr [rbp+57h+var_68.InterfaceClassGuid.Data4+4], xmm0
0x18000e03c  mov     [rbp+57h+var_68.cbSize], 20h ; ' '
0x18000e043  mov     eax, 29Eh
0x18000e048  test    rsi, rsi
0x18000e04b  jz      loc_18000E361
0x18000e051  mov     [rsi], r15d
0x18000e054  mov     [rbp+57h+var_D0], r15d
0x18000e058  mov     [rbp+57h+var_CC], ax
0x18000e05c  lea     r9d, [rbx+11h]; Flags
0x18000e060  xor     r8d, r8d; hwndParent
0x18000e063  xor     edx, edx; Enumerator
0x18000e065  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x18000e06c  call    cs:__imp_SetupDiGetClassDevsW
0x18000e072  mov     r14, rax
0x18000e075  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e079  jz      loc_18000E34C
0x18000e07f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e083  mov     edi, r15d
0x18000e086  mov     [rbp+57h+var_D0], r15d
0x18000e08a  mov     ecx, 2A4h
0x18000e08f  mov     [rbp+57h+var_CC], cx
0x18000e093  mov     r12d, r15d
0x18000e096  lea     rax, [rbp+57h+var_68]
0x18000e09a  mov     [rsp+120h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000e09f  mov     r9d, r12d; MemberIndex
0x18000e0a2  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x18000e0a9  xor     edx, edx; DeviceInfoData
0x18000e0ab  mov     rcx, r14; DeviceInfoSet
0x18000e0ae  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x18000e0b4  test    eax, eax
0x18000e0b6  jz      loc_18000E30D
0x18000e0bc  xorps   xmm0, xmm0
0x18000e0bf  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x18000e0c3  movups  xmmword ptr [rbp+57h+var_88.ClassGuid.Data4+4], xmm0
0x18000e0c7  mov     [rbp+57h+var_88.cbSize], 20h ; ' '
0x18000e0ce  test    rdi, rdi
0x18000e0d1  jz      short loc_18000E0DF
0x18000e0d3  mov     rcx, rdi; pv
0x18000e0d6  call    cs:__imp_CoTaskMemFree
0x18000e0dc  mov     rdi, r15
0x18000e0df  mov     [rsp+120h+DeviceInfoData], r15; DeviceInfoData
0x18000e0e4  lea     rax, [rsp+120h+RequiredSize]
0x18000e0e9  mov     [rsp+120h+DeviceInterfaceData], rax; RequiredSize
0x18000e0ee  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x18000e0f1  xor     r8d, r8d; DeviceInterfaceDetailData
0x18000e0f4  lea     rdx, [rbp+57h+var_68]; DeviceInterfaceData
0x18000e0f8  mov     rcx, r14; DeviceInfoSet
0x18000e0fb  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000e101  call    cs:__imp_GetLastError
0x18000e107  cmp     eax, 7Ah ; 'z'
0x18000e10a  jnz     loc_18000E2FE
0x18000e110  mov     eax, [rsp+120h+RequiredSize]
0x18000e114  test    eax, eax
0x18000e116  jz      loc_18000E2FE
0x18000e11c  mov     [rbp+57h+var_D0], r15d
0x18000e120  mov     ecx, 2B9h
0x18000e125  mov     [rbp+57h+var_CC], cx
0x18000e129  mov     ecx, eax; cb
0x18000e12b  call    cs:__imp_CoTaskMemAlloc
0x18000e131  mov     rdi, rax
0x18000e134  test    rax, rax
0x18000e137  mov     eax, 2BCh
0x18000e13c  jz      loc_18000E2F1
0x18000e142  mov     [rbp+57h+var_D0], r15d
0x18000e146  mov     [rbp+57h+var_CC], ax
0x18000e14a  mov     dword ptr [rdi], 8
0x18000e150  lea     rax, [rbp+57h+var_88]
0x18000e154  mov     [rsp+120h+DeviceInfoData], rax; DeviceInfoData
0x18000e159  mov     [rsp+120h+DeviceInterfaceData], r15; RequiredSize
0x18000e15e  mov     r9d, [rsp+120h+RequiredSize]; DeviceInterfaceDetailDataSize
0x18000e163  mov     r8, rdi; DeviceInterfaceDetailData
0x18000e166  lea     rdx, [rbp+57h+var_68]; DeviceInterfaceData
0x18000e16a  mov     rcx, r14; DeviceInfoSet
0x18000e16d  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000e173  test    eax, eax
0x18000e175  jz      loc_18000E2DE
0x18000e17b  mov     [rbp+57h+var_D0], r15d
0x18000e17f  mov     eax, 2C8h
0x18000e184  mov     [rbp+57h+var_CC], ax
0x18000e188  lea     rax, [rbx-1]
0x18000e18c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e190  ja      short loc_18000E19F
0x18000e192  mov     rcx, rbx; hObject
0x18000e195  call    cs:__imp_CloseHandle
0x18000e19b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e19f  lea     rcx, [rdi+4]; lpFileName
0x18000e1a3  mov     [rsp+120h+hTemplateFile], r15; hTemplateFile
0x18000e1a8  mov     dword ptr [rsp+120h+DeviceInfoData], r15d; dwFlagsAndAttributes
0x18000e1ad  mov     eax, 3
0x18000e1b2  mov     dword ptr [rsp+120h+DeviceInterfaceData], eax; dwCreationDisposition
0x18000e1b6  xor     r9d, r9d; lpSecurityAttributes
0x18000e1b9  mov     r8d, eax; dwShareMode
0x18000e1bc  xor     edx, edx; dwDesiredAccess
0x18000e1be  call    cs:__imp_CreateFileW
0x18000e1c4  mov     r15, rax
0x18000e1c7  lea     rcx, [rbx-1]
0x18000e1cb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000e1cf  ja      short loc_18000E1DA
0x18000e1d1  mov     rcx, rbx; hObject
0x18000e1d4  call    cs:__imp_CloseHandle
0x18000e1da  mov     rbx, r15
0x18000e1dd  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000e1e1  jz      loc_18000E2CF
0x18000e1e7  mov     [rbp+57h+var_D0], 0
0x18000e1ee  mov     eax, 2D2h
0x18000e1f3  mov     [rbp+57h+var_CC], ax
0x18000e1f7  mov     [rsp+120h+lpOverlapped], 0; lpOverlapped
0x18000e200  lea     rax, [rsp+120h+BytesReturned]
0x18000e205  mov     [rsp+120h+hTemplateFile], rax; lpBytesReturned
0x18000e20a  mov     dword ptr [rsp+120h+DeviceInfoData], 0Ch; nOutBufferSize
0x18000e212  lea     rax, [rbp+57h+OutBuffer]
0x18000e216  mov     [rsp+120h+DeviceInterfaceData], rax; lpOutBuffer
0x18000e21b  xor     r9d, r9d; nInBufferSize
0x18000e21e  xor     r8d, r8d; lpInBuffer
0x18000e221  mov     edx, 2D1080h; dwIoControlCode
0x18000e226  mov     rcx, r15; hDevice
0x18000e229  call    cs:__imp_DeviceIoControl
0x18000e22f  xor     r15d, r15d
0x18000e232  test    eax, eax
0x18000e234  jz      loc_18000E2C0
0x18000e23a  mov     [rbp+57h+var_D0], r15d
0x18000e23e  mov     eax, 2DBh
0x18000e243  mov     [rbp+57h+var_CC], ax
0x18000e247  cmp     dword ptr [rbp+57h+OutBuffer+4], r13d
0x18000e24b  jz      short loc_18000E255
0x18000e24d  inc     r12d
0x18000e250  jmp     loc_18000E096
0x18000e255  mov     eax, 2E7h
0x18000e25a  mov     [rbp+57h+var_CC], ax
0x18000e25e  lea     rax, [rsp+120h+BytesReturned]
0x18000e263  mov     [rsp+120h+hTemplateFile], rax; RequiredSize
0x18000e268  mov     dword ptr [rsp+120h+DeviceInfoData], 4; PropertyBufferSize
0x18000e270  lea     rax, [rsp+120h+PropertyBuffer]
0x18000e275  mov     [rsp+120h+DeviceInterfaceData], rax; PropertyBuffer
0x18000e27a  xor     r9d, r9d; PropertyRegDataType
0x18000e27d  lea     r8d, [r9+1Fh]; Property
0x18000e281  lea     rdx, [rbp+57h+var_88]; DeviceInfoData
0x18000e285  mov     rcx, r14; DeviceInfoSet
0x18000e288  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x18000e28e  test    eax, eax
0x18000e290  jnz     short loc_18000E2A1
0x18000e292  call    GetLastFailureAsHRESULT
0x18000e297  mov     [rbp+57h+var_D0], eax
0x18000e29a  mov     eax, 2EFh
0x18000e29f  jmp     short loc_18000E2EB
0x18000e2a1  mov     [rbp+57h+var_D0], r15d
0x18000e2a5  mov     eax, 2EFh
0x18000e2aa  mov     [rbp+57h+var_CC], ax
0x18000e2ae  mov     [rsi], r15d
0x18000e2b1  cmp     dword ptr [rsp+120h+PropertyBuffer], 1
0x18000e2b6  jz      short loc_18000E322
0x18000e2b8  mov     dword ptr [rsi], 1
0x18000e2be  jmp     short loc_18000E322
0x18000e2c0  call    GetLastFailureAsHRESULT
0x18000e2c5  mov     [rbp+57h+var_D0], eax
0x18000e2c8  mov     eax, 2DBh
0x18000e2cd  jmp     short loc_18000E2EB
0x18000e2cf  call    GetLastFailureAsHRESULT
0x18000e2d4  mov     [rbp+57h+var_D0], eax
0x18000e2d7  mov     eax, 2D2h
0x18000e2dc  jmp     short loc_18000E2EB
0x18000e2de  call    GetLastFailureAsHRESULT
0x18000e2e3  mov     [rbp+57h+var_D0], eax
0x18000e2e6  mov     eax, 2C8h
0x18000e2eb  mov     [rbp+57h+var_CA], ax
0x18000e2ef  jmp     short loc_18000E322
0x18000e2f1  mov     [rbp+57h+var_D0], 8007000Eh
0x18000e2f8  mov     [rbp+57h+var_CA], ax
0x18000e2fc  jmp     short loc_18000E32B
0x18000e2fe  call    GetLastFailureAsHRESULT
0x18000e303  mov     [rbp+57h+var_D0], eax
0x18000e306  mov     eax, 2B9h
0x18000e30b  jmp     short loc_18000E319
0x18000e30d  mov     [rbp+57h+var_D0], 81000036h
0x18000e314  mov     eax, 2E7h
0x18000e319  mov     [rbp+57h+var_CA], ax
0x18000e31d  test    rdi, rdi
0x18000e320  jz      short loc_18000E32B
0x18000e322  mov     rcx, rdi; pv
0x18000e325  call    cs:__imp_CoTaskMemFree
0x18000e32b  mov     rcx, r14; DeviceInfoSet
0x18000e32e  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18000e334  mov     edi, [rbp+57h+var_D0]
0x18000e337  lea     rax, [rbx-1]
0x18000e33b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e33f  ja      short loc_18000E36D
0x18000e341  mov     rcx, rbx; hObject
0x18000e344  call    cs:__imp_CloseHandle
0x18000e34a  jmp     short loc_18000E36D
0x18000e34c  call    GetLastFailureAsHRESULT
0x18000e351  mov     edi, eax
0x18000e353  mov     [rbp+57h+var_D0], eax
0x18000e356  mov     ecx, 2A4h
0x18000e35b  mov     [rbp+57h+var_CA], cx
0x18000e35f  jmp     short loc_18000E36D
0x18000e361  mov     edi, 80070057h
0x18000e366  mov     [rbp+57h+var_D0], edi
0x18000e369  mov     [rbp+57h+var_CA], ax
0x18000e36d  lea     rcx, [rbp+57h+var_D0]; this
0x18000e371  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18000e376  mov     eax, edi
0x18000e378  mov     rcx, [rbp+57h+var_48]
0x18000e37c  xor     rcx, rsp; StackCookie
0x18000e37f  call    __security_check_cookie
0x18000e384  add     rsp, 0E8h
0x18000e38b  pop     r15
0x18000e38d  pop     r14
0x18000e38f  pop     r13
0x18000e391  pop     r12
0x18000e393  pop     rdi
0x18000e394  pop     rsi
0x18000e395  pop     rbx
0x18000e396  pop     rbp
0x18000e397  retn
```
