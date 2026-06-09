# DispBrokerSetDisplayConfig(uint,DISPLAYCONFIG_PATH_INFO_INTERNAL *,uint,uint,_DXGK_DISPLAY_SCENARIO_CONTEXT * const,bool)

- ea: `0x1400a31b8`
- end: `0x1400a33aa`
- name: `?DispBrokerSetDisplayConfig@@YAJIPEAUDISPLAYCONFIG_PATH_INFO_INTERNAL@@IIQEAU_DXGK_DISPLAY_SCENARIO_CONTEXT@@_N@Z`
- size: `498`
- prototype: `__int64 __fastcall(__int64, struct DISPLAYCONFIG_PATH_INFO_INTERNAL *, unsigned int, unsigned int, struct _DXGK_DISPLAY_SCENARIO_CONTEXT *const, bool)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140197a80`

## callees

- `0x14007b930`
- `0x14007df80`
- `0x1400a2178`
- `0x1400a2c2c`
- `0x1400a31b8`
- `0x1401baab8`
- `0x1401f44b0`
- `0x1402388e0`
- `0x1402389c0`
- `0x140238a40`

## import_xrefs

- `watchdog!DisplayScenarioJournalFinalize` at `0x1400a3383`
- `watchdog!DisplayScenarioJournalFinalize` at `0x1400a3383`
- `watchdog!DisplayScenarioJournalMissingActualPathModality` at `0x1400a3369`
- `watchdog!DisplayScenarioJournalMissingActualPathModality` at `0x1400a3369`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x1400a335a`
- `watchdog!DisplayScenarioJournalCCDRetrieval` at `0x1400a335a`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x1400a3263`
- `watchdog!DisplayScenarioJournalSetSDCPathsAndModes` at `0x1400a3263`
- `watchdog!DisplayScenarioJournalBegin` at `0x1400a3248`
- `watchdog!DisplayScenarioJournalBegin` at `0x1400a3248`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400a32ee`
- `WIN32K!DxDdGetDxgkWin32kInterface` at `0x1400a32ee`
- `WIN32K!W32GetUserSessionState` at `0x1400a322c`
- `WIN32K!W32GetUserSessionState` at `0x1400a32c8`
- `WIN32K!W32GetUserSessionState` at `0x1400a322c`
- `WIN32K!W32GetUserSessionState` at `0x1400a32c8`

## pseudocode

```c
__int64 __fastcall DispBrokerSetDisplayConfig(
        __int64 a1,
        struct DISPLAYCONFIG_PATH_INFO_INTERNAL *a2,
        unsigned int a3,
        unsigned int a4,
        struct _DXGK_DISPLAY_SCENARIO_CONTEXT *const a5,
        bool a6)
{
  unsigned int v6; // ebx
  __int64 v8; // rdx
  __int64 v9; // rcx
  _WORD *v10; // rdi
  __int64 UserSessionState; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rbx
  __int64 v16; // rcx
  __int64 DxgkWin32kInterface; // rax
  int v18; // ebx
  __int64 v19; // rdx
  unsigned int v20; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v21; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v22; // [rsp+50h] [rbp-B0h] BYREF
  struct DISPLAYCONFIG_PATH_INFO_INTERNAL *v23; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v26[8]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int *v27[5]; // [rsp+78h] [rbp-88h] BYREF
  _DWORD v28[24]; // [rsp+A0h] [rbp-60h] BYREF

  v20 = a1;
  v6 = 216 * a1 + 96;
  v23 = a2;
  v21 = a3;
  v22 = a4;
  if ( v6 >= 0x7FFF )
    return 2147483653LL;
  v10 = (_WORD *)Win32AllocPoolWithQuotaZInitImpl(a1, v6, 0x44535042u);
  if ( !v10 )
    return 3221225495LL;
  UserSessionState = W32GetUserSessionState(v9, v8);
  DisplayScenarioJournalBegin(v21, v22, *(unsigned __int16 *)(UserSessionState + 68736));
  DisplayScenarioJournalSetSDCPathsAndModes(216 * v20, v20, v23);
  v27[0] = &v20;
  v27[1] = &v21;
  v27[2] = &v22;
  v27[3] = (unsigned int *)&a6;
  v27[4] = (unsigned int *)&v23;
  InitDisplayBrokerMessage_DispBroker::AlpcRequest_7___lambda_cc443f55816a528e59093b1569cde5ac___DrvSampleDisplayState_(
    v10,
    a5,
    v27,
    v6 - 96);
  memset(v28, 0, 0x58u);
  v25 = 88;
  v14 = *(_QWORD *)(W32GetUserSessionState(v13, v12) + 56784);
  LeaveEnterUserCritIfAcquired::LeaveEnterUserCritIfAcquired((LeaveEnterUserCritIfAcquired *)v26);
  v15 = *(_QWORD *)(v14 + 16);
  v24 = v15;
  DxgkWin32kInterface = DxDdGetDxgkWin32kInterface(v16);
  v18 = (*(__int64 (__fastcall **)(__int64, _WORD *, _QWORD, _DWORD *, __int64 *, _QWORD, unsigned __int64))(DxgkWin32kInterface + 760))(
          1179648,
          v10,
          0,
          v28,
          &v25,
          0,
          (unsigned __int64)&v24 & -(__int64)(v15 != 0));
  LeaveEnterUserCritIfAcquired::~LeaveEnterUserCritIfAcquired((LeaveEnterUserCritIfAcquired *)v26);
  GreDeleteFastMutex(v10, v19);
  if ( v18 >= 0 )
  {
    if ( v28[21] )
      DisplayScenarioJournalCCDRetrieval(v28[21]);
    v18 = v28[20];
  }
  if ( (unsigned __int8)DisplayScenarioJournalMissingActualPathModality() )
    DrvSetActualPathModalityToDisplayJournal();
  DisplayScenarioJournalFinalize(a5, (unsigned int)v18);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1400a31b8  push    rbp
0x1400a31ba  push    rbx
0x1400a31bb  push    rsi
0x1400a31bc  push    rdi
0x1400a31bd  lea     rbp, [rsp-18h]
0x1400a31c2  sub     rsp, 118h
0x1400a31c9  mov     rax, cs:__security_cookie
0x1400a31d0  xor     rax, rsp
0x1400a31d3  mov     [rbp+30h+var_30], rax
0x1400a31d7  mov     rsi, [rbp+30h+arg_20]
0x1400a31db  mov     eax, ecx
0x1400a31dd  imul    rbx, rax, 0D8h
0x1400a31e4  mov     [rsp+130h+var_F0], ecx
0x1400a31e8  add     rbx, 60h ; '`'
0x1400a31ec  mov     [rsp+130h+var_D8], rdx
0x1400a31f1  mov     [rsp+130h+var_E8], r8d
0x1400a31f6  mov     [rsp+130h+var_E0], r9d
0x1400a31fb  cmp     ebx, 7FFFh
0x1400a3201  jb      short loc_1400A320D
0x1400a3203  mov     eax, 80000005h
0x1400a3208  jmp     loc_1400A3391
0x1400a320d  mov     edx, ebx; unsigned __int64
0x1400a320f  mov     r8d, 44535042h; unsigned int
0x1400a3215  call    ?Win32AllocPoolWithQuotaZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolWithQuotaZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400a321a  mov     rdi, rax
0x1400a321d  test    rax, rax
0x1400a3220  jnz     short loc_1400A322C
0x1400a3222  mov     eax, 0C0000017h
0x1400a3227  jmp     loc_1400A3391
0x1400a322c  call    cs:__imp_W32GetUserSessionState
0x1400a3233  nop     dword ptr [rax+rax+00h]
0x1400a3238  mov     edx, [rsp+130h+var_E0]
0x1400a323c  mov     ecx, [rsp+130h+var_E8]
0x1400a3240  movzx   r8d, word ptr [rax+10C80h]
0x1400a3248  call    cs:__imp_DisplayScenarioJournalBegin
0x1400a324f  nop     dword ptr [rax+rax+00h]
0x1400a3254  mov     edx, [rsp+130h+var_F0]
0x1400a3258  mov     r8, [rsp+130h+var_D8]
0x1400a325d  imul    ecx, edx, 0D8h
0x1400a3263  call    cs:__imp_DisplayScenarioJournalSetSDCPathsAndModes
0x1400a326a  nop     dword ptr [rax+rax+00h]
0x1400a326f  lea     rax, [rsp+130h+var_F0]
0x1400a3274  mov     rdx, rsi
0x1400a3277  mov     [rsp+130h+var_B8], rax
0x1400a327c  lea     r9d, [rbx-60h]
0x1400a3280  lea     rax, [rsp+130h+var_E8]
0x1400a3285  mov     rcx, rdi
0x1400a3288  mov     [rbp+30h+var_B0], rax
0x1400a328c  lea     r8, [rsp+130h+var_B8]
0x1400a3291  lea     rax, [rsp+130h+var_E0]
0x1400a3296  mov     [rbp+30h+var_A8], rax
0x1400a329a  lea     rax, [rbp+30h+arg_28]
0x1400a329e  mov     [rbp+30h+var_A0], rax
0x1400a32a2  lea     rax, [rsp+130h+var_D8]
0x1400a32a7  mov     [rbp+30h+var_98], rax
0x1400a32ab  call    InitDisplayBrokerMessage_DispBroker__AlpcRequest_7___lambda_cc443f55816a528e59093b1569cde5ac___DrvSampleDisplayState_
0x1400a32b0  mov     ebx, 58h ; 'X'
0x1400a32b5  lea     rcx, [rbp+30h+var_90]; void *
0x1400a32b9  mov     r8d, ebx; Size
0x1400a32bc  xor     edx, edx; Val
0x1400a32be  call    memset
0x1400a32c3  mov     [rsp+130h+var_C8], rbx
0x1400a32c8  call    cs:__imp_W32GetUserSessionState
0x1400a32cf  nop     dword ptr [rax+rax+00h]
0x1400a32d4  lea     rcx, [rsp+130h+var_C0]; this
0x1400a32d9  mov     rbx, [rax+0DDD0h]
0x1400a32e0  call    ??0LeaveEnterUserCritIfAcquired@@QEAA@XZ; LeaveEnterUserCritIfAcquired::LeaveEnterUserCritIfAcquired(void)
0x1400a32e5  mov     rbx, [rbx+10h]
0x1400a32e9  mov     [rsp+130h+var_D0], rbx
0x1400a32ee  call    cs:__imp_DxDdGetDxgkWin32kInterface
0x1400a32f5  nop     dword ptr [rax+rax+00h]
0x1400a32fa  lea     rdx, [rsp+130h+var_D0]
0x1400a32ff  neg     rbx
0x1400a3302  lea     r9, [rbp+30h+var_90]
0x1400a3306  sbb     rcx, rcx
0x1400a3309  xor     r8d, r8d
0x1400a330c  mov     rax, [rax+2F8h]
0x1400a3313  and     rcx, rdx
0x1400a3316  mov     [rsp+130h+var_100], rcx
0x1400a331b  mov     rdx, rdi
0x1400a331e  lea     rcx, [rsp+130h+var_C8]
0x1400a3323  mov     [rsp+130h+var_108], 0
0x1400a332c  mov     [rsp+130h+var_110], rcx
0x1400a3331  mov     ecx, 120000h
0x1400a3336  call    _guard_dispatch_icall
0x1400a333b  lea     rcx, [rsp+130h+var_C0]; this
0x1400a3340  mov     ebx, eax
0x1400a3342  call    ??1LeaveEnterUserCritIfAcquired@@QEAA@XZ; LeaveEnterUserCritIfAcquired::~LeaveEnterUserCritIfAcquired(void)
0x1400a3347  mov     rcx, rdi; Buffer
0x1400a334a  call    GreDeleteFastMutex
0x1400a334f  test    ebx, ebx
0x1400a3351  js      short loc_1400A3369
0x1400a3353  mov     ecx, [rbp+30h+var_3C]
0x1400a3356  test    ecx, ecx
0x1400a3358  jz      short loc_1400A3366
0x1400a335a  call    cs:__imp_DisplayScenarioJournalCCDRetrieval
0x1400a3361  nop     dword ptr [rax+rax+00h]
0x1400a3366  mov     ebx, [rbp+30h+var_40]
0x1400a3369  call    cs:__imp_DisplayScenarioJournalMissingActualPathModality
0x1400a3370  nop     dword ptr [rax+rax+00h]
0x1400a3375  test    al, al
0x1400a3377  jz      short loc_1400A337E
0x1400a3379  call    DrvSetActualPathModalityToDisplayJournal
0x1400a337e  mov     edx, ebx
0x1400a3380  mov     rcx, rsi
0x1400a3383  call    cs:__imp_DisplayScenarioJournalFinalize
0x1400a338a  nop     dword ptr [rax+rax+00h]
0x1400a338f  mov     eax, ebx
0x1400a3391  mov     rcx, [rbp+30h+var_30]
0x1400a3395  xor     rcx, rsp; StackCookie
0x1400a3398  call    __security_check_cookie
0x1400a339d  add     rsp, 118h
0x1400a33a4  pop     rdi
0x1400a33a5  pop     rsi
0x1400a33a6  pop     rbx
0x1400a33a7  pop     rbp
0x1400a33a8  retn
```
