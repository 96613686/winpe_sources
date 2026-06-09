# WscServiceUtils::OneWayAMPPLEnablementAgent::AddNonCompliantProduct(ushort const * const)

- ea: `0x1800351ac`
- end: `0x180035323`
- name: `?AddNonCompliantProduct@OneWayAMPPLEnablementAgent@WscServiceUtils@@QEAAXQEBG@Z`
- size: `375`
- prototype: `void __fastcall(HANDLE *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025520`
- `0x18003532c`

## callees

- `0x180008e48`
- `0x180017a48`
- `0x180018ab0`
- `0x1800202e8`
- `0x1800205e4`
- `0x1800228ec`
- `0x180029158`
- `0x180034e84`
- `0x1800351ac`
- `0x180035444`
- `0x180035d98`
- `0x18003fc30`

## pseudocode

```c
void __fastcall WscServiceUtils::OneWayAMPPLEnablementAgent::AddNonCompliantProduct(
        HANDLE *this,
        const unsigned __int16 *a2)
{
  CThirdPartyManager *v4; // rcx
  WscServiceUtils::OneWayAMPPLEnablementAgent *v5; // rcx
  __int64 v6; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v7[16]; // [rsp+38h] [rbp-50h] BYREF
  _QWORD v8[5]; // [rsp+48h] [rbp-40h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids, a2);
    v4 = WPP_GLOBAL_Control;
  }
  if ( this[8] )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      this + 8,
      &v6);
    std::wstring::wstring(v8, a2);
    if ( !std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count(
            this,
            v8)
      && WscServiceUtils::OneWayAMPPLEnablementAgent::ChangeCountInRegistry(v5, *((_DWORD *)this + 2) + 1) )
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert<std::wstring const &,std::_Nil>(
        (__int64 **)this,
        (__int64)v7,
        (__int64)v8);
    }
    std::wstring::_Tidy(v8, 1, 0);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v6);
  }
  else if ( v4 != (CThirdPartyManager *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
  {
    WPP_SF_(*((_QWORD *)v4 + 2), 32, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids);
  }
}

```

## disassembly

```asm
0x1800351ac  mov     [rsp+arg_10], rbx
0x1800351b1  mov     [rsp+arg_18], rsi
0x1800351b6  push    rdi
0x1800351b7  sub     rsp, 80h
0x1800351be  mov     rax, cs:__security_cookie
0x1800351c5  xor     rax, rsp
0x1800351c8  mov     [rsp+88h+var_18], rax
0x1800351cd  mov     rsi, rdx
0x1800351d0  mov     rdi, rcx
0x1800351d3  lea     rbx, WPP_GLOBAL_Control
0x1800351da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351e1  cmp     rcx, rbx
0x1800351e4  jz      short loc_18003520B
0x1800351e6  test    byte ptr [rcx+1Ch], 4
0x1800351ea  jz      short loc_18003520B
0x1800351ec  mov     edx, 1Fh
0x1800351f1  mov     r9, rsi
0x1800351f4  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x1800351fb  mov     rcx, [rcx+10h]
0x1800351ff  call    WPP_SF_S
0x180035204  mov     rcx, cs:WPP_GLOBAL_Control
0x18003520b  cmp     qword ptr [rdi+40h], 0
0x180035210  jnz     short loc_180035237
0x180035212  cmp     rcx, rbx
0x180035215  jz      short loc_180035232
0x180035217  test    byte ptr [rcx+1Ch], 1
0x18003521b  jz      short loc_180035232
0x18003521d  mov     edx, 20h ; ' '
0x180035222  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x180035229  mov     rcx, [rcx+10h]
0x18003522d  call    WPP_SF_
0x180035232  jmp     loc_180035300
0x180035237  lea     rdx, [rsp+88h+var_58]
0x18003523c  lea     rcx, [rdi+40h]
0x180035240  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180035245  nop
0x180035246  mov     rdx, rsi
0x180035249  lea     rcx, [rsp+88h+var_40]
0x18003524e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180035253  nop
0x180035254  lea     rdx, [rsp+88h+var_40]
0x180035259  mov     rcx, rdi
0x18003525c  call    ?count@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::count(std::wstring const &)
0x180035261  test    rax, rax
0x180035264  jz      short loc_180035282
0x180035266  xor     r8d, r8d
0x180035269  mov     dl, 1
0x18003526b  lea     rcx, [rsp+88h+var_40]
0x180035270  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180035275  nop
0x180035276  lea     rcx, [rsp+88h+var_58]
0x18003527b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035280  jmp     short loc_180035300
0x180035282  mov     edx, [rdi+8]
0x180035285  inc     edx; unsigned int
0x180035287  call    ?ChangeCountInRegistry@OneWayAMPPLEnablementAgent@WscServiceUtils@@AEAA_NK@Z; WscServiceUtils::OneWayAMPPLEnablementAgent::ChangeCountInRegistry(ulong)
0x18003528c  test    al, al
0x18003528e  jz      short loc_1800352AA
0x180035290  mov     r9b, cs:byte_1800540D2
0x180035297  lea     r8, [rsp+88h+var_40]
0x18003529c  lea     rdx, [rsp+88h+var_50]
0x1800352a1  mov     rcx, rdi
0x1800352a4  call    ??$_Insert@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_Nil@2@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@U_Nil@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Insert<std::wstring const &,std::_Nil>(std::wstring const &,std::_Nil)
0x1800352a9  nop
0x1800352aa  xor     r8d, r8d
0x1800352ad  mov     dl, 1
0x1800352af  lea     rcx, [rsp+88h+var_40]
0x1800352b4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800352b9  nop
0x1800352ba  lea     rcx, [rsp+88h+var_58]
0x1800352bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800352c4  nop
0x1800352c5  jmp     short loc_180035300
0x1800352c7  mov     r9d, dword ptr [rsp+88h+var_58]
0x1800352cc  test    r9d, r9d
0x1800352cf  jns     short loc_180035300
0x1800352d1  lea     rbx, WPP_GLOBAL_Control
0x1800352d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800352df  cmp     rcx, rbx
0x1800352e2  jz      short loc_180035300
0x1800352e4  test    byte ptr [rcx+1Ch], 1
0x1800352e8  jz      short loc_180035300
0x1800352ea  mov     edx, 21h ; '!'
0x1800352ef  lea     r8, WPP_259e22ae9b843fb308c2f2b5f94ca765_Traceguids
0x1800352f6  mov     rcx, [rcx+10h]
0x1800352fa  call    WPP_SF_d
0x1800352ff  nop
0x180035300  mov     rcx, [rsp+88h+var_18]
0x180035305  xor     rcx, rsp; StackCookie
0x180035308  call    __security_check_cookie
0x18003530d  lea     r11, [rsp+88h+var_8]
0x180035315  mov     rbx, [r11+20h]
0x180035319  mov     rsi, [r11+28h]
0x18003531d  mov     rsp, r11
0x180035320  pop     rdi
0x180035321  retn
```
