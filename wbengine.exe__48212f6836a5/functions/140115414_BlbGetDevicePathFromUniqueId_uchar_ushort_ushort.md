# BlbGetDevicePathFromUniqueId(uchar *,ushort,ushort * *)

- ea: `0x140115414`
- end: `0x1401159c7`
- name: `?BlbGetDevicePathFromUniqueId@@YAJPEAEGPEAPEAG@Z`
- size: `1459`
- prototype: `__int64 __fastcall(unsigned __int8 *Buf2, unsigned __int16, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `14`
- tags: `service_task, installer_update`

## callers

- `0x1400578e0`
- `0x140058444`

## callees

- `0x140006ca8`
- `0x140007ad3`
- `0x14000bb24`
- `0x14000bb4c`
- `0x140014200`
- `0x140014260`
- `0x14003c434`
- `0x14003c54c`
- `0x1400889f0`
- `0x14008bd48`
- `0x140115414`
- `0x140117318`
- `0x140134cc6`
- `0x140134d20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140115511`
- `KERNEL32!GetLastError` at `0x1401155ff`
- `KERNEL32!GetLastError` at `0x14011583c`
- `KERNEL32!GetLastError` at `0x140115884`
- `KERNEL32!GetLastError` at `0x140115511`
- `KERNEL32!GetLastError` at `0x1401155ff`
- `KERNEL32!GetLastError` at `0x14011583c`
- `KERNEL32!GetLastError` at `0x140115884`
- `ole32!CoTaskMemAlloc` at `0x140115613`
- `ole32!CoTaskMemAlloc` at `0x140115613`
- `ole32!CoTaskMemFree` at `0x14011558c`
- `ole32!CoTaskMemFree` at `0x1401155a0`
- `ole32!CoTaskMemFree` at `0x14011592e`
- `ole32!CoTaskMemFree` at `0x140115943`
- `ole32!CoTaskMemFree` at `0x140115972`
- `ole32!CoTaskMemFree` at `0x14011558c`
- `ole32!CoTaskMemFree` at `0x1401155a0`
- `ole32!CoTaskMemFree` at `0x14011592e`
- `ole32!CoTaskMemFree` at `0x140115943`
- `ole32!CoTaskMemFree` at `0x140115972`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140115959`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x140115959`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1401155c8`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1401155c8`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1401154fe`
- `SETUPAPI!SetupDiGetClassDevsW` at `0x1401154fe`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1401155f5`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x140115699`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x1401155f5`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x140115699`

## string_xrefs

- `0x1401154b6`: `pwszDevicePath`

## pseudocode

```c
__int64 __fastcall BlbGetDevicePathFromUniqueId(unsigned __int8 *Buf2, unsigned __int16 a2, unsigned __int16 **a3)
{
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v6; // r14
  void *v7; // rsi
  signed int VolumeNameFromUniquId; // ebx
  HDEVINFO v9; // rdi
  PVOID *v10; // rcx
  DWORD i; // r15d
  signed int v12; // eax
  struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *v13; // rax
  int VolumeUniqueId; // eax
  __int64 v15; // rdx
  signed int v16; // eax
  signed int LastError; // eax
  unsigned __int16 *v18; // rdi
  unsigned __int16 v20[2]; // [rsp+30h] [rbp-59h] BYREF
  DWORD RequiredSize; // [rsp+34h] [rbp-55h] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+38h] [rbp-51h]
  void *Buf1; // [rsp+40h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-41h] BYREF
  void *Buf2a; // [rsp+50h] [rbp-39h]
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+58h] [rbp-31h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+78h] [rbp-11h] BYREF

  Buf2a = Buf2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
  }
  DeviceInfoSet = (HDEVINFO)-1LL;
  RequiredSize = 0;
  pv = 0;
  Buf1 = 0;
  v6 = 0;
  v20[0] = 0;
  v7 = 0;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  if ( !a3 )
    BlbAssert("base\\stor\\blb\\engine\\blbengutils\\blbdeviceutils.cpp", 0x280u, "pwszDevicePath");
  *a3 = 0;
  VolumeNameFromUniquId = BlbutilGetVolumeNameFromUniquId(Buf2, a2, (unsigned __int16 **)&pv);
  if ( VolumeNameFromUniquId >= 0 )
  {
LABEL_71:
    v18 = (unsigned __int16 *)pv;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_f71243d0ae613dd472d921e654574465_Traceguids, pv);
    }
    *a3 = v18;
    pv = 0;
  }
  else
  {
    DeviceInfoSet = SetupDiGetClassDevsW(&GUID_DEVINTERFACE_HIDDEN_VOLUME, 0, 0, 0x12u);
    v9 = DeviceInfoSet;
    if ( DeviceInfoSet == (HDEVINFO)-1LL )
    {
      VolumeNameFromUniquId = GetLastError();
      v10 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( VolumeNameFromUniquId > 0 )
        VolumeNameFromUniquId = (unsigned __int16)VolumeNameFromUniquId | 0x80070000;
      goto LABEL_84;
    }
    for ( i = 0; ; ++i )
    {
      RequiredSize = 0;
      memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
      memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
      if ( v7 )
      {
        CoTaskMemFree(v7);
        v7 = 0;
        Buf1 = 0;
      }
      if ( v6 )
      {
        CoTaskMemFree(v6);
        v6 = 0;
      }
      DeviceInterfaceData.cbSize = 32;
      if ( !SetupDiEnumDeviceInterfaces(v9, 0, &GUID_DEVINTERFACE_HIDDEN_VOLUME, i, &DeviceInterfaceData) )
      {
        LastError = GetLastError();
        if ( LastError == 259 )
          goto LABEL_71;
        if ( LastError > 0 )
          VolumeNameFromUniquId = (unsigned __int16)LastError | 0x80070000;
        else
          VolumeNameFromUniquId = LastError;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 37;
          goto LABEL_43;
        }
        goto LABEL_78;
      }
      if ( !SetupDiGetDeviceInterfaceDetailW(v9, &DeviceInterfaceData, 0, 0, &RequiredSize, 0) )
      {
        v12 = GetLastError();
        VolumeNameFromUniquId = v12;
        if ( v12 != 122 )
        {
          if ( v12 > 0 )
            VolumeNameFromUniquId = (unsigned __int16)v12 | 0x80070000;
          v10 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v15 = 38;
LABEL_43:
            WPP_SF_dd(v10[2], v15, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
            goto LABEL_77;
          }
          goto LABEL_78;
        }
      }
      v13 = (struct _SP_DEVICE_INTERFACE_DETAIL_DATA_W *)CoTaskMemAlloc(RequiredSize);
      v6 = v13;
      if ( !v13 )
      {
        VolumeNameFromUniquId = -2147024882;
        goto LABEL_77;
      }
      memset_0(v13, 0, RequiredSize);
      v6->cbSize = 8;
      DeviceInfoData.cbSize = 32;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
      }
      if ( !SetupDiGetDeviceInterfaceDetailW(v9, &DeviceInterfaceData, v6, RequiredSize, 0, &DeviceInfoData) )
      {
        v16 = GetLastError();
        VolumeNameFromUniquId = v16;
        if ( v16 > 0 )
          VolumeNameFromUniquId = (unsigned __int16)v16 | 0x80070000;
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 40;
          goto LABEL_43;
        }
        goto LABEL_78;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_dS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_f71243d0ae613dd472d921e654574465_Traceguids,
          i,
          (__int64)v6->DevicePath);
      }
      VolumeUniqueId = BlbutilQueryVolumeUniqueId(v6->DevicePath, (unsigned __int8 **)&Buf1, v20);
      VolumeNameFromUniquId = VolumeUniqueId;
      if ( VolumeUniqueId < 0 )
      {
        v10 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)&WPP_f71243d0ae613dd472d921e654574465_Traceguids,
            (_DWORD)v6 + 4,
            VolumeUniqueId);
          v7 = Buf1;
          goto LABEL_76;
        }
        v7 = Buf1;
        v9 = DeviceInfoSet;
        goto LABEL_78;
      }
      v7 = Buf1;
      if ( v20[0] == a2 && !memcmp_0(Buf1, Buf2a, v20[0]) )
        break;
      v9 = DeviceInfoSet;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        43,
        (unsigned int)&WPP_f71243d0ae613dd472d921e654574465_Traceguids,
        (_DWORD)v6 + 4,
        i);
    }
    VolumeNameFromUniquId = BlbutilDuplicateString(v6->DevicePath, (unsigned __int16 **)&pv, 0);
    if ( VolumeNameFromUniquId >= 0 )
      goto LABEL_71;
  }
LABEL_76:
  v9 = DeviceInfoSet;
LABEL_77:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_78:
  if ( v7 )
  {
    CoTaskMemFree(v7);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    CoTaskMemFree(v6);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 != (HDEVINFO)-1LL )
  {
    SetupDiDestroyDeviceInfoList(v9);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_84:
  if ( pv )
  {
    CoTaskMemFree(pv);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    WPP_SF_(v10[2], 45, &WPP_f71243d0ae613dd472d921e654574465_Traceguids);
  return (unsigned int)VolumeNameFromUniquId;
}

```

## disassembly

```asm
0x140115414  push    rbp
0x140115416  push    rbx
0x140115417  push    rsi
0x140115418  push    rdi
0x140115419  push    r12
0x14011541b  push    r13
0x14011541d  push    r14
0x14011541f  push    r15
0x140115421  lea     rbp, [rsp-1Fh]
0x140115426  sub     rsp, 0A8h
0x14011542d  mov     rax, cs:__security_cookie
0x140115434  xor     rax, rsp
0x140115437  mov     [rbp+57h+var_48], rax
0x14011543b  mov     r13, r8
0x14011543e  mov     [rbp+57h+Buf2], rcx
0x140115442  movzx   r12d, dx
0x140115446  mov     rbx, rcx
0x140115449  mov     rcx, cs:WPP_GLOBAL_Control
0x140115450  lea     r15, WPP_GLOBAL_Control
0x140115457  cmp     rcx, r15
0x14011545a  jz      short loc_14011547D
0x14011545c  test    byte ptr [rcx+1Ch], 1
0x140115460  jz      short loc_14011547D
0x140115462  cmp     byte ptr [rcx+19h], 4
0x140115466  jb      short loc_14011547D
0x140115468  mov     rcx, [rcx+10h]
0x14011546c  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140115473  mov     edx, 23h ; '#'
0x140115478  call    WPP_SF_
0x14011547d  xor     edi, edi
0x14011547f  mov     [rbp+57h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x140115487  mov     [rbp+57h+RequiredSize], edi
0x14011548a  xorps   xmm0, xmm0
0x14011548d  mov     [rbp+57h+pv], rdi
0x140115491  xorps   xmm1, xmm1
0x140115494  mov     [rbp+57h+Buf1], rdi
0x140115498  mov     r14d, edi
0x14011549b  mov     [rbp+57h+var_B0], di
0x14011549f  mov     esi, edi
0x1401154a1  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x1401154a5  movups  xmmword ptr [rbp+57h+var_88.InterfaceClassGuid.Data4+4], xmm0
0x1401154a9  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm1
0x1401154ad  movups  xmmword ptr [rbp+57h+var_68.ClassGuid.Data4+4], xmm1
0x1401154b1  test    r13, r13
0x1401154b4  jnz     short loc_1401154CE
0x1401154b6  lea     r8, aPwszdevicepath; "pwszDevicePath"
0x1401154bd  mov     edx, 280h; unsigned int
0x1401154c2  lea     rcx, aBaseStorBlbEng_29; "base\\stor\\blb\\engine\\blbengutils\\b"...
0x1401154c9  call    ?BlbAssert@@YAXPEADI0@Z; BlbAssert(char *,uint,char *)
0x1401154ce  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x1401154d2  mov     [r13+0], rdi
0x1401154d6  movzx   edx, r12w; unsigned __int16
0x1401154da  mov     rcx, rbx; Buf2
0x1401154dd  call    ?BlbutilGetVolumeNameFromUniquId@@YAJPEAEGPEAPEAG@Z; BlbutilGetVolumeNameFromUniquId(uchar *,ushort,ushort * *)
0x1401154e2  mov     ebx, eax
0x1401154e4  test    eax, eax
0x1401154e6  jns     loc_1401158DB
0x1401154ec  mov     r9d, 12h; Flags
0x1401154f2  lea     rcx, GUID_DEVINTERFACE_HIDDEN_VOLUME; ClassGuid
0x1401154f9  xor     r8d, r8d; hwndParent
0x1401154fc  xor     edx, edx; Enumerator
0x1401154fe  call    cs:__imp_SetupDiGetClassDevsW
0x140115504  mov     [rbp+57h+DeviceInfoSet], rax
0x140115508  mov     rdi, rax
0x14011550b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14011550f  jnz     short loc_140115564
0x140115511  call    cs:__imp_GetLastError
0x140115517  mov     ebx, eax
0x140115519  mov     rcx, cs:WPP_GLOBAL_Control
0x140115520  cmp     rcx, r15
0x140115523  jz      short loc_14011554E
0x140115525  test    byte ptr [rcx+1Ch], 1
0x140115529  jz      short loc_14011554E
0x14011552b  cmp     byte ptr [rcx+19h], 2
0x14011552f  jb      short loc_14011554E
0x140115531  mov     rcx, [rcx+10h]
0x140115535  lea     edx, [rdi+25h]
0x140115538  mov     r9d, eax
0x14011553b  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140115542  call    WPP_SF_d
0x140115547  mov     rcx, cs:WPP_GLOBAL_Control
0x14011554e  test    ebx, ebx
0x140115550  jle     loc_140115966
0x140115556  movzx   ebx, bx
0x140115559  or      ebx, 80070000h
0x14011555f  jmp     loc_140115966
0x140115564  xor     r15d, r15d
0x140115567  mov     [rbp+57h+RequiredSize], 0
0x14011556e  xorps   xmm0, xmm0
0x140115571  xorps   xmm1, xmm1
0x140115574  movups  xmmword ptr [rbp+57h+var_88.cbSize], xmm0
0x140115578  movups  xmmword ptr [rbp+57h+var_88.InterfaceClassGuid.Data4+4], xmm0
0x14011557c  movups  xmmword ptr [rbp+57h+var_68.cbSize], xmm1
0x140115580  movups  xmmword ptr [rbp+57h+var_68.ClassGuid.Data4+4], xmm1
0x140115584  test    rsi, rsi
0x140115587  jz      short loc_140115598
0x140115589  mov     rcx, rsi; pv
0x14011558c  call    cs:__imp_CoTaskMemFree
0x140115592  xor     esi, esi
0x140115594  mov     [rbp+57h+Buf1], rsi
0x140115598  test    r14, r14
0x14011559b  jz      short loc_1401155A9
0x14011559d  mov     rcx, r14; pv
0x1401155a0  call    cs:__imp_CoTaskMemFree
0x1401155a6  xor     r14d, r14d
0x1401155a9  lea     rax, [rbp+57h+var_88]
0x1401155ad  mov     [rbp+57h+var_88.cbSize], 20h ; ' '
0x1401155b4  mov     r9d, r15d; MemberIndex
0x1401155b7  mov     [rsp+0E0h+DeviceInterfaceData], rax; DeviceInterfaceData
0x1401155bc  lea     r8, GUID_DEVINTERFACE_HIDDEN_VOLUME; InterfaceClassGuid
0x1401155c3  xor     edx, edx; DeviceInfoData
0x1401155c5  mov     rcx, rdi; DeviceInfoSet
0x1401155c8  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x1401155ce  test    eax, eax
0x1401155d0  jz      loc_140115884
0x1401155d6  lea     rax, [rbp+57h+RequiredSize]
0x1401155da  mov     [rsp+0E0h+DeviceInfoData], 0; DeviceInfoData
0x1401155e3  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x1401155e6  mov     [rsp+0E0h+DeviceInterfaceData], rax; RequiredSize
0x1401155eb  xor     r8d, r8d; DeviceInterfaceDetailData
0x1401155ee  lea     rdx, [rbp+57h+var_88]; DeviceInterfaceData
0x1401155f2  mov     rcx, rdi; DeviceInfoSet
0x1401155f5  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x1401155fb  test    eax, eax
0x1401155fd  jnz     short loc_140115610
0x1401155ff  call    cs:__imp_GetLastError
0x140115605  mov     ebx, eax
0x140115607  cmp     eax, 7Ah ; 'z'
0x14011560a  jnz     loc_14011572A
0x140115610  mov     ecx, [rbp+57h+RequiredSize]; cb
0x140115613  call    cs:__imp_CoTaskMemAlloc
0x140115619  mov     r14, rax
0x14011561c  test    rax, rax
0x14011561f  jz      loc_14011587A
0x140115625  mov     r8d, [rbp+57h+RequiredSize]; Size
0x140115629  xor     edx, edx; Val
0x14011562b  mov     rcx, rax; void *
0x14011562e  call    memset_0
0x140115633  mov     dword ptr [r14], 8
0x14011563a  mov     [rbp+57h+var_68.cbSize], 20h ; ' '
0x140115641  mov     rcx, cs:WPP_GLOBAL_Control
0x140115648  lea     rbx, WPP_GLOBAL_Control
0x14011564f  cmp     rcx, rbx
0x140115652  jz      short loc_140115679
0x140115654  test    byte ptr [rcx+1Ch], 1
0x140115658  jz      short loc_140115679
0x14011565a  cmp     byte ptr [rcx+19h], 4
0x14011565e  jb      short loc_140115679
0x140115660  mov     r9d, [rbp+57h+RequiredSize]
0x140115664  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x14011566b  mov     rcx, [rcx+10h]
0x14011566f  mov     edx, 27h ; '''
0x140115674  call    WPP_SF_d
0x140115679  mov     r9d, [rbp+57h+RequiredSize]; DeviceInterfaceDetailDataSize
0x14011567d  lea     rax, [rbp+57h+var_68]
0x140115681  mov     [rsp+0E0h+DeviceInfoData], rax; DeviceInfoData
0x140115686  lea     rdx, [rbp+57h+var_88]; DeviceInterfaceData
0x14011568a  mov     r8, r14; DeviceInterfaceDetailData
0x14011568d  mov     [rsp+0E0h+DeviceInterfaceData], 0; RequiredSize
0x140115696  mov     rcx, rdi; DeviceInfoSet
0x140115699  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x14011569f  test    eax, eax
0x1401156a1  jz      loc_14011583C
0x1401156a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1401156ae  cmp     rcx, rbx
0x1401156b1  jz      short loc_1401156E0
0x1401156b3  test    byte ptr [rcx+1Ch], 1
0x1401156b7  jz      short loc_1401156E0
0x1401156b9  cmp     byte ptr [rcx+19h], 4
0x1401156bd  jb      short loc_1401156E0
0x1401156bf  mov     rcx, [rcx+10h]
0x1401156c3  lea     rax, [r14+4]
0x1401156c7  mov     edx, 29h ; ')'
0x1401156cc  mov     [rsp+0E0h+DeviceInterfaceData], rax
0x1401156d1  mov     r9d, r15d
0x1401156d4  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x1401156db  call    WPP_SF_dS
0x1401156e0  lea     rdi, [r14+4]
0x1401156e4  mov     rcx, rdi; unsigned __int16 *
0x1401156e7  lea     r8, [rbp+57h+var_B0]; unsigned __int16 *
0x1401156eb  lea     rdx, [rbp+57h+Buf1]; unsigned __int8 **
0x1401156ef  call    ?BlbutilQueryVolumeUniqueId@@YAJPEAGPEAPEAEAEAG@Z; BlbutilQueryVolumeUniqueId(ushort *,uchar * *,ushort &)
0x1401156f4  mov     ebx, eax
0x1401156f6  test    eax, eax
0x1401156f8  js      loc_1401157EB
0x1401156fe  mov     rsi, [rbp+57h+Buf1]
0x140115702  cmp     [rbp+57h+var_B0], r12w
0x140115707  jnz     short loc_14011571E
0x140115709  movzx   r8d, [rbp+57h+var_B0]; Size
0x14011570e  mov     rcx, rsi; Buf1
0x140115711  mov     rdx, [rbp+57h+Buf2]; Buf2
0x140115715  call    memcmp_0
0x14011571a  test    eax, eax
0x14011571c  jz      short loc_14011578A
0x14011571e  mov     rdi, [rbp+57h+DeviceInfoSet]
0x140115722  inc     r15d
0x140115725  jmp     loc_140115567
0x14011572a  test    eax, eax
0x14011572c  jle     short loc_140115737
0x14011572e  movzx   ebx, ax
0x140115731  or      ebx, 80070000h
0x140115737  mov     rcx, cs:WPP_GLOBAL_Control
0x14011573e  lea     rax, WPP_GLOBAL_Control
0x140115745  cmp     rcx, rax
0x140115748  jz      loc_1401158CB
0x14011574e  test    byte ptr [rcx+1Ch], 1
0x140115752  jz      loc_1401158CB
0x140115758  cmp     byte ptr [rcx+19h], 2
0x14011575c  jb      loc_1401158CB
0x140115762  mov     edx, 26h ; '&'
0x140115767  mov     rcx, [rcx+10h]
0x14011576b  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140115772  mov     r9d, r15d
0x140115775  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], ebx
0x140115779  call    WPP_SF_dd
0x14011577e  lea     r15, WPP_GLOBAL_Control
0x140115785  jmp     loc_14011591F
0x14011578a  mov     rcx, cs:WPP_GLOBAL_Control
0x140115791  lea     rax, WPP_GLOBAL_Control
0x140115798  cmp     rcx, rax
0x14011579b  jz      short loc_1401157C6
0x14011579d  test    byte ptr [rcx+1Ch], 1
0x1401157a1  jz      short loc_1401157C6
0x1401157a3  cmp     byte ptr [rcx+19h], 4
0x1401157a7  jb      short loc_1401157C6
0x1401157a9  mov     rcx, [rcx+10h]
0x1401157ad  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x1401157b4  mov     edx, 2Bh ; '+'
0x1401157b9  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], r15d
0x1401157be  mov     r9, rdi
0x1401157c1  call    WPP_SF_Sd
0x1401157c6  xor     r8d, r8d; unsigned __int64
0x1401157c9  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x1401157cd  mov     rcx, rdi; unsigned __int16 *
0x1401157d0  call    ?BlbutilDuplicateString@@YAJPEBGPEAPEAG_K@Z; BlbutilDuplicateString(ushort const *,ushort * *,unsigned __int64)
0x1401157d5  lea     r15, WPP_GLOBAL_Control
0x1401157dc  mov     ebx, eax
0x1401157de  test    eax, eax
0x1401157e0  jns     loc_1401158DB
0x1401157e6  jmp     loc_14011591B
0x1401157eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1401157f2  lea     r15, WPP_GLOBAL_Control
0x1401157f9  cmp     rcx, r15
0x1401157fc  jz      short loc_14011582F
0x1401157fe  test    byte ptr [rcx+1Ch], 1
0x140115802  jz      short loc_14011582F
0x140115804  cmp     byte ptr [rcx+19h], 2
0x140115808  jb      short loc_14011582F
0x14011580a  mov     rcx, [rcx+10h]
0x14011580e  lea     r8, WPP_f71243d0ae613dd472d921e654574465_Traceguids
0x140115815  mov     edx, 2Ah ; '*'
0x14011581a  mov     dword ptr [rsp+0E0h+DeviceInterfaceData], eax
0x14011581e  mov     r9, rdi
0x140115821  call    WPP_SF_Sd
0x140115826  mov     rsi, [rbp+57h+Buf1]
0x14011582a  jmp     loc_14011591B
0x14011582f  mov     rsi, [rbp+57h+Buf1]
0x140115833  mov     rdi, [rbp+57h+DeviceInfoSet]
0x140115837  jmp     loc_140115926
0x14011583c  call    cs:__imp_GetLastError
0x140115842  mov     ebx, eax
0x140115844  test    eax, eax
0x140115846  jle     short loc_140115851
0x140115848  movzx   ebx, ax
0x14011584b  or      ebx, 80070000h
0x140115851  mov     rcx, cs:WPP_GLOBAL_Control
0x140115858  lea     rax, WPP_GLOBAL_Control
0x14011585f  cmp     rcx, rax
0x140115862  jz      short loc_1401158CB
0x140115864  test    byte ptr [rcx+1Ch], 1
0x140115868  jz      short loc_1401158CB
0x14011586a  cmp     byte ptr [rcx+19h], 2
0x14011586e  jb      short loc_1401158CB
0x140115870  mov     edx, 28h ; '('
0x140115875  jmp     loc_140115767
0x14011587a  mov     ebx, 8007000Eh
0x14011587f  jmp     loc_14011577E
0x140115884  call    cs:__imp_GetLastError
0x14011588a  cmp     eax, 103h
0x14011588f  jz      short loc_1401158D4
0x140115891  test    eax, eax
0x140115893  jg      short loc_140115899
0x140115895  mov     ebx, eax
0x140115897  jmp     short loc_1401158A2
0x140115899  movzx   ebx, ax
0x14011589c  or      ebx, 80070000h
0x1401158a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1401158a9  lea     rax, WPP_GLOBAL_Control
0x1401158b0  cmp     rcx, rax
0x1401158b3  jz      short loc_1401158CB
0x1401158b5  test    byte ptr [rcx+1Ch], 1
0x1401158b9  jz      short loc_1401158CB
0x1401158bb  cmp     byte ptr [rcx+19h], 2
0x1401158bf  jb      short loc_1401158CB
0x1401158c1  mov     edx, 25h ; '%'
0x1401158c6  jmp     loc_140115767
0x1401158cb  lea     r15, WPP_GLOBAL_Control
0x1401158d2  jmp     short loc_140115926
0x1401158d4  lea     r15, WPP_GLOBAL_Control
0x1401158db  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
