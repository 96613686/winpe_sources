# ProfileManager::GetProfileXml(void *,ulong,_GUID const *,ulong,ushort const *,bool,ushort * *,ulong *,ulong *)

- ea: `0x18003e670`
- end: `0x18003efa8`
- name: `?GetProfileXml@ProfileManager@@QEAAKPEAXKPEBU_GUID@@KPEBG_NPEAPEAGPEAK5@Z`
- size: `2360`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection, void *, unsigned int, struct _GUID *, unsigned int, const unsigned __int16 *, bool, unsigned __int16 **, unsigned int *, unsigned int *)`
- caller_count: `3`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003dd40`
- `0x18003e120`
- `0x18003f264`

## callees

- `0x1800036c4`
- `0x18000a994`
- `0x18000bfa0`
- `0x18000eb40`
- `0x18001a618`
- `0x180023b50`
- `0x18003e670`
- `0x180057180`
- `0x180057ca0`
- `0x180084364`
- `0x1800a5380`
- `0x1800c6774`
- `0x1800de47c`
- `0x180106340`
- `0x1801067c0`
- `0x18022c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003e73d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003eb27`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003e73d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003eb27`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e7e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ebc7`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003e7e4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ebc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ee5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ee5e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e92c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003e92c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003e913`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003ec79`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003e913`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003ec79`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003e9f0`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003ed79`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003eda2`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003edcc`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003e9f0`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003ed79`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003eda2`
- `MobileNetworking!VerifyRpcClientAccessToSecurityDescriptor` at `0x18003edcc`

## pseudocode

```c
__int64 __fastcall ProfileManager::GetProfileXml(
        LPCRITICAL_SECTION lpCriticalSection,
        void *a2,
        unsigned int a3,
        struct _GUID *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        bool a7,
        unsigned __int16 **a8,
        unsigned int *a9,
        unsigned int *a10)
{
  unsigned int v12; // eax
  __int64 v13; // rcx
  const WCHAR *v14; // rdx
  __int64 v15; // rax
  int v16; // eax
  unsigned int v17; // eax
  struct _RTL_CRITICAL_SECTION *v18; // rdi
  __int64 v19; // rdx
  __int64 v20; // r8
  struct PM_PCB *v21; // rcx
  __int64 v22; // rcx
  char v23; // al
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  char v27; // al
  int v28; // eax
  unsigned __int16 **v29; // rax
  ULONGLONG v30; // rdx
  __int64 v31; // r8
  const char *v32; // r9
  unsigned __int16 *v33; // rcx
  unsigned __int16 *v34; // rax
  __int64 v35; // rcx
  void *v36; // rax
  unsigned int v37; // eax
  ULONGLONG *v38; // rcx
  ULONGLONG Keyword; // rax
  unsigned int ProfileXml; // eax
  bool v41; // zf
  unsigned int *v42; // rcx
  struct PM_PCB *v43; // rsi
  __int64 v44; // rcx
  unsigned int v45; // edi
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  unsigned __int16 *v49; // rax
  volatile signed __int32 *v50; // rbx
  __int64 result; // rax
  unsigned int UserDataCount; // [rsp+20h] [rbp-128h]
  unsigned int UserDataCounta; // [rsp+20h] [rbp-128h]
  WINBOOL v54; // [rsp+40h] [rbp-108h] BYREF
  unsigned int v55; // [rsp+44h] [rbp-104h]
  unsigned __int16 *v56; // [rsp+48h] [rbp-100h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-F8h] BYREF
  char v58; // [rsp+60h] [rbp-E8h]
  WINBOOL fPending[2]; // [rsp+68h] [rbp-E0h] BYREF
  struct PM_PCB *v60; // [rsp+70h] [rbp-D8h] BYREF
  volatile signed __int32 *v61; // [rsp+78h] [rbp-D0h]
  unsigned int *v62; // [rsp+80h] [rbp-C8h]
  LPCRITICAL_SECTION lpCriticalSectiona; // [rsp+88h] [rbp-C0h]
  struct _GUID *v64; // [rsp+90h] [rbp-B8h]
  unsigned __int16 **v65; // [rsp+98h] [rbp-B0h]
  struct _EVENT_DATA_DESCRIPTOR Context; // [rsp+A0h] [rbp-A8h] BYREF
  __int16 *v67; // [rsp+B0h] [rbp-98h]
  int v68; // [rsp+B8h] [rbp-90h]
  int v69; // [rsp+BCh] [rbp-8Ch]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-88h] BYREF
  int *v71; // [rsp+D0h] [rbp-78h]
  int v72; // [rsp+D8h] [rbp-70h]
  int v73; // [rsp+DCh] [rbp-6Ch]
  struct _GUID *v74; // [rsp+E0h] [rbp-68h]
  __int64 v75; // [rsp+E8h] [rbp-60h]
  const WCHAR *v76; // [rsp+F0h] [rbp-58h]
  int v77; // [rsp+F8h] [rbp-50h]
  int v78; // [rsp+FCh] [rbp-4Ch]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v64 = a4;
  v55 = a3;
  *(_QWORD *)&EventDescriptor.Id = a2;
  lpCriticalSectiona = lpCriticalSection;
  v65 = a8;
  v62 = a9;
  if ( a10 )
    *a10 = 0;
  *a8 = 0;
  v54 = 0;
  try
  {
    v12 = PmpCheckInterfaceGuidParameter(a4, a5, (unsigned int *)&v54);
    if ( v12 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xDFA,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
        (const char *)v12,
        UserDataCount);
    Context.Ptr = 0;
    fPending[0] = 0;
    if ( InitOnceBeginInitialize(&`WlansvcLogger::Instance'::`2'::wrapper, 0, fPending, (LPVOID *)&Context)
      && fPending[0] )
    {
      Context.Ptr = (ULONGLONG)&qword_1802A0DE8;
      qword_1802A0DF0 = 0;
      byte_1802A0DF8 = 0;
      dword_1802A0DFC = 0;
      qword_1802A0DE8 = (__int64)&WiFiCloudStoreTelemetry::`vftable';
      CallbackContext = &`WlansvcLogger::StaticHandle::StaticHandle'::`2'::__hInner;
      atexit(`WlansvcLogger::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
      qword_1802A0DF0 = (__int64)CallbackContext;
      byte_1802A0DF8 = 1;
      TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
      dword_1802A0DFC = 1;
      (*(void (__fastcall **)(__int64 *))(qword_1802A0DE8 + 8))(&qword_1802A0DE8);
      InitOnceComplete(&`WlansvcLogger::Instance'::`2'::wrapper, 0, &qword_1802A0DE8);
    }
    v13 = *(_QWORD *)(Context.Ptr + 8);
    if ( *(_DWORD *)v13 > 5u )
    {
      if ( a6 )
      {
        v14 = a6;
        v15 = -1;
        do
          ++v15;
        while ( a6[v15] );
        v16 = 2 * v15 + 2;
      }
      else
      {
        v14 = &word_180243548;
        v16 = 2;
      }
      v76 = v14;
      v77 = v16;
      v78 = 0;
      v74 = a4;
      v75 = 16;
      Context.Ptr = 0x50B000000LL;
      *(_QWORD *)&Context.Size = 0;
      UserData.Ptr = *(_QWORD *)(v13 + 8);
      UserData.Size = *(unsigned __int16 *)UserData.Ptr;
      UserData.Reserved = 2;
      v71 = &dword_180279F5C;
      v72 = 51;
      v73 = 1;
      fPending[0] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(*(_QWORD *)(v13 + 32), (PCEVENT_DESCRIPTOR)&Context, 0, 0, 4u, &UserData);
    }
    EnterCriticalSection(lpCriticalSection);
    *(_QWORD *)fPending = lpCriticalSection;
    Context.Ptr = 0;
    v17 = ProfileManager::ReferencePcbListEx(
            (ProfileManager *)lpCriticalSectiona,
            (void *)a7,
            *(void **)&EventDescriptor.Id,
            0,
            v64,
            v54,
            (struct PM_PCB_LIST **)&Context);
    if ( v17 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xE06,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
        (const char *)v17,
        UserDataCounta);
    v18 = lpCriticalSectiona;
    ProfileManager::FindKeyPcb(lpCriticalSectiona, &v60, Context.Ptr, a6);
    v21 = v60;
    if ( !v60 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xE0A,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
        (const char *)0x490,
        UserDataCounta);
    if ( (*((_BYTE *)v60 + 72) & 3) == 0 )
    {
      v22 = *((_QWORD *)v60 + 6);
      if ( !v22 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(0, v19, v20);
LABEL_20:
        v23 = 1;
        v21 = v60;
        goto LABEL_25;
      }
      v24 = VerifyRpcClientAccessToSecurityDescriptor(v22, 131073);
      if ( v24 == 5 )
        goto LABEL_20;
      if ( v24 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x248,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
          (const char *)v24,
          UserDataCounta);
      v21 = v60;
    }
    v23 = 0;
LABEL_25:
    if ( v23 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0xE0D,
        (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
        (const char *)5,
        UserDataCounta);
    v25 = *((_QWORD *)v21 + 1);
    if ( v25 )
    {
      v26 = *(_QWORD *)(v25 + 552);
      if ( v26 )
      {
        v28 = *(_DWORD *)(v26 + 20);
        if ( v28 != 8 && v28 != 32 || v55 >= 3 )
        {
          v27 = 0;
LABEL_30:
          if ( v27 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0xE10,
              (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
              (const char *)0x32,
              UserDataCounta);
          v56 = 0;
          if ( v62 && (*(_BYTE *)v62 & 4) != 0 )
          {
            if ( CanAccessPlainTextKey(*(HANDLE *)&EventDescriptor.Id, v21, v64, a7) )
            {
              v29 = (unsigned __int16 **)TryGenerateProfileXmlWithClearKey(&EventDescriptor, v60);
              v33 = *v29;
              *v29 = 0;
              v34 = v56;
              v56 = v33;
              if ( v34 )
                WpFreeMemory(v34);
              if ( *(_QWORD *)&EventDescriptor.Id )
                WpFreeMemory(*(_QWORD *)&EventDescriptor.Id);
            }
            else
            {
              Context.Ptr = 0;
              v54 = 0;
              if ( InitOnceBeginInitialize(&`WlansvcLogger::Instance'::`2'::wrapper, 0, &v54, (LPVOID *)&Context) && v54 )
              {
                Context.Ptr = (ULONGLONG)&qword_1802A0DE8;
                qword_1802A0DF0 = 0;
                byte_1802A0DF8 = 0;
                dword_1802A0DFC = 0;
                qword_1802A0DE8 = (__int64)&WiFiCloudStoreTelemetry::`vftable';
                CallbackContext = &`WlansvcLogger::StaticHandle::StaticHandle'::`2'::__hInner;
                atexit(`WlansvcLogger::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
                qword_1802A0DF0 = (__int64)CallbackContext;
                byte_1802A0DF8 = 1;
                TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
                dword_1802A0DFC = 1;
                (*(void (__fastcall **)(__int64 *))(qword_1802A0DE8 + 8))(&qword_1802A0DE8);
                InitOnceComplete(&`WlansvcLogger::Instance'::`2'::wrapper, 0, &qword_1802A0DE8);
              }
              v35 = *(_QWORD *)(Context.Ptr + 8);
              if ( *(_DWORD *)v35 > 3u )
              {
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                *(_DWORD *)&EventDescriptor.Level = 3;
                EventDescriptor.Keyword = 0;
                Context.Ptr = *(_QWORD *)(v35 + 8);
                Context.Size = *(unsigned __int16 *)Context.Ptr;
                Context.Reserved = 2;
                v67 = &word_18027A0FE;
                v68 = 65;
                v69 = 1;
                v55 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(*(_QWORD *)(v35 + 32), &EventDescriptor, 0, 0, 2u, &Context);
              }
            }
            if ( v56 )
            {
              v42 = v62;
              goto LABEL_66;
            }
            v21 = v60;
          }
          v36 = (void *)*((_QWORD *)v21 + 2);
          EventDescriptor.Keyword = 0;
          v58 = 1;
          if ( v36 )
          {
            *(_QWORD *)&EventDescriptor.Id = &v56;
            v37 = WcDuplicateString(v36);
            if ( v37 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0xE28,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                (const char *)v37,
                UserDataCounta);
            if ( v58 )
            {
              v38 = *(ULONGLONG **)&EventDescriptor.Id;
              Keyword = EventDescriptor.Keyword;
              goto LABEL_57;
            }
          }
          else
          {
            *(_QWORD *)&EventDescriptor.Id = &v56;
            ProfileXml = WpGenerateProfileXml(*((struct _PM_PROFILE **)v21 + 1));
            if ( ProfileXml )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0xE2D,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                (const char *)ProfileXml,
                UserDataCounta);
            if ( v58 )
            {
              v38 = *(ULONGLONG **)&EventDescriptor.Id;
              Keyword = EventDescriptor.Keyword;
LABEL_57:
              v30 = *v38;
              v41 = *v38 == 0;
              *v38 = Keyword;
              if ( !v41 )
                WpFreeMemory(v30);
            }
          }
          v42 = v62;
          if ( !v62 )
          {
            v43 = v60;
LABEL_61:
            if ( a10 )
            {
              if ( (*((_BYTE *)v43 + 72) & 3) != 0 )
              {
                v45 = 458787;
              }
              else
              {
                v44 = *((_QWORD *)v43 + 6);
                if ( !v44 )
                {
                  MicrosoftTelemetryAssertTriggeredNoArgs(0, v30, v31);
                  wil::details::in1diag3::Throw_Win32(
                    retaddr,
                    (void *)0x258,
                    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                    (const char *)5,
                    UserDataCounta);
                }
                v45 = 0;
                v46 = VerifyRpcClientAccessToSecurityDescriptor(v44, 131073);
                if ( v46 != 5 )
                {
                  if ( v46 )
                    wil::details::in1diag3::Throw_Win32(
                      retaddr,
                      (void *)0x264,
                      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                      (const char *)v46,
                      UserDataCounta);
                  v45 = 131073;
                }
                v47 = VerifyRpcClientAccessToSecurityDescriptor(*((_QWORD *)v43 + 6), 458787);
                if ( v47 != 5 )
                {
                  if ( v47 )
                    wil::details::in1diag3::Throw_Win32(
                      retaddr,
                      (void *)0x264,
                      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                      (const char *)v47,
                      UserDataCounta);
                  v45 |= 0x70023u;
                }
                v48 = VerifyRpcClientAccessToSecurityDescriptor(*((_QWORD *)v43 + 6), 131105);
                if ( v48 != 5 )
                {
                  if ( v48 )
                    wil::details::in1diag3::Throw_Win32(
                      retaddr,
                      (void *)0x264,
                      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                      (const char *)v48,
                      UserDataCounta);
                  v45 |= 0x20021u;
                }
              }
              *a10 = v45;
              v18 = lpCriticalSectiona;
            }
            v49 = v56;
            v56 = 0;
            *v65 = v49;
            v50 = v61;
            if ( v61 )
            {
              if ( _InterlockedExchangeAdd(v61 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
                if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
              }
            }
            if ( v18 )
              LeaveCriticalSection(v18);
            return 0;
          }
LABEL_66:
          v43 = v60;
          *v42 = *((_DWORD *)v60 + 18);
          goto LABEL_61;
        }
      }
      else
      {
        wil::details::in1diag3::Log_Win32(
          retaddr,
          (void *)0xBF8,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
          (const char *)0x57,
          UserDataCounta);
        v21 = v60;
      }
    }
    v27 = 1;
    goto LABEL_30;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Win32_Return_CaughtException(
                           retaddr,
                           (void *)0xE40,
                           (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\wlansvcext\\profilemanager\\src\\profilemanager.cpp",
                           v32);
  }
  return result;
}

```

## disassembly

```asm
0x18003e670  push    rbx
0x18003e672  push    rsi
0x18003e673  push    rdi
0x18003e674  push    r12
0x18003e676  push    r13
0x18003e678  push    r14
0x18003e67a  push    r15
0x18003e67c  sub     rsp, 110h
0x18003e683  mov     rax, cs:__security_cookie
0x18003e68a  xor     rax, rsp
0x18003e68d  mov     [rsp+148h+var_48], rax
0x18003e695  mov     r15, r9
0x18003e698  mov     [rsp+148h+var_B8], r9
0x18003e6a0  mov     [rsp+148h+var_104], r8d
0x18003e6a5  mov     qword ptr [rsp+148h+EventDescriptor.Id], rdx
0x18003e6aa  mov     r12, rcx
0x18003e6ad  mov     [rsp+148h+lpCriticalSection], rcx
0x18003e6b5  mov     rdi, [rsp+148h+arg_28]
0x18003e6bd  mov     rax, [rsp+148h+arg_38]
0x18003e6c5  mov     [rsp+148h+var_B0], rax
0x18003e6cd  mov     rcx, [rsp+148h+arg_40]
0x18003e6d5  mov     [rsp+148h+var_C8], rcx
0x18003e6dd  mov     r13, [rsp+148h+arg_48]
0x18003e6e5  xor     ebx, ebx
0x18003e6e7  test    r13, r13
0x18003e6ea  jz      short loc_18003E6F0
0x18003e6ec  mov     [r13+0], ebx
0x18003e6f0  mov     [rax], rbx
0x18003e6f3  mov     [rsp+148h+var_108], ebx
0x18003e6f7  lea     r8, [rsp+148h+var_108]; unsigned int *
0x18003e6fc  mov     edx, [rsp+148h+arg_20]; unsigned int
0x18003e703  mov     rcx, r15; struct _GUID *
0x18003e706  call    ?PmpCheckInterfaceGuidParameter@@YAKPEBU_GUID@@KPEAK@Z; PmpCheckInterfaceGuidParameter(_GUID const *,ulong,ulong *)
0x18003e70b  mov     rcx, [rsp+148h]; this
0x18003e713  test    eax, eax
0x18003e715  jnz     loc_18003EE8F
0x18003e71b  mov     [rsp+148h+Context], rbx
0x18003e723  mov     [rsp+148h+fPending], ebx
0x18003e727  lea     r9, [rsp+148h+Context]; lpContext
0x18003e72f  lea     r8, [rsp+148h+fPending]; fPending
0x18003e734  xor     edx, edx; dwFlags
0x18003e736  lea     rcx, ?wrapper@?1??Instance@WlansvcLogger@@KAPEAV2@XZ@4V?$static_lazy@VWlansvcLogger@@@details@wil@@A; lpInitOnce
0x18003e73d  call    cs:__imp_InitOnceBeginInitialize
0x18003e743  test    eax, eax
0x18003e745  jz      loc_18003E7EC
0x18003e74b  cmp     [rsp+148h+fPending], 0
0x18003e750  jz      loc_18003E7EC
0x18003e756  lea     rsi, qword_1802A0DE8
0x18003e75d  mov     [rsp+148h+Context], rsi
0x18003e765  mov     cs:qword_1802A0DF0, rbx
0x18003e76c  mov     cs:byte_1802A0DF8, 0
0x18003e773  mov     cs:dword_1802A0DFC, ebx
0x18003e779  lea     r14, ??_7WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::`vftable'
0x18003e780  mov     cs:qword_1802A0DE8, r14
0x18003e787  lea     r14, ?__hInner@?1???0StaticHandle@WlansvcLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WlansvcLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003e78e  mov     cs:CallbackContext, r14
0x18003e795  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@WlansvcLogger@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18003e79c  call    atexit
0x18003e7a1  mov     rcx, cs:CallbackContext; CallbackContext
0x18003e7a8  mov     cs:qword_1802A0DF0, rcx
0x18003e7af  mov     cs:byte_1802A0DF8, 1
0x18003e7b6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003e7bb  mov     cs:dword_1802A0DFC, 1
0x18003e7c5  mov     rax, cs:qword_1802A0DE8
0x18003e7cc  mov     rcx, rsi
0x18003e7cf  mov     rax, [rax+8]
0x18003e7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e7d8  mov     r8, rsi; lpContext
0x18003e7db  xor     edx, edx; dwFlags
0x18003e7dd  lea     rcx, ?wrapper@?1??Instance@WlansvcLogger@@KAPEAV2@XZ@4V?$static_lazy@VWlansvcLogger@@@details@wil@@A; lpInitOnce
0x18003e7e4  call    cs:__imp_InitOnceComplete
0x18003e7ea  jmp     short loc_18003E7F3
0x18003e7ec  lea     rsi, qword_1802A0DE8
0x18003e7f3  mov     rax, [rsp+148h+Context]
0x18003e7fb  mov     rcx, [rax+8]
0x18003e7ff  mov     eax, [rcx]
0x18003e801  cmp     eax, 5
0x18003e804  jbe     loc_18003E91B
0x18003e80a  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18003e811  test    rdi, rdi
0x18003e814  jz      short loc_18003E834
0x18003e816  mov     rdx, rdi
0x18003e819  mov     rax, r14
0x18003e81c  nop     dword ptr [rax+00h]
0x18003e820  lea     rax, [rax+1]
0x18003e824  cmp     word ptr [rdi+rax*2], 0
0x18003e829  jnz     short loc_18003E820
0x18003e82b  lea     eax, ds:2[rax*2]
0x18003e832  jmp     short loc_18003E840
0x18003e834  lea     rdx, word_180243548
0x18003e83b  mov     eax, 2
0x18003e840  mov     [rsp+148h+var_58], rdx
0x18003e848  mov     [rsp+148h+var_50], eax
0x18003e84f  mov     [rsp+148h+var_4C], ebx
0x18003e856  mov     [rsp+148h+var_68], r15
0x18003e85e  mov     [rsp+148h+var_60], 10h
0x18003e86a  mov     dword ptr [rsp+148h+Context], 0B000000h
0x18003e875  movzx   eax, cs:word_180279F52
0x18003e87c  mov     dword ptr [rsp+148h+Context+4], eax
0x18003e883  mov     [rsp+148h+var_A0], rbx
0x18003e88b  mov     rax, [rcx+8]
0x18003e88f  mov     [rsp+148h+var_88.Ptr], rax
0x18003e897  movzx   eax, word ptr [rax]
0x18003e89a  mov     [rsp+148h+var_88.Size], eax
0x18003e8a1  mov     dword ptr [rsp+148h+var_88.0Ch], 2
0x18003e8ac  lea     rax, dword_180279F5C
0x18003e8b3  mov     [rsp+148h+var_78], rax
0x18003e8bb  mov     [rsp+148h+var_70], 33h ; '3'
0x18003e8c6  mov     [rsp+148h+var_6C], 1
0x18003e8d1  lea     r15, _TraceLoggingMetadataEnd
0x18003e8d8  mov     rax, r15
0x18003e8db  lea     rdx, _TraceLoggingMetadata
0x18003e8e2  sub     eax, edx
0x18003e8e4  mov     [rsp+148h+fPending], eax
0x18003e8e8  mov     eax, [rsp+148h+fPending]
0x18003e8ec  lea     rax, [rsp+148h+var_88]
0x18003e8f4  mov     [rsp+148h+UserData], rax; UserData
0x18003e8f9  mov     [rsp+148h+UserDataCount], 4; UserDataCount
0x18003e901  xor     r9d, r9d; RelatedActivityId
0x18003e904  xor     r8d, r8d; ActivityId
0x18003e907  lea     rdx, [rsp+148h+Context]; EventDescriptor
0x18003e90f  mov     rcx, [rcx+20h]; RegHandle
0x18003e913  call    cs:__imp_EventWriteTransfer
0x18003e919  jmp     short loc_18003E929
0x18003e91b  mov     r14, 0FFFFFFFFFFFFFFFFh
0x18003e922  lea     r15, _TraceLoggingMetadataEnd
0x18003e929  mov     rcx, r12; lpCriticalSection
0x18003e92c  call    cs:__imp_EnterCriticalSection
0x18003e932  mov     qword ptr [rsp+148h+fPending], r12
0x18003e937  mov     [rsp+148h+Context], rbx
0x18003e93f  movzx   r12d, [rsp+148h+arg_30]
0x18003e948  mov     edx, r12d; int
0x18003e94b  lea     rax, [rsp+148h+Context]
0x18003e953  mov     [rsp+148h+var_118], rax; struct PM_PCB_LIST **
0x18003e958  mov     eax, [rsp+148h+var_108]
0x18003e95c  mov     dword ptr [rsp+148h+UserData], eax; unsigned int
0x18003e960  mov     rax, [rsp+148h+var_B8]
0x18003e968  mov     qword ptr [rsp+148h+UserDataCount], rax; unsigned int
0x18003e96d  xor     r9d, r9d; void *
0x18003e970  mov     r8, qword ptr [rsp+148h+EventDescriptor.Id]; void *
0x18003e975  mov     rcx, [rsp+148h+lpCriticalSection]; this
0x18003e97d  call    ?ReferencePcbListEx@ProfileManager@@AEAAKHPEAX0PEBU_GUID@@KPEAPEAUPM_PCB_LIST@@@Z; ProfileManager::ReferencePcbListEx(int,void *,void *,_GUID const *,ulong,PM_PCB_LIST * *)
0x18003e982  mov     rcx, [rsp+148h]; this
0x18003e98a  test    eax, eax
0x18003e98c  jnz     loc_18003EEA4
0x18003e992  mov     r9, rdi
0x18003e995  mov     r8, [rsp+148h+Context]
0x18003e99d  lea     rdx, [rsp+148h+var_D8]
0x18003e9a2  mov     rdi, [rsp+148h+lpCriticalSection]
0x18003e9aa  mov     rcx, rdi
0x18003e9ad  call    ?FindKeyPcb@ProfileManager@@AEBA?AV?$shared_ptr@UPM_PCB@@@std@@AEBUPM_PCB_LIST@@PEBG@Z; ProfileManager::FindKeyPcb(PM_PCB_LIST const &,ushort const *)
0x18003e9b2  nop
0x18003e9b3  mov     rcx, [rsp+148h+var_D8]
0x18003e9b8  test    rcx, rcx
0x18003e9bb  setz    al
0x18003e9be  mov     r10, [rsp+148h]
0x18003e9c6  test    al, al
0x18003e9c8  jnz     loc_18003EEB9
0x18003e9ce  test    byte ptr [rcx+48h], 3
0x18003e9d2  jnz     short loc_18003EA10
0x18003e9d4  mov     rcx, [rcx+30h]
0x18003e9d8  test    rcx, rcx
0x18003e9db  jnz     short loc_18003E9EB
0x18003e9dd  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "false")
0x18003e9e2  mov     al, 1
0x18003e9e4  mov     rcx, [rsp+148h+var_D8]
0x18003e9e9  jmp     short loc_18003EA12
0x18003e9eb  mov     edx, 20001h
0x18003e9f0  call    cs:__imp_VerifyRpcClientAccessToSecurityDescriptor
0x18003e9f6  cmp     eax, 5
0x18003e9f9  jz      short loc_18003E9E2
0x18003e9fb  mov     rcx, [rsp+148h]; this
0x18003ea03  test    eax, eax
0x18003ea05  jnz     loc_18003EED3
0x18003ea0b  mov     rcx, [rsp+148h+var_D8]
0x18003ea10  xor     al, al
0x18003ea12  mov     r10, [rsp+148h]
0x18003ea1a  test    al, al
0x18003ea1c  jnz     loc_18003EEE7
0x18003ea22  mov     rax, [rcx+8]
0x18003ea26  test    rax, rax
0x18003ea29  jz      short loc_18003EA5B
0x18003ea2b  mov     rax, [rax+228h]
0x18003ea32  test    rax, rax
0x18003ea35  jnz     short loc_18003EA6F
0x18003ea37  mov     rcx, [rsp+148h]; this
0x18003ea3f  mov     r9d, 57h ; 'W'; char *
0x18003ea45  lea     r8, aOnecoreuapNetW_63; "onecoreuap\\net\\wlan\\autocfg\\wlansvc"...
0x18003ea4c  mov     edx, 0BF8h; void *
0x18003ea51  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x18003ea56  mov     rcx, [rsp+148h+var_D8]
0x18003ea5b  mov     al, 1
0x18003ea5d  mov     r10, [rsp+148h]
0x18003ea65  test    al, al
0x18003ea67  jnz     loc_18003EF01
0x18003ea6d  jmp     short loc_18003EA87
0x18003ea6f  mov     eax, [rax+14h]
0x18003ea72  cmp     eax, 8
0x18003ea75  jz      short loc_18003EA7C
0x18003ea77  cmp     eax, 20h ; ' '
0x18003ea7a  jnz     short loc_18003EA83
0x18003ea7c  cmp     [rsp+148h+var_104], 3
0x18003ea81  jb      short loc_18003EA5B
0x18003ea83  xor     al, al
0x18003ea85  jmp     short loc_18003EA5D
0x18003ea87  mov     [rsp+148h+var_100], rbx
0x18003ea8c  mov     rax, [rsp+148h+var_C8]
0x18003ea94  test    rax, rax
0x18003ea97  jz      loc_18003EC90
0x18003ea9d  test    byte ptr [rax], 4
0x18003eaa0  jz      loc_18003EC90
0x18003eaa6  movzx   r9d, r12b; bool
0x18003eaaa  mov     r8, [rsp+148h+var_B8]; struct _GUID *
0x18003eab2  mov     rdx, rcx; struct PM_PCB *
0x18003eab5  mov     rcx, qword ptr [rsp+148h+EventDescriptor.Id]; TokenHandle
0x18003eaba  call    ?CanAccessPlainTextKey@@YA_NQEAXAEAUPM_PCB@@AEBU_GUID@@_N@Z; CanAccessPlainTextKey(void * const,PM_PCB &,_GUID const &,bool)
0x18003eabf  test    al, al
0x18003eac1  jz      short loc_18003EB05
0x18003eac3  mov     rdx, [rsp+148h+var_D8]
0x18003eac8  lea     rcx, [rsp+148h+EventDescriptor]
0x18003eacd  call    ?TryGenerateProfileXmlWithClearKey@@YA?AV?$unique_ptr@GU?$integral_constant@P6AXPEAX@Z$1?WpFreeMemory@@YAX0@Z@std@@@std@@AEBUPM_PCB@@@Z; TryGenerateProfileXmlWithClearKey(PM_PCB const &)
0x18003ead2  mov     rcx, [rax]
0x18003ead5  mov     [rax], rbx
0x18003ead8  mov     rax, [rsp+148h+var_100]
0x18003eadd  mov     [rsp+148h+var_100], rcx
0x18003eae2  test    rax, rax
0x18003eae5  jz      short loc_18003EAF0
0x18003eae7  mov     rcx, rax
0x18003eaea  call    WpFreeMemory
0x18003eaef  nop
0x18003eaf0  mov     rcx, qword ptr [rsp+148h+EventDescriptor.Id]
0x18003eaf5  test    rcx, rcx
0x18003eaf8  jz      short loc_18003EB00
0x18003eafa  call    WpFreeMemory
0x18003eaff  nop
0x18003eb00  jmp     loc_18003EC7F
0x18003eb05  mov     [rsp+148h+Context], rbx
0x18003eb0d  mov     [rsp+148h+var_108], ebx
0x18003eb11  lea     r9, [rsp+148h+Context]; lpContext
0x18003eb19  lea     r8, [rsp+148h+var_108]; fPending
0x18003eb1e  xor     edx, edx; dwFlags
0x18003eb20  lea     rcx, ?wrapper@?1??Instance@WlansvcLogger@@KAPEAV2@XZ@4V?$static_lazy@VWlansvcLogger@@@details@wil@@A; lpInitOnce
0x18003eb27  call    cs:__imp_InitOnceBeginInitialize
0x18003eb2d  test    eax, eax
0x18003eb2f  jz      loc_18003EBCD
0x18003eb35  cmp     [rsp+148h+var_108], 0
0x18003eb3a  jz      loc_18003EBCD
0x18003eb40  mov     [rsp+148h+Context], rsi
0x18003eb48  mov     cs:qword_1802A0DF0, rbx
0x18003eb4f  mov     cs:byte_1802A0DF8, 0
0x18003eb56  mov     cs:dword_1802A0DFC, ebx
0x18003eb5c  lea     rax, ??_7WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::`vftable'
0x18003eb63  mov     cs:qword_1802A0DE8, rax
0x18003eb6a  lea     rax, ?__hInner@?1???0StaticHandle@WlansvcLogger@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WlansvcLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18003eb71  mov     cs:CallbackContext, rax
0x18003eb78  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@WlansvcLogger@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18003eb7f  call    atexit
0x18003eb84  mov     rcx, cs:CallbackContext; CallbackContext
0x18003eb8b  mov     cs:qword_1802A0DF0, rcx
0x18003eb92  mov     cs:byte_1802A0DF8, 1
0x18003eb99  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18003eb9e  mov     cs:dword_1802A0DFC, 1
0x18003eba8  mov     rax, cs:qword_1802A0DE8
0x18003ebaf  mov     rcx, rsi
0x18003ebb2  mov     rax, [rax+8]
0x18003ebb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ebbb  mov     r8, rsi; lpContext
0x18003ebbe  xor     edx, edx; dwFlags
0x18003ebc0  lea     rcx, ?wrapper@?1??Instance@WlansvcLogger@@KAPEAV2@XZ@4V?$static_lazy@VWlansvcLogger@@@details@wil@@A; lpInitOnce
0x18003ebc7  call    cs:__imp_InitOnceComplete
0x18003ebcd  mov     rax, [rsp+148h+Context]
0x18003ebd5  mov     rcx, [rax+8]
0x18003ebd9  mov     eax, [rcx]
0x18003ebdb  cmp     eax, 3
0x18003ebde  jbe     loc_18003EC7F
0x18003ebe4  mov     dword ptr [rsp+148h+EventDescriptor.Id], 0B000000h
0x18003ebec  movzx   eax, cs:word_18027A0F4
0x18003ebf3  mov     dword ptr [rsp+148h+EventDescriptor.Level], eax
0x18003ebf7  mov     [rsp+148h+EventDescriptor.Keyword], rbx
0x18003ebfc  mov     rax, [rcx+8]
0x18003ec00  mov     [rsp+148h+Context], rax
0x18003ec08  movzx   eax, word ptr [rax]
0x18003ec0b  mov     dword ptr [rsp+148h+var_A0], eax
0x18003ec12  mov     dword ptr [rsp+148h+var_A0+4], 2
0x18003ec1d  lea     rax, word_18027A0FE
0x18003ec24  mov     [rsp+148h+var_98], rax
0x18003ec2c  mov     [rsp+148h+var_90], 41h ; 'A'
0x18003ec37  mov     [rsp+148h+var_8C], 1
0x18003ec42  lea     rax, _TraceLoggingMetadata
0x18003ec49  sub     r15d, eax
0x18003ec4c  mov     [rsp+148h+var_104], r15d
0x18003ec51  mov     eax, [rsp+148h+var_104]
0x18003ec55  lea     rax, [rsp+148h+Context]
0x18003ec5d  mov     [rsp+148h+UserData], rax; UserData
0x18003ec62  mov     [rsp+148h+UserDataCount], 2; unsigned int
0x18003ec6a  xor     r9d, r9d; RelatedActivityId
0x18003ec6d  xor     r8d, r8d; ActivityId
0x18003ec70  lea     rdx, [rsp+148h+EventDescriptor]; EventDescriptor
0x18003ec75  mov     rcx, [rcx+20h]; RegHandle
0x18003ec79  call    cs:__imp_EventWriteTransfer
  ... truncated ...
```
