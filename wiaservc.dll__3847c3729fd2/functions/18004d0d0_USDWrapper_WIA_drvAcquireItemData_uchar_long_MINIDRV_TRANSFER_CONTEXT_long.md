# USDWrapper::WIA_drvAcquireItemData(uchar *,long,_MINIDRV_TRANSFER_CONTEXT *,long *)

- ea: `0x18004d0d0`
- end: `0x18004d673`
- name: `?WIA_drvAcquireItemData@USDWrapper@@UEAAJPEAEJPEAU_MINIDRV_TRANSFER_CONTEXT@@PEAJ@Z`
- size: `1443`
- prototype: `__int64 __fastcall(USDWrapper *__hidden this, unsigned __int8 *, int, struct _MINIDRV_TRANSFER_CONTEXT *, int *)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000ac34`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18004bf00`
- `0x18004d0d0`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18004d604`
- `KERNEL32!LeaveCriticalSection` at `0x18004d604`
- `KERNEL32!GetLastError` at `0x18004d195`
- `KERNEL32!GetLastError` at `0x18004d1bf`
- `KERNEL32!GetLastError` at `0x18004d1f8`
- `KERNEL32!GetLastError` at `0x18004d222`
- `KERNEL32!GetLastError` at `0x18004d544`
- `KERNEL32!GetLastError` at `0x18004d56e`
- `KERNEL32!GetLastError` at `0x18004d5a7`
- `KERNEL32!GetLastError` at `0x18004d5d1`
- `KERNEL32!GetLastError` at `0x18004d195`
- `KERNEL32!GetLastError` at `0x18004d1bf`
- `KERNEL32!GetLastError` at `0x18004d1f8`
- `KERNEL32!GetLastError` at `0x18004d222`
- `KERNEL32!GetLastError` at `0x18004d544`
- `KERNEL32!GetLastError` at `0x18004d56e`
- `KERNEL32!GetLastError` at `0x18004d5a7`
- `KERNEL32!GetLastError` at `0x18004d5d1`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18004d53a`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18004d59d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18004d53a`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerClearRequest` at `0x18004d59d`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18004d18b`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18004d1ee`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18004d18b`
- `api-ms-win-core-kernel32-legacy-l1-1-1!PowerSetRequest` at `0x18004d1ee`

## string_xrefs

- `0x18004d2f0`: `The WIA service is calling IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...`
- `0x18004d31f`: `The WIA service is calling IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...`
- `0x18004d26f`: `The WIA service is preparing to call IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...`
- `0x18004d29e`: `The WIA service is preparing to call IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...`
- `0x18004d401`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvAcquireItemData`
- `0x18004d431`: `The driver for (%ws) threw an exception (0x%08X) when the WIA service called IWiaMiniDrv::drvAcquireItemData`
- `0x18004d391`: `(%ws) completed IWiaMiniDrv::drvAcquireItemData on item (%p) returning hr 0x%08.8X`
- `0x18004d3c5`: `(%ws) completed IWiaMiniDrv::drvAcquireItemData on item (%p) returning hr 0x%08.8X`

## pseudocode

```c
__int64 __fastcall USDWrapper::WIA_drvAcquireItemData(
        USDWrapper *this,
        unsigned __int8 *a2,
        unsigned int a3,
        struct _MINIDRV_TRANSFER_CONTEXT *a4,
        int *a5)
{
  int v6; // r13d
  HANDLE *v7; // r15
  char *v8; // rbx
  void *v9; // rdx
  void **lpMem; // rax
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
  USDWrapper **v25; // r12
  unsigned __int8 *v26; // r13
  char *v27; // rbx
  void *v28; // rdx
  void **v29; // rax
  void *v30; // rdx
  __int64 v31; // rcx
  char *v32; // rbx
  void *v33; // rdx
  void **v34; // rax
  void *v35; // rdx
  __int64 v36; // rcx
  unsigned __int8 *v37; // rsi
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
  char *v48; // rbx
  void *v49; // rdx
  void **v50; // rax
  void *v51; // rdx
  __int64 v52; // rcx
  char *v53; // rbx
  void *v54; // rdx
  DWORD v55; // eax
  void **v56; // rax
  void *v57; // rdx
  __int64 v58; // rcx
  char *v59; // rbx
  void *v60; // rdx
  DWORD v61; // eax
  void **v62; // rax
  void *v63; // rdx
  __int64 v64; // rcx
  char *v65; // rbx
  void *v66; // rdx
  void **v67; // rax
  void *v68; // rdx
  __int64 v69; // rcx
  int v71; // [rsp+28h] [rbp-60h]
  __int64 v72; // [rsp+28h] [rbp-60h]
  LPCRITICAL_SECTION v73[3]; // [rsp+30h] [rbp-58h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+48h] [rbp-40h]
  USDWrapper *v75; // [rsp+90h] [rbp+8h] BYREF
  unsigned __int8 *v76; // [rsp+98h] [rbp+10h]
  unsigned int v77; // [rsp+A0h] [rbp+18h]
  struct _MINIDRV_TRANSFER_CONTEXT *v78; // [rsp+A8h] [rbp+20h]

  v78 = a4;
  v77 = a3;
  v76 = a2;
  v75 = this;
  v6 = (*(__int64 (__fastcall **)(USDWrapper *, __int64))(*(_QWORD *)this + 104LL))(this, 2);
  if ( v6 < 0 )
  {
    v65 = (char *)WiaTrace_TraceLog("We failed to make the call to IWiaMiniDrv::drvAcquireItemData for (%ws) because the "
                                    "driver could not be loaded");
    WriteDbgTraceErrorWI("USDWrapper::WIA_drvAcquireItemData", v65);
    WiaTrcLib::Free((WiaTrcLib *)v65, v66);
    v67 = (void **)WiaTrace_Trace(
                     "We failed to make the call to IWiaMiniDrv::drvAcquireItemData for (%ws) because the driver could not be loaded",
                     *((_QWORD *)this + 301));
    WiaTrace_ProcessTrace_Ex(v69, v68, (void *)"USDWrapper::WIA_drvAcquireItemData", 1, v67);
  }
  else
  {
    v7 = (HANDLE *)((char *)this + 4120);
    v73[2] = (LPCRITICAL_SECTION)((char *)this + 4120);
    if ( *((_QWORD *)this + 515) != -1 )
    {
      v8 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                     0,
                     0,
                     "Power management: disable system initiated sleep to call IWiaMiniDrv::drvAcquireItemData for (%ws)...",
                     *((_QWORD *)this + 301));
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvAcquireItemData", v8);
      WiaTrcLib::Free((WiaTrcLib *)v8, v9);
      lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         0,
                         0,
                         "Power management: disable system initiated sleep to call IWiaMiniDrv::drvAcquireItemData for (%ws)...",
                         *((_QWORD *)this + 301));
      WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"USDWrapper::WIA_drvAcquireItemData", 4, lpMem);
      if ( !PowerSetRequest(*v7, PowerRequestSystemRequired) )
      {
        GetLastError();
        v13 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestSystemRequired could not be set, GLE 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvAcquireItemData", v13);
        WiaTrcLib::Free((WiaTrcLib *)v13, v14);
        LastError = GetLastError();
        v16 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestSystemRequired could not be set, GLE 0x%08X",
                         LastError);
        WiaTrace_ProcessTrace_Ex(v18, v17, (void *)"USDWrapper::WIA_drvAcquireItemData", 1, v16);
      }
      if ( !PowerSetRequest(*v7, PowerRequestExecutionRequired) )
      {
        GetLastError();
        v19 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestExecutionRequired could not be set, GLE 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvAcquireItemData", v19);
        WiaTrcLib::Free((WiaTrcLib *)v19, v20);
        v21 = GetLastError();
        v22 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestExecutionRequired could not be set, GLE 0x%08X",
                         v21);
        WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"USDWrapper::WIA_drvAcquireItemData", 1, v22);
      }
    }
    v25 = (USDWrapper **)((char *)this + 2408);
    v73[1] = (LPCRITICAL_SECTION)((char *)this + 2408);
    v26 = v76;
    v27 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0,
                    0,
                    "The WIA service is preparing to call IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...",
                    *((_QWORD *)this + 301),
                    v76);
    WriteDbgTraceInfoWI("USDWrapper::WIA_drvAcquireItemData", v27);
    WiaTrcLib::Free((WiaTrcLib *)v27, v28);
    v29 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0,
                     0,
                     "The WIA service is preparing to call IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...",
                     *((_QWORD *)this + 301),
                     v26);
    WiaTrace_ProcessTrace_Ex(v31, v30, (void *)"USDWrapper::WIA_drvAcquireItemData", 4, v29);
    lpCriticalSection = (LPCRITICAL_SECTION)((char *)this + 4184);
    HIDWORD(v73[0]) = CRIT_SECT::Lock((USDWrapper *)((char *)this + 4184));
    if ( *((_QWORD *)this + 457) )
    {
      v32 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "The WIA service is calling IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...",
                      *v25,
                      v26);
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvAcquireItemData", v32);
      WiaTrcLib::Free((WiaTrcLib *)v32, v33);
      v34 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "The WIA service is calling IWiaMiniDrv::drvAcquireItemData from driver for (%ws) on item (%p)...",
                       *v25,
                       v26);
      WiaTrace_ProcessTrace_Ex(v36, v35, (void *)"USDWrapper::WIA_drvAcquireItemData", 4, v34);
      v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int8 *, _QWORD, struct _MINIDRV_TRANSFER_CONTEXT *, int *))(**((_QWORD **)this + 457) + 32LL))(
             *((_QWORD *)this + 457),
             v26,
             v77,
             v78,
             a5);
      LODWORD(v73[0]) = v6;
      v71 = v6;
      v37 = v76;
      v38 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      0,
                      0,
                      "(%ws) completed IWiaMiniDrv::drvAcquireItemData on item (%p) returning hr 0x%08.8X",
                      *v25,
                      v76,
                      v71,
                      v73[0]);
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvAcquireItemData", v38);
      WiaTrcLib::Free((WiaTrcLib *)v38, v39);
      LODWORD(v72) = v6;
      v40 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       0,
                       0,
                       "(%ws) completed IWiaMiniDrv::drvAcquireItemData on item (%p) returning hr 0x%08.8X",
                       *v25,
                       v37,
                       v72);
      WiaTrace_ProcessTrace_Ex(v42, v41, (void *)"USDWrapper::WIA_drvAcquireItemData", 4, v40);
      v75 = *v25;
      WiaServiceTelemetry::WiaScanCompleted<unsigned short const *,long &>(&v75, v73);
    }
    else
    {
      v43 = (char *)WiaTrace_TraceLog("The driver for (%ws) was unexpectedly unloaded");
      WriteDbgTraceErrorWI("USDWrapper::WIA_drvAcquireItemData", v43);
      WiaTrcLib::Free((WiaTrcLib *)v43, v44);
      v45 = (void **)WiaTrace_Trace("The driver for (%ws) was unexpectedly unloaded", *v25);
      WiaTrace_ProcessTrace_Ex(v47, v46, (void *)"USDWrapper::WIA_drvAcquireItemData", 1, v45);
      v6 = -2145320955;
    }
    if ( *v7 != (HANDLE)-1LL )
    {
      v48 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Power management: restore system initiated sleep...");
      WriteDbgTraceInfoWI("USDWrapper::WIA_drvAcquireItemData", v48);
      WiaTrcLib::Free((WiaTrcLib *)v48, v49);
      v50 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Power management: restore system initiated sleep...");
      WiaTrace_ProcessTrace_Ex(v52, v51, (void *)"USDWrapper::WIA_drvAcquireItemData", 4, v50);
      if ( !PowerClearRequest(*v7, PowerRequestSystemRequired) )
      {
        GetLastError();
        v53 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestSystemRequired could not be cleared, GLE 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvAcquireItemData", v53);
        WiaTrcLib::Free((WiaTrcLib *)v53, v54);
        v55 = GetLastError();
        v56 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestSystemRequired could not be cleared, GLE 0x%08X",
                         v55);
        WiaTrace_ProcessTrace_Ex(v58, v57, (void *)"USDWrapper::WIA_drvAcquireItemData", 1, v56);
      }
      if ( !PowerClearRequest(*v7, PowerRequestExecutionRequired) )
      {
        GetLastError();
        v59 = (char *)WiaTrace_TraceLog("Power management: the power request PowerRequestExecutionRequired could not be cleared, 0x%08X");
        WriteDbgTraceErrorWI("USDWrapper::WIA_drvAcquireItemData", v59);
        WiaTrcLib::Free((WiaTrcLib *)v59, v60);
        v61 = GetLastError();
        v62 = (void **)WiaTrace_Trace(
                         "Power management: the power request PowerRequestExecutionRequired could not be cleared, 0x%08X",
                         v61);
        WiaTrace_ProcessTrace_Ex(v64, v63, (void *)"USDWrapper::WIA_drvAcquireItemData", 1, v62);
      }
    }
    if ( HIDWORD(v73[0]) )
      LeaveCriticalSection(lpCriticalSection);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004d0d0  mov     rax, rsp
0x18004d0d3  mov     [rax+20h], r9
0x18004d0d7  mov     [rax+18h], r8d
0x18004d0db  mov     [rax+10h], rdx
0x18004d0df  mov     [rax+8], rcx
0x18004d0e3  push    rbx
0x18004d0e4  push    rsi
0x18004d0e5  push    rdi
0x18004d0e6  push    r12
0x18004d0e8  push    r13
0x18004d0ea  push    r15
0x18004d0ec  sub     rsp, 58h
0x18004d0f0  mov     rsi, rcx
0x18004d0f3  mov     rax, [rcx]
0x18004d0f6  mov     edx, 2
0x18004d0fb  mov     rax, [rax+68h]
0x18004d0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d104  mov     r13d, eax
0x18004d107  test    eax, eax
0x18004d109  js      loc_18004D60C
0x18004d10f  lea     r15, [rsi+1018h]
0x18004d116  mov     [rsp+88h+var_48], r15
0x18004d11b  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18004d11f  jz      loc_18004D24B
0x18004d125  mov     r9, [rsi+968h]
0x18004d12c  lea     r8, aPowerManagemen_2; "Power management: disable system initia"...
0x18004d133  xor     edx, edx
0x18004d135  xor     ecx, ecx
0x18004d137  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004d13c  mov     rbx, rax
0x18004d13f  mov     rdx, rax; char *
0x18004d142  lea     rdi, aUsdwrapperWiaD_14; "USDWrapper::WIA_drvAcquireItemData"
0x18004d149  mov     rcx, rdi; char *
0x18004d14c  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004d151  mov     rcx, rbx; this
0x18004d154  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d159  mov     r9, [rsi+968h]
0x18004d160  lea     r8, aPowerManagemen_2; "Power management: disable system initia"...
0x18004d167  xor     edx, edx
0x18004d169  xor     ecx, ecx
0x18004d16b  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004d170  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d175  mov     r9d, 4; int
0x18004d17b  mov     r8, rdi; int
0x18004d17e  call    WiaTrace_ProcessTrace_Ex
0x18004d183  mov     edx, 1; RequestType
0x18004d188  mov     rcx, [r15]; PowerRequest
0x18004d18b  call    cs:__imp_PowerSetRequest
0x18004d191  test    eax, eax
0x18004d193  jnz     short loc_18004D1E6
0x18004d195  call    cs:__imp_GetLastError
0x18004d19b  mov     edx, eax
0x18004d19d  lea     rcx, aPowerManagemen_5; "Power management: the power request Pow"...
0x18004d1a4  call    WiaTrace_TraceLog
0x18004d1a9  mov     rbx, rax
0x18004d1ac  mov     rdx, rax; char *
0x18004d1af  mov     rcx, rdi; char *
0x18004d1b2  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d1b7  mov     rcx, rbx; this
0x18004d1ba  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d1bf  call    cs:__imp_GetLastError
0x18004d1c5  mov     edx, eax
0x18004d1c7  lea     rcx, aPowerManagemen_5; "Power management: the power request Pow"...
0x18004d1ce  call    WiaTrace_Trace
0x18004d1d3  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d1d8  mov     r9d, 1; int
0x18004d1de  mov     r8, rdi; int
0x18004d1e1  call    WiaTrace_ProcessTrace_Ex
0x18004d1e6  mov     edx, 3; RequestType
0x18004d1eb  mov     rcx, [r15]; PowerRequest
0x18004d1ee  call    cs:__imp_PowerSetRequest
0x18004d1f4  test    eax, eax
0x18004d1f6  jnz     short loc_18004D252
0x18004d1f8  call    cs:__imp_GetLastError
0x18004d1fe  mov     edx, eax
0x18004d200  lea     rcx, aPowerManagemen_1; "Power management: the power request Pow"...
0x18004d207  call    WiaTrace_TraceLog
0x18004d20c  mov     rbx, rax
0x18004d20f  mov     rdx, rax; char *
0x18004d212  mov     rcx, rdi; char *
0x18004d215  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d21a  mov     rcx, rbx; this
0x18004d21d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d222  call    cs:__imp_GetLastError
0x18004d228  mov     edx, eax
0x18004d22a  lea     rcx, aPowerManagemen_1; "Power management: the power request Pow"...
0x18004d231  call    WiaTrace_Trace
0x18004d236  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d23b  mov     r9d, 1; int
0x18004d241  mov     r8, rdi; int
0x18004d244  call    WiaTrace_ProcessTrace_Ex
0x18004d249  jmp     short loc_18004D252
0x18004d24b  lea     rdi, aUsdwrapperWiaD_14; "USDWrapper::WIA_drvAcquireItemData"
0x18004d252  lea     r12, [rsi+968h]
0x18004d259  mov     [rsp+88h+var_50], r12
0x18004d25e  mov     r13, [rsp+88h+arg_8]
0x18004d266  mov     [rsp+88h+lpMem], r13
0x18004d26b  mov     r9, [r12]
0x18004d26f  lea     r8, aTheWiaServiceI; "The WIA service is preparing to call IW"...
0x18004d276  xor     edx, edx
0x18004d278  xor     ecx, ecx
0x18004d27a  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004d27f  mov     rbx, rax
0x18004d282  mov     rdx, rax; char *
0x18004d285  mov     rcx, rdi; char *
0x18004d288  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004d28d  mov     rcx, rbx; this
0x18004d290  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d295  mov     [rsp+88h+lpMem], r13
0x18004d29a  mov     r9, [r12]
0x18004d29e  lea     r8, aTheWiaServiceI; "The WIA service is preparing to call IW"...
0x18004d2a5  xor     edx, edx
0x18004d2a7  xor     ecx, ecx
0x18004d2a9  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004d2ae  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d2b3  mov     r9d, 4; int
0x18004d2b9  mov     r8, rdi; int
0x18004d2bc  call    WiaTrace_ProcessTrace_Ex
0x18004d2c1  lea     rax, [rsi+1058h]
0x18004d2c8  mov     [rsp+88h+lpCriticalSection], rax
0x18004d2cd  mov     rcx, rax; this
0x18004d2d0  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18004d2d5  mov     [rsp+88h+var_54], eax
0x18004d2d9  cmp     qword ptr [rsi+0E48h], 0
0x18004d2e1  jz      loc_18004D490
0x18004d2e7  mov     [rsp+88h+lpMem], r13
0x18004d2ec  mov     r9, [r12]
0x18004d2f0  lea     r8, aTheWiaServiceI_4; "The WIA service is calling IWiaMiniDrv:"...
0x18004d2f7  xor     edx, edx
0x18004d2f9  xor     ecx, ecx
0x18004d2fb  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004d300  mov     rbx, rax
0x18004d303  mov     rdx, rax; char *
0x18004d306  mov     rcx, rdi; char *
0x18004d309  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004d30e  mov     rcx, rbx; this
0x18004d311  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d316  mov     [rsp+88h+lpMem], r13
0x18004d31b  mov     r9, [r12]
0x18004d31f  lea     r8, aTheWiaServiceI_4; "The WIA service is calling IWiaMiniDrv:"...
0x18004d326  xor     edx, edx
0x18004d328  xor     ecx, ecx
0x18004d32a  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004d32f  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d334  mov     r9d, 4; int
0x18004d33a  mov     r8, rdi; int
0x18004d33d  call    WiaTrace_ProcessTrace_Ex
0x18004d342  mov     rcx, [rsi+0E48h]
0x18004d349  mov     rax, [rcx]
0x18004d34c  mov     rdx, [rsp+88h+arg_20]
0x18004d354  mov     [rsp+88h+lpMem], rdx
0x18004d359  mov     r9, [rsp+88h+arg_18]
0x18004d361  mov     r8d, [rsp+88h+arg_10]
0x18004d369  mov     rdx, r13
0x18004d36c  mov     rax, [rax+20h]
0x18004d370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d375  mov     r13d, eax
0x18004d378  mov     [rsp+88h+var_58], eax
0x18004d37c  mov     dword ptr [rsp+88h+var_60], eax
0x18004d380  mov     rsi, [rsp+88h+arg_8]
0x18004d388  mov     [rsp+88h+lpMem], rsi
0x18004d38d  mov     r9, [r12]
0x18004d391  lea     r8, aWsCompletedIwi_6; "(%ws) completed IWiaMiniDrv::drvAcquire"...
0x18004d398  xor     edx, edx
0x18004d39a  xor     ecx, ecx
0x18004d39c  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004d3a1  mov     rbx, rax
0x18004d3a4  mov     rdx, rax; char *
0x18004d3a7  mov     rcx, rdi; char *
0x18004d3aa  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004d3af  mov     rcx, rbx; this
0x18004d3b2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d3b7  mov     dword ptr [rsp+88h+var_60], r13d
0x18004d3bc  mov     [rsp+88h+lpMem], rsi
0x18004d3c1  mov     r9, [r12]
0x18004d3c5  lea     r8, aWsCompletedIwi_6; "(%ws) completed IWiaMiniDrv::drvAcquire"...
0x18004d3cc  xor     edx, edx
0x18004d3ce  xor     ecx, ecx
0x18004d3d0  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004d3d5  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d3da  mov     r9d, 4; int
0x18004d3e0  mov     r8, rdi; int
0x18004d3e3  call    WiaTrace_ProcessTrace_Ex
0x18004d3e8  jmp     loc_18004D470
0x18004d3ed  mov     esi, eax
0x18004d3ef  mov     r8d, eax
0x18004d3f2  mov     rdi, [rsp+88h+arg_0]
0x18004d3fa  mov     rdx, [rdi+968h]
0x18004d401  lea     rcx, aTheDriverForWs_16; "The driver for (%ws) threw an exception"...
0x18004d408  call    WiaTrace_TraceLog
0x18004d40d  mov     rbx, rax
0x18004d410  mov     rdx, rax; char *
0x18004d413  lea     rcx, aUsdwrapperWiaD_14; "USDWrapper::WIA_drvAcquireItemData"
0x18004d41a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d41f  mov     rcx, rbx; this
0x18004d422  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d427  mov     r8d, esi
0x18004d42a  mov     rdx, [rdi+968h]
0x18004d431  lea     rcx, aTheDriverForWs_16; "The driver for (%ws) threw an exception"...
0x18004d438  call    WiaTrace_Trace
0x18004d43d  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d442  mov     r9d, 1; int
0x18004d448  lea     r8, aUsdwrapperWiaD_14; "USDWrapper::WIA_drvAcquireItemData"
0x18004d44f  call    WiaTrace_ProcessTrace_Ex
0x18004d454  mov     r13d, 8021000Eh
0x18004d45a  mov     [rsp+88h+var_58], r13d
0x18004d45f  lea     rdi, aUsdwrapperWiaD_14; "USDWrapper::WIA_drvAcquireItemData"
0x18004d466  mov     r12, [rsp+88h+var_50]
0x18004d46b  mov     r15, [rsp+88h+var_48]
0x18004d470  mov     rax, [r12]
0x18004d474  mov     [rsp+88h+arg_0], rax
0x18004d47c  lea     rdx, [rsp+88h+var_58]
0x18004d481  lea     rcx, [rsp+88h+arg_0]
0x18004d489  call    ??$WiaScanCompleted@PEBGAEAJ@WiaServiceTelemetry@@SAX$$QEAPEBGAEAJ@Z; WiaServiceTelemetry::WiaScanCompleted<ushort const *,long &>(ushort const * &&,long &)
0x18004d48e  jmp     short loc_18004D4DF
0x18004d490  mov     rdx, [r12]
0x18004d494  lea     rcx, aTheDriverForWs_13; "The driver for (%ws) was unexpectedly u"...
0x18004d49b  call    WiaTrace_TraceLog
0x18004d4a0  mov     rbx, rax
0x18004d4a3  mov     rdx, rax; char *
0x18004d4a6  mov     rcx, rdi; char *
0x18004d4a9  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d4ae  mov     rcx, rbx; this
0x18004d4b1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d4b6  mov     rdx, [r12]
0x18004d4ba  lea     rcx, aTheDriverForWs_13; "The driver for (%ws) was unexpectedly u"...
0x18004d4c1  call    WiaTrace_Trace
0x18004d4c6  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d4cb  mov     r9d, 1; int
0x18004d4d1  mov     r8, rdi; int
0x18004d4d4  call    WiaTrace_ProcessTrace_Ex
0x18004d4d9  mov     r13d, 80210005h
0x18004d4df  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18004d4e3  jz      loc_18004D5F8
0x18004d4e9  lea     r8, aPowerManagemen_3; "Power management: restore system initia"...
0x18004d4f0  xor     edx, edx
0x18004d4f2  xor     ecx, ecx
0x18004d4f4  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004d4f9  mov     rbx, rax
0x18004d4fc  mov     rdx, rax; char *
0x18004d4ff  mov     rcx, rdi; char *
0x18004d502  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004d507  mov     rcx, rbx; this
0x18004d50a  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d50f  lea     r8, aPowerManagemen_3; "Power management: restore system initia"...
0x18004d516  xor     edx, edx
0x18004d518  xor     ecx, ecx
0x18004d51a  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004d51f  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d524  mov     r9d, 4; int
0x18004d52a  mov     r8, rdi; int
0x18004d52d  call    WiaTrace_ProcessTrace_Ex
0x18004d532  mov     edx, 1; RequestType
0x18004d537  mov     rcx, [r15]; PowerRequest
0x18004d53a  call    cs:__imp_PowerClearRequest
0x18004d540  test    eax, eax
0x18004d542  jnz     short loc_18004D595
0x18004d544  call    cs:__imp_GetLastError
0x18004d54a  mov     edx, eax
0x18004d54c  lea     rcx, aPowerManagemen_6; "Power management: the power request Pow"...
0x18004d553  call    WiaTrace_TraceLog
0x18004d558  mov     rbx, rax
0x18004d55b  mov     rdx, rax; char *
0x18004d55e  mov     rcx, rdi; char *
0x18004d561  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d566  mov     rcx, rbx; this
0x18004d569  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d56e  call    cs:__imp_GetLastError
0x18004d574  mov     edx, eax
0x18004d576  lea     rcx, aPowerManagemen_6; "Power management: the power request Pow"...
0x18004d57d  call    WiaTrace_Trace
0x18004d582  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d587  mov     r9d, 1; int
0x18004d58d  mov     r8, rdi; int
0x18004d590  call    WiaTrace_ProcessTrace_Ex
0x18004d595  mov     edx, 3; RequestType
0x18004d59a  mov     rcx, [r15]; PowerRequest
0x18004d59d  call    cs:__imp_PowerClearRequest
0x18004d5a3  test    eax, eax
0x18004d5a5  jnz     short loc_18004D5F8
0x18004d5a7  call    cs:__imp_GetLastError
0x18004d5ad  mov     edx, eax
0x18004d5af  lea     rcx, aPowerManagemen_0; "Power management: the power request Pow"...
0x18004d5b6  call    WiaTrace_TraceLog
0x18004d5bb  mov     rbx, rax
0x18004d5be  mov     rdx, rax; char *
0x18004d5c1  mov     rcx, rdi; char *
0x18004d5c4  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004d5c9  mov     rcx, rbx; this
0x18004d5cc  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004d5d1  call    cs:__imp_GetLastError
0x18004d5d7  mov     edx, eax
0x18004d5d9  lea     rcx, aPowerManagemen_0; "Power management: the power request Pow"...
0x18004d5e0  call    WiaTrace_Trace
0x18004d5e5  mov     [rsp+88h+lpMem], rax; lpMem
0x18004d5ea  mov     r9d, 1; int
0x18004d5f0  mov     r8, rdi; int
0x18004d5f3  call    WiaTrace_ProcessTrace_Ex
0x18004d5f8  cmp     [rsp+88h+var_54], 0
0x18004d5fd  jz      short loc_18004D662
  ... truncated ...
```
