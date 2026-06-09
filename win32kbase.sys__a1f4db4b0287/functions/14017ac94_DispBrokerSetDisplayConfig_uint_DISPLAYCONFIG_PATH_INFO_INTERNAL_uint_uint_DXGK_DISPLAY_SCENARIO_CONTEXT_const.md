# DispBrokerSetDisplayConfig(uint,DISPLAYCONFIG_PATH_INFO_INTERNAL *,uint,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT * const,bool)

- ea: `0x14017ac94`
- end: `0x14017ae86`
- name: `?DispBrokerSetDisplayConfig@@YAJIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@IIQEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@_N@Z`
- size: `498`
- prototype: `__int64 __fastcall(unsigned int, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, unsigned int, unsigned int, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *const, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1401952f0`

## callees

- `0x1400411c0`
- `0x140043810`
- `0x1400ca248`
- `0x14017ac94`
- `0x14017ae8c`
- `0x1401b9e98`
- `0x1401f4410`
- `0x140238b10`
- `0x140238bf0`
- `0x140238c40`

## import_xrefs

- `watchdog!DisplayScenarioJournalFinalize` at `0x14017ae5f`
- `watchdog!DisplayScenarioJournalFinalize` at `0x14017ae5f`
- `watchdog!DisplayScenarioJournalMissingActualPathModality` at `0x14017ae45`
- `watchdog!DisplayScenarioJournalMissingActualPathModality` at `0x14017ae45`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x14017ae36`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x14017ae36`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x14017ad3f`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x14017ad3f`
- `watchdog!DisplayScenarioJournalBegin` at `0x14017ad24`
- `watchdog!DisplayScenarioJournalBegin` at `0x14017ad24`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14017adca`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x14017adca`
- `WIN32K!W32GetUserSessionState` at `0x14017ad08`
- `WIN32K!W32GetUserSessionState` at `0x14017ada4`
- `WIN32K!W32GetUserSessionState` at `0x14017ad08`
- `WIN32K!W32GetUserSessionState` at `0x14017ada4`

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
0x14017ac94  push    rbp
0x14017ac96  push    rbx
0x14017ac97  push    rsi
0x14017ac98  push    rdi
0x14017ac99  lea     rbp, [rsp-18h]
0x14017ac9e  sub     rsp, 118h
0x14017aca5  mov     rax, cs:__security_cookie
0x14017acac  xor     rax, rsp
0x14017acaf  mov     [rbp+30h+var_30], rax
0x14017acb3  mov     rsi, [rbp+30h+arg_20]
0x14017acb7  mov     eax, ecx
0x14017acb9  imul    rbx, rax, 0D8h
0x14017acc0  mov     [rsp+130h+var_F0], ecx
0x14017acc4  add     rbx, 60h ; '`'
0x14017acc8  mov     [rsp+130h+var_D8], rdx
0x14017accd  mov     [rsp+130h+var_E8], r8d
0x14017acd2  mov     [rsp+130h+var_E0], r9d
0x14017acd7  cmp     ebx, 7FFFh
0x14017acdd  jb      short loc_14017ACE9
0x14017acdf  mov     eax, 80000005h
0x14017ace4  jmp     loc_14017AE6D
0x14017ace9  mov     edx, ebx; unsigned __int64
0x14017aceb  mov     r8d, 44535042h; unsigned int
0x14017acf1  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x14017acf6  mov     rdi, rax
0x14017acf9  test    rax, rax
0x14017acfc  jnz     short loc_14017AD08
0x14017acfe  mov     eax, 0C0000017h
0x14017ad03  jmp     loc_14017AE6D
0x14017ad08  call    cs:__imp_W32GetUserSessionState
0x14017ad0f  nop     dword ptr [rax+rax+00h]
0x14017ad14  mov     edx, [rsp+130h+var_E0]
0x14017ad18  mov     ecx, [rsp+130h+var_E8]
0x14017ad1c  movzx   r8d, word ptr [rax+10C80h]
0x14017ad24  call    cs:__imp_DisplayScenarioJournalBegin
0x14017ad2b  nop     dword ptr [rax+rax+00h]
0x14017ad30  mov     edx, [rsp+130h+var_F0]
0x14017ad34  mov     r8, [rsp+130h+var_D8]
0x14017ad39  imul    ecx, edx, 0D8h
0x14017ad3f  call    cs:__imp_DisplayScenarioJournalSetSDCPathsAndModes
0x14017ad46  nop     dword ptr [rax+rax+00h]
0x14017ad4b  lea     rax, [rsp+130h+var_F0]
0x14017ad50  mov     rdx, rsi
0x14017ad53  mov     [rsp+130h+var_B8], rax
0x14017ad58  lea     r9d, [rbx-60h]
0x14017ad5c  lea     rax, [rsp+130h+var_E8]
0x14017ad61  mov     rcx, rdi
0x14017ad64  mov     [rbp+30h+var_B0], rax
0x14017ad68  lea     r8, [rsp+130h+var_B8]
0x14017ad6d  lea     rax, [rsp+130h+var_E0]
0x14017ad72  mov     [rbp+30h+var_A8], rax
0x14017ad76  lea     rax, [rbp+30h+arg_28]
0x14017ad7a  mov     [rbp+30h+var_A0], rax
0x14017ad7e  lea     rax, [rsp+130h+var_D8]
0x14017ad83  mov     [rbp+30h+var_98], rax
0x14017ad87  call    InitDisplayBrokerMessage_DispBroker__AlpcRequest_7___lambda_cc443f55816a528e59093b1569cde5ac___DrvSampleDisplayState_
0x14017ad8c  mov     ebx, 58h ; 'X'
0x14017ad91  lea     rcx, [rbp+30h+var_90]; void *
0x14017ad95  mov     r8d, ebx; Size
0x14017ad98  xor     edx, edx; Val
0x14017ad9a  call    memset
0x14017ad9f  mov     [rsp+130h+var_C8], rbx
0x14017ada4  call    cs:__imp_W32GetUserSessionState
0x14017adab  nop     dword ptr [rax+rax+00h]
0x14017adb0  lea     rcx, [rsp+130h+var_C0]; this
0x14017adb5  mov     rbx, [rax+0DDD0h]
0x14017adbc  call    ??0LeaveEnterUserCritIfAcquired@@QEAA@XZ; LeaveEnterUserCritIfAcquired::LeaveEnterUserCritIfAcquired(void)
0x14017adc1  mov     rbx, [rbx+10h]
0x14017adc5  mov     [rsp+130h+var_D0], rbx
0x14017adca  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x14017add1  nop     dword ptr [rax+rax+00h]
0x14017add6  lea     rdx, [rsp+130h+var_D0]
0x14017addb  neg     rbx
0x14017adde  lea     r9, [rbp+30h+var_90]
0x14017ade2  sbb     rcx, rcx
0x14017ade5  xor     r8d, r8d
0x14017ade8  mov     rax, [rax+2F8h]
0x14017adef  and     rcx, rdx
0x14017adf2  mov     [rsp+130h+var_100], rcx
0x14017adf7  mov     rdx, rdi
0x14017adfa  lea     rcx, [rsp+130h+var_C8]
0x14017adff  mov     [rsp+130h+var_108], 0
0x14017ae08  mov     [rsp+130h+var_110], rcx
0x14017ae0d  mov     ecx, 120000h
0x14017ae12  call    _guard_dispatch_icall
0x14017ae17  lea     rcx, [rsp+130h+var_C0]; this
0x14017ae1c  mov     ebx, eax
0x14017ae1e  call    ??1LeaveEnterUserCritIfAcquired@@QEAA@XZ; LeaveEnterUserCritIfAcquired::~LeaveEnterUserCritIfAcquired(void)
0x14017ae23  mov     rcx, rdi; Buffer
0x14017ae26  call    GreDeleteFastMutex
0x14017ae2b  test    ebx, ebx
0x14017ae2d  js      short loc_14017AE45
0x14017ae2f  mov     ecx, [rbp+30h+var_3C]
0x14017ae32  test    ecx, ecx
0x14017ae34  jz      short loc_14017AE42
0x14017ae36  call    cs:__imp_DisplayScenarioJournalCCDRetrieval
0x14017ae3d  nop     dword ptr [rax+rax+00h]
0x14017ae42  mov     ebx, [rbp+30h+var_40]
0x14017ae45  call    cs:__imp_DisplayScenarioJournalMissingActualPathModality
0x14017ae4c  nop     dword ptr [rax+rax+00h]
0x14017ae51  test    al, al
0x14017ae53  jz      short loc_14017AE5A
0x14017ae55  call    DrvSetActualPathModalityToDisplayJournal
0x14017ae5a  mov     edx, ebx
0x14017ae5c  mov     rcx, rsi
0x14017ae5f  call    cs:__imp_DisplayScenarioJournalFinalize
0x14017ae66  nop     dword ptr [rax+rax+00h]
0x14017ae6b  mov     eax, ebx
0x14017ae6d  mov     rcx, [rbp+30h+var_30]
0x14017ae71  xor     rcx, rsp; StackCookie
0x14017ae74  call    __security_check_cookie
0x14017ae79  add     rsp, 118h
0x14017ae80  pop     rdi
0x14017ae81  pop     rsi
0x14017ae82  pop     rbx
0x14017ae83  pop     rbp
0x14017ae84  retn
```
