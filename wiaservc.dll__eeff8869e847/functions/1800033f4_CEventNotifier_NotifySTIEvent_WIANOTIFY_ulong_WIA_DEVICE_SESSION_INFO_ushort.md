# CEventNotifier::NotifySTIEvent(_WIANOTIFY *,ulong,_WIA_DEVICE_SESSION_INFO &,ushort *)

- ea: `0x1800033f4`
- end: `0x180004266`
- name: `?NotifySTIEvent@CEventNotifier@@QEAAJPEAU_WIANOTIFY@@KAEAU_WIA_DEVICE_SESSION_INFO@@PEAG@Z`
- size: `3698`
- prototype: `__int64 __fastcall(CEventNotifier *this, struct _WIANOTIFY *, int, struct _WIA_DEVICE_SESSION_INFO *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `34`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005a48`
- `0x18003ce70`
- `0x18004c370`

## callees

- `0x180002db4`
- `0x1800033f4`
- `0x180004380`
- `0x1800044d8`
- `0x1800045e0`
- `0x18000469c`
- `0x1800049e0`
- `0x18000a974`
- `0x18000a9e0`
- `0x18000ac34`
- `0x18000b6a0`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x18000f808`
- `0x18000fbec`
- `0x180026380`
- `0x180028984`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033884`
- `0x180033cc0`
- `0x180034658`
- `0x180039664`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x180003e86`
- `KERNEL32!EnterCriticalSection` at `0x180003e86`
- `KERNEL32!LeaveCriticalSection` at `0x180003ff3`
- `KERNEL32!LeaveCriticalSection` at `0x180004018`
- `KERNEL32!LeaveCriticalSection` at `0x180003ff3`
- `KERNEL32!LeaveCriticalSection` at `0x180004018`
- `OLEAUT32!__imp_SysAllocString` at `0x1800039a0`
- `OLEAUT32!__imp_SysAllocString` at `0x180003c51`
- `OLEAUT32!__imp_SysAllocString` at `0x180003cf5`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d17`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d39`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ec9`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ede`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ef4`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f18`
- `OLEAUT32!__imp_SysAllocString` at `0x1800039a0`
- `OLEAUT32!__imp_SysAllocString` at `0x180003c51`
- `OLEAUT32!__imp_SysAllocString` at `0x180003cf5`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d17`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d39`
- `OLEAUT32!__imp_SysAllocString` at `0x180003d5b`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ec9`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ede`
- `OLEAUT32!__imp_SysAllocString` at `0x180003ef4`
- `OLEAUT32!__imp_SysAllocString` at `0x180003f18`
- `OLEAUT32!__imp_SysFreeString` at `0x180003864`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ce0`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d08`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180004165`
- `OLEAUT32!__imp_SysFreeString` at `0x180004178`
- `OLEAUT32!__imp_SysFreeString` at `0x18000418b`
- `OLEAUT32!__imp_SysFreeString` at `0x180003864`
- `OLEAUT32!__imp_SysFreeString` at `0x180003ce0`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d08`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d2a`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d4c`
- `OLEAUT32!__imp_SysFreeString` at `0x180004165`
- `OLEAUT32!__imp_SysFreeString` at `0x180004178`
- `OLEAUT32!__imp_SysFreeString` at `0x18000418b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003f43`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180003f43`

## string_xrefs

- `0x180003dd8`: `WIA_ACTION_EVENT, starting the WiaRpc service...`
- `0x180003e02`: `WIA_ACTION_EVENT, starting the WiaRpc service...`
- `0x180003e2e`: `Attempt to complete WiaRpc async RPC call...`
- `0x180003e58`: `Attempt to complete WiaRpc async RPC call...`
- `0x180003f53`: `RpcAsyncComplete failed with error 0x%x`
- `0x180003f7d`: `RpcAsyncComplete failed with error 0x%x`

## pseudocode

```c
__int64 __fastcall CEventNotifier::NotifySTIEvent(
        CEventNotifier *this,
        struct _WIANOTIFY *a2,
        int a3,
        struct _WIA_DEVICE_SESSION_INFO *a4,
        unsigned __int16 *a5)
{
  struct tagWiaTraceData_Type *v6; // rax
  char *v7; // rdx
  unsigned int v8; // r8d
  char *v9; // rsi
  int DeviceInfo; // r14d
  char *v11; // rbx
  void *v12; // rdx
  void *v13; // rax
  int v14; // edx
  int v15; // ecx
  __int64 v16; // r8
  OLECHAR *v17; // rdx
  struct USDWrapper *v18; // r12
  unsigned __int64 v19; // rdx
  StiLockMgr *v20; // rbx
  char *v21; // rbx
  void *v22; // rdx
  void *v23; // rax
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  char *v27; // rbx
  void *v28; // rdx
  void *v29; // rax
  int v30; // edx
  int v31; // ecx
  _QWORD *v32; // rbx
  int v33; // r8d
  __int64 v34; // rax
  __int64 v35; // rdx
  CEventNotifier *v36; // rcx
  __int64 v37; // rax
  StiLockMgr *v38; // rcx
  int v39; // r9d
  __int64 v40; // rax
  int i; // ebx
  _QWORD *v42; // rcx
  __int64 v43; // rax
  OLECHAR *v44; // rax
  char *v45; // rbx
  void *v46; // rdx
  void *v47; // rax
  int v48; // edx
  int v49; // ecx
  char *v50; // rbx
  void *v51; // rdx
  void *v52; // rax
  int v53; // edx
  int v54; // ecx
  char *v55; // rbx
  void *v56; // rdx
  void *v57; // rax
  int v58; // edx
  int v59; // ecx
  __int64 v60; // rdx
  char *v61; // rbx
  void *v62; // rdx
  void *v63; // rax
  int v64; // edx
  int v65; // ecx
  __int64 v66; // rbx
  __int64 v67; // rdx
  void *v68; // rdx
  void *v69; // rax
  int v70; // edx
  int v71; // ecx
  __int64 v72; // rax
  const OLECHAR *v73; // rcx
  const OLECHAR *v74; // rax
  OLECHAR *v75; // rcx
  OLECHAR *v76; // rcx
  OLECHAR *v77; // rcx
  OLECHAR *v78; // rcx
  void *v79; // rdx
  void *v80; // rax
  int v81; // edx
  int v82; // ecx
  char *v83; // rbx
  void *v84; // rdx
  void *v85; // rax
  int v86; // edx
  int v87; // ecx
  char *v88; // rbx
  void *v89; // rdx
  void *v90; // rax
  int v91; // edx
  int v92; // ecx
  char *v93; // rbx
  void *v94; // rdx
  void *v95; // rax
  int v96; // edx
  int v97; // ecx
  char *v98; // rbx
  void *v99; // rdx
  void *v100; // rax
  int v101; // edx
  int v102; // ecx
  unsigned __int64 v103; // rdx
  WiaEventNotifier *v104; // rbx
  char *v105; // rcx
  char *v106; // rbx
  void *v107; // rdx
  void *v108; // rax
  int v109; // edx
  int v110; // ecx
  char *v111; // rax
  char *v112; // rcx
  __int64 v113; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-418h]
  struct USDWrapper *Reply; // [rsp+48h] [rbp-3F0h] BYREF
  int v118; // [rsp+50h] [rbp-3E8h]
  unsigned int v119; // [rsp+54h] [rbp-3E4h] BYREF
  int v120; // [rsp+58h] [rbp-3E0h] BYREF
  OLECHAR *psz; // [rsp+60h] [rbp-3D8h]
  BSTR v122; // [rsp+68h] [rbp-3D0h]
  int v123; // [rsp+70h] [rbp-3C8h]
  BSTR bstrString; // [rsp+78h] [rbp-3C0h] BYREF
  __int64 v125; // [rsp+80h] [rbp-3B8h] BYREF
  StiLockMgr *v126; // [rsp+88h] [rbp-3B0h]
  int v127; // [rsp+90h] [rbp-3A8h] BYREF
  __int64 v128; // [rsp+98h] [rbp-3A0h] BYREF
  _QWORD v129[3]; // [rsp+A0h] [rbp-398h] BYREF
  unsigned __int16 **v130; // [rsp+B8h] [rbp-380h]
  struct _WIA_DEVICE_SESSION_INFO *v131; // [rsp+D0h] [rbp-368h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+D8h] [rbp-360h] BYREF
  int v133; // [rsp+E0h] [rbp-358h]
  char v134[8]; // [rsp+E8h] [rbp-350h] BYREF
  __int64 v135; // [rsp+F0h] [rbp-348h]
  char v136[48]; // [rsp+100h] [rbp-338h] BYREF
  OLECHAR *v137; // [rsp+130h] [rbp-308h]
  _BYTE v138[80]; // [rsp+150h] [rbp-2E8h] BYREF
  const unsigned __int64 *v139; // [rsp+1A0h] [rbp-298h] BYREF
  char v140; // [rsp+1A8h] [rbp-290h] BYREF
  void *v141; // [rsp+2A8h] [rbp-190h]
  __int64 v142; // [rsp+2B0h] [rbp-188h]
  const unsigned __int64 *v143; // [rsp+2D0h] [rbp-168h] BYREF
  char v144; // [rsp+2D8h] [rbp-160h] BYREF
  void *v145; // [rsp+3D8h] [rbp-60h]
  __int64 v146; // [rsp+3E0h] [rbp-58h]

  v131 = a4;
  v129[0] = a2;
  v122 = a5;
  v6 = WiaTrace_Trace(&Class);
  CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v138, v7, v8, "CEventNotifier::NotifySTIEvent", lpMem, v6);
  v119 = 0;
  bstrString = 0;
  v125 = 0;
  v128 = 0;
  psz = 0;
  v120 = 0;
  v127 = 0;
  Reply = 0;
  v9 = 0;
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v134);
  memset_0(v136, 0, 0x48u);
  v130 = (unsigned __int16 **)((char *)a2 + 8);
  DeviceInfo = WiaGetDeviceInfo(*((const unsigned __int16 **)a2 + 1), &v119, &bstrString, &Reply);
  if ( DeviceInfo )
  {
    v126 = 0;
    v11 = (char *)WiaTrace_TraceLog("Failed to get WiaGetDeviceInfo from NotifySTIEvent, 0x%X");
    WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v11);
    WiaTrcLib::Free((WiaTrcLib *)v11, v12);
    v13 = (void *)WiaTrace_Trace("Failed to get WiaGetDeviceInfo from NotifySTIEvent, 0x%X", DeviceInfo);
    WiaTrace_ProcessTrace_Ex(v15, v14, (int)"CEventNotifier::NotifySTIEvent", 1, v13);
LABEL_3:
    v17 = v137;
    v122 = v137;
    v18 = Reply;
LABEL_102:
    v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
    v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
    goto LABEL_103;
  }
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v139, L"StiLockMgr");
  v20 = (StiLockMgr *)ServiceComponentHolder::Get<StiLockMgr>(v134, &v139);
  v126 = v20;
  v129[2] = v20;
  v139 = &CSimpleStringBase<unsigned short>::`vftable';
  if ( v141 && v141 != &v140 )
    operator delete(v141, v19);
  v141 = 0;
  v142 = 0;
  if ( !v20 )
  {
    v21 = (char *)WiaTrace_TraceLog("The Lock Manager is NULL - we cannot notify handlers of event for (%ws)");
    WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v21);
    WiaTrcLib::Free((WiaTrcLib *)v21, v22);
    v23 = (void *)WiaTrace_Trace(
                    "The Lock Manager is NULL - we cannot notify handlers of event for (%ws)",
                    *((_QWORD *)a2 + 1));
    WiaTrace_ProcessTrace_Ex(v25, v24, (int)"CEventNotifier::NotifySTIEvent", 1, v23);
    DeviceInfo = -2147418113;
    goto LABEL_3;
  }
  CWiaCritSect::CWiaCritSect((CWiaCritSect *)&lpCriticalSection, &stru_1800AF348);
  v18 = Reply;
  v26 = (**(__int64 (__fastcall ***)(struct USDWrapper *, GUID *, __int64 *))Reply)(Reply, &IID_IWiaMiniDrv, &v125);
  DeviceInfo = v26;
  if ( v26 < 0 )
  {
    v27 = (char *)WiaTrace_TraceLogWithSubComp(0, "Failed to QI for IWiaMini from NotifySTIEvent (0x%X)", v26);
    WriteDbgTraceWarningWI("CEventNotifier::NotifySTIEvent", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void *)WiaTrace_TraceWithSubComp(0, "Failed to QI for IWiaMini from NotifySTIEvent (0x%X)", DeviceInfo);
    WiaTrace_ProcessTrace_Ex(v31, v30, (int)"CEventNotifier::NotifySTIEvent", 2, v29);
  }
  v118 = 0;
  if ( DeviceInfo < 0 )
  {
    v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
    v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
    goto LABEL_30;
  }
  v32 = (_QWORD *)((char *)a2 + 20);
  DeviceInfo = (*(__int64 (__fastcall **)(struct USDWrapper *, char *, unsigned __int16 *, _QWORD))(*(_QWORD *)v18
                                                                                                  + 464LL))(
                 v18,
                 (char *)a2 + 20,
                 *v130,
                 0);
  v123 = DeviceInfo;
  if ( DeviceInfo < 0 )
    goto LABEL_25;
  v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
  v35 = *v32 - *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
  v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
  if ( *v32 == *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1 )
    v35 = *(_QWORD *)((char *)a2 + 28) - *(_QWORD *)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
  if ( !v35 )
    goto LABEL_26;
  v37 = (*(__int64 (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v18 + 152LL))(v18);
  if ( !v37 )
    goto LABEL_23;
  if ( (*(_BYTE *)(v37 + 24) & 8) != 0 )
  {
    v40 = *v32 - *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1;
    if ( *v32 == *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1 )
      v40 = *(_QWORD *)((char *)a2 + 28) - *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4;
    if ( !v40 )
      goto LABEL_23;
  }
  DeviceInfo = StiLockMgr::RequestLock(v38, v18, 0x4E20u, v39, 0);
  v123 = DeviceInfo;
  if ( DeviceInfo >= 0 )
  {
    v118 = 1;
LABEL_23:
    DeviceInfo = (*(__int64 (__fastcall **)(struct USDWrapper *, _QWORD, __int64, int *, __int64 *, int *))(*(_QWORD *)v18 + 448LL))(
                   v18,
                   0,
                   2,
                   &v120,
                   &v128,
                   &v127);
    v123 = DeviceInfo;
  }
LABEL_25:
  v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
  v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
LABEL_26:
  if ( v118 )
  {
    StiLockMgr::RequestUnlock(v126, v18, v33);
    v118 = 0;
    v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
    v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
  }
LABEL_30:
  if ( DeviceInfo >= 0 )
  {
    if ( v128 )
    {
      v129[1] = v18;
      LODWORD(v129[0]) = CRIT_SECT::Lock((struct USDWrapper *)((char *)v18 + 4136));
      if ( (*(unsigned int (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v18 + 168LL))(v18) )
      {
        for ( i = 0; ; ++i )
        {
          LODWORD(Reply) = i;
          if ( i >= v120 )
            break;
          v42 = *(_QWORD **)(v128 + 40LL * i);
          if ( v42 )
          {
            v43 = *v42 - *(_QWORD *)((char *)a2 + 20);
            if ( *v42 == *(_QWORD *)((char *)a2 + 20) )
              v43 = v42[1] - *(_QWORD *)((char *)a2 + 28);
            if ( !v43 )
            {
              if ( !a3 )
                a3 = *(_DWORD *)(v128 + 40LL * i + 8);
              v44 = SysAllocString(*(const OLECHAR **)(v128 + 40LL * i + 24));
              psz = v44;
              goto LABEL_46;
            }
          }
          else
          {
            v45 = (char *)WiaTrace_TraceLogWithSubComp(0, "Driver's event guid is NULL, index = %d", i);
            WriteDbgTraceWarningWI("CEventNotifier::NotifySTIEvent", v45);
            WiaTrcLib::Free((WiaTrcLib *)v45, v46);
            i = (int)Reply;
            v47 = (void *)WiaTrace_TraceWithSubComp(0, "Driver's event guid is NULL, index = %d", (_DWORD)Reply);
            WiaTrace_ProcessTrace_Ex(v49, v48, (int)"CEventNotifier::NotifySTIEvent", 2, v47);
          }
        }
      }
      else
      {
        LODWORD(Reply) = 0;
        v50 = (char *)WiaTrace_TraceLog("Driver is unloaded, can't query for event type");
        WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v50);
        WiaTrcLib::Free((WiaTrcLib *)v50, v51);
        v52 = (void *)WiaTrace_Trace("Driver is unloaded, can't query for event type");
        WiaTrace_ProcessTrace_Ex(v54, v53, (int)"CEventNotifier::NotifySTIEvent", 1, v52);
        DeviceInfo = -2147467259;
        i = 0;
      }
      v44 = 0;
LABEL_46:
      if ( i == v120 || !v44 )
      {
        v55 = (char *)WiaTrace_TraceLog("Event description is NULL or Event GUID not found");
        WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v55);
        WiaTrcLib::Free((WiaTrcLib *)v55, v56);
        v57 = (void *)WiaTrace_Trace("Event description is NULL or Event GUID not found");
        WiaTrace_ProcessTrace_Ex(v59, v58, (int)"CEventNotifier::NotifySTIEvent", 1, v57);
        DeviceInfo = -2147467259;
      }
      USDWrapper::DriverLoaderLock::~DriverLoaderLock((USDWrapper::DriverLoaderLock *)v129);
      v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
      v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
    }
    else
    {
      v60 = *(_QWORD *)((char *)a2 + 20) - v34;
      if ( !v60 )
        v60 = *(_QWORD *)((char *)a2 + 28) - (_QWORD)v36;
      if ( v60 )
      {
        v61 = (char *)WiaTrace_TraceLog("Got NULL cap list from drivers");
        WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v61);
        WiaTrcLib::Free((WiaTrcLib *)v61, v62);
        v63 = (void *)WiaTrace_Trace("Got NULL cap list from drivers");
        WiaTrace_ProcessTrace_Ex(v65, v64, (int)"CEventNotifier::NotifySTIEvent", 1, v63);
        v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
        v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
      }
      DeviceInfo = -2147467259;
    }
  }
  v17 = (OLECHAR *)(*(_QWORD *)((char *)a2 + 20) - *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1);
  v16 = *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4;
  if ( !v17 )
    v17 = (OLECHAR *)(*(_QWORD *)((char *)a2 + 28) - *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4);
  if ( !v17 )
    goto LABEL_61;
  v17 = (OLECHAR *)(*(_QWORD *)((char *)a2 + 20) - v34);
  if ( !v17 )
    v17 = (OLECHAR *)(*(_QWORD *)((char *)a2 + 28) - (_QWORD)v36);
  if ( v17 )
  {
    LODWORD(v66) = a3;
  }
  else
  {
LABEL_61:
    LODWORD(v66) = a3 | 1;
    a3 |= 1u;
  }
  if ( DeviceInfo < 0 )
  {
    v67 = *(_QWORD *)((char *)a2 + 20) - *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1;
    if ( !v67 )
      v67 = *(_QWORD *)((char *)a2 + 28) - *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4;
    if ( !v67 )
      goto LABEL_70;
    v17 = (OLECHAR *)(*(_QWORD *)((char *)a2 + 20) - v34);
    if ( !v17 )
      v17 = (OLECHAR *)(*(_QWORD *)((char *)a2 + 28) - (_QWORD)v36);
    if ( !v17 )
    {
LABEL_70:
      v66 = WiaTrace_TraceLogWithSubCompTraceLevel(
              0,
              0,
              "hr indicates FAILURE (expected for Disconnect), but event is Connect/Disconnect");
      WriteDbgTraceInfoWI("CEventNotifier::NotifySTIEvent", (char *)v66);
      WiaTrcLib::Free((WiaTrcLib *)v66, v68);
      v69 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                      0,
                      0,
                      "hr indicates FAILURE (expected for Disconnect), but event is Connect/Disconnect");
      WiaTrace_ProcessTrace_Ex(v71, v70, (int)"CEventNotifier::NotifySTIEvent", 4, v69);
      LODWORD(v66) = a3;
      if ( !a3 )
        LODWORD(v66) = 1;
      a3 = v66;
      v72 = *(_QWORD *)((char *)a2 + 20) - *(_QWORD *)&WIA_EVENT_DEVICE_CONNECTED.Data1;
      if ( !v72 )
        v72 = *(_QWORD *)((char *)a2 + 28) - *(_QWORD *)WIA_EVENT_DEVICE_CONNECTED.Data4;
      v73 = L"Device Connected";
      if ( v72 )
        v73 = L"Device Disconnected";
      psz = SysAllocString(v73);
      v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
      v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
    }
  }
  if ( (v66 & 1) != 0 )
  {
    v9 = (char *)operator new(0x48u);
    if ( v9 )
    {
      *(_QWORD *)v9 = &WiaEventInfo::`vftable';
      *((_DWORD *)v9 + 2) = 1;
      *(GUID *)(v9 + 12) = GUID_NULL;
      *((_QWORD *)v9 + 4) = 0;
      *((_QWORD *)v9 + 5) = 0;
      *((_QWORD *)v9 + 6) = 0;
      *((_QWORD *)v9 + 7) = 0;
      *((_QWORD *)v9 + 8) = 0;
    }
    else
    {
      v9 = 0;
    }
    if ( v9 )
    {
      *(_OWORD *)(v9 + 12) = *(_OWORD *)((char *)a2 + 20);
      v74 = (const OLECHAR *)*((_QWORD *)a2 + 1);
      v129[0] = v74;
      v75 = (OLECHAR *)*((_QWORD *)v9 + 5);
      if ( v75 )
      {
        SysFreeString(v75);
        *((_QWORD *)v9 + 5) = 0;
        v74 = (const OLECHAR *)v129[0];
      }
      *((_QWORD *)v9 + 5) = SysAllocString(v74);
      v76 = (OLECHAR *)*((_QWORD *)v9 + 4);
      if ( v76 )
      {
        SysFreeString(v76);
        *((_QWORD *)v9 + 4) = 0;
      }
      *((_QWORD *)v9 + 4) = SysAllocString(psz);
      v77 = (OLECHAR *)*((_QWORD *)v9 + 6);
      if ( v77 )
      {
        SysFreeString(v77);
        *((_QWORD *)v9 + 6) = 0;
      }
      *((_QWORD *)v9 + 6) = SysAllocString(bstrString);
      v78 = (OLECHAR *)*((_QWORD *)v9 + 7);
      if ( v78 )
      {
        SysFreeString(v78);
        *((_QWORD *)v9 + 7) = 0;
      }
      *((_QWORD *)v9 + 7) = SysAllocString(v122);
      *((_DWORD *)v9 + 16) = v119;
      *((_DWORD *)v9 + 17) = v66;
    }
    else
    {
      v66 = WiaTrace_TraceLog("Cannot notify clients of runtime event - we appear to be out of memory");
      WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", (char *)v66);
      WiaTrcLib::Free((WiaTrcLib *)v66, v79);
      v80 = (void *)WiaTrace_Trace("Cannot notify clients of runtime event - we appear to be out of memory");
      WiaTrace_ProcessTrace_Ex(v82, v81, (int)"CEventNotifier::NotifySTIEvent", 1, v80);
      DeviceInfo = -2147024882;
      LOBYTE(v66) = a3;
    }
    v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
    v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
  }
  if ( (v66 & 2) != 0 )
  {
    v83 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "WIA_ACTION_EVENT, starting the WiaRpc service...");
    WriteDbgTraceInfoWI("CEventNotifier::NotifySTIEvent", v83);
    WiaTrcLib::Free((WiaTrcLib *)v83, v84);
    v85 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "WIA_ACTION_EVENT, starting the WiaRpc service...");
    WiaTrace_ProcessTrace_Ex(v87, v86, (int)"CEventNotifier::NotifySTIEvent", 4, v85);
    StartWiaRpcService();
    v88 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Attempt to complete WiaRpc async RPC call...");
    WriteDbgTraceInfoWI("CEventNotifier::NotifySTIEvent", v88);
    WiaTrcLib::Free((WiaTrcLib *)v88, v89);
    v90 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Attempt to complete WiaRpc async RPC call...");
    WiaTrace_ProcessTrace_Ex(v92, v91, (int)"CEventNotifier::NotifySTIEvent", 4, v90);
    EnterCriticalSection(&CriticalSection);
    if ( g_RpcEvent )
    {
      LODWORD(Reply) = 1;
      *(_QWORD *)(qword_1800B1700 + 60) = *(_QWORD *)v131;
      *(_OWORD *)qword_1800B1700 = *(_OWORD *)((char *)a2 + 20);
      *(_QWORD *)(qword_1800B1700 + 16) = SysAllocString(psz);
      *(_QWORD *)(qword_1800B1700 + 24) = SysAllocString(*((const OLECHAR **)a2 + 1));
      *(_QWORD *)(qword_1800B1700 + 32) = SysAllocString(bstrString);
      *(_DWORD *)(qword_1800B1700 + 40) = v119;
      *(_QWORD *)(qword_1800B1700 + 48) = SysAllocString(v122);
      *(_DWORD *)(qword_1800B1700 + 56) = a3;
      v119 = RpcAsyncCompleteCall(g_RpcEvent, &Reply);
      if ( v119 )
      {
        v93 = (char *)WiaTrace_TraceLog("RpcAsyncComplete failed with error 0x%x");
        WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v93);
        WiaTrcLib::Free((WiaTrcLib *)v93, v94);
        v95 = (void *)WiaTrace_Trace("RpcAsyncComplete failed with error 0x%x", v119);
        WiaTrace_ProcessTrace_Ex(v97, v96, (int)"CEventNotifier::NotifySTIEvent", 1, v95);
      }
      g_RpcEvent = 0;
    }
    else
    {
      v98 = (char *)WiaTrace_TraceLog("There was no WiaRpc async RPC call!");
      WriteDbgTraceErrorWI("CEventNotifier::NotifySTIEvent", v98);
      WiaTrcLib::Free((WiaTrcLib *)v98, v99);
      v100 = (void *)WiaTrace_Trace("There was no WiaRpc async RPC call!");
      WiaTrace_ProcessTrace_Ex(v102, v101, (int)"CEventNotifier::NotifySTIEvent", 1, v100);
    }
    LeaveCriticalSection(&CriticalSection);
    v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
    v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
  }
  if ( v133 )
  {
    LeaveCriticalSection(lpCriticalSection);
    goto LABEL_102;
  }
LABEL_103:
  if ( v9 )
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v143, L"WiaEventNotifier");
    v104 = (WiaEventNotifier *)ServiceComponentHolder::Get<WiaEventNotifier>(v134, &v143);
    v143 = &CSimpleStringBase<unsigned short>::`vftable';
    if ( v145 && v145 != &v144 )
      operator delete(v145, v103);
    v145 = 0;
    v146 = 0;
    if ( v104 )
    {
      WiaEventNotifier::NotifyClients(v104, (struct WiaEventInfo *)v9);
      v105 = (char *)v104 + *(int *)(*(_QWORD *)v104 + 4LL);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v105 + 16LL))(v105);
    }
    else
    {
      v106 = (char *)WiaTrace_TraceLogWithSubComp(
                       1,
                       "StiRpc Error: Could not notify runtime event client because the WiaEventNotifier doesn't exist");
      WriteDbgTraceWarningWI("CEventNotifier::NotifySTIEvent", v106);
      WiaTrcLib::Free((WiaTrcLib *)v106, v107);
      v108 = (void *)WiaTrace_TraceWithSubComp(
                       1,
                       "StiRpc Error: Could not notify runtime event client because the WiaEventNotifier doesn't exist");
      WiaTrace_ProcessTrace_Ex(v110, v109, (int)"CEventNotifier::NotifySTIEvent", 2, v108);
      DeviceInfo = -2147467259;
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    v36 = *(CEventNotifier **)WIA_EVENT_DEVICE_DISCONNECTED.Data4;
    v34 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1;
  }
  v111 = (char *)(v34 - *(_QWORD *)((char *)a2 + 20));
  if ( !v111 )
    v111 = (char *)v36 - *(_QWORD *)((char *)a2 + 28);
  if ( !v111 )
    CEventNotifier::DelAllNodesForDevice(v36, *v130);
  if ( bstrString )
    SysFreeString(bstrString);
  if ( psz )
    SysFreeString(psz);
  if ( v122 )
    SysFreeString(v122);
  if ( v18 )
  {
    if ( (*(unsigned int (__fastcall **)(struct USDWrapper *, OLECHAR *, __int64))(*(_QWORD *)v18 + 168LL))(
           v18,
           v17,
           v16)
      && v125 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v125 + 16LL))(v125);
      v125 = 0;
    }
    (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  if ( v126 )
  {
    v112 = (char *)v126 + *(int *)(*((_QWORD *)v126 + 1) + 4LL) + 8;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v112 + 16LL))(v112);
  }
  if ( v135 )
  {
    v113 = v135 + *(int *)(*(_QWORD *)v135 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
  }
  CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v138);
  return (unsigned int)DeviceInfo;
}

```

## disassembly

```asm
0x1800033f4  mov     [rsp+arg_0], rbx
0x1800033f9  mov     [rsp+arg_18], rsi
0x1800033fe  push    rdi
0x1800033ff  push    r12
0x180003401  push    r13
0x180003403  push    r14
0x180003405  push    r15
0x180003407  sub     rsp, 410h
0x18000340e  mov     rax, cs:__security_cookie
0x180003415  xor     rax, rsp
0x180003418  mov     [rsp+438h+var_38], rax
0x180003420  mov     [rsp+438h+var_368], r9
0x180003428  mov     [rsp+438h+var_3F8], r8d
0x18000342d  mov     r13, rdx
0x180003430  mov     [rsp+438h+var_398], rdx
0x180003438  mov     rax, [rsp+438h+arg_20]
0x180003440  mov     [rsp+438h+var_3D0], rax
0x180003445  lea     rcx, Class; unsigned __int16 *
0x18000344c  call    ?WiaTrace_Trace@@YAPEAUtagWiaTraceData_Type@@PEBGZZ; WiaTrace_Trace(ushort const *,...)
0x180003451  mov     [rsp+438h+var_410], rax; struct tagWiaTraceData_Type *
0x180003456  lea     r15, aCeventnotifier_6; "CEventNotifier::NotifySTIEvent"
0x18000345d  mov     r9, r15; char *
0x180003460  lea     rcx, [rsp+438h+var_2E8]; this
0x180003468  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18000346d  xor     edi, edi
0x18000346f  mov     [rsp+438h+var_3E4], edi
0x180003473  mov     [rsp+438h+bstrString], rdi
0x180003478  mov     [rsp+438h+var_3B8], rdi
0x180003480  mov     [rsp+438h+var_3A0], rdi
0x180003488  mov     [rsp+438h+psz], rdi
0x18000348d  mov     [rsp+438h+var_3E0], edi
0x180003491  mov     [rsp+438h+var_3A8], edi
0x180003498  mov     [rsp+438h+Reply], rdi
0x18000349d  mov     esi, edi
0x18000349f  lea     rcx, [rsp+438h+var_350]; this
0x1800034a7  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x1800034ac  xor     edx, edx; Val
0x1800034ae  lea     r8d, [rdi+48h]; Size
0x1800034b2  lea     rcx, [rsp+438h+var_338]; void *
0x1800034ba  call    memset_0
0x1800034bf  lea     r12, [r13+8]
0x1800034c3  mov     [rsp+438h+var_380], r12
0x1800034cb  lea     r9, [rsp+438h+Reply]; struct USDWrapper **
0x1800034d0  lea     r8, [rsp+438h+bstrString]; unsigned __int16 **
0x1800034d5  lea     rdx, [rsp+438h+var_3E4]; unsigned int *
0x1800034da  mov     rcx, [r12]; unsigned __int16 *
0x1800034de  call    ?WiaGetDeviceInfo@@YAJPEBGPEAKPEAPEAGPEAPEAVUSDWrapper@@@Z; WiaGetDeviceInfo(ushort const *,ulong *,ushort * *,USDWrapper * *)
0x1800034e3  mov     r14d, eax
0x1800034e6  test    eax, eax
0x1800034e8  jz      short loc_180003554
0x1800034ea  mov     [rsp+438h+var_3B0], rdi
0x1800034f2  mov     edx, eax
0x1800034f4  lea     rcx, aFailedToGetWia; "Failed to get WiaGetDeviceInfo from Not"...
0x1800034fb  call    WiaTrace_TraceLog
0x180003500  mov     rbx, rax
0x180003503  mov     rdx, rax; char *
0x180003506  mov     rcx, r15; char *
0x180003509  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000350e  mov     rcx, rbx; this
0x180003511  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180003516  mov     edx, r14d
0x180003519  lea     rcx, aFailedToGetWia; "Failed to get WiaGetDeviceInfo from Not"...
0x180003520  call    WiaTrace_Trace
0x180003525  mov     [rsp+438h+lpMem], rax; lpMem
0x18000352a  lea     r15d, [rdi+1]
0x18000352e  mov     r9d, r15d; int
0x180003531  lea     r8, aCeventnotifier_6; "CEventNotifier::NotifySTIEvent"
0x180003538  call    WiaTrace_ProcessTrace_Ex
0x18000353d  mov     rdx, [rsp+438h+var_308]
0x180003545  mov     [rsp+438h+var_3D0], rdx
0x18000354a  mov     r12, [rsp+438h+Reply]
0x18000354f  jmp     loc_18000401E
0x180003554  lea     rdx, aStilockmgr; "StiLockMgr"
0x18000355b  lea     rcx, [rsp+438h+var_298]
0x180003563  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x180003568  lea     rdx, [rsp+438h+var_298]
0x180003570  lea     rcx, [rsp+438h+var_350]
0x180003578  call    ??$Get@VStiLockMgr@@@ServiceComponentHolder@@QEAAPEAVStiLockMgr@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<StiLockMgr>(CSimpleStringBase<ushort> const &)
0x18000357d  mov     rbx, rax
0x180003580  mov     [rsp+438h+var_3B0], rax
0x180003588  mov     [rsp+438h+var_388], rax
0x180003590  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180003597  mov     [rsp+438h+var_298], rax
0x18000359f  mov     rcx, [rsp+438h+var_190]; void *
0x1800035a7  test    rcx, rcx
0x1800035aa  jz      short loc_1800035BE
0x1800035ac  lea     rax, [rsp+438h+var_290]
0x1800035b4  cmp     rcx, rax
0x1800035b7  jz      short loc_1800035BE
0x1800035b9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800035be  mov     [rsp+438h+var_190], rdi
0x1800035c6  mov     [rsp+438h+var_188], rdi
0x1800035ce  test    rbx, rbx
0x1800035d1  jnz     short loc_18000362E
0x1800035d3  mov     rdx, [r12]
0x1800035d7  lea     rcx, aTheLockManager_7; "The Lock Manager is NULL - we cannot no"...
0x1800035de  call    WiaTrace_TraceLog
0x1800035e3  mov     rbx, rax
0x1800035e6  mov     rdx, rax; char *
0x1800035e9  mov     rcx, r15; char *
0x1800035ec  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800035f1  mov     rcx, rbx; this
0x1800035f4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800035f9  mov     rdx, [r12]
0x1800035fd  lea     rcx, aTheLockManager_7; "The Lock Manager is NULL - we cannot no"...
0x180003604  call    WiaTrace_Trace
0x180003609  mov     [rsp+438h+lpMem], rax; lpMem
0x18000360e  mov     r15d, 1
0x180003614  mov     r9d, r15d; int
0x180003617  lea     r8, aCeventnotifier_6; "CEventNotifier::NotifySTIEvent"
0x18000361e  call    WiaTrace_ProcessTrace_Ex
0x180003623  mov     r14d, 8000FFFFh
0x180003629  jmp     loc_18000353D
0x18000362e  lea     rdx, stru_1800AF348; struct _RTL_CRITICAL_SECTION *
0x180003635  lea     rcx, [rsp+438h+lpCriticalSection]; this
0x18000363d  call    ??0CWiaCritSect@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CWiaCritSect::CWiaCritSect(_RTL_CRITICAL_SECTION *)
0x180003642  mov     r12, [rsp+438h+Reply]
0x180003647  mov     rax, [r12]
0x18000364b  lea     r8, [rsp+438h+var_3B8]
0x180003653  lea     rdx, IID_IWiaMiniDrv
0x18000365a  mov     rcx, r12
0x18000365d  mov     rax, [rax]
0x180003660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003665  mov     r14d, eax
0x180003668  test    eax, eax
0x18000366a  jns     short loc_1800036B7
0x18000366c  mov     r8d, eax
0x18000366f  lea     rdx, aFailedToQiForI; "Failed to QI for IWiaMini from NotifyST"...
0x180003676  xor     ecx, ecx
0x180003678  call    WiaTrace_TraceLogWithSubComp
0x18000367d  mov     rbx, rax
0x180003680  mov     rdx, rax; char *
0x180003683  mov     rcx, r15; char *
0x180003686  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000368b  mov     rcx, rbx; this
0x18000368e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180003693  mov     r8d, r14d
0x180003696  lea     rdx, aFailedToQiForI; "Failed to QI for IWiaMini from NotifyST"...
0x18000369d  xor     ecx, ecx
0x18000369f  call    WiaTrace_TraceWithSubComp
0x1800036a4  mov     [rsp+438h+lpMem], rax; lpMem
0x1800036a9  mov     r9d, 2; int
0x1800036af  mov     r8, r15; int
0x1800036b2  call    WiaTrace_ProcessTrace_Ex
0x1800036b7  mov     [rsp+438h+var_3E8], edi
0x1800036bb  test    r14d, r14d
0x1800036be  js      loc_1800038EC
0x1800036c4  lea     rbx, [r13+14h]
0x1800036c8  mov     rax, [r12]
0x1800036cc  xor     r9d, r9d
0x1800036cf  mov     r8, [rsp+438h+var_380]
0x1800036d7  mov     r8, [r8]
0x1800036da  mov     rdx, rbx
0x1800036dd  mov     rcx, r12
0x1800036e0  mov     rax, [rax+1D0h]
0x1800036e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ec  mov     r14d, eax
0x1800036ef  mov     [rsp+438h+var_3C8], eax
0x1800036f3  test    eax, eax
0x1800036f5  js      loc_1800037D5
0x1800036fb  mov     rdx, [rbx]
0x1800036fe  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data1
0x180003705  sub     rdx, rax
0x180003708  mov     rcx, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data4
0x18000370f  jnz     short loc_180003718
0x180003711  mov     rdx, [rbx+8]
0x180003715  sub     rdx, rcx
0x180003718  test    rdx, rdx
0x18000371b  jz      loc_1800037CD
0x180003721  mov     rax, [r12]
0x180003725  mov     rcx, r12
0x180003728  mov     rax, [rax+98h]
0x18000372f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003734  test    rax, rax
0x180003737  jz      short loc_180003786
0x180003739  test    byte ptr [rax+18h], 8
0x18000373d  jz      short loc_18000375B
0x18000373f  mov     rax, [rbx]
0x180003742  sub     rax, qword ptr cs:WIA_EVENT_DEVICE_CONNECTED.Data1
0x180003749  jnz     short loc_180003756
0x18000374b  mov     rax, [rbx+8]
0x18000374f  sub     rax, qword ptr cs:WIA_EVENT_DEVICE_CONNECTED.Data4
0x180003756  test    rax, rax
0x180003759  jz      short loc_180003786
0x18000375b  mov     [rsp+438h+lpMem], rdi; unsigned __int8 *
0x180003760  mov     r8d, 4E20h; unsigned int
0x180003766  mov     rdx, r12; struct USDWrapper *
0x180003769  call    ?RequestLock@StiLockMgr@@QEAAJPEAVUSDWrapper@@KHPEAE@Z; StiLockMgr::RequestLock(USDWrapper *,ulong,int,uchar *)
0x18000376e  mov     r14d, eax
0x180003771  mov     [rsp+438h+var_3C8], eax
0x180003775  test    eax, eax
0x180003777  js      short loc_1800037D5
0x180003779  mov     r15d, 1
0x18000377f  mov     [rsp+438h+var_3E8], r15d
0x180003784  jmp     short loc_18000378C
0x180003786  mov     r15d, 1
0x18000378c  mov     rax, [r12]
0x180003790  lea     rcx, [rsp+438h+var_3A8]
0x180003798  mov     [rsp+438h+var_410], rcx
0x18000379d  lea     rcx, [rsp+438h+var_3A0]
0x1800037a5  mov     [rsp+438h+lpMem], rcx
0x1800037aa  lea     r9, [rsp+438h+var_3E0]
0x1800037af  xor     edx, edx
0x1800037b1  lea     r8d, [rdx+2]
0x1800037b5  mov     rcx, r12
0x1800037b8  mov     rax, [rax+1C0h]
0x1800037bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c4  mov     r14d, eax
0x1800037c7  mov     [rsp+438h+var_3C8], eax
0x1800037cb  jmp     short loc_1800037DB
0x1800037cd  mov     r15d, 1
0x1800037d3  jmp     short loc_1800037E9
0x1800037d5  mov     r15d, 1
0x1800037db  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data1
0x1800037e2  mov     rcx, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data4
0x1800037e9  cmp     [rsp+438h+var_3E8], edi
0x1800037ed  jz      short loc_180003811
0x1800037ef  mov     rdx, r12; struct USDWrapper *
0x1800037f2  mov     rcx, [rsp+438h+var_3B0]; this
0x1800037fa  call    ?RequestUnlock@StiLockMgr@@QEAAJPEAVUSDWrapper@@H@Z; StiLockMgr::RequestUnlock(USDWrapper *,int)
0x1800037ff  mov     [rsp+438h+var_3E8], edi
0x180003803  mov     rcx, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data4
0x18000380a  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data1
0x180003811  jmp     loc_180003900
0x180003816  lea     rcx, aExceptionHappe; "Exception happened in the drvGetCapabil"...
0x18000381d  call    WiaTrace_TraceLog
0x180003822  mov     rbx, rax
0x180003825  mov     rdx, rax; char *
0x180003828  lea     rcx, aCeventnotifier_6; "CEventNotifier::NotifySTIEvent"
0x18000382f  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180003834  mov     rcx, rbx; this
0x180003837  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000383c  lea     rcx, aExceptionHappe; "Exception happened in the drvGetCapabil"...
0x180003843  call    WiaTrace_Trace
0x180003848  mov     [rsp+438h+lpMem], rax; lpMem
0x18000384d  mov     r9d, 1; int
0x180003853  lea     r8, aCeventnotifier_6; "CEventNotifier::NotifySTIEvent"
0x18000385a  call    WiaTrace_ProcessTrace_Ex
0x18000385f  mov     rcx, [rsp+438h+bstrString]; bstrString
0x180003864  call    cs:__imp_SysFreeString
0x18000386a  mov     rcx, [rsp+438h+var_3B8]
0x180003872  test    rcx, rcx
0x180003875  jz      short loc_18000388F
0x180003877  mov     rax, [rcx]
0x18000387a  mov     rax, [rax+10h]
0x18000387e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003883  mov     [rsp+438h+var_3B8], 0
0x18000388f  mov     r14d, 80004005h
0x180003895  lea     rcx, [rsp+438h+lpCriticalSection]; this
0x18000389d  call    ??1CWiaCritSect@@QEAA@XZ; CWiaCritSect::~CWiaCritSect(void)
0x1800038a2  xor     edi, edi
0x1800038a4  lea     r15d, [rdi+1]
0x1800038a8  mov     [rsp+438h+psz], rdi
0x1800038ad  mov     rax, [rsp+438h+var_308]
0x1800038b5  mov     [rsp+438h+var_3D0], rax
0x1800038ba  mov     r12, [rsp+438h+Reply]
0x1800038bf  mov     esi, edi
0x1800038c1  mov     rcx, [rsp+438h+var_388]
0x1800038c9  mov     [rsp+438h+var_3B0], rcx
0x1800038d1  mov     rcx, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data4
0x1800038d8  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data1
0x1800038df  mov     r13, [rsp+438h+var_398]
0x1800038e7  jmp     loc_18000402C
0x1800038ec  mov     r15d, 1
0x1800038f2  mov     rcx, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data4
0x1800038f9  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data1
0x180003900  test    r14d, r14d
0x180003903  js      loc_180003B47
0x180003909  cmp     [rsp+438h+var_3A0], rdi
0x180003911  jz      loc_180003AD8
0x180003917  mov     [rsp+438h+var_390], r12
0x18000391f  lea     rcx, [r12+1028h]; this
0x180003927  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18000392c  mov     dword ptr [rsp+438h+var_398], eax
0x180003933  mov     rax, [r12]
0x180003937  mov     rcx, r12
0x18000393a  mov     rax, [rax+0A8h]
0x180003941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003946  test    eax, eax
0x180003948  jz      loc_180003A0F
0x18000394e  mov     ebx, edi
0x180003950  mov     dword ptr [rsp+438h+Reply], ebx
0x180003954  cmp     ebx, [rsp+438h+var_3E0]
0x180003958  jge     loc_180003A61
0x18000395e  movsxd  rax, ebx
0x180003961  lea     rdx, [rax+rax*4]
0x180003965  mov     r8, [rsp+438h+var_3A0]
0x18000396d  mov     rcx, [r8+rdx*8]
0x180003971  test    rcx, rcx
0x180003974  jz      short loc_1800039B0
0x180003976  mov     rax, [rcx]
0x180003979  sub     rax, [r13+14h]
0x18000397d  jnz     short loc_180003987
0x18000397f  mov     rax, [rcx+8]
0x180003983  sub     rax, [r13+1Ch]
0x180003987  test    rax, rax
0x18000398a  jnz     short loc_180003A07
0x18000398c  cmp     [rsp+438h+var_3F8], eax
0x180003990  jnz     short loc_18000399B
0x180003992  mov     eax, [r8+rdx*8+8]
  ... truncated ...
```
