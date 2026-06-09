# ServiceEventHandler::ProcessEvent(ulong,ulong,ulong,void *)

- ea: `0x18000ecf0`
- end: `0x18000f4f3`
- name: `?ProcessEvent@ServiceEventHandler@@UEAAJKKKPEAX@Z`
- size: `2051`
- prototype: `__int64 __fastcall(ServiceEventHandler *__hidden this, unsigned int, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000557c`
- `0x180006300`
- `0x18000645c`
- `0x180006a2c`
- `0x180006c24`
- `0x1800085b0`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000ecf0`
- `0x18000f4fc`
- `0x18000f928`
- `0x18000fc60`
- `0x180011a94`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e72c`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033cc0`
- `0x18003ae9c`
- `0x180078010`

## string_xrefs

- `0x18000eda1`: `The WiaService object is NULL`
- `0x18000edcd`: `The WiaService object is NULL`
- `0x18000ed2c`: `WiaService`
- `0x18000edb0`: `ServiceEventHandler::ProcessEvent`
- `0x18000ee7f`: `ServiceEventHandler::ProcessEvent`
- `0x18000f0cf`: `ServiceEventHandler::ProcessEvent`
- `0x18000f23b`: `ServiceEventHandler::ProcessEvent`
- `0x18000f2fb`: `ServiceEventHandler::ProcessEvent`
- `0x18000f397`: `ServiceEventHandler::ProcessEvent`
- `0x18000f42b`: `ServiceEventHandler::ProcessEvent`
- `0x18000f4ad`: `ServiceEventHandler::ProcessEvent`
- `0x18000ee6e`: `The ServiceEventHandler received a SERVICE_CONTROL_INTERROGATE and may update the service status for interrogation`
- `0x18000ee9c`: `The ServiceEventHandler received a SERVICE_CONTROL_INTERROGATE and may update the service status for interrogation`
- `0x18000eec0`: `ServiceStatus`
- `0x18000ef9a`: `ServiceComponentHolder::Get`
- `0x18000efcc`: `ServiceComponentHolder::Get`
- `0x18000f041`: `ServiceComponentHolder::Get`
- `0x18000f077`: `ServiceComponentHolder::Get`
- `0x18000ef85`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000efb5`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000f02c`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000f05f`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000efdd`: `We received a SERVICE_CONTROL_INTERROGATE message, but could not notify the controller of our current status`
- `0x18000efff`: `We received a SERVICE_CONTROL_INTERROGATE message, but could not notify the controller of our current status`
- `0x18000f41a`: `The ServiceEventHandler received a SERVICE_CONTROL_STOP and is now Stopping the service`
- `0x18000f448`: `The ServiceEventHandler received a SERVICE_CONTROL_STOP and is now Stopping the service`
- `0x18000f386`: `The ServiceEventHandler received a SERVICE_CONTROL_PAUSE and is now Pausing the service`
- `0x18000f3b4`: `The ServiceEventHandler received a SERVICE_CONTROL_PAUSE and is now Pausing the service`
- `0x18000f22a`: `The ServiceEventHandler received a SERVICE_CONTROL_SHUTDOWN and is now Stopping the service`
- `0x18000f258`: `The ServiceEventHandler received a SERVICE_CONTROL_SHUTDOWN and is now Stopping the service`
- `0x18000f2ea`: `The ServiceEventHandler received a SERVICE_CONTROL_CONTINUE and is now UnPausing the service`
- `0x18000f318`: `The ServiceEventHandler received a SERVICE_CONTROL_CONTINUE and is now UnPausing the service`
- `0x18000f0be`: `The ServiceEventHandler received a STI_SERVICE_CONTROL_REFRESH message`
- `0x18000f0ec`: `The ServiceEventHandler received a STI_SERVICE_CONTROL_REFRESH message`
- `0x18000f49e`: `The ServiceEventHandler received a call to process an event where dwTimeToWait is not SYNC_WAIT_TIME!`
- `0x18000f4ca`: `The ServiceEventHandler received a call to process an event where dwTimeToWait is not SYNC_WAIT_TIME!`

## pseudocode

```c
__int64 __fastcall ServiceEventHandler::ProcessEvent(ServiceEventHandler *this, int a2, int a3)
{
  __int64 v5; // r12
  unsigned __int64 v6; // rdx
  __int64 v7; // r8
  WiaService *v8; // r15
  void *v9; // rcx
  char *v10; // rbx
  void *v11; // rdx
  void **lpMem; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  unsigned int UnloadDrivers; // esi
  __int64 v16; // rcx
  int v18; // edi
  int v19; // edi
  int v20; // edi
  int v21; // edi
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // r14
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // r8
  char *v32; // rcx
  char *v33; // rbx
  void *v34; // rdx
  void **v35; // rax
  void *v36; // rdx
  __int64 v37; // rcx
  char *v38; // rbx
  void *v39; // rdx
  void **v40; // rax
  void *v41; // rdx
  __int64 v42; // rcx
  char *v43; // rbx
  void *v44; // rdx
  void **v45; // rax
  void *v46; // rdx
  __int64 v47; // rcx
  int v48; // edi
  char *v49; // rbx
  void *v50; // rdx
  void **v51; // rax
  void *v52; // rdx
  __int64 v53; // rcx
  DeviceListManager *v54; // rbx
  __int64 v55; // rdx
  __int64 v56; // r8
  char *v57; // rcx
  char *v58; // rbx
  void *v59; // rdx
  void **v60; // rax
  void *v61; // rdx
  __int64 v62; // rcx
  __int64 *v63; // rdx
  char *v64; // rbx
  void *v65; // rdx
  void **v66; // rax
  void *v67; // rdx
  __int64 v68; // rcx
  WiaService *v69; // rcx
  char *v70; // rbx
  void *v71; // rdx
  void **v72; // rax
  void *v73; // rdx
  __int64 v74; // rcx
  WiaService *v75; // rcx
  char *v76; // rbx
  void *v77; // rdx
  void **v78; // rax
  void *v79; // rdx
  __int64 v80; // rcx
  WiaService *v81; // rcx
  char *v82; // rbx
  void *v83; // rdx
  void **v84; // rax
  void *v85; // rdx
  __int64 v86; // rcx
  WiaService *v87; // rcx
  char *v88; // rbx
  void *v89; // rdx
  void **v90; // rax
  void *v91; // rdx
  __int64 v92; // rcx
  char v93[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v94; // [rsp+38h] [rbp-C8h]
  const unsigned __int64 *v95; // [rsp+40h] [rbp-C0h] BYREF
  char v96; // [rsp+48h] [rbp-B8h] BYREF
  void *v97; // [rsp+148h] [rbp+48h]
  __int64 v98; // [rsp+150h] [rbp+50h]
  const unsigned __int64 *v99; // [rsp+170h] [rbp+70h] BYREF
  char v100; // [rsp+178h] [rbp+78h] BYREF
  void *v101; // [rsp+278h] [rbp+178h]
  __int64 v102; // [rsp+280h] [rbp+180h]
  _QWORD v103[38]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v104[16]; // [rsp+3D0h] [rbp+2D0h] BYREF

  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v93);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v95, L"WiaService");
  v5 = v94;
  if ( v94 )
  {
    v8 = (WiaService *)CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<WiaService>(v94, &v95);
  }
  else
  {
    v8 = 0;
    v33 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                    v97);
    WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v33);
    WiaTrcLib::Free((WiaTrcLib *)v33, v34);
    v35 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                     v97);
    WiaTrace_ProcessTrace_Ex(v37, v36, (void *)"ServiceComponentHolder::Get", 2, v35);
  }
  v9 = v97;
  v95 = &CSimpleStringBase<unsigned short>::`vftable';
  if ( v97 && v97 != &v96 )
    operator delete(v97, v6);
  v97 = 0;
  v98 = 0;
  if ( !v8 )
  {
    v10 = (char *)WiaTrace_TraceLogWithSubComp(1, "The WiaService object is NULL");
    WriteDbgTraceWarningWI("ServiceEventHandler::ProcessEvent", v10);
    WiaTrcLib::Free((WiaTrcLib *)v10, v11);
    lpMem = (void **)WiaTrace_TraceWithSubComp(1, "The WiaService object is NULL");
    WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"ServiceEventHandler::ProcessEvent", 2, lpMem);
    UnloadDrivers = -2147418113;
    goto LABEL_8;
  }
  if ( a2 == -1 )
  {
    UnloadDrivers = 0;
    v18 = a3 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          v21 = v20 - 1;
          if ( v21 )
          {
            v48 = v21 - 1;
            if ( v48 )
            {
              if ( v48 != 123 )
                goto LABEL_26;
              if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
                McGenEventWrite_EventWriteTransfer(v9, DocPerf_Wia_ServiceRefresh_Start, v7, 1, v104);
              v49 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                              2,
                              0,
                              "The ServiceEventHandler received a STI_SERVICE_CONTROL_REFRESH message");
              WriteDbgTraceInfoWI("ServiceEventHandler::ProcessEvent", v49);
              WiaTrcLib::Free((WiaTrcLib *)v49, v50);
              v51 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                               2,
                               0,
                               "The ServiceEventHandler received a STI_SERVICE_CONTROL_REFRESH message");
              WiaTrace_ProcessTrace_Ex(v53, v52, (void *)"ServiceEventHandler::ProcessEvent", 4, v51);
              CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v103, L"DeviceListManager");
              v54 = (DeviceListManager *)ServiceComponentHolder::Get<DeviceListManager>(v93, v103);
              v103[0] = &CSimpleStringBase<unsigned short>::`vftable';
              CSimpleStringBase<unsigned short>::DeleteStorage(v103);
              v103[34] = 0;
              if ( v54 )
              {
                DeviceListManager::Enumerate(v54, 0);
                UnloadDrivers = DeviceListManager::LoadUnloadDrivers(v54, v55, v56);
                v57 = (char *)v54 + *(int *)(*((_QWORD *)v54 + 1) + 4LL) + 8;
                (*(void (__fastcall **)(char *))(*(_QWORD *)v57 + 16LL))(v57);
              }
              else
              {
                v58 = (char *)WiaTrace_TraceLog("We could not refresh the device list because the DeviceListManager object is NULL");
                WriteDbgTraceErrorWI("ServiceEventHandler::ProcessEvent", v58);
                WiaTrcLib::Free((WiaTrcLib *)v58, v59);
                v60 = (void **)WiaTrace_Trace("We could not refresh the device list because the DeviceListManager object is NULL");
                WiaTrace_ProcessTrace_Ex(v62, v61, (void *)"ServiceEventHandler::ProcessEvent", 1, v60);
                UnloadDrivers = -2147418113;
              }
              WiaService::CheckForActivityAndShutdown(v8);
              if ( (Microsoft_Windows_DocumentsEnableBits & 2) == 0 )
                goto LABEL_26;
              v63 = DocPerf_Wia_ServiceRefresh_Stop;
            }
            else
            {
              if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
                McGenEventWrite_EventWriteTransfer(v9, DocPerf_Wia_ServiceShutdown_Start, v7, 1, v104);
              v64 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                              2,
                              0,
                              "The ServiceEventHandler received a SERVICE_CONTROL_SHUTDOWN and is now Stopping the service");
              WriteDbgTraceInfoWI("ServiceEventHandler::ProcessEvent", v64);
              WiaTrcLib::Free((WiaTrcLib *)v64, v65);
              v66 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                               2,
                               0,
                               "The ServiceEventHandler received a SERVICE_CONTROL_SHUTDOWN and is now Stopping the service");
              WiaTrace_ProcessTrace_Ex(v68, v67, (void *)"ServiceEventHandler::ProcessEvent", 4, v66);
              WiaService::Stop(v69);
              if ( (Microsoft_Windows_DocumentsEnableBits & 2) == 0 )
                goto LABEL_26;
              v63 = DocPerf_Wia_ServiceShutdown_Stop;
            }
          }
          else
          {
            if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
              McGenEventWrite_EventWriteTransfer(v9, DocPerf_Wia_ServiceInterrogate_Start, v7, 1, v104);
            v22 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                            2,
                            0,
                            "The ServiceEventHandler received a SERVICE_CONTROL_INTERROGATE and may update the service st"
                            "atus for interrogation");
            WriteDbgTraceInfoWI("ServiceEventHandler::ProcessEvent", v22);
            WiaTrcLib::Free((WiaTrcLib *)v22, v23);
            v24 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                             2,
                             0,
                             "The ServiceEventHandler received a SERVICE_CONTROL_INTERROGATE and may update the service s"
                             "tatus for interrogation");
            WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"ServiceEventHandler::ProcessEvent", 4, v24);
            CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v99, L"ServiceStatus");
            if ( v5 )
            {
              v28 = CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<ServiceStatus>(v5, &v99);
            }
            else
            {
              v28 = 0;
              v43 = (char *)WiaTrace_TraceLogWithSubComp(
                              1,
                              "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                              v101);
              WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v43);
              WiaTrcLib::Free((WiaTrcLib *)v43, v44);
              v45 = (void **)WiaTrace_TraceWithSubComp(
                               1,
                               "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                               v101);
              WiaTrace_ProcessTrace_Ex(v47, v46, (void *)"ServiceComponentHolder::Get", 2, v45);
            }
            v99 = &CSimpleStringBase<unsigned short>::`vftable';
            if ( v101 && v101 != &v100 )
              operator delete(v101, v27);
            v101 = 0;
            v102 = 0;
            if ( v28 )
            {
              (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v28)(v28, 0, 0);
              v29 = v28 + *(int *)(*(_QWORD *)(v28 + 8) + 4LL) + 8LL;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
            }
            else
            {
              v38 = (char *)WiaTrace_TraceLog("We received a SERVICE_CONTROL_INTERROGATE message, but could not notify th"
                                              "e controller of our current status");
              WriteDbgTraceErrorWI("ServiceEventHandler::ProcessEvent", v38);
              WiaTrcLib::Free((WiaTrcLib *)v38, v39);
              v40 = (void **)WiaTrace_Trace(
                               "We received a SERVICE_CONTROL_INTERROGATE message, but could not notify the controller of"
                               " our current status");
              WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"ServiceEventHandler::ProcessEvent", 1, v40);
              UnloadDrivers = -2147418113;
            }
            WiaService::CheckForActivityAndShutdown(v8);
            if ( (Microsoft_Windows_DocumentsEnableBits & 2) == 0 )
              goto LABEL_26;
            v63 = DocPerf_Wia_ServiceInterrogate_Stop;
          }
        }
        else
        {
          if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
            McGenEventWrite_EventWriteTransfer(v9, DocPerf_Wia_ServiceContinue_Start, v7, 1, v104);
          v70 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "The ServiceEventHandler received a SERVICE_CONTROL_CONTINUE and is now UnPausing the service");
          WriteDbgTraceInfoWI("ServiceEventHandler::ProcessEvent", v70);
          WiaTrcLib::Free((WiaTrcLib *)v70, v71);
          v72 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           2,
                           0,
                           "The ServiceEventHandler received a SERVICE_CONTROL_CONTINUE and is now UnPausing the service");
          WiaTrace_ProcessTrace_Ex(v74, v73, (void *)"ServiceEventHandler::ProcessEvent", 4, v72);
          WiaService::Continue(v75);
          WiaService::CheckForActivityAndShutdown(v8);
          if ( (Microsoft_Windows_DocumentsEnableBits & 2) == 0 )
            goto LABEL_26;
          v63 = DocPerf_Wia_ServiceContinue_Stop;
        }
      }
      else
      {
        if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
          McGenEventWrite_EventWriteTransfer(v9, DocPerf_Wia_ServicePause_Start, v7, 1, v104);
        v76 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        2,
                        0,
                        "The ServiceEventHandler received a SERVICE_CONTROL_PAUSE and is now Pausing the service");
        WriteDbgTraceInfoWI("ServiceEventHandler::ProcessEvent", v76);
        WiaTrcLib::Free((WiaTrcLib *)v76, v77);
        v78 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         2,
                         0,
                         "The ServiceEventHandler received a SERVICE_CONTROL_PAUSE and is now Pausing the service");
        WiaTrace_ProcessTrace_Ex(v80, v79, (void *)"ServiceEventHandler::ProcessEvent", 4, v78);
        WiaService::Pause(v81);
        if ( (Microsoft_Windows_DocumentsEnableBits & 2) == 0 )
          goto LABEL_26;
        v63 = DocPerf_Wia_ServicePause_Stop;
      }
    }
    else
    {
      if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(v9, DocPerf_Wia_ServiceStop_Start, v7, 1, v104);
      v82 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      2,
                      0,
                      "The ServiceEventHandler received a SERVICE_CONTROL_STOP and is now Stopping the service");
      WriteDbgTraceInfoWI("ServiceEventHandler::ProcessEvent", v82);
      WiaTrcLib::Free((WiaTrcLib *)v82, v83);
      v84 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       2,
                       0,
                       "The ServiceEventHandler received a SERVICE_CONTROL_STOP and is now Stopping the service");
      WiaTrace_ProcessTrace_Ex(v86, v85, (void *)"ServiceEventHandler::ProcessEvent", 4, v84);
      WiaService::Stop(v87);
      if ( (Microsoft_Windows_DocumentsEnableBits & 2) == 0 )
        goto LABEL_26;
      v63 = DocPerf_Wia_ServiceStop_Stop;
    }
    McGenEventWrite_EventWriteTransfer(v30, v63, v31, 1, v104);
  }
  else
  {
    v88 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "The ServiceEventHandler received a call to process an event where dwTimeToWait is not SYNC_WAIT_TIME!");
    WriteDbgTraceWarningWI("ServiceEventHandler::ProcessEvent", v88);
    WiaTrcLib::Free((WiaTrcLib *)v88, v89);
    v90 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "The ServiceEventHandler received a call to process an event where dwTimeToWait is not SYNC_WAIT_TIME!");
    WiaTrace_ProcessTrace_Ex(v92, v91, (void *)"ServiceEventHandler::ProcessEvent", 2, v90);
    UnloadDrivers = -2147024809;
  }
LABEL_26:
  v32 = (char *)v8 + *(int *)(*(_QWORD *)v8 + 4LL);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v32 + 16LL))(v32);
LABEL_8:
  if ( v5 )
  {
    v16 = v5 + *(int *)(*(_QWORD *)v5 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return UnloadDrivers;
}

```

## disassembly

```asm
0x18000ecf0  push    rbp
0x18000ecf2  push    rbx
0x18000ecf3  push    rsi
0x18000ecf4  push    rdi
0x18000ecf5  push    r12
0x18000ecf7  push    r13
0x18000ecf9  push    r14
0x18000ecfb  push    r15
0x18000ecfd  lea     rbp, [rsp-2F8h]
0x18000ed05  sub     rsp, 3F8h
0x18000ed0c  mov     rax, cs:__security_cookie
0x18000ed13  xor     rax, rsp
0x18000ed16  mov     [rbp+330h+var_50], rax
0x18000ed1d  lea     rcx, [rsp+430h+var_400]; this
0x18000ed22  mov     edi, r8d
0x18000ed25  mov     esi, edx
0x18000ed27  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18000ed2c  lea     rdx, aWiaservice; "WiaService"
0x18000ed33  lea     rcx, [rsp+430h+var_3F0]
0x18000ed38  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000ed3d  mov     r12, [rsp+430h+var_3F8]
0x18000ed42  mov     r13d, 1
0x18000ed48  lea     r14d, [r13+1]
0x18000ed4c  test    r12, r12
0x18000ed4f  jz      loc_18000EF81
0x18000ed55  lea     rdx, [rsp+430h+var_3F0]
0x18000ed5a  mov     rcx, r12
0x18000ed5d  call    ??$Get@VWiaService@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVWiaService@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<WiaService>(CSimpleStringBase<ushort> const &)
0x18000ed62  mov     r15, rax
0x18000ed65  mov     rcx, [rbp+330h+var_2E8]; void *
0x18000ed69  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000ed70  mov     [rsp+430h+var_3F0], rax
0x18000ed75  test    rcx, rcx
0x18000ed78  jz      short loc_18000ED88
0x18000ed7a  lea     rax, [rsp+430h+var_3E8]
0x18000ed7f  cmp     rcx, rax
0x18000ed82  jnz     loc_18000F18E
0x18000ed88  mov     [rbp+330h+var_2E8], 0
0x18000ed90  mov     [rbp+330h+var_2E0], 0
0x18000ed98  test    r15, r15
0x18000ed9b  jnz     loc_18000EE32
0x18000eda1  lea     rdx, aTheWiaserviceO; "The WiaService object is NULL"
0x18000eda8  mov     ecx, r13d
0x18000edab  call    WiaTrace_TraceLogWithSubComp
0x18000edb0  lea     rdi, aServiceeventha_0; "ServiceEventHandler::ProcessEvent"
0x18000edb7  mov     rdx, rax; char *
0x18000edba  mov     rcx, rdi; char *
0x18000edbd  mov     rbx, rax
0x18000edc0  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000edc5  mov     rcx, rbx; this
0x18000edc8  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000edcd  lea     rdx, aTheWiaserviceO; "The WiaService object is NULL"
0x18000edd4  mov     ecx, r13d
0x18000edd7  call    WiaTrace_TraceWithSubComp
0x18000eddc  mov     r9d, r14d; int
0x18000eddf  mov     [rsp+430h+lpMem], rax; lpMem
0x18000ede4  mov     r8, rdi; int
0x18000ede7  call    WiaTrace_ProcessTrace_Ex
0x18000edec  mov     esi, 8000FFFFh
0x18000edf1  test    r12, r12
0x18000edf4  jz      short loc_18000EE0D
0x18000edf6  mov     rax, [r12]
0x18000edfa  movsxd  rcx, dword ptr [rax+4]
0x18000edfe  add     rcx, r12
0x18000ee01  mov     rax, [rcx]
0x18000ee04  mov     rax, [rax+10h]
0x18000ee08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee0d  mov     eax, esi
0x18000ee0f  mov     rcx, [rbp+330h+var_50]
0x18000ee16  xor     rcx, rsp; StackCookie
0x18000ee19  call    __security_check_cookie
0x18000ee1e  add     rsp, 3F8h
0x18000ee25  pop     r15
0x18000ee27  pop     r14
0x18000ee29  pop     r13
0x18000ee2b  pop     r12
0x18000ee2d  pop     rdi
0x18000ee2e  pop     rsi
0x18000ee2f  pop     rbx
0x18000ee30  pop     rbp
0x18000ee31  retn
0x18000ee32  cmp     esi, 0FFFFFFFFh
0x18000ee35  jnz     loc_18000F49E
0x18000ee3b  xor     esi, esi
0x18000ee3d  sub     edi, r13d
0x18000ee40  jz      loc_18000F3F6
0x18000ee46  sub     edi, r13d
0x18000ee49  jz      loc_18000F362
0x18000ee4f  sub     edi, r13d
0x18000ee52  jz      loc_18000F2C6
0x18000ee58  sub     edi, r13d
0x18000ee5b  jnz     loc_18000F088
0x18000ee61  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x18000ee68  jnz     loc_18000F29A
0x18000ee6e  lea     r8, aTheServiceeven_0; "The ServiceEventHandler received a SERV"...
0x18000ee75  xor     edx, edx
0x18000ee77  mov     ecx, r14d
0x18000ee7a  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000ee7f  lea     rdi, aServiceeventha_0; "ServiceEventHandler::ProcessEvent"
0x18000ee86  mov     rdx, rax; char *
0x18000ee89  mov     rcx, rdi; char *
0x18000ee8c  mov     rbx, rax
0x18000ee8f  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000ee94  mov     rcx, rbx; this
0x18000ee97  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000ee9c  lea     r8, aTheServiceeven_0; "The ServiceEventHandler received a SERV"...
0x18000eea3  xor     edx, edx
0x18000eea5  mov     ecx, r14d
0x18000eea8  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000eead  mov     r9d, 4; int
0x18000eeb3  mov     [rsp+430h+lpMem], rax; lpMem
0x18000eeb8  mov     r8, rdi; int
0x18000eebb  call    WiaTrace_ProcessTrace_Ex
0x18000eec0  lea     rdx, aServicestatus; "ServiceStatus"
0x18000eec7  lea     rcx, [rbp+330h+var_2C0]
0x18000eecb  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000eed0  test    r12, r12
0x18000eed3  jz      loc_18000F025
0x18000eed9  lea     rdx, [rbp+330h+var_2C0]
0x18000eedd  mov     rcx, r12
0x18000eee0  call    ??$Get@VServiceStatus@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVServiceStatus@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<ServiceStatus>(CSimpleStringBase<ushort> const &)
0x18000eee5  mov     r14, rax
0x18000eee8  mov     rcx, [rbp+330h+var_1B8]; void *
0x18000eeef  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000eef6  mov     [rbp+330h+var_2C0], rax
0x18000eefa  test    rcx, rcx
0x18000eefd  jz      short loc_18000EF0C
0x18000eeff  lea     rax, [rbp+330h+var_2B8]
0x18000ef03  cmp     rcx, rax
0x18000ef06  jnz     loc_18000F198
0x18000ef0c  mov     [rbp+330h+var_1B8], rsi
0x18000ef13  mov     [rbp+330h+var_1B0], rsi
0x18000ef1a  test    r14, r14
0x18000ef1d  jz      loc_18000EFDD
0x18000ef23  mov     rax, [r14]
0x18000ef26  xor     r8d, r8d
0x18000ef29  xor     edx, edx
0x18000ef2b  mov     rcx, r14
0x18000ef2e  mov     rax, [rax]
0x18000ef31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef36  mov     rax, [r14+8]
0x18000ef3a  movsxd  rcx, dword ptr [rax+4]
0x18000ef3e  add     rcx, 8
0x18000ef42  add     rcx, r14
0x18000ef45  mov     rax, [rcx]
0x18000ef48  mov     rax, [rax+10h]
0x18000ef4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef51  mov     rcx, r15; this
0x18000ef54  call    ?CheckForActivityAndShutdown@WiaService@@QEAAJXZ; WiaService::CheckForActivityAndShutdown(void)
0x18000ef59  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000ef60  jnz     loc_18000F2BA
0x18000ef66  mov     rax, [r15]
0x18000ef69  movsxd  rcx, dword ptr [rax+4]
0x18000ef6d  add     rcx, r15
0x18000ef70  mov     rax, [rcx]
0x18000ef73  mov     rax, [rax+10h]
0x18000ef77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef7c  jmp     loc_18000EDF1
0x18000ef81  mov     r8, [rbp+330h+var_2E8]
0x18000ef85  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000ef8c  mov     ecx, r13d
0x18000ef8f  xor     r15d, r15d
0x18000ef92  call    WiaTrace_TraceLogWithSubComp
0x18000ef97  mov     rdx, rax; char *
0x18000ef9a  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x18000efa1  mov     rbx, rax
0x18000efa4  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000efa9  mov     rcx, rbx; this
0x18000efac  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000efb1  mov     r8, [rbp+330h+var_2E8]
0x18000efb5  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000efbc  mov     ecx, r13d
0x18000efbf  call    WiaTrace_TraceWithSubComp
0x18000efc4  mov     r9d, r14d; int
0x18000efc7  mov     [rsp+430h+lpMem], rax; lpMem
0x18000efcc  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x18000efd3  call    WiaTrace_ProcessTrace_Ex
0x18000efd8  jmp     loc_18000ED65
0x18000efdd  lea     rcx, aWeReceivedASer; "We received a SERVICE_CONTROL_INTERROGA"...
0x18000efe4  call    WiaTrace_TraceLog
0x18000efe9  mov     rdx, rax; char *
0x18000efec  mov     rcx, rdi; char *
0x18000efef  mov     rbx, rax
0x18000eff2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000eff7  mov     rcx, rbx; this
0x18000effa  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000efff  lea     rcx, aWeReceivedASer; "We received a SERVICE_CONTROL_INTERROGA"...
0x18000f006  call    WiaTrace_Trace
0x18000f00b  mov     r9d, r13d; int
0x18000f00e  mov     [rsp+430h+lpMem], rax; lpMem
0x18000f013  mov     r8, rdi; int
0x18000f016  call    WiaTrace_ProcessTrace_Ex
0x18000f01b  mov     esi, 8000FFFFh
0x18000f020  jmp     loc_18000EF51
0x18000f025  mov     r8, [rbp+330h+var_1B8]
0x18000f02c  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000f033  mov     ecx, r13d
0x18000f036  xor     r14d, r14d
0x18000f039  call    WiaTrace_TraceLogWithSubComp
0x18000f03e  mov     rdx, rax; char *
0x18000f041  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x18000f048  mov     rbx, rax
0x18000f04b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000f050  mov     rcx, rbx; this
0x18000f053  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000f058  mov     r8, [rbp+330h+var_1B8]
0x18000f05f  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000f066  mov     ecx, r13d
0x18000f069  call    WiaTrace_TraceWithSubComp
0x18000f06e  lea     r9d, [r14+2]; int
0x18000f072  mov     [rsp+430h+lpMem], rax; lpMem
0x18000f077  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x18000f07e  call    WiaTrace_ProcessTrace_Ex
0x18000f083  jmp     loc_18000EEE8
0x18000f088  sub     edi, r13d
0x18000f08b  jz      loc_18000F206
0x18000f091  cmp     edi, 7Bh ; '{'
0x18000f094  jnz     loc_18000EF66
0x18000f09a  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x18000f0a1  jz      short loc_18000F0BE
0x18000f0a3  lea     rax, [rbp+330h+var_60]
0x18000f0aa  mov     r9d, r13d
0x18000f0ad  lea     rdx, DocPerf_Wia_ServiceRefresh_Start
0x18000f0b4  mov     [rsp+430h+lpMem], rax
0x18000f0b9  call    McGenEventWrite_EventWriteTransfer
0x18000f0be  lea     r8, aTheServiceeven_5; "The ServiceEventHandler received a STI_"...
0x18000f0c5  xor     edx, edx
0x18000f0c7  mov     ecx, r14d
0x18000f0ca  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000f0cf  lea     rdi, aServiceeventha_0; "ServiceEventHandler::ProcessEvent"
0x18000f0d6  mov     rdx, rax; char *
0x18000f0d9  mov     rcx, rdi; char *
0x18000f0dc  mov     rbx, rax
0x18000f0df  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000f0e4  mov     rcx, rbx; this
0x18000f0e7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000f0ec  lea     r8, aTheServiceeven_5; "The ServiceEventHandler received a STI_"...
0x18000f0f3  xor     edx, edx
0x18000f0f5  mov     ecx, r14d
0x18000f0f8  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000f0fd  mov     r9d, 4; int
0x18000f103  mov     [rsp+430h+lpMem], rax; lpMem
0x18000f108  mov     r8, rdi; int
0x18000f10b  call    WiaTrace_ProcessTrace_Ex
0x18000f110  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x18000f117  lea     rcx, [rbp+330h+var_190]
0x18000f11e  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000f123  lea     rdx, [rbp+330h+var_190]
0x18000f12a  lea     rcx, [rsp+430h+var_400]
0x18000f12f  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x18000f134  mov     rbx, rax
0x18000f137  lea     rcx, [rbp+330h+var_190]
0x18000f13e  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000f145  mov     [rbp+330h+var_190], rax
0x18000f14c  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000f151  mov     [rbp+330h+var_80], rsi
0x18000f158  test    rbx, rbx
0x18000f15b  jz      short loc_18000F1A2
0x18000f15d  xor     edx, edx; int
0x18000f15f  mov     rcx, rbx; this
0x18000f162  call    ?Enumerate@DeviceListManager@@QEAAJJ@Z; DeviceListManager::Enumerate(long)
0x18000f167  mov     rcx, rbx; this
0x18000f16a  call    ?LoadUnloadDrivers@DeviceListManager@@QEAAJJ@Z; DeviceListManager::LoadUnloadDrivers(long)
0x18000f16f  mov     rcx, [rbx+8]
0x18000f173  mov     esi, eax
0x18000f175  movsxd  rcx, dword ptr [rcx+4]
0x18000f179  add     rcx, 8
0x18000f17d  add     rcx, rbx
0x18000f180  mov     rdx, [rcx]
0x18000f183  mov     rax, [rdx+10h]
0x18000f187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f18c  jmp     short loc_18000F1E5
0x18000f18e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f193  jmp     loc_18000ED88
0x18000f198  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f19d  jmp     loc_18000EF0C
0x18000f1a2  lea     rcx, aWeCouldNotRefr; "We could not refresh the device list be"...
0x18000f1a9  call    WiaTrace_TraceLog
0x18000f1ae  mov     rdx, rax; char *
0x18000f1b1  mov     rcx, rdi; char *
0x18000f1b4  mov     rbx, rax
0x18000f1b7  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000f1bc  mov     rcx, rbx; this
0x18000f1bf  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000f1c4  lea     rcx, aWeCouldNotRefr; "We could not refresh the device list be"...
0x18000f1cb  call    WiaTrace_Trace
0x18000f1d0  mov     r9d, r13d; int
0x18000f1d3  mov     [rsp+430h+lpMem], rax; lpMem
0x18000f1d8  mov     r8, rdi; int
0x18000f1db  call    WiaTrace_ProcessTrace_Ex
0x18000f1e0  mov     esi, 8000FFFFh
0x18000f1e5  mov     rcx, r15; this
0x18000f1e8  call    ?CheckForActivityAndShutdown@WiaService@@QEAAJXZ; WiaService::CheckForActivityAndShutdown(void)
0x18000f1ed  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x18000f1f4  jz      loc_18000EF66
0x18000f1fa  lea     rdx, DocPerf_Wia_ServiceRefresh_Stop
0x18000f201  jmp     loc_18000F485
0x18000f206  test    cs:Microsoft_Windows_DocumentsEnableBits, r14b
0x18000f20d  jz      short loc_18000F22A
0x18000f20f  lea     rax, [rbp+330h+var_60]
  ... truncated ...
```
