# WscServiceUtils::OneWayAMPPLEnablementAgent::RemoveNonCompliantProduct(ushort const * const)

- ea: `0x180035548`
- end: `0x1800356ab`
- name: `?RemoveNonCompliantProduct@OneWayAMPPLEnablementAgent@WscServiceUtils@@QEAAXQEBG@Z`
- size: `355`
- prototype: `void __fastcall(WscServiceUtils::OneWayAMPPLEnablementAgent *__hidden this, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800356b4`

## callees

- `0x180008e48`
- `0x180017a48`
- `0x180018ab0`
- `0x1800202e8`
- `0x1800205e4`
- `0x1800228ec`
- `0x180029158`
- `0x180035444`
- `0x180035548`
- `0x180035d98`
- `0x180035fa0`
- `0x18003fc30`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall WscServiceUtils::OneWayAMPPLEnablementAgent::RemoveNonCompliantProduct(
        HANDLE *this,
        const unsigned __int16 *a2)
{
  CThirdPartyManager *v4; // rcx
  WscServiceUtils::OneWayAMPPLEnablementAgent *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v7[5]; // [rsp+38h] [rbp-40h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, a2);
    v4 = WPP_GLOBAL_Control;
  }
  if ( this[8] )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      this + 8,
      &v6);
    std::wstring::wstring(v7, a2);
    if ( std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count(
           (__int64)this,
           (__int64)v7)
      && WscServiceUtils::OneWayAMPPLEnablementAgent::ChangeCountInRegistry(
           v5,
           (unsigned int)(*((_DWORD *)this + 2) - 1)) )
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(
        (__int64 *)this,
        v7);
    }
    std::wstring::_Tidy(v7, 1, 0);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v6);
  }
  else if ( v4 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v4 + 2), 35, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  }
}

```

## disassembly

```asm
0x180035548  mov     [rsp+arg_10], rbx
0x18003554d  mov     [rsp+arg_18], rsi
0x180035552  push    rdi
0x180035553  sub     rsp, 70h
0x180035557  mov     rax, cs:__security_cookie
0x18003555e  xor     rax, rsp
0x180035561  mov     [rsp+78h+var_18], rax
0x180035566  mov     rsi, rdx
0x180035569  mov     rdi, rcx
0x18003556c  lea     rbx, WPP_GLOBAL_Control
0x180035573  mov     rcx, cs:WPP_GLOBAL_Control
0x18003557a  cmp     rcx, rbx
0x18003557d  jz      short loc_1800355A4
0x18003557f  test    byte ptr [rcx+1Ch], 4
0x180035583  jz      short loc_1800355A4
0x180035585  mov     edx, 22h ; '"'
0x18003558a  mov     r9, rsi
0x18003558d  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180035594  mov     rcx, [rcx+10h]
0x180035598  call    WPP_SF_S
0x18003559d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800355a4  cmp     qword ptr [rdi+40h], 0
0x1800355a9  jnz     short loc_1800355D0
0x1800355ab  cmp     rcx, rbx
0x1800355ae  jz      short loc_1800355CB
0x1800355b0  test    byte ptr [rcx+1Ch], 1
0x1800355b4  jz      short loc_1800355CB
0x1800355b6  mov     edx, 23h ; '#'
0x1800355bb  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x1800355c2  mov     rcx, [rcx+10h]
0x1800355c6  call    WPP_SF_
0x1800355cb  jmp     loc_18003568B
0x1800355d0  lea     rdx, [rsp+78h+var_48]
0x1800355d5  lea     rcx, [rdi+40h]
0x1800355d9  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800355de  nop
0x1800355df  mov     rdx, rsi
0x1800355e2  lea     rcx, [rsp+78h+var_40]
0x1800355e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800355ec  lea     rdx, [rsp+78h+var_40]
0x1800355f1  mov     rcx, rdi
0x1800355f4  call    ?count@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count(std::wstring const &)
0x1800355f9  test    rax, rax
0x1800355fc  jnz     short loc_18003561A
0x1800355fe  xor     r8d, r8d
0x180035601  mov     dl, 1
0x180035603  lea     rcx, [rsp+78h+var_40]
0x180035608  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18003560d  nop
0x18003560e  lea     rcx, [rsp+78h+var_48]
0x180035613  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035618  jmp     short loc_18003568B
0x18003561a  mov     edx, [rdi+8]
0x18003561d  dec     edx; unsigned int
0x18003561f  call    ?ChangeCountInRegistry@OneWayAMPPLEnablementAgent@WscServiceUtils@@AEAA_NK@Z; WscServiceUtils::OneWayAMPPLEnablementAgent::ChangeCountInRegistry(ulong)
0x180035624  test    al, al
0x180035626  jz      short loc_180035635
0x180035628  lea     rdx, [rsp+78h+var_40]
0x18003562d  mov     rcx, rdi
0x180035630  call    ?erase@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::erase(std::wstring const &)
0x180035635  xor     r8d, r8d
0x180035638  mov     dl, 1
0x18003563a  lea     rcx, [rsp+78h+var_40]
0x18003563f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180035644  nop
0x180035645  lea     rcx, [rsp+78h+var_48]
0x18003564a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003564f  nop
0x180035650  jmp     short loc_18003568B
0x180035652  mov     r9d, dword ptr [rsp+78h+var_48]
0x180035657  test    r9d, r9d
0x18003565a  jns     short loc_18003568B
0x18003565c  lea     rbx, WPP_GLOBAL_Control
0x180035663  mov     rcx, cs:WPP_GLOBAL_Control
0x18003566a  cmp     rcx, rbx
0x18003566d  jz      short loc_18003568B
0x18003566f  test    byte ptr [rcx+1Ch], 1
0x180035673  jz      short loc_18003568B
0x180035675  mov     edx, 24h ; '$'
0x18003567a  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180035681  mov     rcx, [rcx+10h]
0x180035685  call    WPP_SF_d
0x18003568a  nop
0x18003568b  mov     rcx, [rsp+78h+var_18]
0x180035690  xor     rcx, rsp; StackCookie
0x180035693  call    __security_check_cookie
0x180035698  lea     r11, [rsp+78h+var_8]
0x18003569d  mov     rbx, [r11+20h]
0x1800356a1  mov     rsi, [r11+28h]
0x1800356a5  mov     rsp, r11
0x1800356a8  pop     rdi
0x1800356a9  retn
```
