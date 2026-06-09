# WldpGetApplicationSettingBoolean

- ea: `0x1800351e0`
- end: `0x1800354f9`
- name: `WldpGetApplicationSettingBoolean`
- size: `793`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR, __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180017054`
- `0x18002e4d4`

## callees

- `0x18001de88`
- `0x18001e628`
- `0x18001f038`
- `0x1800206f4`
- `0x1800313ac`
- `0x1800331ec`
- `0x180033778`
- `0x180035180`
- `0x1800351e0`
- `0x18003932c`
- `0x180039b54`
- `0x180042010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003534e`
- `ntdll!RtlInitUnicodeString` at `0x18003535c`
- `ntdll!RtlInitUnicodeString` at `0x18003534e`
- `ntdll!RtlInitUnicodeString` at `0x18003535c`

## string_xrefs

- `0x180035236`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x18003526e`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800352a6`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800352df`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035397`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800353f4`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035468`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WldpGetApplicationSettingBoolean(PCWSTR SourceString, PCWSTR a2, __int64 a3)
{
  const char *v6; // r9
  __int64 result; // rax
  int v8; // eax
  unsigned int v9; // ebx
  __int64 ActiveState; // rax
  int AppSettingDefinition; // eax
  unsigned int v12; // ebx
  int AppSettingBoolean; // eax
  int v14; // [rsp+20h] [rbp-98h]
  unsigned int v15; // [rsp+20h] [rbp-98h]
  int v16; // [rsp+20h] [rbp-98h]
  __int64 v17; // [rsp+30h] [rbp-88h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-80h] BYREF
  void (__fastcall *v19)(__int64, __int64); // [rsp+40h] [rbp-78h] BYREF
  __int64 v20; // [rsp+48h] [rbp-70h]
  __int64 v21; // [rsp+50h] [rbp-68h]
  char v22; // [rsp+58h] [rbp-60h]
  struct _UNICODE_STRING v23; // [rsp+68h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-40h] BYREF
  _QWORD v25[3]; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v27; // [rsp+D8h] [rbp+20h] BYREF

  try
  {
    v18 = 0;
    v17 = 0;
    DestinationString = 0;
    v23 = 0;
    v27 = 5;
    if ( !SourceString )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FF,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)0x80070057LL,
        v14);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
      return 2147942487LL;
    }
    if ( !a2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x400,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)0x80070057LL,
        v14);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
      return 2147942487LL;
    }
    if ( !a3 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x401,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)0x80070057LL,
        v14);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
      return 2147942487LL;
    }
    v8 = InitializeWDAC();
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x403,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)(unsigned int)v8,
        v14);
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
      return v9;
    }
    ActiveState = SIPolicyGetActiveState();
    wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t___::reset(
      &v17,
      ActiveState);
    v25[0] = GetApplicationSettingCleanup;
    v25[1] = a2;
    v25[2] = SourceString;
    ___ScopeExit_V___Binder_U_Unforced_std__A6AXPEBG0__EAEAPEBGAEAPEBG_std___wil__YA_AV__ScopeExitFn_V___Binder_U_Unforced_std__A6AXPEBG0__EAEAPEBGAEAPEBG_std___details_0___QEAV___Binder_U_Unforced_std__A6AXPEBG0__EAEAPEBGAEAPEBG_std___Z(
      &v19,
      v25);
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlInitUnicodeString(&v23, a2);
    AppSettingDefinition = SIPolicyGetAppSettingDefinition(
                             v17,
                             (unsigned int)&DestinationString,
                             (unsigned int)&v23,
                             (unsigned int)&v27,
                             (__int64)&v18);
    if ( AppSettingDefinition < 0 )
    {
      v12 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0x413,
              (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
              (const char *)(unsigned int)AppSettingDefinition,
              v15);
      if ( v22 )
        goto LABEL_18;
      goto LABEL_19;
    }
    if ( v27 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x416,
              (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
              (const char *)0x65D,
              v15);
      if ( v22 )
        goto LABEL_18;
      goto LABEL_19;
    }
    AppSettingBoolean = GetAppSettingBoolean(v17, (unsigned int)&DestinationString, (unsigned int)&v23, v18, a3);
    v12 = AppSettingBoolean;
    if ( AppSettingBoolean < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41D,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
        (const char *)(unsigned int)AppSettingBoolean,
        v16);
      if ( v22 )
      {
LABEL_18:
        v22 = 0;
        v19(v21, v20);
      }
LABEL_19:
      wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
      return v12;
    }
    if ( v22 )
    {
      v22 = 0;
      v19(v21, v20);
    }
    wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____::_unique_any_t_wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd::integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std::nullptr_t_____(&v17);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x420,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x1800351e0  mov     rax, rsp
0x1800351e3  mov     [rax+8], rbx
0x1800351e7  mov     [rax+10h], rsi
0x1800351eb  push    rdi
0x1800351ec  push    r14
0x1800351ee  push    r15
0x1800351f0  sub     rsp, 0A0h
0x1800351f7  mov     rdi, r8
0x1800351fa  mov     rsi, rdx
0x1800351fd  mov     r14, rcx
0x180035200  xor     r15d, r15d
0x180035203  mov     [rax-80h], r15d
0x180035207  mov     [rsp+0B8h+var_88], r15
0x18003520c  xorps   xmm0, xmm0
0x18003520f  movups  xmmword ptr [rax-40h], xmm0
0x180035213  xorps   xmm1, xmm1
0x180035216  movups  xmmword ptr [rax-50h], xmm1
0x18003521a  mov     dword ptr [rax+20h], 5
0x180035221  test    rcx, rcx
0x180035224  jnz     short loc_180035259
0x180035226  mov     rcx, [rsp+0B8h]; this
0x18003522e  mov     ebx, 80070057h
0x180035233  mov     r9d, ebx; char *
0x180035236  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003523d  mov     edx, 3FFh; void *
0x180035242  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035247  nop
0x180035248  lea     rcx, [rsp+0B8h+var_88]
0x18003524d  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035252  mov     eax, ebx
0x180035254  jmp     loc_1800354DF
0x180035259  test    rsi, rsi
0x18003525c  jnz     short loc_180035291
0x18003525e  mov     rcx, [rsp+0B8h]; this
0x180035266  mov     ebx, 80070057h
0x18003526b  mov     r9d, ebx; char *
0x18003526e  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180035275  mov     edx, 400h; void *
0x18003527a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003527f  nop
0x180035280  lea     rcx, [rsp+0B8h+var_88]
0x180035285  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x18003528a  mov     eax, ebx
0x18003528c  jmp     loc_1800354DF
0x180035291  test    rdi, rdi
0x180035294  jnz     short loc_1800352C9
0x180035296  mov     rcx, [rsp+0B8h]; this
0x18003529e  mov     ebx, 80070057h
0x1800352a3  mov     r9d, ebx; char *
0x1800352a6  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800352ad  mov     edx, 401h; void *
0x1800352b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800352b7  nop
0x1800352b8  lea     rcx, [rsp+0B8h+var_88]
0x1800352bd  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800352c2  mov     eax, ebx
0x1800352c4  jmp     loc_1800354DF
0x1800352c9  call    InitializeWDAC
0x1800352ce  mov     ebx, eax
0x1800352d0  test    eax, eax
0x1800352d2  jns     short loc_180035302
0x1800352d4  mov     rcx, [rsp+0B8h]; this
0x1800352dc  mov     r9d, eax; char *
0x1800352df  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800352e6  mov     edx, 403h; void *
0x1800352eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800352f0  nop
0x1800352f1  lea     rcx, [rsp+0B8h+var_88]
0x1800352f6  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800352fb  mov     eax, ebx
0x1800352fd  jmp     loc_1800354DF
0x180035302  call    SIPolicyGetActiveState
0x180035307  mov     rdx, rax
0x18003530a  lea     rcx, [rsp+0B8h+var_88]
0x18003530f  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____reset
0x180035314  lea     rax, GetApplicationSettingCleanup
0x18003531b  mov     [rsp+0B8h+var_30], rax
0x180035323  mov     [rsp+0B8h+var_28], rsi
0x18003532b  mov     [rsp+0B8h+var_20], r14
0x180035333  lea     rdx, [rsp+0B8h+var_30]
0x18003533b  lea     rcx, [rsp+0B8h+var_78]
0x180035340  call    ??$ScopeExit@V?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@wil@@YA?AV?$ScopeExitFn@V?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@details@0@$$QEAV?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@Z
0x180035345  nop
0x180035346  mov     rdx, r14; SourceString
0x180035349  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x18003534e  call    cs:__imp_RtlInitUnicodeString
0x180035354  mov     rdx, rsi; SourceString
0x180035357  lea     rcx, [rsp+0B8h+var_50]; DestinationString
0x18003535c  call    cs:__imp_RtlInitUnicodeString
0x180035362  lea     rax, [rsp+0B8h+var_80]
0x180035367  mov     qword ptr [rsp+0B8h+var_98], rax; unsigned int
0x18003536c  lea     r9, [rsp+0B8h+arg_18]
0x180035374  lea     r8, [rsp+0B8h+var_50]
0x180035379  lea     rdx, [rsp+0B8h+DestinationString]
0x18003537e  mov     rcx, [rsp+0B8h+var_88]
0x180035383  call    SIPolicyGetAppSettingDefinition
0x180035388  test    eax, eax
0x18003538a  jns     short loc_1800353DC
0x18003538c  mov     rcx, [rsp+0B8h]; this
0x180035394  mov     r9d, eax; char *
0x180035397  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003539e  mov     edx, 413h; void *
0x1800353a3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800353a8  mov     ebx, eax
0x1800353aa  cmp     [rsp+0B8h+var_60], r15b
0x1800353af  jz      short loc_1800353CB
0x1800353b1  mov     [rsp+0B8h+var_60], r15b
0x1800353b6  mov     rdx, [rsp+0B8h+var_70]
0x1800353bb  mov     rcx, [rsp+0B8h+var_68]
0x1800353c0  mov     rax, [rsp+0B8h+var_78]
0x1800353c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800353ca  nop
0x1800353cb  lea     rcx, [rsp+0B8h+var_88]
0x1800353d0  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800353d5  mov     eax, ebx
0x1800353d7  jmp     loc_1800354DF
0x1800353dc  cmp     [rsp+0B8h+arg_18], r15d
0x1800353e4  jz      short loc_180035439
0x1800353e6  mov     rcx, [rsp+0B8h]; this
0x1800353ee  mov     r9d, 65Dh; char *
0x1800353f4  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800353fb  mov     edx, 416h; void *
0x180035400  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035405  mov     ebx, eax
0x180035407  cmp     [rsp+0B8h+var_60], r15b
0x18003540c  jz      short loc_180035428
0x18003540e  mov     [rsp+0B8h+var_60], r15b
0x180035413  mov     rdx, [rsp+0B8h+var_70]
0x180035418  mov     rcx, [rsp+0B8h+var_68]
0x18003541d  mov     rax, [rsp+0B8h+var_78]
0x180035422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035427  nop
0x180035428  lea     rcx, [rsp+0B8h+var_88]
0x18003542d  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035432  mov     eax, ebx
0x180035434  jmp     loc_1800354DF
0x180035439  mov     qword ptr [rsp+0B8h+var_98], rdi; int
0x18003543e  mov     r9d, [rsp+0B8h+var_80]
0x180035443  lea     r8, [rsp+0B8h+var_50]
0x180035448  lea     rdx, [rsp+0B8h+DestinationString]
0x18003544d  mov     rcx, [rsp+0B8h+var_88]
0x180035452  call    GetAppSettingBoolean
0x180035457  mov     ebx, eax
0x180035459  test    eax, eax
0x18003545b  jns     short loc_1800354A9
0x18003545d  mov     rcx, [rsp+0B8h]; this
0x180035465  mov     r9d, eax; char *
0x180035468  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003546f  mov     edx, 41Dh; void *
0x180035474  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035479  nop
0x18003547a  cmp     [rsp+0B8h+var_60], r15b
0x18003547f  jz      short loc_18003549B
0x180035481  mov     [rsp+0B8h+var_60], r15b
0x180035486  mov     rdx, [rsp+0B8h+var_70]
0x18003548b  mov     rcx, [rsp+0B8h+var_68]
0x180035490  mov     rax, [rsp+0B8h+var_78]
0x180035495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003549a  nop
0x18003549b  lea     rcx, [rsp+0B8h+var_88]
0x1800354a0  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800354a5  mov     eax, ebx
0x1800354a7  jmp     short loc_1800354DF
0x1800354a9  cmp     [rsp+0B8h+var_60], r15b
0x1800354ae  jz      short loc_1800354CA
0x1800354b0  mov     [rsp+0B8h+var_60], r15b
0x1800354b5  mov     rdx, [rsp+0B8h+var_70]
0x1800354ba  mov     rcx, [rsp+0B8h+var_68]
0x1800354bf  mov     rax, [rsp+0B8h+var_78]
0x1800354c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800354c9  nop
0x1800354ca  lea     rcx, [rsp+0B8h+var_88]
0x1800354cf  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800354d4  xor     eax, eax
0x1800354d6  jmp     short loc_1800354DF
0x1800354d8  mov     eax, [rsp+0B8h+arg_18]
0x1800354df  lea     r11, [rsp+0B8h+var_18]
0x1800354e7  mov     rbx, [r11+20h]
0x1800354eb  mov     rsi, [r11+28h]
0x1800354ef  mov     rsp, r11
0x1800354f2  pop     r15
0x1800354f4  pop     r14
0x1800354f6  pop     rdi
0x1800354f7  retn
```
