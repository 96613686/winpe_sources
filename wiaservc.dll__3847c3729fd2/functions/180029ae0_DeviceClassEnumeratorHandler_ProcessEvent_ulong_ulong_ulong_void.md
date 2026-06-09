# DeviceClassEnumeratorHandler::ProcessEvent(ulong,ulong,ulong,void *)

- ea: `0x180029ae0`
- end: `0x18002a442`
- name: `?ProcessEvent@DeviceClassEnumeratorHandler@@UEAAJKKKPEAX@Z`
- size: `2402`
- prototype: `__int64 __fastcall(DeviceClassEnumeratorHandler *__hidden this, unsigned int, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004ff8`
- `0x18000645c`
- `0x1800085b0`
- `0x1800095e8`
- `0x18000a538`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x18000fc60`
- `0x180011a94`
- `0x1800174c4`
- `0x180029ae0`
- `0x18002a448`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18002a1bc`
- `KERNEL32!Sleep` at `0x18002a1bc`

## string_xrefs

- `0x180029bb4`: `DBT_DEVICEQUERYREMOVE`
- `0x180029bcf`: `DBT_DEVICEQUERYREMOVEFAILED`
- `0x180029bdb`: `DBT_DEVICEREMOVEPENDING`
- `0x180029be7`: `DBT_DEVICEREMOVECOMPLETE`
- `0x180029dda`: `DBT_DEVICEQUERYREMOVEFAILED, re-enumerate devices..`
- `0x180029e00`: `DBT_DEVICEQUERYREMOVEFAILED, re-enumerate devices..`
- `0x180029e30`: `DBT_DEVICEQUERYREMOVEFAILED, load/unload drivers..`
- `0x180029e56`: `DBT_DEVICEQUERYREMOVEFAILED, load/unload drivers..`
- `0x18002a3b9`: `Processing system event control code %u, event type %u, completed with with hr 0x%08X`
- `0x18002a3ee`: `Processing system event control code %u, event type %u, completed with with hr 0x%08X`

## pseudocode

```c
__int64 __fastcall DeviceClassEnumeratorHandler::ProcessEvent(
        DeviceClassEnumeratorHandler *this,
        int a2,
        int a3,
        int a4,
        void *a5)
{
  int v6; // r15d
  char *v8; // rbx
  void *v9; // rdx
  void **lpMem; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  unsigned int UnloadDrivers; // esi
  const char *v14; // r13
  __int64 v15; // rax
  __int64 v16; // r15
  const char *v17; // r9
  char *v18; // rbx
  void *v19; // rdx
  void **v20; // rax
  void *v21; // rdx
  __int64 v22; // rcx
  DeviceListManager *v23; // r15
  __int64 v24; // rcx
  __int64 v25; // rcx
  unsigned int DeviceNameFromDevHdr; // eax
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  struct USDWrapper *v33; // rax
  int v34; // edx
  DeviceListManager *v35; // rcx
  struct USDWrapper *v36; // rbx
  char *v37; // rbx
  void *v38; // rdx
  void **v39; // rax
  void *v40; // rdx
  __int64 v41; // rcx
  char *v42; // rbx
  void *v43; // rdx
  void **v44; // rax
  void *v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // r8
  char *v49; // rbx
  void *v50; // rdx
  void **v51; // rax
  void *v52; // rdx
  __int64 v53; // rcx
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
  char *v64; // rbx
  void *v65; // rdx
  void **v66; // rax
  void *v67; // rdx
  __int64 v68; // rcx
  int v69; // r13d
  char v70; // al
  unsigned int v71; // eax
  char *v72; // rbx
  void *v73; // rdx
  void **v74; // rax
  void *v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // rdx
  __int64 v78; // rax
  struct USDWrapper *v79; // rbx
  int v80; // edx
  char *v81; // rbx
  void *v82; // rdx
  void **v83; // rax
  void *v84; // rdx
  __int64 v85; // rcx
  char *v86; // rbx
  void *v87; // rdx
  char *v88; // rbx
  void *v89; // rdx
  void **v90; // rax
  void *v91; // rdx
  __int64 v92; // rcx
  char *v93; // rbx
  void *v94; // rdx
  void **v95; // rax
  void *v96; // rdx
  __int64 v97; // rcx
  char *v98; // rbx
  void *v99; // rdx
  __int64 v100; // rdx
  __int64 v101; // r8
  char *v102; // rcx
  char *v103; // rbx
  void *v104; // rdx
  void **v105; // rax
  void *v106; // rdx
  __int64 v107; // rcx
  char *v108; // rbx
  void *v109; // rdx
  void **v110; // rax
  void *v111; // rdx
  __int64 v112; // rcx
  char *v113; // rbx
  void *v114; // rdx
  void **v115; // rax
  void *v116; // rdx
  __int64 v117; // rcx
  char *v118; // rbx
  void *v119; // rdx
  void **v120; // rax
  void *v121; // rdx
  __int64 v122; // rcx
  char v124; // [rsp+30h] [rbp-D0h]
  _QWORD v126[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v127[6]; // [rsp+50h] [rbp-B0h]
  const unsigned __int64 *v128; // [rsp+80h] [rbp-80h] BYREF
  _WORD v129[128]; // [rsp+88h] [rbp-78h] BYREF
  _WORD *v130; // [rsp+188h] [rbp+88h]
  __int64 v131; // [rsp+190h] [rbp+90h]
  __int64 v132; // [rsp+198h] [rbp+98h]
  char v133; // [rsp+1A0h] [rbp+A0h]
  _QWORD v134[38]; // [rsp+1B0h] [rbp+B0h] BYREF

  v6 = a3;
  v8 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                 0,
                 0,
                 "Processing system event, control code %u, event type %u..",
                 a3,
                 a4);
  WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v8);
  WiaTrcLib::Free((WiaTrcLib *)v8, v9);
  lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "Processing system event, control code %u, event type %u..",
                     v6,
                     a4);
  WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, lpMem);
  if ( a2 != -1 )
  {
    v108 = (char *)WiaTrace_TraceLogWithSubComp(
                     1,
                     "The DeviceClassEnumeratorHandler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)");
    WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::ProcessEvent", v108);
    WiaTrcLib::Free((WiaTrcLib *)v108, v109);
    v110 = (void **)WiaTrace_TraceWithSubComp(
                      1,
                      "The DeviceClassEnumeratorHandler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)");
    WiaTrace_ProcessTrace_Ex(v112, v111, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 2, v110);
    v113 = (char *)WiaTrace_TraceLogWithSubComp(
                     1,
                     "    We currently only handle sync requests (i.e. dwTimeToWait must be ASYNCH_WAIT_TIME).");
    WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::ProcessEvent", v113);
    WiaTrcLib::Free((WiaTrcLib *)v113, v114);
    v115 = (void **)WiaTrace_TraceWithSubComp(
                      1,
                      "    We currently only handle sync requests (i.e. dwTimeToWait must be ASYNCH_WAIT_TIME).");
    WiaTrace_ProcessTrace_Ex(v117, v116, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 2, v115);
    UnloadDrivers = -2147024809;
    goto LABEL_38;
  }
  UnloadDrivers = 0;
  if ( v6 == 11 )
  {
    v127[1] = "DBT_DEVICEARRIVAL";
    v127[2] = "DBT_DEVICEQUERYREMOVE";
    v14 = "Unknown PnP Message";
    v127[0] = "Unknown PnP Message";
    v127[3] = "DBT_DEVICEQUERYREMOVEFAILED";
    v127[4] = "DBT_DEVICEREMOVEPENDING";
    v127[5] = "DBT_DEVICEREMOVECOMPLETE";
    v15 = 0;
    if ( (a4 & 0xFFFF7FF0) == 0 )
      v15 = (a4 & 0xFu) + 1;
    v126[0] = v15;
    v16 = v15;
    if ( (unsigned int)v15 >= 6 )
      v17 = "Unknown PnP Message";
    else
      v17 = (const char *)v127[v15];
    v18 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Message from PnP: %s", v17);
    WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v18);
    WiaTrcLib::Free((WiaTrcLib *)v18, v19);
    if ( LODWORD(v126[0]) < 6 )
      v14 = (const char *)v127[v16];
    v20 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Message from PnP: %s", v14);
    WiaTrace_ProcessTrace_Ex(v22, v21, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v20);
    ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v126);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v134, L"DeviceListManager");
    v23 = (DeviceListManager *)ServiceComponentHolder::Get<DeviceListManager>(v126, v134);
    v134[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage(v134);
    v134[34] = 0;
    if ( !v23 )
    {
      v103 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "The Image Device Class enumerator could not process the PnP message because the DeviceListManager is NULL!");
      WriteDbgTraceWarningWI("DeviceClassEnumeratorHandler::ProcessEvent", v103);
      WiaTrcLib::Free((WiaTrcLib *)v103, v104);
      v105 = (void **)WiaTrace_TraceWithSubComp(
                        1,
                        "The Image Device Class enumerator could not process the PnP message because the DeviceListManager is NULL!");
      WiaTrace_ProcessTrace_Ex(v107, v106, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 2, v105);
      UnloadDrivers = -2147418113;
      goto LABEL_36;
    }
    v24 = (unsigned int)(a4 - 0x8000);
    if ( a4 != 0x8000 )
    {
      v25 = (unsigned int)(a4 - 32769);
      if ( a4 != 32769 )
      {
        if ( a4 == 32770 )
        {
          v37 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DBT_DEVICEQUERYREMOVEFAILED, re-enumerate devices..");
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v37);
          WiaTrcLib::Free((WiaTrcLib *)v37, v38);
          v39 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           2,
                           0,
                           "DBT_DEVICEQUERYREMOVEFAILED, re-enumerate devices..");
          WiaTrace_ProcessTrace_Ex(v41, v40, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v39);
          DeviceListManager::Enumerate(v23, 0);
          v42 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "DBT_DEVICEQUERYREMOVEFAILED, load/unload drivers..");
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v42);
          WiaTrcLib::Free((WiaTrcLib *)v42, v43);
          v44 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "DBT_DEVICEQUERYREMOVEFAILED, load/unload drivers..");
          WiaTrace_ProcessTrace_Ex(v46, v45, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v44);
          UnloadDrivers = DeviceListManager::LoadUnloadDrivers(v23, v47, v48);
        }
        else
        {
          v25 = (unsigned int)(a4 - 32771);
          if ( (unsigned int)v25 <= 1 )
            goto LABEL_15;
        }
LABEL_34:
        v102 = (char *)v23 + *(int *)(*((_QWORD *)v23 + 1) + 4LL) + 8;
        (*(void (__fastcall **)(char *))(*(_QWORD *)v102 + 16LL))(v102);
LABEL_36:
        ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v126);
        v6 = a3;
        goto LABEL_38;
      }
LABEL_15:
      v130 = v129;
      v128 = &CSimpleStringBase<unsigned short>::`vftable';
      v129[0] = 0;
      v131 = 128;
      v132 = 16;
      v133 = 0;
      DeviceNameFromDevHdr = DeviceClassEnumeratorHandler::GetDeviceNameFromDevHdr(v25, a5, &v128);
      UnloadDrivers = DeviceNameFromDevHdr;
      if ( DeviceNameFromDevHdr )
      {
        v54 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        2,
                        0,
                        "GetDeviceNameFromDevHdr failed returning 0x%08X",
                        DeviceNameFromDevHdr);
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v54);
        WiaTrcLib::Free((WiaTrcLib *)v54, v55);
        v56 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         2,
                         0,
                         "GetDeviceNameFromDevHdr failed returning 0x%08X",
                         UnloadDrivers);
        WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v56);
        v59 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Fallback, re-enumerate devices..");
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v59);
        WiaTrcLib::Free((WiaTrcLib *)v59, v60);
        v61 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Fallback, re-enumerate devices..");
        WiaTrace_ProcessTrace_Ex(v63, v62, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v61);
        DeviceListManager::Enumerate(v23, 0);
        v64 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Load/unload drivers..");
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v64);
        WiaTrcLib::Free((WiaTrcLib *)v64, v65);
        v66 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Load/unload drivers..");
LABEL_32:
        WiaTrace_ProcessTrace_Ex(v68, v67, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v66);
        UnloadDrivers = DeviceListManager::LoadUnloadDrivers(v23, v100, v101);
      }
      else
      {
        v27 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Processing device removal for device (%ws)..", v130);
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v27);
        WiaTrcLib::Free((WiaTrcLib *)v27, v28);
        v29 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Processing device removal for device (%ws)..", v130);
        WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v29);
        v33 = (struct USDWrapper *)DeviceListManager::isInList(v23, v32, &v128);
        v36 = v33;
        if ( v33 )
        {
          DeviceListManager::ProcessDeviceRemoval(v35, v34, v33);
          (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v36 + 16LL))(v36);
        }
        else
        {
          v49 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "Device (%ws) was not found in the device list",
                          v130);
          WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v49);
          WiaTrcLib::Free((WiaTrcLib *)v49, v50);
          v51 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           2,
                           0,
                           "Device (%ws) was not found in the device list",
                           v130);
          WiaTrace_ProcessTrace_Ex(v53, v52, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v51);
          UnloadDrivers = 1;
        }
      }
LABEL_33:
      v128 = &CSimpleStringBase<unsigned short>::`vftable';
      CSimpleStringBase<unsigned short>::DeleteStorage(&v128);
      goto LABEL_34;
    }
    v128 = &CSimpleStringBase<unsigned short>::`vftable';
    v130 = v129;
    v129[0] = 0;
    v69 = 0;
    v70 = 1;
    v131 = 128;
    v124 = 1;
    v132 = 16;
    v133 = 0;
    while ( 1 )
    {
      if ( !v70 )
        goto LABEL_33;
      v71 = DeviceClassEnumeratorHandler::GetDeviceNameFromDevHdr(v24, a5, &v128);
      UnloadDrivers = v71;
      if ( v71 )
        break;
      v72 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Processing device arrival for device (%ws)..", v130);
      WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v72);
      WiaTrcLib::Free((WiaTrcLib *)v72, v73);
      v74 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Processing device arrival for device (%ws)..", v130);
      WiaTrace_ProcessTrace_Ex(v76, v75, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v74);
      v78 = DeviceListManager::isInList(v23, v77, &v128);
      v79 = (struct USDWrapper *)v78;
      if ( !v78 )
      {
        v81 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        2,
                        0,
                        "DeviceListManager::isInList, the device (%ws) is not in list",
                        v130);
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v81);
        WiaTrcLib::Free((WiaTrcLib *)v81, v82);
        v83 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         2,
                         0,
                         "DeviceListManager::isInList, the device (%ws) is not in list",
                         v130);
LABEL_28:
        WiaTrace_ProcessTrace_Ex(v85, v84, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v83);
        v88 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Retry %d", v69);
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v88);
        WiaTrcLib::Free((WiaTrcLib *)v88, v89);
        v90 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Retry %d", v69);
        WiaTrace_ProcessTrace_Ex(v92, v91, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v90);
        Sleep(0xC8u);
        v70 = v124;
        goto LABEL_29;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 112LL))(v78);
      UnloadDrivers = DeviceListManager::ProcessDeviceArrival(v23, v80, v79);
      (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v79 + 16LL))(v79);
      v70 = 0;
      v124 = 0;
LABEL_29:
      if ( ++v69 >= 5 )
      {
        if ( !v70 )
          goto LABEL_33;
        v93 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Fallback, re-enumerate devices..");
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v93);
        WiaTrcLib::Free((WiaTrcLib *)v93, v94);
        v95 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Fallback, re-enumerate devices..");
        WiaTrace_ProcessTrace_Ex(v97, v96, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v95);
        DeviceListManager::Enumerate(v23, 0);
        v98 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Load/unload drivers..");
        WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v98);
        WiaTrcLib::Free((WiaTrcLib *)v98, v99);
        v66 = (void **)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Load/unload drivers..");
        goto LABEL_32;
      }
    }
    v86 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "GetDeviceNameFromDevHdr failed returning 0x%08X", v71);
    WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v86);
    WiaTrcLib::Free((WiaTrcLib *)v86, v87);
    v83 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     2,
                     0,
                     "GetDeviceNameFromDevHdr failed returning 0x%08X",
                     UnloadDrivers);
    goto LABEL_28;
  }
LABEL_38:
  v118 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                   0,
                   0,
                   "Processing system event control code %u, event type %u, completed with with hr 0x%08X",
                   v6,
                   a4,
                   UnloadDrivers);
  WriteDbgTraceInfoWI("DeviceClassEnumeratorHandler::ProcessEvent", v118);
  WiaTrcLib::Free((WiaTrcLib *)v118, v119);
  v120 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                    0,
                    0,
                    "Processing system event control code %u, event type %u, completed with with hr 0x%08X",
                    v6,
                    a4,
                    UnloadDrivers);
  WiaTrace_ProcessTrace_Ex(v122, v121, (void *)"DeviceClassEnumeratorHandler::ProcessEvent", 4, v120);
  return UnloadDrivers;
}

```

## disassembly

```asm
0x180029ae0  mov     [rsp-8+arg_0], rbx
0x180029ae5  push    rbp
0x180029ae6  push    rsi
0x180029ae7  push    rdi
0x180029ae8  push    r12
0x180029aea  push    r13
0x180029aec  push    r14
0x180029aee  push    r15
0x180029af0  lea     rbp, [rsp-1F0h]
0x180029af8  sub     rsp, 2F0h
0x180029aff  mov     rax, cs:__security_cookie
0x180029b06  xor     rax, rsp
0x180029b09  mov     [rbp+220h+var_40], rax
0x180029b10  mov     rax, [rbp+220h+arg_20]
0x180029b17  mov     r12d, r9d
0x180029b1a  mov     dword ptr [rsp+320h+lpMem], r9d
0x180029b1f  mov     r15d, r8d
0x180029b22  mov     r9d, r8d
0x180029b25  mov     [rsp+320h+var_2EC], r8d
0x180029b2a  mov     edi, edx
0x180029b2c  mov     [rsp+320h+var_2E8], rax
0x180029b31  lea     r8, aProcessingSyst_0; "Processing system event, control code %"...
0x180029b38  xor     edx, edx
0x180029b3a  xor     ecx, ecx
0x180029b3c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029b41  lea     r13, aDeviceclassenu_2; "DeviceClassEnumeratorHandler::ProcessEv"...
0x180029b48  mov     rdx, rax; char *
0x180029b4b  mov     rcx, r13; char *
0x180029b4e  mov     rbx, rax
0x180029b51  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029b56  mov     rcx, rbx; this
0x180029b59  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029b5e  mov     r9d, r15d
0x180029b61  mov     dword ptr [rsp+320h+lpMem], r12d
0x180029b66  lea     r8, aProcessingSyst_0; "Processing system event, control code %"...
0x180029b6d  xor     edx, edx
0x180029b6f  xor     ecx, ecx
0x180029b71  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029b76  mov     r9d, 4; int
0x180029b7c  mov     [rsp+320h+lpMem], rax; lpMem
0x180029b81  mov     r8, r13; int
0x180029b84  call    WiaTrace_ProcessTrace_Ex
0x180029b89  cmp     edi, 0FFFFFFFFh
0x180029b8c  jnz     loc_18002A31E
0x180029b92  xor     esi, esi
0x180029b94  cmp     r15d, 0Bh
0x180029b98  jnz     loc_18002A3B5
0x180029b9e  lea     rax, aDbtDevicearriv; "DBT_DEVICEARRIVAL"
0x180029ba5  mov     ecx, r12d
0x180029ba8  mov     [rsp+320h+var_2C8], rax
0x180029bad  lea     r14d, [r15-0Ah]
0x180029bb1  and     ecx, 0Fh
0x180029bb4  lea     rax, aDbtDevicequery; "DBT_DEVICEQUERYREMOVE"
0x180029bbb  mov     [rsp+320h+var_2C0], rax
0x180029bc0  lea     r13, aUnknownPnpMess; "Unknown PnP Message"
0x180029bc7  add     ecx, r14d
0x180029bca  mov     [rsp+320h+var_2D0], r13
0x180029bcf  lea     rax, aDbtDevicequery_0; "DBT_DEVICEQUERYREMOVEFAILED"
0x180029bd6  mov     [rsp+320h+var_2B8], rax
0x180029bdb  lea     rax, aDbtDeviceremov_0; "DBT_DEVICEREMOVEPENDING"
0x180029be2  mov     [rsp+320h+var_2B0], rax
0x180029be7  lea     rax, aDbtDeviceremov; "DBT_DEVICEREMOVECOMPLETE"
0x180029bee  mov     [rsp+320h+var_2A8], rax
0x180029bf3  xor     eax, eax
0x180029bf5  test    r12d, 0FFFF7FF0h
0x180029bfc  cmovz   eax, ecx
0x180029bff  mov     [rsp+320h+var_2E0], rax
0x180029c04  lea     r15, ds:0[rax*8]
0x180029c0c  cmp     eax, 6
0x180029c0f  jnb     short loc_180029C18
0x180029c11  mov     r9, [rsp+r15+320h+var_2D0]
0x180029c16  jmp     short loc_180029C1B
0x180029c18  mov     r9, r13
0x180029c1b  xor     edx, edx
0x180029c1d  lea     r8, aMessageFromPnp; "Message from PnP: %s"
0x180029c24  lea     edi, [rdx+2]
0x180029c27  mov     ecx, edi
0x180029c29  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029c2e  mov     rdx, rax; char *
0x180029c31  lea     rcx, aDeviceclassenu_2; "DeviceClassEnumeratorHandler::ProcessEv"...
0x180029c38  mov     rbx, rax
0x180029c3b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029c40  mov     rcx, rbx; this
0x180029c43  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029c48  cmp     dword ptr [rsp+320h+var_2E0], 6
0x180029c4d  jnb     short loc_180029C54
0x180029c4f  mov     r13, [rsp+r15+320h+var_2D0]
0x180029c54  mov     r9, r13
0x180029c57  lea     r8, aMessageFromPnp; "Message from PnP: %s"
0x180029c5e  xor     edx, edx
0x180029c60  mov     ecx, edi
0x180029c62  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029c67  lea     r13, aDeviceclassenu_2; "DeviceClassEnumeratorHandler::ProcessEv"...
0x180029c6e  mov     [rsp+320h+lpMem], rax; lpMem
0x180029c73  mov     r8, r13; int
0x180029c76  mov     r9d, 4; int
0x180029c7c  call    WiaTrace_ProcessTrace_Ex
0x180029c81  lea     rcx, [rsp+320h+var_2E0]; this
0x180029c86  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x180029c8b  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x180029c92  lea     rcx, [rbp+220h+var_170]
0x180029c99  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180029c9e  lea     rdx, [rbp+220h+var_170]
0x180029ca5  lea     rcx, [rsp+320h+var_2E0]
0x180029caa  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x180029caf  lea     rbx, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180029cb6  mov     r15, rax
0x180029cb9  lea     rcx, [rbp+220h+var_170]
0x180029cc0  mov     [rbp+220h+var_170], rbx
0x180029cc7  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x180029ccc  mov     [rbp+220h+var_60], rsi
0x180029cd3  test    r15, r15
0x180029cd6  jz      loc_18002A2C1
0x180029cdc  mov     ecx, r12d
0x180029cdf  sub     ecx, 8000h
0x180029ce5  jz      loc_180029FC0
0x180029ceb  sub     ecx, r14d
0x180029cee  jz      short loc_180029D07
0x180029cf0  sub     ecx, r14d
0x180029cf3  jz      loc_180029DDA
0x180029cf9  sub     ecx, r14d
0x180029cfc  jz      short loc_180029D07
0x180029cfe  cmp     ecx, r14d
0x180029d01  jnz     loc_18002A2A4
0x180029d07  mov     rdx, [rsp+320h+var_2E8]
0x180029d0c  lea     rax, [rbp+220h+var_298]
0x180029d10  mov     [rbp+220h+var_198], rax
0x180029d17  lea     r8, [rbp+220h+var_2A0]
0x180029d1b  xor     eax, eax
0x180029d1d  mov     [rbp+220h+var_2A0], rbx
0x180029d21  mov     [rbp+220h+var_298], ax
0x180029d25  mov     [rbp+220h+var_190], 80h
0x180029d30  mov     [rbp+220h+var_188], 10h
0x180029d3b  mov     [rbp+220h+var_180], sil
0x180029d42  call    ?GetDeviceNameFromDevHdr@DeviceClassEnumeratorHandler@@AEAAJPEAU_DEV_BROADCAST_HDR@@AEAV?$CSimpleStringBase@G@@@Z; DeviceClassEnumeratorHandler::GetDeviceNameFromDevHdr(_DEV_BROADCAST_HDR *,CSimpleStringBase<ushort> &)
0x180029d47  xor     edx, edx
0x180029d49  mov     esi, eax
0x180029d4b  mov     ecx, edi
0x180029d4d  test    eax, eax
0x180029d4f  jnz     loc_180029EE4
0x180029d55  mov     r9, [rbp+220h+var_198]
0x180029d5c  lea     r8, aProcessingDevi_0; "Processing device removal for device (%"...
0x180029d63  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029d68  mov     rdx, rax; char *
0x180029d6b  mov     rcx, r13; char *
0x180029d6e  mov     rbx, rax
0x180029d71  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029d76  mov     rcx, rbx; this
0x180029d79  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029d7e  mov     r9, [rbp+220h+var_198]
0x180029d85  lea     r8, aProcessingDevi_0; "Processing device removal for device (%"...
0x180029d8c  xor     edx, edx
0x180029d8e  mov     ecx, edi
0x180029d90  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029d95  lea     r9d, [rsi+4]; int
0x180029d99  mov     [rsp+320h+lpMem], rax; lpMem
0x180029d9e  mov     r8, r13; int
0x180029da1  call    WiaTrace_ProcessTrace_Ex
0x180029da6  lea     r8, [rbp+220h+var_2A0]
0x180029daa  mov     rcx, r15
0x180029dad  call    ?isInList@DeviceListManager@@QEAAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; DeviceListManager::isInList(long,CSimpleStringBase<ushort> const &)
0x180029db2  mov     rbx, rax
0x180029db5  test    rax, rax
0x180029db8  jz      loc_180029E85
0x180029dbe  mov     r8, rax; struct USDWrapper *
0x180029dc1  call    ?ProcessDeviceRemoval@DeviceListManager@@QEAAJJPEAVUSDWrapper@@@Z; DeviceListManager::ProcessDeviceRemoval(long,USDWrapper *)
0x180029dc6  mov     rcx, [rbx]
0x180029dc9  mov     rax, [rcx+10h]
0x180029dcd  mov     rcx, rbx
0x180029dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029dd5  jmp     loc_18002A290
0x180029dda  lea     r8, aDbtDevicequery_2; "DBT_DEVICEQUERYREMOVEFAILED, re-enumera"...
0x180029de1  xor     edx, edx
0x180029de3  mov     ecx, edi
0x180029de5  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029dea  mov     rdx, rax; char *
0x180029ded  mov     rcx, r13; char *
0x180029df0  mov     rbx, rax
0x180029df3  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029df8  mov     rcx, rbx; this
0x180029dfb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029e00  lea     r8, aDbtDevicequery_2; "DBT_DEVICEQUERYREMOVEFAILED, re-enumera"...
0x180029e07  xor     edx, edx
0x180029e09  mov     ecx, edi
0x180029e0b  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029e10  mov     r14d, 4
0x180029e16  mov     [rsp+320h+lpMem], rax; lpMem
0x180029e1b  mov     r9d, r14d; int
0x180029e1e  mov     r8, r13; int
0x180029e21  call    WiaTrace_ProcessTrace_Ex
0x180029e26  xor     edx, edx; int
0x180029e28  mov     rcx, r15; this
0x180029e2b  call    ?Enumerate@DeviceListManager@@QEAAJJ@Z; DeviceListManager::Enumerate(long)
0x180029e30  lea     r8, aDbtDevicequery_1; "DBT_DEVICEQUERYREMOVEFAILED, load/unloa"...
0x180029e37  xor     edx, edx
0x180029e39  mov     ecx, edi
0x180029e3b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029e40  mov     rdx, rax; char *
0x180029e43  mov     rcx, r13; char *
0x180029e46  mov     rbx, rax
0x180029e49  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029e4e  mov     rcx, rbx; this
0x180029e51  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029e56  lea     r8, aDbtDevicequery_1; "DBT_DEVICEQUERYREMOVEFAILED, load/unloa"...
0x180029e5d  xor     edx, edx
0x180029e5f  mov     ecx, edi
0x180029e61  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029e66  mov     r9d, r14d; int
0x180029e69  mov     [rsp+320h+lpMem], rax; lpMem
0x180029e6e  mov     r8, r13; int
0x180029e71  call    WiaTrace_ProcessTrace_Ex
0x180029e76  mov     rcx, r15; this
0x180029e79  call    ?LoadUnloadDrivers@DeviceListManager@@QEAAJJ@Z; DeviceListManager::LoadUnloadDrivers(long)
0x180029e7e  mov     esi, eax
0x180029e80  jmp     loc_18002A2A4
0x180029e85  mov     r9, [rbp+220h+var_198]
0x180029e8c  lea     r8, aDeviceWsWasNot; "Device (%ws) was not found in the devic"...
0x180029e93  xor     edx, edx
0x180029e95  mov     ecx, edi
0x180029e97  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029e9c  mov     rdx, rax; char *
0x180029e9f  mov     rcx, r13; char *
0x180029ea2  mov     rbx, rax
0x180029ea5  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029eaa  mov     rcx, rbx; this
0x180029ead  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029eb2  mov     r9, [rbp+220h+var_198]
0x180029eb9  lea     r8, aDeviceWsWasNot; "Device (%ws) was not found in the devic"...
0x180029ec0  xor     edx, edx
0x180029ec2  mov     ecx, edi
0x180029ec4  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029ec9  mov     r9d, 4; int
0x180029ecf  mov     [rsp+320h+lpMem], rax; lpMem
0x180029ed4  mov     r8, r13; int
0x180029ed7  call    WiaTrace_ProcessTrace_Ex
0x180029edc  mov     esi, r14d
0x180029edf  jmp     loc_18002A290
0x180029ee4  mov     r9d, esi
0x180029ee7  lea     r8, aGetdevicenamef; "GetDeviceNameFromDevHdr failed returnin"...
0x180029eee  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029ef3  mov     rdx, rax; char *
0x180029ef6  mov     rcx, r13; char *
0x180029ef9  mov     rbx, rax
0x180029efc  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029f01  mov     rcx, rbx; this
0x180029f04  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029f09  mov     r9d, esi
0x180029f0c  lea     r8, aGetdevicenamef; "GetDeviceNameFromDevHdr failed returnin"...
0x180029f13  xor     edx, edx
0x180029f15  mov     ecx, edi
0x180029f17  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029f1c  mov     r14d, 4
0x180029f22  mov     [rsp+320h+lpMem], rax; lpMem
0x180029f27  mov     r9d, r14d; int
0x180029f2a  mov     r8, r13; int
0x180029f2d  call    WiaTrace_ProcessTrace_Ex
0x180029f32  lea     r8, aFallbackReEnum; "Fallback, re-enumerate devices.."
0x180029f39  xor     edx, edx
0x180029f3b  mov     ecx, edi
0x180029f3d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029f42  mov     rdx, rax; char *
0x180029f45  mov     rcx, r13; char *
0x180029f48  mov     rbx, rax
0x180029f4b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029f50  mov     rcx, rbx; this
0x180029f53  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029f58  lea     r8, aFallbackReEnum; "Fallback, re-enumerate devices.."
0x180029f5f  xor     edx, edx
0x180029f61  mov     ecx, edi
0x180029f63  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029f68  mov     r9d, r14d; int
0x180029f6b  mov     [rsp+320h+lpMem], rax; lpMem
0x180029f70  mov     r8, r13; int
0x180029f73  call    WiaTrace_ProcessTrace_Ex
0x180029f78  xor     edx, edx; int
0x180029f7a  mov     rcx, r15; this
0x180029f7d  call    ?Enumerate@DeviceListManager@@QEAAJJ@Z; DeviceListManager::Enumerate(long)
0x180029f82  lea     r8, aLoadUnloadDriv; "Load/unload drivers.."
0x180029f89  xor     edx, edx
0x180029f8b  mov     ecx, edi
0x180029f8d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180029f92  mov     rdx, rax; char *
0x180029f95  mov     rcx, r13; char *
0x180029f98  mov     rbx, rax
0x180029f9b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180029fa0  mov     rcx, rbx; this
0x180029fa3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180029fa8  lea     r8, aLoadUnloadDriv; "Load/unload drivers.."
0x180029faf  xor     edx, edx
0x180029fb1  mov     ecx, edi
0x180029fb3  call    WiaTrace_TraceWithSubCompTraceLevel
0x180029fb8  mov     r9d, r14d
0x180029fbb  jmp     loc_18002A270
0x180029fc0  lea     rax, [rbp+220h+var_298]
0x180029fc4  mov     [rbp+220h+var_2A0], rbx
0x180029fc8  mov     [rbp+220h+var_198], rax
0x180029fcf  xor     eax, eax
0x180029fd1  mov     [rbp+220h+var_298], ax
0x180029fd5  xor     r13d, r13d
0x180029fd8  mov     al, r14b
  ... truncated ...
```
