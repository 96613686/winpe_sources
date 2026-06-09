# USDWrapper::RefreshSettings(void)

- ea: `0x180012fd0`
- end: `0x180013586`
- name: `?RefreshSettings@USDWrapper@@UEAAJXZ`
- size: `1462`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180008bb4`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x180010a28`
- `0x180010f0c`
- `0x1800113d8`
- `0x180012fd0`
- `0x18002ac5c`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180013524`
- `ADVAPI32!RegCloseKey` at `0x180013524`

## string_xrefs

- `0x18001340d`: `ServiceComponentHolder::Get`
- `0x18001343f`: `ServiceComponentHolder::Get`
- `0x1800133f8`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x180013428`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x180013202`: `Device state 0x00000001 means 'disabled', 0x00000002 'removed',  0x00000004 'active'`
- `0x180013229`: `Device state 0x00000001 means 'disabled', 0x00000002 'removed',  0x00000004 'active'`
- `0x180013454`: `Device state for (%ws) updated from 0x%08X to 0x%08X`
- `0x180013483`: `Device state for (%ws) updated from 0x%08X to 0x%08X`
- `0x1800134c8`: `Updating the current settings for (%ws) from Registry`
- `0x1800134f5`: `Updating the current settings for (%ws) from Registry`

## pseudocode

```c
__int64 __fastcall USDWrapper::RefreshSettings(USDWrapper *this)
{
  char *v2; // rbx
  void *v3; // rdx
  void **v4; // rax
  void *v5; // rdx
  __int64 v6; // rcx
  HKEY v7; // rsi
  __int64 v8; // r9
  char *v9; // rbx
  void *v10; // rdx
  int v11; // eax
  const char *v12; // r8
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // r14
  unsigned int v18; // r15d
  int DeviceStatus; // eax
  __int64 v20; // r9
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  char *v31; // rbx
  void *v32; // rdx
  void **v33; // rax
  void *v34; // rdx
  __int64 v35; // rcx
  __int64 InterfaceName; // rax
  char *v37; // rbx
  void *v38; // rdx
  void **v39; // rax
  void *v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  char *v45; // rbx
  void *v46; // rdx
  char *v47; // rbx
  void *v48; // rdx
  void **v49; // rax
  void *v50; // rdx
  __int64 v51; // rcx
  char *v52; // rbx
  void *v53; // rdx
  char *v54; // rbx
  void *v55; // rdx
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  void **v61; // rax
  void *v62; // rdx
  __int64 v63; // rcx
  LPVOID lpMem; // [rsp+20h] [rbp-E0h]
  LPVOID lpMema; // [rsp+20h] [rbp-E0h]
  LPVOID lpMemb; // [rsp+20h] [rbp-E0h]
  LPVOID lpMemc; // [rsp+20h] [rbp-E0h]
  LPVOID lpMemd; // [rsp+20h] [rbp-E0h]
  __int64 v69; // [rsp+28h] [rbp-D8h]
  _BYTE v70[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v71; // [rsp+38h] [rbp-C8h]
  const unsigned __int64 *v72; // [rsp+40h] [rbp-C0h] BYREF
  char v73; // [rsp+48h] [rbp-B8h] BYREF
  void *v74; // [rsp+148h] [rbp+48h]
  __int64 v75; // [rsp+150h] [rbp+50h]
  const unsigned __int64 *v76; // [rsp+170h] [rbp+70h] BYREF
  char v77; // [rsp+178h] [rbp+78h] BYREF
  void *v78; // [rsp+278h] [rbp+178h]

  v2 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                 0,
                 0,
                 "Refreshing USDWrapper settings for (%ws)",
                 *((_QWORD *)this + 301));
  WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v2);
  WiaTrcLib::Free((WiaTrcLib *)v2, v3);
  v4 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                  0,
                  0,
                  "Refreshing USDWrapper settings for (%ws)",
                  *((_QWORD *)this + 301));
  WiaTrace_ProcessTrace_Ex(v6, v5, (void *)"USDWrapper::RefreshSettings", 4, v4);
  v7 = (HKEY)(*(__int64 (__fastcall **)(USDWrapper *))(*(_QWORD *)this + 480LL))(this);
  if ( (unsigned __int64)v7 - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v54 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "Updating the current settings for (%ws) from Registry",
                    *((_QWORD *)this + 301));
    WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v54);
    WiaTrcLib::Free((WiaTrcLib *)v54, v55);
    v56 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "Updating the current settings for (%ws) from Registry",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"USDWrapper::RefreshSettings", 4, v56);
    USDInfo::ReadCommonSettingsFromRegistryKey((USDWrapper *)((char *)this + 24), v7);
    RegCloseKey(v7);
  }
  v8 = *((_QWORD *)this + 301);
  if ( (*((_DWORD *)this + 15) & 0x10) != 0 )
  {
    *((_DWORD *)this + 8) |= 0x10u;
    LODWORD(lpMem) = *((_DWORD *)this + 8);
    v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                   0,
                   0,
                   "(%ws) is a WIA device (internal type: 0x%08X)",
                   v8,
                   lpMem);
    WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    v11 = *((_DWORD *)this + 8);
    v12 = "(%ws) is a WIA device (internal type: 0x%08X)";
  }
  else
  {
    LODWORD(lpMem) = *((_DWORD *)this + 15);
    v45 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "(%ws) is not a WIA device (capabilities: 0x%08X)",
                    v8,
                    lpMem);
    WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v45);
    WiaTrcLib::Free((WiaTrcLib *)v45, v46);
    v11 = *((_DWORD *)this + 15);
    v12 = "(%ws) is not a WIA device (capabilities: 0x%08X)";
  }
  LODWORD(lpMema) = v11;
  v13 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, v12, *((_QWORD *)this + 301), lpMema);
  WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"USDWrapper::RefreshSettings", 4, v13);
  if ( *((_DWORD *)this + 4) == 3 )
  {
    ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v70);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v72, L"DeviceInfoSet");
    v16 = v71;
    if ( v71 )
    {
      v17 = CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<DeviceInfoSet>(v71, (__int64)&v72);
    }
    else
    {
      v17 = 0;
      v47 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                      v74);
      WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v47);
      WiaTrcLib::Free((WiaTrcLib *)v47, v48);
      v49 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                       v74);
      WiaTrace_ProcessTrace_Ex(v51, v50, (void *)"ServiceComponentHolder::Get", 2, v49);
    }
    v72 = &CSimpleStringBase<unsigned short>::`vftable';
    if ( v74 && v74 != &v73 )
      operator delete(v74);
    v74 = 0;
    v75 = 0;
    if ( v17 )
    {
      v18 = *((_DWORD *)this + 7);
      DeviceStatus = DeviceInfoSet::GetDeviceStatus(v17, (char *)this + 72, v18);
      v20 = *((_QWORD *)this + 301);
      *((_DWORD *)this + 7) = DeviceStatus;
      if ( v18 == DeviceStatus )
      {
        LODWORD(lpMemb) = DeviceStatus;
        v21 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(4, 0, "Device state for (%ws) remains 0x%08X", v20, lpMemb);
        WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v21);
        WiaTrcLib::Free((WiaTrcLib *)v21, v22);
        LODWORD(lpMemc) = *((_DWORD *)this + 7);
        v23 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         4,
                         0,
                         "Device state for (%ws) remains 0x%08X",
                         *((_QWORD *)this + 301),
                         lpMemc);
      }
      else
      {
        LODWORD(lpMemb) = v18;
        v52 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        4,
                        0,
                        "Device state for (%ws) updated from 0x%08X to 0x%08X",
                        v20,
                        lpMemb,
                        DeviceStatus);
        WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v52);
        WiaTrcLib::Free((WiaTrcLib *)v52, v53);
        LODWORD(v69) = *((_DWORD *)this + 7);
        LODWORD(lpMemd) = v18;
        v23 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         4,
                         0,
                         "Device state for (%ws) updated from 0x%08X to 0x%08X",
                         *((_QWORD *)this + 301),
                         lpMemd,
                         v69);
      }
      WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"USDWrapper::RefreshSettings", 4, v23);
      v26 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      4,
                      0,
                      "Device state 0x00000001 means 'disabled', 0x00000002 'removed',  0x00000004 'active'");
      WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v26);
      WiaTrcLib::Free((WiaTrcLib *)v26, v27);
      v28 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       4,
                       0,
                       "Device state 0x00000001 means 'disabled', 0x00000002 'removed',  0x00000004 'active'");
      WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"USDWrapper::RefreshSettings", 4, v28);
      v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      4,
                      0,
                      "Previous PnP identifier of (%ws): %ws",
                      *((_QWORD *)this + 301),
                      *((_QWORD *)this + 449));
      WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v31);
      WiaTrcLib::Free((WiaTrcLib *)v31, v32);
      v33 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       4,
                       0,
                       "Previous PnP identifier of (%ws): %ws",
                       *((_QWORD *)this + 301),
                       *((_QWORD *)this + 449));
      WiaTrace_ProcessTrace_Ex(v35, v34, (void *)"USDWrapper::RefreshSettings", 4, v33);
      InterfaceName = DeviceInfoSet::GetInterfaceName(v17, &v76, (char *)this + 72);
      CSimpleStringBase<unsigned short>::operator=((__int64)this + 3328, InterfaceName);
      v76 = &CSimpleStringBase<unsigned short>::`vftable';
      if ( v78 && v78 != &v77 )
        operator delete(v78);
      v37 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      4,
                      0,
                      "New PnP identifier for (%ws): %ws",
                      *((_QWORD *)this + 301),
                      *((_QWORD *)this + 449));
      WriteDbgTraceInfoWI("USDWrapper::RefreshSettings", v37);
      WiaTrcLib::Free((WiaTrcLib *)v37, v38);
      v39 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       4,
                       0,
                       "New PnP identifier for (%ws): %ws",
                       *((_QWORD *)this + 301),
                       *((_QWORD *)this + 449));
      WiaTrace_ProcessTrace_Ex(v41, v40, (void *)"USDWrapper::RefreshSettings", 4, v39);
      v42 = v17 + *(int *)(*(_QWORD *)v17 + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    else
    {
      v59 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "The Device Class wrapper for (%ws) could not refresh the device state because the DeviceInfoSet co"
                      "uld not be found",
                      *((_QWORD *)this + 301));
      WriteDbgTraceWarningWI("USDWrapper::RefreshSettings", v59);
      WiaTrcLib::Free((WiaTrcLib *)v59, v60);
      v61 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "The Device Class wrapper for (%ws) could not refresh the device state because the DeviceInfoSet c"
                       "ould not be found",
                       *((_QWORD *)this + 301));
      WiaTrace_ProcessTrace_Ex(v63, v62, (void *)"USDWrapper::RefreshSettings", 2, v61);
    }
    if ( v16 )
    {
      v43 = v16 + *(int *)(*(_QWORD *)v16 + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180012fd0  push    rbp
0x180012fd2  push    rbx
0x180012fd3  push    rsi
0x180012fd4  push    rdi
0x180012fd5  push    r12
0x180012fd7  push    r13
0x180012fd9  push    r14
0x180012fdb  push    r15
0x180012fdd  lea     rbp, [rsp-1B8h]
0x180012fe5  sub     rsp, 2B8h
0x180012fec  mov     rax, cs:__security_cookie
0x180012ff3  xor     rax, rsp
0x180012ff6  mov     [rbp+1F0h+var_50], rax
0x180012ffd  mov     r9, [rcx+968h]
0x180013004  lea     r8, aRefreshingUsdw; "Refreshing USDWrapper settings for (%ws"...
0x18001300b  mov     rdi, rcx
0x18001300e  xor     edx, edx
0x180013010  xor     ecx, ecx
0x180013012  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180013017  lea     r13, aUsdwrapperRefr; "USDWrapper::RefreshSettings"
0x18001301e  mov     rdx, rax; char *
0x180013021  mov     rcx, r13; char *
0x180013024  mov     rbx, rax
0x180013027  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001302c  mov     rcx, rbx; this
0x18001302f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013034  mov     r9, [rdi+968h]
0x18001303b  lea     r8, aRefreshingUsdw; "Refreshing USDWrapper settings for (%ws"...
0x180013042  xor     edx, edx
0x180013044  xor     ecx, ecx
0x180013046  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001304b  mov     r15d, 4
0x180013051  mov     [rsp+2F0h+lpMem], rax; lpMem
0x180013056  mov     r9d, r15d; int
0x180013059  mov     r8, r13; int
0x18001305c  call    WiaTrace_ProcessTrace_Ex
0x180013061  mov     rax, [rdi]
0x180013064  mov     rcx, rdi
0x180013067  mov     rax, [rax+1E0h]
0x18001306e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013073  mov     rsi, rax
0x180013076  lea     rcx, [rax-1]
0x18001307a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18001307e  jbe     loc_1800134C1
0x180013084  mov     eax, [rdi+3Ch]
0x180013087  xor     edx, edx
0x180013089  mov     r9, [rdi+968h]
0x180013090  xor     ecx, ecx
0x180013092  test    al, 10h
0x180013094  jz      loc_1800133BF
0x18001309a  or      dword ptr [rdi+20h], 10h
0x18001309e  lea     r8, aWsIsAWiaDevice; "(%ws) is a WIA device (internal type: 0"...
0x1800130a5  mov     eax, [rdi+20h]
0x1800130a8  mov     dword ptr [rsp+2F0h+lpMem], eax
0x1800130ac  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800130b1  mov     rdx, rax; char *
0x1800130b4  mov     rcx, r13; char *
0x1800130b7  mov     rbx, rax
0x1800130ba  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800130bf  mov     rcx, rbx; this
0x1800130c2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800130c7  mov     eax, [rdi+20h]
0x1800130ca  lea     r8, aWsIsAWiaDevice; "(%ws) is a WIA device (internal type: 0"...
0x1800130d1  mov     r9, [rdi+968h]
0x1800130d8  xor     edx, edx
0x1800130da  xor     ecx, ecx
0x1800130dc  mov     dword ptr [rsp+2F0h+lpMem], eax
0x1800130e0  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800130e5  mov     r9d, r15d; int
0x1800130e8  mov     [rsp+2F0h+lpMem], rax; lpMem
0x1800130ed  mov     r8, r13; int
0x1800130f0  call    WiaTrace_ProcessTrace_Ex
0x1800130f5  cmp     dword ptr [rdi+10h], 3
0x1800130f9  jnz     loc_18001339A
0x1800130ff  lea     rcx, [rsp+2F0h+var_2C0]; this
0x180013104  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180013109  lea     rdx, aDeviceinfoset; "DeviceInfoSet"
0x180013110  lea     rcx, [rsp+2F0h+var_2B0]
0x180013115  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18001311a  mov     rsi, [rsp+2F0h+var_2B8]
0x18001311f  mov     r15d, 1
0x180013125  lea     r12d, [r15+1]
0x180013129  test    rsi, rsi
0x18001312c  jz      loc_1800133F4
0x180013132  lea     rdx, [rsp+2F0h+var_2B0]
0x180013137  mov     rcx, rsi
0x18001313a  call    ??$Get@VDeviceInfoSet@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVDeviceInfoSet@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<DeviceInfoSet>(CSimpleStringBase<ushort> const &)
0x18001313f  mov     r14, rax
0x180013142  mov     rcx, [rbp+1F0h+var_1A8]; void *
0x180013146  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18001314d  mov     [rsp+2F0h+var_2B0], rax
0x180013152  test    rcx, rcx
0x180013155  jz      short loc_180013165
0x180013157  lea     rax, [rsp+2F0h+var_2A8]
0x18001315c  cmp     rcx, rax
0x18001315f  jnz     loc_1800134AD
0x180013165  mov     [rbp+1F0h+var_1A8], 0
0x18001316d  mov     [rbp+1F0h+var_1A0], 0
0x180013175  test    r14, r14
0x180013178  jz      loc_18001352F
0x18001317e  mov     r15d, [rdi+1Ch]
0x180013182  lea     rdx, [rdi+48h]
0x180013186  mov     r8d, r15d
0x180013189  mov     rcx, r14
0x18001318c  call    ?GetDeviceStatus@DeviceInfoSet@@QEAAKAEBV?$CSimpleStringBase@G@@K@Z; DeviceInfoSet::GetDeviceStatus(CSimpleStringBase<ushort> const &,ulong)
0x180013191  mov     r9, [rdi+968h]
0x180013198  xor     edx, edx
0x18001319a  mov     [rdi+1Ch], eax
0x18001319d  cmp     r15d, eax
0x1800131a0  jnz     loc_180013450
0x1800131a6  lea     r15d, [rdx+4]
0x1800131aa  mov     dword ptr [rsp+2F0h+lpMem], eax
0x1800131ae  mov     ecx, r15d
0x1800131b1  lea     r8, aDeviceStateFor; "Device state for (%ws) remains 0x%08X"
0x1800131b8  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800131bd  mov     rdx, rax; char *
0x1800131c0  mov     rcx, r13; char *
0x1800131c3  mov     rbx, rax
0x1800131c6  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800131cb  mov     rcx, rbx; this
0x1800131ce  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800131d3  mov     eax, [rdi+1Ch]
0x1800131d6  lea     r8, aDeviceStateFor; "Device state for (%ws) remains 0x%08X"
0x1800131dd  mov     r9, [rdi+968h]
0x1800131e4  xor     edx, edx
0x1800131e6  mov     ecx, r15d
0x1800131e9  mov     dword ptr [rsp+2F0h+lpMem], eax
0x1800131ed  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800131f2  mov     r9d, r15d; int
0x1800131f5  mov     [rsp+2F0h+lpMem], rax; lpMem
0x1800131fa  mov     r8, r13; int
0x1800131fd  call    WiaTrace_ProcessTrace_Ex
0x180013202  lea     r8, aDeviceState0x0; "Device state 0x00000001 means 'disabled"...
0x180013209  xor     edx, edx
0x18001320b  mov     ecx, r15d
0x18001320e  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180013213  mov     rdx, rax; char *
0x180013216  mov     rcx, r13; char *
0x180013219  mov     rbx, rax
0x18001321c  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180013221  mov     rcx, rbx; this
0x180013224  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013229  lea     r8, aDeviceState0x0; "Device state 0x00000001 means 'disabled"...
0x180013230  xor     edx, edx
0x180013232  mov     ecx, r15d
0x180013235  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001323a  mov     r9d, r15d; int
0x18001323d  mov     [rsp+2F0h+lpMem], rax; lpMem
0x180013242  mov     r8, r13; int
0x180013245  call    WiaTrace_ProcessTrace_Ex
0x18001324a  mov     rax, [rdi+0E08h]
0x180013251  lea     r8, aPreviousPnpIde; "Previous PnP identifier of (%ws): %ws"
0x180013258  mov     r9, [rdi+968h]
0x18001325f  xor     edx, edx
0x180013261  mov     ecx, r15d
0x180013264  mov     [rsp+2F0h+lpMem], rax
0x180013269  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001326e  mov     rdx, rax; char *
0x180013271  mov     rcx, r13; char *
0x180013274  mov     rbx, rax
0x180013277  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001327c  mov     rcx, rbx; this
0x18001327f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013284  mov     rax, [rdi+0E08h]
0x18001328b  lea     r8, aPreviousPnpIde; "Previous PnP identifier of (%ws): %ws"
0x180013292  mov     r9, [rdi+968h]
0x180013299  xor     edx, edx
0x18001329b  mov     ecx, r15d
0x18001329e  mov     [rsp+2F0h+lpMem], rax
0x1800132a3  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800132a8  mov     r9d, r15d; int
0x1800132ab  mov     [rsp+2F0h+lpMem], rax; lpMem
0x1800132b0  mov     r8, r13; int
0x1800132b3  call    WiaTrace_ProcessTrace_Ex
0x1800132b8  lea     r8, [rdi+48h]
0x1800132bc  mov     rcx, r14
0x1800132bf  lea     rdx, [rbp+1F0h+var_180]
0x1800132c3  call    ?GetInterfaceName@DeviceInfoSet@@QEAA?AV?$CSimpleStringBase@G@@AEBV2@K@Z; DeviceInfoSet::GetInterfaceName(CSimpleStringBase<ushort> const &,ulong)
0x1800132c8  mov     rdx, rax
0x1800132cb  lea     rcx, [rdi+0D00h]
0x1800132d2  call    ??4?$CSimpleStringBase@G@@QEAAAEAV0@AEBV0@@Z; CSimpleStringBase<ushort>::operator=(CSimpleStringBase<ushort> const &)
0x1800132d7  mov     rcx, [rbp+1F0h+var_78]; void *
0x1800132de  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x1800132e5  mov     [rbp+1F0h+var_180], rax
0x1800132e9  test    rcx, rcx
0x1800132ec  jz      short loc_1800132FB
0x1800132ee  lea     rax, [rbp+1F0h+var_178]
0x1800132f2  cmp     rcx, rax
0x1800132f5  jnz     loc_1800134B7
0x1800132fb  mov     rax, [rdi+0E08h]
0x180013302  lea     r8, aNewPnpIdentifi; "New PnP identifier for (%ws): %ws"
0x180013309  mov     r9, [rdi+968h]
0x180013310  xor     edx, edx
0x180013312  mov     ecx, r15d
0x180013315  mov     [rsp+2F0h+lpMem], rax
0x18001331a  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001331f  mov     rdx, rax; char *
0x180013322  mov     rcx, r13; char *
0x180013325  mov     rbx, rax
0x180013328  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001332d  mov     rcx, rbx; this
0x180013330  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013335  mov     rax, [rdi+0E08h]
0x18001333c  lea     r8, aNewPnpIdentifi; "New PnP identifier for (%ws): %ws"
0x180013343  mov     r9, [rdi+968h]
0x18001334a  xor     edx, edx
0x18001334c  mov     ecx, r15d
0x18001334f  mov     [rsp+2F0h+lpMem], rax
0x180013354  call    WiaTrace_TraceWithSubCompTraceLevel
0x180013359  mov     r9d, r15d; int
0x18001335c  mov     [rsp+2F0h+lpMem], rax; lpMem
0x180013361  mov     r8, r13; int
0x180013364  call    WiaTrace_ProcessTrace_Ex
0x180013369  mov     rax, [r14]
0x18001336c  movsxd  rcx, dword ptr [rax+4]
0x180013370  add     rcx, r14
0x180013373  mov     rax, [rcx]
0x180013376  mov     rax, [rax+10h]
0x18001337a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001337f  test    rsi, rsi
0x180013382  jz      short loc_18001339A
0x180013384  mov     rax, [rsi]
0x180013387  movsxd  rcx, dword ptr [rax+4]
0x18001338b  add     rcx, rsi
0x18001338e  mov     rax, [rcx]
0x180013391  mov     rax, [rax+10h]
0x180013395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001339a  xor     eax, eax
0x18001339c  mov     rcx, [rbp+1F0h+var_50]
0x1800133a3  xor     rcx, rsp; StackCookie
0x1800133a6  call    __security_check_cookie
0x1800133ab  add     rsp, 2B8h
0x1800133b2  pop     r15
0x1800133b4  pop     r14
0x1800133b6  pop     r13
0x1800133b8  pop     r12
0x1800133ba  pop     rdi
0x1800133bb  pop     rsi
0x1800133bc  pop     rbx
0x1800133bd  pop     rbp
0x1800133be  retn
0x1800133bf  lea     r8, aWsIsNotAWiaDev; "(%ws) is not a WIA device (capabilities"...
0x1800133c6  mov     dword ptr [rsp+2F0h+lpMem], eax
0x1800133ca  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800133cf  mov     rdx, rax; char *
0x1800133d2  mov     rcx, r13; char *
0x1800133d5  mov     rbx, rax
0x1800133d8  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800133dd  mov     rcx, rbx; this
0x1800133e0  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800133e5  mov     eax, [rdi+3Ch]
0x1800133e8  lea     r8, aWsIsNotAWiaDev; "(%ws) is not a WIA device (capabilities"...
0x1800133ef  jmp     loc_1800130D1
0x1800133f4  mov     r8, [rbp+1F0h+var_1A8]
0x1800133f8  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x1800133ff  mov     ecx, r15d
0x180013402  xor     r14d, r14d
0x180013405  call    WiaTrace_TraceLogWithSubComp
0x18001340a  mov     rdx, rax; char *
0x18001340d  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x180013414  mov     rbx, rax
0x180013417  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001341c  mov     rcx, rbx; this
0x18001341f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013424  mov     r8, [rbp+1F0h+var_1A8]
0x180013428  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18001342f  mov     ecx, r15d
0x180013432  call    WiaTrace_TraceWithSubComp
0x180013437  mov     r9d, r12d; int
0x18001343a  mov     [rsp+2F0h+lpMem], rax; lpMem
0x18001343f  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x180013446  call    WiaTrace_ProcessTrace_Ex
0x18001344b  jmp     loc_180013142
0x180013450  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x180013454  lea     r8, aDeviceStateFor_1; "Device state for (%ws) updated from 0x%"...
0x18001345b  mov     ecx, 4
0x180013460  mov     dword ptr [rsp+2F0h+lpMem], r15d
0x180013465  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001346a  mov     rdx, rax; char *
0x18001346d  mov     rcx, r13; char *
0x180013470  mov     rbx, rax
0x180013473  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180013478  mov     rcx, rbx; this
0x18001347b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180013480  mov     eax, [rdi+1Ch]
0x180013483  lea     r8, aDeviceStateFor_1; "Device state for (%ws) updated from 0x%"...
0x18001348a  mov     r9, [rdi+968h]
0x180013491  xor     edx, edx
0x180013493  mov     dword ptr [rsp+2F0h+var_2C8], eax
0x180013497  mov     dword ptr [rsp+2F0h+lpMem], r15d
0x18001349c  lea     r15d, [rdx+4]
0x1800134a0  mov     ecx, r15d
0x1800134a3  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800134a8  jmp     loc_1800131F2
0x1800134ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800134b2  jmp     loc_180013165
0x1800134b7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800134bc  jmp     loc_1800132FB
0x1800134c1  mov     r9, [rdi+968h]
0x1800134c8  lea     r8, aUpdatingTheCur; "Updating the current settings for (%ws)"...
  ... truncated ...
```
