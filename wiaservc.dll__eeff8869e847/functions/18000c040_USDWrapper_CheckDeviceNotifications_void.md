# USDWrapper::CheckDeviceNotifications(void)

- ea: `0x18000c040`
- end: `0x18000c7b5`
- name: `?CheckDeviceNotifications@USDWrapper@@MEAAXXZ`
- size: `1909`
- prototype: `void __fastcall(USDWrapper *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000a6b4`
- `0x18000a974`
- `0x18000aa7c`
- `0x18000ac34`
- `0x18000b6a0`
- `0x18000c040`
- `0x18000c7c0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000dd00`
- `0x18000f4fc`
- `0x18000f668`
- `0x18000f808`
- `0x18000fa9c`
- `0x18000fbec`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033cc0`
- `0x180034658`
- `0x180054d0c`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000c4d0`
- `KERNEL32!LeaveCriticalSection` at `0x18000c4d0`
- `KERNEL32!WaitForSingleObject` at `0x18000c1a6`
- `KERNEL32!WaitForSingleObject` at `0x18000c1a6`
- `KERNEL32!GetCurrentThreadId` at `0x18000c140`
- `KERNEL32!GetCurrentThreadId` at `0x18000c263`
- `KERNEL32!GetCurrentThreadId` at `0x18000c140`
- `KERNEL32!GetCurrentThreadId` at `0x18000c263`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c6a7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000c6a7`

## string_xrefs

- `0x18000c390`: `ServiceComponentHolder::Get`
- `0x18000c3c6`: `ServiceComponentHolder::Get`
- `0x18000c37b`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x18000c3ae`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`

## pseudocode

```c
void __fastcall USDWrapper::CheckDeviceNotifications(USDWrapper *this)
{
  __int64 v2; // r12
  int v3; // r9d
  StiLockMgr *v4; // r13
  StiLockMgr *v5; // rcx
  unsigned int v6; // r15d
  char ***v7; // rax
  char *v8; // rdx
  __int64 v9; // r8
  char ***v10; // rax
  char *v11; // rdx
  __int64 v12; // r8
  StiLockMgr *v13; // rcx
  int LockInfo; // esi
  __int64 v15; // rbx
  StiLockMgr *v16; // rcx
  __int64 v17; // rax
  int v18; // esi
  char ***v19; // rax
  char *v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // r9d
  char *v23; // rcx
  __int64 v24; // rcx
  int v25; // eax
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
  char *v36; // rbx
  void *v37; // rdx
  void **v38; // rax
  void *v39; // rdx
  __int64 v40; // rcx
  char *v41; // rbx
  void *v42; // rdx
  void **v43; // rax
  void *v44; // rdx
  __int64 v45; // rcx
  int v46; // eax
  char *v47; // rcx
  int v48; // eax
  char *v49; // rbx
  void *v50; // rdx
  void **v51; // rax
  void *v52; // rdx
  __int64 v53; // rcx
  int v54; // eax
  int v55; // esi
  int v56; // esi
  int v57; // r8d
  char *v58; // rbx
  void *v59; // rdx
  void **v60; // rax
  void *v61; // rdx
  __int64 v62; // rcx
  char *v63; // rbx
  void *v64; // rdx
  void **v65; // rax
  void *v66; // rdx
  __int64 v67; // rcx
  char *v68; // rbx
  void *v69; // rdx
  void **v70; // rax
  void *v71; // rdx
  __int64 v72; // rcx
  unsigned int v73; // eax
  unsigned int v74; // esi
  char *v75; // rbx
  void *v76; // rdx
  void **v77; // rax
  void *v78; // rdx
  __int64 v79; // rcx
  unsigned int lpMem; // [rsp+20h] [rbp-E0h]
  unsigned int lpMemc; // [rsp+20h] [rbp-E0h]
  LPVOID lpMema; // [rsp+20h] [rbp-E0h]
  LPVOID lpMemd; // [rsp+20h] [rbp-E0h]
  LPVOID lpMemb; // [rsp+20h] [rbp-E0h]
  LPVOID lpMeme; // [rsp+20h] [rbp-E0h]
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h]
  int v87; // [rsp+30h] [rbp-D0h]
  _BYTE v88[80]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v89[80]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v90; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v91; // [rsp+F0h] [rbp-10h]
  _BYTE v92[96]; // [rsp+100h] [rbp+0h] BYREF
  const unsigned __int64 *v93; // [rsp+160h] [rbp+60h] BYREF
  char v94; // [rsp+168h] [rbp+68h] BYREF
  void *v95; // [rsp+268h] [rbp+168h]
  __int64 v96; // [rsp+270h] [rbp+170h]

  memset_0(v92, 0, 0x54u);
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)&v90);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)&v93, L"StiLockMgr");
  v2 = *((_QWORD *)&v90 + 1);
  if ( *((_QWORD *)&v90 + 1) )
  {
    v4 = (StiLockMgr *)CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<StiLockMgr>(
                         *((__int64 *)&v90 + 1),
                         (__int64)&v93);
  }
  else
  {
    v4 = 0;
    v31 = (char *)WiaTrace_TraceLogWithSubComp(
                    1,
                    "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                    v95);
    WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v31);
    WiaTrcLib::Free((WiaTrcLib *)v31, v32);
    v33 = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                     v95);
    WiaTrace_ProcessTrace_Ex(v35, v34, (void *)"ServiceComponentHolder::Get", 2, v33);
  }
  v5 = (StiLockMgr *)v95;
  v93 = &CSimpleStringBase<unsigned short>::`vftable';
  if ( v95 && v95 != &v94 )
    operator delete(v95);
  v95 = 0;
  v96 = 0;
  if ( v4 )
  {
    if ( (*((_BYTE *)this + 60) & 2) == 0 )
      goto LABEL_36;
    v6 = 0;
    v90 = 0;
    v91 = 0;
    v7 = (char ***)WiaTrace_Trace("StiLockMgr::RequestLock");
    CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v88, v8, v9, (char **)"StiLockMgr::RequestLock", lpMem, v7);
    CurrentThreadId = GetCurrentThreadId();
    v10 = (char ***)WiaTrace_Trace("StiLockMgr::RequestLockHelper");
    CWiaTraceFn::CWiaTraceFn((CWiaTraceFn *)v89, v11, v12, (char **)"StiLockMgr::RequestLockHelper", lpMemc, v10);
    if ( *((_QWORD *)this + 516) )
    {
      LockInfo = 0;
    }
    else
    {
      LockInfo = StiLockMgr::CreateLockInfo(v13, this);
      if ( LockInfo < 0 )
      {
LABEL_15:
        CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v89);
        CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v88);
        if ( LockInfo < 0 )
        {
          if ( LockInfo == -2145320955 )
            goto LABEL_20;
          LODWORD(lpMema) = LockInfo;
          v49 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          0,
                          0,
                          "While trying to poll the device (%ws), locking failed (%#x)",
                          *((_QWORD *)this + 301),
                          lpMema);
          WriteDbgTraceInfoWI("USDWrapper::CheckDeviceNotifications", v49);
          WiaTrcLib::Free((WiaTrcLib *)v49, v50);
          LODWORD(lpMemd) = LockInfo;
          v51 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           0,
                           0,
                           "While trying to poll the device (%ws), locking failed (%#x)",
                           *((_QWORD *)this + 301),
                           lpMemd);
          WiaTrace_ProcessTrace_Ex(v53, v52, (void *)"USDWrapper::CheckDeviceNotifications", 4, v51);
        }
        else
        {
          _InterlockedExchange((volatile __int32 *)this + 1014, 1);
          v91 = 0;
          v17 = *(_QWORD *)this;
          v90 = 0;
          DWORD1(v90) = 2;
          v18 = (*(__int64 (__fastcall **)(USDWrapper *, __int128 *))(v17 + 280))(this, &v90);
          if ( v18 < 0 )
          {
            if ( v18 != -2145320955 )
            {
              v26 = (char *)WiaTrace_TraceLog("While trying to poll the device, the driver for (%ws) failed IStiUSD::GetS"
                                              "tatus (%#x), ignoring ...");
              WriteDbgTraceErrorWI("USDWrapper::CheckDeviceNotifications", v26);
              WiaTrcLib::Free((WiaTrcLib *)v26, v27);
              v28 = (void **)WiaTrace_Trace(
                               "While trying to poll the device, the driver for (%ws) failed IStiUSD::GetStatus (%#x), ignoring ...",
                               *((_QWORD *)this + 301),
                               (unsigned int)v18);
              WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"USDWrapper::CheckDeviceNotifications", 1, v28);
            }
          }
          else
          {
            v6 = ((unsigned int)v91 >> 2) & 1;
          }
          v19 = (char ***)WiaTrace_Trace("StiLockMgr::RequestUnlock");
          CWiaTraceFn::CWiaTraceFn(
            (CWiaTraceFn *)v88,
            v20,
            v21,
            (char **)"StiLockMgr::RequestUnlock",
            (unsigned int)lpMema,
            v19);
          GetCurrentThreadId();
          StiLockMgr::RequestUnlockHelper(v4, this, 1, v22);
          CWiaTraceFn::~CWiaTraceFn((CWiaTraceFn *)v88);
          _InterlockedExchange((volatile __int32 *)this + 1014, 0);
        }
        if ( !v6 )
        {
LABEL_20:
          v23 = (char *)v4 + *(int *)(*((_QWORD *)v4 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v23 + 16LL))(v23);
          goto LABEL_21;
        }
LABEL_36:
        v54 = StiLockMgr::RequestLock(v5, this, 0x64u, v3, 0);
        v55 = v54;
        if ( v54 < 0 )
        {
          if ( v54 != -2145320955 )
          {
            LODWORD(lpMemb) = v54;
            v63 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                            0,
                            0,
                            "Failed to retrieve notification data for (%ws), could not obtain a device lock (hr = 0x%08X)"
                            ". Ignoring this notification.",
                            *((_QWORD *)this + 301),
                            lpMemb);
            WriteDbgTraceInfoWI("USDWrapper::CheckDeviceNotifications", v63);
            WiaTrcLib::Free((WiaTrcLib *)v63, v64);
            LODWORD(lpMeme) = v55;
            v65 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                             0,
                             0,
                             "Failed to retrieve notification data for (%ws), could not obtain a device lock (hr = 0x%08X"
                             "). Ignoring this notification.",
                             *((_QWORD *)this + 301),
                             lpMeme);
            WiaTrace_ProcessTrace_Ex(v67, v66, (void *)"USDWrapper::CheckDeviceNotifications", 4, v65);
          }
        }
        else
        {
          _InterlockedExchange((volatile __int32 *)this + 1014, 1);
          v56 = (*(__int64 (__fastcall **)(USDWrapper *, _BYTE *))(*(_QWORD *)this + 288LL))(this, v92);
          if ( v56 < 0 )
          {
            if ( v56 != -2147024637 && v56 != -2145320955 )
            {
              v58 = (char *)WiaTrace_TraceLog("Driver for (%ws) failed IStiUSD::GetNotificationData with hr = 0x%08X...ignoring");
              WriteDbgTraceErrorWI("USDWrapper::CheckDeviceNotifications", v58);
              WiaTrcLib::Free((WiaTrcLib *)v58, v59);
              v60 = (void **)WiaTrace_Trace(
                               "Driver for (%ws) failed IStiUSD::GetNotificationData with hr = 0x%08X...ignoring",
                               *((_QWORD *)this + 301),
                               (unsigned int)v56);
              WiaTrace_ProcessTrace_Ex(v62, v61, (void *)"USDWrapper::CheckDeviceNotifications", 1, v60);
            }
          }
          else
          {
            (*(void (__fastcall **)(USDWrapper *, _BYTE *))(*(_QWORD *)this + 256LL))(this, v92);
          }
          StiLockMgr::RequestUnlock(v4, this, v57);
          _InterlockedExchange((volatile __int32 *)this + 1014, 0);
        }
        v46 = CRIT_SECT::Lock((USDWrapper *)((char *)this + 4232));
        v47 = (char *)*((_QWORD *)this + 500);
        v87 = v46;
        if ( (unsigned __int64)(v47 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          ResetEvent(v47);
          v68 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          0,
                          0,
                          "DeviceEvent [0x%X] for (%ws) reset to be passed to IStiUSD::SetNotificationHandle",
                          *((_QWORD *)this + 500),
                          *((_QWORD *)this + 301));
          WriteDbgTraceInfoWI("USDWrapper::CheckDeviceNotifications", v68);
          WiaTrcLib::Free((WiaTrcLib *)v68, v69);
          v70 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                           0,
                           0,
                           "DeviceEvent [0x%X] for (%ws) reset to be passed to IStiUSD::SetNotificationHandle",
                           *((_QWORD *)this + 500),
                           *((_QWORD *)this + 301));
          WiaTrace_ProcessTrace_Ex(v72, v71, (void *)"USDWrapper::CheckDeviceNotifications", 4, v70);
          v73 = (*(__int64 (__fastcall **)(USDWrapper *, _QWORD))(*(_QWORD *)this + 296LL))(
                  this,
                  *((_QWORD *)this + 501));
          v74 = 0;
          if ( v73 != -2147467263 )
            v74 = v73;
          if ( ((v74 + 0x80000000) & 0x80000000) == 0 && v74 != -2145320955 )
          {
            v75 = (char *)WiaTrace_TraceLog("USD for (%ws) refused to take event handle - call to IStiUSD::SetNotificatio"
                                            "nHandle failed with 0x%08X");
            WriteDbgTraceErrorWI("USDWrapper::CheckDeviceNotifications", v75);
            WiaTrcLib::Free((WiaTrcLib *)v75, v76);
            v77 = (void **)WiaTrace_Trace(
                             "USD for (%ws) refused to take event handle - call to IStiUSD::SetNotificationHandle failed with 0x%08X",
                             *((_QWORD *)this + 301),
                             v74);
            WiaTrace_ProcessTrace_Ex(v79, v78, (void *)"USDWrapper::CheckDeviceNotifications", 1, v77);
          }
        }
        if ( v87 )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 4232));
        goto LABEL_20;
      }
    }
    v15 = *((_QWORD *)this + 516);
    if ( CurrentThreadId == _InterlockedCompareExchange(
                              (volatile signed __int32 *)(v15 + 16),
                              CurrentThreadId,
                              CurrentThreadId) )
    {
      v48 = *(_DWORD *)(v15 + 20);
      ++*(_DWORD *)(v15 + 12);
      *(_DWORD *)(v15 + 24) = v48;
    }
    else if ( WaitForSingleObject(*(HANDLE *)v15, 0x64u) )
    {
      LockInfo = -2145320954;
      v36 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Device is busy, returning %#x", -2145320954);
      WriteDbgTraceInfoWI("StiLockMgr::RequestLockHelper", v36);
      WiaTrcLib::Free((WiaTrcLib *)v36, v37);
      v38 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Device is busy, returning %#x", -2145320954);
      WiaTrace_ProcessTrace_Ex(v40, v39, (void *)"StiLockMgr::RequestLockHelper", 4, v38);
    }
    else if ( (*(unsigned int (__fastcall **)(USDWrapper *))(*(_QWORD *)this + 168LL))(this) )
    {
      _InterlockedExchange((volatile __int32 *)(v15 + 16), CurrentThreadId);
      v25 = *(_DWORD *)(v15 + 20);
      ++*(_DWORD *)(v15 + 12);
      *(_DWORD *)(v15 + 24) = v25;
      LockInfo = StiLockMgr::LockDevice(v16, this);
    }
    else
    {
      StiLockMgr::ClearLockInfo(v16, (struct LockInfo *)v15);
      LockInfo = -2145320955;
    }
    goto LABEL_15;
  }
  v41 = (char *)WiaTrace_TraceLog("The Lock Manager is NULL - we cannot check for device notifications on (%ws)");
  WriteDbgTraceErrorWI("USDWrapper::CheckDeviceNotifications", v41);
  WiaTrcLib::Free((WiaTrcLib *)v41, v42);
  v43 = (void **)WiaTrace_Trace(
                   "The Lock Manager is NULL - we cannot check for device notifications on (%ws)",
                   *((_QWORD *)this + 301));
  WiaTrace_ProcessTrace_Ex(v45, v44, (void *)"USDWrapper::CheckDeviceNotifications", 1, v43);
LABEL_21:
  if ( v2 )
  {
    v24 = v2 + *(int *)(*(_QWORD *)v2 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
}

```

## disassembly

```asm
0x18000c040  push    rbp
0x18000c042  push    rbx
0x18000c043  push    rsi
0x18000c044  push    rdi
0x18000c045  push    r12
0x18000c047  push    r13
0x18000c049  push    r14
0x18000c04b  push    r15
0x18000c04d  lea     rbp, [rsp-1A8h]
0x18000c055  sub     rsp, 2A8h
0x18000c05c  mov     rax, cs:__security_cookie
0x18000c063  xor     rax, rsp
0x18000c066  mov     [rbp+1E0h+var_50], rax
0x18000c06d  xor     edx, edx; Val
0x18000c06f  mov     rdi, rcx
0x18000c072  lea     rcx, [rbp+1E0h+var_1E0]; void *
0x18000c076  lea     r8d, [rdx+54h]; Size
0x18000c07a  call    memset_0
0x18000c07f  lea     rcx, [rbp+1E0h+var_200]; this
0x18000c083  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18000c088  lea     rdx, aStilockmgr; "StiLockMgr"
0x18000c08f  lea     rcx, [rbp+1E0h+var_180]
0x18000c093  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000c098  mov     r12, qword ptr [rbp+1E0h+var_200+8]
0x18000c09c  mov     r15d, 1
0x18000c0a2  test    r12, r12
0x18000c0a5  jz      loc_18000C374
0x18000c0ab  lea     rdx, [rbp+1E0h+var_180]
0x18000c0af  mov     rcx, r12
0x18000c0b2  call    ??$Get@VStiLockMgr@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVStiLockMgr@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<StiLockMgr>(CSimpleStringBase<ushort> const &)
0x18000c0b7  mov     r13, rax
0x18000c0ba  mov     rcx, [rbp+1E0h+var_78]; void *
0x18000c0c1  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000c0c8  mov     [rbp+1E0h+var_180], rax
0x18000c0cc  test    rcx, rcx
0x18000c0cf  jz      short loc_18000C0DE
0x18000c0d1  lea     rax, [rbp+1E0h+var_178]
0x18000c0d5  cmp     rcx, rax
0x18000c0d8  jnz     loc_18000C490
0x18000c0de  mov     [rbp+1E0h+var_78], 0
0x18000c0e9  mov     [rbp+1E0h+var_70], 0
0x18000c0f4  test    r13, r13
0x18000c0f7  jz      loc_18000C438
0x18000c0fd  test    byte ptr [rdi+3Ch], 2
0x18000c101  lea     r14, aUsdwrapperChec; "USDWrapper::CheckDeviceNotifications"
0x18000c108  jz      loc_18000C55F
0x18000c10e  xorps   xmm0, xmm0
0x18000c111  lea     rcx, aStilockmgrRequ_1; "StiLockMgr::RequestLock"
0x18000c118  xor     eax, eax
0x18000c11a  xor     r15d, r15d
0x18000c11d  movups  [rbp+1E0h+var_200], xmm0
0x18000c121  mov     [rbp+1E0h+var_1F0], rax
0x18000c125  call    WiaTrace_Trace
0x18000c12a  lea     r9, aStilockmgrRequ_1; "StiLockMgr::RequestLock"
0x18000c131  mov     [rsp+2E0h+var_2B8], rax; struct tagWiaTraceData_Type *
0x18000c136  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000c13b  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18000c140  call    cs:__imp_GetCurrentThreadId
0x18000c146  lea     rcx, aStilockmgrRequ_2; "StiLockMgr::RequestLockHelper"
0x18000c14d  mov     [rsp+2E0h+var_2B0], eax
0x18000c151  call    WiaTrace_Trace
0x18000c156  lea     r9, aStilockmgrRequ_2; "StiLockMgr::RequestLockHelper"
0x18000c15d  mov     [rsp+2E0h+var_2B8], rax; struct tagWiaTraceData_Type *
0x18000c162  lea     rcx, [rbp+1E0h+var_250]; this
0x18000c166  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18000c16b  cmp     [rdi+1020h], r15
0x18000c172  jz      short loc_18000C178
0x18000c174  xor     esi, esi
0x18000c176  jmp     short loc_18000C186
0x18000c178  mov     rdx, rdi; struct USDWrapper *
0x18000c17b  call    ?CreateLockInfo@StiLockMgr@@AEAAJPEAVUSDWrapper@@@Z; StiLockMgr::CreateLockInfo(USDWrapper *)
0x18000c180  mov     esi, eax
0x18000c182  test    eax, eax
0x18000c184  js      short loc_18000C1DB
0x18000c186  mov     ecx, [rsp+2E0h+var_2B0]
0x18000c18a  mov     eax, ecx
0x18000c18c  mov     rbx, [rdi+1020h]
0x18000c193  lock cmpxchg [rbx+10h], ecx
0x18000c198  jz      loc_18000C4DB
0x18000c19e  mov     rcx, [rbx]; hHandle
0x18000c1a1  mov     edx, 64h ; 'd'; dwMilliseconds
0x18000c1a6  call    cs:__imp_WaitForSingleObject
0x18000c1ac  test    eax, eax
0x18000c1ae  jnz     loc_18000C3D7
0x18000c1b4  mov     rax, [rdi]
0x18000c1b7  mov     rcx, rdi
0x18000c1ba  mov     rax, [rax+0A8h]
0x18000c1c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1c6  test    eax, eax
0x18000c1c8  jnz     loc_18000C2EF
0x18000c1ce  mov     rdx, rbx; struct LockInfo *
0x18000c1d1  call    ?ClearLockInfo@StiLockMgr@@QEAAJPEAVLockInfo@@@Z; StiLockMgr::ClearLockInfo(LockInfo *)
0x18000c1d6  mov     esi, 80210005h
0x18000c1db  lea     rcx, [rbp+1E0h+var_250]; this
0x18000c1df  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18000c1e4  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000c1e9  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18000c1ee  test    esi, esi
0x18000c1f0  js      loc_18000C4E9
0x18000c1f6  mov     eax, 1
0x18000c1fb  lea     rdx, [rbp+1E0h+var_200]
0x18000c1ff  xchg    eax, [rdi+0FD8h]
0x18000c205  xor     eax, eax
0x18000c207  xorps   xmm0, xmm0
0x18000c20a  mov     [rbp+1E0h+var_1F0], rax
0x18000c20e  mov     rcx, rdi
0x18000c211  mov     rax, [rdi]
0x18000c214  movups  [rbp+1E0h+var_200], xmm0
0x18000c218  mov     dword ptr [rbp+1E0h+var_200+4], 2
0x18000c21f  mov     rax, [rax+118h]
0x18000c226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c22b  mov     esi, eax
0x18000c22d  test    eax, eax
0x18000c22f  js      loc_18000C30E
0x18000c235  mov     r15d, dword ptr [rbp+1E0h+var_1F0]
0x18000c239  shr     r15d, 2
0x18000c23d  and     r15d, 1
0x18000c241  lea     rcx, aStilockmgrRequ_4; "StiLockMgr::RequestUnlock"
0x18000c248  call    WiaTrace_Trace
0x18000c24d  lea     r9, aStilockmgrRequ_4; "StiLockMgr::RequestUnlock"
0x18000c254  mov     [rsp+2E0h+var_2B8], rax; struct tagWiaTraceData_Type *
0x18000c259  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000c25e  call    ??0CWiaTraceFn@@QEAA@PEADK0KPEAUtagWiaTraceData_Type@@@Z; CWiaTraceFn::CWiaTraceFn(char *,ulong,char *,ulong,tagWiaTraceData_Type *)
0x18000c263  call    cs:__imp_GetCurrentThreadId
0x18000c269  mov     r8d, 1; int
0x18000c26f  mov     rdx, rdi; struct USDWrapper *
0x18000c272  mov     rcx, r13; this
0x18000c275  call    ?RequestUnlockHelper@StiLockMgr@@AEAAJPEAVUSDWrapper@@HK@Z; StiLockMgr::RequestUnlockHelper(USDWrapper *,int,ulong)
0x18000c27a  lea     rcx, [rsp+2E0h+var_2A0]; this
0x18000c27f  call    ??1CWiaTraceFn@@QEAA@XZ; CWiaTraceFn::~CWiaTraceFn(void)
0x18000c284  xor     eax, eax
0x18000c286  xchg    eax, [rdi+0FD8h]
0x18000c28c  test    r15d, r15d
0x18000c28f  jnz     loc_18000C559
0x18000c295  mov     rax, [r13+8]
0x18000c299  movsxd  rcx, dword ptr [rax+4]
0x18000c29d  add     rcx, 8
0x18000c2a1  add     rcx, r13
0x18000c2a4  mov     rax, [rcx]
0x18000c2a7  mov     rax, [rax+10h]
0x18000c2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2b0  test    r12, r12
0x18000c2b3  jz      short loc_18000C2CC
0x18000c2b5  mov     rax, [r12]
0x18000c2b9  movsxd  rcx, dword ptr [rax+4]
0x18000c2bd  add     rcx, r12
0x18000c2c0  mov     rax, [rcx]
0x18000c2c3  mov     rax, [rax+10h]
0x18000c2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2cc  mov     rcx, [rbp+1E0h+var_50]
0x18000c2d3  xor     rcx, rsp; StackCookie
0x18000c2d6  call    __security_check_cookie
0x18000c2db  add     rsp, 2A8h
0x18000c2e2  pop     r15
0x18000c2e4  pop     r14
0x18000c2e6  pop     r13
0x18000c2e8  pop     r12
0x18000c2ea  pop     rdi
0x18000c2eb  pop     rsi
0x18000c2ec  pop     rbx
0x18000c2ed  pop     rbp
0x18000c2ee  retn
0x18000c2ef  mov     eax, [rsp+2E0h+var_2B0]
0x18000c2f3  mov     rdx, rdi; struct USDWrapper *
0x18000c2f6  xchg    eax, [rbx+10h]
0x18000c2f9  mov     eax, [rbx+14h]
0x18000c2fc  inc     dword ptr [rbx+0Ch]
0x18000c2ff  mov     [rbx+18h], eax
0x18000c302  call    ?LockDevice@StiLockMgr@@QEAAJPEAVUSDWrapper@@@Z; StiLockMgr::LockDevice(USDWrapper *)
0x18000c307  mov     esi, eax
0x18000c309  jmp     loc_18000C1DB
0x18000c30e  cmp     esi, 80210005h
0x18000c314  jz      loc_18000C241
0x18000c31a  mov     rdx, [rdi+968h]
0x18000c321  lea     rcx, aWhileTryingToP_0; "While trying to poll the device, the dr"...
0x18000c328  mov     r8d, esi
0x18000c32b  call    WiaTrace_TraceLog
0x18000c330  mov     rdx, rax; char *
0x18000c333  mov     rcx, r14; char *
0x18000c336  mov     rbx, rax
0x18000c339  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000c33e  mov     rcx, rbx; this
0x18000c341  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000c346  mov     rdx, [rdi+968h]
0x18000c34d  lea     rcx, aWhileTryingToP_0; "While trying to poll the device, the dr"...
0x18000c354  mov     r8d, esi
0x18000c357  call    WiaTrace_Trace
0x18000c35c  mov     r9d, 1; int
0x18000c362  mov     [rsp+2E0h+lpMem], rax; lpMem
0x18000c367  mov     r8, r14; int
0x18000c36a  call    WiaTrace_ProcessTrace_Ex
0x18000c36f  jmp     loc_18000C241
0x18000c374  mov     r8, [rbp+1E0h+var_78]
0x18000c37b  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000c382  mov     ecx, r15d
0x18000c385  xor     r13d, r13d
0x18000c388  call    WiaTrace_TraceLogWithSubComp
0x18000c38d  mov     rdx, rax; char *
0x18000c390  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x18000c397  mov     rbx, rax
0x18000c39a  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000c39f  mov     rcx, rbx; this
0x18000c3a2  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000c3a7  mov     r8, [rbp+1E0h+var_78]
0x18000c3ae  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x18000c3b5  mov     ecx, r15d
0x18000c3b8  call    WiaTrace_TraceWithSubComp
0x18000c3bd  lea     r9d, [r13+2]; int
0x18000c3c1  mov     [rsp+2E0h+lpMem], rax; lpMem
0x18000c3c6  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x18000c3cd  call    WiaTrace_ProcessTrace_Ex
0x18000c3d2  jmp     loc_18000C0BA
0x18000c3d7  mov     esi, 80210006h
0x18000c3dc  lea     r8, aDeviceIsBusyRe; "Device is busy, returning %#x"
0x18000c3e3  mov     r9d, esi
0x18000c3e6  xor     edx, edx
0x18000c3e8  xor     ecx, ecx
0x18000c3ea  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000c3ef  mov     rdx, rax; char *
0x18000c3f2  lea     rcx, aStilockmgrRequ_2; "StiLockMgr::RequestLockHelper"
0x18000c3f9  mov     rbx, rax
0x18000c3fc  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000c401  mov     rcx, rbx; this
0x18000c404  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000c409  mov     r9d, esi
0x18000c40c  lea     r8, aDeviceIsBusyRe; "Device is busy, returning %#x"
0x18000c413  xor     edx, edx
0x18000c415  xor     ecx, ecx
0x18000c417  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000c41c  mov     r9d, 4; int
0x18000c422  mov     [rsp+2E0h+lpMem], rax; lpMem
0x18000c427  lea     r8, aStilockmgrRequ_2; "StiLockMgr::RequestLockHelper"
0x18000c42e  call    WiaTrace_ProcessTrace_Ex
0x18000c433  jmp     loc_18000C1DB
0x18000c438  mov     rdx, [rdi+968h]
0x18000c43f  lea     rcx, aTheLockManager_2; "The Lock Manager is NULL - we cannot ch"...
0x18000c446  call    WiaTrace_TraceLog
0x18000c44b  lea     r14, aUsdwrapperChec; "USDWrapper::CheckDeviceNotifications"
0x18000c452  mov     rdx, rax; char *
0x18000c455  mov     rcx, r14; char *
0x18000c458  mov     rbx, rax
0x18000c45b  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18000c460  mov     rcx, rbx; this
0x18000c463  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000c468  mov     rdx, [rdi+968h]
0x18000c46f  lea     rcx, aTheLockManager_2; "The Lock Manager is NULL - we cannot ch"...
0x18000c476  call    WiaTrace_Trace
0x18000c47b  mov     r9d, r15d; int
0x18000c47e  mov     [rsp+2E0h+lpMem], rax; lpMem
0x18000c483  mov     r8, r14; int
0x18000c486  call    WiaTrace_ProcessTrace_Ex
0x18000c48b  jmp     loc_18000C2B0
0x18000c490  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c495  jmp     loc_18000C0DE
0x18000c49a  lea     r15, [rdi+1088h]
0x18000c4a1  mov     rcx, r15; this
0x18000c4a4  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18000c4a9  mov     rcx, [rdi+0FA0h]; hEvent
0x18000c4b0  mov     [rsp+2E0h+var_2B0], eax
0x18000c4b4  lea     rdx, [rcx-1]
0x18000c4b8  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18000c4bc  jbe     loc_18000C6A7
0x18000c4c2  cmp     [rsp+2E0h+var_2B0], 0
0x18000c4c7  jz      loc_18000C295
0x18000c4cd  mov     rcx, r15; lpCriticalSection
0x18000c4d0  call    cs:__imp_LeaveCriticalSection
0x18000c4d6  jmp     loc_18000C295
0x18000c4db  mov     eax, [rbx+14h]
0x18000c4de  inc     dword ptr [rbx+0Ch]
0x18000c4e1  mov     [rbx+18h], eax
0x18000c4e4  jmp     loc_18000C1DB
0x18000c4e9  cmp     esi, 80210005h
0x18000c4ef  jz      loc_18000C295
0x18000c4f5  mov     r9, [rdi+968h]
0x18000c4fc  lea     r8, aWhileTryingToP; "While trying to poll the device (%ws), "...
0x18000c503  xor     edx, edx
0x18000c505  mov     dword ptr [rsp+2E0h+lpMem], esi
0x18000c509  xor     ecx, ecx
0x18000c50b  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000c510  mov     rdx, rax; char *
0x18000c513  mov     rcx, r14; char *
0x18000c516  mov     rbx, rax
0x18000c519  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000c51e  mov     rcx, rbx; this
0x18000c521  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000c526  mov     r9, [rdi+968h]
0x18000c52d  lea     r8, aWhileTryingToP; "While trying to poll the device (%ws), "...
0x18000c534  xor     edx, edx
0x18000c536  mov     dword ptr [rsp+2E0h+lpMem], esi
0x18000c53a  xor     ecx, ecx
0x18000c53c  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000c541  mov     r9d, 4; int
0x18000c547  mov     [rsp+2E0h+lpMem], rax; lpMem
0x18000c54c  mov     r8, r14; int
0x18000c54f  call    WiaTrace_ProcessTrace_Ex
0x18000c554  jmp     loc_18000C28C
0x18000c559  mov     r15d, 1
0x18000c55f  mov     r8d, 64h ; 'd'; unsigned int
0x18000c565  mov     [rsp+2E0h+lpMem], 0; unsigned __int8 *
0x18000c56e  mov     rdx, rdi; struct USDWrapper *
  ... truncated ...
```
