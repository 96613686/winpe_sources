# WldpGetApplicationSettingStringSet

- ea: `0x180035800`
- end: `0x180035aed`
- name: `WldpGetApplicationSettingStringSet`
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
- `0x180033d40`
- `0x180035180`
- `0x180035800`
- `0x18003932c`
- `0x180039b54`
- `0x180042010`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180035973`
- `ntdll!RtlInitUnicodeString` at `0x180035981`
- `ntdll!RtlInitUnicodeString` at `0x180035973`
- `ntdll!RtlInitUnicodeString` at `0x180035981`

## string_xrefs

- `0x180035858`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035890`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800358c8`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035901`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x1800359bc`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`
- `0x180035a16`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall WldpGetApplicationSettingStringSet(
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
  unsigned int AppSettingStringSet; // ebx
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
              if ( v19 == 4 )
              {
                AppSettingStringSet = GetAppSettingStringSet(
                                        v17,
                                        (unsigned int)&DestinationString,
                                        (unsigned int)&v25,
                                        v18,
                                        (__int64)&v24,
                                        a5);
                if ( (int)(AppSettingStringSet + 0x80000000) < 0 || AppSettingStringSet == -2147024662 )
                  *a4 = v24;
                if ( v23 )
                {
                  v23 = 0;
                  v20(v22, v21);
                }
              }
              else
              {
                AppSettingStringSet = wil::details::in1diag3::Return_Win32(
                                        retaddr,
                                        (void *)0x4C6,
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
              AppSettingStringSet = wil::details::in1diag3::Return_NtStatus(
                                      retaddr,
                                      (void *)0x4C3,
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
            result = AppSettingStringSet;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4B4,
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
            (void *)0x4B2,
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
          (void *)0x4B1,
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
        (void *)0x4B0,
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
                           (void *)0x4D5,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x180035800  mov     rax, rsp
0x180035803  push    rbx
0x180035804  push    rsi
0x180035805  push    rdi
0x180035806  push    r14
0x180035808  sub     rsp, 0B8h
0x18003580f  mov     rdi, r9
0x180035812  mov     rsi, rdx
0x180035815  mov     r14, rcx
0x180035818  mov     [rsp+0D8h+var_A0], 0
0x180035820  mov     [rsp+0D8h+var_A8], 0
0x180035829  mov     [rax-78h], r8
0x18003582d  xorps   xmm0, xmm0
0x180035830  movups  xmmword ptr [rax-58h], xmm0
0x180035834  xorps   xmm1, xmm1
0x180035837  movups  xmmword ptr [rax-68h], xmm1
0x18003583b  mov     [rsp+0D8h+var_9C], 5
0x180035843  test    rcx, rcx
0x180035846  jnz     short loc_18003587B
0x180035848  mov     rcx, [rsp+0D8h]; this
0x180035850  mov     ebx, 80070057h
0x180035855  mov     r9d, ebx; char *
0x180035858  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18003585f  mov     edx, 4B0h; void *
0x180035864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035869  nop
0x18003586a  lea     rcx, [rsp+0D8h+var_A8]
0x18003586f  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035874  mov     eax, ebx
0x180035876  jmp     loc_180035ADF
0x18003587b  test    rsi, rsi
0x18003587e  jnz     short loc_1800358B3
0x180035880  mov     rcx, [rsp+0D8h]; this
0x180035888  mov     ebx, 80070057h
0x18003588d  mov     r9d, ebx; char *
0x180035890  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180035897  mov     edx, 4B1h; void *
0x18003589c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358a1  nop
0x1800358a2  lea     rcx, [rsp+0D8h+var_A8]
0x1800358a7  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800358ac  mov     eax, ebx
0x1800358ae  jmp     loc_180035ADF
0x1800358b3  test    rdi, rdi
0x1800358b6  jnz     short loc_1800358EB
0x1800358b8  mov     rcx, [rsp+0D8h]; this
0x1800358c0  mov     ebx, 80070057h
0x1800358c5  mov     r9d, ebx; char *
0x1800358c8  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800358cf  mov     edx, 4B2h; void *
0x1800358d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800358d9  nop
0x1800358da  lea     rcx, [rsp+0D8h+var_A8]
0x1800358df  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800358e4  mov     eax, ebx
0x1800358e6  jmp     loc_180035ADF
0x1800358eb  call    InitializeWDAC
0x1800358f0  mov     ebx, eax
0x1800358f2  test    eax, eax
0x1800358f4  jns     short loc_180035924
0x1800358f6  mov     rcx, [rsp+0D8h]; this
0x1800358fe  mov     r9d, eax; char *
0x180035901  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180035908  mov     edx, 4B4h; void *
0x18003590d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035912  nop
0x180035913  lea     rcx, [rsp+0D8h+var_A8]
0x180035918  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x18003591d  mov     eax, ebx
0x18003591f  jmp     loc_180035ADF
0x180035924  call    SIPolicyGetActiveState
0x180035929  mov     rdx, rax
0x18003592c  lea     rcx, [rsp+0D8h+var_A8]
0x180035931  call    wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____reset
0x180035936  lea     rax, GetApplicationSettingCleanup
0x18003593d  mov     [rsp+0D8h+var_48], rax
0x180035945  mov     [rsp+0D8h+var_40], rsi
0x18003594d  mov     [rsp+0D8h+var_38], r14
0x180035955  lea     rdx, [rsp+0D8h+var_48]
0x18003595d  lea     rcx, [rsp+0D8h+var_98]
0x180035962  call    ??$ScopeExit@V?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@wil@@YA?AV?$ScopeExitFn@V?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@details@0@$$QEAV?$_Binder@U_Unforced@std@@A6AXPEBG0@_EAEAPEBGAEAPEBG@std@@@Z
0x180035967  nop
0x180035968  mov     rdx, r14; SourceString
0x18003596b  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x180035973  call    cs:__imp_RtlInitUnicodeString
0x180035979  mov     rdx, rsi; SourceString
0x18003597c  lea     rcx, [rsp+0D8h+var_68]; DestinationString
0x180035981  call    cs:__imp_RtlInitUnicodeString
0x180035987  lea     rax, [rsp+0D8h+var_A0]
0x18003598c  mov     qword ptr [rsp+0D8h+var_B8], rax; unsigned int
0x180035991  lea     r9, [rsp+0D8h+var_9C]
0x180035996  lea     r8, [rsp+0D8h+var_68]
0x18003599b  lea     rdx, [rsp+0D8h+DestinationString]
0x1800359a3  mov     rcx, [rsp+0D8h+var_A8]
0x1800359a8  call    SIPolicyGetAppSettingDefinition
0x1800359ad  test    eax, eax
0x1800359af  jns     short loc_180035A01
0x1800359b1  mov     rcx, [rsp+0D8h]; this
0x1800359b9  mov     r9d, eax; char *
0x1800359bc  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800359c3  mov     edx, 4C3h; void *
0x1800359c8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800359cd  mov     ebx, eax
0x1800359cf  cmp     [rsp+0D8h+var_80], 0
0x1800359d4  jz      short loc_1800359F0
0x1800359d6  mov     [rsp+0D8h+var_80], 0
0x1800359db  mov     rdx, [rsp+0D8h+var_90]
0x1800359e0  mov     rcx, [rsp+0D8h+var_88]
0x1800359e5  mov     rax, [rsp+0D8h+var_98]
0x1800359ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359ef  nop
0x1800359f0  lea     rcx, [rsp+0D8h+var_A8]
0x1800359f5  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x1800359fa  mov     eax, ebx
0x1800359fc  jmp     loc_180035ADF
0x180035a01  cmp     [rsp+0D8h+var_9C], 4
0x180035a06  jz      short loc_180035A5B
0x180035a08  mov     rcx, [rsp+0D8h]; this
0x180035a10  mov     r9d, 65Dh; char *
0x180035a16  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x180035a1d  mov     edx, 4C6h; void *
0x180035a22  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180035a27  mov     ebx, eax
0x180035a29  cmp     [rsp+0D8h+var_80], 0
0x180035a2e  jz      short loc_180035A4A
0x180035a30  mov     [rsp+0D8h+var_80], 0
0x180035a35  mov     rdx, [rsp+0D8h+var_90]
0x180035a3a  mov     rcx, [rsp+0D8h+var_88]
0x180035a3f  mov     rax, [rsp+0D8h+var_98]
0x180035a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a49  nop
0x180035a4a  lea     rcx, [rsp+0D8h+var_A8]
0x180035a4f  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035a54  mov     eax, ebx
0x180035a56  jmp     loc_180035ADF
0x180035a5b  mov     rax, [rsp+0D8h+arg_20]
0x180035a63  mov     [rsp+0D8h+var_B0], rax
0x180035a68  lea     rax, [rsp+0D8h+var_78]
0x180035a6d  mov     qword ptr [rsp+0D8h+var_B8], rax
0x180035a72  mov     r9d, [rsp+0D8h+var_A0]
0x180035a77  lea     r8, [rsp+0D8h+var_68]
0x180035a7c  lea     rdx, [rsp+0D8h+DestinationString]
0x180035a84  mov     rcx, [rsp+0D8h+var_A8]
0x180035a89  call    GetAppSettingStringSet
0x180035a8e  mov     ebx, eax
0x180035a90  mov     eax, 80000000h
0x180035a95  lea     ecx, [rbx+rax]
0x180035a98  test    eax, ecx
0x180035a9a  jnz     short loc_180035AA4
0x180035a9c  cmp     ebx, 800700EAh
0x180035aa2  jnz     short loc_180035AAC
0x180035aa4  mov     rcx, [rsp+0D8h+var_78]
0x180035aa9  mov     [rdi], rcx
0x180035aac  cmp     [rsp+0D8h+var_80], 0
0x180035ab1  jz      short loc_180035ACD
0x180035ab3  mov     [rsp+0D8h+var_80], 0
0x180035ab8  mov     rdx, [rsp+0D8h+var_90]
0x180035abd  mov     rcx, [rsp+0D8h+var_88]
0x180035ac2  mov     rax, [rsp+0D8h+var_98]
0x180035ac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035acc  nop
0x180035acd  lea     rcx, [rsp+0D8h+var_A8]
0x180035ad2  call    wil__unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t________unique_any_t_wil__details__unique_storage_wil__details__resource_policy_SIPOLICY_STATE___void___cdecl_SIPOLICY_STATE_____ReleaseState_wistd__integral_constant_unsigned___int64_0__SIPOLICY_STATE___SIPOLICY_STATE___0_std__nullptr_t_____
0x180035ad7  mov     eax, ebx
0x180035ad9  jmp     short loc_180035ADF
0x180035adb  mov     eax, [rsp+0D8h+var_A0]
0x180035adf  add     rsp, 0B8h
0x180035ae6  pop     r14
0x180035ae8  pop     rdi
0x180035ae9  pop     rsi
0x180035aea  pop     rbx
0x180035aeb  retn
```
