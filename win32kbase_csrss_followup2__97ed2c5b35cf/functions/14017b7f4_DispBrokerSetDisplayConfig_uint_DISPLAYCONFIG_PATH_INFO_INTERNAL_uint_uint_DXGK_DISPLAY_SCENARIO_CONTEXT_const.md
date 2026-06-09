# DispBrokerSetDisplayConfig(uint,DISPLAYCONFIG_PATH_INFO_INTERNAL *,uint,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT * const,bool)

- ea: `0x14017b7f4`
- end: `0x14017b9e6`
- name: `?DispBrokerSetDisplayConfig@@YAJIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@IIQEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@_N@Z`
- size: `498`
- prototype: `__int64 __fastcall(unsigned int, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, unsigned int, unsigned int, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *const, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140195420`

## callees

- `0x14004a0d0`
- `0x14004c720`
- `0x1400b0b38`
- `0x14017b7f4`
- `0x14017b9ec`
- `0x1401b9938`
- `0x1401f3c50`
- `0x140238160`
- `0x140238240`
- `0x1402382c0`

## import_xrefs

- `watchdog!DisplayScenarioJournalFinalize` at `0x14017b9bf`
- `watchdog!DisplayScenarioJournalFinalize` at `0x14017b9bf`
- `watchdog!DisplayScenarioJournalMissingActualPathModality` at `0x14017b9a5`
- `watchdog!DisplayScenarioJournalMissingActualPathModality` at `0x14017b9a5`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x14017b996`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x14017b996`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x14017b89f`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x14017b89f`
- `watchdog!DisplayScenarioJournalBegin` at `0x14017b884`
- `watchdog!DisplayScenarioJournalBegin` at `0x14017b884`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14017b92a`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14017b92a`
- `WIN32K!W32GetUserSessionState` at `0x14017b868`
- `WIN32K!W32GetUserSessionState` at `0x14017b904`
- `WIN32K!W32GetUserSessionState` at `0x14017b868`
- `WIN32K!W32GetUserSessionState` at `0x14017b904`

## pseudocode

```c
__int64 __fastcall DispBrokerSetDisplayConfig(
        unsigned __int64 a1,
        struct DISPLAYCONFIG_PATH_INFO_INTERNAL *a2,
        unsigned int a3,
        unsigned int a4,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *const a5,
        bool a6)
{
  unsigned int v6; // ebx
  __int64 v8; // rcx
  void *v9; // rdi
  __int64 UserSessionState; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 DxgkWin32kInterface; // rax
  int v18; // ebx
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v21; // [rsp+50h] [rbp-B0h] BYREF
  struct DISPLAYCONFIG_PATH_INFO_INTERNAL *v22; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v25[8]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[5]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v27[24]; // [rsp+A0h] [rbp-60h] BYREF

  v19 = a1;
  v6 = 216 * a1 + 96;
  v22 = a2;
  v20 = a3;
  v21 = a4;
  if ( v6 >= 0x7FFF )
    return 2147483653LL;
  v9 = Win32AllocPoolWithQuotaZInitImpl(a1, v6, 0x44535042u);
  if ( !v9 )
    return 3221225495LL;
  UserSessionState = W32GetUserSessionState(v8);
  DisplayScenarioJournalBegin(v20, v21, *(unsigned __int16 *)(UserSessionState + 68736));
  DisplayScenarioJournalSetSDCPathsAndModes(216 * v19, v19, v22);
  v26[0] = &v19;
  v26[1] = &v20;
  v26[2] = &v21;
  v26[3] = &a6;
  v26[4] = &v22;
  InitDisplayBrokerMessage_DispBroker::AlpcRequest_7___lambda_cc443f55816a528e59093b1569cde5ac___DrvSampleDisplayState_(
    v9,
    a5,
    v26,
    v6 - 96);
  memset(v27, 0, 0x58u);
  v24 = 88;
  v12 = *(_QWORD *)(W32GetUserSessionState(v11) + 56784);
  LeaveEnterUserCritIfAcquired::LeaveEnterUserCritIfAcquired((LeaveEnterUserCritIfAcquired *)v25);
  v13 = *(_QWORD *)(v12 + 16);
  v23 = v13;
  DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v15, v14, v16);
  v18 = (*(__int64 (__fastcall **)(__int64, void *, _QWORD, _DWORD *, __int64 *, _QWORD, unsigned __int64))(DxgkWin32kInterface + 760))(
          1179648,
          v9,
          0,
          v27,
          &v24,
          0,
          (unsigned __int64)&v23 & -(__int64)(v13 != 0));
  LeaveEnterUserCritIfAcquired::~LeaveEnterUserCritIfAcquired((LeaveEnterUserCritIfAcquired *)v25);
  GreDeleteFastMutex(v9);
  if ( v18 >= 0 )
  {
    if ( v27[21] )
      DisplayScenarioJournalCCDRetrieval(v27[21]);
    v18 = v27[20];
  }
  if ( (unsigned __int8)DisplayScenarioJournalMissingActualPathModality() )
    DrvSetActualPathModalityToDisplayJournal();
  DisplayScenarioJournalFinalize(a5, (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x14017b7f4  push    rbp
0x14017b7f6  push    rbx
0x14017b7f7  push    rsi
0x14017b7f8  push    rdi
0x14017b7f9  lea     rbp, [rsp-18h]
0x14017b7fe  sub     rsp, 118h
0x14017b805  mov     rax, cs:__security_cookie
0x14017b80c  xor     rax, rsp
0x14017b80f  mov     [rbp+30h+var_30], rax
0x14017b813  mov     rsi, [rbp+30h+arg_20]
0x14017b817  mov     eax, ecx
0x14017b819  imul    rbx, rax, 0D8h
0x14017b820  mov     [rsp+130h+var_F0], ecx
0x14017b824  add     rbx, 60h ; '`'
0x14017b828  mov     [rsp+130h+var_D8], rdx
0x14017b82d  mov     [rsp+130h+var_E8], r8d
0x14017b832  mov     [rsp+130h+var_E0], r9d
0x14017b837  cmp     ebx, 7FFFh
0x14017b83d  jb      short loc_14017B849
0x14017b83f  mov     eax, 80000005h
0x14017b844  jmp     loc_14017B9CD
0x14017b849  mov     edx, ebx; unsigned __int64
0x14017b84b  mov     r8d, 44535042h; unsigned int
0x14017b851  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14017b856  mov     rdi, rax
0x14017b859  test    rax, rax
0x14017b85c  jnz     short loc_14017B868
0x14017b85e  mov     eax, 0C0000017h
0x14017b863  jmp     loc_14017B9CD
0x14017b868  call    cs:__imp_W32GetUserSessionState
0x14017b86f  nop     dword ptr [rax+rax+00h]
0x14017b874  mov     edx, [rsp+130h+var_E0]
0x14017b878  mov     ecx, [rsp+130h+var_E8]
0x14017b87c  movzx   r8d, word ptr [rax+10C80h]
0x14017b884  call    cs:__imp_DisplayScenarioJournalBegin
0x14017b88b  nop     dword ptr [rax+rax+00h]
0x14017b890  mov     edx, [rsp+130h+var_F0]
0x14017b894  mov     r8, [rsp+130h+var_D8]
0x14017b899  imul    ecx, edx, 0D8h
0x14017b89f  call    cs:__imp_DisplayScenarioJournalSetSDCPathsAndModes
0x14017b8a6  nop     dword ptr [rax+rax+00h]
0x14017b8ab  lea     rax, [rsp+130h+var_F0]
0x14017b8b0  mov     rdx, rsi
0x14017b8b3  mov     [rsp+130h+var_B8], rax
0x14017b8b8  lea     r9d, [rbx-60h]
0x14017b8bc  lea     rax, [rsp+130h+var_E8]
0x14017b8c1  mov     rcx, rdi
0x14017b8c4  mov     [rbp+30h+var_B0], rax
0x14017b8c8  lea     r8, [rsp+130h+var_B8]
0x14017b8cd  lea     rax, [rsp+130h+var_E0]
0x14017b8d2  mov     [rbp+30h+var_A8], rax
0x14017b8d6  lea     rax, [rbp+30h+arg_28]
0x14017b8da  mov     [rbp+30h+var_A0], rax
0x14017b8de  lea     rax, [rsp+130h+var_D8]
0x14017b8e3  mov     [rbp+30h+var_98], rax
0x14017b8e7  call    InitDisplayBrokerMessage_DispBroker__AlpcRequest_7___lambda_cc443f55816a528e59093b1569cde5ac___DrvSampleDisplayState_
0x14017b8ec  mov     ebx, 58h ; 'X'
0x14017b8f1  lea     rcx, [rbp+30h+var_90]; void *
0x14017b8f5  mov     r8d, ebx; Size
0x14017b8f8  xor     edx, edx; Val
0x14017b8fa  call    memset
0x14017b8ff  mov     [rsp+130h+var_C8], rbx
0x14017b904  call    cs:__imp_W32GetUserSessionState
0x14017b90b  nop     dword ptr [rax+rax+00h]
0x14017b910  lea     rcx, [rsp+130h+var_C0]; this
0x14017b915  mov     rbx, [rax+0DDD0h]
0x14017b91c  call    ??0LeaveEnterUserCritIfAcquired@@QEAA@XZ; LeaveEnterUserCritIfAcquired::LeaveEnterUserCritIfAcquired(void)
0x14017b921  mov     rbx, [rbx+10h]
0x14017b925  mov     [rsp+130h+var_D0], rbx
0x14017b92a  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14017b931  nop     dword ptr [rax+rax+00h]
0x14017b936  lea     rdx, [rsp+130h+var_D0]
0x14017b93b  neg     rbx
0x14017b93e  lea     r9, [rbp+30h+var_90]
0x14017b942  sbb     rcx, rcx
0x14017b945  xor     r8d, r8d
0x14017b948  mov     rax, [rax+2F8h]
0x14017b94f  and     rcx, rdx
0x14017b952  mov     [rsp+130h+var_100], rcx
0x14017b957  mov     rdx, rdi
0x14017b95a  lea     rcx, [rsp+130h+var_C8]
0x14017b95f  mov     [rsp+130h+var_108], 0
0x14017b968  mov     [rsp+130h+var_110], rcx
0x14017b96d  mov     ecx, 120000h
0x14017b972  call    _guard_dispatch_icall
0x14017b977  lea     rcx, [rsp+130h+var_C0]; this
0x14017b97c  mov     ebx, eax
0x14017b97e  call    ??1LeaveEnterUserCritIfAcquired@@QEAA@XZ; LeaveEnterUserCritIfAcquired::~LeaveEnterUserCritIfAcquired(void)
0x14017b983  mov     rcx, rdi; Buffer
0x14017b986  call    GreDeleteFastMutex
0x14017b98b  test    ebx, ebx
0x14017b98d  js      short loc_14017B9A5
0x14017b98f  mov     ecx, [rbp+30h+var_3C]
0x14017b992  test    ecx, ecx
0x14017b994  jz      short loc_14017B9A2
0x14017b996  call    cs:__imp_DisplayScenarioJournalCCDRetrieval
0x14017b99d  nop     dword ptr [rax+rax+00h]
0x14017b9a2  mov     ebx, [rbp+30h+var_40]
0x14017b9a5  call    cs:__imp_DisplayScenarioJournalMissingActualPathModality
0x14017b9ac  nop     dword ptr [rax+rax+00h]
0x14017b9b1  test    al, al
0x14017b9b3  jz      short loc_14017B9BA
0x14017b9b5  call    DrvSetActualPathModalityToDisplayJournal
0x14017b9ba  mov     edx, ebx
0x14017b9bc  mov     rcx, rsi
0x14017b9bf  call    cs:__imp_DisplayScenarioJournalFinalize
0x14017b9c6  nop     dword ptr [rax+rax+00h]
0x14017b9cb  mov     eax, ebx
0x14017b9cd  mov     rcx, [rbp+30h+var_30]
0x14017b9d1  xor     rcx, rsp; StackCookie
0x14017b9d4  call    __security_check_cookie
0x14017b9d9  add     rsp, 118h
0x14017b9e0  pop     rdi
0x14017b9e1  pop     rsi
0x14017b9e2  pop     rbx
0x14017b9e3  pop     rbp
0x14017b9e4  retn
```
