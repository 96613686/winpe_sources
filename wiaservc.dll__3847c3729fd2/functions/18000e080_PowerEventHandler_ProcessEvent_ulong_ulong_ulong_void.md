# PowerEventHandler::ProcessEvent(ulong,ulong,ulong,void *)

- ea: `0x18000e080`
- end: `0x18000e807`
- name: `?ProcessEvent@PowerEventHandler@@UEAAJKKKPEAX@Z`
- size: `1927`
- prototype: `__int64 __fastcall(PowerEventHandler *__hidden this, unsigned int, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callees

- `0x180006300`
- `0x18000645c`
- `0x180006a2c`
- `0x180006f9c`
- `0x1800085b0`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000e080`
- `0x18000f4fc`
- `0x18000f928`
- `0x18000fcfc`
- `0x18001e888`
- `0x180026d60`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033cc0`
- `0x180078010`

## string_xrefs

- `0x18000e284`: `WiaService`
- `0x18000e4b9`: `ServiceComponentHolder::Get`
- `0x18000e4f0`: `ServiceComponentHolder::Get`
- `0x18000e612`: `ServiceComponentHolder::Get`
- `0x18000e64b`: `ServiceComponentHolder::Get`
- `0x18000e4a6`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000e4dc`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000e5f8`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000e630`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000e6f6`: `The PowerEventHandler could not process the power message because the WiaService object is NULL!`
- `0x18000e71a`: `The PowerEventHandler could not process the power message because the WiaService object is NULL!`

## pseudocode

```c
__int64 __fastcall PowerEventHandler::ProcessEvent(PowerEventHandler *this, int a2, int a3, int a4, _QWORD *a5)
{
  int v5; // r15d
  unsigned int v7; // r14d
  const char *v8; // rdi
  char *v9; // rbx
  void *v10; // rdx
  void **lpMem; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  int v14; // r12d
  int v15; // r9d
  unsigned __int64 v16; // rdx
  DeviceListManager *v17; // rdi
  unsigned __int64 v18; // rdx
  int v19; // r15d
  int v20; // r15d
  __int64 v21; // rcx
  char *v22; // rcx
  __int64 v23; // rcx
  char *v25; // rbx
  void *v26; // rdx
  void **v27; // rax
  void *v28; // rdx
  __int64 v29; // rcx
  char *v30; // rbx
  void *v31; // rdx
  void **v32; // rax
  void *v33; // rdx
  __int64 v34; // rcx
  char *v35; // rbx
  void *v36; // rdx
  void **v37; // rax
  void *v38; // rdx
  __int64 v39; // rcx
  char *v40; // rbx
  void *v41; // rdx
  void **v42; // rax
  void *v43; // rdx
  __int64 v44; // rcx
  char *v45; // rbx
  void *v46; // rdx
  void **v47; // rax
  void *v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // rax
  char *v51; // rbx
  void *v52; // rdx
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  char *v56; // rbx
  void *v57; // rdx
  void **v58; // rax
  void *v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rdx
  __int64 v62; // r8
  WiaService *v63; // rcx
  struct EnumDeviceInterface *v64; // r9
  int v65; // edx
  int v66; // eax
  DeviceListManager *v67; // rcx
  char *v68; // rbx
  void *v69; // rdx
  void **v70; // rax
  void *v71; // rdx
  __int64 v72; // rcx
  char *v73; // rbx
  void *v74; // rdx
  void **v75; // rax
  void *v76; // rdx
  __int64 v77; // rcx
  char *v78; // rbx
  void *v79; // rdx
  unsigned int v80; // [rsp+30h] [rbp-D0h]
  int v81; // [rsp+34h] [rbp-CCh]
  __int64 v82; // [rsp+38h] [rbp-C8h]
  char v83[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v84; // [rsp+48h] [rbp-B8h]
  _QWORD v85[20]; // [rsp+50h] [rbp-B0h]
  const unsigned __int64 *v86; // [rsp+F0h] [rbp-10h] BYREF
  char v87; // [rsp+F8h] [rbp-8h] BYREF
  void *v88; // [rsp+1F8h] [rbp+F8h]
  __int64 v89; // [rsp+200h] [rbp+100h]
  const unsigned __int64 *v90; // [rsp+220h] [rbp+120h] BYREF
  char v91; // [rsp+228h] [rbp+128h] BYREF
  void *v92; // [rsp+328h] [rbp+228h]
  __int64 v93; // [rsp+330h] [rbp+230h]

  v5 = a4;
  if ( a2 != -1 )
  {
    v25 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "The PowerEventHandler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)");
    WriteDbgTraceWarningWI("PowerEventHandler::ProcessEvent", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v27 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "The PowerEventHandler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)");
    WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"PowerEventHandler::ProcessEvent", 2, v27);
    v30 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "    We currently only handle sync requests (i.e. dwTimeToWait must be ASYNCH_WAIT_TIME).");
    WriteDbgTraceWarningWI("PowerEventHandler::ProcessEvent", v30);
    WiaTrcLib::Free((WiaTrcLib *)v30, v31);
    v32 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "    We currently only handle sync requests (i.e. dwTimeToWait must be ASYNCH_WAIT_TIME).");
    WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"PowerEventHandler::ProcessEvent", 2, v32);
    return (unsigned int)-2147024809;
  }
  v7 = 0;
  v80 = 0;
  if ( a3 == 13 )
  {
    v81 = 0;
    v85[0] = "Unknown Power Message";
    v85[1] = "PBT_APMQUERYSUSPEND";
    v85[2] = "PBT_APMQUERYSTANDBY";
    v85[3] = "PBT_APMQUERYSUSPENDFAILED";
    v85[4] = "PBT_APMQUERYSTANDBYFAILED";
    v85[5] = "PBT_APMSUSPEND";
    v85[6] = "PBT_APMSTANDBY";
    v85[7] = "PBT_APMRESUMECRITICAL";
    v85[8] = "PBT_APMRESUMESUSPEND";
    v85[9] = "PBT_APMRESUMESTANDBY";
    v85[10] = "PBT_APMBATTERYLOW";
    v85[11] = "PBT_APMPOWERSTATUSCHANGE";
    v85[12] = "PBT_APMOEMEVENT";
    v85[19] = "PBT_APMRESUMEAUTOMATIC";
    v85[13] = "Unknown Power Message";
    v85[14] = "Unknown Power Message";
    v85[15] = "Unknown Power Message";
    v85[16] = "Unknown Power Message";
    v85[17] = "Unknown Power Message";
    v85[18] = "Unknown Power Message";
    if ( a4 == 32787 )
    {
      v45 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      2,
                      0,
                      "Message from Power Management: PBT_POWERSETTINGCHANGE");
      WriteDbgTraceInfoWI("PowerEventHandler::ProcessEvent", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v47 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Message from Power Management: PBT_POWERSETTINGCHANGE");
      v14 = 4;
      WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"PowerEventHandler::ProcessEvent", 4, v47);
      if ( a5 )
      {
        v50 = *a5 - *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1;
        if ( *a5 == *(_QWORD *)&GUID_LOW_POWER_EPOCH.Data1 )
          v50 = a5[1] - *(_QWORD *)GUID_LOW_POWER_EPOCH.Data4;
        if ( !v50 && *((_DWORD *)a5 + 4) == 4 )
        {
          if ( *((_DWORD *)a5 + 5) )
          {
            v51 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Entering Connected Standby...");
            WriteDbgTraceInfoWI("PowerEventHandler::ProcessEvent", v51);
            WiaTrcLib::Free((WiaTrcLib *)v51, v52);
            v53 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Entering Connected Standby...");
            WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"PowerEventHandler::ProcessEvent", 4, v53);
            v5 = 4;
            v81 = 3;
          }
          else
          {
            v73 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Leaving Connected Standby...");
            WriteDbgTraceInfoWI("PowerEventHandler::ProcessEvent", v73);
            WiaTrcLib::Free((WiaTrcLib *)v73, v74);
            v75 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Leaving Connected Standby...");
            WiaTrace_ProcessTrace_Ex(v77, v76, (void *)"PowerEventHandler::ProcessEvent", 4, v75);
            v5 = 7;
            v81 = 4;
          }
        }
LABEL_6:
        ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v83);
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v86, L"DeviceListManager");
        if ( v84 )
        {
          v17 = (DeviceListManager *)CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<DeviceListManager>(v84, &v86);
        }
        else
        {
          v17 = 0;
          v40 = (char *)WiaTrace_TraceLogWithSubComp(
                          1,
                          "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                          v88);
          WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v40);
          WiaTrcLib::Free((WiaTrcLib *)v40, v41);
          v42 = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                           v88);
          WiaTrace_ProcessTrace_Ex(v44, v43, (void *)"ServiceComponentHolder::Get", 2, v42);
        }
        v86 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v88 && v88 != &v87 )
          operator delete(v88, v16);
        v88 = 0;
        v89 = 0;
        if ( !v17 )
        {
          v35 = (char *)WiaTrace_TraceLogWithSubComp(
                          1,
                          "The PowerEventHandler could not process the power message because the DeviceListManager is NULL!");
          WriteDbgTraceWarningWI("PowerEventHandler::ProcessEvent", v35);
          WiaTrcLib::Free((WiaTrcLib *)v35, v36);
          v37 = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "The PowerEventHandler could not process the power message because the DeviceListManager is NULL!");
          WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"PowerEventHandler::ProcessEvent", 2, v37);
          v7 = -2147418113;
LABEL_24:
          if ( v84 )
          {
            v23 = v84 + *(int *)(*(_QWORD *)v84 + 4LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          }
          return v7;
        }
        CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v90, L"WiaService");
        if ( v84 )
        {
          v82 = CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<WiaService>(v84, &v90);
        }
        else
        {
          v82 = 0;
          v56 = (char *)WiaTrace_TraceLogWithSubComp(
                          1,
                          "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                          v92);
          WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v56);
          WiaTrcLib::Free((WiaTrcLib *)v56, v57);
          v58 = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                           v92);
          WiaTrace_ProcessTrace_Ex(v60, v59, (void *)"ServiceComponentHolder::Get", 2, v58);
        }
        v90 = &CSimpleStringBase<unsigned short>::`vftable';
        if ( v92 && v92 != &v91 )
          operator delete(v92, v18);
        v92 = 0;
        v93 = 0;
        if ( !v82 )
        {
          v68 = (char *)WiaTrace_TraceLogWithSubComp(
                          1,
                          "The PowerEventHandler could not process the power message because the WiaService object is NULL!");
          WriteDbgTraceWarningWI("PowerEventHandler::ProcessEvent", v68);
          WiaTrcLib::Free((WiaTrcLib *)v68, v69);
          v70 = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "The PowerEventHandler could not process the power message because the WiaService object is NULL!");
          WiaTrace_ProcessTrace_Ex(v72, v71, (void *)"PowerEventHandler::ProcessEvent", 2, v70);
          v7 = -2147418113;
          goto LABEL_23;
        }
        v19 = v5 - 2;
        if ( v19 )
        {
          v20 = v19 - 2;
          if ( !v20 )
          {
            g_fSchedulePaused = 1;
            v7 = WiaService::Pause(0);
            v66 = 3;
            if ( v81 != 3 )
              v66 = 1;
            DeviceListManager::EnumerateDevicesWithCallback(
              v17,
              v66,
              0,
              (struct EnumDeviceInterface *)(((unsigned __int64)this + 16) & -(__int64)(this != 0)));
            DeviceListManager::ShutdownWSDChallenge(v67);
            goto LABEL_22;
          }
          if ( (unsigned int)(v20 - 2) >= 2 )
          {
            v7 = 0;
LABEL_22:
            v21 = v82 + *(int *)(*(_QWORD *)v82 + 4LL);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_23:
            v22 = (char *)v17 + *(int *)(*((_QWORD *)v17 + 1) + 4LL) + 8;
            (*(void (__fastcall **)(char *))(*(_QWORD *)v22 + 16LL))(v22);
            goto LABEL_24;
          }
          DeviceListManager::InitializeWSDChallenge(0);
          DeviceListManager::Enumerate(v17, 0);
          DeviceListManager::LoadUnloadDrivers(v17, v61, v62);
          v80 = WiaService::Continue(v63);
          g_fSchedulePaused = 0;
          v64 = (struct EnumDeviceInterface *)(((unsigned __int64)this + 16) & -(__int64)(this != 0));
          if ( v81 != 4 )
            v14 = 2;
          v65 = v14;
        }
        else
        {
          g_fSchedulePaused = 0;
          DeviceListManager::InitializeWSDChallenge(0);
          v65 = 2;
          v64 = (struct EnumDeviceInterface *)(((unsigned __int64)this + 16) & -(__int64)(this != 0));
        }
        DeviceListManager::EnumerateDevicesWithCallback(v17, v65, 0, v64);
        v7 = v80;
        goto LABEL_22;
      }
      v78 = (char *)WiaTrace_TraceLogWithSubComp(0, "PBT_POWERSETTINGCHANGE received without data, unable to process");
      WriteDbgTraceWarningWI("PowerEventHandler::ProcessEvent", v78);
      WiaTrcLib::Free((WiaTrcLib *)v78, v79);
      lpMem = (void **)WiaTrace_TraceWithSubComp(0, "PBT_POWERSETTINGCHANGE received without data, unable to process");
      v15 = 2;
    }
    else
    {
      v8 = (const char *)v85[(a4 + 1) & (unsigned int)-((unsigned int)(a4 + 1) < 0x14)];
      v9 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Message from Power Management: %s", v8);
      WriteDbgTraceInfoWI("PowerEventHandler::ProcessEvent", v9);
      WiaTrcLib::Free((WiaTrcLib *)v9, v10);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Message from Power Management: %s", v8);
      v14 = 4;
      v15 = 4;
    }
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"PowerEventHandler::ProcessEvent", v15, lpMem);
    goto LABEL_6;
  }
  return v7;
}

```

## disassembly

```asm
0x18000e080  mov     [rsp-8+arg_8], rbx
0x18000e085  push    rbp
0x18000e086  push    rsi
0x18000e087  push    rdi
0x18000e088  push    r12
0x18000e08a  push    r13
0x18000e08c  push    r14
0x18000e08e  push    r15
0x18000e090  lea     rbp, [rsp-260h]
0x18000e098  sub     rsp, 360h
0x18000e09f  mov     rax, cs:__security_cookie
0x18000e0a6  xor     rax, rsp
0x18000e0a9  mov     [rbp+290h+var_40], rax
0x18000e0b0  mov     r15d, r9d
0x18000e0b3  mov     rsi, rcx
0x18000e0b6  cmp     edx, 0FFFFFFFFh
0x18000e0b9  jnz     loc_18000E3A9
0x18000e0bf  xor     r14d, r14d
0x18000e0c2  mov     [rsp+390h+var_360], r14d
0x18000e0c7  cmp     r8d, 0Dh
0x18000e0cb  jnz     loc_18000E37C
0x18000e0d1  mov     [rsp+390h+var_35C], r14d
0x18000e0d6  lea     rcx, aUnknownPowerMe; "Unknown Power Message"
0x18000e0dd  mov     [rsp+390h+var_340], rcx
0x18000e0e2  lea     rax, aPbtApmquerysus_0; "PBT_APMQUERYSUSPEND"
0x18000e0e9  mov     [rsp+390h+var_338], rax
0x18000e0ee  lea     rax, aPbtApmquerysta_0; "PBT_APMQUERYSTANDBY"
0x18000e0f5  mov     [rsp+390h+var_330], rax
0x18000e0fa  lea     rax, aPbtApmquerysus; "PBT_APMQUERYSUSPENDFAILED"
0x18000e101  mov     [rsp+390h+var_328], rax
0x18000e106  lea     rax, aPbtApmquerysta; "PBT_APMQUERYSTANDBYFAILED"
0x18000e10d  mov     [rsp+390h+var_320], rax
0x18000e112  lea     rax, aPbtApmsuspend; "PBT_APMSUSPEND"
0x18000e119  mov     [rsp+390h+var_318], rax
0x18000e11e  lea     rax, aPbtApmstandby; "PBT_APMSTANDBY"
0x18000e125  mov     [rbp+290h+var_310], rax
0x18000e129  lea     rax, aPbtApmresumecr; "PBT_APMRESUMECRITICAL"
0x18000e130  mov     [rbp+290h+var_308], rax
0x18000e134  lea     rax, aPbtApmresumesu; "PBT_APMRESUMESUSPEND"
0x18000e13b  mov     [rbp+290h+var_300], rax
0x18000e13f  lea     rax, aPbtApmresumest; "PBT_APMRESUMESTANDBY"
0x18000e146  mov     [rbp+290h+var_2F8], rax
0x18000e14a  lea     rax, aPbtApmbatteryl; "PBT_APMBATTERYLOW"
0x18000e151  mov     [rbp+290h+var_2F0], rax
0x18000e155  lea     rax, aPbtApmpowersta; "PBT_APMPOWERSTATUSCHANGE"
0x18000e15c  mov     [rbp+290h+var_2E8], rax
0x18000e160  lea     rax, aPbtApmoemevent; "PBT_APMOEMEVENT"
0x18000e167  mov     [rbp+290h+var_2E0], rax
0x18000e16b  lea     rax, aPbtApmresumeau; "PBT_APMRESUMEAUTOMATIC"
0x18000e172  mov     [rbp+290h+var_2A8], rax
0x18000e176  lea     r14d, [r8-0Bh]
0x18000e17a  mov     [rbp+290h+var_2D8], rcx
0x18000e17e  mov     [rbp+290h+var_2D0], rcx
0x18000e182  mov     [rbp+290h+var_2C8], rcx
0x18000e186  mov     [rbp+290h+var_2C0], rcx
0x18000e18a  mov     [rbp+290h+var_2B8], rcx
0x18000e18e  mov     [rbp+290h+var_2B0], rcx
0x18000e192  cmp     r9d, 8013h
0x18000e199  jz      loc_18000E501
0x18000e19f  lea     ecx, [r9+1]
0x18000e1a3  cmp     ecx, 14h
0x18000e1a6  lea     r8, aMessageFromPow; "Message from Power Management: %s"
0x18000e1ad  sbb     eax, eax
0x18000e1af  xor     edx, edx
0x18000e1b1  and     eax, ecx
0x18000e1b3  mov     ecx, r14d
0x18000e1b6  mov     rdi, [rsp+rax*8+390h+var_340]
0x18000e1bb  mov     r9, rdi
0x18000e1be  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000e1c3  lea     r13, aPowereventhand; "PowerEventHandler::ProcessEvent"
0x18000e1ca  mov     rdx, rax; char *
0x18000e1cd  mov     rcx, r13; char *
0x18000e1d0  mov     rbx, rax
0x18000e1d3  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000e1d8  mov     rcx, rbx; this
0x18000e1db  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000e1e0  mov     r9, rdi
0x18000e1e3  lea     r8, aMessageFromPow; "Message from Power Management: %s"
0x18000e1ea  xor     edx, edx
0x18000e1ec  mov     ecx, r14d
0x18000e1ef  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000e1f4  lea     r12d, [r14+2]
0x18000e1f8  mov     r9d, r12d; int
0x18000e1fb  mov     r8, r13; int
0x18000e1fe  mov     [rsp+390h+lpMem], rax; lpMem
0x18000e203  call    WiaTrace_ProcessTrace_Ex
0x18000e208  lea     rcx, [rsp+390h+var_350]; this
0x18000e20d  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18000e212  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x18000e219  lea     rcx, [rbp+290h+var_2A0]
0x18000e21d  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000e222  mov     rcx, [rsp+390h+var_348]
0x18000e227  mov     ebx, 1
0x18000e22c  test    rcx, rcx
0x18000e22f  jz      loc_18000E49F
0x18000e235  lea     rdx, [rbp+290h+var_2A0]
0x18000e239  call    ??$Get@VDeviceListManager@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x18000e23e  mov     rdi, rax
0x18000e241  mov     rcx, [rbp+290h+var_198]; void *
0x18000e248  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000e24f  mov     [rbp+290h+var_2A0], rax
0x18000e253  test    rcx, rcx
0x18000e256  jz      short loc_18000E265
0x18000e258  lea     rax, [rbp+290h+var_298]
0x18000e25c  cmp     rcx, rax
0x18000e25f  jnz     loc_18000E799
0x18000e265  mov     [rbp+290h+var_198], 0
0x18000e270  mov     [rbp+290h+var_190], 0
0x18000e27b  test    rdi, rdi
0x18000e27e  jz      loc_18000E448
0x18000e284  lea     rdx, aWiaservice; "WiaService"
0x18000e28b  lea     rcx, [rbp+290h+var_170]
0x18000e292  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000e297  mov     rax, [rsp+390h+var_348]
0x18000e29c  test    rax, rax
0x18000e29f  jz      loc_18000E5F1
0x18000e2a5  lea     rdx, [rbp+290h+var_170]
0x18000e2ac  mov     rcx, rax
0x18000e2af  call    ??$Get@VWiaService@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVWiaService@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<WiaService>(CSimpleStringBase<ushort> const &)
0x18000e2b4  mov     [rsp+390h+var_358], rax
0x18000e2b9  mov     rcx, [rbp+290h+var_68]; void *
0x18000e2c0  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000e2c7  mov     [rbp+290h+var_170], rax
0x18000e2ce  test    rcx, rcx
0x18000e2d1  jz      short loc_18000E2E3
0x18000e2d3  lea     rax, [rbp+290h+var_168]
0x18000e2da  cmp     rcx, rax
0x18000e2dd  jnz     loc_18000E7A3
0x18000e2e3  xor     ecx, ecx; this
0x18000e2e5  mov     [rbp+290h+var_68], rcx
0x18000e2ec  mov     [rbp+290h+var_60], rcx
0x18000e2f3  cmp     [rsp+390h+var_358], rcx
0x18000e2f8  jz      loc_18000E6F6
0x18000e2fe  sub     r15d, r14d
0x18000e301  jz      loc_18000E7E7
0x18000e307  sub     r15d, r14d
0x18000e30a  jz      loc_18000E6B6
0x18000e310  sub     r15d, r14d
0x18000e313  jz      loc_18000E65C
0x18000e319  cmp     r15d, 1
0x18000e31d  jz      loc_18000E65C
0x18000e323  mov     r14d, ecx
0x18000e326  mov     rbx, [rsp+390h+var_358]
0x18000e32b  mov     rax, [rbx]
0x18000e32e  movsxd  rcx, dword ptr [rax+4]
0x18000e332  add     rcx, rbx
0x18000e335  mov     rax, [rcx]
0x18000e338  mov     rax, [rax+10h]
0x18000e33c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e341  mov     rax, [rdi+8]
0x18000e345  movsxd  rcx, dword ptr [rax+4]
0x18000e349  add     rcx, 8
0x18000e34d  add     rcx, rdi
0x18000e350  mov     rax, [rcx]
0x18000e353  mov     rax, [rax+10h]
0x18000e357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e35c  mov     rdx, [rsp+390h+var_348]
0x18000e361  test    rdx, rdx
0x18000e364  jz      short loc_18000E37C
0x18000e366  mov     rax, [rdx]
0x18000e369  movsxd  rcx, dword ptr [rax+4]
0x18000e36d  add     rcx, rdx
0x18000e370  mov     rax, [rcx]
0x18000e373  mov     rax, [rax+10h]
0x18000e377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e37c  mov     eax, r14d
0x18000e37f  mov     rcx, [rbp+290h+var_40]
0x18000e386  xor     rcx, rsp; StackCookie
0x18000e389  call    __security_check_cookie
0x18000e38e  mov     rbx, [rsp+390h+arg_8]
0x18000e396  add     rsp, 360h
0x18000e39d  pop     r15
0x18000e39f  pop     r14
0x18000e3a1  pop     r13
0x18000e3a3  pop     r12
0x18000e3a5  pop     rdi
0x18000e3a6  pop     rsi
0x18000e3a7  pop     rbp
0x18000e3a8  retn
0x18000e3a9  mov     esi, 1
0x18000e3ae  lea     rdx, aThePowereventh_4; "The PowerEventHandler received an async"...
0x18000e3b5  mov     ecx, esi
0x18000e3b7  call    WiaTrace_TraceLogWithSubComp
0x18000e3bc  lea     r13, aPowereventhand; "PowerEventHandler::ProcessEvent"
0x18000e3c3  mov     rdx, rax; char *
0x18000e3c6  mov     rcx, r13; char *
0x18000e3c9  mov     rbx, rax
0x18000e3cc  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000e3d1  mov     rcx, rbx; this
0x18000e3d4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000e3d9  lea     rdx, aThePowereventh_4; "The PowerEventHandler received an async"...
0x18000e3e0  mov     ecx, esi
0x18000e3e2  call    WiaTrace_TraceWithSubComp
0x18000e3e7  lea     r14d, [rsi+1]
0x18000e3eb  mov     [rsp+390h+lpMem], rax; lpMem
0x18000e3f0  mov     r9d, r14d; int
0x18000e3f3  mov     r8, r13; int
0x18000e3f6  call    WiaTrace_ProcessTrace_Ex
0x18000e3fb  lea     rdx, aWeCurrentlyOnl; "    We currently only handle sync reque"...
0x18000e402  mov     ecx, esi
0x18000e404  call    WiaTrace_TraceLogWithSubComp
0x18000e409  mov     rdx, rax; char *
0x18000e40c  mov     rcx, r13; char *
0x18000e40f  mov     rbx, rax
0x18000e412  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000e417  mov     rcx, rbx; this
0x18000e41a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000e41f  lea     rdx, aWeCurrentlyOnl; "    We currently only handle sync reque"...
0x18000e426  mov     ecx, esi
0x18000e428  call    WiaTrace_TraceWithSubComp
0x18000e42d  mov     r9d, r14d; int
0x18000e430  mov     [rsp+390h+lpMem], rax; lpMem
0x18000e435  mov     r8, r13; int
0x18000e438  call    WiaTrace_ProcessTrace_Ex
0x18000e43d  mov     r14d, 80070057h
0x18000e443  jmp     loc_18000E37C
0x18000e448  lea     rdx, aThePowereventh_3; "The PowerEventHandler could not process"...
0x18000e44f  mov     ecx, ebx
0x18000e451  call    WiaTrace_TraceLogWithSubComp
0x18000e456  mov     rdx, rax; char *
0x18000e459  mov     rcx, r13; char *
0x18000e45c  mov     rbx, rax
0x18000e45f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000e464  mov     rcx, rbx; this
0x18000e467  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000e46c  lea     rdx, aThePowereventh_3; "The PowerEventHandler could not process"...
0x18000e473  mov     ecx, 1
0x18000e478  call    WiaTrace_TraceWithSubComp
0x18000e47d  mov     r9d, r14d; int
0x18000e480  mov     [rsp+390h+lpMem], rax; lpMem
0x18000e485  mov     r8, r13; int
0x18000e488  call    WiaTrace_ProcessTrace_Ex
0x18000e48d  mov     [rsp+390h+var_360], 8000FFFFh
0x18000e495  mov     r14d, [rsp+390h+var_360]
0x18000e49a  jmp     loc_18000E35C
0x18000e49f  mov     r8, [rbp+290h+var_198]
0x18000e4a6  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000e4ad  mov     ecx, ebx
0x18000e4af  xor     edi, edi
0x18000e4b1  call    WiaTrace_TraceLogWithSubComp
0x18000e4b6  mov     rdx, rax; char *
0x18000e4b9  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x18000e4c0  mov     rbx, rax
0x18000e4c3  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000e4c8  mov     rcx, rbx; this
0x18000e4cb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000e4d0  mov     r8, [rbp+290h+var_198]
0x18000e4d7  lea     ebx, [rdi+1]
0x18000e4da  mov     ecx, ebx
0x18000e4dc  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000e4e3  call    WiaTrace_TraceWithSubComp
0x18000e4e8  mov     r9d, r14d; int
0x18000e4eb  mov     [rsp+390h+lpMem], rax; lpMem
0x18000e4f0  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x18000e4f7  call    WiaTrace_ProcessTrace_Ex
0x18000e4fc  jmp     loc_18000E241
0x18000e501  lea     r8, aMessageFromPow_0; "Message from Power Management: PBT_POWE"...
0x18000e508  xor     edx, edx
0x18000e50a  mov     ecx, r14d
0x18000e50d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000e512  lea     r13, aPowereventhand; "PowerEventHandler::ProcessEvent"
0x18000e519  mov     rdx, rax; char *
0x18000e51c  mov     rcx, r13; char *
0x18000e51f  mov     rbx, rax
0x18000e522  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000e527  mov     rcx, rbx; this
0x18000e52a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000e52f  lea     r8, aMessageFromPow_0; "Message from Power Management: PBT_POWE"...
0x18000e536  xor     edx, edx
0x18000e538  mov     ecx, r14d
0x18000e53b  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000e540  mov     r12d, 4
0x18000e546  mov     [rsp+390h+lpMem], rax; lpMem
0x18000e54b  mov     r9d, r12d; int
0x18000e54e  mov     r8, r13; int
0x18000e551  call    WiaTrace_ProcessTrace_Ex
0x18000e556  mov     rcx, [rbp+290h+arg_20]
0x18000e55d  test    rcx, rcx
0x18000e560  jz      loc_18000E7AD
0x18000e566  mov     rax, [rcx]
0x18000e569  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data1
0x18000e570  jnz     short loc_18000E57D
0x18000e572  mov     rax, [rcx+8]
0x18000e576  sub     rax, qword ptr cs:GUID_LOW_POWER_EPOCH.Data4
0x18000e57d  test    rax, rax
0x18000e580  jnz     loc_18000E208
0x18000e586  cmp     [rcx+10h], r12d
0x18000e58a  jnz     loc_18000E208
0x18000e590  xor     edx, edx
0x18000e592  cmp     [rcx+14h], edx
0x18000e595  mov     ecx, r14d
0x18000e598  jz      loc_18000E746
0x18000e59e  lea     r8, aEnteringConnec; "Entering Connected Standby..."
0x18000e5a5  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000e5aa  mov     rdx, rax; char *
0x18000e5ad  mov     rcx, r13; char *
0x18000e5b0  mov     rbx, rax
0x18000e5b3  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000e5b8  mov     rcx, rbx; this
0x18000e5bb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
  ... truncated ...
```
