# BlbIsDiskYankable(ulong,uchar *)

- ea: `0x1401169a8`
- end: `0x140116ea7`
- name: `?BlbIsDiskYankable@@YAJKPEAE@Z`
- size: `1279`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x140100e3c`

## callees

- `0x140007ad3`
- `0x14000bb4c`
- `0x140014260`
- `0x1400c3fec`
- `0x1401169a8`
- `0x140134d20`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140116bc2`
- `KERNEL32!CreateFileW` at `0x140116bc2`
- `KERNEL32!CloseHandle` at `0x140116b93`
- `KERNEL32!CloseHandle` at `0x140116d59`
- `KERNEL32!CloseHandle` at `0x140116b93`
- `KERNEL32!CloseHandle` at `0x140116d59`
- `KERNEL32!GetLastError` at `0x140116a23`
- `KERNEL32!GetLastError` at `0x140116afc`
- `KERNEL32!GetLastError` at `0x140116bd2`
- `KERNEL32!GetLastError` at `0x140116c59`
- `KERNEL32!GetLastError` at `0x140116d0d`
- `KERNEL32!GetLastError` at `0x140116dee`
- `KERNEL32!GetLastError` at `0x140116e1c`
- `KERNEL32!GetLastError` at `0x140116a23`
- `KERNEL32!GetLastError` at `0x140116afc`
- `KERNEL32!GetLastError` at `0x140116bd2`
- `KERNEL32!GetLastError` at `0x140116c59`
- `KERNEL32!GetLastError` at `0x140116d0d`
- `KERNEL32!GetLastError` at `0x140116dee`
- `KERNEL32!GetLastError` at `0x140116e1c`
- `KERNEL32!DeviceIoControl` at `0x140116c4f`
- `KERNEL32!DeviceIoControl` at `0x140116c4f`
- `ole32!CoTaskMemAlloc` at `0x140116b21`
- `ole32!CoTaskMemAlloc` at `0x140116b21`
- `ole32!CoTaskMemFree` at `0x140116b18`
- `ole32!CoTaskMemFree` at `0x140116d67`
- `ole32!CoTaskMemFree` at `0x140116b18`
- `ole32!CoTaskMemFree` at `0x140116d67`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140116d71`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140116d71`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x140116ac4`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x140116ac4`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x140116cff`
- `SETUPAPI!SetupDiGetDeviceRegistryPropertyW` at `0x140116cff`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x140116a13`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x140116a13`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x140116af2`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x140116b7c`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x140116af2`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x140116b7c`

## pseudocode

```c
__int64 __fastcall BlbIsDiskYankable(unsigned int a1, unsigned __int8 *a2)
{
  DWORD v2; // ebx
  unsigned int v3; // r12d
  HDEVINFO ClassDevsW; // rax
  signed int LastError; // ebx
  PVOID *v6; // rcx
  bool v7; // sf
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v8; // r13
  __int64 v9; // r12
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v10; // rax
  HDEVINFO v11; // rcx
  HANDLE FileW; // rax
  char v13; // al
  char v14; // al
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  DWORD v17; // eax
  DWORD RequiredSize; // [rsp+40h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+44h] [rbp-45h]
  DWORD v21; // [rsp+48h] [rbp-41h]
  BYTE PropertyBuffer[4]; // [rsp+4Ch] [rbp-3Dh] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+50h] [rbp-39h]
  HANDLE hObject; // [rsp+58h] [rbp-31h]
  unsigned __int8 *v25; // [rsp+60h] [rbp-29h]
  __int64 OutBuffer; // [rsp+68h] [rbp-21h] BYREF
  int v27; // [rsp+70h] [rbp-19h]
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+78h] [rbp-11h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+98h] [rbp+Fh] BYREF

  v2 = 0;
  v20 = a1;
  v3 = a1;
  v25 = a2;
  *a2 = 0;
  OutBuffer = 0;
  v27 = 0;
  RequiredSize = 0;
  *(_DWORD *)PropertyBuffer = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  ClassDevsW = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_DISK, 0, 0, 0x12u);
  DeviceInfoSet = ClassDevsW;
  if ( ClassDevsW != (HDEVINFO)-1LL )
  {
    v8 = 0;
    v9 = -1;
    while ( 1 )
    {
      v21 = v2;
      memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
      DeviceInterfaceData.cbSize = 32;
      if ( !SetupDiEnumDeviceInterfaces(ClassDevsW, 0, &GUID_DEVINTERFACE_DISK, v2, &DeviceInterfaceData) )
        break;
      if ( !SetupDiGetDeviceInterfaceDetailW(DeviceInfoSet, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
      {
        LastError = GetLastError();
        if ( LastError != 122 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v16 = 18;
            goto LABEL_66;
          }
          goto LABEL_67;
        }
        v2 = v21;
      }
      if ( v8 )
        CoTaskMemFree(v8);
      v10 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)CoTaskMemAlloc(RequiredSize);
      v8 = v10;
      if ( !v10 )
      {
        LastError = -2147024882;
        goto LABEL_74;
      }
      memset_0(v10, 0, RequiredSize);
      v11 = DeviceInfoSet;
      v8->cbSize = 8;
      memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
      DeviceInfoData.cbSize = 32;
      if ( !SetupDiGetDeviceInterfaceDetailW(v11, &DeviceInterfaceData, v8, RequiredSize, 0, &DeviceInfoData) )
      {
        LastError = GetLastError();
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = 19;
          goto LABEL_66;
        }
        goto LABEL_67;
      }
      if ( v9 != -1 )
        CloseHandle((HANDLE)v9);
      FileW = CreateFileW(v8->DevicePath, 0, 3u, 0, 3u, 0, 0);
      hObject = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        v13 = GetLastError();
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_f71243d0ae613dd472d921e654574465_Traceguids,
            (_DWORD)v8 + 4,
            v13);
        }
      }
      else
      {
        OutBuffer = 0;
        v27 = 0;
        if ( DeviceIoControl(FileW, 0x2D1080u, 0, 0, &OutBuffer, 0xCu, &RequiredSize, 0) )
        {
          if ( HIDWORD(OutBuffer) == v20 )
          {
            if ( SetupDiGetDeviceRegistryPropertyW(
                   DeviceInfoSet,
                   &DeviceInfoData,
                   0x1Fu,
                   0,
                   PropertyBuffer,
                   4u,
                   &RequiredSize) )
            {
              LastError = 0;
              if ( *(_DWORD *)PropertyBuffer != 1 )
                *v25 = 1;
            }
            else
            {
              v17 = GetLastError();
              LastError = v17;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_Sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  22,
                  (unsigned int)&WPP_f71243d0ae613dd472d921e654574465_Traceguids,
                  (_DWORD)v8 + 4,
                  v17);
              }
              if ( LastError > 0 )
                LastError = (unsigned __int16)LastError | 0x80070000;
            }
            v9 = (__int64)hObject;
            goto LABEL_43;
          }
        }
        else
        {
          v14 = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              (unsigned int)&WPP_f71243d0ae613dd472d921e654574465_Traceguids,
              (_DWORD)v8 + 4,
              v14);
          }
        }
      }
      v9 = (__int64)hObject;
      ++v2;
      ClassDevsW = DeviceInfoSet;
    }
    LastError = GetLastError();
    if ( LastError == 259 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
      }
      LastError = -2147418113;
    }
    else
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = 17;
LABEL_66:
        WPP_SF_d(v15[2], v16, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
      }
LABEL_67:
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
LABEL_74:
    if ( v9 != -1 )
LABEL_43:
      CloseHandle((HANDLE)v9);
    if ( v8 )
      CoTaskMemFree(v8);
    SetupDiDestroyDeviceInfoList(DeviceInfoSet);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v3 = v20;
    goto LABEL_47;
  }
  LastError = GetLastError();
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  v7 = LastError < 0;
  if ( LastError > 0 )
  {
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_47:
    v7 = LastError < 0;
  }
  if ( v7 && v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) >= 2u )
    WPP_SF_LD(v6[2], 24, &WPP_f71243d0ae613dd472d921e654574465_Traceguids, v3, LastError);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1401169a8  mov     [rsp-8+arg_10], rbx
0x1401169ad  push    rbp
0x1401169ae  push    r12
0x1401169b0  push    r13
0x1401169b2  push    r14
0x1401169b4  push    r15
0x1401169b6  lea     rbp, [rsp-37h]
0x1401169bb  sub     rsp, 0C0h
0x1401169c2  mov     rax, cs:__security_cookie
0x1401169c9  xor     rax, rsp
0x1401169cc  mov     [rbp+57h+var_28], rax
0x1401169d0  xor     ebx, ebx
0x1401169d2  mov     [rbp+57h+var_9C], ecx
0x1401169d5  mov     r12d, ecx
0x1401169d8  mov     [rbp+57h+var_80], rdx
0x1401169dc  xor     ecx, ecx
0x1401169de  mov     [rdx], bl
0x1401169e0  xorps   xmm0, xmm0
0x1401169e3  mov     [rbp+57h+OutBuffer], rcx
0x1401169e7  xorps   xmm1, xmm1
0x1401169ea  mov     [rbp+57h+var_70], ecx
0x1401169ed  lea     r9d, [rbx+12h]; Flags
0x1401169f1  mov     [rbp+57h+RequiredSize], ebx
0x1401169f4  xor     r8d, r8d; hwndParent
0x1401169f7  mov     dword ptr [rbp+57h+PropertyBuffer], ebx
0x1401169fa  xor     edx, edx; Enumerator
0x1401169fc  lea     rcx, GUID_DEVINTERFACE_DISK; ClassGuid
0x140116a03  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm0
0x140116a07  movups  xmmword ptr [rbp+57h+var_68.InterfaceClassGuid.Data4+4], xmm0
0x140116a0b  movups  xmmword ptr [rbp+57h+var_48.cbSize], xmm1
0x140116a0f  movups  xmmword ptr [rbp+57h+var_48.ClassGuid.Data4+4], xmm1
0x140116a13  call    cs:__imp_SetupDiGetClassDevsW
0x140116a19  mov     [rbp+57h+DeviceInfoSet], rax
0x140116a1d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140116a21  jnz     short loc_140116A82
0x140116a23  call    cs:__imp_GetLastError
0x140116a29  mov     ebx, eax
0x140116a2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140116a32  lea     r14, WPP_GLOBAL_Control
0x140116a39  lea     r15, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140116a40  cmp     rcx, r14
0x140116a43  jz      short loc_140116A6C
0x140116a45  test    byte ptr [rcx+1Ch], 1
0x140116a49  jz      short loc_140116A6C
0x140116a4b  cmp     byte ptr [rcx+19h], 2
0x140116a4f  jb      short loc_140116A6C
0x140116a51  mov     rcx, [rcx+10h]
0x140116a55  mov     edx, 10h
0x140116a5a  mov     r9d, eax
0x140116a5d  mov     r8, r15
0x140116a60  call    WPP_SF_d
0x140116a65  mov     rcx, cs:WPP_GLOBAL_Control
0x140116a6c  test    ebx, ebx
0x140116a6e  jle     loc_140116D84
0x140116a74  movzx   ebx, bx
0x140116a77  or      ebx, 80070000h
0x140116a7d  jmp     loc_140116D82
0x140116a82  mov     r13, rbx
0x140116a85  lea     r14, WPP_GLOBAL_Control
0x140116a8c  or      r12, 0FFFFFFFFFFFFFFFFh
0x140116a90  lea     r15, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140116a97  xorps   xmm0, xmm0
0x140116a9a  mov     [rbp+57h+var_98], ebx
0x140116a9d  lea     rcx, [rbp+57h+var_68]
0x140116aa1  mov     r9d, ebx; MemberIndex
0x140116aa4  mov     [rsp+0E0h+DeviceInterfaceData], rcx; DeviceInterfaceData
0x140116aa9  lea     r8, GUID_DEVINTERFACE_DISK; InterfaceClassGuid
0x140116ab0  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm0
0x140116ab4  mov     rcx, rax; DeviceInfoSet
0x140116ab7  mov     [rbp+57h+var_68.cbSize], 20h ; ' '
0x140116abe  xor     edx, edx; DeviceInfoData
0x140116ac0  movups  xmmword ptr [rbp+57h+var_68.InterfaceClassGuid.Data4+4], xmm0
0x140116ac4  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x140116aca  test    eax, eax
0x140116acc  jz      loc_140116E1C
0x140116ad2  mov     rcx, [rbp+57h+DeviceInfoSet]; DeviceInfoSet
0x140116ad6  lea     rax, [rbp+57h+RequiredSize]
0x140116ada  mov     [rsp+0E0h+DeviceInfoData], 0; DeviceInfoData
0x140116ae3  lea     rdx, [rbp+57h+var_68]; DeviceInterfaceData
0x140116ae7  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x140116aea  mov     [rsp+0E0h+DeviceInterfaceData], rax; RequiredSize
0x140116aef  xor     r8d, r8d; DeviceInterfaceDetailData
0x140116af2  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x140116af8  test    eax, eax
0x140116afa  jnz     short loc_140116B10
0x140116afc  call    cs:__imp_GetLastError
0x140116b02  mov     ebx, eax
0x140116b04  cmp     eax, 7Ah ; 'z'
0x140116b07  jnz     loc_140116CA8
0x140116b0d  mov     ebx, [rbp+57h+var_98]
0x140116b10  test    r13, r13
0x140116b13  jz      short loc_140116B1E
0x140116b15  mov     rcx, r13; pv
0x140116b18  call    cs:__imp_CoTaskMemFree
0x140116b1e  mov     ecx, [rbp+57h+RequiredSize]; cb
0x140116b21  call    cs:__imp_CoTaskMemAlloc
0x140116b27  mov     r13, rax
0x140116b2a  test    rax, rax
0x140116b2d  jz      loc_140116E15
0x140116b33  mov     r8d, [rbp+57h+RequiredSize]; Size
0x140116b37  xor     edx, edx; Val
0x140116b39  mov     rcx, rax; void *
0x140116b3c  call    memset_0
0x140116b41  mov     rcx, [rbp+57h+DeviceInfoSet]; DeviceInfoSet
0x140116b45  lea     rax, [rbp+57h+var_48]
0x140116b49  mov     dword ptr [r13+0], 8
0x140116b51  lea     rdx, [rbp+57h+var_68]; DeviceInterfaceData
0x140116b55  mov     r9d, [rbp+57h+RequiredSize]; DeviceInterfaceDetailDataSize
0x140116b59  xorps   xmm0, xmm0
0x140116b5c  movups  xmmword ptr [rbp+57h+var_48.cbSize], xmm0
0x140116b60  mov     [rsp+0E0h+DeviceInfoData], rax; DeviceInfoData
0x140116b65  mov     r8, r13; DeviceInterfaceDetailData
0x140116b68  mov     [rbp+57h+var_48.cbSize], 20h ; ' '
0x140116b6f  mov     [rsp+0E0h+DeviceInterfaceData], 0; RequiredSize
0x140116b78  movups  xmmword ptr [rbp+57h+var_48.ClassGuid.Data4+4], xmm0
0x140116b7c  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x140116b82  test    eax, eax
0x140116b84  jz      loc_140116DEE
0x140116b8a  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140116b8e  jz      short loc_140116B99
0x140116b90  mov     rcx, r12; hObject
0x140116b93  call    cs:__imp_CloseHandle
0x140116b99  mov     eax, 3
0x140116b9e  mov     [rsp+0E0h+hTemplateFile], 0; hTemplateFile
0x140116ba7  lea     r12, [r13+4]
0x140116bab  mov     dword ptr [rsp+0E0h+DeviceInfoData], 0; dwFlagsAndAttributes
0x140116bb3  mov     r8d, eax; dwShareMode
0x140116bb6  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], eax; dwCreationDisposition
0x140116bba  mov     rcx, r12; lpFileName
0x140116bbd  xor     r9d, r9d; lpSecurityAttributes
0x140116bc0  xor     edx, edx; dwDesiredAccess
0x140116bc2  call    cs:__imp_CreateFileW
0x140116bc8  mov     [rbp+57h+hObject], rax
0x140116bcc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140116bd0  jnz     short loc_140116C19
0x140116bd2  call    cs:__imp_GetLastError
0x140116bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140116bdf  cmp     rcx, r14
0x140116be2  jz      loc_140116C99
0x140116be8  test    byte ptr [rcx+1Ch], 1
0x140116bec  jz      loc_140116C99
0x140116bf2  cmp     byte ptr [rcx+19h], 3
0x140116bf6  jb      loc_140116C99
0x140116bfc  mov     rcx, [rcx+10h]
0x140116c00  mov     edx, 14h
0x140116c05  mov     r9, r12
0x140116c08  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], eax
0x140116c0c  mov     r8, r15
0x140116c0f  call    WPP_SF_Sd
0x140116c14  jmp     loc_140116C99
0x140116c19  xor     ecx, ecx
0x140116c1b  xor     r9d, r9d; nInBufferSize
0x140116c1e  mov     [rsp+0E0h+lpOverlapped], rcx; lpOverlapped
0x140116c23  xor     r8d, r8d; lpInBuffer
0x140116c26  mov     [rbp+57h+OutBuffer], rcx
0x140116c2a  mov     edx, 2D1080h; dwIoControlCode
0x140116c2f  mov     [rbp+57h+var_70], ecx
0x140116c32  lea     rcx, [rbp+57h+RequiredSize]
0x140116c36  mov     [rsp+0E0h+hTemplateFile], rcx; lpBytesReturned
0x140116c3b  lea     rcx, [rbp+57h+OutBuffer]
0x140116c3f  mov     dword ptr [rsp+0E0h+DeviceInfoData], 0Ch; nOutBufferSize
0x140116c47  mov     [rsp+0E0h+DeviceInterfaceData], rcx; lpOutBuffer
0x140116c4c  mov     rcx, rax; hDevice
0x140116c4f  call    cs:__imp_DeviceIoControl
0x140116c55  test    eax, eax
0x140116c57  jnz     short loc_140116C91
0x140116c59  call    cs:__imp_GetLastError
0x140116c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140116c66  cmp     rcx, r14
0x140116c69  jz      short loc_140116C99
0x140116c6b  test    byte ptr [rcx+1Ch], 1
0x140116c6f  jz      short loc_140116C99
0x140116c71  cmp     byte ptr [rcx+19h], 3
0x140116c75  jb      short loc_140116C99
0x140116c77  mov     rcx, [rcx+10h]
0x140116c7b  mov     edx, 15h
0x140116c80  mov     r9, r12
0x140116c83  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], eax
0x140116c87  mov     r8, r15
0x140116c8a  call    WPP_SF_Sd
0x140116c8f  jmp     short loc_140116C99
0x140116c91  mov     eax, [rbp+57h+var_9C]
0x140116c94  cmp     dword ptr [rbp+57h+OutBuffer+4], eax
0x140116c97  jz      short loc_140116CD6
0x140116c99  mov     r12, [rbp+57h+hObject]
0x140116c9d  inc     ebx
0x140116c9f  mov     rax, [rbp+57h+DeviceInfoSet]
0x140116ca3  jmp     loc_140116A97
0x140116ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x140116caf  cmp     rcx, r14
0x140116cb2  jz      loc_140116E57
0x140116cb8  test    byte ptr [rcx+1Ch], 1
0x140116cbc  jz      loc_140116E57
0x140116cc2  cmp     byte ptr [rcx+19h], 2
0x140116cc6  jb      loc_140116E57
0x140116ccc  mov     edx, 12h
0x140116cd1  jmp     loc_140116E48
0x140116cd6  mov     rcx, [rbp+57h+DeviceInfoSet]; DeviceInfoSet
0x140116cda  lea     rax, [rbp+57h+RequiredSize]
0x140116cde  mov     [rsp+0E0h+hTemplateFile], rax; RequiredSize
0x140116ce3  lea     rdx, [rbp+57h+var_48]; DeviceInfoData
0x140116ce7  xor     r9d, r9d; PropertyRegDataType
0x140116cea  mov     dword ptr [rsp+0E0h+DeviceInfoData], 4; PropertyBufferSize
0x140116cf2  lea     rax, [rbp+57h+PropertyBuffer]
0x140116cf6  mov     [rsp+0E0h+DeviceInterfaceData], rax; PropertyBuffer
0x140116cfb  lea     r8d, [r9+1Fh]; Property
0x140116cff  call    cs:__imp_SetupDiGetDeviceRegistryPropertyW
0x140116d05  test    eax, eax
0x140116d07  jnz     loc_140116DD6
0x140116d0d  call    cs:__imp_GetLastError
0x140116d13  mov     ebx, eax
0x140116d15  mov     rcx, cs:WPP_GLOBAL_Control
0x140116d1c  cmp     rcx, r14
0x140116d1f  jz      short loc_140116D45
0x140116d21  test    byte ptr [rcx+1Ch], 1
0x140116d25  jz      short loc_140116D45
0x140116d27  cmp     byte ptr [rcx+19h], 2
0x140116d2b  jb      short loc_140116D45
0x140116d2d  mov     rcx, [rcx+10h]
0x140116d31  mov     edx, 16h
0x140116d36  mov     r9, r12
0x140116d39  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], eax
0x140116d3d  mov     r8, r15
0x140116d40  call    WPP_SF_Sd
0x140116d45  test    ebx, ebx
0x140116d47  jle     short loc_140116D52
0x140116d49  movzx   ebx, bx
0x140116d4c  or      ebx, 80070000h
0x140116d52  mov     r12, [rbp+57h+hObject]
0x140116d56  mov     rcx, r12; hObject
0x140116d59  call    cs:__imp_CloseHandle
0x140116d5f  test    r13, r13
0x140116d62  jz      short loc_140116D6D
0x140116d64  mov     rcx, r13; pv
0x140116d67  call    cs:__imp_CoTaskMemFree
0x140116d6d  mov     rcx, [rbp+57h+DeviceInfoSet]; DeviceInfoSet
0x140116d71  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x140116d77  mov     rcx, cs:WPP_GLOBAL_Control
0x140116d7e  mov     r12d, [rbp+57h+var_9C]
0x140116d82  test    ebx, ebx
0x140116d84  jns     short loc_140116DAF
0x140116d86  cmp     rcx, r14
0x140116d89  jz      short loc_140116DAF
0x140116d8b  test    byte ptr [rcx+1Ch], 1
0x140116d8f  jz      short loc_140116DAF
0x140116d91  cmp     byte ptr [rcx+19h], 2
0x140116d95  jb      short loc_140116DAF
0x140116d97  mov     rcx, [rcx+10h]
0x140116d9b  mov     edx, 18h
0x140116da0  mov     r9d, r12d
0x140116da3  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], ebx
0x140116da7  mov     r8, r15
0x140116daa  call    WPP_SF_LD
0x140116daf  mov     eax, ebx
0x140116db1  mov     rcx, [rbp+57h+var_28]
0x140116db5  xor     rcx, rsp; StackCookie
0x140116db8  call    __security_check_cookie
0x140116dbd  mov     rbx, [rsp+0E0h+arg_10]
0x140116dc5  add     rsp, 0C0h
0x140116dcc  pop     r15
0x140116dce  pop     r14
0x140116dd0  pop     r13
0x140116dd2  pop     r12
0x140116dd4  pop     rbp
0x140116dd5  retn
0x140116dd6  xor     ebx, ebx
0x140116dd8  cmp     dword ptr [rbp+57h+PropertyBuffer], 1
0x140116ddc  jz      loc_140116D52
0x140116de2  mov     rax, [rbp+57h+var_80]
0x140116de6  mov     byte ptr [rax], 1
0x140116de9  jmp     loc_140116D52
0x140116dee  call    cs:__imp_GetLastError
0x140116df4  mov     ebx, eax
0x140116df6  mov     rcx, cs:WPP_GLOBAL_Control
0x140116dfd  cmp     rcx, r14
0x140116e00  jz      short loc_140116E57
0x140116e02  test    byte ptr [rcx+1Ch], 1
0x140116e06  jz      short loc_140116E57
0x140116e08  cmp     byte ptr [rcx+19h], 2
0x140116e0c  jb      short loc_140116E57
0x140116e0e  mov     edx, 13h
0x140116e13  jmp     short loc_140116E48
0x140116e15  mov     ebx, 8007000Eh
0x140116e1a  jmp     short loc_140116E98
0x140116e1c  call    cs:__imp_GetLastError
0x140116e22  mov     ebx, eax
0x140116e24  cmp     eax, 103h
0x140116e29  jz      short loc_140116E66
0x140116e2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140116e32  cmp     rcx, r14
0x140116e35  jz      short loc_140116E57
0x140116e37  test    byte ptr [rcx+1Ch], 1
0x140116e3b  jz      short loc_140116E57
0x140116e3d  cmp     byte ptr [rcx+19h], 2
0x140116e41  jb      short loc_140116E57
0x140116e43  mov     edx, 11h
0x140116e48  mov     rcx, [rcx+10h]
0x140116e4c  mov     r9d, ebx
0x140116e4f  mov     r8, r15
0x140116e52  call    WPP_SF_d
  ... truncated ...
```
