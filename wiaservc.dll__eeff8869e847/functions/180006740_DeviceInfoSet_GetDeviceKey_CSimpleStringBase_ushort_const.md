# DeviceInfoSet::GetDeviceKey(CSimpleStringBase<ushort> const &)

- ea: `0x180006740`
- end: `0x180006a23`
- name: `?GetDeviceKey@DeviceInfoSet@@QEAAPEAUHKEY__@@AEBV?$CSimpleStringBase@G@@@Z`
- size: `739`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180007fd0`
- `0x180029290`

## callees

- `0x180006740`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x180010dbc`
- `0x180011658`
- `0x180011a94`
- `0x18002c868`
- `0x18002c8b0`
- `0x180033878`
- `0x180033cc0`

## import_xrefs

- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18000685c`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18000688e`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18000685c`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x18000688e`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x180006900`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x180006924`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x180006900`
- `SETUPAPI!SetupDiOpenDeviceInterfaceRegKey` at `0x180006924`

## string_xrefs

- `0x1800068ad`: `The Device Info Set could not open the devnode device key for (%ws).  Error code 0x%08X`
- `0x1800068d5`: `The Device Info Set could not open the devnode device key for (%ws).  Error code 0x%08X`
- `0x180006943`: `The Device Info Set could not open the interface device key for (%ws).  Error code 0x%08X`
- `0x18000696b`: `The Device Info Set could not open the interface device key for (%ws).  Error code 0x%08X`

## pseudocode

```c
HKEY __fastcall DeviceInfoSet::GetDeviceKey(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  void *v5; // rcx
  HKEY v6; // rbx
  char *v7; // rbx
  void *v8; // rdx
  void **v9; // rax
  void *v10; // rdx
  __int64 v11; // rcx
  char *v12; // rbx
  void *v13; // rdx
  char *v14; // rbx
  void *v15; // rdx
  _BYTE v17[296]; // [rsp+30h] [rbp-D0h] BYREF
  _SP_DEVINFO_DATA DeviceInfoData; // [rsp+158h] [rbp+58h] BYREF
  void **v19; // [rsp+180h] [rbp+80h] BYREF
  _QWORD v20[37]; // [rsp+188h] [rbp+88h] BYREF
  int v21; // [rsp+2B0h] [rbp+1B0h]
  _SP_DEVINFO_DATA v22; // [rsp+2B8h] [rbp+1B8h]
  _SP_DEVINFO_DATA v23; // [rsp+2D8h] [rbp+1D8h]
  __int64 v24; // [rsp+2F8h] [rbp+1F8h]
  __int64 v25; // [rsp+300h] [rbp+200h]
  const unsigned __int64 *v26; // [rsp+310h] [rbp+210h] BYREF
  char v27; // [rsp+318h] [rbp+218h] BYREF
  void *v28; // [rsp+418h] [rbp+318h]

  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v26, &Class);
  v19 = &DeviceInfoSet::DeviceCacheEntry::`vftable';
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v20, (__int64)&v26);
  v21 = 0;
  v24 = 0;
  v25 = 0;
  v26 = &CSimpleStringBase<unsigned short>::`vftable';
  if ( v28 && v28 != &v27 )
    operator delete(v28);
  v4 = CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v17, a2);
  if ( !(unsigned int)DeviceInfoSet::LookupEntryByName(a1, v4, &v19) )
  {
    v14 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    8,
                    0,
                    "The Device Info Set could not find device (%ws) in the device list....ignoring request for device ke"
                    "y and returning NULL",
                    *(_QWORD *)(a2 + 264));
    WriteDbgTraceInfoWI("DeviceInfoSet::GetDeviceKey", v14);
    WiaTrcLib::Free((WiaTrcLib *)v14, v15);
    v9 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                    8,
                    0,
                    "The Device Info Set could not find device (%ws) in the device list....ignoring request for device ke"
                    "y and returning NULL",
                    *(_QWORD *)(a2 + 264));
    goto LABEL_13;
  }
  v5 = *(void **)(a1 + 16);
  if ( v21 )
  {
    DeviceInfoData = v22;
    v6 = SetupDiOpenDevRegKey(v5, &DeviceInfoData, 1u, 0, 2u, 0x2001Fu);
    if ( v6 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v6 = SetupDiOpenDevRegKey(*(HDEVINFO *)(a1 + 16), &DeviceInfoData, 1u, 0, 2u, 0x20019u);
      if ( v6 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        v7 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                       8,
                       0,
                       "The Device Info Set could not open the devnode device key for (%ws).  Error code 0x%08X",
                       *(_QWORD *)(a2 + 264));
        WriteDbgTraceInfoWI("DeviceInfoSet::GetDeviceKey", v7);
        WiaTrcLib::Free((WiaTrcLib *)v7, v8);
        v9 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                        8,
                        0,
                        "The Device Info Set could not open the devnode device key for (%ws).  Error code 0x%08X",
                        *(_QWORD *)(a2 + 264));
LABEL_13:
        WiaTrace_ProcessTrace_Ex(v11, v10, (void *)"DeviceInfoSet::GetDeviceKey", 4, v9);
        v6 = 0;
      }
    }
  }
  else
  {
    DeviceInfoData = v23;
    v6 = SetupDiOpenDeviceInterfaceRegKey(v5, (PSP_DEVICE_INTERFACE_DATA)&DeviceInfoData, 0, 0x2001Fu);
    if ( v6 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      v6 = SetupDiOpenDeviceInterfaceRegKey(
             *(HDEVINFO *)(a1 + 16),
             (PSP_DEVICE_INTERFACE_DATA)&DeviceInfoData,
             0,
             0x20019u);
      if ( v6 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        v12 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        8,
                        0,
                        "The Device Info Set could not open the interface device key for (%ws).  Error code 0x%08X",
                        *(_QWORD *)(a2 + 264));
        WriteDbgTraceInfoWI("DeviceInfoSet::GetDeviceKey", v12);
        WiaTrcLib::Free((WiaTrcLib *)v12, v13);
        v9 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                        8,
                        0,
                        "The Device Info Set could not open the interface device key for (%ws).  Error code 0x%08X",
                        *(_QWORD *)(a2 + 264));
        goto LABEL_13;
      }
    }
  }
  v19 = &DeviceInfoSet::DeviceCacheEntry::`vftable';
  v20[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v20);
  return v6;
}

```

## disassembly

```asm
0x180006740  mov     [rsp-8+arg_10], rbx
0x180006745  mov     [rsp-8+arg_18], rsi
0x18000674a  push    rbp
0x18000674b  push    rdi
0x18000674c  push    r13
0x18000674e  lea     rbp, [rsp-350h]
0x180006756  sub     rsp, 450h
0x18000675d  mov     rax, cs:__security_cookie
0x180006764  xor     rax, rsp
0x180006767  mov     [rbp+360h+var_20], rax
0x18000676e  mov     rsi, rdx
0x180006771  mov     rdi, rcx
0x180006774  lea     rdx, Class
0x18000677b  lea     rcx, [rbp+360h+var_150]
0x180006782  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180006787  lea     r13, ??_7DeviceCacheEntry@DeviceInfoSet@@6B@; const DeviceInfoSet::DeviceCacheEntry::`vftable'
0x18000678e  lea     rdx, [rbp+360h+var_150]
0x180006795  mov     [rbp+360h+var_2E0], r13
0x18000679c  lea     rcx, [rbp+360h+var_2D8]
0x1800067a3  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x1800067a8  mov     rcx, [rbp+360h+var_48]; void *
0x1800067af  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800067b6  mov     [rbp+360h+var_1B0], 0
0x1800067c0  mov     [rbp+360h+var_168], 0
0x1800067cb  mov     [rbp+360h+var_160], 0
0x1800067d6  mov     [rbp+360h+var_150], rax
0x1800067dd  test    rcx, rcx
0x1800067e0  jz      short loc_1800067F3
0x1800067e2  lea     rax, [rbp+360h+var_148]
0x1800067e9  cmp     rcx, rax
0x1800067ec  jz      short loc_1800067F3
0x1800067ee  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800067f3  mov     rdx, rsi
0x1800067f6  lea     rcx, [rsp+460h+var_430]
0x1800067fb  call    ??0?$CSimpleStringBase@G@@QEAA@AEBV0@@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(CSimpleStringBase<ushort> const &)
0x180006800  mov     rdx, rax
0x180006803  lea     r8, [rbp+360h+var_2E0]
0x18000680a  mov     rcx, rdi
0x18000680d  call    ?LookupEntryByName@DeviceInfoSet@@AEAAHV?$CSimpleStringBase@G@@AEAVDeviceCacheEntry@1@@Z; DeviceInfoSet::LookupEntryByName(CSimpleStringBase<ushort>,DeviceInfoSet::DeviceCacheEntry &)
0x180006812  test    eax, eax
0x180006814  jz      loc_180006974
0x18000681a  cmp     [rbp+360h+var_1B0], 0
0x180006821  lea     rdx, [rbp+360h+DeviceInfoData]; DeviceInterfaceData
0x180006825  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180006829  jz      loc_1800068E1
0x18000682f  movups  xmm0, [rbp+360h+var_1A8]
0x180006836  xor     r9d, r9d; HwProfile
0x180006839  mov     [rsp+460h+samDesired], 2001Fh; samDesired
0x180006841  movups  xmm1, [rbp+360h+var_198]
0x180006848  mov     [rsp+460h+KeyType], 2; KeyType
0x180006850  movups  xmmword ptr [rbp+360h+DeviceInfoData.cbSize], xmm0
0x180006854  lea     r8d, [r9+1]; Scope
0x180006858  movups  xmmword ptr [rbp+360h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x18000685c  call    cs:__imp_SetupDiOpenDevRegKey
0x180006862  mov     rbx, rax
0x180006865  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006869  jnz     loc_1800069D8
0x18000686f  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180006873  lea     r8d, [rax+2]; Scope
0x180006877  mov     [rsp+460h+samDesired], 20019h; samDesired
0x18000687f  lea     rdx, [rbp+360h+DeviceInfoData]; DeviceInfoData
0x180006883  xor     r9d, r9d; HwProfile
0x180006886  mov     [rsp+460h+KeyType], 2; KeyType
0x18000688e  call    cs:__imp_SetupDiOpenDevRegKey
0x180006894  mov     rbx, rax
0x180006897  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000689b  jnz     loc_1800069D8
0x1800068a1  mov     r9, [rsi+108h]
0x1800068a8  lea     edi, [rax+9]
0x1800068ab  mov     ecx, edi
0x1800068ad  lea     r8, aTheDeviceInfoS_7; "The Device Info Set could not open the "...
0x1800068b4  xor     edx, edx
0x1800068b6  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800068bb  mov     rdx, rax; char *
0x1800068be  lea     rcx, aDeviceinfosetG_0; "DeviceInfoSet::GetDeviceKey"
0x1800068c5  mov     rbx, rax
0x1800068c8  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800068cd  mov     rcx, rbx; this
0x1800068d0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800068d5  lea     r8, aTheDeviceInfoS_7; "The Device Info Set could not open the "...
0x1800068dc  jmp     loc_1800069AF
0x1800068e1  movups  xmm0, [rbp+360h+var_188]
0x1800068e8  mov     r9d, 2001Fh; samDesired
0x1800068ee  xor     r8d, r8d; Reserved
0x1800068f1  movups  xmm1, [rbp+360h+var_178]
0x1800068f8  movups  xmmword ptr [rbp+360h+DeviceInfoData.cbSize], xmm0
0x1800068fc  movups  xmmword ptr [rbp+360h+DeviceInfoData.ClassGuid.Data4+4], xmm1
0x180006900  call    cs:__imp_SetupDiOpenDeviceInterfaceRegKey
0x180006906  mov     rbx, rax
0x180006909  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000690d  jnz     loc_1800069D8
0x180006913  mov     rcx, [rdi+10h]; DeviceInfoSet
0x180006917  lea     rdx, [rbp+360h+DeviceInfoData]; DeviceInterfaceData
0x18000691b  mov     r9d, 20019h; samDesired
0x180006921  xor     r8d, r8d; Reserved
0x180006924  call    cs:__imp_SetupDiOpenDeviceInterfaceRegKey
0x18000692a  mov     rbx, rax
0x18000692d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006931  jnz     loc_1800069D8
0x180006937  mov     r9, [rsi+108h]
0x18000693e  lea     edi, [rax+9]
0x180006941  mov     ecx, edi
0x180006943  lea     r8, aTheDeviceInfoS_4; "The Device Info Set could not open the "...
0x18000694a  xor     edx, edx
0x18000694c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180006951  mov     rdx, rax; char *
0x180006954  lea     rcx, aDeviceinfosetG_0; "DeviceInfoSet::GetDeviceKey"
0x18000695b  mov     rbx, rax
0x18000695e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180006963  mov     rcx, rbx; this
0x180006966  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000696b  lea     r8, aTheDeviceInfoS_4; "The Device Info Set could not open the "...
0x180006972  jmp     short loc_1800069AF
0x180006974  mov     r9, [rsi+108h]
0x18000697b  lea     r8, aTheDeviceInfoS_0; "The Device Info Set could not find devi"...
0x180006982  xor     edx, edx
0x180006984  lea     edi, [rdx+8]
0x180006987  mov     ecx, edi
0x180006989  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000698e  mov     rdx, rax; char *
0x180006991  lea     rcx, aDeviceinfosetG_0; "DeviceInfoSet::GetDeviceKey"
0x180006998  mov     rbx, rax
0x18000699b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800069a0  mov     rcx, rbx; this
0x1800069a3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800069a8  lea     r8, aTheDeviceInfoS_0; "The Device Info Set could not find devi"...
0x1800069af  mov     r9, [rsi+108h]
0x1800069b6  xor     edx, edx
0x1800069b8  mov     ecx, edi
0x1800069ba  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800069bf  mov     r9d, 4; int
0x1800069c5  mov     qword ptr [rsp+460h+KeyType], rax; lpMem
0x1800069ca  lea     r8, aDeviceinfosetG_0; "DeviceInfoSet::GetDeviceKey"
0x1800069d1  call    WiaTrace_ProcessTrace_Ex
0x1800069d6  xor     ebx, ebx
0x1800069d8  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800069df  mov     [rbp+360h+var_2E0], r13
0x1800069e6  lea     rcx, [rbp+360h+var_2D8]
0x1800069ed  mov     [rbp+360h+var_2D8], rax
0x1800069f4  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x1800069f9  mov     rax, rbx
0x1800069fc  mov     rcx, [rbp+360h+var_20]
0x180006a03  xor     rcx, rsp; StackCookie
0x180006a06  call    __security_check_cookie
0x180006a0b  lea     r11, [rsp+460h+var_10]
0x180006a13  mov     rbx, [r11+30h]
0x180006a17  mov     rsi, [r11+38h]
0x180006a1b  mov     rsp, r11
0x180006a1e  pop     r13
0x180006a20  pop     rdi
0x180006a21  pop     rbp
0x180006a22  retn
```
