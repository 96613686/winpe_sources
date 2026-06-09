# USDWrapper::ProcessDeviceEvent(_STINOTIFY *)

- ea: `0x18004c370`
- end: `0x18004c921`
- name: `?ProcessDeviceEvent@USDWrapper@@UEAAJPEAU_STINOTIFY@@@Z`
- size: `1457`
- prototype: `__int64 __fastcall(USDWrapper *this, struct _STINOTIFY *)`
- caller_count: `0`
- callee_count: `24`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800033f4`
- `0x180008b18`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18000f4fc`
- `0x180011a94`
- `0x180011c20`
- `0x1800174c4`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033cc0`
- `0x180034658`
- `0x180039664`
- `0x18004c370`
- `0x180051738`
- `0x180078010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x18004c6e2`
- `KERNEL32!EnterCriticalSection` at `0x18004c6e2`
- `KERNEL32!LeaveCriticalSection` at `0x18004c886`
- `KERNEL32!LeaveCriticalSection` at `0x18004c886`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c4fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c725`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c73d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c755`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c775`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c4fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c725`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c73d`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c755`
- `OLEAUT32!__imp_SysAllocString` at `0x18004c775`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c599`
- `OLEAUT32!__imp_SysFreeString` at `0x18004c599`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c7a0`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18004c7a0`

## string_xrefs

- `0x18004c692`: `Attempt to complete WiaRpc async RPC call...`
- `0x18004c6b8`: `Attempt to complete WiaRpc async RPC call...`
- `0x18004c7ae`: `RpcAsyncComplete failed with RPC error code 0x%X`
- `0x18004c7d2`: `RpcAsyncComplete failed with RPC error code 0x%X`
- `0x18004c63d`: `STI_DEVICE_EVENT, starting the WiaRpc service...`
- `0x18004c66a`: `STI_DEVICE_EVENT, starting the WiaRpc service...`
- `0x18004c7e8`: `Completed RPC call for STI event`
- `0x18004c80f`: `Completed RPC call for STI event`

## pseudocode

```c
__int64 __fastcall USDWrapper::ProcessDeviceEvent(USDWrapper *this, struct _STINOTIFY *a2)
{
  __int64 v4; // rbx
  char *v5; // rbx
  void *v6; // rdx
  void *lpMem; // rax
  int v8; // edx
  int v9; // ecx
  int v10; // r14d
  int DeviceSession; // eax
  __int64 v12; // rcx
  GUID guidNotificationCode; // xmm0
  const OLECHAR *v14; // rcx
  char *v15; // rbx
  void *v16; // rdx
  void *v17; // rax
  int v18; // edx
  int v19; // ecx
  char *v20; // rbx
  void *v21; // rdx
  void *v22; // rax
  int v23; // edx
  int v24; // ecx
  STI_CONN *v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  void *v28; // rax
  int v29; // edx
  int v30; // ecx
  char *v31; // rbx
  void *v32; // rdx
  void *v33; // rax
  int v34; // edx
  int v35; // ecx
  RPC_STATUS v36; // esi
  char *v37; // rbx
  void *v38; // rdx
  void *v39; // rax
  int v40; // edx
  int v41; // ecx
  int v42; // r9d
  char *v43; // rbx
  void *v44; // rdx
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
  int Reply; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v57; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v58[16]; // [rsp+40h] [rbp-C0h] BYREF
  int v59; // [rsp+50h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-A8h]
  int v61; // [rsp+60h] [rbp-A0h]
  GUID v62; // [rsp+64h] [rbp-9Ch]
  _QWORD v63[38]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v64[38]; // [rsp+1F0h] [rbp+F0h] BYREF

  v57 = 0;
  ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)v58);
  CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v63, L"DeviceInfoSet");
  v4 = ServiceComponentHolder::Get<DeviceInfoSet>(v58, v63);
  v63[0] = &CSimpleStringBase<unsigned short>::`vftable';
  CSimpleStringBase<unsigned short>::DeleteStorage(v63);
  v63[34] = 0;
  if ( v4 )
  {
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(v64, *((_QWORD *)this + 42));
    DeviceSession = DeviceInfoSet::GetDeviceSession(v4, v64, &v57);
    v64[0] = &CSimpleStringBase<unsigned short>::`vftable';
    v10 = DeviceSession;
    CSimpleStringBase<unsigned short>::DeleteStorage(v64);
    v12 = v4 + *(int *)(*(_QWORD *)v4 + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( v10 >= 0 )
    {
      if ( (*(unsigned int (__fastcall **)(USDWrapper *))(*(_QWORD *)this + 160LL))(this) )
      {
        memset_0(&v59, 0, 0x68u);
        guidNotificationCode = a2->guidNotificationCode;
        v14 = (const OLECHAR *)*((_QWORD *)this + 42);
        v59 = 104;
        v62 = guidNotificationCode;
        v61 = 84;
        bstrString = SysAllocString(v14);
        if ( bstrString )
        {
          v10 = CEventNotifier::NotifySTIEvent(
                  (CEventNotifier *)&g_eventNotifier,
                  (struct _WIANOTIFY *)&v59,
                  0,
                  (struct _WIA_DEVICE_SESSION_INFO *)&v57,
                  0);
          if ( v10 < 0 )
          {
            v15 = (char *)WiaTrace_TraceLogWithSubComp(
                            0,
                            "Detected error trying to notify registered handlers of event from (%ws)",
                            *((_QWORD *)this + 301));
            WriteDbgTraceWarningWI("USDWrapper::ProcessDeviceEvent", v15);
            WiaTrcLib::Free((WiaTrcLib *)v15, v16);
            v17 = (void *)WiaTrace_TraceWithSubComp(
                            0,
                            "Detected error trying to notify registered handlers of event from (%ws)",
                            *((_QWORD *)this + 301));
            WiaTrace_ProcessTrace_Ex(v19, v18, (int)"USDWrapper::ProcessDeviceEvent", 2, v17);
          }
          SysFreeString(bstrString);
        }
        else
        {
          v20 = (char *)WiaTrace_TraceLogWithSubComp(
                          0,
                          "We ran out of memory trying to process event from (%ws)...ignoring event",
                          *((_QWORD *)this + 301));
          WriteDbgTraceWarningWI("USDWrapper::ProcessDeviceEvent", v20);
          WiaTrcLib::Free((WiaTrcLib *)v20, v21);
          v22 = (void *)WiaTrace_TraceWithSubComp(
                          0,
                          "We ran out of memory trying to process event from (%ws)...ignoring event",
                          *((_QWORD *)this + 301));
          WiaTrace_ProcessTrace_Ex(v24, v23, (int)"USDWrapper::ProcessDeviceEvent", 2, v22);
          v10 = -2147024882;
        }
      }
      else
      {
        if ( *((_DWORD *)this + 1012) )
        {
          v25 = *(STI_CONN **)(*((_QWORD *)this + 504) + 8LL);
          if ( v25 )
            STI_CONN::QueueNotificationToProcess(v25, a2);
        }
        if ( *((_DWORD *)this + 11) )
        {
          v50 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                          2,
                          0,
                          "Ignoring event from device (%ws) since notifications have been diabled for this device",
                          *((_QWORD *)this + 301));
          WriteDbgTraceInfoWI("USDWrapper::ProcessDeviceEvent", v50);
          WiaTrcLib::Free((WiaTrcLib *)v50, v51);
          v52 = (void *)WiaTrace_TraceWithSubCompTraceLevel(
                          2,
                          0,
                          "Ignoring event from device (%ws) since notifications have been diabled for this device",
                          *((_QWORD *)this + 301));
          WiaTrace_ProcessTrace_Ex(v54, v53, (int)"USDWrapper::ProcessDeviceEvent", 4, v52);
        }
        else if ( a2 )
        {
          v26 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "STI_DEVICE_EVENT, starting the WiaRpc service...");
          WriteDbgTraceInfoWI("USDWrapper::ProcessDeviceEvent", v26);
          WiaTrcLib::Free((WiaTrcLib *)v26, v27);
          v28 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "STI_DEVICE_EVENT, starting the WiaRpc service...");
          WiaTrace_ProcessTrace_Ex(v30, v29, (int)"USDWrapper::ProcessDeviceEvent", 4, v28);
          StartWiaRpcService();
          v31 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Attempt to complete WiaRpc async RPC call...");
          WriteDbgTraceInfoWI("USDWrapper::ProcessDeviceEvent", v31);
          WiaTrcLib::Free((WiaTrcLib *)v31, v32);
          v33 = (void *)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Attempt to complete WiaRpc async RPC call...");
          WiaTrace_ProcessTrace_Ex(v35, v34, (int)"USDWrapper::ProcessDeviceEvent", 4, v33);
          EnterCriticalSection(&CriticalSection);
          if ( g_RpcEvent )
          {
            Reply = 1;
            *(_QWORD *)(qword_1800B1700 + 60) = v57;
            *(GUID *)qword_1800B1700 = a2->guidNotificationCode;
            *(_QWORD *)(qword_1800B1700 + 16) = SysAllocString(&Class);
            *(_QWORD *)(qword_1800B1700 + 24) = SysAllocString(*((const OLECHAR **)this + 42));
            *(_QWORD *)(qword_1800B1700 + 32) = SysAllocString(*((const OLECHAR **)this + 190));
            *(_DWORD *)(qword_1800B1700 + 40) = *((_DWORD *)this + 16);
            *(_QWORD *)(qword_1800B1700 + 48) = SysAllocString(0);
            *(_DWORD *)(qword_1800B1700 + 56) = -268435456;
            v36 = RpcAsyncCompleteCall(g_RpcEvent, &Reply);
            if ( v36 )
            {
              v37 = (char *)WiaTrace_TraceLog("RpcAsyncComplete failed with RPC error code 0x%X");
              WriteDbgTraceErrorWI("USDWrapper::ProcessDeviceEvent", v37);
              WiaTrcLib::Free((WiaTrcLib *)v37, v38);
              v39 = (void *)WiaTrace_Trace("RpcAsyncComplete failed with RPC error code 0x%X", v36);
              v42 = 1;
            }
            else
            {
              v43 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(2, 0, "Completed RPC call for STI event");
              WriteDbgTraceInfoWI("USDWrapper::ProcessDeviceEvent", v43);
              WiaTrcLib::Free((WiaTrcLib *)v43, v44);
              v39 = (void *)WiaTrace_TraceWithSubCompTraceLevel(2, 0, "Completed RPC call for STI event");
              v42 = 4;
            }
            WiaTrace_ProcessTrace_Ex(v41, v40, (int)"USDWrapper::ProcessDeviceEvent", v42, v39);
            g_RpcEvent = 0;
          }
          else
          {
            v45 = (char *)WiaTrace_TraceLog("There was no WiaRpc async RPC call!");
            WriteDbgTraceErrorWI("USDWrapper::ProcessDeviceEvent", v45);
            WiaTrcLib::Free((WiaTrcLib *)v45, v46);
            v47 = (void *)WiaTrace_Trace("There was no WiaRpc async RPC call!");
            WiaTrace_ProcessTrace_Ex(v49, v48, (int)"USDWrapper::ProcessDeviceEvent", 1, v47);
          }
          LeaveCriticalSection(&CriticalSection);
        }
      }
    }
  }
  else
  {
    v5 = (char *)WiaTrace_TraceLogWithSubComp(
                   1,
                   "Could not get SessionID because the DeviceInfoSet object could not be found!");
    WriteDbgTraceWarningWI("USDWrapper::ProcessDeviceEvent", v5);
    WiaTrcLib::Free((WiaTrcLib *)v5, v6);
    lpMem = (void *)WiaTrace_TraceWithSubComp(
                      1,
                      "Could not get SessionID because the DeviceInfoSet object could not be found!");
    WiaTrace_ProcessTrace_Ex(v9, v8, (int)"USDWrapper::ProcessDeviceEvent", 2, lpMem);
    v10 = -2147418113;
  }
  ServiceComponentHolder::~ServiceComponentHolder((ServiceComponentHolder *)v58);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004c370  mov     [rsp-8+arg_10], rbx
0x18004c375  push    rbp
0x18004c376  push    rsi
0x18004c377  push    rdi
0x18004c378  push    r14
0x18004c37a  push    r15
0x18004c37c  lea     rbp, [rsp-230h]
0x18004c384  sub     rsp, 330h
0x18004c38b  mov     rax, cs:__security_cookie
0x18004c392  xor     rax, rsp
0x18004c395  mov     [rbp+250h+var_30], rax
0x18004c39c  mov     rsi, rcx
0x18004c39f  mov     [rsp+350h+var_318], 0
0x18004c3a8  lea     rcx, [rsp+350h+var_310]; this
0x18004c3ad  mov     r15, rdx
0x18004c3b0  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x18004c3b5  lea     rdx, aDeviceinfoset; "DeviceInfoSet"
0x18004c3bc  lea     rcx, [rbp+250h+var_290]
0x18004c3c0  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18004c3c5  lea     rdx, [rbp+250h+var_290]
0x18004c3c9  lea     rcx, [rsp+350h+var_310]
0x18004c3ce  call    ??$Get@VDeviceInfoSet@@@ServiceComponentHolder@@QEAAPEAVDeviceInfoSet@@AEBV?$CSimpleStringBase@G@@@Z; ServiceComponentHolder::Get<DeviceInfoSet>(CSimpleStringBase<ushort> const &)
0x18004c3d3  lea     rdi, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x18004c3da  mov     rbx, rax
0x18004c3dd  lea     rcx, [rbp+250h+var_290]
0x18004c3e1  mov     [rbp+250h+var_290], rdi
0x18004c3e5  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004c3ea  mov     [rbp+250h+var_180], 0
0x18004c3f5  test    rbx, rbx
0x18004c3f8  jnz     short loc_18004C455
0x18004c3fa  lea     rdx, aCouldNotGetSes; "Could not get SessionID because the Dev"...
0x18004c401  lea     ecx, [rbx+1]
0x18004c404  call    WiaTrace_TraceLogWithSubComp
0x18004c409  lea     rdi, aUsdwrapperProc; "USDWrapper::ProcessDeviceEvent"
0x18004c410  mov     rdx, rax; char *
0x18004c413  mov     rcx, rdi; char *
0x18004c416  mov     rbx, rax
0x18004c419  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004c41e  mov     rcx, rbx; this
0x18004c421  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c426  lea     rdx, aCouldNotGetSes; "Could not get SessionID because the Dev"...
0x18004c42d  mov     ecx, 1
0x18004c432  call    WiaTrace_TraceWithSubComp
0x18004c437  mov     r9d, 2; int
0x18004c43d  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c442  mov     r8, rdi; int
0x18004c445  call    WiaTrace_ProcessTrace_Ex
0x18004c44a  mov     r14d, 8000FFFFh
0x18004c450  jmp     loc_18004C8EE
0x18004c455  mov     rdx, [rsi+150h]
0x18004c45c  lea     rcx, [rbp+250h+var_160]
0x18004c463  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x18004c468  lea     r8, [rsp+350h+var_318]
0x18004c46d  mov     rcx, rbx
0x18004c470  lea     rdx, [rbp+250h+var_160]
0x18004c477  call    ?GetDeviceSession@DeviceInfoSet@@QEAAJAEBV?$CSimpleStringBase@G@@AEAU_WIA_DEVICE_SESSION_INFO@@@Z; DeviceInfoSet::GetDeviceSession(CSimpleStringBase<ushort> const &,_WIA_DEVICE_SESSION_INFO &)
0x18004c47c  lea     rcx, [rbp+250h+var_160]
0x18004c483  mov     [rbp+250h+var_160], rdi
0x18004c48a  mov     r14d, eax
0x18004c48d  call    ?DeleteStorage@?$CSimpleStringBase@G@@AEAAXXZ; CSimpleStringBase<ushort>::DeleteStorage(void)
0x18004c492  mov     rcx, [rbx]
0x18004c495  movsxd  rcx, dword ptr [rcx+4]
0x18004c499  add     rcx, rbx
0x18004c49c  mov     rdx, [rcx]
0x18004c49f  mov     rax, [rdx+10h]
0x18004c4a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4a8  test    r14d, r14d
0x18004c4ab  js      loc_18004C8EE
0x18004c4b1  mov     rax, [rsi]
0x18004c4b4  mov     rcx, rsi
0x18004c4b7  mov     rax, [rax+0A0h]
0x18004c4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c4c3  test    eax, eax
0x18004c4c5  jz      loc_18004C609
0x18004c4cb  mov     ebx, 68h ; 'h'
0x18004c4d0  lea     rcx, [rsp+350h+var_300]; void *
0x18004c4d5  mov     r8d, ebx; Size
0x18004c4d8  xor     edx, edx; Val
0x18004c4da  call    memset_0
0x18004c4df  movups  xmm0, xmmword ptr [r15+4]
0x18004c4e4  mov     rcx, [rsi+150h]; psz
0x18004c4eb  mov     [rsp+350h+var_300], ebx
0x18004c4ef  movdqu  [rsp+350h+var_2EC], xmm0
0x18004c4f5  mov     [rsp+350h+var_2F0], 54h ; 'T'
0x18004c4fd  call    cs:__imp_SysAllocString
0x18004c503  mov     [rsp+350h+bstrString], rax
0x18004c508  test    rax, rax
0x18004c50b  jz      loc_18004C5A4
0x18004c511  lea     r9, [rsp+350h+var_318]; struct _WIA_DEVICE_SESSION_INFO *
0x18004c516  mov     [rsp+350h+lpMem], 0; unsigned __int16 *
0x18004c51f  xor     r8d, r8d; unsigned int
0x18004c522  lea     rdx, [rsp+350h+var_300]; struct _WIANOTIFY *
0x18004c527  lea     rcx, ?g_eventNotifier@@3VCEventNotifier@@A; this
0x18004c52e  call    ?NotifySTIEvent@CEventNotifier@@QEAAJPEAU_WIANOTIFY@@KAEAU_WIA_DEVICE_SESSION_INFO@@PEAG@Z; CEventNotifier::NotifySTIEvent(_WIANOTIFY *,ulong,_WIA_DEVICE_SESSION_INFO &,ushort *)
0x18004c533  mov     r14d, eax
0x18004c536  test    eax, eax
0x18004c538  jns     short loc_18004C594
0x18004c53a  mov     r8, [rsi+968h]
0x18004c541  lea     rdx, aDetectedErrorT; "Detected error trying to notify registe"...
0x18004c548  xor     ecx, ecx
0x18004c54a  call    WiaTrace_TraceLogWithSubComp
0x18004c54f  lea     rdi, aUsdwrapperProc; "USDWrapper::ProcessDeviceEvent"
0x18004c556  mov     rdx, rax; char *
0x18004c559  mov     rcx, rdi; char *
0x18004c55c  mov     rbx, rax
0x18004c55f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004c564  mov     rcx, rbx; this
0x18004c567  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c56c  mov     r8, [rsi+968h]
0x18004c573  lea     rdx, aDetectedErrorT; "Detected error trying to notify registe"...
0x18004c57a  xor     ecx, ecx
0x18004c57c  call    WiaTrace_TraceWithSubComp
0x18004c581  mov     r9d, 2; int
0x18004c587  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c58c  mov     r8, rdi; int
0x18004c58f  call    WiaTrace_ProcessTrace_Ex
0x18004c594  mov     rcx, [rsp+350h+bstrString]; bstrString
0x18004c599  call    cs:__imp_SysFreeString
0x18004c59f  jmp     loc_18004C8EE
0x18004c5a4  mov     r8, [rsi+968h]
0x18004c5ab  lea     rdx, aWeRanOutOfMemo; "We ran out of memory trying to process "...
0x18004c5b2  xor     ecx, ecx
0x18004c5b4  call    WiaTrace_TraceLogWithSubComp
0x18004c5b9  lea     rdi, aUsdwrapperProc; "USDWrapper::ProcessDeviceEvent"
0x18004c5c0  mov     rdx, rax; char *
0x18004c5c3  mov     rcx, rdi; char *
0x18004c5c6  mov     rbx, rax
0x18004c5c9  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18004c5ce  mov     rcx, rbx; this
0x18004c5d1  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c5d6  mov     r8, [rsi+968h]
0x18004c5dd  lea     rdx, aWeRanOutOfMemo; "We ran out of memory trying to process "...
0x18004c5e4  xor     ecx, ecx
0x18004c5e6  call    WiaTrace_TraceWithSubComp
0x18004c5eb  mov     r9d, 2; int
0x18004c5f1  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c5f6  mov     r8, rdi; int
0x18004c5f9  call    WiaTrace_ProcessTrace_Ex
0x18004c5fe  mov     r14d, 8007000Eh
0x18004c604  jmp     loc_18004C8EE
0x18004c609  cmp     dword ptr [rsi+0FD0h], 0
0x18004c610  jz      short loc_18004C62A
0x18004c612  mov     rax, [rsi+0FC0h]
0x18004c619  mov     rcx, [rax+8]; this
0x18004c61d  test    rcx, rcx
0x18004c620  jz      short loc_18004C62A
0x18004c622  mov     rdx, r15; Src
0x18004c625  call    ?QueueNotificationToProcess@STI_CONN@@QEAAHPEAU_STINOTIFY@@@Z; STI_CONN::QueueNotificationToProcess(_STINOTIFY *)
0x18004c62a  cmp     dword ptr [rsi+2Ch], 0
0x18004c62e  jnz     loc_18004C88E
0x18004c634  test    r15, r15
0x18004c637  jz      loc_18004C8EE
0x18004c63d  lea     r8, aStiDeviceEvent; "STI_DEVICE_EVENT, starting the WiaRpc s"...
0x18004c644  xor     edx, edx
0x18004c646  xor     ecx, ecx
0x18004c648  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004c64d  lea     rdi, aUsdwrapperProc; "USDWrapper::ProcessDeviceEvent"
0x18004c654  mov     rdx, rax; char *
0x18004c657  mov     rcx, rdi; char *
0x18004c65a  mov     rbx, rax
0x18004c65d  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004c662  mov     rcx, rbx; this
0x18004c665  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c66a  lea     r8, aStiDeviceEvent; "STI_DEVICE_EVENT, starting the WiaRpc s"...
0x18004c671  xor     edx, edx
0x18004c673  xor     ecx, ecx
0x18004c675  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004c67a  mov     r9d, 4; int
0x18004c680  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c685  mov     r8, rdi; int
0x18004c688  call    WiaTrace_ProcessTrace_Ex
0x18004c68d  call    ?StartWiaRpcService@@YAHXZ; StartWiaRpcService(void)
0x18004c692  lea     r8, aAttemptToCompl; "Attempt to complete WiaRpc async RPC ca"...
0x18004c699  xor     edx, edx
0x18004c69b  xor     ecx, ecx
0x18004c69d  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004c6a2  mov     rdx, rax; char *
0x18004c6a5  mov     rcx, rdi; char *
0x18004c6a8  mov     rbx, rax
0x18004c6ab  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004c6b0  mov     rcx, rbx; this
0x18004c6b3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c6b8  lea     r8, aAttemptToCompl; "Attempt to complete WiaRpc async RPC ca"...
0x18004c6bf  xor     edx, edx
0x18004c6c1  xor     ecx, ecx
0x18004c6c3  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004c6c8  mov     r9d, 4; int
0x18004c6ce  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c6d3  mov     r8, rdi; int
0x18004c6d6  call    WiaTrace_ProcessTrace_Ex
0x18004c6db  lea     rcx, CriticalSection; lpCriticalSection
0x18004c6e2  call    cs:__imp_EnterCriticalSection
0x18004c6e8  cmp     cs:?g_RpcEvent@@3UWIAEVENTRPCSTRUCT@@A, 0; WIAEVENTRPCSTRUCT g_RpcEvent
0x18004c6f0  jz      loc_18004C83E
0x18004c6f6  mov     rax, cs:qword_1800B1700
0x18004c6fd  mov     rcx, [rsp+350h+var_318]
0x18004c702  mov     [rsp+350h+Reply], 1
0x18004c70a  mov     [rax+3Ch], rcx
0x18004c70e  lea     rcx, Class; psz
0x18004c715  mov     rax, cs:qword_1800B1700
0x18004c71c  movups  xmm0, xmmword ptr [r15+4]
0x18004c721  movdqu  xmmword ptr [rax], xmm0
0x18004c725  call    cs:__imp_SysAllocString
0x18004c72b  mov     rcx, cs:qword_1800B1700
0x18004c732  mov     [rcx+10h], rax
0x18004c736  mov     rcx, [rsi+150h]; psz
0x18004c73d  call    cs:__imp_SysAllocString
0x18004c743  mov     rcx, cs:qword_1800B1700
0x18004c74a  mov     [rcx+18h], rax
0x18004c74e  mov     rcx, [rsi+5F0h]; psz
0x18004c755  call    cs:__imp_SysAllocString
0x18004c75b  mov     rcx, cs:qword_1800B1700
0x18004c762  mov     [rcx+20h], rax
0x18004c766  mov     ecx, [rsi+40h]
0x18004c769  mov     rax, cs:qword_1800B1700
0x18004c770  mov     [rax+28h], ecx
0x18004c773  xor     ecx, ecx; psz
0x18004c775  call    cs:__imp_SysAllocString
0x18004c77b  mov     rcx, cs:qword_1800B1700
0x18004c782  lea     rdx, [rsp+350h+Reply]; Reply
0x18004c787  mov     [rcx+30h], rax
0x18004c78b  mov     rax, cs:qword_1800B1700
0x18004c792  mov     dword ptr [rax+38h], 0F0000000h
0x18004c799  mov     rcx, cs:?g_RpcEvent@@3UWIAEVENTRPCSTRUCT@@A; pAsync
0x18004c7a0  call    cs:__imp_RpcAsyncCompleteCall
0x18004c7a6  mov     esi, eax
0x18004c7a8  test    eax, eax
0x18004c7aa  jz      short loc_18004C7E6
0x18004c7ac  mov     edx, eax
0x18004c7ae  lea     rcx, aRpcasynccomple_0; "RpcAsyncComplete failed with RPC error "...
0x18004c7b5  call    WiaTrace_TraceLog
0x18004c7ba  mov     rdx, rax; char *
0x18004c7bd  mov     rcx, rdi; char *
0x18004c7c0  mov     rbx, rax
0x18004c7c3  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004c7c8  mov     rcx, rbx; this
0x18004c7cb  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c7d0  mov     edx, esi
0x18004c7d2  lea     rcx, aRpcasynccomple_0; "RpcAsyncComplete failed with RPC error "...
0x18004c7d9  call    WiaTrace_Trace
0x18004c7de  mov     r9d, 1
0x18004c7e4  jmp     short loc_18004C824
0x18004c7e6  xor     edx, edx
0x18004c7e8  lea     r8, aCompletedRpcCa; "Completed RPC call for STI event"
0x18004c7ef  lea     ecx, [rdx+2]
0x18004c7f2  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004c7f7  mov     rdx, rax; char *
0x18004c7fa  mov     rcx, rdi; char *
0x18004c7fd  mov     rbx, rax
0x18004c800  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004c805  mov     rcx, rbx; this
0x18004c808  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c80d  xor     edx, edx
0x18004c80f  lea     r8, aCompletedRpcCa; "Completed RPC call for STI event"
0x18004c816  lea     ecx, [rdx+2]
0x18004c819  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004c81e  mov     r9d, 4; int
0x18004c824  mov     r8, rdi; int
0x18004c827  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c82c  call    WiaTrace_ProcessTrace_Ex
0x18004c831  mov     cs:?g_RpcEvent@@3UWIAEVENTRPCSTRUCT@@A, 0; WIAEVENTRPCSTRUCT g_RpcEvent
0x18004c83c  jmp     short loc_18004C87F
0x18004c83e  lea     rcx, aThereWasNoWiar; "There was no WiaRpc async RPC call!"
0x18004c845  call    WiaTrace_TraceLog
0x18004c84a  mov     rdx, rax; char *
0x18004c84d  mov     rcx, rdi; char *
0x18004c850  mov     rbx, rax
0x18004c853  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18004c858  mov     rcx, rbx; this
0x18004c85b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c860  lea     rcx, aThereWasNoWiar; "There was no WiaRpc async RPC call!"
0x18004c867  call    WiaTrace_Trace
0x18004c86c  mov     r9d, 1; int
0x18004c872  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c877  mov     r8, rdi; int
0x18004c87a  call    WiaTrace_ProcessTrace_Ex
0x18004c87f  lea     rcx, CriticalSection; lpCriticalSection
0x18004c886  call    cs:__imp_LeaveCriticalSection
0x18004c88c  jmp     short loc_18004C8EE
0x18004c88e  mov     r9, [rsi+968h]
0x18004c895  lea     r8, aIgnoringEventF; "Ignoring event from device (%ws) since "...
0x18004c89c  xor     edx, edx
0x18004c89e  lea     ecx, [rdx+2]
0x18004c8a1  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18004c8a6  lea     rdi, aUsdwrapperProc; "USDWrapper::ProcessDeviceEvent"
0x18004c8ad  mov     rdx, rax; char *
0x18004c8b0  mov     rcx, rdi; char *
0x18004c8b3  mov     rbx, rax
0x18004c8b6  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18004c8bb  mov     rcx, rbx; this
0x18004c8be  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18004c8c3  mov     r9, [rsi+968h]
0x18004c8ca  lea     r8, aIgnoringEventF; "Ignoring event from device (%ws) since "...
0x18004c8d1  xor     edx, edx
0x18004c8d3  lea     ecx, [rdx+2]
0x18004c8d6  call    WiaTrace_TraceWithSubCompTraceLevel
0x18004c8db  mov     r9d, 4; int
0x18004c8e1  mov     [rsp+350h+lpMem], rax; lpMem
0x18004c8e6  mov     r8, rdi; int
0x18004c8e9  call    WiaTrace_ProcessTrace_Ex
  ... truncated ...
```
