# RegistryDeviceEnumerator::ProcessEvent(ulong,ulong,ulong,void *)

- ea: `0x18000b780`
- end: `0x18000bc44`
- name: `?ProcessEvent@RegistryDeviceEnumerator@@UEAAJKKKPEAX@Z`
- size: `1220`
- prototype: `__int64 __fastcall(RegistryDeviceEnumerator *__hidden this, unsigned int, unsigned int, unsigned int, void *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180004ff8`
- `0x18000645c`
- `0x1800085b0`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000b780`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x18000fc60`
- `0x180011a94`
- `0x1800174c4`
- `0x180027590`
- `0x18002a448`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180078010`

## string_xrefs

- `0x18000b7c5`: `The Registry Device enumerator/handler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)`
- `0x18000b7f0`: `The Registry Device enumerator/handler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)`
- `0x18000b7d3`: `RegistryDeviceEnumerator::ProcessEvent`
- `0x18000b8f6`: `RegistryDeviceEnumerator::ProcessEvent`
- `0x18000b889`: `Unknown Registry Device Message`
- `0x18000b8af`: `Message for Registry Device Enumerator: %s`
- `0x18000b91b`: `Message for Registry Device Enumerator: %s`
- `0x18000baf0`: `The Registry Device enumerator could not process the message (%s) because the DeviceListManager is NULL!`
- `0x18000bb1b`: `The Registry Device enumerator could not process the message (%s) because the DeviceListManager is NULL!`
- `0x18000bb4f`: `The Registry Device enumerator/handler found a device wrapper with a NULL USDInfo (%ws)`
- `0x18000bb7f`: `The Registry Device enumerator/handler found a device wrapper with a NULL USDInfo (%ws)`

## pseudocode

```c
__int64 __fastcall RegistryDeviceEnumerator::ProcessEvent(
        RegistryDeviceEnumerator *this,
        int a2,
        int a3,
        unsigned int a4,
        void *a5)
{
  char *v6; // rbx
  void *v7; // rdx
  void **lpMem; // rax
  void *v9; // rdx
  __int64 v10; // rcx
  char *v11; // rbx
  void *v12; // rdx
  void **v13; // rax
  void *v14; // rdx
  __int64 v15; // rcx
  unsigned int v16; // ebx
  __int64 v18; // r14
  char *v19; // rbx
  void *v20; // rdx
  void **v21; // rax
  void *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 USDWrapperFromDeviceList; // rax
  struct USDWrapper *v26; // rsi
  __int64 v27; // rax
  int v28; // edx
  __int64 (__fastcall *v29)(struct USDWrapper *, _QWORD *, _QWORD *, __int64, int *, int); // rbx
  __int64 v30; // rax
  DeviceListManager *v31; // r14
  int v32; // edx
  DeviceListManager *v33; // rcx
  __int64 v34; // r8
  unsigned int v35; // edi
  unsigned int v36; // edi
  __int64 v37; // rdx
  __int64 v38; // r8
  int UnloadDrivers; // eax
  int v40; // edx
  char *v41; // rcx
  char *v42; // rbx
  void *v43; // rdx
  void **v44; // rax
  void *v45; // rdx
  __int64 v46; // rcx
  char *v47; // rbx
  void *v48; // rdx
  void **v49; // rax
  void *v50; // rdx
  __int64 v51; // rcx
  char *v52; // rbx
  void *v53; // rdx
  void **v54; // rax
  void *v55; // rdx
  __int64 v56; // rcx
  int v57; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v58[24]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v59[34]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v60; // [rsp+170h] [rbp+70h]
  _QWORD v61[33]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v62; // [rsp+298h] [rbp+198h]
  _QWORD v63[38]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _QWORD v64[5]; // [rsp+3F0h] [rbp+2F0h] BYREF

  if ( a2 == -1 )
  {
    v16 = 0;
    if ( a3 != 254 )
      return v16;
    v64[0] = "Unknown Registry Device Message";
    v64[1] = "REG_DEVICE_EVENT_TYPE_QUICK_ACTIVATE";
    v64[2] = "REG_DEVICE_EVENT_TYPE_QUICK_DEACTIVATE";
    v64[3] = "REG_DEVICE_EVENT_TYPE_SLOW_ACTIVATE";
    v64[4] = "REG_DEVICE_EVENT_TYPE_SLOW_DEACTIVATE";
    v18 = a4 < 5 ? a4 : 0;
    v19 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    2,
                    0,
                    "Message for Registry Device Enumerator: %s",
                    (const char *)v64[v18]);
    WriteDbgTraceInfoWI("RegistryDeviceEnumerator::ProcessEvent", v19);
    WiaTrcLib::Free((WiaTrcLib *)v19, v20);
    v21 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     2,
                     0,
                     "Message for Registry Device Enumerator: %s",
                     (const char *)v64[v18]);
    WiaTrace_ProcessTrace_Ex(v23, v22, (void *)"RegistryDeviceEnumerator::ProcessEvent", 4, v21);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v61, a5);
    USDWrapperFromDeviceList = GetUSDWrapperFromDeviceList(v24, v61);
    v26 = (struct USDWrapper *)USDWrapperFromDeviceList;
    if ( !USDWrapperFromDeviceList )
    {
      v52 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      2,
                      0,
                      "Could not find device (%ws)..ignoring message (%s)",
                      v62,
                      v64[v18]);
      WriteDbgTraceInfoWI("RegistryDeviceEnumerator::ProcessEvent", v52);
      WiaTrcLib::Free((WiaTrcLib *)v52, v53);
      v54 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       2,
                       0,
                       "Could not find device (%ws)..ignoring message (%s)",
                       v62,
                       v64[v18]);
      WiaTrace_ProcessTrace_Ex(v56, v55, (void *)"RegistryDeviceEnumerator::ProcessEvent", 4, v54);
      v16 = 0;
      goto LABEL_24;
    }
    v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)USDWrapperFromDeviceList + 152LL))(USDWrapperFromDeviceList);
    if ( !v27 )
    {
      v47 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "The Registry Device enumerator/handler found a device wrapper with a NULL USDInfo (%ws)",
                      v62);
      WriteDbgTraceWarningWI("RegistryDeviceEnumerator::ProcessEvent", v47);
      WiaTrcLib::Free((WiaTrcLib *)v47, v48);
      v49 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "The Registry Device enumerator/handler found a device wrapper with a NULL USDInfo (%ws)",
                       v62);
      WiaTrace_ProcessTrace_Ex(v51, v50, (void *)"RegistryDeviceEnumerator::ProcessEvent", 2, v49);
      v16 = -2147024809;
      goto LABEL_22;
    }
    v28 = 0;
    v57 = 0;
    if ( a4 == 1 || a4 == 3 )
    {
      v28 = 4;
      v57 = 4;
    }
    *(_DWORD *)(v27 + 4) = v28;
    v29 = *(__int64 (__fastcall **)(struct USDWrapper *, _QWORD *, _QWORD *, __int64, int *, int))(*(_QWORD *)v26 + 184LL);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v63, L"DeviceState");
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v59, &Class);
    v16 = v29(v26, v59, v63, 4, &v57, 4);
    v59[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v59);
    v60 = 0;
    v63[0] = &CSimpleStringBase<unsigned short>::`vftable';
    CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v63);
    ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v58);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>((__int64)v59, L"DeviceListManager");
    v30 = ServiceComponentHolder::Get<DeviceListManager>((__int64)v58, (__int64)v59);
    v59[0] = &CSimpleStringBase<unsigned short>::`vftable';
    v31 = (DeviceListManager *)v30;
    CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v59);
    v60 = 0;
    if ( !v31 )
    {
      v42 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "The Registry Device enumerator could not process the message (%s) because the DeviceListManager is NULL!",
                      (const char *)v64);
      WriteDbgTraceWarningWI("RegistryDeviceEnumerator::ProcessEvent", v42);
      WiaTrcLib::Free((WiaTrcLib *)v42, v43);
      v44 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "The Registry Device enumerator could not process the message (%s) because the DeviceListManager is NULL!",
                       (const char *)v64);
      WiaTrace_ProcessTrace_Ex(v46, v45, (void *)"RegistryDeviceEnumerator::ProcessEvent", 2, v44);
      v16 = -2147418113;
      goto LABEL_20;
    }
    v35 = a4 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( v36 )
      {
        if ( v36 - 1 > 1 )
        {
LABEL_18:
          v41 = (char *)v31 + *(int *)(*((_QWORD *)v31 + 1) + 4LL) + 8;
          (*(void (__fastcall **)(char *))(*(_QWORD *)v41 + 16LL))(v41);
LABEL_20:
          ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v58);
LABEL_22:
          (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v26 + 16LL))(v26);
LABEL_24:
          v61[0] = &CSimpleStringBase<unsigned short>::`vftable';
          CSimpleStringBase<unsigned short>::DeleteStorage((__int64)v61);
          return v16;
        }
        DeviceListManager::Enumerate(v31, 0, v34);
        UnloadDrivers = DeviceListManager::LoadUnloadDrivers(v31, v37, v38);
      }
      else
      {
        UnloadDrivers = DeviceListManager::ProcessDeviceRemoval(v33, v32, v26);
      }
    }
    else
    {
      (*(void (__fastcall **)(struct USDWrapper *))(*(_QWORD *)v26 + 112LL))(v26);
      UnloadDrivers = DeviceListManager::ProcessDeviceArrival(v31, v40, v26);
    }
    v16 = UnloadDrivers;
    goto LABEL_18;
  }
  v6 = (char *)WiaTrace_TraceLogWithSubComp(
                 1,
                 "The Registry Device enumerator/handler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)");
  WriteDbgTraceWarningWI("RegistryDeviceEnumerator::ProcessEvent", v6);
  WiaTrcLib::Free((WiaTrcLib *)v6, v7);
  lpMem = (void **)WiaTrace_TraceWithSubComp(
                     1,
                     "The Registry Device enumerator/handler received an async request (dwTimeToWait == ASYNCH_WAIT_TIME)");
  WiaTrace_ProcessTrace_Ex(v10, v9, (void *)"RegistryDeviceEnumerator::ProcessEvent", 2, lpMem);
  v11 = (char *)WiaTrace_TraceLogWithSubComp(
                  1,
                  "    We currently only handle sync requests (i.e. dwTimeToWait must be ASYNCH_WAIT_TIME).");
  WriteDbgTraceWarningWI("RegistryDeviceEnumerator::ProcessEvent", v11);
  WiaTrcLib::Free((WiaTrcLib *)v11, v12);
  v13 = (void **)WiaTrace_TraceWithSubComp(
                   1,
                   "    We currently only handle sync requests (i.e. dwTimeToWait must be ASYNCH_WAIT_TIME).");
  WiaTrace_ProcessTrace_Ex(v15, v14, (void *)"RegistryDeviceEnumerator::ProcessEvent", 2, v13);
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x18000b780  push    rbp
0x18000b782  push    rbx
0x18000b783  push    rsi
0x18000b784  push    rdi
0x18000b785  push    r12
0x18000b787  push    r13
0x18000b789  push    r14
0x18000b78b  push    r15
0x18000b78d  lea     rbp, [rsp-328h]
0x18000b795  sub     rsp, 428h
0x18000b79c  mov     rax, cs:__security_cookie
0x18000b7a3  xor     rax, rsp
0x18000b7a6  mov     [rbp+360h+var_48], rax
0x18000b7ad  mov     rsi, [rbp+360h+arg_20]
0x18000b7b4  mov     edi, r9d
0x18000b7b7  cmp     edx, 0FFFFFFFFh
0x18000b7ba  jz      loc_18000B87E
0x18000b7c0  mov     edi, 1
0x18000b7c5  lea     rdx, aTheRegistryDev_0; "The Registry Device enumerator/handler "...
0x18000b7cc  mov     ecx, edi
0x18000b7ce  call    WiaTrace_TraceLogWithSubComp
0x18000b7d3  lea     r15, aRegistrydevice_4; "RegistryDeviceEnumerator::ProcessEvent"
0x18000b7da  mov     rdx, rax; char *
0x18000b7dd  mov     rcx, r15; char *
0x18000b7e0  mov     rbx, rax
0x18000b7e3  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000b7e8  mov     rcx, rbx; this
0x18000b7eb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000b7f0  lea     rdx, aTheRegistryDev_0; "The Registry Device enumerator/handler "...
0x18000b7f7  mov     ecx, edi
0x18000b7f9  call    WiaTrace_TraceWithSubComp
0x18000b7fe  lea     r12d, [rdi+1]
0x18000b802  mov     [rsp+460h+lpMem], rax; lpMem
0x18000b807  mov     r9d, r12d; int
0x18000b80a  mov     r8, r15; int
0x18000b80d  call    WiaTrace_ProcessTrace_Ex
0x18000b812  lea     rdx, aWeCurrentlyOnl; "    We currently only handle sync reque"...
0x18000b819  mov     ecx, edi
0x18000b81b  call    WiaTrace_TraceLogWithSubComp
0x18000b820  mov     rdx, rax; char *
0x18000b823  mov     rcx, r15; char *
0x18000b826  mov     rbx, rax
0x18000b829  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000b82e  mov     rcx, rbx; this
0x18000b831  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000b836  lea     rdx, aWeCurrentlyOnl; "    We currently only handle sync reque"...
0x18000b83d  mov     ecx, edi
0x18000b83f  call    WiaTrace_TraceWithSubComp
0x18000b844  mov     r9d, r12d; int
0x18000b847  mov     [rsp+460h+lpMem], rax; lpMem
0x18000b84c  mov     r8, r15; int
0x18000b84f  call    WiaTrace_ProcessTrace_Ex
0x18000b854  mov     ebx, 80070057h
0x18000b859  mov     eax, ebx
0x18000b85b  mov     rcx, [rbp+360h+var_48]
0x18000b862  xor     rcx, rsp; StackCookie
0x18000b865  call    __security_check_cookie
0x18000b86a  add     rsp, 428h
0x18000b871  pop     r15
0x18000b873  pop     r14
0x18000b875  pop     r13
0x18000b877  pop     r12
0x18000b879  pop     rdi
0x18000b87a  pop     rsi
0x18000b87b  pop     rbx
0x18000b87c  pop     rbp
0x18000b87d  retn
0x18000b87e  xor     ebx, ebx
0x18000b880  cmp     r8d, 0FEh
0x18000b887  jnz     short loc_18000B859
0x18000b889  lea     rax, aUnknownRegistr; "Unknown Registry Device Message"
0x18000b890  cmp     edi, 5
0x18000b893  mov     [rbp+360h+var_70], rax
0x18000b89a  lea     r12d, [rbx+2]
0x18000b89e  lea     rax, aRegDeviceEvent_0; "REG_DEVICE_EVENT_TYPE_QUICK_ACTIVATE"
0x18000b8a5  mov     ecx, r12d
0x18000b8a8  mov     [rbp+360h+var_68], rax
0x18000b8af  lea     r8, aMessageForRegi; "Message for Registry Device Enumerator:"...
0x18000b8b6  lea     rax, aRegDeviceEvent_1; "REG_DEVICE_EVENT_TYPE_QUICK_DEACTIVATE"
0x18000b8bd  mov     [rbp+360h+var_60], rax
0x18000b8c4  lea     rax, aRegDeviceEvent; "REG_DEVICE_EVENT_TYPE_SLOW_ACTIVATE"
0x18000b8cb  mov     [rbp+360h+var_58], rax
0x18000b8d2  lea     rax, aRegDeviceEvent_2; "REG_DEVICE_EVENT_TYPE_SLOW_DEACTIVATE"
0x18000b8d9  mov     [rbp+360h+var_50], rax
0x18000b8e0  sbb     eax, eax
0x18000b8e2  and     eax, edi
0x18000b8e4  xor     edx, edx
0x18000b8e6  mov     r14d, eax
0x18000b8e9  mov     r9, [rbp+rax*8+360h+var_70]
0x18000b8f1  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000b8f6  lea     r15, aRegistrydevice_4; "RegistryDeviceEnumerator::ProcessEvent"
0x18000b8fd  mov     rdx, rax; char *
0x18000b900  mov     rcx, r15; char *
0x18000b903  mov     rbx, rax
0x18000b906  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000b90b  mov     rcx, rbx; this
0x18000b90e  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000b913  mov     r9, [rbp+r14*8+360h+var_70]
0x18000b91b  lea     r8, aMessageForRegi; "Message for Registry Device Enumerator:"...
0x18000b922  xor     edx, edx
0x18000b924  mov     ecx, r12d
0x18000b927  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000b92c  lea     r13d, [r12+2]
0x18000b931  mov     [rsp+460h+lpMem], rax; lpMem
0x18000b936  mov     r9d, r13d; int
0x18000b939  mov     r8, r15; int
0x18000b93c  call    WiaTrace_ProcessTrace_Ex
0x18000b941  mov     rdx, rsi
0x18000b944  lea     rcx, [rbp+360h+var_2D0]
0x18000b94b  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000b950  lea     rdx, [rbp+360h+var_2D0]
0x18000b957  call    ?GetUSDWrapperFromDeviceList@@YAPEAVUSDWrapper@@JAEBV?$CSimpleStringBase@G@@@Z; GetUSDWrapperFromDeviceList(long,CSimpleStringBase<ushort> const &)
0x18000b95c  mov     rsi, rax
0x18000b95f  test    rax, rax
0x18000b962  jz      loc_18000BBB3
0x18000b968  mov     rax, [rax]
0x18000b96b  mov     rcx, rsi
0x18000b96e  mov     rax, [rax+98h]
0x18000b975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b97a  test    rax, rax
0x18000b97d  jz      loc_18000BB48
0x18000b983  xor     edx, edx
0x18000b985  mov     ecx, edi
0x18000b987  mov     [rsp+460h+var_420], edx
0x18000b98b  sub     ecx, 1
0x18000b98e  jz      short loc_18000B99A
0x18000b990  sub     ecx, 1
0x18000b993  jz      short loc_18000B9A1
0x18000b995  cmp     ecx, 1
0x18000b998  jnz     short loc_18000B9A1
0x18000b99a  mov     edx, r13d
0x18000b99d  mov     [rsp+460h+var_420], edx
0x18000b9a1  mov     [rax+4], edx
0x18000b9a4  lea     rcx, [rbp+360h+var_1A0]
0x18000b9ab  mov     rax, [rsi]
0x18000b9ae  lea     rdx, aDevicestate; "DeviceState"
0x18000b9b5  mov     rbx, [rax+0B8h]
0x18000b9bc  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000b9c1  lea     rdx, Class
0x18000b9c8  lea     rcx, [rsp+460h+var_400]
0x18000b9cd  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000b9d2  lea     rax, [rsp+460h+var_420]
0x18000b9d7  mov     [rsp+460h+var_438], r13d
0x18000b9dc  mov     [rsp+460h+lpMem], rax
0x18000b9e1  lea     r8, [rbp+360h+var_1A0]
0x18000b9e8  mov     rax, rbx
0x18000b9eb  lea     rdx, [rsp+460h+var_400]
0x18000b9f0  mov     r9d, r13d
0x18000b9f3  mov     rcx, rsi
0x18000b9f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9fb  lea     r13, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000ba02  mov     ebx, eax
0x18000ba04  lea     rcx, [rsp+460h+var_400]
0x18000ba09  mov     [rsp+460h+var_400], r13
0x18000ba0e  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000ba13  lea     rcx, [rbp+360h+var_1A0]
0x18000ba1a  mov     [rbp+360h+var_2F0], 0
0x18000ba22  mov     [rbp+360h+var_1A0], r13
0x18000ba29  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000ba2e  lea     rcx, [rsp+460h+var_418]; this
0x18000ba33  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18000ba38  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x18000ba3f  lea     rcx, [rsp+460h+var_400]
0x18000ba44  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18000ba49  lea     rdx, [rsp+460h+var_400]
0x18000ba4e  lea     rcx, [rsp+460h+var_418]
0x18000ba53  call    ??$Get@VDeviceListManager@@@ServiceComponentHolder@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x18000ba58  lea     rcx, [rsp+460h+var_400]
0x18000ba5d  mov     [rsp+460h+var_400], r13
0x18000ba62  mov     r14, rax
0x18000ba65  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000ba6a  mov     [rbp+360h+var_2F0], 0
0x18000ba72  test    r14, r14
0x18000ba75  jz      short loc_18000BAE2
0x18000ba77  sub     edi, 1
0x18000ba7a  jz      short loc_18000BAA9
0x18000ba7c  sub     edi, 1
0x18000ba7f  jz      short loc_18000BA9F
0x18000ba81  sub     edi, 1
0x18000ba84  jz      short loc_18000BA8B
0x18000ba86  cmp     edi, 1
0x18000ba89  jnz     short loc_18000BAC5
0x18000ba8b  xor     edx, edx; int
0x18000ba8d  mov     rcx, r14; this
0x18000ba90  call    ?Enumerate@DeviceListManager@@QEAAJJ@Z; DeviceListManager::Enumerate(long)
0x18000ba95  mov     rcx, r14; this
0x18000ba98  call    ?LoadUnloadDrivers@DeviceListManager@@QEAAJJ@Z; DeviceListManager::LoadUnloadDrivers(long)
0x18000ba9d  jmp     short loc_18000BAC3
0x18000ba9f  mov     r8, rsi; struct USDWrapper *
0x18000baa2  call    ?ProcessDeviceRemoval@DeviceListManager@@QEAAJJPEAVUSDWrapper@@@Z; DeviceListManager::ProcessDeviceRemoval(long,USDWrapper *)
0x18000baa7  jmp     short loc_18000BAC3
0x18000baa9  mov     rax, [rsi]
0x18000baac  mov     rcx, rsi
0x18000baaf  mov     rax, [rax+70h]
0x18000bab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab8  mov     r8, rsi; struct USDWrapper *
0x18000babb  mov     rcx, r14; this
0x18000babe  call    ?ProcessDeviceArrival@DeviceListManager@@QEAAJJPEAVUSDWrapper@@@Z; DeviceListManager::ProcessDeviceArrival(long,USDWrapper *)
0x18000bac3  mov     ebx, eax
0x18000bac5  mov     rax, [r14+8]
0x18000bac9  movsxd  rcx, dword ptr [rax+4]
0x18000bacd  add     rcx, 8
0x18000bad1  add     rcx, r14
0x18000bad4  mov     rax, [rcx]
0x18000bad7  mov     rax, [rax+10h]
0x18000badb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bae0  jmp     short loc_18000BB3C
0x18000bae2  mov     edi, 1
0x18000bae7  lea     r8, [rbp+360h+var_70]
0x18000baee  mov     ecx, edi
0x18000baf0  lea     rdx, aTheRegistryDev_2; "The Registry Device enumerator could no"...
0x18000baf7  call    WiaTrace_TraceLogWithSubComp
0x18000bafc  mov     rdx, rax; char *
0x18000baff  mov     rcx, r15; char *
0x18000bb02  mov     rbx, rax
0x18000bb05  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000bb0a  mov     rcx, rbx; this
0x18000bb0d  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bb12  lea     r8, [rbp+360h+var_70]
0x18000bb19  mov     ecx, edi
0x18000bb1b  lea     rdx, aTheRegistryDev_2; "The Registry Device enumerator could no"...
0x18000bb22  call    WiaTrace_TraceWithSubComp
0x18000bb27  mov     r9d, r12d; int
0x18000bb2a  mov     [rsp+460h+lpMem], rax; lpMem
0x18000bb2f  mov     r8, r15; int
0x18000bb32  call    WiaTrace_ProcessTrace_Ex
0x18000bb37  mov     ebx, 8000FFFFh
0x18000bb3c  lea     rcx, [rsp+460h+var_418]; this
0x18000bb41  call    ??1ServiceComponentHolder@@UEAA@XZ; ServiceComponentHolder::~ServiceComponentHolder(void)
0x18000bb46  jmp     short loc_18000BBA2
0x18000bb48  mov     r8, [rbp+360h+var_1C8]
0x18000bb4f  lea     rdx, aTheRegistryDev; "The Registry Device enumerator/handler "...
0x18000bb56  mov     edi, 1
0x18000bb5b  mov     ecx, edi
0x18000bb5d  call    WiaTrace_TraceLogWithSubComp
0x18000bb62  mov     rdx, rax; char *
0x18000bb65  mov     rcx, r15; char *
0x18000bb68  mov     rbx, rax
0x18000bb6b  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000bb70  mov     rcx, rbx; this
0x18000bb73  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bb78  mov     r8, [rbp+360h+var_1C8]
0x18000bb7f  lea     rdx, aTheRegistryDev; "The Registry Device enumerator/handler "...
0x18000bb86  mov     ecx, edi
0x18000bb88  call    WiaTrace_TraceWithSubComp
0x18000bb8d  mov     r9d, r12d; int
0x18000bb90  mov     [rsp+460h+lpMem], rax; lpMem
0x18000bb95  mov     r8, r15; int
0x18000bb98  call    WiaTrace_ProcessTrace_Ex
0x18000bb9d  mov     ebx, 80070057h
0x18000bba2  mov     rax, [rsi]
0x18000bba5  mov     rcx, rsi
0x18000bba8  mov     rax, [rax+10h]
0x18000bbac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb1  jmp     short loc_18000BC25
0x18000bbb3  mov     rax, [rbp+r14*8+360h+var_70]
0x18000bbbb  lea     r8, aCouldNotFindDe; "Could not find device (%ws)..ignoring m"...
0x18000bbc2  mov     r9, [rbp+360h+var_1C8]
0x18000bbc9  xor     edx, edx
0x18000bbcb  mov     ecx, r12d
0x18000bbce  mov     [rsp+460h+lpMem], rax
0x18000bbd3  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000bbd8  mov     rdx, rax; char *
0x18000bbdb  mov     rcx, r15; char *
0x18000bbde  mov     rbx, rax
0x18000bbe1  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18000bbe6  mov     rcx, rbx; this
0x18000bbe9  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000bbee  mov     rax, [rbp+r14*8+360h+var_70]
0x18000bbf6  lea     r8, aCouldNotFindDe; "Could not find device (%ws)..ignoring m"...
0x18000bbfd  mov     r9, [rbp+360h+var_1C8]
0x18000bc04  xor     edx, edx
0x18000bc06  mov     ecx, r12d
0x18000bc09  mov     [rsp+460h+lpMem], rax
0x18000bc0e  call    WiaTrace_TraceWithSubCompTraceLevel
0x18000bc13  mov     r9d, r13d; int
0x18000bc16  mov     [rsp+460h+lpMem], rax; lpMem
0x18000bc1b  mov     r8, r15; int
0x18000bc1e  call    WiaTrace_ProcessTrace_Ex
0x18000bc23  xor     ebx, ebx
0x18000bc25  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18000bc2c  lea     rcx, [rbp+360h+var_2D0]
0x18000bc33  mov     [rbp+360h+var_2D0], rax
0x18000bc3a  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18000bc3f  jmp     loc_18000B859
```
