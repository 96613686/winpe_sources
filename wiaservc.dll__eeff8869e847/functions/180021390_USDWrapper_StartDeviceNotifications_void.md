# USDWrapper::StartDeviceNotifications(void)

- ea: `0x180021390`
- end: `0x18002194f`
- name: `?StartDeviceNotifications@USDWrapper@@MEAAJXZ`
- size: `1471`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009210`
- `0x18000ac34`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x180021390`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800218cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800218cb`
- `KERNEL32!CreateEventW` at `0x1800215c6`
- `KERNEL32!CreateEventW` at `0x1800215c6`
- `KERNEL32!GetLastError` at `0x1800215dd`
- `KERNEL32!GetLastError` at `0x180021772`
- `KERNEL32!GetLastError` at `0x1800215dd`
- `KERNEL32!GetLastError` at `0x180021772`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800216b7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800216b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002173e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021732`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002173e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021768`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180021768`

## string_xrefs

- `0x18002177b`: `We could not create the Event object for (%ws), DuplicateHandle returned 0x%08X`
- `0x1800217a2`: `We could not create the Event object for (%ws), DuplicateHandle returned 0x%08X`
- `0x1800215e6`: `We could not create the Event object for (%ws), CreateEvent returned 0x%08X`
- `0x18002160d`: `We could not create the Event object for (%ws), CreateEvent returned 0x%08X`
- `0x18002164b`: `DeviceEvent [0x%X] for (%ws) successfully created`
- `0x180021679`: `DeviceEvent [0x%X] for (%ws) successfully created`
- `0x1800214c4`: `DeviceEvent [0x%X] for (%ws) reset to be scheduled`
- `0x1800214f5`: `DeviceEvent [0x%X] for (%ws) reset to be scheduled`

## pseudocode

```c
__int64 __fastcall USDWrapper::StartDeviceNotifications(struct IUnknown *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  signed int LastError; // edi
  struct IUnknown *v4; // rsi
  char *v5; // rbx
  void *v6; // rdx
  void **v7; // rax
  void *v8; // rdx
  __int64 v9; // rcx
  char *v10; // rbx
  void *v11; // rdx
  void **v12; // rax
  void *v13; // rdx
  __int64 v14; // rcx
  struct IUnknown *v15; // r15
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // eax
  char *v22; // rbx
  void *v23; // rdx
  void **v24; // rax
  void *v25; // rdx
  __int64 v26; // rcx
  struct IUnknownVtbl *EventW; // r9
  char *v28; // rbx
  void *v29; // rdx
  void **v30; // rax
  void *v31; // rdx
  __int64 v32; // rcx
  bool v33; // sf
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  char *v39; // rbx
  void *v40; // rdx
  void **v41; // rax
  void *v42; // rdx
  __int64 v43; // rcx
  HANDLE CurrentProcess; // rax
  struct IUnknownVtbl *lpVtbl; // rdi
  void *v46; // rbx
  HANDLE v47; // rax
  char *v48; // rbx
  void *v49; // rdx
  signed int v50; // eax
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
  char *v61; // rbx
  void *v62; // rdx
  void **v63; // rax
  void *v64; // rdx
  __int64 v65; // rcx
  char *v67; // rbx
  void *v68; // rdx
  void **v69; // rax
  void *v70; // rdx
  __int64 v71; // rcx
  DWORD dwDesiredAccess[2]; // [rsp+20h] [rbp-48h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-48h]
  int v74; // [rsp+70h] [rbp+8h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp+10h]

  v1 = (struct _RTL_CRITICAL_SECTION *)&this[529];
  lpCriticalSection = (LPCRITICAL_SECTION)&this[529];
  LastError = 0;
  v74 = CRIT_SECT::Lock((CRIT_SECT *)&this[529]);
  if ( (BYTE4(this[7].lpVtbl) & 1) != 0 && !HIDWORD(this[5].lpVtbl) )
  {
    v4 = this + 301;
    v5 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                   0,
                   0,
                   "The device (%ws) appears to support device notifications",
                   this[301].lpVtbl);
    WriteDbgTraceInfoWI("USDWrapper::StartDeviceNotifications", v5);
    WiaTrcLib::Free((WiaTrcLib *)v5, v6);
    v7 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                    0,
                    0,
                    "The device (%ws) appears to support device notifications",
                    this[301].lpVtbl);
    WiaTrace_ProcessTrace_Ex(v9, v8, (void *)"USDWrapper::StartDeviceNotifications", 4, v7);
    if ( (BYTE4(this[7].lpVtbl) & 2) != 0 )
    {
      if ( LODWORD(this[5].lpVtbl) < 0x1F4 )
      {
        v10 = (char *)WiaTrace_TraceLogWithSubComp(
                        0,
                        "The USD for (%ws) specified a polling interval of %dms - we will change it to be our minimum acc"
                        "epted value of %dms",
                        v4->lpVtbl);
        WriteDbgTraceWarningWI("USDWrapper::StartDeviceNotifications", v10);
        WiaTrcLib::Free((WiaTrcLib *)v10, v11);
        dwDesiredAccess[0] = 500;
        v12 = (void **)WiaTrace_TraceWithSubComp(
                         0,
                         "The USD for (%ws) specified a polling interval of %dms - we will change it to be our minimum ac"
                         "cepted value of %dms",
                         v4->lpVtbl,
                         LODWORD(this[5].lpVtbl),
                         *(_QWORD *)dwDesiredAccess);
        WiaTrace_ProcessTrace_Ex(v14, v13, (void *)"USDWrapper::StartDeviceNotifications", 2, v12);
        LODWORD(this[5].lpVtbl) = 500;
      }
      v15 = this + 500;
      goto LABEL_7;
    }
    v15 = this + 500;
    LODWORD(this[5].lpVtbl) = -1;
    if ( (((unsigned __int64)&this[500].lpVtbl->QueryInterface + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      EventW = (struct IUnknownVtbl *)CreateEventW(0, 1, 0, 0);
      v15->lpVtbl = EventW;
      if ( (((unsigned __int64)&EventW->QueryInterface + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      {
        LastError = GetLastError();
        v28 = (char *)WiaTrace_TraceLog("We could not create the Event object for (%ws), CreateEvent returned 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::StartDeviceNotifications", v28);
        WiaTrcLib::Free((WiaTrcLib *)v28, v29);
        v30 = (void **)WiaTrace_Trace(
                         "We could not create the Event object for (%ws), CreateEvent returned 0x%08X",
                         v4->lpVtbl,
                         (unsigned int)LastError);
        goto LABEL_12;
      }
      v34 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "DeviceEvent [0x%X] for (%ws) successfully created",
                      EventW,
                      v4->lpVtbl);
      WriteDbgTraceInfoWI("USDWrapper::StartDeviceNotifications", v34);
      WiaTrcLib::Free((WiaTrcLib *)v34, v35);
      v36 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "DeviceEvent [0x%X] for (%ws) successfully created",
                       v15->lpVtbl,
                       v4->lpVtbl);
      WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"USDWrapper::StartDeviceNotifications", 4, v36);
    }
    if ( (((unsigned __int64)&v15->lpVtbl->QueryInterface + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
LABEL_7:
      ((void (__fastcall *)(struct IUnknown *))this->lpVtbl[22].AddRef)(this);
      v16 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "DeviceEvent [0x%X] for (%ws) reset to be scheduled",
                      v15->lpVtbl,
                      v4->lpVtbl);
      WriteDbgTraceInfoWI("USDWrapper::StartDeviceNotifications", v16);
      WiaTrcLib::Free((WiaTrcLib *)v16, v17);
      v18 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "DeviceEvent [0x%X] for (%ws) reset to be scheduled",
                       v15->lpVtbl,
                       v4->lpVtbl);
      WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"USDWrapper::StartDeviceNotifications", 4, v18);
      v21 = ScheduleWorkItem(
              (void (*)(struct IUnknown *))USDWrapper::NotificationCallback,
              this,
              (unsigned int)this[5].lpVtbl,
              v15->lpVtbl,
              dwDesiredAccessa);
      LODWORD(this[502].lpVtbl) = v21;
      if ( v21 )
      {
        v22 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0,
                        0,
                        "Started receiving notifications for device (%ws)",
                        v4->lpVtbl);
        WriteDbgTraceInfoWI("USDWrapper::StartDeviceNotifications", v22);
        WiaTrcLib::Free((WiaTrcLib *)v22, v23);
        v24 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         0,
                         0,
                         "Started receiving notifications for device (%ws)",
                         v4->lpVtbl);
        WiaTrace_ProcessTrace_Ex(v26, v25, (void *)"USDWrapper::StartDeviceNotifications", 4, v24);
      }
      else
      {
        v56 = (char *)WiaTrace_TraceLog("We could not schedule the notification callback for (%ws)");
        WriteDbgTraceErrorWI("USDWrapper::StartDeviceNotifications", v56);
        WiaTrcLib::Free((WiaTrcLib *)v56, v57);
        v58 = (void **)WiaTrace_Trace("We could not schedule the notification callback for (%ws)", v4->lpVtbl);
        WiaTrace_ProcessTrace_Ex(v60, v59, (void *)"USDWrapper::StartDeviceNotifications", 1, v58);
        LastError = -2147418113;
      }
      goto LABEL_24;
    }
    ResetEvent(v15->lpVtbl);
    v39 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "DeviceEvent [0x%X] for (%ws) reset to be passed to IStiUSD::SetNotificationHandle",
                    v15->lpVtbl,
                    v4->lpVtbl);
    WriteDbgTraceInfoWI("USDWrapper::StartDeviceNotifications", v39);
    WiaTrcLib::Free((WiaTrcLib *)v39, v40);
    v41 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "DeviceEvent [0x%X] for (%ws) reset to be passed to IStiUSD::SetNotificationHandle",
                     v15->lpVtbl,
                     v4->lpVtbl);
    WiaTrace_ProcessTrace_Ex(v43, v42, (void *)"USDWrapper::StartDeviceNotifications", 4, v41);
    if ( (((unsigned __int64)&this[501].lpVtbl->QueryInterface + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
      || (CurrentProcess = GetCurrentProcess(),
          lpVtbl = v15->lpVtbl,
          v46 = CurrentProcess,
          v47 = GetCurrentProcess(),
          DuplicateHandle(v47, lpVtbl, v46, (LPHANDLE)&this[501].lpVtbl, 0, 0, 2u)) )
    {
      v50 = ((__int64 (__fastcall *)(struct IUnknown *, struct IUnknownVtbl *))this->lpVtbl[12].AddRef)(
              this,
              this[501].lpVtbl);
      LastError = 0;
      if ( v50 != -2147467263 )
        LastError = v50;
      if ( LastError < 0 )
      {
        v51 = (char *)WiaTrace_TraceLog("USD for (%ws) refused to take event handle - call to IStiUSD::SetNotificationHan"
                                        "dle failed with 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::StartDeviceNotifications", v51);
        WiaTrcLib::Free((WiaTrcLib *)v51, v52);
        v53 = (void **)WiaTrace_Trace(
                         "USD for (%ws) refused to take event handle - call to IStiUSD::SetNotificationHandle failed with 0x%08X",
                         v4->lpVtbl,
                         (unsigned int)LastError);
        WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"USDWrapper::StartDeviceNotifications", 1, v53);
        goto LABEL_26;
      }
      goto LABEL_7;
    }
    LastError = GetLastError();
    v48 = (char *)WiaTrace_TraceLog("We could not create the Event object for (%ws), DuplicateHandle returned 0x%08X");
    WriteDbgTraceErrorWI("USDWrapper::StartDeviceNotifications", v48);
    WiaTrcLib::Free((WiaTrcLib *)v48, v49);
    v30 = (void **)WiaTrace_Trace(
                     "We could not create the Event object for (%ws), DuplicateHandle returned 0x%08X",
                     v4->lpVtbl,
                     (unsigned int)LastError);
LABEL_12:
    WiaTrace_ProcessTrace_Ex(v32, v31, (void *)"USDWrapper::StartDeviceNotifications", 1, v30);
    v33 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_25;
    LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_24:
    v33 = LastError < 0;
LABEL_25:
    if ( !v33 )
    {
LABEL_27:
      v1 = lpCriticalSection;
      goto LABEL_28;
    }
LABEL_26:
    v61 = (char *)WiaTrace_TraceLog("Due to the above errors, we will likely NOT be able to receive event notifications from (%ws)");
    WriteDbgTraceErrorWI("USDWrapper::StartDeviceNotifications", v61);
    WiaTrcLib::Free((WiaTrcLib *)v61, v62);
    v63 = (void **)WiaTrace_Trace(
                     "Due to the above errors, we will likely NOT be able to receive event notifications from (%ws)",
                     v4->lpVtbl);
    WiaTrace_ProcessTrace_Ex(v65, v64, (void *)"USDWrapper::StartDeviceNotifications", 1, v63);
    goto LABEL_27;
  }
  v67 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                  0,
                  0,
                  "Driver for (%ws) reported that it not capable of generating events",
                  this[301].lpVtbl);
  WriteDbgTraceInfoWI("USDWrapper::StartDeviceNotifications", v67);
  WiaTrcLib::Free((WiaTrcLib *)v67, v68);
  v69 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                   0,
                   0,
                   "Driver for (%ws) reported that it not capable of generating events",
                   this[301].lpVtbl);
  WiaTrace_ProcessTrace_Ex(v71, v70, (void *)"USDWrapper::StartDeviceNotifications", 4, v69);
LABEL_28:
  if ( v74 )
    LeaveCriticalSection(v1);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180021390  mov     [rsp+arg_10], rbx
0x180021395  mov     [rsp+arg_18], rbp
0x18002139a  push    rsi
0x18002139b  push    rdi
0x18002139c  push    r13
0x18002139e  push    r14
0x1800213a0  push    r15
0x1800213a2  sub     rsp, 40h
0x1800213a6  lea     rsi, [rcx+1088h]
0x1800213ad  mov     r14, rcx
0x1800213b0  mov     rcx, rsi; this
0x1800213b3  mov     [rsp+68h+lpCriticalSection], rsi
0x1800213b8  xor     edi, edi
0x1800213ba  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x1800213bf  test    byte ptr [r14+3Ch], 1
0x1800213c4  mov     [rsp+68h+arg_0], eax
0x1800213c8  jz      loc_1800218EC
0x1800213ce  cmp     [r14+2Ch], edi
0x1800213d2  jnz     loc_1800218EC
0x1800213d8  lea     rsi, [r14+968h]
0x1800213df  xor     edx, edx
0x1800213e1  mov     r9, [rsi]
0x1800213e4  lea     r8, aTheDeviceWsApp; "The device (%ws) appears to support dev"...
0x1800213eb  xor     ecx, ecx
0x1800213ed  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800213f2  lea     rbp, aUsdwrapperStar; "USDWrapper::StartDeviceNotifications"
0x1800213f9  mov     rdx, rax; char *
0x1800213fc  mov     rcx, rbp; char *
0x1800213ff  mov     rbx, rax
0x180021402  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180021407  mov     rcx, rbx; this
0x18002140a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002140f  mov     r9, [rsi]
0x180021412  lea     r8, aTheDeviceWsApp; "The device (%ws) appears to support dev"...
0x180021419  xor     edx, edx
0x18002141b  xor     ecx, ecx
0x18002141d  call    WiaTrace_TraceWithSubCompTraceLevel
0x180021422  lea     r9d, [rdi+4]; int
0x180021426  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x18002142b  mov     r8, rbp; int
0x18002142e  call    WiaTrace_ProcessTrace_Ex
0x180021433  test    byte ptr [r14+3Ch], 2
0x180021438  jz      loc_180021599
0x18002143e  mov     r9d, [r14+28h]
0x180021442  mov     r15d, 1F4h
0x180021448  cmp     r9d, r15d
0x18002144b  jnb     short loc_1800214A8
0x18002144d  mov     r8, [rsi]
0x180021450  lea     rdx, aTheUsdForWsSpe; "The USD for (%ws) specified a polling i"...
0x180021457  xor     ecx, ecx
0x180021459  mov     [rsp+68h+dwDesiredAccess], r15d
0x18002145e  call    WiaTrace_TraceLogWithSubComp
0x180021463  mov     rdx, rax; char *
0x180021466  mov     rcx, rbp; char *
0x180021469  mov     rbx, rax
0x18002146c  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180021471  mov     rcx, rbx; this
0x180021474  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021479  mov     r9d, [r14+28h]
0x18002147d  lea     rdx, aTheUsdForWsSpe; "The USD for (%ws) specified a polling i"...
0x180021484  mov     r8, [rsi]
0x180021487  xor     ecx, ecx
0x180021489  mov     [rsp+68h+dwDesiredAccess], r15d
0x18002148e  call    WiaTrace_TraceWithSubComp
0x180021493  lea     r9d, [rdi+2]; int
0x180021497  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x18002149c  mov     r8, rbp; int
0x18002149f  call    WiaTrace_ProcessTrace_Ex
0x1800214a4  mov     [r14+28h], r15d
0x1800214a8  lea     r15, [r14+0FA0h]
0x1800214af  mov     rax, [r14]
0x1800214b2  mov     rcx, r14
0x1800214b5  mov     rax, [rax+218h]
0x1800214bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214c1  mov     rax, [rsi]
0x1800214c4  lea     r8, aDeviceevent0xX_1; "DeviceEvent [0x%X] for (%ws) reset to b"...
0x1800214cb  mov     r9, [r15]
0x1800214ce  xor     edx, edx
0x1800214d0  xor     ecx, ecx
0x1800214d2  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x1800214d7  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800214dc  mov     rdx, rax; char *
0x1800214df  mov     rcx, rbp; char *
0x1800214e2  mov     rbx, rax
0x1800214e5  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800214ea  mov     rcx, rbx; this
0x1800214ed  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800214f2  mov     rax, [rsi]
0x1800214f5  lea     r8, aDeviceevent0xX_1; "DeviceEvent [0x%X] for (%ws) reset to b"...
0x1800214fc  mov     r9, [r15]
0x1800214ff  xor     edx, edx
0x180021501  xor     ecx, ecx
0x180021503  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x180021508  call    WiaTrace_TraceWithSubCompTraceLevel
0x18002150d  mov     r9d, 4; int
0x180021513  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; int
0x180021518  mov     r8, rbp; int
0x18002151b  call    WiaTrace_ProcessTrace_Ex
0x180021520  mov     r9, [r15]; void *
0x180021523  lea     rcx, ?NotificationCallback@USDWrapper@@KAXPEAX@Z; void (*)(struct IUnknown *)
0x18002152a  mov     r8d, [r14+28h]; unsigned int
0x18002152e  mov     rdx, r14; struct IUnknown *
0x180021531  call    ?ScheduleWorkItem@@YAKP6AXPEAUIUnknown@@@Z0KPEAXH@Z; ScheduleWorkItem(void (*)(IUnknown *),IUnknown *,ulong,void *,int)
0x180021536  mov     [r14+0FB0h], eax
0x18002153d  test    eax, eax
0x18002153f  jz      loc_180021825
0x180021545  mov     r9, [rsi]
0x180021548  lea     r8, aStartedReceivi; "Started receiving notifications for dev"...
0x18002154f  xor     edx, edx
0x180021551  xor     ecx, ecx
0x180021553  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180021558  mov     rdx, rax; char *
0x18002155b  mov     rcx, rbp; char *
0x18002155e  mov     rbx, rax
0x180021561  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180021566  mov     rcx, rbx; this
0x180021569  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002156e  mov     r9, [rsi]
0x180021571  lea     r8, aStartedReceivi; "Started receiving notifications for dev"...
0x180021578  xor     edx, edx
0x18002157a  xor     ecx, ecx
0x18002157c  call    WiaTrace_TraceWithSubCompTraceLevel
0x180021581  mov     r9d, 4; int
0x180021587  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x18002158c  mov     r8, rbp; int
0x18002158f  call    WiaTrace_ProcessTrace_Ex
0x180021594  jmp     loc_180021871
0x180021599  lea     r15, [r14+0FA0h]
0x1800215a0  mov     dword ptr [r14+28h], 0FFFFFFFFh
0x1800215a8  mov     rax, [r15]
0x1800215ab  inc     rax
0x1800215ae  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800215b4  jnz     loc_1800216A4
0x1800215ba  xor     r9d, r9d; lpName
0x1800215bd  xor     r8d, r8d; bInitialState
0x1800215c0  xor     ecx, ecx; lpEventAttributes
0x1800215c2  lea     edx, [r9+1]; bManualReset
0x1800215c6  call    cs:__imp_CreateEventW
0x1800215cc  mov     r9, rax
0x1800215cf  mov     [r15], rax
0x1800215d2  inc     rax
0x1800215d5  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800215db  jnz     short loc_180021648
0x1800215dd  call    cs:__imp_GetLastError
0x1800215e3  mov     rdx, [rsi]
0x1800215e6  lea     rcx, aWeCouldNotCrea_0; "We could not create the Event object fo"...
0x1800215ed  mov     r8d, eax
0x1800215f0  mov     edi, eax
0x1800215f2  call    WiaTrace_TraceLog
0x1800215f7  mov     rdx, rax; char *
0x1800215fa  mov     rcx, rbp; char *
0x1800215fd  mov     rbx, rax
0x180021600  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021605  mov     rcx, rbx; this
0x180021608  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002160d  lea     rcx, aWeCouldNotCrea_0; "We could not create the Event object fo"...
0x180021614  mov     rdx, [rsi]
0x180021617  mov     r8d, edi
0x18002161a  call    WiaTrace_Trace
0x18002161f  mov     r9d, 1; int
0x180021625  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x18002162a  mov     r8, rbp; int
0x18002162d  call    WiaTrace_ProcessTrace_Ex
0x180021632  test    edi, edi
0x180021634  jle     loc_180021873
0x18002163a  movzx   edi, di
0x18002163d  or      edi, 80070000h
0x180021643  jmp     loc_180021871
0x180021648  mov     rax, [rsi]
0x18002164b  lea     r8, aDeviceevent0xX_5; "DeviceEvent [0x%X] for (%ws) successful"...
0x180021652  xor     edx, edx
0x180021654  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x180021659  xor     ecx, ecx
0x18002165b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x180021660  mov     rdx, rax; char *
0x180021663  mov     rcx, rbp; char *
0x180021666  mov     rbx, rax
0x180021669  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18002166e  mov     rcx, rbx; this
0x180021671  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180021676  mov     rax, [rsi]
0x180021679  lea     r8, aDeviceevent0xX_5; "DeviceEvent [0x%X] for (%ws) successful"...
0x180021680  mov     r9, [r15]
0x180021683  xor     edx, edx
0x180021685  xor     ecx, ecx
0x180021687  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x18002168c  call    WiaTrace_TraceWithSubCompTraceLevel
0x180021691  mov     r9d, 4; int
0x180021697  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x18002169c  mov     r8, rbp; int
0x18002169f  call    WiaTrace_ProcessTrace_Ex
0x1800216a4  mov     rcx, [r15]; hEvent
0x1800216a7  lea     rax, [rcx+1]
0x1800216ab  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800216b1  jz      loc_1800214AF
0x1800216b7  call    cs:__imp_ResetEvent
0x1800216bd  mov     rax, [rsi]
0x1800216c0  lea     r8, aDeviceevent0xX_7; "DeviceEvent [0x%X] for (%ws) reset to b"...
0x1800216c7  mov     r9, [r15]
0x1800216ca  xor     edx, edx
0x1800216cc  xor     ecx, ecx
0x1800216ce  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x1800216d3  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800216d8  mov     rdx, rax; char *
0x1800216db  mov     rcx, rbp; char *
0x1800216de  mov     rbx, rax
0x1800216e1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800216e6  mov     rcx, rbx; this
0x1800216e9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800216ee  mov     rax, [rsi]
0x1800216f1  lea     r8, aDeviceevent0xX_7; "DeviceEvent [0x%X] for (%ws) reset to b"...
0x1800216f8  mov     r9, [r15]
0x1800216fb  xor     edx, edx
0x1800216fd  xor     ecx, ecx
0x1800216ff  mov     qword ptr [rsp+68h+dwDesiredAccess], rax
0x180021704  call    WiaTrace_TraceWithSubCompTraceLevel
0x180021709  mov     r9d, 4; int
0x18002170f  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x180021714  mov     r8, rbp; int
0x180021717  call    WiaTrace_ProcessTrace_Ex
0x18002171c  lea     r13, [r14+0FA8h]
0x180021723  mov     rax, [r13+0]
0x180021727  inc     rax
0x18002172a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180021730  jnz     short loc_1800217AE
0x180021732  call    cs:__imp_GetCurrentProcess
0x180021738  mov     rdi, [r15]
0x18002173b  mov     rbx, rax
0x18002173e  call    cs:__imp_GetCurrentProcess
0x180021744  mov     [rsp+68h+dwOptions], 2; dwOptions
0x18002174c  mov     r9, r13; lpTargetHandle
0x18002174f  mov     rcx, rax; hSourceProcessHandle
0x180021752  mov     [rsp+68h+bInheritHandle], 0; bInheritHandle
0x18002175a  mov     r8, rbx; hTargetProcessHandle
0x18002175d  mov     [rsp+68h+dwDesiredAccess], 0; dwDesiredAccess
0x180021765  mov     rdx, rdi; hSourceHandle
0x180021768  call    cs:__imp_DuplicateHandle
0x18002176e  test    eax, eax
0x180021770  jnz     short loc_1800217AE
0x180021772  call    cs:__imp_GetLastError
0x180021778  mov     rdx, [rsi]
0x18002177b  lea     rcx, aWeCouldNotCrea; "We could not create the Event object fo"...
0x180021782  mov     r8d, eax
0x180021785  mov     edi, eax
0x180021787  call    WiaTrace_TraceLog
0x18002178c  mov     rdx, rax; char *
0x18002178f  mov     rcx, rbp; char *
0x180021792  mov     rbx, rax
0x180021795  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18002179a  mov     rcx, rbx; this
0x18002179d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800217a2  lea     rcx, aWeCouldNotCrea; "We could not create the Event object fo"...
0x1800217a9  jmp     loc_180021614
0x1800217ae  mov     rax, [r14]
0x1800217b1  mov     rcx, r14
0x1800217b4  mov     rdx, [r13+0]
0x1800217b8  mov     rax, [rax+128h]
0x1800217bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217c4  xor     edi, edi
0x1800217c6  cmp     eax, 80004001h
0x1800217cb  cmovnz  edi, eax
0x1800217ce  test    edi, edi
0x1800217d0  jns     loc_1800214AF
0x1800217d6  mov     rdx, [rsi]
0x1800217d9  lea     rcx, aUsdForWsRefuse; "USD for (%ws) refused to take event han"...
0x1800217e0  mov     r8d, edi
0x1800217e3  call    WiaTrace_TraceLog
0x1800217e8  mov     rdx, rax; char *
0x1800217eb  mov     rcx, rbp; char *
0x1800217ee  mov     rbx, rax
0x1800217f1  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x1800217f6  mov     rcx, rbx; this
0x1800217f9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800217fe  mov     rdx, [rsi]
0x180021801  lea     rcx, aUsdForWsRefuse; "USD for (%ws) refused to take event han"...
0x180021808  mov     r8d, edi
0x18002180b  call    WiaTrace_Trace
0x180021810  mov     r9d, 1; int
0x180021816  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x18002181b  mov     r8, rbp; int
0x18002181e  call    WiaTrace_ProcessTrace_Ex
0x180021823  jmp     short loc_180021875
0x180021825  mov     rdx, [rsi]
0x180021828  lea     rcx, aWeCouldNotSche; "We could not schedule the notification "...
0x18002182f  call    WiaTrace_TraceLog
0x180021834  mov     rdx, rax; char *
0x180021837  mov     rcx, rbp; char *
0x18002183a  mov     rbx, rax
0x18002183d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x180021842  mov     rcx, rbx; this
0x180021845  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18002184a  mov     rdx, [rsi]
0x18002184d  lea     rcx, aWeCouldNotSche; "We could not schedule the notification "...
0x180021854  call    WiaTrace_Trace
0x180021859  mov     r9d, 1; int
0x18002185f  mov     qword ptr [rsp+68h+dwDesiredAccess], rax; lpMem
0x180021864  mov     r8, rbp; int
0x180021867  call    WiaTrace_ProcessTrace_Ex
0x18002186c  mov     edi, 8000FFFFh
0x180021871  test    edi, edi
  ... truncated ...
```
