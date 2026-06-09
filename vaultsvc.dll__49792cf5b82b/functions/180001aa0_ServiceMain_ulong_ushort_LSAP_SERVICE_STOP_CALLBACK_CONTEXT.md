# ServiceMain(ulong,ushort * *,_LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)

- ea: `0x180001aa0`
- end: `0x180002126`
- name: `?ServiceMain@@YAJKPEAPEAGPEAU_LSAP_SERVICE_STOP_CALLBACK_CONTEXT@@@Z`
- size: `1670`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 **, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000212c`
- `0x1800021e8`
- `0x18000240c`
- `0x180002494`
- `0x180002610`
- `0x180002884`
- `0x180003140`
- `0x180038dec`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18004b43c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001cf1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180001cf1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001c0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001f3c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001d51`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180001d51`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001bf8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x180001bf8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001f2e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180001f2e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d75`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180001d75`
- `ntdll!RtlLeaveCriticalSection` at `0x180001ae5`
- `ntdll!RtlLeaveCriticalSection` at `0x180001b95`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c44`
- `ntdll!RtlLeaveCriticalSection` at `0x180001faf`
- `ntdll!RtlLeaveCriticalSection` at `0x1800020dc`
- `ntdll!RtlLeaveCriticalSection` at `0x180001ae5`
- `ntdll!RtlLeaveCriticalSection` at `0x180001b95`
- `ntdll!RtlLeaveCriticalSection` at `0x180001c44`
- `ntdll!RtlLeaveCriticalSection` at `0x180001faf`
- `ntdll!RtlLeaveCriticalSection` at `0x1800020dc`
- `ntdll!RtlEnterCriticalSection` at `0x180001ad3`
- `ntdll!RtlEnterCriticalSection` at `0x180001ad3`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180002042`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000209e`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180002042`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x18000209e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ServiceMain(__int64 a1, unsigned __int16 **a2, struct _LSAP_SERVICE_STOP_CALLBACK_CONTEXT *a3)
{
  const unsigned __int16 *v4; // rdi
  PVOID *v5; // rcx
  unsigned int v6; // ebx
  DWORD LastError; // eax
  DWORD started; // eax
  unsigned int v10; // ebx
  PVOID *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  HANDLE EventW; // rax
  int StringW; // eax
  size_t v16; // rbx
  DWORD v17; // eax
  unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // rdx
  size_t v20; // rbx
  DWORD v21; // eax
  int v22; // eax
  int v23; // eax
  __int64 v24; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-20h]
  int v26; // [rsp+50h] [rbp-18h]
  const void *Buffer; // [rsp+C8h] [rbp+60h] BYREF

  v4 = 0;
  v25 = 0;
  v26 = 0;
  v24 = 0;
  RtlEnterCriticalSection(&CriticalSection);
  if ( byte_18005F5C5 )
  {
    RtlLeaveCriticalSection(&CriticalSection);
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    return 0;
  }
  qword_18005F5E8 = 0;
  WPP_MAIN_CB = 0;
  qword_18005F5F0 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_VaultGlobalDebugTraceControlGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  WppInitUm();
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !a3 )
  {
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 )
      WPP_SF_(v5[2], 45, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
    WppCleanupUm();
    RtlLeaveCriticalSection(&CriticalSection);
    v6 = 87;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_78b059fac4093813b2646cef9913e025_Traceguids, 87);
LABEL_13:
    CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
    return v6;
  }
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwServiceSpecificExitCode = 0;
  hServiceStatus = RegisterServiceCtrlHandlerExW(L"VaultSvc", VaultSvcCtrlHandlerEx, 0);
  if ( !hServiceStatus )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_78b059fac4093813b2646cef9913e025_Traceguids, LastError);
    WppCleanupUm();
    RtlLeaveCriticalSection(&CriticalSection);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v6);
    goto LABEL_13;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
  started = NotifySCM(2, 3000);
  v10 = started;
  if ( started )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_78;
    v12 = 50;
    goto LABEL_29;
  }
  CVaultConfiguration::ReadConfiguration();
  EventW = CreateEventW(0, 1, 0, 0);
  hEvent = EventW;
  if ( !EventW )
  {
    started = GetLastError();
    v10 = started;
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_78;
    v12 = 52;
    goto LABEL_29;
  }
  *((_QWORD *)a3 + 1) = EventW;
  *(_QWORD *)a3 = VaultSvcStopCallback;
  Buffer = 0;
  StringW = LoadStringW(hInstance, 0x2716u, (LPWSTR)&Buffer, 0);
  v16 = StringW;
  if ( StringW )
  {
    v18 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (unsigned int)(StringW + 1));
    v4 = v18;
    v25 = v18;
    if ( v18 )
    {
      v20 = v16;
      memcpy_0(v18, Buffer, v20 * 2);
      v4[v20] = 0;
LABEL_44:
      v19 = v4;
      goto LABEL_45;
    }
    v17 = 14;
  }
  else
  {
    v17 = GetLastError();
    if ( !v17 )
      goto LABEL_44;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v17);
  v19 = L"Web Credentials";
LABEL_45:
  v10 = VaultInitialize(hInstance, v19);
  if ( v10 )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_78;
    v12 = 54;
    goto LABEL_76;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
  started = NotifySCM(2, 3000);
  v10 = started;
  if ( started )
  {
    v11 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_78;
    v12 = 56;
  }
  else
  {
    started = StartVaultRpcServer();
    v10 = started;
    if ( started )
    {
      v11 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_78;
      v12 = 57;
    }
    else
    {
      started = NotifySCM(2, 3000);
      v10 = started;
      if ( started )
      {
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_78;
        v12 = 58;
      }
      else
      {
        started = NotifySCM(2, 3000);
        v10 = started;
        if ( !started )
        {
          ServiceStatus.dwCurrentState = 4;
          *(_QWORD *)&ServiceStatus.dwCheckPoint = 0;
          *(_QWORD *)&ServiceStatus.dwControlsAccepted = 133;
          if ( SetServiceStatus(hServiceStatus, &ServiceStatus) )
          {
            v11 = (PVOID *)WPP_GLOBAL_Control;
          }
          else
          {
            v21 = GetLastError();
            v10 = v21;
            v11 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v21);
              v11 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v10 )
            {
              if ( v11 == &WPP_GLOBAL_Control || (*((_BYTE *)v11 + 28) & 1) == 0 )
                goto LABEL_78;
              v12 = 61;
LABEL_76:
              v13 = v10;
              goto LABEL_77;
            }
          }
          if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
            WPP_SF_(v11[2], 62, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
          v22 = RtlSubscribeWnfStateChangeNotification(
                  &qword_18005F8C8,
                  WNF_SHEL_LOGON_COMPLETE,
                  0,
                  VaultShellNotificationsCallback,
                  0,
                  0,
                  0,
                  1,
                  v24,
                  v25,
                  v26);
          if ( v22 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              63,
              WPP_78b059fac4093813b2646cef9913e025_Traceguids,
              (unsigned int)v22);
          v23 = RtlSubscribeWnfStateChangeNotification(
                  &qword_18005F8B8,
                  WNF_VTSV_CDS_SYNC,
                  0,
                  VaultCDSNotificationsCallback,
                  0,
                  0,
                  0,
                  1,
                  v24,
                  v25,
                  v26);
          if ( v23 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              64,
              WPP_78b059fac4093813b2646cef9913e025_Traceguids,
              (unsigned int)v23);
          byte_18005F5C5 = 1;
          RtlLeaveCriticalSection(&CriticalSection);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_78b059fac4093813b2646cef9913e025_Traceguids, 0);
          CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
          return 0;
        }
        v11 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_78;
        v12 = 60;
      }
    }
  }
LABEL_29:
  v13 = started;
LABEL_77:
  WPP_SF_d(v11[2], v12, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v13);
LABEL_78:
  ShutdownService(v10, 0);
  byte_18005F5C5 = 0;
  RtlLeaveCriticalSection(&CriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_78b059fac4093813b2646cef9913e025_Traceguids, 3221225701LL);
  CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v24);
  return 3221225701LL;
}

```

## disassembly

```asm
0x180001aa0  push    rbp
0x180001aa2  push    rbx
0x180001aa3  push    rsi
0x180001aa4  push    rdi
0x180001aa5  push    r12
0x180001aa7  push    r13
0x180001aa9  push    r14
0x180001aab  push    r15
0x180001aad  mov     rbp, rsp
0x180001ab0  sub     rsp, 68h
0x180001ab4  mov     rsi, r8
0x180001ab7  xor     r14d, r14d
0x180001aba  mov     edi, r14d
0x180001abd  mov     [rbp+var_20], r14
0x180001ac1  mov     [rbp+var_18], r14d
0x180001ac5  mov     [rbp+var_28], r14
0x180001ac9  lea     rbx, CriticalSection
0x180001ad0  mov     rcx, rbx; CriticalSection
0x180001ad3  call    cs:__imp_RtlEnterCriticalSection
0x180001ad9  cmp     cs:byte_18005F5C5, r14b
0x180001ae0  jz      short loc_180001AFB
0x180001ae2  mov     rcx, rbx; CriticalSection
0x180001ae5  call    cs:__imp_RtlLeaveCriticalSection
0x180001aeb  nop
0x180001aec  lea     rcx, [rbp+var_28]
0x180001af0  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180001af5  nop
0x180001af6  jmp     loc_180002113
0x180001afb  mov     cs:qword_18005F5E8, r14
0x180001b02  mov     cs:WPP_MAIN_CB, r14
0x180001b09  mov     r13d, 1
0x180001b0f  mov     cs:qword_18005F5F0, r13
0x180001b16  lea     rax, WPP_ThisDir_CTLGUID_VaultGlobalDebugTraceControlGuid
0x180001b1d  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180001b24  lea     rax, WPP_MAIN_CB
0x180001b2b  mov     cs:WPP_GLOBAL_Control, rax
0x180001b32  call    WppInitUm
0x180001b37  lea     r15, WPP_GLOBAL_Control
0x180001b3e  lea     r12, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x180001b45  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b4c  cmp     rcx, r15
0x180001b4f  jz      short loc_180001B6E
0x180001b51  test    byte ptr [rcx+1Ch], 8
0x180001b55  jz      short loc_180001B6E
0x180001b57  lea     edx, [r13+2Ah]
0x180001b5b  mov     r8, r12
0x180001b5e  mov     rcx, [rcx+10h]
0x180001b62  call    WPP_SF_
0x180001b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b6e  test    rsi, rsi
0x180001b71  jnz     short loc_180001BD6
0x180001b73  cmp     rcx, r15
0x180001b76  jz      short loc_180001B8D
0x180001b78  test    [rcx+1Ch], r13b
0x180001b7c  jz      short loc_180001B8D
0x180001b7e  lea     edx, [rsi+2Dh]
0x180001b81  mov     r8, r12
0x180001b84  mov     rcx, [rcx+10h]
0x180001b88  call    WPP_SF_
0x180001b8d  call    WppCleanupUm
0x180001b92  mov     rcx, rbx; CriticalSection
0x180001b95  call    cs:__imp_RtlLeaveCriticalSection
0x180001b9b  mov     ebx, 57h ; 'W'
0x180001ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ba7  cmp     rcx, r15
0x180001baa  jz      short loc_180001BC5
0x180001bac  test    byte ptr [rcx+1Ch], 8
0x180001bb0  jz      short loc_180001BC5
0x180001bb2  lea     edx, [rbx-29h]
0x180001bb5  mov     r9d, ebx
0x180001bb8  mov     r8, r12
0x180001bbb  mov     rcx, [rcx+10h]
0x180001bbf  call    WPP_SF_d
0x180001bc4  nop
0x180001bc5  lea     rcx, [rbp+var_28]
0x180001bc9  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180001bce  nop
0x180001bcf  mov     eax, ebx
0x180001bd1  jmp     loc_180002115
0x180001bd6  mov     cs:ServiceStatus.dwServiceType, 20h ; ' '
0x180001be0  mov     cs:ServiceStatus.dwServiceSpecificExitCode, r14d
0x180001be7  xor     r8d, r8d; lpContext
0x180001bea  lea     rdx, ?VaultSvcCtrlHandlerEx@@YAKKKPEAX0@Z; lpHandlerProc
0x180001bf1  lea     rcx, ServiceName; "VaultSvc"
0x180001bf8  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180001bfe  mov     cs:hServiceStatus, rax
0x180001c05  test    rax, rax
0x180001c08  jnz     short loc_180001C80
0x180001c0a  call    cs:__imp_GetLastError
0x180001c10  mov     ebx, eax
0x180001c12  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c19  cmp     rcx, r15
0x180001c1c  jz      short loc_180001C38
0x180001c1e  test    [rcx+1Ch], r13b
0x180001c22  jz      short loc_180001C38
0x180001c24  mov     edx, 2Fh ; '/'
0x180001c29  mov     r9d, eax
0x180001c2c  mov     r8, r12
0x180001c2f  mov     rcx, [rcx+10h]
0x180001c33  call    WPP_SF_d
0x180001c38  call    WppCleanupUm
0x180001c3d  lea     rcx, CriticalSection; CriticalSection
0x180001c44  call    cs:__imp_RtlLeaveCriticalSection
0x180001c4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c51  cmp     rcx, r15
0x180001c54  jz      short loc_180001C71
0x180001c56  test    byte ptr [rcx+1Ch], 8
0x180001c5a  jz      short loc_180001C71
0x180001c5c  mov     edx, 30h ; '0'
0x180001c61  mov     r9d, ebx
0x180001c64  mov     r8, r12
0x180001c67  mov     rcx, [rcx+10h]
0x180001c6b  call    WPP_SF_d
0x180001c70  nop
0x180001c71  lea     rcx, [rbp+var_28]
0x180001c75  call    ?Delete@?$CVaultAutoPtr@PEAUHKEY__@@JPEAU1@$0A@@@QEAAXXZ; CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(void)
0x180001c7a  nop
0x180001c7b  jmp     loc_180001BCF
0x180001c80  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c87  cmp     rcx, r15
0x180001c8a  jz      short loc_180001CA3
0x180001c8c  test    byte ptr [rcx+1Ch], 8
0x180001c90  jz      short loc_180001CA3
0x180001c92  mov     edx, 31h ; '1'
0x180001c97  mov     r8, r12
0x180001c9a  mov     rcx, [rcx+10h]
0x180001c9e  call    WPP_SF_
0x180001ca3  xor     r8d, r8d
0x180001ca6  mov     edx, 0BB8h
0x180001cab  lea     ecx, [r8+2]
0x180001caf  call    NotifySCM
0x180001cb4  mov     ebx, eax
0x180001cb6  test    eax, eax
0x180001cb8  jz      short loc_180001CE1
0x180001cba  mov     rcx, cs:WPP_GLOBAL_Control
0x180001cc1  cmp     rcx, r15
0x180001cc4  jz      loc_180001F98
0x180001cca  test    [rcx+1Ch], r13b
0x180001cce  jz      loc_180001F98
0x180001cd4  mov     edx, 32h ; '2'
0x180001cd9  mov     r9d, eax
0x180001cdc  jmp     loc_180001F8C
0x180001ce1  call    ?ReadConfiguration@CVaultConfiguration@@SAXW4VaultConfigType@@@Z; CVaultConfiguration::ReadConfiguration(VaultConfigType)
0x180001ce6  xor     r9d, r9d; lpName
0x180001ce9  xor     r8d, r8d; bInitialState
0x180001cec  mov     edx, r13d; bManualReset
0x180001cef  xor     ecx, ecx; lpEventAttributes
0x180001cf1  call    cs:__imp_CreateEventW
0x180001cf7  mov     cs:hEvent, rax
0x180001cfe  test    rax, rax
0x180001d01  jnz     short loc_180001D2C
0x180001d03  call    cs:__imp_GetLastError
0x180001d09  mov     ebx, eax
0x180001d0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d12  cmp     rcx, r15
0x180001d15  jz      loc_180001F98
0x180001d1b  test    [rcx+1Ch], r13b
0x180001d1f  jz      loc_180001F98
0x180001d25  mov     edx, 34h ; '4'
0x180001d2a  jmp     short loc_180001CD9
0x180001d2c  mov     [rsi+8], rax
0x180001d30  lea     rax, ?VaultSvcStopCallback@@YAJPEAX@Z; VaultSvcStopCallback(void *)
0x180001d37  mov     [rsi], rax
0x180001d3a  mov     [rbp+Buffer], r14
0x180001d3e  xor     r9d, r9d; cchBufferMax
0x180001d41  lea     r8, [rbp+Buffer]; lpBuffer
0x180001d45  mov     edx, 2716h; uID
0x180001d4a  mov     rcx, cs:hInstance; hInstance
0x180001d51  call    cs:__imp_LoadStringW
0x180001d57  movsxd  rbx, eax
0x180001d5a  test    eax, eax
0x180001d5c  jnz     short loc_180001D6A
0x180001d5e  call    cs:__imp_GetLastError
0x180001d64  test    eax, eax
0x180001d66  jnz     short loc_180001D8A
0x180001d68  jmp     short loc_180001DD0
0x180001d6a  lea     edx, [rbx+1]
0x180001d6d  add     rdx, rdx; uBytes
0x180001d70  mov     ecx, 40h ; '@'; uFlags
0x180001d75  call    cs:__imp_LocalAlloc
0x180001d7b  mov     rdi, rax
0x180001d7e  mov     [rbp+var_20], rax
0x180001d82  test    rax, rax
0x180001d85  jnz     short loc_180001DB9
0x180001d87  lea     eax, [rdi+0Eh]
0x180001d8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d91  cmp     rcx, r15
0x180001d94  jz      short loc_180001DB0
0x180001d96  test    byte ptr [rcx+1Ch], 4
0x180001d9a  jz      short loc_180001DB0
0x180001d9c  mov     edx, 35h ; '5'
0x180001da1  mov     r9d, eax
0x180001da4  mov     r8, r12
0x180001da7  mov     rcx, [rcx+10h]
0x180001dab  call    WPP_SF_d
0x180001db0  lea     rdx, aWebCredentials; "Web Credentials"
0x180001db7  jmp     short loc_180001DD3
0x180001db9  add     rbx, rbx
0x180001dbc  mov     r8, rbx; Size
0x180001dbf  mov     rdx, [rbp+Buffer]; Src
0x180001dc3  mov     rcx, rdi; void *
0x180001dc6  call    memcpy_0
0x180001dcb  mov     [rdi+rbx], r14w
0x180001dd0  mov     rdx, rdi; unsigned __int16 *
0x180001dd3  mov     rcx, cs:hInstance; HINSTANCE
0x180001dda  call    ?VaultInitialize@@YAKPEAUHINSTANCE__@@PEBG@Z; VaultInitialize(HINSTANCE__ *,ushort const *)
0x180001ddf  mov     ebx, eax
0x180001de1  test    eax, eax
0x180001de3  jz      short loc_180001E09
0x180001de5  mov     rcx, cs:WPP_GLOBAL_Control
0x180001dec  cmp     rcx, r15
0x180001def  jz      loc_180001F98
0x180001df5  test    [rcx+1Ch], r13b
0x180001df9  jz      loc_180001F98
0x180001dff  mov     edx, 36h ; '6'
0x180001e04  jmp     loc_180001F89
0x180001e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e10  cmp     rcx, r15
0x180001e13  jz      short loc_180001E2C
0x180001e15  test    byte ptr [rcx+1Ch], 8
0x180001e19  jz      short loc_180001E2C
0x180001e1b  mov     edx, 37h ; '7'
0x180001e20  mov     r8, r12
0x180001e23  mov     rcx, [rcx+10h]
0x180001e27  call    WPP_SF_
0x180001e2c  xor     r8d, r8d
0x180001e2f  mov     esi, 0BB8h
0x180001e34  mov     edx, esi
0x180001e36  lea     edi, [r8+2]
0x180001e3a  mov     ecx, edi
0x180001e3c  call    NotifySCM
0x180001e41  mov     ebx, eax
0x180001e43  test    eax, eax
0x180001e45  jz      short loc_180001E69
0x180001e47  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e4e  cmp     rcx, r15
0x180001e51  jz      loc_180001F98
0x180001e57  test    [rcx+1Ch], r13b
0x180001e5b  jz      loc_180001F98
0x180001e61  lea     edx, [rdi+36h]
0x180001e64  jmp     loc_180001CD9
0x180001e69  call    ?StartVaultRpcServer@@YAJXZ; StartVaultRpcServer(void)
0x180001e6e  mov     ebx, eax
0x180001e70  test    eax, eax
0x180001e72  jz      short loc_180001E98
0x180001e74  mov     rcx, cs:WPP_GLOBAL_Control
0x180001e7b  cmp     rcx, r15
0x180001e7e  jz      loc_180001F98
0x180001e84  test    [rcx+1Ch], r13b
0x180001e88  jz      loc_180001F98
0x180001e8e  mov     edx, 39h ; '9'
0x180001e93  jmp     loc_180001CD9
0x180001e98  xor     r8d, r8d
0x180001e9b  mov     edx, esi
0x180001e9d  mov     ecx, edi
0x180001e9f  call    NotifySCM
0x180001ea4  mov     ebx, eax
0x180001ea6  test    eax, eax
0x180001ea8  jz      short loc_180001ECE
0x180001eaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180001eb1  cmp     rcx, r15
0x180001eb4  jz      loc_180001F98
0x180001eba  test    [rcx+1Ch], r13b
0x180001ebe  jz      loc_180001F98
0x180001ec4  mov     edx, 3Ah ; ':'
0x180001ec9  jmp     loc_180001CD9
0x180001ece  xor     r8d, r8d
0x180001ed1  mov     edx, esi
0x180001ed3  mov     ecx, edi
0x180001ed5  call    NotifySCM
0x180001eda  mov     ebx, eax
0x180001edc  test    eax, eax
0x180001ede  jz      short loc_180001F04
0x180001ee0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ee7  cmp     rcx, r15
0x180001eea  jz      loc_180001F98
0x180001ef0  test    [rcx+1Ch], r13b
0x180001ef4  jz      loc_180001F98
0x180001efa  mov     edx, 3Ch ; '<'
0x180001eff  jmp     loc_180001CD9
0x180001f04  mov     cs:ServiceStatus.dwCurrentState, 4
0x180001f0e  mov     qword ptr cs:ServiceStatus.dwCheckPoint, r14
0x180001f15  mov     qword ptr cs:ServiceStatus.dwControlsAccepted, 85h
0x180001f20  lea     rdx, ServiceStatus; lpServiceStatus
0x180001f27  mov     rcx, cs:hServiceStatus; hServiceStatus
0x180001f2e  call    cs:__imp_SetServiceStatus
0x180001f34  test    eax, eax
0x180001f36  jnz     loc_180001FF3
0x180001f3c  call    cs:__imp_GetLastError
0x180001f42  mov     ebx, eax
0x180001f44  mov     rcx, cs:WPP_GLOBAL_Control
0x180001f4b  cmp     rcx, r15
0x180001f4e  jz      short loc_180001F71
0x180001f50  test    [rcx+1Ch], dil
0x180001f54  jz      short loc_180001F71
0x180001f56  mov     edx, 1Ah
0x180001f5b  mov     r9d, eax
0x180001f5e  mov     r8, r12
0x180001f61  mov     rcx, [rcx+10h]
0x180001f65  call    WPP_SF_d
  ... truncated ...
```
