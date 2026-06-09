# PeriodicUpdateManager::SetupTimer(_WPN_FILE_TIME,__MIDL___MIDL_itf_wpnplatform_0000_0007_0003,_WPN_TIMER_PERSISTENCE *,_GUID *)

- ea: `0x1800d8d0c`
- end: `0x1800d928a`
- name: `?SetupTimer@PeriodicUpdateManager@@AEAAJU_WPN_FILE_TIME@@W4__MIDL___MIDL_itf_wpnplatform_0000_0007_0003@@PEAU_WPN_TIMER_PERSISTENCE@@PEAU_GUID@@@Z`
- size: `1406`
- prototype: `int __high(struct _WPN_FILE_TIME, enum __MIDL___MIDL_itf_wpnplatform_0000_0007_0003, struct _WPN_TIMER_PERSISTENCE *, struct _GUID *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d8340`

## callees

- `0x180024640`
- `0x18002ee38`
- `0x180078cd4`
- `0x180088504`
- `0x1800af0a4`
- `0x1800b99f0`
- `0x1800ba574`
- `0x1800d8d0c`
- `0x1800f5990`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8dd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8dd2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d8da2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d8da2`
- `ntdll!RtlNtStatusToDosError` at `0x1800d9094`
- `ntdll!RtlNtStatusToDosError` at `0x1800d91dd`
- `ntdll!RtlNtStatusToDosError` at `0x1800d9094`
- `ntdll!RtlNtStatusToDosError` at `0x1800d91dd`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800d8dc8`
- `api-ms-win-core-timezone-l1-1-0!FileTimeToSystemTime` at `0x1800d8dc8`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtCreateEventForPackageName` at `0x1800d91cd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtCreateEventForPackageName` at `0x1800d91cd`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x1800d907e`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtAssociateActivationProxy` at `0x1800d907e`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x1800d9249`
- `api-ms-win-core-biptcltapi-l1-1-7!BiPtDisassociateWorkItemEx` at `0x1800d9249`
- `TimeBrokerClient!TbCreateEvent` at `0x1800d8f2a`
- `TimeBrokerClient!TbCreateEvent` at `0x1800d8f2a`
- `TimeBrokerClient!TbDeleteEvent` at `0x1800d910e`
- `TimeBrokerClient!TbDeleteEvent` at `0x1800d910e`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1800d9129`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1800d9149`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1800d9129`
- `SystemEventsBrokerClient!SebDeleteEvent` at `0x1800d9149`

## string_xrefs

- `0x1800d8dee`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800d8f3d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800d8fab`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800d9015`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800d90b5`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800d916d`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`
- `0x1800d91fa`: `onecoreuap\base\diagnosis\platform\notifications\platform\endpoint\periodicupdatemanager.cpp`

## pseudocode

```c
__int64 __fastcall PeriodicUpdateManager::SetupTimer(__int64 a1, __int64 a2, unsigned int a3, __int128 *a4, _OWORD *a5)
{
  __int64 v8; // rbx
  __int64 v9; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  bool v14; // cf
  __int64 v15; // r14
  int v16; // eax
  SebEvents *v17; // rcx
  int v18; // r12d
  int InternetAvailableEvent; // eax
  SebEvents *v20; // rcx
  int v21; // esi
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  int DisplayOnEvent; // eax
  NTSTATUS v25; // eax
  unsigned int v26; // edx
  signed int v27; // eax
  int UserSid; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  _QWORD *v31; // rcx
  __int64 v32; // rdx
  NTSTATUS v33; // eax
  signed int v34; // eax
  int v36; // [rsp+20h] [rbp-E0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v38; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v39; // [rsp+60h] [rbp-A0h] BYREF
  char v40; // [rsp+68h] [rbp-98h]
  __int128 *v41; // [rsp+70h] [rbp-90h]
  char v42; // [rsp+78h] [rbp-88h]
  __m256i v43; // [rsp+80h] [rbp-80h] BYREF
  __int128 v44; // [rsp+A0h] [rbp-60h]
  __int128 v45; // [rsp+B0h] [rbp-50h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int128 v47; // [rsp+D0h] [rbp-30h]
  __int128 v48; // [rsp+E0h] [rbp-20h]
  __int128 v49; // [rsp+F0h] [rbp-10h]
  __int128 v50; // [rsp+100h] [rbp+0h]
  __int128 v51; // [rsp+110h] [rbp+10h]
  __int128 v52; // [rsp+120h] [rbp+20h]
  __int128 v53; // [rsp+130h] [rbp+30h]
  __int128 v54; // [rsp+140h] [rbp+40h]
  __int128 v55; // [rsp+150h] [rbp+50h]
  __int128 v56; // [rsp+160h] [rbp+60h]
  __int64 v57; // [rsp+170h] [rbp+70h]
  __m256i v58; // [rsp+180h] [rbp+80h] BYREF
  __int128 v59; // [rsp+1A0h] [rbp+A0h]
  __int128 v60; // [rsp+1B0h] [rbp+B0h]
  __int128 v61; // [rsp+1C0h] [rbp+C0h]
  __int128 v62; // [rsp+1D0h] [rbp+D0h]
  __int128 v63; // [rsp+1E0h] [rbp+E0h]
  __int128 v64; // [rsp+1F0h] [rbp+F0h]
  __int128 v65; // [rsp+200h] [rbp+100h]
  __int128 v66; // [rsp+210h] [rbp+110h]
  __int128 v67; // [rsp+220h] [rbp+120h]
  __int128 v68; // [rsp+230h] [rbp+130h]
  __int128 v69; // [rsp+240h] [rbp+140h]
  __int128 v70; // [rsp+250h] [rbp+150h]
  __int128 v71; // [rsp+260h] [rbp+160h]
  __int64 v72; // [rsp+270h] [rbp+170h]
  __int128 v73; // [rsp+280h] [rbp+180h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v75[80]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  SystemTimeAsFileTime = 0;
  v43.m256i_i32[1] = 0;
  SystemTime = 0;
  v73 = 0;
  memset_0(&v43.m256i_u64[1], 0, 0xF0u);
  v8 = (unsigned int)WpnConvertRecurrenceToMinute(a3);
  if ( *(_DWORD *)a2 )
  {
    SystemTimeAsFileTime = *(struct _FILETIME *)(a2 + 4);
  }
  else
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v9 = v8 + *(_QWORD *)&SystemTimeAsFileTime;
    SystemTimeAsFileTime.dwLowDateTime += v8;
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v9);
  }
  if ( !FileTimeToSystemTime(&SystemTimeAsFileTime, &SystemTime) )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    if ( (v11 & 0x80000000) == 0 )
      v11 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x650,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
      (const char *)v11,
      v36);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    {
      v13 = 68;
LABEL_16:
      WPP_SF_d(v12[2], v13, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, v11);
      return v11;
    }
    return v11;
  }
  v14 = *((_DWORD *)a4 + 19) != 0;
  v43.m256i_i32[0] = 2;
  *(struct _SYSTEMTIME *)&v43.m256i_u64[1] = SystemTime;
  v43.m256i_i64[3] = (unsigned int)v8 | 0xA8C000000000LL;
  v15 = ((unsigned __int64)a4 + 340) & -(__int64)v14;
  v58 = v43;
  LODWORD(v44) = 4;
  v59 = v44;
  v72 = v57;
  v61 = v46;
  v60 = v45;
  v63 = v48;
  v62 = v47;
  v65 = v50;
  v64 = v49;
  v67 = v52;
  v66 = v51;
  v69 = v54;
  v68 = v53;
  v71 = v56;
  v70 = v55;
  v16 = TbCreateEvent(v15, &v58, a4);
  v11 = v16;
  if ( v16 >= 0 )
  {
    v18 = 0;
    InternetAvailableEvent = SebEvents::GetInternetAvailableEvent(v17, (struct _GUID *)((char *)a4 + 52));
    v11 = InternetAvailableEvent;
    if ( InternetAvailableEvent < 0 )
    {
      v21 = 0;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x670,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)InternetAvailableEvent,
        v36);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_34;
      v23 = 70;
LABEL_33:
      WPP_SF_d(v22[2], v23, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, v11);
LABEL_34:
      v38 = *a4;
      TbDeleteEvent(v15, &v38);
      if ( v21 )
      {
        v38 = *(__int128 *)((char *)a4 + 52);
        SebDeleteEvent(&v38, 0);
      }
      if ( v18 )
      {
        v38 = a4[2];
        SebDeleteEvent(&v38, 0);
      }
      return v11;
    }
    v39 = (__int64)a4 + 52;
    v21 = 1;
    *((_DWORD *)a4 + 12) = 1;
    v40 = 1;
    DisplayOnEvent = SebEvents::GetDisplayOnEvent(v20, (struct _GUID *)a4 + 2);
    v11 = DisplayOnEvent;
    if ( DisplayOnEvent < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x679,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)DisplayOnEvent,
        v36);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_34;
      v23 = 71;
      goto LABEL_33;
    }
    v41 = a4 + 2;
    v42 = 1;
    v25 = BiPtAssociateActivationProxy(a4 + 1, (char *)a4 + 68, a4, &v39);
    if ( v25 < 0 )
    {
      v27 = RtlNtStatusToDosError(v25);
      v11 = v27;
      if ( v27 > 0 )
        v11 = (unsigned __int16)v27 | 0x80070000;
    }
    else
    {
      v11 = 0;
    }
    if ( (v11 & 0x80000000) != 0 )
    {
      v18 = 1;
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x68B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)v11,
        2);
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_34;
      v23 = 72;
      goto LABEL_33;
    }
    UserSid = WpnGetUserSid(v75, v26);
    v11 = UserSid;
    if ( UserSid >= 0 )
    {
      v33 = BiPtCreateEventForPackageName(&v73, qword_1801252B0, 0, 0);
      if ( v33 < 0 )
      {
        v34 = RtlNtStatusToDosError(v33);
        v11 = v34;
        if ( v34 > 0 )
          v11 = (unsigned __int16)v34 | 0x80070000;
      }
      else
      {
        v11 = 0;
      }
      if ( (v11 & 0x80000000) == 0 )
      {
        *a5 = v73;
        return v11;
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x69C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)v11,
        (int)a4);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_51;
      v32 = 74;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x690,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
        (const char *)(unsigned int)UserSid,
        2);
      v31 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *((char *)WPP_GLOBAL_Control + 28) >= 0 )
        goto LABEL_51;
      v32 = 73;
    }
    WPP_SF_d(v31[2], v32, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids, v11);
LABEL_51:
    LOBYTE(v30) = 1;
    LOBYTE(v29) = 1;
    BiPtDisassociateWorkItemEx(a4 + 1, v29, v30);
    return v11;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0x668,
    (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\periodicupdatemanager.cpp",
    (const char *)(unsigned int)v16,
    v36);
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v13 = 69;
    goto LABEL_16;
  }
  return v11;
}

```

## disassembly

```asm
0x1800d8d0c  mov     [rsp-8+arg_0], rbx
0x1800d8d11  push    rbp
0x1800d8d12  push    rsi
0x1800d8d13  push    rdi
0x1800d8d14  push    r12
0x1800d8d16  push    r13
0x1800d8d18  push    r14
0x1800d8d1a  push    r15
0x1800d8d1c  lea     rbp, [rsp-200h]
0x1800d8d24  sub     rsp, 300h
0x1800d8d2b  mov     rax, cs:__security_cookie
0x1800d8d32  xor     rax, rsp
0x1800d8d35  mov     [rbp+230h+var_40], rax
0x1800d8d3c  mov     r13, [rbp+230h+arg_20]
0x1800d8d43  lea     rcx, [rbp+230h+var_2B0+8]; void *
0x1800d8d47  mov     ebx, r8d
0x1800d8d4a  mov     qword ptr [rsp+330h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800d8d53  mov     rsi, rdx
0x1800d8d56  xorps   xmm0, xmm0
0x1800d8d59  xorps   xmm1, xmm1
0x1800d8d5c  xor     eax, eax
0x1800d8d5e  xor     edx, edx; Val
0x1800d8d60  mov     dword ptr [rbp+230h+var_2B0+4], eax
0x1800d8d63  mov     r8d, 0F0h; Size
0x1800d8d69  mov     rdi, r9
0x1800d8d6c  movups  xmmword ptr [rbp+230h+SystemTime.wYear], xmm0
0x1800d8d73  movups  [rbp+230h+var_B0], xmm1
0x1800d8d7a  call    memset_0
0x1800d8d7f  mov     ecx, ebx
0x1800d8d81  call    ?WpnConvertRecurrenceToMinute@@YAIW4__MIDL___MIDL_itf_wpnplatform_0000_0007_0003@@@Z; WpnConvertRecurrenceToMinute(__MIDL___MIDL_itf_wpnplatform_0000_0007_0003)
0x1800d8d86  cmp     dword ptr [rsi], 0
0x1800d8d89  mov     ebx, eax
0x1800d8d8b  jz      short loc_1800D8D9D
0x1800d8d8d  mov     ecx, [rsi+4]
0x1800d8d90  mov     [rsp+330h+SystemTimeAsFileTime.dwLowDateTime], ecx
0x1800d8d94  mov     ecx, [rsi+8]
0x1800d8d97  mov     [rsp+330h+SystemTimeAsFileTime.dwHighDateTime], ecx
0x1800d8d9b  jmp     short loc_1800D8DBC
0x1800d8d9d  lea     rcx, [rsp+330h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800d8da2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d8da8  mov     rax, qword ptr [rsp+330h+SystemTimeAsFileTime.dwLowDateTime]
0x1800d8dad  add     rax, rbx
0x1800d8db0  mov     [rsp+330h+SystemTimeAsFileTime.dwLowDateTime], eax
0x1800d8db4  shr     rax, 20h
0x1800d8db8  mov     [rsp+330h+SystemTimeAsFileTime.dwHighDateTime], eax
0x1800d8dbc  lea     rdx, [rbp+230h+SystemTime]; lpSystemTime
0x1800d8dc3  lea     rcx, [rsp+330h+SystemTimeAsFileTime]; lpFileTime
0x1800d8dc8  call    cs:__imp_FileTimeToSystemTime
0x1800d8dce  test    eax, eax
0x1800d8dd0  jnz     short loc_1800D8E37
0x1800d8dd2  call    cs:__imp_GetLastError
0x1800d8dd8  mov     ebx, eax
0x1800d8dda  test    eax, eax
0x1800d8ddc  jle     short loc_1800D8DE7
0x1800d8dde  movzx   ebx, ax
0x1800d8de1  or      ebx, 80070000h
0x1800d8de7  mov     rcx, [rbp+238h]; this
0x1800d8dee  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d8df5  test    ebx, ebx
0x1800d8df7  mov     eax, 80004005h
0x1800d8dfc  mov     edx, 650h; void *
0x1800d8e01  cmovns  ebx, eax
0x1800d8e04  mov     r9d, ebx; char *
0x1800d8e07  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d8e0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8e13  lea     rax, WPP_GLOBAL_Control
0x1800d8e1a  cmp     rcx, rax
0x1800d8e1d  jz      loc_1800D925E
0x1800d8e23  test    byte ptr [rcx+1Ch], 80h
0x1800d8e27  jz      loc_1800D925E
0x1800d8e2d  mov     edx, 44h ; 'D'
0x1800d8e32  jmp     loc_1800D8F77
0x1800d8e37  movups  xmm0, xmmword ptr [rbp+230h+SystemTime.wYear]
0x1800d8e3e  mov     eax, [rdi+4Ch]
0x1800d8e41  lea     rcx, [rdi+154h]
0x1800d8e48  neg     eax
0x1800d8e4a  mov     dword ptr [rbp+230h+var_2B0], 2
0x1800d8e51  mov     rax, [rbp+230h+var_1C0]
0x1800d8e55  lea     rdx, [rbp+230h+var_1B0]
0x1800d8e5c  movdqu  [rbp+230h+var_2B0+8], xmm0
0x1800d8e61  sbb     r14, r14
0x1800d8e64  mov     [rbp+230h+var_298], ebx
0x1800d8e67  movaps  xmm0, [rbp+230h+var_2B0]
0x1800d8e6b  and     r14, rcx
0x1800d8e6e  movups  [rbp+230h+var_1B0], xmm0
0x1800d8e75  mov     dword ptr [rbp+230h+var_290], 4
0x1800d8e7c  mov     r8, rdi
0x1800d8e7f  movaps  xmm0, [rbp+230h+var_290]
0x1800d8e83  mov     rcx, r14
0x1800d8e86  movups  [rbp+230h+var_190], xmm0
0x1800d8e8d  mov     [rbp+230h+var_294], 0A8C0h
0x1800d8e94  movaps  xmm1, xmmword ptr [rbp-70h]
0x1800d8e98  movaps  xmm0, [rbp+230h+var_270]
0x1800d8e9c  movups  [rbp+230h+var_1A0], xmm1
0x1800d8ea3  mov     [rbp+230h+var_C0], rax
0x1800d8eaa  movaps  xmm1, [rbp+230h+var_280]
0x1800d8eae  movups  [rbp+230h+var_170], xmm0
0x1800d8eb5  movaps  xmm0, [rbp+230h+var_250]
0x1800d8eb9  movups  [rbp+230h+var_180], xmm1
0x1800d8ec0  movaps  xmm1, [rbp+230h+var_260]
0x1800d8ec4  movups  [rbp+230h+var_150], xmm0
0x1800d8ecb  movaps  xmm0, [rbp+230h+var_230]
0x1800d8ecf  movups  [rbp+230h+var_160], xmm1
0x1800d8ed6  movaps  xmm1, [rbp+230h+var_240]
0x1800d8eda  movups  [rbp+230h+var_130], xmm0
0x1800d8ee1  movaps  xmm0, [rbp+230h+var_210]
0x1800d8ee5  movups  [rbp+230h+var_140], xmm1
0x1800d8eec  movaps  xmm1, [rbp+230h+var_220]
0x1800d8ef0  movups  [rbp+230h+var_110], xmm0
0x1800d8ef7  movaps  xmm0, [rbp+230h+var_1F0]
0x1800d8efb  movups  [rbp+230h+var_120], xmm1
0x1800d8f02  movaps  xmm1, [rbp+230h+var_200]
0x1800d8f06  movups  [rbp+230h+var_F0], xmm0
0x1800d8f0d  movaps  xmm0, [rbp+230h+var_1D0]
0x1800d8f11  movups  [rbp+230h+var_100], xmm1
0x1800d8f18  movaps  xmm1, [rbp+230h+var_1E0]
0x1800d8f1c  movups  [rbp+230h+var_D0], xmm0
0x1800d8f23  movups  [rbp+230h+var_E0], xmm1
0x1800d8f2a  call    cs:__imp_TbCreateEvent
0x1800d8f30  mov     ebx, eax
0x1800d8f32  test    eax, eax
0x1800d8f34  jns     short loc_1800D8F8F
0x1800d8f36  mov     rcx, [rbp+238h]; this
0x1800d8f3d  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d8f44  mov     r9d, eax; char *
0x1800d8f47  mov     edx, 668h; void *
0x1800d8f4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d8f51  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8f58  lea     rax, WPP_GLOBAL_Control
0x1800d8f5f  cmp     rcx, rax
0x1800d8f62  jz      loc_1800D925E
0x1800d8f68  test    byte ptr [rcx+1Ch], 80h
0x1800d8f6c  jz      loc_1800D925E
0x1800d8f72  mov     edx, 45h ; 'E'
0x1800d8f77  mov     rcx, [rcx+10h]
0x1800d8f7b  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x1800d8f82  mov     r9d, ebx
0x1800d8f85  call    WPP_SF_d
0x1800d8f8a  jmp     loc_1800D925E
0x1800d8f8f  lea     r15, [rdi+34h]
0x1800d8f93  xor     r12d, r12d
0x1800d8f96  mov     rdx, r15; struct _GUID *
0x1800d8f99  call    ?GetInternetAvailableEvent@SebEvents@@QEAAJPEAU_GUID@@@Z; SebEvents::GetInternetAvailableEvent(_GUID *)
0x1800d8f9e  mov     ebx, eax
0x1800d8fa0  test    eax, eax
0x1800d8fa2  jns     short loc_1800D8FEA
0x1800d8fa4  mov     rcx, [rbp+238h]; this
0x1800d8fab  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d8fb2  xor     esi, esi
0x1800d8fb4  mov     r9d, eax; char *
0x1800d8fb7  mov     edx, 670h; void *
0x1800d8fbc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d8fc1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d8fc8  lea     rax, WPP_GLOBAL_Control
0x1800d8fcf  cmp     rcx, rax
0x1800d8fd2  jz      loc_1800D90FD
0x1800d8fd8  test    byte ptr [rcx+1Ch], 80h
0x1800d8fdc  jz      loc_1800D90FD
0x1800d8fe2  lea     edx, [rsi+46h]
0x1800d8fe5  jmp     loc_1800D90EA
0x1800d8fea  mov     [rsp+330h+var_2D0], r15
0x1800d8fef  mov     esi, 1
0x1800d8ff4  lea     r15, [rdi+20h]
0x1800d8ff8  mov     [rdi+30h], esi
0x1800d8ffb  mov     rdx, r15; struct _GUID *
0x1800d8ffe  mov     [rsp+330h+var_2C8], sil
0x1800d9003  call    ?GetDisplayOnEvent@SebEvents@@QEAAJPEAU_GUID@@@Z; SebEvents::GetDisplayOnEvent(_GUID *)
0x1800d9008  mov     ebx, eax
0x1800d900a  test    eax, eax
0x1800d900c  jns     short loc_1800D9052
0x1800d900e  mov     rcx, [rbp+238h]; this
0x1800d9015  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d901c  mov     r9d, eax; char *
0x1800d901f  mov     edx, 679h; void *
0x1800d9024  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d9029  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9030  lea     rax, WPP_GLOBAL_Control
0x1800d9037  cmp     rcx, rax
0x1800d903a  jz      loc_1800D90FD
0x1800d9040  test    byte ptr [rcx+1Ch], 80h
0x1800d9044  jz      loc_1800D90FD
0x1800d904a  lea     edx, [rsi+46h]
0x1800d904d  jmp     loc_1800D90EA
0x1800d9052  mov     [rsp+330h+var_300], r12
0x1800d9057  lea     rdx, [rdi+44h]
0x1800d905b  mov     [rsp+330h+var_308], r12d
0x1800d9060  lea     rcx, [rdi+10h]
0x1800d9064  lea     r9, [rsp+330h+var_2D0]
0x1800d9069  mov     [rsp+330h+var_310], 2; int
0x1800d9071  mov     r8, rdi
0x1800d9074  mov     [rsp+330h+var_2C0], r15
0x1800d9079  mov     [rsp+330h+var_2B8], sil
0x1800d907e  call    cs:__imp_BiPtAssociateActivationProxy
0x1800d9084  mov     r15d, 80070000h
0x1800d908a  test    eax, eax
0x1800d908c  js      short loc_1800D9092
0x1800d908e  xor     ebx, ebx
0x1800d9090  jmp     short loc_1800D90A6
0x1800d9092  mov     ecx, eax; Status
0x1800d9094  call    cs:__imp_RtlNtStatusToDosError
0x1800d909a  mov     ebx, eax
0x1800d909c  test    eax, eax
0x1800d909e  jle     short loc_1800D90A6
0x1800d90a0  movzx   ebx, ax
0x1800d90a3  or      ebx, r15d
0x1800d90a6  test    ebx, ebx
0x1800d90a8  jns     loc_1800D9154
0x1800d90ae  mov     rcx, [rbp+238h]; this
0x1800d90b5  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d90bc  mov     r9d, ebx; char *
0x1800d90bf  mov     edx, 68Bh; void *
0x1800d90c4  mov     r12d, esi
0x1800d90c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d90cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d90d3  lea     rax, WPP_GLOBAL_Control
0x1800d90da  cmp     rcx, rax
0x1800d90dd  jz      short loc_1800D90FD
0x1800d90df  test    byte ptr [rcx+1Ch], 80h
0x1800d90e3  jz      short loc_1800D90FD
0x1800d90e5  mov     edx, 48h ; 'H'
0x1800d90ea  mov     rcx, [rcx+10h]
0x1800d90ee  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x1800d90f5  mov     r9d, ebx
0x1800d90f8  call    WPP_SF_d
0x1800d90fd  movaps  xmm0, xmmword ptr [rdi]
0x1800d9100  lea     rdx, [rsp+330h+var_2E0]
0x1800d9105  mov     rcx, r14
0x1800d9108  movdqa  [rsp+330h+var_2E0], xmm0
0x1800d910e  call    cs:__imp_TbDeleteEvent
0x1800d9114  test    esi, esi
0x1800d9116  jz      short loc_1800D912F
0x1800d9118  movups  xmm0, xmmword ptr [rdi+34h]
0x1800d911c  xor     edx, edx
0x1800d911e  lea     rcx, [rsp+330h+var_2E0]
0x1800d9123  movdqu  [rsp+330h+var_2E0], xmm0
0x1800d9129  call    cs:__imp_SebDeleteEvent
0x1800d912f  test    r12d, r12d
0x1800d9132  jz      loc_1800D925E
0x1800d9138  movups  xmm0, xmmword ptr [rdi+20h]
0x1800d913c  xor     edx, edx
0x1800d913e  lea     rcx, [rsp+330h+var_2E0]
0x1800d9143  movdqu  [rsp+330h+var_2E0], xmm0
0x1800d9149  call    cs:__imp_SebDeleteEvent
0x1800d914f  jmp     loc_1800D925E
0x1800d9154  lea     rcx, [rbp+230h+var_90]; void *
0x1800d915b  call    ?WpnGetUserSid@@YAJPEAXK@Z; WpnGetUserSid(void *,ulong)
0x1800d9160  mov     ebx, eax
0x1800d9162  test    eax, eax
0x1800d9164  jns     short loc_1800D91AC
0x1800d9166  mov     rcx, [rbp+238h]; this
0x1800d916d  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d9174  mov     r9d, eax; char *
0x1800d9177  mov     edx, 690h; void *
0x1800d917c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d9181  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9188  lea     rax, WPP_GLOBAL_Control
0x1800d918f  cmp     rcx, rax
0x1800d9192  jz      loc_1800D923F
0x1800d9198  test    byte ptr [rcx+1Ch], 80h
0x1800d919c  jz      loc_1800D923F
0x1800d91a2  mov     edx, 49h ; 'I'
0x1800d91a7  jmp     loc_1800D922C
0x1800d91ac  mov     [rsp+330h+var_308], 12A4h
0x1800d91b4  lea     rdx, qword_1801252B0
0x1800d91bb  xor     r9d, r9d
0x1800d91be  mov     qword ptr [rsp+330h+var_310], rdi; int
0x1800d91c3  xor     r8d, r8d
0x1800d91c6  lea     rcx, [rbp+230h+var_B0]
0x1800d91cd  call    cs:__imp_BiPtCreateEventForPackageName
0x1800d91d3  test    eax, eax
0x1800d91d5  js      short loc_1800D91DB
0x1800d91d7  xor     ebx, ebx
0x1800d91d9  jmp     short loc_1800D91EF
0x1800d91db  mov     ecx, eax; Status
0x1800d91dd  call    cs:__imp_RtlNtStatusToDosError
0x1800d91e3  mov     ebx, eax
0x1800d91e5  test    eax, eax
0x1800d91e7  jle     short loc_1800D91EF
0x1800d91e9  movzx   ebx, ax
0x1800d91ec  or      ebx, r15d
0x1800d91ef  test    ebx, ebx
0x1800d91f1  jns     short loc_1800D9251
0x1800d91f3  mov     rcx, [rbp+238h]; this
0x1800d91fa  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800d9201  mov     r9d, ebx; char *
0x1800d9204  mov     edx, 69Ch; void *
0x1800d9209  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800d920e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d9215  lea     rax, WPP_GLOBAL_Control
0x1800d921c  cmp     rcx, rax
0x1800d921f  jz      short loc_1800D923F
0x1800d9221  test    byte ptr [rcx+1Ch], 80h
0x1800d9225  jz      short loc_1800D923F
0x1800d9227  mov     edx, 4Ah ; 'J'
0x1800d922c  mov     rcx, [rcx+10h]
0x1800d9230  lea     r8, WPP_6b3164ff505c38b9d951495712a9c50a_Traceguids
0x1800d9237  mov     r9d, ebx
0x1800d923a  call    WPP_SF_d
0x1800d923f  lea     rcx, [rdi+10h]
0x1800d9243  mov     r8b, sil
  ... truncated ...
```
