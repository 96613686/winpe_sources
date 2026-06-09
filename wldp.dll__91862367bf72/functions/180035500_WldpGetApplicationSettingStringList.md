# WldpGetApplicationSettingStringList

- ea: `0x180035500`
- end: `0x1800357ed`
- name: `WldpGetApplicationSettingStringList`
- size: `749`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callees

- `0x18001de88`
- `0x18001e628`
- `0x18001f038`
- `0x1800206f4`
- `0x1800313ac`
- `0x1800331ec`
- `0x1800339f8`
- `0x180035180`
- `0x180035500`
- `0x18003932c`
- `0x180039b54`
- `0x180042010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180035673`
- `ntdll!RtlInitUnicodeString` at `0x180035681`
- `ntdll!RtlInitUnicodeString` at `0x180035673`
- `ntdll!RtlInitUnicodeString` at `0x180035681`

## string_xrefs

- `0x180035558`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035590`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800355c8`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035601`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800356bc`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035716`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall WldpGetApplicationSettingStringList(
        PCWSTR SourceString,
        PCWSTR a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5)
{
  const char *v8; // r9
  __int64 result; // rax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 ActiveState; // rax
  int AppSettingDefinition; // eax
  unsigned int AppSettingString; // ebx
  int v15; // [rsp+20h] [rbp-B8h]
  unsigned int v16; // [rsp+20h] [rbp-B8h]
  __int64 v17; // [rsp+30h] [rbp-A8h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-A0h] BYREF
  int v19; // [rsp+3Ch] [rbp-9Ch] BYREF
  void (__fastcall *v20)(__int64, __int64); // [rsp+40h] [rbp-98h] BYREF
  __int64 v21; // [rsp+48h] [rbp-90h]
  __int64 v22; // [rsp+50h] [rbp-88h]
  char v23; // [rsp+58h] [rbp-80h]
  __int64 v24; // [rsp+60h] [rbp-78h] BYREF
  struct _UNICODE_STRING v25; // [rsp+70h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-58h] BYREF
  _QWORD v27[9]; // [rsp+90h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  try
  {
    v18 = 0;
    v17 = 0;
    v24 = a3;
    DestinationString = 0;
    v25 = 0;
    v19 = 5;
    if ( SourceString )
    {
      if ( a2 )
      {
        if ( a4 )
        {
          v10 = InitializeWDAC();
          v11 = v10;
          if ( v10 >= 0 )
          {
            ActiveState = SIPolicyGetActiveState();
            wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::reset(
              &v17,
              ActiveState);
            v27[0] = GetApplicationSettingCleanup;
            v27[1] = a2;
            v27[2] = SourceString;
            ___ScopeExit_V___Binder_U_Unforced_std__A6AXPEBG0__EAEAPEBGAEAPEBG_std___wil__YA_AV__ScopeExitFn_V___Binder_U_Unforced_std__A6AXPEBG0__EAEAPEBGAEAPEBG_std___details_0___QEAV___Binder_U_Unforced_std__A6AXPEBG0__EAEAPEBGAEAPEBG_std___Z(
              &v20,
              v27);
            RtlInitUnicodeString(&DestinationString, SourceString);
            RtlInitUnicodeString(&v25, a2);
            AppSettingDefinition = SIPolicyGetAppSettingDefinition(
                                     v17,
                                     (unsigned int)&DestinationString,
                                     (unsigned int)&v25,
                                     (unsigned int)&v19,
                                     (__int64)&v18);
            if ( AppSettingDefinition >= 0 )
            {
              if ( v19 == 3 )
              {
                AppSettingString = GetAppSettingString(
                                     v17,
                                     (unsigned int)&DestinationString,
                                     (unsigned int)&v25,
                                     v18,
                                     (__int64)&v24,
                                     a5);
                if ( (int)(AppSettingString + 0x80000000) < 0 || AppSettingString == -2147024662 )
                  *a4 = v24;
                if ( v23 )
                {
                  v23 = 0;
                  v20(v22, v21);
                }
              }
              else
              {
                AppSettingString = wil::details::in1diag3::Return_Win32(
                                     retaddr,
                                     (void *)0x46B,
                                     (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                                     (const char *)0x65D,
                                     v16);
                if ( v23 )
                {
                  v23 = 0;
                  v20(v22, v21);
                }
              }
            }
            else
            {
              AppSettingString = wil::details::in1diag3::Return_NtStatus(
                                   retaddr,
                                   (void *)0x468,
                                   (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                                   (const char *)(unsigned int)AppSettingDefinition,
                                   v16);
              if ( v23 )
              {
                v23 = 0;
                v20(v22, v21);
              }
            }
            wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
            result = AppSettingString;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x459,
              (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
              (const char *)(unsigned int)v10,
              v15);
            wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
            result = v11;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x457,
            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
            (const char *)0x80070057LL,
            v15);
          wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
          result = 2147942487LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x456,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
          (const char *)0x80070057LL,
          v15);
        wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
        result = 2147942487LL;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x455,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)0x80070057LL,
        v15);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
      result = 2147942487LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x47A,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180035500  mov     rax, rsp
0x180035503  push    rbx
0x180035504  push    rsi
0x180035505  push    rdi
0x180035506  push    r14
0x180035508  sub     rsp, 0B8h
0x18003550f  mov     rdi, r9
0x180035512  mov     rsi, rdx
0x180035515  mov     r14, rcx
0x180035518  mov     [rsp+0D8h+var_A0], 0
0x180035520  mov     [rsp+0D8h+var_A8], 0
0x180035529  mov     [rax-78h], r8
0x18003552d  xorps   xmm0, xmm0
0x180035530  movups  xmmword ptr [rax-58h], xmm0
0x180035534  xorps   xmm1, xmm1
0x180035537  movups  xmmword ptr [rax-68h], xmm1
0x18003553b  mov     [rsp+0D8h+var_9C], 5
0x180035543  test    rcx, rcx
0x180035546  jnz     short loc_18003557B
0x180035548  mov     rcx, [rsp+0D8h]; this
0x180035550  mov     ebx, 80070057h
0x180035555  mov     r9d, ebx; char *
0x180035558  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003555f  mov     edx, 455h; void *
0x180035564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035569  nop
0x18003556a  lea     rcx, [rsp+0D8h+var_A8]
0x18003556f  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035574  mov     eax, ebx
0x180035576  jmp     loc_1800357DF
0x18003557b  test    rsi, rsi
0x18003557e  jnz     short loc_1800355B3
0x180035580  mov     rcx, [rsp+0D8h]; this
0x180035588  mov     ebx, 80070057h
0x18003558d  mov     r9d, ebx; char *
0x180035590  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180035597  mov     edx, 456h; void *
0x18003559c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800355a1  nop
0x1800355a2  lea     rcx, [rsp+0D8h+var_A8]
0x1800355a7  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800355ac  mov     eax, ebx
0x1800355ae  jmp     loc_1800357DF
0x1800355b3  test    rdi, rdi
0x1800355b6  jnz     short loc_1800355EB
0x1800355b8  mov     rcx, [rsp+0D8h]; this
0x1800355c0  mov     ebx, 80070057h
0x1800355c5  mov     r9d, ebx; char *
0x1800355c8  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800355cf  mov     edx, 457h; void *
0x1800355d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800355d9  nop
0x1800355da  lea     rcx, [rsp+0D8h+var_A8]
0x1800355df  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800355e4  mov     eax, ebx
0x1800355e6  jmp     loc_1800357DF
0x1800355eb  call    InitializeWDAC
0x1800355f0  mov     ebx, eax
0x1800355f2  test    eax, eax
0x1800355f4  jns     short loc_180035624
0x1800355f6  mov     rcx, [rsp+0D8h]; this
0x1800355fe  mov     r9d, eax; char *
0x180035601  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180035608  mov     edx, 459h; void *
0x18003560d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035612  nop
0x180035613  lea     rcx, [rsp+0D8h+var_A8]
0x180035618  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x18003561d  mov     eax, ebx
0x18003561f  jmp     loc_1800357DF
0x180035624  call    SIPolicyGetActiveState
0x180035629  mov     rdx, rax
0x18003562c  lea     rcx, [rsp+0D8h+var_A8]
0x180035631  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____reset
0x180035636  lea     rax, GetApplicationSettingCleanup
0x18003563d  mov     [rsp+0D8h+var_48], rax
0x180035645  mov     [rsp+0D8h+var_40], rsi
0x18003564d  mov     [rsp+0D8h+var_38], r14
0x180035655  lea     rdx, [rsp+0D8h+var_48]
0x18003565d  lea     rcx, [rsp+0D8h+var_98]
0x180035662  call    ??$ScopeExit@V?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@wil@@YA?AV?$ScopeExitFn@V?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@details@0@$$QEAV?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@Z
0x180035667  nop
0x180035668  mov     rdx, r14; SourceString
0x18003566b  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180035673  call    cs:__imp_RtlInitUnicodeString
0x180035679  mov     rdx, rsi; SourceString
0x18003567c  lea     rcx, [rsp+0D8h+var_68]; DestinationString
0x180035681  call    cs:__imp_RtlInitUnicodeString
0x180035687  lea     rax, [rsp+0D8h+var_A0]
0x18003568c  mov     qword ptr [rsp+0D8h+var_B8], rax; unsigned int
0x180035691  lea     r9, [rsp+0D8h+var_9C]
0x180035696  lea     r8, [rsp+0D8h+var_68]
0x18003569b  lea     rdx, [rsp+0D8h+DestinationString]
0x1800356a3  mov     rcx, [rsp+0D8h+var_A8]
0x1800356a8  call    SIPolicyGetAppSettingDefinition
0x1800356ad  test    eax, eax
0x1800356af  jns     short loc_180035701
0x1800356b1  mov     rcx, [rsp+0D8h]; this
0x1800356b9  mov     r9d, eax; char *
0x1800356bc  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800356c3  mov     edx, 468h; void *
0x1800356c8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800356cd  mov     ebx, eax
0x1800356cf  cmp     [rsp+0D8h+var_80], 0
0x1800356d4  jz      short loc_1800356F0
0x1800356d6  mov     [rsp+0D8h+var_80], 0
0x1800356db  mov     rdx, [rsp+0D8h+var_90]
0x1800356e0  mov     rcx, [rsp+0D8h+var_88]
0x1800356e5  mov     rax, [rsp+0D8h+var_98]
0x1800356ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800356ef  nop
0x1800356f0  lea     rcx, [rsp+0D8h+var_A8]
0x1800356f5  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800356fa  mov     eax, ebx
0x1800356fc  jmp     loc_1800357DF
0x180035701  cmp     [rsp+0D8h+var_9C], 3
0x180035706  jz      short loc_18003575B
0x180035708  mov     rcx, [rsp+0D8h]; this
0x180035710  mov     r9d, 65Dh; char *
0x180035716  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003571d  mov     edx, 46Bh; void *
0x180035722  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035727  mov     ebx, eax
0x180035729  cmp     [rsp+0D8h+var_80], 0
0x18003572e  jz      short loc_18003574A
0x180035730  mov     [rsp+0D8h+var_80], 0
0x180035735  mov     rdx, [rsp+0D8h+var_90]
0x18003573a  mov     rcx, [rsp+0D8h+var_88]
0x18003573f  mov     rax, [rsp+0D8h+var_98]
0x180035744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035749  nop
0x18003574a  lea     rcx, [rsp+0D8h+var_A8]
0x18003574f  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035754  mov     eax, ebx
0x180035756  jmp     loc_1800357DF
0x18003575b  mov     rax, [rsp+0D8h+arg_20]
0x180035763  mov     [rsp+0D8h+var_B0], rax
0x180035768  lea     rax, [rsp+0D8h+var_78]
0x18003576d  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180035772  mov     r9d, [rsp+0D8h+var_A0]
0x180035777  lea     r8, [rsp+0D8h+var_68]
0x18003577c  lea     rdx, [rsp+0D8h+DestinationString]
0x180035784  mov     rcx, [rsp+0D8h+var_A8]
0x180035789  call    GetAppSettingString
0x18003578e  mov     ebx, eax
0x180035790  mov     eax, 80000000h
0x180035795  lea     ecx, [rbx+rax]
0x180035798  test    eax, ecx
0x18003579a  jnz     short loc_1800357A4
0x18003579c  cmp     ebx, 800700EAh
0x1800357a2  jnz     short loc_1800357AC
0x1800357a4  mov     rcx, [rsp+0D8h+var_78]
0x1800357a9  mov     [rdi], rcx
0x1800357ac  cmp     [rsp+0D8h+var_80], 0
0x1800357b1  jz      short loc_1800357CD
0x1800357b3  mov     [rsp+0D8h+var_80], 0
0x1800357b8  mov     rdx, [rsp+0D8h+var_90]
0x1800357bd  mov     rcx, [rsp+0D8h+var_88]
0x1800357c2  mov     rax, [rsp+0D8h+var_98]
0x1800357c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357cc  nop
0x1800357cd  lea     rcx, [rsp+0D8h+var_A8]
0x1800357d2  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800357d7  mov     eax, ebx
0x1800357d9  jmp     short loc_1800357DF
0x1800357db  mov     eax, [rsp+0D8h+var_A0]
0x1800357df  add     rsp, 0B8h
0x1800357e6  pop     r14
0x1800357e8  pop     rdi
0x1800357e9  pop     rsi
0x1800357ea  pop     rbx
0x1800357eb  retn
```
