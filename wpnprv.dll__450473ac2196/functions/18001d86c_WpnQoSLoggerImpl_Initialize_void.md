# WpnQoSLoggerImpl::Initialize(void)

- ea: `0x18001d86c`
- end: `0x18001dc42`
- name: `?Initialize@WpnQoSLoggerImpl@@SAJXZ`
- size: `982`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011354`

## callees

- `0x18000795c`
- `0x18000fddc`
- `0x18000fe54`
- `0x18001c06c`
- `0x18001d86c`
- `0x18001f554`
- `0x18001f970`
- `0x1800852d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001da44`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001da44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d971`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d8fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d971`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18001da60`
- `api-ms-win-core-localization-l1-2-0!GetUserGeoID` at `0x18001da60`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001d95c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolCleanupGroup` at `0x18001d95c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18001d8ea`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18001d8ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc2f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001dc2f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001da0f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001da0f`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x18001da4f`
- `api-ms-win-power-base-l1-1-0!PowerDeterminePlatformRoleEx` at `0x18001da4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall WpnQoSLoggerImpl::Initialize(__int64 a1)
{
  signed int LastError; // eax
  unsigned int v2; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  struct _TP_CLEANUP_GROUP *v6; // rcx
  signed int v7; // eax
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  int v10; // eax
  int v11; // eax
  int phkResult; // [rsp+20h] [rbp-18h]
  int phkResulta; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v16; // [rsp+40h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF
  _QWORD *v18; // [rsp+50h] [rbp+18h]

  if ( WpnQoSLoggerImpl::s_DataConnectionLogger )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  if ( WpnQoSLoggerImpl::s_TestConnectionLogger )
    MicrosoftTelemetryAssertTriggeredNoArgs(a1);
  hKey = 0;
  *(_OWORD *)&WpnQoSLoggerImpl::s_Environment.RaceDll = 0;
  v16 = 0;
  WpnQoSLoggerImpl::s_Environment.Version = 3;
  WpnQoSLoggerImpl::s_Environment.Pool = 0;
  WpnQoSLoggerImpl::s_Environment.CleanupGroup = 0;
  WpnQoSLoggerImpl::s_Environment.CleanupGroupCancelCallback = 0;
  WpnQoSLoggerImpl::s_Environment.FinalizationCallback = 0;
  WpnQoSLoggerImpl::s_Environment.u.Flags = 0;
  WpnQoSLoggerImpl::s_Environment.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  WpnQoSLoggerImpl::s_Environment.Size = 72;
  WpnQoSLoggerImpl::s_ThreadPool = CreateThreadpool(0);
  if ( !WpnQoSLoggerImpl::s_ThreadPool )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    if ( (v2 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x23D,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
        (const char *)v2,
        phkResult);
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      {
        v4 = 25;
LABEL_12:
        v5 = v2;
LABEL_41:
        WPP_SF_d(v3[2], v4, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids, v5);
        goto LABEL_42;
      }
      goto LABEL_42;
    }
  }
  WpnQoSLoggerImpl::s_CleanupGroup = CreateThreadpoolCleanupGroup();
  v6 = WpnQoSLoggerImpl::s_CleanupGroup;
  if ( WpnQoSLoggerImpl::s_CleanupGroup )
  {
LABEL_21:
    WpnQoSLoggerImpl::s_Environment.Pool = WpnQoSLoggerImpl::s_ThreadPool;
    WpnQoSLoggerImpl::s_Environment.CleanupGroup = v6;
    WpnQoSLoggerImpl::s_Environment.CleanupGroupCancelCallback = 0;
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications",
            0,
            0x20019u,
            &hKey)
      && (int)WpnRegLoadDWord(hKey, L"QoSLoggerDelay", &v16) >= 0 )
    {
      WpnQoSLoggerImpl::s_QoSLoggerDelaySeconds = v16;
    }
    InitializeCriticalSection(&WpnQoSLoggerImpl::s_TimerLock);
    WpnQoSLoggerImpl::s_PlatformRole = (unsigned int)PowerDeterminePlatformRoleEx(2);
    WpnQoSLoggerImpl::s_GeoId = GetUserGeoID(0x10u);
    v8 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
    v18 = v8;
    if ( v8 )
    {
      v8[1] = 1;
      *v8 = &WpnQoSLoggerImpl::`vftable';
      *((_DWORD *)v8 + 4) = 1;
      WpnQoSLoggerImpl::s_DataConnectionLogger = (struct WpnQoSLoggerImpl *)v8;
      v9 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
      v18 = v9;
      if ( v9 )
      {
        *v9 = &WpnQoSLoggerImpl::`vftable';
        v9[1] = 2;
        *((_DWORD *)v9 + 4) = 1;
        WpnQoSLoggerImpl::s_TestConnectionLogger = (struct WpnQoSLoggerImpl *)v9;
        v10 = WatsonWrapper::Initialize();
        v2 = v10;
        if ( v10 >= 0 )
        {
          v11 = SqmApiWrapper::Initialize();
          v2 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x269,
              (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
              (const char *)(unsigned int)v11,
              phkResulta);
            v3 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
            {
              v4 = 30;
              goto LABEL_12;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x266,
            (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
            (const char *)(unsigned int)v10,
            phkResulta);
          v3 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
          {
            v4 = 29;
            goto LABEL_12;
          }
        }
        goto LABEL_42;
      }
      WpnQoSLoggerImpl::s_TestConnectionLogger = 0;
      v2 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x263,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_42;
      v4 = 28;
    }
    else
    {
      WpnQoSLoggerImpl::s_DataConnectionLogger = 0;
      v2 = -2147024882;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x260,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_42;
      v4 = 27;
    }
    v5 = 2147942414LL;
    goto LABEL_41;
  }
  v7 = GetLastError();
  v2 = v7;
  if ( v7 > 0 )
    v2 = (unsigned __int16)v7 | 0x80070000;
  if ( (v2 & 0x80000000) == 0 )
  {
    v6 = WpnQoSLoggerImpl::s_CleanupGroup;
    goto LABEL_21;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x244,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\prov\\qos\\wpnqosloggerimpl.cpp",
    (const char *)v2,
    phkResult);
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v4 = 26;
    goto LABEL_12;
  }
LABEL_42:
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x18001d86c  mov     [rsp+arg_18], rbx
0x18001d871  push    rdi
0x18001d872  sub     rsp, 30h
0x18001d876  xor     edi, edi
0x18001d878  cmp     cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, rdi; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001d87f  jz      short loc_18001D886
0x18001d881  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d886  cmp     cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, rdi; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001d88d  jz      short loc_18001D894
0x18001d88f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001d894  xorps   xmm0, xmm0
0x18001d897  mov     [rsp+38h+hKey], rdi
0x18001d89c  xor     ecx, ecx; reserved
0x18001d89e  movdqa  xmmword ptr cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8a6  mov     [rsp+38h+arg_0], edi
0x18001d8aa  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.Version, 3; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8b4  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rdi; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8bb  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rdi; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8c2  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8c9  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, rdi; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8d0  mov     dword ptr cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.u, edi; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8d6  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8e0  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d8ea  call    cs:__imp_CreateThreadpool
0x18001d8f0  mov     cs:?s_ThreadPool@WpnQoSLoggerImpl@@0PEAU_TP_POOL@@EA, rax; _TP_POOL * WpnQoSLoggerImpl::s_ThreadPool
0x18001d8f7  test    rax, rax
0x18001d8fa  jnz     short loc_18001D95C
0x18001d8fc  call    cs:__imp_GetLastError
0x18001d902  mov     ebx, eax
0x18001d904  test    eax, eax
0x18001d906  jle     short loc_18001D911
0x18001d908  movzx   ebx, ax
0x18001d90b  or      ebx, 80070000h
0x18001d911  test    ebx, ebx
0x18001d913  jns     short loc_18001D95C
0x18001d915  mov     rcx, [rsp+38h]; this
0x18001d91a  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d921  mov     r9d, ebx; char *
0x18001d924  mov     edx, 23Dh; void *
0x18001d929  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d92e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d935  lea     rax, WPP_GLOBAL_Control
0x18001d93c  cmp     rcx, rax
0x18001d93f  jz      loc_18001DC25
0x18001d945  test    byte ptr [rcx+1Ch], 80h
0x18001d949  jz      loc_18001DC25
0x18001d94f  mov     edx, 19h
0x18001d954  mov     r9d, ebx
0x18001d957  jmp     loc_18001DC15
0x18001d95c  call    cs:__imp_CreateThreadpoolCleanupGroup
0x18001d962  mov     cs:?s_CleanupGroup@WpnQoSLoggerImpl@@0PEAU_TP_CLEANUP_GROUP@@EA, rax; _TP_CLEANUP_GROUP * WpnQoSLoggerImpl::s_CleanupGroup
0x18001d969  mov     rcx, rax
0x18001d96c  test    rax, rax
0x18001d96f  jnz     short loc_18001D9D2
0x18001d971  call    cs:__imp_GetLastError
0x18001d977  mov     ebx, eax
0x18001d979  test    eax, eax
0x18001d97b  jle     short loc_18001D986
0x18001d97d  movzx   ebx, ax
0x18001d980  or      ebx, 80070000h
0x18001d986  test    ebx, ebx
0x18001d988  jns     short loc_18001D9CB
0x18001d98a  mov     rcx, [rsp+38h]; this
0x18001d98f  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001d996  mov     r9d, ebx; char *
0x18001d999  mov     edx, 244h; void *
0x18001d99e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d9a3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d9aa  lea     rax, WPP_GLOBAL_Control
0x18001d9b1  cmp     rcx, rax
0x18001d9b4  jz      loc_18001DC25
0x18001d9ba  test    byte ptr [rcx+1Ch], 80h
0x18001d9be  jz      loc_18001DC25
0x18001d9c4  mov     edx, 1Ah
0x18001d9c9  jmp     short loc_18001D954
0x18001d9cb  mov     rcx, cs:?s_CleanupGroup@WpnQoSLoggerImpl@@0PEAU_TP_CLEANUP_GROUP@@EA; _TP_CLEANUP_GROUP * WpnQoSLoggerImpl::s_CleanupGroup
0x18001d9d2  mov     rax, cs:?s_ThreadPool@WpnQoSLoggerImpl@@0PEAU_TP_POOL@@EA; _TP_POOL * WpnQoSLoggerImpl::s_ThreadPool
0x18001d9d9  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001d9e0  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d9e7  mov     r9d, 20019h; samDesired
0x18001d9ed  lea     rax, [rsp+38h+hKey]
0x18001d9f2  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, rcx; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001d9f9  xor     r8d, r8d; ulOptions
0x18001d9fc  mov     qword ptr [rsp+38h+phkResult], rax; int
0x18001da01  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001da08  mov     cs:?s_Environment@WpnQoSLoggerImpl@@0U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, rdi; _TP_CALLBACK_ENVIRON_V3 WpnQoSLoggerImpl::s_Environment ...
0x18001da0f  call    cs:__imp_RegOpenKeyExW
0x18001da15  test    eax, eax
0x18001da17  jnz     short loc_18001DA3D
0x18001da19  mov     rcx, [rsp+38h+hKey]; hKey
0x18001da1e  lea     r8, [rsp+38h+arg_0]; unsigned int *
0x18001da23  lea     rdx, aQosloggerdelay; "QoSLoggerDelay"
0x18001da2a  call    ?WpnRegLoadDWord@@YAJPEAUHKEY__@@PEBGPEAK@Z; WpnRegLoadDWord(HKEY__ *,ushort const *,ulong *)
0x18001da2f  test    eax, eax
0x18001da31  js      short loc_18001DA3D
0x18001da33  mov     eax, [rsp+38h+arg_0]
0x18001da37  mov     cs:?s_QoSLoggerDelaySeconds@WpnQoSLoggerImpl@@0KA, eax; ulong WpnQoSLoggerImpl::s_QoSLoggerDelaySeconds
0x18001da3d  lea     rcx, ?s_TimerLock@WpnQoSLoggerImpl@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001da44  call    cs:__imp_InitializeCriticalSection
0x18001da4a  mov     ecx, 2
0x18001da4f  call    cs:__imp_PowerDeterminePlatformRoleEx
0x18001da55  mov     ecx, 10h; GeoClass
0x18001da5a  mov     cs:?s_PlatformRole@WpnQoSLoggerImpl@@0W4_POWER_PLATFORM_ROLE@@A, eax; _POWER_PLATFORM_ROLE WpnQoSLoggerImpl::s_PlatformRole
0x18001da60  call    cs:__imp_GetUserGeoID
0x18001da66  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001da6d  mov     ecx, 18h; unsigned __int64
0x18001da72  mov     cs:?s_GeoId@WpnQoSLoggerImpl@@0JA, eax; long WpnQoSLoggerImpl::s_GeoId
0x18001da78  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001da7d  mov     [rsp+38h+arg_10], rax
0x18001da82  test    rax, rax
0x18001da85  jz      loc_18001DBCB
0x18001da8b  lea     rbx, ??_7WpnQoSLoggerImpl@@6B@; const WpnQoSLoggerImpl::`vftable'
0x18001da92  mov     qword ptr [rax+8], 1
0x18001da9a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001daa1  mov     [rax], rbx
0x18001daa4  mov     ecx, 18h; unsigned __int64
0x18001daa9  mov     dword ptr [rax+10h], 1
0x18001dab0  mov     cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, rax; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001dab7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001dabc  mov     [rsp+38h+arg_10], rax
0x18001dac1  test    rax, rax
0x18001dac4  jz      loc_18001DB85
0x18001daca  mov     [rax], rbx
0x18001dacd  mov     qword ptr [rax+8], 2
0x18001dad5  mov     dword ptr [rax+10h], 1
0x18001dadc  mov     cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, rax; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001dae3  call    ?Initialize@WatsonWrapper@@SAJXZ; WatsonWrapper::Initialize(void)
0x18001dae8  mov     ebx, eax
0x18001daea  test    eax, eax
0x18001daec  jns     short loc_18001DB32
0x18001daee  mov     rcx, [rsp+38h]; this
0x18001daf3  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dafa  mov     r9d, eax; char *
0x18001dafd  mov     edx, 266h; void *
0x18001db02  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001db07  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db0e  lea     rax, WPP_GLOBAL_Control
0x18001db15  cmp     rcx, rax
0x18001db18  jz      loc_18001DC25
0x18001db1e  test    byte ptr [rcx+1Ch], 80h
0x18001db22  jz      loc_18001DC25
0x18001db28  mov     edx, 1Dh
0x18001db2d  jmp     loc_18001D954
0x18001db32  call    ?Initialize@SqmApiWrapper@@SAJXZ; SqmApiWrapper::Initialize(void)
0x18001db37  mov     ebx, eax
0x18001db39  test    eax, eax
0x18001db3b  jns     loc_18001DC25
0x18001db41  mov     rcx, [rsp+38h]; this
0x18001db46  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001db4d  mov     r9d, eax; char *
0x18001db50  mov     edx, 269h; void *
0x18001db55  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001db5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001db61  lea     rax, WPP_GLOBAL_Control
0x18001db68  cmp     rcx, rax
0x18001db6b  jz      loc_18001DC25
0x18001db71  test    byte ptr [rcx+1Ch], 80h
0x18001db75  jz      loc_18001DC25
0x18001db7b  mov     edx, 1Eh
0x18001db80  jmp     loc_18001D954
0x18001db85  mov     rcx, [rsp+38h]; this
0x18001db8a  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001db91  mov     r9d, 8007000Eh; char *
0x18001db97  mov     cs:?s_TestConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, rdi; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_TestConnectionLogger
0x18001db9e  mov     edx, 263h; void *
0x18001dba3  mov     ebx, r9d
0x18001dba6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dbab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbb2  lea     rax, WPP_GLOBAL_Control
0x18001dbb9  cmp     rcx, rax
0x18001dbbc  jz      short loc_18001DC25
0x18001dbbe  test    byte ptr [rcx+1Ch], 80h
0x18001dbc2  jz      short loc_18001DC25
0x18001dbc4  mov     edx, 1Ch
0x18001dbc9  jmp     short loc_18001DC0F
0x18001dbcb  mov     rcx, [rsp+38h]; this
0x18001dbd0  lea     r8, aOnecoreuapBase_20; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18001dbd7  mov     r9d, 8007000Eh; char *
0x18001dbdd  mov     cs:?s_DataConnectionLogger@WpnQoSLoggerImpl@@0PEAV1@EA, rdi; WpnQoSLoggerImpl * WpnQoSLoggerImpl::s_DataConnectionLogger
0x18001dbe4  mov     edx, 260h; void *
0x18001dbe9  mov     ebx, r9d
0x18001dbec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dbf1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbf8  lea     rax, WPP_GLOBAL_Control
0x18001dbff  cmp     rcx, rax
0x18001dc02  jz      short loc_18001DC25
0x18001dc04  test    byte ptr [rcx+1Ch], 80h
0x18001dc08  jz      short loc_18001DC25
0x18001dc0a  mov     edx, 1Bh
0x18001dc0f  mov     r9d, 8007000Eh
0x18001dc15  mov     rcx, [rcx+10h]
0x18001dc19  lea     r8, WPP_b4f52972f4d4384da41e73b76c391f2b_Traceguids
0x18001dc20  call    WPP_SF_d
0x18001dc25  mov     rcx, [rsp+38h+hKey]; hKey
0x18001dc2a  test    rcx, rcx
0x18001dc2d  jz      short loc_18001DC35
0x18001dc2f  call    cs:__imp_RegCloseKey
0x18001dc35  mov     eax, ebx
0x18001dc37  mov     rbx, [rsp+38h+arg_18]
0x18001dc3c  add     rsp, 30h
0x18001dc40  pop     rdi
0x18001dc41  retn
```
