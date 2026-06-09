# DeviceInfoSet::AddDevNodeDevices(void)

- ea: `0x1800129fc`
- end: `0x180012ebe`
- name: `?AddDevNodeDevices@DeviceInfoSet@@AEAAXXZ`
- size: `1218`
- prototype: `void __fastcall(DeviceInfoSet *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008cac`

## callees

- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x1800113d8`
- `0x18001148c`
- `0x180011658`
- `0x1800119c8`
- `0x180011a94`
- `0x180011b50`
- `0x1800129fc`
- `0x180028f4c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002fc10`
- `0x18002fedc`
- `0x180033878`
- `0x180033884`
- `0x180033cc0`
- `0x1800775e4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180012e61`
- `ADVAPI32!RegCloseKey` at `0x180012e61`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180012ab1`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180012ab1`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180012a75`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180012e80`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180012a75`
- `SETUPAPI!SetupDiEnumDeviceInfo` at `0x180012e80`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180012c33`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180012c33`

## string_xrefs

- `0x180012dfa`: `The Device Info Set skipped devnode index %d, because its "Subclass" value is not of a compatible correct type.`
- `0x180012e28`: `The Device Info Set skipped devnode index %d, because its "Subclass" value is not of a compatible correct type.`

## pseudocode

```c
void __fastcall DeviceInfoSet::AddDevNodeDevices(DeviceInfoSet *this)
{
  void *v2; // rcx
  DWORD v3; // esi
  HKEY v4; // r14
  unsigned __int64 v5; // rdx
  unsigned __int64 v6; // rdx
  void *v7; // rcx
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  __int64 StringFromDevInterfaceProperty; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  unsigned __int64 v16; // rdx
  char *v17; // rbx
  void *v18; // rdx
  void **v19; // rax
  void *v20; // rdx
  __int64 v21; // rcx
  struct _SP_DEVICE_INTERFACE_DATA samDesired_8; // [rsp+38h] [rbp-D0h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData_8; // [rsp+58h] [rbp-B0h] BYREF
  GUID InterfaceClassGuid_8; // [rsp+78h] [rbp-90h] BYREF
  void **v25; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v26[37]; // [rsp+90h] [rbp-78h] BYREF
  int v27; // [rsp+1B8h] [rbp+B0h]
  DWORD cbSize; // [rsp+1C0h] [rbp+B8h]
  _BYTE v29[28]; // [rsp+1C4h] [rbp+BCh]
  DWORD v30; // [rsp+1E0h] [rbp+D8h]
  _BYTE v31[28]; // [rsp+1E4h] [rbp+DCh]
  __int64 v32; // [rsp+200h] [rbp+F8h]
  __int64 v33; // [rsp+208h] [rbp+100h]
  void **v34; // [rsp+218h] [rbp+110h] BYREF
  _BYTE v35[296]; // [rsp+220h] [rbp+118h] BYREF
  HKEY v36; // [rsp+348h] [rbp+240h]
  __int64 v37; // [rsp+350h] [rbp+248h]
  char v38; // [rsp+358h] [rbp+250h]
  __int64 v39; // [rsp+360h] [rbp+258h]
  int v40; // [rsp+368h] [rbp+260h]
  const unsigned __int64 *v41; // [rsp+378h] [rbp+270h] BYREF
  char v42; // [rsp+380h] [rbp+278h] BYREF
  wchar_t *String2; // [rsp+480h] [rbp+378h]
  const unsigned __int64 *v44; // [rsp+4A8h] [rbp+3A0h] BYREF
  char v45; // [rsp+4B0h] [rbp+3A8h] BYREF
  void *v46; // [rsp+5B0h] [rbp+4A8h]
  __int64 v47; // [rsp+5B8h] [rbp+4B0h]
  const unsigned __int64 *v48; // [rsp+5D8h] [rbp+4D0h] BYREF
  char v49; // [rsp+5E0h] [rbp+4D8h] BYREF
  void *v50; // [rsp+6E0h] [rbp+5D8h]
  const unsigned __int64 *v51; // [rsp+708h] [rbp+600h] BYREF
  char v52; // [rsp+710h] [rbp+608h] BYREF
  void *v53; // [rsp+810h] [rbp+708h]
  _QWORD v54[38]; // [rsp+838h] [rbp+730h] BYREF

  v2 = (void *)*((_QWORD *)this + 2);
  memset(&DeviceInfoData_8, 0, sizeof(DeviceInfoData_8));
  DeviceInfoData_8.cbSize = 32;
  InterfaceClassGuid_8 = GUID_DEVCLASS_IMAGE;
  v3 = 0;
  memset(&samDesired_8, 0, sizeof(samDesired_8));
  if ( SetupDiEnumDeviceInfo(v2, 0, &DeviceInfoData_8) )
  {
    do
    {
      v4 = SetupDiOpenDevRegKey(*((HDEVINFO *)this + 2), &DeviceInfoData_8, 1u, 0, 2u, 0x20019u);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v48, &Class);
      v34 = &CSimpleReg::`vftable';
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v35, &v48);
      v36 = v4;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v40 = 131097;
      CSimpleReg::Open((CSimpleReg *)&v34);
      v48 = &CSimpleStringBase<unsigned short>::`vftable';
      if ( v50 && v50 != &v49 )
        operator delete(v50, v5);
      if ( (unsigned int)DeviceInfoSet::IsCorrectDeviceClass(this, (struct CSimpleReg *)&v34, &DeviceInfoData_8, 0) )
      {
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v51, L"Device ID not found");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v44, L"DeviceID");
        CSimpleReg::Query(&v34, &v41, &v44, &v51);
        v44 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v46 && v46 != &v45 )
          operator delete(v46, v6);
        v46 = 0;
        v47 = 0;
        v51 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v53 && v53 != &v52 )
          operator delete(v53, v6);
        v7 = (void *)*((_QWORD *)this + 2);
        *(_QWORD *)&samDesired_8.Flags = 0;
        HIDWORD(samDesired_8.Reserved) = 0;
        samDesired_8.cbSize = 32;
        samDesired_8.InterfaceClassGuid = GUID_DEVCLASS_IMAGE;
        if ( !SetupDiEnumDeviceInterfaces(v7, &DeviceInfoData_8, &InterfaceClassGuid_8, 0, &samDesired_8) )
        {
          v8 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                         8,
                         0,
                         "The Device Info Set could not get the imaging interface data for device (%ws)",
                         String2);
          WriteDbgTraceInfoWI("DeviceInfoSet::AddDevNodeDevices", v8);
          WiaTrcLib::Free((WiaTrcLib *)v8, v9);
          v10 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           8,
                           0,
                           "The Device Info Set could not get the imaging interface data for device (%ws)",
                           String2);
          WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"DeviceInfoSet::AddDevNodeDevices", 4, v10);
          memset(&samDesired_8, 0, sizeof(samDesired_8));
        }
        if ( !wcscmp_0(L"Device ID not found", String2) )
        {
          StringFromDevInterfaceProperty = GetStringFromDevInterfaceProperty(
                                             (__int64)v54,
                                             *((void **)this + 2),
                                             &samDesired_8,
                                             &DEVPKEY_Device_InstanceId);
          CSimpleStringBase<unsigned short>::operator=(&v41, StringFromDevInterfaceProperty);
          v54[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(v54);
        }
        v25 = &DeviceInfoSet::DeviceCacheEntry::`vftable';
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v26, &v41);
        cbSize = DeviceInfoData_8.cbSize;
        *(GUID *)v29 = DeviceInfoData_8.ClassGuid;
        v27 = 1;
        v32 = 0;
        *(_OWORD *)&v29[12] = *(_OWORD *)&DeviceInfoData_8.ClassGuid.Data4[4];
        v33 = 0;
        v30 = samDesired_8.cbSize;
        *(GUID *)v31 = samDesired_8.InterfaceClassGuid;
        *(_OWORD *)&v31[12] = *(_OWORD *)&samDesired_8.InterfaceClassGuid.Data4[4];
        v14 = operator new(0x190u);
        v15 = v14;
        if ( v14 )
        {
          *v14 = 0;
          DeviceInfoSet::DeviceCacheEntry::DeviceCacheEntry(
            (DeviceInfoSet::DeviceCacheEntry *)(v14 + 1),
            (const struct DeviceInfoSet::DeviceCacheEntry *)&v25);
          if ( *((_QWORD *)this + 4) )
            **((_QWORD **)this + 5) = v15;
          else
            *((_QWORD *)this + 4) = v15;
          *((_QWORD *)this + 5) = v15;
          ++*((_DWORD *)this + 12);
        }
        v26[0] = &CSimpleStringBase<unsigned short>::`vftable';
        v25 = &DeviceInfoSet::DeviceCacheEntry::`vftable';
        CSimpleStringBase<unsigned short>::DeleteStorage(v26);
        v26[34] = 0;
        v41 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( String2 && String2 != (wchar_t *)&v42 )
          operator delete(String2, v16);
      }
      else
      {
        v17 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        8,
                        0,
                        "The Device Info Set skipped devnode index %d, because its \"Subclass\" value is not of a compati"
                        "ble correct type.",
                        v3);
        WriteDbgTraceInfoWI("DeviceInfoSet::AddDevNodeDevices", v17);
        WiaTrcLib::Free((WiaTrcLib *)v17, v18);
        v19 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         8,
                         0,
                         "The Device Info Set skipped devnode index %d, because its \"Subclass\" value is not of a compat"
                         "ible correct type.",
                         v3);
        WiaTrace_ProcessTrace_Ex(v21, v20, (void *)"DeviceInfoSet::AddDevNodeDevices", 4, v19);
      }
      if ( v4 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        RegCloseKey(v4);
      CSimpleReg::~CSimpleReg((CSimpleReg *)&v34);
      ++v3;
    }
    while ( SetupDiEnumDeviceInfo(*((HDEVINFO *)this + 2), v3, &DeviceInfoData_8) );
  }
}

```

## disassembly

```asm
0x1800129fc  mov     rax, rsp
0x1800129ff  mov     [rax+10h], rbx
0x180012a03  mov     [rax+18h], rsi
0x180012a07  push    rbp
0x180012a08  push    rdi
0x180012a09  push    r12
0x180012a0b  push    r14
0x180012a0d  push    r15
0x180012a0f  lea     rbp, [rax-8A8h]
0x180012a16  sub     rsp, 980h
0x180012a1d  movaps  xmmword ptr [rax-38h], xmm6
0x180012a21  mov     rax, cs:__security_cookie
0x180012a28  xor     rax, rsp
0x180012a2b  mov     [rbp+8A0h+var_40], rax
0x180012a32  movups  xmm6, xmmword ptr cs:GUID_DEVCLASS_IMAGE.Data1
0x180012a39  lea     r8, [rsp+9A0h+DeviceInfoData.ClassGuid.Data2]; DeviceInfoData
0x180012a3e  mov     rdi, rcx
0x180012a41  mov     rcx, [rcx+10h]; DeviceInfoSet
0x180012a45  xorps   xmm0, xmm0
0x180012a48  xorps   xmm1, xmm1
0x180012a4b  xor     r15d, r15d
0x180012a4e  movups  xmmword ptr [rsp+9A0h+DeviceInfoData.ClassGuid.Data2], xmm0
0x180012a53  xor     edx, edx; MemberIndex
0x180012a55  mov     dword ptr [rsp+9A0h+DeviceInfoData.ClassGuid.Data2], 20h ; ' '
0x180012a5d  movdqu  xmmword ptr [rsp+9A0h+InterfaceClassGuid+8], xmm6
0x180012a63  mov     esi, r15d
0x180012a66  movups  xmmword ptr [rsp+9A0h+DeviceInfoData.Reserved], xmm0
0x180012a6b  movups  xmmword ptr [rsp+9A0h+samDesired+8], xmm1
0x180012a70  movups  [rsp+9A0h+var_968+8], xmm1
0x180012a75  call    cs:__imp_SetupDiEnumDeviceInfo
0x180012a7b  test    eax, eax
0x180012a7d  jz      loc_180012E8E
0x180012a83  lea     r12, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180012a8a  lea     rbx, ??_7DeviceCacheEntry@DeviceInfoSet@@6B@; const DeviceInfoSet::DeviceCacheEntry::`vftable'
0x180012a91  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180012a95  lea     rdx, [rsp+9A0h+DeviceInfoData.ClassGuid.Data2]; DeviceInfoData
0x180012a9a  xor     r9d, r9d; HwProfile
0x180012a9d  mov     [rsp+9A0h+samDesired], 20019h; samDesired
0x180012aa5  mov     [rsp+9A0h+KeyType], 2; KeyType
0x180012aad  lea     r8d, [r9+1]; Scope
0x180012ab1  call    cs:__imp_SetupDiOpenDevRegKey
0x180012ab7  lea     rdx, Class
0x180012abe  mov     r14, rax
0x180012ac1  lea     rcx, [rbp+8A0h+var_3D0]
0x180012ac8  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180012acd  lea     rax, ??_7CSimpleReg@@6B@; const CSimpleReg::`vftable'
0x180012ad4  lea     rdx, [rbp+8A0h+var_3D0]
0x180012adb  mov     [rbp+8A0h+var_790], rax
0x180012ae2  lea     rcx, [rbp+8A0h+var_788]
0x180012ae9  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x180012aee  lea     rcx, [rbp+8A0h+var_790]; this
0x180012af5  mov     [rbp+8A0h+var_660], r14
0x180012afc  mov     [rbp+8A0h+var_658], r15
0x180012b03  mov     [rbp+8A0h+var_650], r15b
0x180012b0a  mov     [rbp+8A0h+var_648], r15
0x180012b11  mov     [rbp+8A0h+var_640], 20019h
0x180012b1b  call    ?Open@CSimpleReg@@QEAA_NXZ; CSimpleReg::Open(void)
0x180012b20  mov     rcx, [rbp+8A0h+var_2C8]; void *
0x180012b27  mov     [rbp+8A0h+var_3D0], r12
0x180012b2e  test    rcx, rcx
0x180012b31  jz      short loc_180012B44
0x180012b33  lea     rax, [rbp+8A0h+var_3C8]
0x180012b3a  cmp     rcx, rax
0x180012b3d  jz      short loc_180012B44
0x180012b3f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012b44  xor     r9d, r9d; struct _SP_DEVICE_INTERFACE_DATA *
0x180012b47  lea     r8, [rsp+9A0h+DeviceInfoData.ClassGuid.Data2]; struct _SP_DEVINFO_DATA *
0x180012b4c  lea     rdx, [rbp+8A0h+var_790]; struct CSimpleReg *
0x180012b53  mov     rcx, rdi; this
0x180012b56  call    ?IsCorrectDeviceClass@DeviceInfoSet@@AEAAHAEAVCSimpleReg@@PEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVICE_INTERFACE_DATA@@@Z; DeviceInfoSet::IsCorrectDeviceClass(CSimpleReg &,_SP_DEVINFO_DATA *,_SP_DEVICE_INTERFACE_DATA *)
0x180012b5b  test    eax, eax
0x180012b5d  jz      loc_180012DF8
0x180012b63  lea     rdx, aDeviceIdNotFou; "Device ID not found"
0x180012b6a  lea     rcx, [rbp+8A0h+var_2A0]
0x180012b71  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180012b76  lea     rdx, ValueName; "DeviceID"
0x180012b7d  lea     rcx, [rbp+8A0h+var_500]
0x180012b84  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180012b89  lea     r9, [rbp+8A0h+var_2A0]
0x180012b90  lea     r8, [rbp+8A0h+var_500]
0x180012b97  lea     rdx, [rbp+8A0h+var_630]
0x180012b9e  lea     rcx, [rbp+8A0h+var_790]
0x180012ba5  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x180012baa  mov     rcx, [rbp+8A0h+var_3F8]; void *
0x180012bb1  mov     [rbp+8A0h+var_500], r12
0x180012bb8  test    rcx, rcx
0x180012bbb  jz      short loc_180012BCE
0x180012bbd  lea     rax, [rbp+8A0h+var_4F8]
0x180012bc4  cmp     rcx, rax
0x180012bc7  jz      short loc_180012BCE
0x180012bc9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012bce  mov     rcx, [rbp+8A0h+var_198]; void *
0x180012bd5  mov     [rbp+8A0h+var_3F8], r15
0x180012bdc  mov     [rbp+8A0h+var_3F0], r15
0x180012be3  mov     [rbp+8A0h+var_2A0], r12
0x180012bea  test    rcx, rcx
0x180012bed  jz      short loc_180012C00
0x180012bef  lea     rax, [rbp+8A0h+var_298]
0x180012bf6  cmp     rcx, rax
0x180012bf9  jz      short loc_180012C00
0x180012bfb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012c00  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180012c04  lea     rax, [rsp+9A0h+samDesired+8]
0x180012c09  xor     r9d, r9d; MemberIndex
0x180012c0c  mov     qword ptr [rsp+9A0h+KeyType], rax; DeviceInterfaceData
0x180012c11  lea     r8, [rsp+9A0h+InterfaceClassGuid+8]; InterfaceClassGuid
0x180012c16  mov     qword ptr [rsp+9A0h+var_968+0Ch], r15
0x180012c1b  lea     rdx, [rsp+9A0h+DeviceInfoData.ClassGuid.Data2]; DeviceInfoData
0x180012c20  mov     [rsp+9A0h+DeviceInfoData.ClassGuid.Data1], r15d
0x180012c25  mov     [rsp+9A0h+samDesired+8], 20h ; ' '
0x180012c2d  movdqu  xmmword ptr [rsp+9A0h+samDesired+0Ch], xmm6
0x180012c33  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180012c39  test    eax, eax
0x180012c3b  jnz     short loc_180012CB2
0x180012c3d  mov     r9, [rbp+8A0h+String2]
0x180012c44  lea     r8, aTheDeviceInfoS_9; "The Device Info Set could not get the i"...
0x180012c4b  xor     edx, edx
0x180012c4d  lea     ecx, [rax+8]
0x180012c50  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180012c55  mov     rdx, rax; char *
0x180012c58  lea     rcx, aDeviceinfosetA; "DeviceInfoSet::AddDevNodeDevices"
0x180012c5f  mov     rbx, rax
0x180012c62  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180012c67  mov     rcx, rbx; this
0x180012c6a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180012c6f  mov     r9, [rbp+8A0h+String2]
0x180012c76  lea     r8, aTheDeviceInfoS_9; "The Device Info Set could not get the i"...
0x180012c7d  xor     edx, edx
0x180012c7f  lea     ecx, [rdx+8]
0x180012c82  call    WiaTrace_TraceWithSubCompTraceLevel
0x180012c87  mov     r9d, 4; int
0x180012c8d  mov     qword ptr [rsp+9A0h+KeyType], rax; lpMem
0x180012c92  lea     r8, aDeviceinfosetA; "DeviceInfoSet::AddDevNodeDevices"
0x180012c99  call    WiaTrace_ProcessTrace_Ex
0x180012c9e  xorps   xmm0, xmm0
0x180012ca1  lea     rbx, ??_7DeviceCacheEntry@DeviceInfoSet@@6B@; const DeviceInfoSet::DeviceCacheEntry::`vftable'
0x180012ca8  movups  xmmword ptr [rsp+9A0h+samDesired+8], xmm0
0x180012cad  movups  [rsp+9A0h+var_968+8], xmm0
0x180012cb2  mov     rdx, [rbp+8A0h+String2]; String2
0x180012cb9  lea     rcx, aDeviceIdNotFou; "Device ID not found"
0x180012cc0  call    wcscmp_0
0x180012cc5  test    eax, eax
0x180012cc7  jnz     short loc_180012D07
0x180012cc9  mov     rdx, [rdi+10h]
0x180012ccd  lea     r9, DEVPKEY_Device_InstanceId
0x180012cd4  lea     r8, [rsp+9A0h+samDesired+8]
0x180012cd9  lea     rcx, [rbp+8A0h+var_170]
0x180012ce0  call    ?GetStringFromDevInterfaceProperty@@YA?AV?$CSimpleStringBase@G@@PEAXPEAU_SP_DEVICE_INTERFACE_DATA@@PEBU_DEVPROPKEY@@@Z; GetStringFromDevInterfaceProperty(void *,_SP_DEVICE_INTERFACE_DATA *,_DEVPROPKEY const *)
0x180012ce5  mov     rdx, rax
0x180012ce8  lea     rcx, [rbp+8A0h+var_630]
0x180012cef  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180012cf4  lea     rcx, [rbp+8A0h+var_170]
0x180012cfb  mov     [rbp+8A0h+var_170], r12
0x180012d02  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180012d07  lea     rdx, [rbp+8A0h+var_630]
0x180012d0e  mov     [rbp+8A0h+var_920], rbx
0x180012d12  lea     rcx, [rbp+8A0h+var_918]
0x180012d16  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x180012d1b  movups  xmm0, xmmword ptr [rsp+9A0h+DeviceInfoData.ClassGuid.Data4]
0x180012d20  mov     eax, dword ptr [rsp+9A0h+DeviceInfoData.ClassGuid.Data2]
0x180012d24  mov     ecx, 190h; Size
0x180012d29  movups  xmm1, xmmword ptr [rsp+9A0h+DeviceInfoData.Reserved]
0x180012d2e  mov     [rbp+8A0h+var_7E8], eax
0x180012d34  mov     eax, [rsp+9A0h+samDesired+8]
0x180012d38  movups  xmmword ptr [rbp+8A0h+var_7E4], xmm0
0x180012d3f  mov     [rbp+8A0h+var_7F0], 1
0x180012d49  movups  xmm0, xmmword ptr [rsp+9A0h+samDesired+0Ch]
0x180012d4e  mov     [rbp+8A0h+var_7A8], r15
0x180012d55  movups  xmmword ptr [rbp+8A0h+var_7E4+0Ch], xmm1
0x180012d5c  mov     [rbp+8A0h+var_7A0], r15
0x180012d63  movups  xmm1, [rsp+9A0h+var_968+8]
0x180012d68  mov     [rbp+8A0h+var_7C8], eax
0x180012d6e  movups  xmmword ptr [rbp+8A0h+var_7C4], xmm0
0x180012d75  movups  xmmword ptr [rbp+8A0h+var_7C4+0Ch], xmm1
0x180012d7c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012d81  mov     rbx, rax
0x180012d84  test    rax, rax
0x180012d87  jz      short loc_180012DB3
0x180012d89  lea     rcx, [rax+8]; this
0x180012d8d  mov     [rax], r15
0x180012d90  lea     rdx, [rbp+8A0h+var_920]; struct DeviceInfoSet::DeviceCacheEntry *
0x180012d94  call    ??0DeviceCacheEntry@DeviceInfoSet@@QEAA@AEBV01@@Z; DeviceInfoSet::DeviceCacheEntry::DeviceCacheEntry(DeviceInfoSet::DeviceCacheEntry const &)
0x180012d99  cmp     [rdi+20h], r15
0x180012d9d  jnz     short loc_180012DA5
0x180012d9f  mov     [rdi+20h], rbx
0x180012da3  jmp     short loc_180012DAC
0x180012da5  mov     rax, [rdi+28h]
0x180012da9  mov     [rax], rbx
0x180012dac  mov     [rdi+28h], rbx
0x180012db0  inc     dword ptr [rdi+30h]
0x180012db3  lea     rbx, ??_7DeviceCacheEntry@DeviceInfoSet@@6B@; const DeviceInfoSet::DeviceCacheEntry::`vftable'
0x180012dba  mov     [rbp+8A0h+var_918], r12
0x180012dbe  lea     rcx, [rbp+8A0h+var_918]
0x180012dc2  mov     [rbp+8A0h+var_920], rbx
0x180012dc6  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180012dcb  mov     rcx, [rbp+8A0h+String2]; void *
0x180012dd2  mov     [rbp+8A0h+var_808], r15
0x180012dd9  mov     [rbp+8A0h+var_630], r12
0x180012de0  test    rcx, rcx
0x180012de3  jz      short loc_180012E58
0x180012de5  lea     rax, [rbp+8A0h+var_628]
0x180012dec  cmp     rcx, rax
0x180012def  jz      short loc_180012E58
0x180012df1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180012df6  jmp     short loc_180012E58
0x180012df8  xor     edx, edx
0x180012dfa  lea     r8, aTheDeviceInfoS_3; "The Device Info Set skipped devnode ind"...
0x180012e01  mov     r9d, esi
0x180012e04  lea     ecx, [rdx+8]
0x180012e07  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180012e0c  mov     rdx, rax; char *
0x180012e0f  lea     rcx, aDeviceinfosetA; "DeviceInfoSet::AddDevNodeDevices"
0x180012e16  mov     rbx, rax
0x180012e19  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180012e1e  mov     rcx, rbx; this
0x180012e21  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180012e26  xor     edx, edx
0x180012e28  lea     r8, aTheDeviceInfoS_3; "The Device Info Set skipped devnode ind"...
0x180012e2f  mov     r9d, esi
0x180012e32  lea     ecx, [rdx+8]
0x180012e35  call    WiaTrace_TraceWithSubCompTraceLevel
0x180012e3a  mov     r9d, 4; int
0x180012e40  mov     qword ptr [rsp+9A0h+KeyType], rax; lpMem
0x180012e45  lea     r8, aDeviceinfosetA; "DeviceInfoSet::AddDevNodeDevices"
0x180012e4c  call    WiaTrace_ProcessTrace_Ex
0x180012e51  lea     rbx, ??_7DeviceCacheEntry@DeviceInfoSet@@6B@; const DeviceInfoSet::DeviceCacheEntry::`vftable'
0x180012e58  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180012e5c  jz      short loc_180012E67
0x180012e5e  mov     rcx, r14; hKey
0x180012e61  call    cs:__imp_RegCloseKey
0x180012e67  lea     rcx, [rbp+8A0h+var_790]; this
0x180012e6e  call    ??1CSimpleReg@@UEAA@XZ; CSimpleReg::~CSimpleReg(void)
0x180012e73  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180012e77  lea     r8, [rsp+9A0h+DeviceInfoData.ClassGuid.Data2]; DeviceInfoData
0x180012e7c  inc     esi
0x180012e7e  mov     edx, esi; MemberIndex
0x180012e80  call    cs:__imp_SetupDiEnumDeviceInfo
0x180012e86  test    eax, eax
0x180012e88  jnz     loc_180012A91
0x180012e8e  mov     rcx, [rbp+8A0h+var_40]
0x180012e95  xor     rcx, rsp; StackCookie
0x180012e98  call    __security_check_cookie
0x180012e9d  lea     r11, [rsp+9A0h+var_20]
0x180012ea5  mov     rbx, [r11+38h]
0x180012ea9  mov     rsi, [r11+40h]
0x180012ead  movaps  xmm6, xmmword ptr [r11-10h]
0x180012eb2  mov     rsp, r11
0x180012eb5  pop     r15
0x180012eb7  pop     r14
0x180012eb9  pop     r12
0x180012ebb  pop     rdi
0x180012ebc  pop     rbp
0x180012ebd  retn
```
