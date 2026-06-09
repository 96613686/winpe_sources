# DeviceInfoSet::AddInterfaceDevices(void)

- ea: `0x18000813c`
- end: `0x1800085a9`
- name: `?AddInterfaceDevices@DeviceInfoSet@@AEAAXXZ`
- size: `1133`
- prototype: `void __fastcall(DeviceInfoSet *__hidden this)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180008cac`

## callees

- `0x18000813c`
- `0x18000b6a0`
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
- `0x180012ec4`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x18002f304`
- `0x18002fc10`
- `0x18002fedc`
- `0x180033878`
- `0x180033cc0`
- `0x1800775e4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180008543`
- `ADVAPI32!RegCloseKey` at `0x180008543`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180008460`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180008460`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180008375`
- `SETUPAPI!SetupDiGetDeviceInterfaceDetailW` at `0x180008375`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800081bb`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180008570`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x1800081bb`
- `SETUPAPI!SetupDiEnumDeviceInterfaces` at `0x180008570`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x1800081e2`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x1800081e2`

## string_xrefs

- `0x1800084e3`: `The Device Info Set skipped interface index %d, because its "Subclass" value is not of a compatible correct type.`
- `0x180008511`: `The Device Info Set skipped interface index %d, because its "Subclass" value is not of a compatible correct type.`

## pseudocode

```c
void __fastcall DeviceInfoSet::AddInterfaceDevices(DeviceInfoSet *this)
{
  void *v2; // rcx
  DWORD v3; // r14d
  HKEY v4; // r15
  void *v5; // rcx
  unsigned int DeviceInterfaceDetailW; // eax
  unsigned int v7; // esi
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  WCHAR *v13; // rbx
  __int64 StringFromDevInterfaceProperty; // rax
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  _BYTE v20[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct _SP_DEVICE_INTERFACE_DATA DeviceInterfaceData; // [rsp+38h] [rbp-C8h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+58h] [rbp-A8h] BYREF
  GUID InterfaceClassGuid; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int64 *v24; // [rsp+90h] [rbp-70h] BYREF
  char v25; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String2; // [rsp+198h] [rbp+98h]
  void **v27; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v28[296]; // [rsp+1C8h] [rbp+C8h] BYREF
  HKEY v29; // [rsp+2F0h] [rbp+1F0h]
  __int64 v30; // [rsp+2F8h] [rbp+1F8h]
  char v31; // [rsp+300h] [rbp+200h]
  __int64 v32; // [rsp+308h] [rbp+208h]
  int v33; // [rsp+310h] [rbp+210h]
  const unsigned __int64 *v34; // [rsp+320h] [rbp+220h] BYREF
  char v35; // [rsp+328h] [rbp+228h] BYREF
  void *v36; // [rsp+428h] [rbp+328h]
  __int64 v37; // [rsp+430h] [rbp+330h]
  const unsigned __int64 *v38; // [rsp+450h] [rbp+350h] BYREF
  char v39; // [rsp+458h] [rbp+358h] BYREF
  void *v40; // [rsp+558h] [rbp+458h]
  const unsigned __int64 *v41; // [rsp+580h] [rbp+480h] BYREF
  char v42; // [rsp+588h] [rbp+488h] BYREF
  void *v43; // [rsp+688h] [rbp+588h]
  void **v44; // [rsp+6B0h] [rbp+5B0h] BYREF
  const unsigned __int64 *v45; // [rsp+6B8h] [rbp+5B8h] BYREF
  _QWORD v46[38]; // [rsp+840h] [rbp+740h] BYREF

  v2 = (void *)*((_QWORD *)this + 2);
  InterfaceClassGuid = GUID_DEVCLASS_IMAGE;
  memset(&DeviceInterfaceData, 0, sizeof(DeviceInterfaceData));
  DeviceInterfaceData.cbSize = 32;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  v3 = 0;
  if ( SetupDiEnumDeviceInterfaces(v2, 0, &InterfaceClassGuid, 0, &DeviceInterfaceData) )
  {
    do
    {
      v4 = SetupDiOpenDeviceInterfaceRegKey(*((HDEVINFO *)this + 2), &DeviceInterfaceData, 0, 0x20019u);
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v38, &Class);
      v27 = &CSimpleReg::`vftable';
      CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v28, (__int64)&v38);
      v29 = v4;
      v30 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 131097;
      CSimpleReg::Open((CSimpleReg *)&v27);
      v38 = &CSimpleStringBase<unsigned short>::`vftable';
      if ( v40 && v40 != &v39 )
        operator delete(v40);
      if ( (unsigned int)DeviceInfoSet::IsCorrectDeviceClass(this, (struct CSimpleReg *)&v27, 0, &DeviceInterfaceData) )
      {
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v41, L"Device ID not found");
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v34, L"DeviceID");
        CSimpleReg::Query(&v27, &v24, &v34, &v41);
        v34 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v36 && v36 != &v35 )
          operator delete(v36);
        v36 = 0;
        v37 = 0;
        v41 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v43 && v43 != &v42 )
          operator delete(v43);
        v5 = (void *)*((_QWORD *)this + 2);
        memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
        DeviceInfoData.cbSize = 32;
        DeviceInterfaceDetailW = SetupDiGetDeviceInterfaceDetailW(v5, &DeviceInterfaceData, 0, 0, 0, &DeviceInfoData);
        v7 = DeviceInterfaceDetailW;
        if ( !DeviceInterfaceDetailW || DeviceInterfaceDetailW == 122 )
        {
          v13 = String2;
          if ( !wcscmp_0(L"Device ID not found", String2) )
          {
            StringFromDevInterfaceProperty = GetStringFromDevInterfaceProperty(
                                               v46,
                                               *((_QWORD *)this + 2),
                                               &DeviceInterfaceData,
                                               &DEVPKEY_Device_InstanceId);
            CSimpleStringBase<unsigned short>::operator=((__int64)&v24, StringFromDevInterfaceProperty);
            v46[0] = &CSimpleStringBase<unsigned short>::`vftable';
            CSimpleStringBase<unsigned short>::DeleteStorage(v46);
            v13 = String2;
          }
          if ( !DeviceInfoData.DevInst )
            CM_Locate_DevNodeW(&DeviceInfoData.DevInst, v13, 0);
          DeviceInfoSet::DeviceCacheEntry::DeviceCacheEntry(
            (__int64)&v44,
            (__int64)&v24,
            1,
            &DeviceInfoData,
            &DeviceInterfaceData);
          CSimpleLinkedList<DeviceInfoSet::DeviceCacheEntry>::Append((char *)this + 24, v20, &v44);
          v45 = &CSimpleStringBase<unsigned short>::`vftable';
          v44 = &DeviceInfoSet::DeviceCacheEntry::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage(&v45);
        }
        else
        {
          v8 = (char *)WiaTrace_TraceLogWithSubComp(
                         1,
                         "The Device Info Set could not add device (%ws) because we got error 0x%08X getting the interface data",
                         String2,
                         DeviceInterfaceDetailW);
          WriteDbgTraceWarningWI("DeviceInfoSet::AddInterfaceDevices", v8);
          WiaTrcLib::Free((WiaTrcLib *)v8, v9);
          v10 = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "The Device Info Set could not add device (%ws) because we got error 0x%08X getting the interface data",
                           String2,
                           v7);
          WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"DeviceInfoSet::AddInterfaceDevices", 2, v10);
        }
        v24 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( String2 && String2 != (wchar_t *)&v25 )
          operator delete(String2);
      }
      else
      {
        v15 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        8,
                        0,
                        "The Device Info Set skipped interface index %d, because its \"Subclass\" value is not of a compa"
                        "tible correct type.",
                        v3);
        WriteDbgTraceInfoWI("DeviceInfoSet::AddInterfaceDevices", v15);
        WiaTrcLib::Free((WiaTrcLib *)v15, v16);
        v17 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         8,
                         0,
                         "The Device Info Set skipped interface index %d, because its \"Subclass\" value is not of a comp"
                         "atible correct type.",
                         v3);
        WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"DeviceInfoSet::AddInterfaceDevices", 4, v17);
      }
      if ( v4 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        RegCloseKey(v4);
      CSimpleReg::~CSimpleReg((CSimpleReg *)&v27);
      ++v3;
    }
    while ( SetupDiEnumDeviceInterfaces(*((HDEVINFO *)this + 2), 0, &InterfaceClassGuid, v3, &DeviceInterfaceData) );
  }
}

```

## disassembly

```asm
0x18000813c  mov     [rsp-8+arg_8], rbx
0x180008141  mov     [rsp-8+arg_10], rsi
0x180008146  push    rbp
0x180008147  push    rdi
0x180008148  push    r13
0x18000814a  push    r14
0x18000814c  push    r15
0x18000814e  lea     rbp, [rsp-880h]
0x180008156  sub     rsp, 980h
0x18000815d  mov     rax, cs:__security_cookie
0x180008164  xor     rax, rsp
0x180008167  mov     [rbp+8A0h+var_30], rax
0x18000816e  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_IMAGE.Data1
0x180008175  lea     rax, [rsp+9A0h+var_968]
0x18000817a  mov     rdi, rcx
0x18000817d  mov     rcx, [rcx+10h]; DeviceInfoSet
0x180008181  xorps   xmm1, xmm1
0x180008184  movdqu  xmmword ptr [rsp+9A0h+InterfaceClassGuid.Data1], xmm0
0x18000818a  mov     [rsp+9A0h+DeviceInterfaceData], rax; DeviceInterfaceData
0x18000818f  xor     r9d, r9d; MemberIndex
0x180008192  xorps   xmm0, xmm0
0x180008195  lea     r8, [rsp+9A0h+InterfaceClassGuid]; InterfaceClassGuid
0x18000819a  movups  xmmword ptr [rsp+9A0h+var_968.cbSize], xmm0
0x18000819f  xor     edx, edx; DeviceInfoData
0x1800081a1  mov     [rsp+9A0h+var_968.cbSize], 20h ; ' '
0x1800081a9  movups  xmmword ptr [rsp+9A0h+var_948.cbSize], xmm1
0x1800081ae  xor     r14d, r14d
0x1800081b1  movups  xmmword ptr [rsp+9A0h+var_948.ClassGuid.Data4+4], xmm1
0x1800081b6  movups  xmmword ptr [rsp+9A0h+var_968.InterfaceClassGuid.Data4+4], xmm0
0x1800081bb  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x1800081c1  test    eax, eax
0x1800081c3  jz      loc_18000857E
0x1800081c9  lea     r13, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800081d0  mov     rcx, [rdi+10h]; DeviceInfoSet
0x1800081d4  lea     rdx, [rsp+9A0h+var_968]; DeviceInterfaceData
0x1800081d9  mov     r9d, 20019h; samDesired
0x1800081df  xor     r8d, r8d; Reserved
0x1800081e2  call    cs:__imp_SetupDiOpenDeviceInterfaceRegKey
0x1800081e8  lea     rdx, Class
0x1800081ef  mov     r15, rax
0x1800081f2  lea     rcx, [rbp+8A0h+var_550]
0x1800081f9  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800081fe  lea     rax, ??_7CSimpleReg@@6B@; const CSimpleReg::`vftable'
0x180008205  lea     rdx, [rbp+8A0h+var_550]
0x18000820c  mov     [rbp+8A0h+var_7E0], rax
0x180008213  lea     rcx, [rbp+8A0h+var_7D8]
0x18000821a  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x18000821f  lea     rcx, [rbp+8A0h+var_7E0]; this
0x180008226  mov     [rbp+8A0h+var_6B0], r15
0x18000822d  mov     [rbp+8A0h+var_6A8], 0
0x180008238  mov     [rbp+8A0h+var_6A0], 0
0x18000823f  mov     [rbp+8A0h+var_698], 0
0x18000824a  mov     [rbp+8A0h+var_690], 20019h
0x180008254  call    ?Open@CSimpleReg@@QEAA_NXZ; CSimpleReg::Open(void)
0x180008259  mov     rcx, [rbp+8A0h+var_448]; void *
0x180008260  mov     [rbp+8A0h+var_550], r13
0x180008267  test    rcx, rcx
0x18000826a  jz      short loc_18000827D
0x18000826c  lea     rax, [rbp+8A0h+var_548]
0x180008273  cmp     rcx, rax
0x180008276  jz      short loc_18000827D
0x180008278  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000827d  lea     r9, [rsp+9A0h+var_968]; struct _SP_DEVICE_INTERFACE_DATA *
0x180008282  xor     r8d, r8d; struct _SP_DEVINFO_DATA *
0x180008285  lea     rdx, [rbp+8A0h+var_7E0]; struct CSimpleReg *
0x18000828c  mov     rcx, rdi; this
0x18000828f  call    ?IsCorrectDeviceClass@DeviceInfoSet@@AEAAHAEAVCSimpleReg@@PEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVICE_INTERFACE_DATA@@@Z; DeviceInfoSet::IsCorrectDeviceClass(CSimpleReg &,_SP_DEVINFO_DATA *,_SP_DEVICE_INTERFACE_DATA *)
0x180008294  test    eax, eax
0x180008296  jz      loc_1800084E1
0x18000829c  lea     rdx, aDeviceIdNotFou; "Device ID not found"
0x1800082a3  lea     rcx, [rbp+8A0h+var_420]
0x1800082aa  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800082af  lea     rdx, ValueName; "DeviceID"
0x1800082b6  lea     rcx, [rbp+8A0h+var_680]
0x1800082bd  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800082c2  lea     r9, [rbp+8A0h+var_420]
0x1800082c9  lea     r8, [rbp+8A0h+var_680]
0x1800082d0  lea     rdx, [rbp+8A0h+var_910]
0x1800082d4  lea     rcx, [rbp+8A0h+var_7E0]
0x1800082db  call    ?Query@CSimpleReg@@QEBA?AV?$CSimpleStringBase@G@@AEBV2@0@Z; CSimpleReg::Query(CSimpleStringBase<ushort> const &,CSimpleStringBase<ushort> const &)
0x1800082e0  mov     rcx, [rbp+8A0h+var_578]; void *
0x1800082e7  mov     [rbp+8A0h+var_680], r13
0x1800082ee  test    rcx, rcx
0x1800082f1  jz      short loc_180008304
0x1800082f3  lea     rax, [rbp+8A0h+var_678]
0x1800082fa  cmp     rcx, rax
0x1800082fd  jz      short loc_180008304
0x1800082ff  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008304  mov     rcx, [rbp+8A0h+var_318]; void *
0x18000830b  mov     [rbp+8A0h+var_578], 0
0x180008316  mov     [rbp+8A0h+var_570], 0
0x180008321  mov     [rbp+8A0h+var_420], r13
0x180008328  test    rcx, rcx
0x18000832b  jz      short loc_18000833E
0x18000832d  lea     rax, [rbp+8A0h+var_418]
0x180008334  cmp     rcx, rax
0x180008337  jz      short loc_18000833E
0x180008339  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000833e  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180008342  lea     rax, [rsp+9A0h+var_948]
0x180008347  xorps   xmm0, xmm0
0x18000834a  mov     [rsp+9A0h+DeviceInfoData], rax; DeviceInfoData
0x18000834f  movups  xmmword ptr [rsp+9A0h+var_948.cbSize], xmm0
0x180008354  xor     r9d, r9d; DeviceInterfaceDetailDataSize
0x180008357  mov     [rsp+9A0h+var_948.cbSize], 20h ; ' '
0x18000835f  xor     r8d, r8d; DeviceInterfaceDetailData
0x180008362  mov     [rsp+9A0h+DeviceInterfaceData], 0; RequiredSize
0x18000836b  lea     rdx, [rsp+9A0h+var_968]; DeviceInterfaceData
0x180008370  movups  xmmword ptr [rsp+9A0h+var_948.ClassGuid.Data4+4], xmm0
0x180008375  call    cs:__imp_SetupDiGetDeviceInterfaceDetailW
0x18000837b  mov     esi, eax
0x18000837d  test    eax, eax
0x18000837f  jz      short loc_1800083F2
0x180008381  cmp     eax, 7Ah ; 'z'
0x180008384  jz      short loc_1800083F2
0x180008386  mov     r8, [rbp+8A0h+String2]
0x18000838d  lea     rdx, aTheDeviceInfoS_5; "The Device Info Set could not add devic"...
0x180008394  mov     r9d, eax
0x180008397  mov     ecx, 1
0x18000839c  call    WiaTrace_TraceLogWithSubComp
0x1800083a1  mov     rdx, rax; char *
0x1800083a4  lea     rcx, aDeviceinfosetA_0; "DeviceInfoSet::AddInterfaceDevices"
0x1800083ab  mov     rbx, rax
0x1800083ae  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800083b3  mov     rcx, rbx; this
0x1800083b6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800083bb  mov     r8, [rbp+8A0h+String2]
0x1800083c2  lea     rdx, aTheDeviceInfoS_5; "The Device Info Set could not add devic"...
0x1800083c9  mov     r9d, esi
0x1800083cc  mov     ecx, 1
0x1800083d1  call    WiaTrace_TraceWithSubComp
0x1800083d6  mov     r9d, 2; int
0x1800083dc  mov     [rsp+9A0h+DeviceInterfaceData], rax; lpMem
0x1800083e1  lea     r8, aDeviceinfosetA_0; "DeviceInfoSet::AddInterfaceDevices"
0x1800083e8  call    WiaTrace_ProcessTrace_Ex
0x1800083ed  jmp     loc_1800084C1
0x1800083f2  mov     rbx, [rbp+8A0h+String2]
0x1800083f9  lea     rcx, aDeviceIdNotFou; "Device ID not found"
0x180008400  mov     rdx, rbx; String2
0x180008403  call    wcscmp_0
0x180008408  test    eax, eax
0x18000840a  jnz     short loc_18000844E
0x18000840c  mov     rdx, [rdi+10h]
0x180008410  lea     r9, DEVPKEY_Device_InstanceId
0x180008417  lea     r8, [rsp+9A0h+var_968]
0x18000841c  lea     rcx, [rbp+8A0h+var_160]
0x180008423  call    ?GetStringFromDevInterfaceProperty@@YA?AV?$CSimpleStringBase@G@@PEAXPEAU_SP_DEVICE_INTERFACE_DATA@@PEBU_DEVPROPKEY@@@Z; GetStringFromDevInterfaceProperty(void *,_SP_DEVICE_INTERFACE_DATA *,_DEVPROPKEY const *)
0x180008428  mov     rdx, rax
0x18000842b  lea     rcx, [rbp+8A0h+var_910]
0x18000842f  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x180008434  lea     rcx, [rbp+8A0h+var_160]
0x18000843b  mov     [rbp+8A0h+var_160], r13
0x180008442  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180008447  mov     rbx, [rbp+8A0h+String2]
0x18000844e  cmp     [rsp+9A0h+var_948.DevInst], 0
0x180008453  jnz     short loc_180008466
0x180008455  xor     r8d, r8d; ulFlags
0x180008458  lea     rcx, [rsp+9A0h+var_948.DevInst]; pdnDevInst
0x18000845d  mov     rdx, rbx; pDeviceID
0x180008460  call    cs:__imp_CM_Locate_DevNodeW
0x180008466  lea     rax, [rsp+9A0h+var_968]
0x18000846b  mov     r8d, 1
0x180008471  lea     r9, [rsp+9A0h+var_948]
0x180008476  mov     [rsp+9A0h+DeviceInterfaceData], rax
0x18000847b  lea     rdx, [rbp+8A0h+var_910]
0x18000847f  lea     rcx, [rbp+8A0h+var_2F0]
0x180008486  call    ??0DeviceCacheEntry@DeviceInfoSet@@QEAA@AEBV?$CSimpleStringBase@G@@HPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVICE_INTERFACE_DATA@@@Z; DeviceInfoSet::DeviceCacheEntry::DeviceCacheEntry(CSimpleStringBase<ushort> const &,int,_SP_DEVINFO_DATA *,_SP_DEVICE_INTERFACE_DATA *)
0x18000848b  lea     rcx, [rdi+18h]
0x18000848f  lea     r8, [rbp+8A0h+var_2F0]
0x180008496  lea     rdx, [rsp+9A0h+var_970]
0x18000849b  call    ?Append@?$CSimpleLinkedList@VDeviceCacheEntry@DeviceInfoSet@@@@QEAA?AVIterator@1@AEBVDeviceCacheEntry@DeviceInfoSet@@@Z; CSimpleLinkedList<DeviceInfoSet::DeviceCacheEntry>::Append(DeviceInfoSet::DeviceCacheEntry const &)
0x1800084a0  lea     rax, ??_7DeviceCacheEntry@DeviceInfoSet@@6B@; const DeviceInfoSet::DeviceCacheEntry::`vftable'
0x1800084a7  mov     [rbp+8A0h+var_2E8], r13
0x1800084ae  lea     rcx, [rbp+8A0h+var_2E8]
0x1800084b5  mov     [rbp+8A0h+var_2F0], rax
0x1800084bc  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800084c1  mov     rcx, [rbp+8A0h+String2]; void *
0x1800084c8  mov     [rbp+8A0h+var_910], r13
0x1800084cc  test    rcx, rcx
0x1800084cf  jz      short loc_18000853A
0x1800084d1  lea     rax, [rbp+8A0h+var_908]
0x1800084d5  cmp     rcx, rax
0x1800084d8  jz      short loc_18000853A
0x1800084da  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800084df  jmp     short loc_18000853A
0x1800084e1  xor     edx, edx
0x1800084e3  lea     r8, aTheDeviceInfoS; "The Device Info Set skipped interface i"...
0x1800084ea  mov     r9d, r14d
0x1800084ed  lea     ecx, [rdx+8]
0x1800084f0  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800084f5  mov     rdx, rax; char *
0x1800084f8  lea     rcx, aDeviceinfosetA_0; "DeviceInfoSet::AddInterfaceDevices"
0x1800084ff  mov     rbx, rax
0x180008502  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180008507  mov     rcx, rbx; this
0x18000850a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000850f  xor     edx, edx
0x180008511  lea     r8, aTheDeviceInfoS; "The Device Info Set skipped interface i"...
0x180008518  mov     r9d, r14d
0x18000851b  lea     ecx, [rdx+8]
0x18000851e  call    WiaTrace_TraceWithSubCompTraceLevel
0x180008523  mov     r9d, 4; int
0x180008529  mov     [rsp+9A0h+DeviceInterfaceData], rax; lpMem
0x18000852e  lea     r8, aDeviceinfosetA_0; "DeviceInfoSet::AddInterfaceDevices"
0x180008535  call    WiaTrace_ProcessTrace_Ex
0x18000853a  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000853e  jz      short loc_180008549
0x180008540  mov     rcx, r15; hKey
0x180008543  call    cs:__imp_RegCloseKey
0x180008549  lea     rcx, [rbp+8A0h+var_7E0]; this
0x180008550  call    ??1CSimpleReg@@UEAA@XZ; CSimpleReg::~CSimpleReg(void)
0x180008555  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180008559  lea     rax, [rsp+9A0h+var_968]
0x18000855e  inc     r14d
0x180008561  mov     [rsp+9A0h+DeviceInterfaceData], rax; DeviceInterfaceData
0x180008566  mov     r9d, r14d; MemberIndex
0x180008569  lea     r8, [rsp+9A0h+InterfaceClassGuid]; InterfaceClassGuid
0x18000856e  xor     edx, edx; DeviceInfoData
0x180008570  call    cs:__imp_SetupDiEnumDeviceInterfaces
0x180008576  test    eax, eax
0x180008578  jnz     loc_1800081D0
0x18000857e  mov     rcx, [rbp+8A0h+var_30]
0x180008585  xor     rcx, rsp; StackCookie
0x180008588  call    __security_check_cookie
0x18000858d  lea     r11, [rsp+9A0h+var_20]
0x180008595  mov     rbx, [r11+38h]
0x180008599  mov     rsi, [r11+40h]
0x18000859d  mov     rsp, r11
0x1800085a0  pop     r15
0x1800085a2  pop     r14
0x1800085a4  pop     r13
0x1800085a6  pop     rdi
0x1800085a7  pop     rbp
0x1800085a8  retn
```
