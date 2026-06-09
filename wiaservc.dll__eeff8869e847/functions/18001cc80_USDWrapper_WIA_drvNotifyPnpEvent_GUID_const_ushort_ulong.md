# USDWrapper::WIA_drvNotifyPnpEvent(_GUID const *,ushort *,ulong)

- ea: `0x18001cc80`
- end: `0x18001d218`
- name: `?WIA_drvNotifyPnpEvent@USDWrapper@@UEAAJPEBU_GUID@@PEAGK@Z`
- size: `1432`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this, const struct _GUID *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18001cc80`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001d1a9`
- `KERNEL32!LeaveCriticalSection` at `0x18001d1a9`
- `KERNEL32!GetLastError` at `0x18001cd81`
- `KERNEL32!GetLastError` at `0x18001cdab`
- `KERNEL32!GetLastError` at `0x18001cde4`
- `KERNEL32!GetLastError` at `0x18001ce0e`
- `KERNEL32!GetLastError` at `0x18001d0eb`
- `KERNEL32!GetLastError` at `0x18001d115`
- `KERNEL32!GetLastError` at `0x18001d14e`
- `KERNEL32!GetLastError` at `0x18001d178`
- `KERNEL32!GetLastError` at `0x18001cd81`
- `KERNEL32!GetLastError` at `0x18001cdab`
- `KERNEL32!GetLastError` at `0x18001cde4`
- `KERNEL32!GetLastError` at `0x18001ce0e`
- `KERNEL32!GetLastError` at `0x18001d0eb`
- `KERNEL32!GetLastError` at `0x18001d115`
- `KERNEL32!GetLastError` at `0x18001d14e`
- `KERNEL32!GetLastError` at `0x18001d178`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18001d0e1`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18001d144`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18001d0e1`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18001d144`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18001cd77`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18001cdda`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18001cd77`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18001cdda`

## string_xrefs

- `0x18001ce45`: `The WIA service is preparing to call IWiaMiniDrv::drvNotifyPnpEvent from the driver for (%ws) ...`
- `0x18001ce72`: `The WIA service is preparing to call IWiaMiniDrv::drvNotifyPnpEvent from the driver for (%ws) ...`
- `0x18001cec2`: `The WIA service is calling IWiaMiniDrv::drvNotifyPnpEvent from the driver (%ws) ...`
- `0x18001ceef`: `The WIA service is calling IWiaMiniDrv::drvNotifyPnpEvent from the driver (%ws) ...`
- `0x18001cf52`: `(%ws) completed IWiaMiniDrv::drvNotifyPnpEvent returning hr 0x%08.8X`
- `0x18001cf84`: `(%ws) completed IWiaMiniDrv::drvNotifyPnpEvent returning hr 0x%08.8X`
- `0x18001cfc0`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvNotifyPnpEvent`
- `0x18001cff0`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvNotifyPnpEvent`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvNotifyPnpEvent(
        USDWrapper *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v5; // rax
  int v6; // r12d
  HANDLE *v7; // r15
  char *v8; // rbx
  void *v9; // rdx
  void **v10; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  char *v13; // rbx
  void *v14; // rdx
  DWORD LastError; // eax
  void **v16; // rax
  void *v17; // rdx
  __int64 v18; // rcx
  char *v19; // rbx
  void *v20; // rdx
  DWORD v21; // eax
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
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
  char *v50; // rbx
  void *v51; // rdx
  DWORD v52; // eax
  void **v53; // rax
  void *v54; // rdx
  __int64 v55; // rcx
  char *v56; // rbx
  void *v57; // rdx
  DWORD v58; // eax
  void **v59; // rax
  void *v60; // rdx
  __int64 v61; // rcx
  char *v62; // rbx
  void *v63; // rdx
  void **v64; // rax
  void *v65; // rdx
  __int64 v66; // rcx
  LPVOID lpMem; // [rsp+20h] [rbp-68h]
  LPVOID lpMema; // [rsp+20h] [rbp-68h]
  int v70; // [rsp+34h] [rbp-54h]

  v5 = *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&WIA_EVENT_DEVICE_DISCONNECTED.Data1 == *(_QWORD *)&a2->Data1 )
    v5 = *(_QWORD *)WIA_EVENT_DEVICE_DISCONNECTED.Data4 - *(_QWORD *)a2->Data4;
  if ( v5 )
    v6 = (*(__int64 (__fastcall **)(USDWrapper *, __int64))(*(_QWORD *)this + 104LL))(this, 2);
  else
    v6 = 0;
  if ( v6 >= 0 && (*(unsigned int (__fastcall **)(USDWrapper *))(*(_QWORD *)this + 168LL))(this) )
  {
    v7 = (HANDLE *)((char *)this + 4120);
    if ( *((_QWORD *)this + 515) != -1 )
    {
      v8 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                     0,
                     0,
                     "Power management: disable system initiated sleep to call IWiaMiniDrv::drvNotifyPnPEvent for (%ws)...",
                     *((_QWORD *)this + 301));
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvNotifyPnpEvent", v8);
      WiaTrcLib::Free((WiaTrcLib *)v8, v9);
      v10 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "Power management: disable system initiated sleep to call IWiaMiniDrv::drvNotifyPnPEvent for (%ws)...",
                       *((_QWORD *)this + 301));
      WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 4, v10);
      if ( !PowerSetRequest(*v7, PowerRequestSystemRequired) )
      {
        GetLastError();
        v13 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestSystemRequired could not be set, GLE 0x%X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvNotifyPnpEvent", v13);
        WiaTrcLib::Free((WiaTrcLib *)v13, v14);
        LastError = GetLastError();
        v16 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestSystemRequired could not be set, GLE 0x%X",
                         LastError);
        WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 1, v16);
      }
      if ( !PowerSetRequest(*v7, PowerRequestExecutionRequired) )
      {
        GetLastError();
        v19 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestExecutionRequired could not be set, GLE 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvNotifyPnpEvent", v19);
        WiaTrcLib::Free((WiaTrcLib *)v19, v20);
        v21 = GetLastError();
        v22 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestExecutionRequired could not be set, GLE 0x%08X",
                         v21);
        WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 1, v22);
      }
    }
    v25 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "The WIA service is preparing to call IWiaMiniDrv::drvNotifyPnpEvent from the driver for (%ws) ...",
                    *((_QWORD *)this + 301));
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvNotifyPnpEvent", v25);
    WiaTrcLib::Free((WiaTrcLib *)v25, v26);
    v27 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "The WIA service is preparing to call IWiaMiniDrv::drvNotifyPnpEvent from the driver for (%ws) ...",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v29, v28, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 4, v27);
    v70 = CRIT_SECT::Lock((USDWrapper *)((char *)this + 4136));
    if ( *((_QWORD *)this + 457) )
    {
      v30 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "The WIA service is calling IWiaMiniDrv::drvNotifyPnpEvent from the driver (%ws) ...",
                      *((_QWORD *)this + 301));
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvNotifyPnpEvent", v30);
      WiaTrcLib::Free((WiaTrcLib *)v30, v31);
      v32 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "The WIA service is calling IWiaMiniDrv::drvNotifyPnpEvent from the driver (%ws) ...",
                       *((_QWORD *)this + 301));
      WiaTrace_ProcessTrace_Ex(v34, v33, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 4, v32);
      v6 = (*(__int64 (__fastcall **)(_QWORD, const struct _GUID *, unsigned __int16 *, _QWORD))(**((_QWORD **)this + 457)
                                                                                               + 144LL))(
             *((_QWORD *)this + 457),
             a2,
             a3,
             a4);
      LODWORD(lpMem) = v6;
      v35 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "(%ws) completed IWiaMiniDrv::drvNotifyPnpEvent returning hr 0x%08.8X",
                      *((_QWORD *)this + 301),
                      lpMem);
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvNotifyPnpEvent", v35);
      WiaTrcLib::Free((WiaTrcLib *)v35, v36);
      LODWORD(lpMema) = v6;
      v37 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "(%ws) completed IWiaMiniDrv::drvNotifyPnpEvent returning hr 0x%08.8X",
                       *((_QWORD *)this + 301),
                       lpMema);
      WiaTrace_ProcessTrace_Ex(v39, v38, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 4, v37);
    }
    else
    {
      v40 = (char *)WiaTrace_TraceLog("The driver for (%ws) was unexpectedly unloaded");
      WriteDbgTraceErrorWI("USDWrapper::WIA_drvNotifyPnpEvent", v40);
      WiaTrcLib::Free((WiaTrcLib *)v40, v41);
      v42 = (void **)WiaTrace_Trace("The driver for (%ws) was unexpectedly unloaded", *((_QWORD *)this + 301));
      WiaTrace_ProcessTrace_Ex(v44, v43, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 1, v42);
      v6 = -2145320955;
    }
    if ( *v7 != (HANDLE)-1LL )
    {
      v45 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Power management: restore system initiated sleep...");
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvNotifyPnpEvent", v45);
      WiaTrcLib::Free((WiaTrcLib *)v45, v46);
      v47 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Power management: restore system initiated sleep...");
      WiaTrace_ProcessTrace_Ex(v49, v48, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 4, v47);
      if ( !PowerClearRequest(*v7, PowerRequestSystemRequired) )
      {
        GetLastError();
        v50 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestSystemRequired could not be cleared, GLE 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvNotifyPnpEvent", v50);
        WiaTrcLib::Free((WiaTrcLib *)v50, v51);
        v52 = GetLastError();
        v53 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestSystemRequired could not be cleared, GLE 0x%08X",
                         v52);
        WiaTrace_ProcessTrace_Ex(v55, v54, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 1, v53);
      }
      if ( !PowerClearRequest(*v7, PowerRequestExecutionRequired) )
      {
        GetLastError();
        v56 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestExecutionRequired could not be cleared, 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvNotifyPnpEvent", v56);
        WiaTrcLib::Free((WiaTrcLib *)v56, v57);
        v58 = GetLastError();
        v59 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestExecutionRequired could not be cleared, 0x%08X",
                         v58);
        WiaTrace_ProcessTrace_Ex(v61, v60, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 1, v59);
      }
    }
    if ( v70 )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4136));
  }
  else
  {
    v62 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvNotifyPnpEvent for (%ws) because the d"
                                    "river could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvNotifyPnpEvent", v62);
    WiaTrcLib::Free((WiaTrcLib *)v62, v63);
    v64 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvNotifyPnpEvent for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v66, v65, (void *)"USDWrapper::WIA_drvNotifyPnpEvent", 1, v64);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001cc80  mov     rax, rsp
0x18001cc83  mov     [rax+20h], r9d
0x18001cc87  mov     [rax+18h], r8
0x18001cc8b  mov     [rax+10h], rdx
0x18001cc8f  mov     [rax+8], rcx
0x18001cc93  push    rbx
0x18001cc94  push    rsi
0x18001cc95  push    rdi
0x18001cc96  push    r12
0x18001cc98  push    r13
0x18001cc9a  push    r15
0x18001cc9c  sub     rsp, 58h
0x18001cca0  mov     rsi, rcx
0x18001cca3  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data1
0x18001ccaa  sub     rax, [rdx]
0x18001ccad  jnz     short loc_18001CCBA
0x18001ccaf  mov     rax, qword ptr cs:WIA_EVENT_DEVICE_DISCONNECTED.Data4
0x18001ccb6  sub     rax, [rdx+8]
0x18001ccba  test    rax, rax
0x18001ccbd  jnz     short loc_18001CCC4
0x18001ccbf  xor     r12d, r12d
0x18001ccc2  jmp     short loc_18001CCD8
0x18001ccc4  mov     rax, [rcx]
0x18001ccc7  mov     edx, 2
0x18001cccc  mov     rax, [rax+68h]
0x18001ccd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccd5  mov     r12d, eax
0x18001ccd8  test    r12d, r12d
0x18001ccdb  js      loc_18001D1B1
0x18001cce1  mov     rcx, [rsi]
0x18001cce4  mov     rax, [rcx+0A8h]
0x18001cceb  mov     rcx, rsi
0x18001ccee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccf3  test    eax, eax
0x18001ccf5  jz      loc_18001D1B1
0x18001ccfb  lea     r15, [rsi+1018h]
0x18001cd02  mov     [rsp+88h+var_50], r15
0x18001cd07  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18001cd0b  jz      loc_18001CE37
0x18001cd11  mov     r9, [rsi+968h]
0x18001cd18  lea     r8, aPowerManagemen; "Power management: disable system initia"...
0x18001cd1f  xor     edx, edx
0x18001cd21  xor     ecx, ecx
0x18001cd23  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001cd28  mov     rbx, rax
0x18001cd2b  mov     rdx, rax; char *
0x18001cd2e  lea     rdi, aUsdwrapperWiaD_7; "USDWrapper::WIA_drvNotifyPnpEvent"
0x18001cd35  mov     rcx, rdi; char *
0x18001cd38  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001cd3d  mov     rcx, rbx; this
0x18001cd40  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001cd45  mov     r9, [rsi+968h]
0x18001cd4c  lea     r8, aPowerManagemen; "Power management: disable system initia"...
0x18001cd53  xor     edx, edx
0x18001cd55  xor     ecx, ecx
0x18001cd57  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001cd5c  mov     [rsp+88h+lpMem], rax; lpMem
0x18001cd61  mov     r9d, 4; int
0x18001cd67  mov     r8, rdi; int
0x18001cd6a  call    WiaTrace_ProcessTrace_Ex
0x18001cd6f  mov     edx, 1; RequestType
0x18001cd74  mov     rcx, [r15]; PowerRequest
0x18001cd77  call    cs:__imp_PowerSetRequest
0x18001cd7d  test    eax, eax
0x18001cd7f  jnz     short loc_18001CDD2
0x18001cd81  call    cs:__imp_GetLastError
0x18001cd87  mov     edx, eax
0x18001cd89  lea     rcx, aPowerManagemen_4; "Power management: the power request Pow"...
0x18001cd90  call    WiaTrace_TraceLog
0x18001cd95  mov     rbx, rax
0x18001cd98  mov     rdx, rax; char *
0x18001cd9b  mov     rcx, rdi; char *
0x18001cd9e  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001cda3  mov     rcx, rbx; this
0x18001cda6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001cdab  call    cs:__imp_GetLastError
0x18001cdb1  mov     edx, eax
0x18001cdb3  lea     rcx, aPowerManagemen_4; "Power management: the power request Pow"...
0x18001cdba  call    WiaTrace_Trace
0x18001cdbf  mov     [rsp+88h+lpMem], rax; lpMem
0x18001cdc4  mov     r9d, 1; int
0x18001cdca  mov     r8, rdi; int
0x18001cdcd  call    WiaTrace_ProcessTrace_Ex
0x18001cdd2  mov     edx, 3; RequestType
0x18001cdd7  mov     rcx, [r15]; PowerRequest
0x18001cdda  call    cs:__imp_PowerSetRequest
0x18001cde0  test    eax, eax
0x18001cde2  jnz     short loc_18001CE3E
0x18001cde4  call    cs:__imp_GetLastError
0x18001cdea  mov     edx, eax
0x18001cdec  lea     rcx, aPowerManagemen_1; "Power management: the power request Pow"...
0x18001cdf3  call    WiaTrace_TraceLog
0x18001cdf8  mov     rbx, rax
0x18001cdfb  mov     rdx, rax; char *
0x18001cdfe  mov     rcx, rdi; char *
0x18001ce01  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001ce06  mov     rcx, rbx; this
0x18001ce09  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001ce0e  call    cs:__imp_GetLastError
0x18001ce14  mov     edx, eax
0x18001ce16  lea     rcx, aPowerManagemen_1; "Power management: the power request Pow"...
0x18001ce1d  call    WiaTrace_Trace
0x18001ce22  mov     [rsp+88h+lpMem], rax; lpMem
0x18001ce27  mov     r9d, 1; int
0x18001ce2d  mov     r8, rdi; int
0x18001ce30  call    WiaTrace_ProcessTrace_Ex
0x18001ce35  jmp     short loc_18001CE3E
0x18001ce37  lea     rdi, aUsdwrapperWiaD_7; "USDWrapper::WIA_drvNotifyPnpEvent"
0x18001ce3e  mov     r9, [rsi+968h]
0x18001ce45  lea     r8, aTheWiaServiceI_1; "The WIA service is preparing to call IW"...
0x18001ce4c  xor     edx, edx
0x18001ce4e  xor     ecx, ecx
0x18001ce50  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001ce55  mov     rbx, rax
0x18001ce58  mov     rdx, rax; char *
0x18001ce5b  mov     rcx, rdi; char *
0x18001ce5e  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001ce63  mov     rcx, rbx; this
0x18001ce66  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001ce6b  mov     r9, [rsi+968h]
0x18001ce72  lea     r8, aTheWiaServiceI_1; "The WIA service is preparing to call IW"...
0x18001ce79  xor     edx, edx
0x18001ce7b  xor     ecx, ecx
0x18001ce7d  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001ce82  mov     [rsp+88h+lpMem], rax; lpMem
0x18001ce87  mov     r9d, 4; int
0x18001ce8d  mov     r8, rdi; int
0x18001ce90  call    WiaTrace_ProcessTrace_Ex
0x18001ce95  lea     r13, [rsi+1028h]
0x18001ce9c  mov     [rsp+88h+var_48], r13
0x18001cea1  mov     rcx, r13; this
0x18001cea4  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18001cea9  mov     [rsp+88h+var_54], eax
0x18001cead  cmp     qword ptr [rsi+0E48h], 0
0x18001ceb5  jz      loc_18001D031
0x18001cebb  mov     r9, [rsi+968h]
0x18001cec2  lea     r8, aTheWiaServiceI_0; "The WIA service is calling IWiaMiniDrv:"...
0x18001cec9  xor     edx, edx
0x18001cecb  xor     ecx, ecx
0x18001cecd  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001ced2  mov     rbx, rax
0x18001ced5  mov     rdx, rax; char *
0x18001ced8  mov     rcx, rdi; char *
0x18001cedb  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001cee0  mov     rcx, rbx; this
0x18001cee3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001cee8  mov     r9, [rsi+968h]
0x18001ceef  lea     r8, aTheWiaServiceI_0; "The WIA service is calling IWiaMiniDrv:"...
0x18001cef6  xor     edx, edx
0x18001cef8  xor     ecx, ecx
0x18001cefa  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001ceff  mov     [rsp+88h+lpMem], rax; lpMem
0x18001cf04  mov     r9d, 4; int
0x18001cf0a  mov     r8, rdi; int
0x18001cf0d  call    WiaTrace_ProcessTrace_Ex
0x18001cf12  mov     rcx, [rsi+0E48h]
0x18001cf19  mov     rax, [rcx]
0x18001cf1c  mov     r9d, [rsp+88h+arg_18]
0x18001cf24  mov     r8, [rsp+88h+arg_10]
0x18001cf2c  mov     rdx, [rsp+88h+arg_8]
0x18001cf34  mov     rax, [rax+90h]
0x18001cf3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf40  mov     r12d, eax
0x18001cf43  mov     [rsp+88h+var_58], eax
0x18001cf47  mov     dword ptr [rsp+88h+lpMem], eax
0x18001cf4b  mov     r9, [rsi+968h]
0x18001cf52  lea     r8, aWsCompletedIwi; "(%ws) completed IWiaMiniDrv::drvNotifyP"...
0x18001cf59  xor     edx, edx
0x18001cf5b  xor     ecx, ecx
0x18001cf5d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001cf62  mov     rbx, rax
0x18001cf65  mov     rdx, rax; char *
0x18001cf68  mov     rcx, rdi; char *
0x18001cf6b  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001cf70  mov     rcx, rbx; this
0x18001cf73  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001cf78  mov     dword ptr [rsp+88h+lpMem], r12d
0x18001cf7d  mov     r9, [rsi+968h]
0x18001cf84  lea     r8, aWsCompletedIwi; "(%ws) completed IWiaMiniDrv::drvNotifyP"...
0x18001cf8b  xor     edx, edx
0x18001cf8d  xor     ecx, ecx
0x18001cf8f  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001cf94  mov     [rsp+88h+lpMem], rax; lpMem
0x18001cf99  mov     r9d, 4; int
0x18001cf9f  mov     r8, rdi; int
0x18001cfa2  call    WiaTrace_ProcessTrace_Ex
0x18001cfa7  jmp     loc_18001D086
0x18001cfac  mov     esi, eax
0x18001cfae  mov     r8d, eax
0x18001cfb1  mov     rdi, [rsp+88h+arg_0]
0x18001cfb9  mov     rdx, [rdi+968h]
0x18001cfc0  lea     rcx, aTheDriverForWs_11; "The driver for (%ws) threw an exception"...
0x18001cfc7  call    WiaTrace_TraceLog
0x18001cfcc  mov     rbx, rax
0x18001cfcf  mov     rdx, rax; char *
0x18001cfd2  lea     rcx, aUsdwrapperWiaD_7; "USDWrapper::WIA_drvNotifyPnpEvent"
0x18001cfd9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001cfde  mov     rcx, rbx; this
0x18001cfe1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001cfe6  mov     r8d, esi
0x18001cfe9  mov     rdx, [rdi+968h]
0x18001cff0  lea     rcx, aTheDriverForWs_11; "The driver for (%ws) threw an exception"...
0x18001cff7  call    WiaTrace_Trace
0x18001cffc  mov     [rsp+88h+lpMem], rax; lpMem
0x18001d001  mov     r9d, 1; int
0x18001d007  lea     r8, aUsdwrapperWiaD_7; "USDWrapper::WIA_drvNotifyPnpEvent"
0x18001d00e  call    WiaTrace_ProcessTrace_Ex
0x18001d013  mov     r12d, 8021000Eh
0x18001d019  mov     [rsp+88h+var_58], r12d
0x18001d01e  lea     rdi, aUsdwrapperWiaD_7; "USDWrapper::WIA_drvNotifyPnpEvent"
0x18001d025  mov     r15, [rsp+88h+var_50]
0x18001d02a  mov     r13, [rsp+88h+var_48]
0x18001d02f  jmp     short loc_18001D086
0x18001d031  mov     rdx, [rsi+968h]
0x18001d038  lea     rcx, aTheDriverForWs_13; "The driver for (%ws) was unexpectedly u"...
0x18001d03f  call    WiaTrace_TraceLog
0x18001d044  mov     rbx, rax
0x18001d047  mov     rdx, rax; char *
0x18001d04a  mov     rcx, rdi; char *
0x18001d04d  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001d052  mov     rcx, rbx; this
0x18001d055  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001d05a  mov     rdx, [rsi+968h]
0x18001d061  lea     rcx, aTheDriverForWs_13; "The driver for (%ws) was unexpectedly u"...
0x18001d068  call    WiaTrace_Trace
0x18001d06d  mov     [rsp+88h+lpMem], rax; lpMem
0x18001d072  mov     r9d, 1; int
0x18001d078  mov     r8, rdi; int
0x18001d07b  call    WiaTrace_ProcessTrace_Ex
0x18001d080  mov     r12d, 80210005h
0x18001d086  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18001d08a  jz      loc_18001D19F
0x18001d090  lea     r8, aPowerManagemen_3; "Power management: restore system initia"...
0x18001d097  xor     edx, edx
0x18001d099  xor     ecx, ecx
0x18001d09b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001d0a0  mov     rbx, rax
0x18001d0a3  mov     rdx, rax; char *
0x18001d0a6  mov     rcx, rdi; char *
0x18001d0a9  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001d0ae  mov     rcx, rbx; this
0x18001d0b1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001d0b6  lea     r8, aPowerManagemen_3; "Power management: restore system initia"...
0x18001d0bd  xor     edx, edx
0x18001d0bf  xor     ecx, ecx
0x18001d0c1  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001d0c6  mov     [rsp+88h+lpMem], rax; lpMem
0x18001d0cb  mov     r9d, 4; int
0x18001d0d1  mov     r8, rdi; int
0x18001d0d4  call    WiaTrace_ProcessTrace_Ex
0x18001d0d9  mov     edx, 1; RequestType
0x18001d0de  mov     rcx, [r15]; PowerRequest
0x18001d0e1  call    cs:__imp_PowerClearRequest
0x18001d0e7  test    eax, eax
0x18001d0e9  jnz     short loc_18001D13C
0x18001d0eb  call    cs:__imp_GetLastError
0x18001d0f1  mov     edx, eax
0x18001d0f3  lea     rcx, aPowerManagemen_6; "Power management: the power request Pow"...
0x18001d0fa  call    WiaTrace_TraceLog
0x18001d0ff  mov     rbx, rax
0x18001d102  mov     rdx, rax; char *
0x18001d105  mov     rcx, rdi; char *
0x18001d108  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001d10d  mov     rcx, rbx; this
0x18001d110  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001d115  call    cs:__imp_GetLastError
0x18001d11b  mov     edx, eax
0x18001d11d  lea     rcx, aPowerManagemen_6; "Power management: the power request Pow"...
0x18001d124  call    WiaTrace_Trace
0x18001d129  mov     [rsp+88h+lpMem], rax; lpMem
0x18001d12e  mov     r9d, 1; int
0x18001d134  mov     r8, rdi; int
0x18001d137  call    WiaTrace_ProcessTrace_Ex
0x18001d13c  mov     edx, 3; RequestType
0x18001d141  mov     rcx, [r15]; PowerRequest
0x18001d144  call    cs:__imp_PowerClearRequest
0x18001d14a  test    eax, eax
0x18001d14c  jnz     short loc_18001D19F
0x18001d14e  call    cs:__imp_GetLastError
0x18001d154  mov     edx, eax
0x18001d156  lea     rcx, aPowerManagemen_0; "Power management: the power request Pow"...
0x18001d15d  call    WiaTrace_TraceLog
0x18001d162  mov     rbx, rax
0x18001d165  mov     rdx, rax; char *
0x18001d168  mov     rcx, rdi; char *
0x18001d16b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001d170  mov     rcx, rbx; this
0x18001d173  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001d178  call    cs:__imp_GetLastError
0x18001d17e  mov     edx, eax
0x18001d180  lea     rcx, aPowerManagemen_0; "Power management: the power request Pow"...
0x18001d187  call    WiaTrace_Trace
0x18001d18c  mov     [rsp+88h+lpMem], rax; lpMem
0x18001d191  mov     r9d, 1; int
0x18001d197  mov     r8, rdi; int
0x18001d19a  call    WiaTrace_ProcessTrace_Ex
0x18001d19f  cmp     [rsp+88h+var_54], 0
0x18001d1a4  jz      short loc_18001D207
0x18001d1a6  mov     rcx, r13; lpCriticalSection
0x18001d1a9  call    cs:__imp_LeaveCriticalSection
  ... truncated ...
```
