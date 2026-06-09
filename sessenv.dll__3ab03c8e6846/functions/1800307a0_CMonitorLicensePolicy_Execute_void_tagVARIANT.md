# CMonitorLicensePolicy::Execute(void *,tagVARIANT *)

- ea: `0x1800307a0`
- end: `0x1800309c6`
- name: `?Execute@CMonitorLicensePolicy@@UEAAJPEAXPEAUtagVARIANT@@@Z`
- size: `550`
- prototype: `__int64 __fastcall(CMonitorLicensePolicy *this, void *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003f30`
- `0x180025a7c`
- `0x1800307a0`
- `0x180030a10`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180030996`
- `ntdll!RtlUnsubscribeWnfStateChangeNotification` at `0x180030996`
- `ntdll!NtQueryWnfStateData` at `0x180030872`
- `ntdll!NtQueryWnfStateData` at `0x180030872`
- `ntdll!RtlNtStatusToDosError` at `0x18003087e`
- `ntdll!RtlNtStatusToDosError` at `0x1800308e6`
- `ntdll!RtlNtStatusToDosError` at `0x18003087e`
- `ntdll!RtlNtStatusToDosError` at `0x1800308e6`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800308da`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800308da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030828`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030828`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800309a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800309a3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030816`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180030816`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180030932`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180030932`

## string_xrefs

- `0x180030844`: `CreateEvent failed: 0x%x in %s`
- `0x1800307ef`: `IsAutomatedAppServerInstallation failed: 0x%x in %s`
- `0x180030966`: `Thread aborted failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CMonitorLicensePolicy::Execute(CMonitorLicensePolicy *this, void *a2, struct tagVARIANT *a3)
{
  HRESULT IsAutomatedAppServerInstallation; // eax
  signed int v6; // ebx
  const char *v7; // rdx
  HANDLE EventW; // rax
  signed int LastError; // eax
  NTSTATUS v10; // eax
  signed int v11; // eax
  NTSTATUS v12; // eax
  signed int v13; // eax
  CMonitorLicensePolicy *v14; // rcx
  __int64 result; // rax
  DWORD dwindex; // [rsp+40h] [rbp-20h] BYREF
  int v17; // [rsp+44h] [rbp-1Ch] BYREF
  __int64 v18; // [rsp+48h] [rbp-18h] BYREF
  HANDLE pHandles[2]; // [rsp+50h] [rbp-10h] BYREF
  int v20; // [rsp+80h] [rbp+20h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+38h] BYREF

  v21 = 0;
  v18 = 0;
  v17 = 0;
  *(_OWORD *)pHandles = 0;
  dwindex = 0;
  v20 = 0;
  IsAutomatedAppServerInstallation = CSLQuery::IsAutomatedAppServerInstallation(&v20);
  v6 = IsAutomatedAppServerInstallation;
  if ( IsAutomatedAppServerInstallation >= 0 )
  {
    if ( !v20 )
      goto LABEL_28;
    *(_OWORD *)pHandles = 0;
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 199) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        _DbgPrintMessage(8, "CreateEvent failed: 0x%x in %s", (unsigned int)v6, "CMonitorLicensePolicy::Execute");
        goto LABEL_28;
      }
    }
    v10 = NtQueryWnfStateData(&WNF_OLIC_OS_EDITION_CHANGE, 0, 0, &v21, 0, &v17);
    if ( v10 < 0 )
    {
      v11 = RtlNtStatusToDosError(v10);
      v6 = v11;
      if ( v11 > 0 )
        v6 = (unsigned __int16)v11 | 0x80070000;
      if ( v6 < 0 )
      {
        _DbgPrintMessage(
          8,
          "NtQueryWnfStateData failed: 0x%x in %s",
          (unsigned int)v6,
          "CMonitorLicensePolicy::Execute");
        goto LABEL_28;
      }
    }
    v12 = RtlSubscribeWnfStateChangeNotification(
            &v18,
            WNF_OLIC_OS_EDITION_CHANGE,
            v21,
            CMonitorLicensePolicy::s_LicensePolicyNotificationCallback,
            this,
            0,
            0,
            1);
    if ( v12 < 0 )
    {
      v13 = RtlNtStatusToDosError(v12);
      v6 = v13;
      if ( v13 > 0 )
        v6 = (unsigned __int16)v13 | 0x80070000;
      if ( v6 < 0 )
      {
        _DbgPrintMessage(
          8,
          "RtlSubscribeWnfStateChangeNotification failed: 0x%x in %s",
          (unsigned int)v6,
          "CMonitorLicensePolicy::Execute");
        goto LABEL_28;
      }
    }
    pHandles[1] = *((HANDLE *)this + 199);
    pHandles[0] = a2;
    while ( 1 )
    {
      IsAutomatedAppServerInstallation = CoWaitForMultipleHandles(0, 0xFFFFFFFF, 2u, pHandles, &dwindex);
      v6 = IsAutomatedAppServerInstallation;
      if ( IsAutomatedAppServerInstallation < 0 )
        break;
      if ( !dwindex )
      {
        v6 = -2147467260;
        _DbgPrintMessage(8, "Thread aborted failed: 0x%x in %s", 2147500036LL, "CMonitorLicensePolicy::Execute");
        goto LABEL_28;
      }
      if ( dwindex == 1 )
      {
        IsAutomatedAppServerInstallation = CMonitorLicensePolicy::HandleNotification(v14, a2);
        v6 = IsAutomatedAppServerInstallation;
        if ( IsAutomatedAppServerInstallation < 0 )
        {
          v7 = "HandleNotification failed: 0x%x in %s";
          goto LABEL_27;
        }
      }
    }
    v7 = "CoWaitForMultipleHandles failed: 0x%x in %s";
  }
  else
  {
    v7 = "IsAutomatedAppServerInstallation failed: 0x%x in %s";
  }
LABEL_27:
  _DbgPrintMessage(8, v7, (unsigned int)IsAutomatedAppServerInstallation, "CMonitorLicensePolicy::Execute");
LABEL_28:
  if ( v18 )
    RtlUnsubscribeWnfStateChangeNotification();
  CloseHandle(*((HANDLE *)this + 199));
  result = (unsigned int)v6;
  *((_QWORD *)this + 199) = 0;
  return result;
}

```

## disassembly

```asm
0x1800307a0  mov     [rsp-18h+arg_8], rbx
0x1800307a5  push    rbp
0x1800307a6  push    rsi
0x1800307a7  push    rdi
0x1800307a8  mov     rbp, rsp
0x1800307ab  sub     rsp, 60h
0x1800307af  mov     rdi, rcx
0x1800307b2  mov     [rbp+arg_18], 0
0x1800307b9  xorps   xmm0, xmm0
0x1800307bc  mov     [rbp+var_18], 0
0x1800307c4  lea     rcx, [rbp+arg_0]; int *
0x1800307c8  mov     [rbp+var_1C], 0
0x1800307cf  movups  xmmword ptr [rbp+pHandles], xmm0
0x1800307d3  mov     rsi, rdx
0x1800307d6  mov     [rbp+dwindex], 0
0x1800307dd  mov     [rbp+arg_0], 0
0x1800307e4  call    ?IsAutomatedAppServerInstallation@CSLQuery@@SAJPEAH@Z; CSLQuery::IsAutomatedAppServerInstallation(int *)
0x1800307e9  mov     ebx, eax
0x1800307eb  test    eax, eax
0x1800307ed  jns     short loc_1800307FB
0x1800307ef  lea     rdx, aIsautomatedapp; "IsAutomatedAppServerInstallation failed"...
0x1800307f6  jmp     loc_180030979
0x1800307fb  cmp     [rbp+arg_0], 0
0x1800307ff  jz      loc_18003098D
0x180030805  xorps   xmm0, xmm0
0x180030808  xor     r9d, r9d; lpName
0x18003080b  xor     r8d, r8d; bInitialState
0x18003080e  xor     edx, edx; bManualReset
0x180030810  xor     ecx, ecx; lpEventAttributes
0x180030812  movups  xmmword ptr [rbp+pHandles], xmm0
0x180030816  call    cs:__imp_CreateEventW
0x18003081c  mov     [rdi+638h], rax
0x180030823  test    rax, rax
0x180030826  jnz     short loc_180030850
0x180030828  call    cs:__imp_GetLastError
0x18003082e  mov     ebx, eax
0x180030830  test    eax, eax
0x180030832  jle     short loc_18003083D
0x180030834  movzx   ebx, ax
0x180030837  or      ebx, 80070000h
0x18003083d  test    ebx, ebx
0x18003083f  jns     short loc_180030850
0x180030841  mov     r8d, ebx
0x180030844  lea     rdx, aCreateeventFai; "CreateEvent failed: 0x%x in %s"
0x18003084b  jmp     loc_18003097C
0x180030850  lea     rax, [rbp+var_1C]
0x180030854  xor     r8d, r8d
0x180030857  mov     [rsp+60h+var_38], rax
0x18003085c  lea     r9, [rbp+arg_18]
0x180030860  xor     edx, edx
0x180030862  mov     [rsp+60h+lpdwindex], 0
0x18003086b  lea     rcx, WNF_OLIC_OS_EDITION_CHANGE
0x180030872  call    cs:__imp_NtQueryWnfStateData
0x180030878  test    eax, eax
0x18003087a  jns     short loc_1800308A6
0x18003087c  mov     ecx, eax; Status
0x18003087e  call    cs:__imp_RtlNtStatusToDosError
0x180030884  mov     ebx, eax
0x180030886  test    eax, eax
0x180030888  jle     short loc_180030893
0x18003088a  movzx   ebx, ax
0x18003088d  or      ebx, 80070000h
0x180030893  test    ebx, ebx
0x180030895  jns     short loc_1800308A6
0x180030897  mov     r8d, ebx
0x18003089a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData failed: 0x%x in %s"
0x1800308a1  jmp     loc_18003097C
0x1800308a6  mov     r8d, [rbp+arg_18]
0x1800308aa  lea     r9, ?s_LicensePolicyNotificationCallback@CMonitorLicensePolicy@@CAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; CMonitorLicensePolicy::s_LicensePolicyNotificationCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x1800308b1  mov     rdx, cs:WNF_OLIC_OS_EDITION_CHANGE
0x1800308b8  lea     rcx, [rbp+var_18]
0x1800308bc  mov     [rsp+60h+var_28], 1
0x1800308c4  mov     [rsp+60h+var_30], 0
0x1800308cc  mov     [rsp+60h+var_38], 0
0x1800308d5  mov     [rsp+60h+lpdwindex], rdi
0x1800308da  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800308e0  test    eax, eax
0x1800308e2  jns     short loc_18003090B
0x1800308e4  mov     ecx, eax; Status
0x1800308e6  call    cs:__imp_RtlNtStatusToDosError
0x1800308ec  mov     ebx, eax
0x1800308ee  test    eax, eax
0x1800308f0  jle     short loc_1800308FB
0x1800308f2  movzx   ebx, ax
0x1800308f5  or      ebx, 80070000h
0x1800308fb  test    ebx, ebx
0x1800308fd  jns     short loc_18003090B
0x1800308ff  mov     r8d, ebx
0x180030902  lea     rdx, aRtlsubscribewn; "RtlSubscribeWnfStateChangeNotification "...
0x180030909  jmp     short loc_18003097C
0x18003090b  mov     rax, [rdi+638h]
0x180030912  mov     [rbp+pHandles+8], rax
0x180030916  mov     [rbp+pHandles], rsi
0x18003091a  lea     rax, [rbp+dwindex]
0x18003091e  mov     r8d, 2; cHandles
0x180030924  lea     r9, [rbp+pHandles]; pHandles
0x180030928  mov     [rsp+60h+lpdwindex], rax; lpdwindex
0x18003092d  or      edx, 0FFFFFFFFh; dwTimeout
0x180030930  xor     ecx, ecx; dwFlags
0x180030932  call    cs:__imp_CoWaitForMultipleHandles
0x180030938  mov     ebx, eax
0x18003093a  test    eax, eax
0x18003093c  js      short loc_180030972
0x18003093e  mov     eax, [rbp+dwindex]
0x180030941  test    eax, eax
0x180030943  jz      short loc_180030961
0x180030945  cmp     eax, 1
0x180030948  jnz     short loc_18003091A
0x18003094a  mov     rdx, rsi; void *
0x18003094d  call    ?HandleNotification@CMonitorLicensePolicy@@AEAAJPEAX@Z; CMonitorLicensePolicy::HandleNotification(void *)
0x180030952  mov     ebx, eax
0x180030954  test    eax, eax
0x180030956  jns     short loc_18003091A
0x180030958  lea     rdx, aHandlenotifica; "HandleNotification failed: 0x%x in %s"
0x18003095f  jmp     short loc_180030979
0x180030961  mov     ebx, 80004004h
0x180030966  lea     rdx, aThreadAbortedF; "Thread aborted failed: 0x%x in %s"
0x18003096d  mov     r8d, ebx
0x180030970  jmp     short loc_18003097C
0x180030972  lea     rdx, aCowaitformulti; "CoWaitForMultipleHandles failed: 0x%x i"...
0x180030979  mov     r8d, eax
0x18003097c  lea     r9, aCmonitorlicens_0; "CMonitorLicensePolicy::Execute"
0x180030983  mov     ecx, 8; int
0x180030988  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003098d  mov     rcx, [rbp+var_18]
0x180030991  test    rcx, rcx
0x180030994  jz      short loc_18003099C
0x180030996  call    cs:__imp_RtlUnsubscribeWnfStateChangeNotification
0x18003099c  mov     rcx, [rdi+638h]; hObject
0x1800309a3  call    cs:__imp_CloseHandle
0x1800309a9  mov     eax, ebx
0x1800309ab  mov     qword ptr [rdi+638h], 0
0x1800309b6  mov     rbx, [rsp+60h+arg_8]
0x1800309be  add     rsp, 60h
0x1800309c2  pop     rdi
0x1800309c3  pop     rsi
0x1800309c4  pop     rbp
0x1800309c5  retn
```
