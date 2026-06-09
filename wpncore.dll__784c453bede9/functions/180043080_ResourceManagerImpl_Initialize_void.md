# ResourceManagerImpl::Initialize(void)

- ea: `0x180043080`
- end: `0x180043404`
- name: `?Initialize@ResourceManagerImpl@@UEAAJXZ`
- size: `900`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18002e5d0`
- `0x18002ee38`
- `0x180043080`
- `0x18004340c`
- `0x1800436f8`
- `0x1800a15a0`
- `0x1800a27c8`
- `0x1800a61dc`
- `0x1800af0a4`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800431ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800431d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800431ae`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800431d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004331d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043207`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004331d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800431f9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800431f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800433a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043392`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800433a5`

## pseudocode

```c
__int64 __fastcall ResourceManagerImpl::Initialize(struct NotificationPlatform **pv)
{
  struct NotificationPlatform **v1; // r14
  struct NotificationPlatform *v3; // rcx
  int v4; // ecx
  signed int v5; // ebx
  int v6; // eax
  unsigned int v7; // ecx
  int v8; // r9d
  char *EventW; // r15
  __int64 v10; // rsi
  PTP_WORK v11; // r12
  signed int v12; // eax
  unsigned int v13; // ecx
  int v14; // eax
  unsigned int v15; // ecx
  signed int v16; // eax
  signed int LastError; // eax
  int v19; // [rsp+20h] [rbp-49h]
  _TP_CALLBACK_ENVIRON_V3 pcbe; // [rsp+40h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  struct GroupPolicyHandler *v22; // [rsp+D0h] [rbp+67h] BYREF
  struct PowerManagementHandler *v23; // [rsp+D8h] [rbp+6Fh] BYREF
  struct UserSessionHandler *v24; // [rsp+E0h] [rbp+77h] BYREF

  v1 = pv + 1;
  *(_QWORD *)&pcbe.Version = 3;
  *(_QWORD *)&pcbe.Size = 72;
  v3 = pv[1];
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset(&pcbe.Pool, 0, 52);
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  v5 = GroupPolicyHandler::CreateInstance(v3, &v22);
  if ( v5 < 0 )
  {
    if ( (Microsoft_Windows_PushNotifications_PlatformEnableBits & 0x20) != 0 )
      McTemplateU0zzdqz_EventWriteTransfer(
        v4,
        (unsigned int)WPNCORE_EVENT_DEBUG_INIT,
        (unsigned int)L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
        (unsigned int)L"ResourceManagerImpl::Initialize",
        154,
        v5,
        (__int64)&word_180124798);
    goto LABEL_37;
  }
  v6 = PowerManagementHandler::CreateInstance(*v1, &v23);
  v5 = v6;
  if ( v6 < 0 )
  {
    v8 = 1439;
LABEL_6:
    WpnDebugInitTrace(
      v7,
      L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
      L"ResourceManagerImpl::Initialize",
      v8,
      v6);
LABEL_37:
    if ( v22 )
      (**(void (__fastcall ***)(struct GroupPolicyHandler *, __int64))v22)(v22, 1);
    if ( v23 )
      (**(void (__fastcall ***)(struct PowerManagementHandler *, __int64))v23)(v23, 1);
    if ( v24 )
      (**(void (__fastcall ***)(struct UserSessionHandler *, __int64))v24)(v24, 1);
    return (unsigned int)v5;
  }
  v6 = UserSessionHandler::CreateInstance(*v1, &v24);
  v5 = v6;
  if ( v6 < 0 )
  {
    v8 = 1444;
    goto LABEL_6;
  }
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  if ( (unsigned __int64)(EventW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v10 = -1;
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5AB,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
      (const char *)(unsigned int)v5,
      v19);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        72,
        WPP_249126a5ebe4366b3ec9e973b2dbb55a_Traceguids,
        (unsigned int)v5);
    if ( !EventW || EventW == (char *)-1LL )
      goto LABEL_35;
    goto LABEL_34;
  }
  v10 = (__int64)CreateEventW(0, 1, 0, 0);
  if ( (unsigned __int64)(v10 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v16 = GetLastError();
    v5 = v16;
    if ( v16 > 0 )
      v5 = (unsigned __int16)v16 | 0x80070000;
    if ( v5 >= 0 )
      v5 = -2147467259;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5AE,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
      (const char *)(unsigned int)v5,
      v19);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        73,
        WPP_249126a5ebe4366b3ec9e973b2dbb55a_Traceguids,
        (unsigned int)v5);
    goto LABEL_34;
  }
  pcbe.u.Flags |= 1u;
  v11 = CreateThreadpoolWork(ResourceManagerImpl::BackgroundProcessing, pv, &pcbe);
  if ( !v11 )
  {
    v12 = GetLastError();
    v5 = v12;
    if ( v12 > 0 )
      v5 = (unsigned __int16)v12 | 0x80070000;
    if ( v5 < 0 )
    {
      WpnDebugInitTrace(
        v13,
        L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
        L"ResourceManagerImpl::Initialize",
        1465,
        v5);
LABEL_34:
      CloseHandle(EventW);
LABEL_35:
      if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle((HANDLE)v10);
      goto LABEL_37;
    }
  }
  pv[2] = v22;
  pv[3] = v23;
  pv[4] = v24;
  pv[13] = v11;
  pv[10] = (struct NotificationPlatform *)EventW;
  pv[12] = (struct NotificationPlatform *)v10;
  v14 = Microsoft::WRL::Details::MakeAndInitialize<EnergySaverAllowlistManager,EnergySaverAllowlistManager,NotificationPlatform * &>(
          pv + 21,
          v1);
  v5 = v14;
  if ( v14 < 0 )
    WpnDebugInitTrace(
      v15,
      L"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\conn\\resourcemanagerimpl.cpp",
      L"ResourceManagerImpl::Initialize",
      1487,
      v14);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180043080  push    rbp
0x180043082  push    rbx
0x180043083  push    rsi
0x180043084  push    rdi
0x180043085  push    r12
0x180043087  push    r14
0x180043089  push    r15
0x18004308b  lea     rbp, [rsp-27h]
0x180043090  sub     rsp, 90h
0x180043097  lea     r14, [rcx+8]
0x18004309b  mov     qword ptr [rbp+57h+pcbe.Version], 3
0x1800430a3  mov     rdi, rcx
0x1800430a6  mov     qword ptr [rbp+57h+pcbe.Size], 48h ; 'H'
0x1800430ae  mov     rcx, [r14]; struct NotificationPlatform *
0x1800430b1  lea     rdx, [rbp+57h+arg_0]; struct GroupPolicyHandler **
0x1800430b5  xorps   xmm0, xmm0
0x1800430b8  mov     [rbp+57h+arg_0], 0
0x1800430c0  mov     r12d, 1
0x1800430c6  mov     [rbp+57h+arg_8], 0
0x1800430ce  mov     [rbp+57h+arg_10], 0
0x1800430d6  mov     [rbp+57h+pcbe.Pool], 0
0x1800430de  mov     [rbp+57h+pcbe.CleanupGroup], 0
0x1800430e6  mov     [rbp+57h+pcbe.CleanupGroupCancelCallback], 0
0x1800430ee  movdqa  xmmword ptr [rbp+57h+pcbe.RaceDll], xmm0
0x1800430f3  mov     [rbp+57h+pcbe.FinalizationCallback], 0
0x1800430fb  mov     dword ptr [rbp+57h+pcbe.u], 0
0x180043102  mov     [rbp+57h+pcbe.CallbackPriority], r12d
0x180043106  call    ?CreateInstance@GroupPolicyHandler@@SAJPEAVNotificationPlatform@@PEAPEAV1@@Z; GroupPolicyHandler::CreateInstance(NotificationPlatform *,GroupPolicyHandler * *)
0x18004310b  mov     ebx, eax
0x18004310d  test    eax, eax
0x18004310f  jns     short loc_180043155
0x180043111  test    cs:Microsoft_Windows_PushNotifications_PlatformEnableBits, 20h
0x180043118  jz      loc_1800433AB
0x18004311e  lea     rax, word_180124798
0x180043125  mov     [rsp+0C0h+var_90], rax
0x18004312a  lea     r9, aResourcemanage_1; "ResourceManagerImpl::Initialize"
0x180043131  mov     [rsp+0C0h+var_98], ebx
0x180043135  lea     r8, aOnecoreuapBase_96; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004313c  lea     rdx, WPNCORE_EVENT_DEBUG_INIT
0x180043143  mov     [rsp+0C0h+var_A0], 59Ah
0x18004314b  call    McTemplateU0zzdqz_EventWriteTransfer
0x180043150  jmp     loc_1800433AB
0x180043155  mov     rcx, [r14]; struct NotificationPlatform *
0x180043158  lea     rdx, [rbp+57h+arg_8]; struct PowerManagementHandler **
0x18004315c  call    ?CreateInstance@PowerManagementHandler@@SAJPEAVNotificationPlatform@@PEAPEAV1@@Z; PowerManagementHandler::CreateInstance(NotificationPlatform *,PowerManagementHandler * *)
0x180043161  mov     ebx, eax
0x180043163  test    eax, eax
0x180043165  jns     short loc_180043189
0x180043167  mov     r9d, 59Fh; int
0x18004316d  lea     r8, aResourcemanage_1; "ResourceManagerImpl::Initialize"
0x180043174  mov     [rsp+0C0h+var_A0], eax; int
0x180043178  lea     rdx, aOnecoreuapBase_96; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004317f  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x180043184  jmp     loc_1800433AB
0x180043189  mov     rcx, [r14]; struct NotificationPlatform *
0x18004318c  lea     rdx, [rbp+57h+arg_10]; struct UserSessionHandler **
0x180043190  call    ?CreateInstance@UserSessionHandler@@SAJPEAVNotificationPlatform@@PEAPEAV1@@Z; UserSessionHandler::CreateInstance(NotificationPlatform *,UserSessionHandler * *)
0x180043195  mov     ebx, eax
0x180043197  test    eax, eax
0x180043199  jns     short loc_1800431A3
0x18004319b  mov     r9d, 5A4h
0x1800431a1  jmp     short loc_18004316D
0x1800431a3  xor     r9d, r9d; lpName
0x1800431a6  xor     r8d, r8d; bInitialState
0x1800431a9  mov     edx, r12d; bManualReset
0x1800431ac  xor     ecx, ecx; lpEventAttributes
0x1800431ae  call    cs:__imp_CreateEventW
0x1800431b4  mov     r15, rax
0x1800431b7  lea     rcx, [rax-1]
0x1800431bb  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800431bf  ja      loc_180043319
0x1800431c5  xor     r9d, r9d; lpName
0x1800431c8  xor     r8d, r8d; bInitialState
0x1800431cb  mov     edx, r12d; bManualReset
0x1800431ce  xor     ecx, ecx; lpEventAttributes
0x1800431d0  call    cs:__imp_CreateEventW
0x1800431d6  mov     rsi, rax
0x1800431d9  lea     rcx, [rax-1]
0x1800431dd  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x1800431e1  ja      loc_1800432A7
0x1800431e7  or      dword ptr [rbp+57h+pcbe.u], r12d
0x1800431eb  lea     r8, [rbp+57h+pcbe]; pcbe
0x1800431ef  mov     rdx, rdi; pv
0x1800431f2  lea     rcx, ?BackgroundProcessing@ResourceManagerImpl@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800431f9  call    cs:__imp_CreateThreadpoolWork
0x1800431ff  mov     r12, rax
0x180043202  test    rax, rax
0x180043205  jnz     short loc_180043248
0x180043207  call    cs:__imp_GetLastError
0x18004320d  mov     ebx, eax
0x18004320f  test    eax, eax
0x180043211  jle     short loc_18004321C
0x180043213  movzx   ebx, ax
0x180043216  or      ebx, 80070000h
0x18004321c  test    ebx, ebx
0x18004321e  jns     short loc_180043248
0x180043220  mov     r9d, 5B9h; int
0x180043226  mov     [rsp+0C0h+var_A0], ebx; int
0x18004322a  lea     r8, aResourcemanage_1; "ResourceManagerImpl::Initialize"
0x180043231  lea     rdx, aOnecoreuapBase_96; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180043238  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x18004323d  mov     r12d, 1
0x180043243  jmp     loc_18004338F
0x180043248  mov     rax, [rbp+57h+arg_0]
0x18004324c  lea     rcx, [rdi+0A8h]
0x180043253  mov     [rdi+10h], rax
0x180043257  mov     rdx, r14
0x18004325a  mov     rax, [rbp+57h+arg_8]
0x18004325e  mov     [rdi+18h], rax
0x180043262  mov     rax, [rbp+57h+arg_10]
0x180043266  mov     [rdi+20h], rax
0x18004326a  mov     [rdi+68h], r12
0x18004326e  mov     [rdi+50h], r15
0x180043272  mov     [rdi+60h], rsi
0x180043276  call    ??$MakeAndInitialize@VEnergySaverAllowlistManager@@V1@AEAPEAVNotificationPlatform@@@Details@WRL@Microsoft@@YAJPEAPEAVEnergySaverAllowlistManager@@AEAPEAVNotificationPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<EnergySaverAllowlistManager,EnergySaverAllowlistManager,NotificationPlatform * &>(EnergySaverAllowlistManager * *,NotificationPlatform * &)
0x18004327b  mov     ebx, eax
0x18004327d  test    eax, eax
0x18004327f  jns     loc_1800433F0
0x180043285  mov     r9d, 5CFh; int
0x18004328b  mov     [rsp+0C0h+var_A0], eax; int
0x18004328f  lea     r8, aResourcemanage_1; "ResourceManagerImpl::Initialize"
0x180043296  lea     rdx, aOnecoreuapBase_96; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004329d  call    ?WpnDebugInitTrace@@YAXKPEBG0HJ@Z; WpnDebugInitTrace(ulong,ushort const *,ushort const *,int,long)
0x1800432a2  jmp     loc_1800433F0
0x1800432a7  call    cs:__imp_GetLastError
0x1800432ad  mov     ebx, eax
0x1800432af  test    eax, eax
0x1800432b1  jle     short loc_1800432BC
0x1800432b3  movzx   ebx, ax
0x1800432b6  or      ebx, 80070000h
0x1800432bc  mov     rcx, [rbp+5Fh]; this
0x1800432c0  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800432c7  test    ebx, ebx
0x1800432c9  mov     eax, 80004005h
0x1800432ce  mov     edx, 5AEh; void *
0x1800432d3  cmovns  ebx, eax
0x1800432d6  mov     r9d, ebx; char *
0x1800432d9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800432de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800432e5  lea     rax, WPP_GLOBAL_Control
0x1800432ec  cmp     rcx, rax
0x1800432ef  jz      loc_18004338F
0x1800432f5  test    byte ptr [rcx+1Ch], 80h
0x1800432f9  jz      loc_18004338F
0x1800432ff  mov     rcx, [rcx+10h]
0x180043303  lea     r8, WPP_249126a5ebe4366b3ec9e973b2dbb55a_Traceguids
0x18004330a  mov     edx, 49h ; 'I'
0x18004330f  mov     r9d, ebx
0x180043312  call    WPP_SF_d
0x180043317  jmp     short loc_18004338F
0x180043319  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004331d  call    cs:__imp_GetLastError
0x180043323  mov     ebx, eax
0x180043325  test    eax, eax
0x180043327  jle     short loc_180043332
0x180043329  movzx   ebx, ax
0x18004332c  or      ebx, 80070000h
0x180043332  mov     rcx, [rbp+5Fh]; this
0x180043336  lea     r8, aOnecoreuapBase_126; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18004333d  test    ebx, ebx
0x18004333f  mov     eax, 80004005h
0x180043344  mov     edx, 5ABh; void *
0x180043349  cmovns  ebx, eax
0x18004334c  mov     r9d, ebx; char *
0x18004334f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043354  mov     rcx, cs:WPP_GLOBAL_Control
0x18004335b  lea     rax, WPP_GLOBAL_Control
0x180043362  cmp     rcx, rax
0x180043365  jz      short loc_180043385
0x180043367  test    byte ptr [rcx+1Ch], 80h
0x18004336b  jz      short loc_180043385
0x18004336d  mov     rcx, [rcx+10h]
0x180043371  lea     r8, WPP_249126a5ebe4366b3ec9e973b2dbb55a_Traceguids
0x180043378  mov     edx, 48h ; 'H'
0x18004337d  mov     r9d, ebx
0x180043380  call    WPP_SF_d
0x180043385  test    r15, r15
0x180043388  jz      short loc_180043398
0x18004338a  cmp     r15, rsi
0x18004338d  jz      short loc_180043398
0x18004338f  mov     rcx, r15; hObject
0x180043392  call    cs:__imp_CloseHandle
0x180043398  lea     rax, [rsi-1]
0x18004339c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800433a0  ja      short loc_1800433AB
0x1800433a2  mov     rcx, rsi; hObject
0x1800433a5  call    cs:__imp_CloseHandle
0x1800433ab  mov     rcx, [rbp+57h+arg_0]
0x1800433af  test    rcx, rcx
0x1800433b2  jz      short loc_1800433C2
0x1800433b4  mov     rax, [rcx]
0x1800433b7  mov     edx, r12d
0x1800433ba  mov     rax, [rax]
0x1800433bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433c2  mov     rcx, [rbp+57h+arg_8]
0x1800433c6  test    rcx, rcx
0x1800433c9  jz      short loc_1800433D9
0x1800433cb  mov     rax, [rcx]
0x1800433ce  mov     edx, r12d
0x1800433d1  mov     rax, [rax]
0x1800433d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433d9  mov     rcx, [rbp+57h+arg_10]
0x1800433dd  test    rcx, rcx
0x1800433e0  jz      short loc_1800433F0
0x1800433e2  mov     rax, [rcx]
0x1800433e5  mov     edx, r12d
0x1800433e8  mov     rax, [rax]
0x1800433eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433f0  mov     eax, ebx
0x1800433f2  add     rsp, 90h
0x1800433f9  pop     r15
0x1800433fb  pop     r14
0x1800433fd  pop     r12
0x1800433ff  pop     rdi
0x180043400  pop     rsi
0x180043401  pop     rbx
0x180043402  pop     rbp
0x180043403  retn
```
