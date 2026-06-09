# WiaService::CheckForActivityAndShutdown(void)

- ea: `0x18000557c`
- end: `0x180005a40`
- name: `?CheckForActivityAndShutdown@WiaService@@QEAAJXZ`
- size: `1220`
- prototype: `__int64 __fastcall(WiaService *__hidden this)`
- caller_count: `4`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004f60`
- `0x180004ff8`
- `0x18000ecf0`
- `0x180045cd4`

## callees

- `0x18000557c`
- `0x180009210`
- `0x18000a974`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000f4fc`
- `0x18000fcfc`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180033878`
- `0x180033884`
- `0x180033cc0`
- `0x180078010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800058bb`
- `ADVAPI32!RegCloseKey` at `0x1800058bb`
- `ADVAPI32!RegOpenKeyExW` at `0x18000569b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000569b`
- `ADVAPI32!RegQueryValueExW` at `0x1800056db`
- `ADVAPI32!RegQueryValueExW` at `0x1800056db`

## string_xrefs

- `0x1800057c3`: `ServiceComponentHolder::Get`
- `0x1800057f5`: `ServiceComponentHolder::Get`
- `0x1800057b0`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x1800057de`: `Could not retrieve (%ws) because the ServiceComponentHolder is NULL`
- `0x180005810`: `Unable to initiate possible shutdown of service - cannot get reference to DeviceListManager`
- `0x18000583b`: `Unable to initiate possible shutdown of service - cannot get reference to DeviceListManager`
- `0x1800056a1`: `WiaService::CheckForActivityAndShutdown`
- `0x18000581e`: `WiaService::CheckForActivityAndShutdown`
- `0x18000599e`: `WiaService::CheckForActivityAndShutdown`
- `0x1800059fc`: `WiaService::CheckForActivityAndShutdown`
- `0x18000586f`: `Malformed registry value for shutdown timeout found, DWORD expected, shutdown not initiated`
- `0x180005894`: `Malformed registry value for shutdown timeout found, DWORD expected, shutdown not initiated`
- `0x180005945`: `StiRpc Error: Out of memory (new returned zero) attempting to allocate callback for server shutdown`
- `0x18000596a`: `StiRpc Error: Out of memory (new returned zero) attempting to allocate callback for server shutdown`
- `0x18000598a`: `Not shutting down service because %d devices are installed`
- `0x1800059be`: `Not shutting down service because %d devices are installed`
- `0x1800059eb`: `Last client released reference to service, not initiating shutdown because another shutdown is already pending.`
- `0x180005a19`: `Last client released reference to service, not initiating shutdown because another shutdown is already pending.`

## pseudocode

```c
__int64 __fastcall WiaService::CheckForActivityAndShutdown(WiaService *this)
{
  __int64 v2; // r14
  unsigned __int64 v3; // rdx
  __int64 v4; // rdi
  unsigned int v5; // esi
  int v6; // r12d
  __int64 v7; // rcx
  unsigned int v8; // r15d
  char *v9; // rbx
  void *v10; // rdx
  void **v11; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  char *v16; // rbx
  void *v17; // rdx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  char *v21; // rbx
  void *v22; // rdx
  void **v23; // rax
  void *v24; // rdx
  __int64 v25; // rcx
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  struct IUnknown *v31; // rax
  struct IUnknown *v32; // rbx
  unsigned int v33; // eax
  char *v34; // rbx
  void *v35; // rdx
  void **v36; // rax
  void *v37; // rdx
  __int64 v38; // rcx
  char *v39; // rbx
  void *v40; // rdx
  int v41; // r9d
  char *v42; // rbx
  void *v43; // rdx
  char *v44; // rbx
  void *v45; // rdx
  void **v46; // rax
  void *v47; // rdx
  __int64 v48; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v54; // [rsp+48h] [rbp-B8h]
  const unsigned __int64 *v55; // [rsp+50h] [rbp-B0h] BYREF
  char v56; // [rsp+58h] [rbp-A8h] BYREF
  void *v57; // [rsp+158h] [rbp+58h]
  __int64 v58; // [rsp+160h] [rbp+60h]

  if ( !*((_DWORD *)this + 6) )
  {
    if ( *((_DWORD *)this + 4) )
      return 0;
    ServiceComponentHolder::ServiceComponentHolder((ServiceComponentHolder *)&hKey);
    CSimpleStringBase<unsigned short>::CSimpleStringBase<unsigned short>(&v55, L"DeviceListManager");
    v2 = v54;
    if ( v54 )
    {
      v4 = CSimpleRefMap<CSimpleStringBase<unsigned short>>::Get<DeviceListManager>(v54, &v55);
    }
    else
    {
      v4 = 0;
      v16 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                      v57);
      WriteDbgTraceWarningWI("ServiceComponentHolder::Get", v16);
      WiaTrcLib::Free((WiaTrcLib *)v16, v17);
      v18 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "Could not retrieve (%ws) because the ServiceComponentHolder is NULL",
                       v57);
      WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"ServiceComponentHolder::Get", 2, v18);
    }
    v55 = &CSimpleStringBase<unsigned short>::`vftable';
    if ( v57 && v57 != &v56 )
      operator delete(v57, v3);
    v57 = 0;
    v58 = 0;
    if ( v4 )
    {
      v5 = 0;
      v6 = *(_DWORD *)(v4 + 80);
      v7 = v4 + *(int *)(*(_QWORD *)(v4 + 8) + 4LL) + 8LL;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      if ( v6 )
      {
        v42 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                        0x80000000LL,
                        0,
                        "Not shutting down service because %d devices are installed",
                        v6);
        WriteDbgTraceInfoWI("WiaService::CheckForActivityAndShutdown", v42);
        WiaTrcLib::Free((WiaTrcLib *)v42, v43);
        v36 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                         0x80000000LL,
                         0,
                         "Not shutting down service because %d devices are installed",
                         v6);
        v41 = 4;
        goto LABEL_17;
      }
      hKey = 0;
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( RegOpenKeyExW(
             HKEY_LOCAL_MACHINE,
             L"System\\CurrentControlSet\\Control\\StillImage\\ServerSettings",
             0,
             1u,
             &hKey) )
      {
        goto LABEL_29;
      }
      v8 = 0;
      if ( !RegQueryValueExW(hKey, L"ShutdownIfUnusedDelay", 0, &Type, Data, &cbData) )
      {
        if ( Type == 4 )
        {
          if ( *(_DWORD *)Data )
          {
            if ( *(_DWORD *)Data <= 0x20C49Bu )
            {
              v8 = 1000 * *(_DWORD *)Data;
            }
            else
            {
              v9 = (char *)WiaTrace_TraceLogWithSubComp(1, "DWORD overflow in timeout time, maximum time assumed");
              WriteDbgTraceWarningWI("WiaService::CheckForActivityAndShutdown", v9);
              WiaTrcLib::Free((WiaTrcLib *)v9, v10);
              v11 = (void **)WiaTrace_TraceWithSubComp(1, "DWORD overflow in timeout time, maximum time assumed");
              WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"WiaService::CheckForActivityAndShutdown", 2, v11);
              v8 = 0x7FFFFFFF;
            }
          }
        }
        else
        {
          v26 = (char *)WiaTrace_TraceLogWithSubComp(
                          1,
                          "Malformed registry value for shutdown timeout found, DWORD expected, shutdown not initiated");
          WriteDbgTraceWarningWI("WiaService::CheckForActivityAndShutdown", v26);
          WiaTrcLib::Free((WiaTrcLib *)v26, v27);
          v28 = (void **)WiaTrace_TraceWithSubComp(
                           1,
                           "Malformed registry value for shutdown timeout found, DWORD expected, shutdown not initiated");
          WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"WiaService::CheckForActivityAndShutdown", 2, v28);
        }
      }
      RegCloseKey(hKey);
      if ( !v8 )
      {
LABEL_29:
        v39 = (char *)WiaTrace_TraceLogWithSubComp(
                        1,
                        "StiRpc Error: Out of memory (new returned zero) attempting to allocate callback for server shutdown");
        WriteDbgTraceWarningWI("WiaService::CheckForActivityAndShutdown", v39);
        WiaTrcLib::Free((WiaTrcLib *)v39, v40);
        v36 = (void **)WiaTrace_TraceWithSubComp(
                         1,
                         "StiRpc Error: Out of memory (new returned zero) attempting to allocate callback for server shutdown");
        goto LABEL_30;
      }
      v31 = (struct IUnknown *)operator new(0x10u);
      v32 = v31;
      if ( v31 )
      {
        LODWORD(v31[1].lpVtbl) = 1;
        v31->lpVtbl = (struct IUnknownVtbl *)&WiaService::CShutdownScheduledTask::`vftable';
        WiaEventInfo::AddRef((WiaEventInfo *)v31);
        v33 = ScheduleWorkItem(
                (void (*)(struct IUnknown *))WiaService::CShutdownScheduledTask::StopServiceCallback,
                v32,
                v8,
                0,
                phkResult);
        *((_DWORD *)this + 6) = v33;
        if ( !v33 )
        {
          v34 = (char *)WiaTrace_TraceLogWithSubComp(
                          1,
                          "StiRpc Error: Failure to schedule callback for server shutdown");
          WriteDbgTraceWarningWI("WiaService::CheckForActivityAndShutdown", v34);
          WiaTrcLib::Free((WiaTrcLib *)v34, v35);
          v36 = (void **)WiaTrace_TraceWithSubComp(1, "StiRpc Error: Failure to schedule callback for server shutdown");
LABEL_30:
          v41 = 2;
LABEL_17:
          WiaTrace_ProcessTrace_Ex(v38, v37, (void *)"WiaService::CheckForActivityAndShutdown", v41, v36);
        }
      }
    }
    else
    {
      v21 = (char *)WiaTrace_TraceLogWithSubComp(
                      1,
                      "Unable to initiate possible shutdown of service - cannot get reference to DeviceListManager");
      WriteDbgTraceWarningWI("WiaService::CheckForActivityAndShutdown", v21);
      WiaTrcLib::Free((WiaTrcLib *)v21, v22);
      v23 = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "Unable to initiate possible shutdown of service - cannot get reference to DeviceListManager");
      WiaTrace_ProcessTrace_Ex(v25, v24, (void *)"WiaService::CheckForActivityAndShutdown", 2, v23);
      v5 = -2147418113;
    }
    if ( v2 )
    {
      v14 = v2 + *(int *)(*(_QWORD *)v2 + 4LL);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    }
    return v5;
  }
  v5 = 0;
  if ( !*((_DWORD *)this + 4) )
  {
    v44 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                    0x80000000LL,
                    0,
                    "Last client released reference to service, not initiating shutdown because another shutdown is already pending.");
    WriteDbgTraceInfoWI("WiaService::CheckForActivityAndShutdown", v44);
    WiaTrcLib::Free((WiaTrcLib *)v44, v45);
    v46 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                     0x80000000LL,
                     0,
                     "Last client released reference to service, not initiating shutdown because another shutdown is already pending.");
    WiaTrace_ProcessTrace_Ex(v48, v47, (void *)"WiaService::CheckForActivityAndShutdown", 4, v46);
  }
  return v5;
}

```

## disassembly

```asm
0x18000557c  push    rbp
0x18000557e  push    rbx
0x18000557f  push    rsi
0x180005580  push    rdi
0x180005581  push    r12
0x180005583  push    r13
0x180005585  push    r14
0x180005587  push    r15
0x180005589  lea     rbp, [rsp-98h]
0x180005591  sub     rsp, 198h
0x180005598  mov     rax, cs:__security_cookie
0x18000559f  xor     rax, rsp
0x1800055a2  mov     [rbp+0D0h+var_50], rax
0x1800055a9  cmp     dword ptr [rcx+18h], 0
0x1800055ad  mov     r13, rcx
0x1800055b0  jnz     loc_1800059DA
0x1800055b6  cmp     dword ptr [rcx+10h], 0
0x1800055ba  jnz     loc_18000575B
0x1800055c0  lea     rcx, [rsp+1D0h+hKey]; this
0x1800055c5  call    ??0ServiceComponentHolder@@QEAA@XZ; ServiceComponentHolder::ServiceComponentHolder(void)
0x1800055ca  lea     rdx, aDevicelistmana_17; "DeviceListManager"
0x1800055d1  lea     rcx, [rsp+1D0h+var_180]
0x1800055d6  call    ??0?$CSimpleStringBase@G@@QEAA@PEBG@Z; CSimpleStringBase<ushort>::CSimpleStringBase<ushort>(ushort const *)
0x1800055db  mov     r14, [rsp+1D0h+var_188]
0x1800055e0  mov     esi, 1
0x1800055e5  test    r14, r14
0x1800055e8  jz      loc_1800057AC
0x1800055ee  lea     rdx, [rsp+1D0h+var_180]
0x1800055f3  mov     rcx, r14
0x1800055f6  call    ??$Get@VDeviceListManager@@@?$CSimpleRefMap@V?$CSimpleStringBase@G@@@@QEAAPEAVDeviceListManager@@AEBV?$CSimpleStringBase@G@@@Z; CSimpleRefMap<CSimpleStringBase<ushort>>::Get<DeviceListManager>(CSimpleStringBase<ushort> const &)
0x1800055fb  mov     rdi, rax
0x1800055fe  mov     rcx, [rbp+0D0h+var_78]; void *
0x180005602  lea     rax, ??_7?$CSimpleStringBase@G@@6B@; const CSimpleStringBase<ushort>::`vftable'
0x180005609  mov     [rsp+1D0h+var_180], rax
0x18000560e  test    rcx, rcx
0x180005611  jz      short loc_180005621
0x180005613  lea     rax, [rsp+1D0h+var_178]
0x180005618  cmp     rcx, rax
0x18000561b  jnz     loc_180005806
0x180005621  mov     [rbp+0D0h+var_78], 0
0x180005629  mov     [rbp+0D0h+var_70], 0
0x180005631  test    rdi, rdi
0x180005634  jz      loc_180005810
0x18000563a  mov     rax, [rdi+8]
0x18000563e  xor     esi, esi
0x180005640  mov     r12d, [rdi+50h]
0x180005644  movsxd  rcx, dword ptr [rax+4]
0x180005648  add     rcx, 8
0x18000564c  add     rcx, rdi
0x18000564f  mov     rax, [rcx]
0x180005652  mov     rax, [rax+10h]
0x180005656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000565b  test    r12d, r12d
0x18000565e  jnz     loc_180005984
0x180005664  lea     rax, [rsp+1D0h+hKey]
0x180005669  mov     [rsp+1D0h+hKey], rsi
0x18000566e  lea     r12d, [rsi+1]
0x180005672  mov     [rsp+1D0h+Type], esi
0x180005676  mov     r9d, r12d; samDesired
0x180005679  mov     dword ptr [rsp+1D0h+Data], esi
0x18000567d  xor     r8d, r8d; ulOptions
0x180005680  mov     [rsp+1D0h+cbData], 4
0x180005688  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Sti"...
0x18000568f  mov     [rsp+1D0h+phkResult], rax; phkResult
0x180005694  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000569b  call    cs:__imp_RegOpenKeyExW
0x1800056a1  lea     rdi, aWiaserviceChec; "WiaService::CheckForActivityAndShutdown"
0x1800056a8  test    eax, eax
0x1800056aa  jnz     loc_180005945
0x1800056b0  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800056b5  lea     rax, [rsp+1D0h+cbData]
0x1800056ba  mov     [rsp+1D0h+lpcbData], rax; lpcbData
0x1800056bf  lea     r9, [rsp+1D0h+Type]; lpType
0x1800056c4  lea     rax, [rsp+1D0h+Data]
0x1800056c9  xor     r8d, r8d; lpReserved
0x1800056cc  lea     rdx, aShutdownifunus; "ShutdownIfUnusedDelay"
0x1800056d3  mov     [rsp+1D0h+phkResult], rax; lpData
0x1800056d8  xor     r15d, r15d
0x1800056db  call    cs:__imp_RegQueryValueExW
0x1800056e1  test    eax, eax
0x1800056e3  jnz     loc_1800058B6
0x1800056e9  cmp     [rsp+1D0h+Type], 4
0x1800056ee  jnz     loc_18000586F
0x1800056f4  mov     eax, dword ptr [rsp+1D0h+Data]
0x1800056f8  test    eax, eax
0x1800056fa  jz      loc_1800058B6
0x180005700  cmp     eax, 20C49Bh
0x180005705  jbe     loc_180005866
0x18000570b  lea     rdx, aDwordOverflowI; "DWORD overflow in timeout time, maximum"...
0x180005712  mov     ecx, r12d
0x180005715  call    WiaTrace_TraceLogWithSubComp
0x18000571a  mov     rdx, rax; char *
0x18000571d  mov     rcx, rdi; char *
0x180005720  mov     rbx, rax
0x180005723  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180005728  mov     rcx, rbx; this
0x18000572b  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180005730  lea     rdx, aDwordOverflowI; "DWORD overflow in timeout time, maximum"...
0x180005737  mov     ecx, r12d
0x18000573a  call    WiaTrace_TraceWithSubComp
0x18000573f  lea     r9d, [rsi+2]; int
0x180005743  mov     [rsp+1D0h+phkResult], rax; lpMem
0x180005748  mov     r8, rdi; int
0x18000574b  call    WiaTrace_ProcessTrace_Ex
0x180005750  mov     r15d, 7FFFFFFFh
0x180005756  jmp     loc_1800058B6
0x18000575b  xor     esi, esi
0x18000575d  jmp     short loc_180005787
0x18000575f  mov     r8, rdi; int
0x180005762  mov     [rsp+1D0h+phkResult], rax; lpMem
0x180005767  call    WiaTrace_ProcessTrace_Ex
0x18000576c  test    r14, r14
0x18000576f  jz      short loc_180005787
0x180005771  mov     rax, [r14]
0x180005774  movsxd  rcx, dword ptr [rax+4]
0x180005778  add     rcx, r14
0x18000577b  mov     rax, [rcx]
0x18000577e  mov     rax, [rax+10h]
0x180005782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005787  mov     eax, esi
0x180005789  mov     rcx, [rbp+0D0h+var_50]
0x180005790  xor     rcx, rsp; StackCookie
0x180005793  call    __security_check_cookie
0x180005798  add     rsp, 198h
0x18000579f  pop     r15
0x1800057a1  pop     r14
0x1800057a3  pop     r13
0x1800057a5  pop     r12
0x1800057a7  pop     rdi
0x1800057a8  pop     rsi
0x1800057a9  pop     rbx
0x1800057aa  pop     rbp
0x1800057ab  retn
0x1800057ac  mov     r8, [rbp+0D0h+var_78]
0x1800057b0  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x1800057b7  mov     ecx, esi
0x1800057b9  xor     edi, edi
0x1800057bb  call    WiaTrace_TraceLogWithSubComp
0x1800057c0  mov     rdx, rax; char *
0x1800057c3  lea     rcx, aServicecompone; "ServiceComponentHolder::Get"
0x1800057ca  mov     rbx, rax
0x1800057cd  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x1800057d2  mov     rcx, rbx; this
0x1800057d5  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800057da  mov     r8, [rbp+0D0h+var_78]
0x1800057de  lea     rdx, aCouldNotRetrie; "Could not retrieve (%ws) because the Se"...
0x1800057e5  mov     ecx, esi
0x1800057e7  call    WiaTrace_TraceWithSubComp
0x1800057ec  lea     r9d, [rdi+2]; int
0x1800057f0  mov     [rsp+1D0h+phkResult], rax; lpMem
0x1800057f5  lea     r8, aServicecompone; "ServiceComponentHolder::Get"
0x1800057fc  call    WiaTrace_ProcessTrace_Ex
0x180005801  jmp     loc_1800055FE
0x180005806  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000580b  jmp     loc_180005621
0x180005810  lea     rdx, aUnableToInitia; "Unable to initiate possible shutdown of"...
0x180005817  mov     ecx, esi
0x180005819  call    WiaTrace_TraceLogWithSubComp
0x18000581e  lea     rdi, aWiaserviceChec; "WiaService::CheckForActivityAndShutdown"
0x180005825  mov     rdx, rax; char *
0x180005828  mov     rcx, rdi; char *
0x18000582b  mov     rbx, rax
0x18000582e  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180005833  mov     rcx, rbx; this
0x180005836  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000583b  lea     rdx, aUnableToInitia; "Unable to initiate possible shutdown of"...
0x180005842  mov     ecx, esi
0x180005844  call    WiaTrace_TraceWithSubComp
0x180005849  mov     r9d, 2; int
0x18000584f  mov     [rsp+1D0h+phkResult], rax; lpMem
0x180005854  mov     r8, rdi; int
0x180005857  call    WiaTrace_ProcessTrace_Ex
0x18000585c  mov     esi, 8000FFFFh
0x180005861  jmp     loc_18000576C
0x180005866  imul    r15d, eax, 3E8h
0x18000586d  jmp     short loc_1800058B6
0x18000586f  lea     rdx, aMalformedRegis; "Malformed registry value for shutdown t"...
0x180005876  mov     ecx, r12d
0x180005879  call    WiaTrace_TraceLogWithSubComp
0x18000587e  mov     rdx, rax; char *
0x180005881  mov     rcx, rdi; char *
0x180005884  mov     rbx, rax
0x180005887  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18000588c  mov     rcx, rbx; this
0x18000588f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180005894  lea     rdx, aMalformedRegis; "Malformed registry value for shutdown t"...
0x18000589b  mov     ecx, r12d
0x18000589e  call    WiaTrace_TraceWithSubComp
0x1800058a3  mov     r9d, 2; int
0x1800058a9  mov     [rsp+1D0h+phkResult], rax; int
0x1800058ae  mov     r8, rdi; int
0x1800058b1  call    WiaTrace_ProcessTrace_Ex
0x1800058b6  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800058bb  call    cs:__imp_RegCloseKey
0x1800058c1  test    r15d, r15d
0x1800058c4  jz      short loc_180005945
0x1800058c6  mov     ecx, 10h; Size
0x1800058cb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800058d0  mov     rbx, rax
0x1800058d3  test    rax, rax
0x1800058d6  jz      loc_18000576C
0x1800058dc  lea     rax, ??_7CShutdownScheduledTask@WiaService@@6B@; const WiaService::CShutdownScheduledTask::`vftable'
0x1800058e3  mov     [rbx+8], r12d
0x1800058e7  mov     [rbx], rax
0x1800058ea  mov     rcx, rbx
0x1800058ed  mov     rax, [rax+8]
0x1800058f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f6  xor     r9d, r9d; void *
0x1800058f9  lea     rcx, ?StopServiceCallback@CShutdownScheduledTask@WiaService@@SAXPEAUIUnknown@@@Z; void (*)(struct IUnknown *)
0x180005900  mov     r8d, r15d; unsigned int
0x180005903  mov     rdx, rbx; struct IUnknown *
0x180005906  call    ?ScheduleWorkItem@@YAKP6AXPEAUIUnknown@@@Z0KPEAXH@Z; ScheduleWorkItem(void (*)(IUnknown *),IUnknown *,ulong,void *,int)
0x18000590b  mov     [r13+18h], eax
0x18000590f  test    eax, eax
0x180005911  jnz     loc_18000576C
0x180005917  lea     rdx, aStirpcErrorFai; "StiRpc Error: Failure to schedule callb"...
0x18000591e  mov     ecx, r12d
0x180005921  call    WiaTrace_TraceLogWithSubComp
0x180005926  mov     rdx, rax; char *
0x180005929  mov     rcx, rdi; char *
0x18000592c  mov     rbx, rax
0x18000592f  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180005934  mov     rcx, rbx; this
0x180005937  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000593c  lea     rdx, aStirpcErrorFai; "StiRpc Error: Failure to schedule callb"...
0x180005943  jmp     short loc_180005971
0x180005945  lea     rdx, aStirpcErrorOut; "StiRpc Error: Out of memory (new return"...
0x18000594c  mov     ecx, r12d
0x18000594f  call    WiaTrace_TraceLogWithSubComp
0x180005954  mov     rdx, rax; char *
0x180005957  mov     rcx, rdi; char *
0x18000595a  mov     rbx, rax
0x18000595d  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x180005962  mov     rcx, rbx; this
0x180005965  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18000596a  lea     rdx, aStirpcErrorOut; "StiRpc Error: Out of memory (new return"...
0x180005971  mov     ecx, r12d
0x180005974  call    WiaTrace_TraceWithSubComp
0x180005979  mov     r9d, 2; int
0x18000597f  jmp     loc_18000575F
0x180005984  mov     r15d, 80000000h
0x18000598a  lea     r8, aNotShuttingDow; "Not shutting down service because %d de"...
0x180005991  mov     ecx, r15d
0x180005994  mov     r9d, r12d
0x180005997  xor     edx, edx
0x180005999  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18000599e  lea     rdi, aWiaserviceChec; "WiaService::CheckForActivityAndShutdown"
0x1800059a5  mov     rdx, rax; char *
0x1800059a8  mov     rcx, rdi; char *
0x1800059ab  mov     rbx, rax
0x1800059ae  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x1800059b3  mov     rcx, rbx; this
0x1800059b6  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x1800059bb  mov     r9d, r12d
0x1800059be  lea     r8, aNotShuttingDow; "Not shutting down service because %d de"...
0x1800059c5  xor     edx, edx
0x1800059c7  mov     ecx, r15d
0x1800059ca  call    WiaTrace_TraceWithSubCompTraceLevel
0x1800059cf  mov     r9d, 4
0x1800059d5  jmp     loc_18000575F
0x1800059da  xor     esi, esi
0x1800059dc  cmp     [rcx+10h], esi
0x1800059df  jnz     loc_180005787
0x1800059e5  mov     r15d, 80000000h
0x1800059eb  lea     r8, aLastClientRele; "Last client released reference to servi"...
0x1800059f2  mov     ecx, r15d
0x1800059f5  xor     edx, edx
0x1800059f7  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x1800059fc  lea     rdi, aWiaserviceChec; "WiaService::CheckForActivityAndShutdown"
0x180005a03  mov     rdx, rax; char *
0x180005a06  mov     rcx, rdi; char *
0x180005a09  mov     rbx, rax
0x180005a0c  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x180005a11  mov     rcx, rbx; this
0x180005a14  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x180005a19  lea     r8, aLastClientRele; "Last client released reference to servi"...
0x180005a20  xor     edx, edx
0x180005a22  mov     ecx, r15d
0x180005a25  call    WiaTrace_TraceWithSubCompTraceLevel
0x180005a2a  lea     r9d, [rsi+4]; int
0x180005a2e  mov     [rsp+1D0h+phkResult], rax; lpMem
0x180005a33  mov     r8, rdi; int
0x180005a36  call    WiaTrace_ProcessTrace_Ex
0x180005a3b  jmp     loc_180005787
```
