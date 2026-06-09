# CredentialManager::DeleteCredentialInt(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001b3b4`
- end: `0x18001b559`
- name: `?DeleteCredentialInt@CredentialManager@@AEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x18001b238`
- `0x18001bdac`

## callees

- `0x18000195c`
- `0x1800032dc`
- `0x1800037d8`
- `0x1800062d4`
- `0x180010fdc`
- `0x1800195c8`
- `0x18001b3b4`
- `0x18001c648`
- `0x18001fe50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b478`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b478`
- `ADVAPI32!CredDeleteW` at `0x18001b46a`
- `ADVAPI32!CredDeleteW` at `0x18001b46a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CredentialManager::DeleteCredentialInt(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  __int64 v3; // rbx
  __int64 v4; // rbx
  unsigned int v5; // eax
  const WCHAR *v6; // rcx
  DWORD LastError; // eax
  DWORD v8; // edi
  __int64 v9; // [rsp+20h] [rbp-19h] BYREF
  void **pExceptionObject; // [rsp+28h] [rbp-11h] BYREF
  char v11; // [rsp+30h] [rbp-9h]
  const char *v12; // [rsp+38h] [rbp-1h]
  __int64 v13; // [rsp+40h] [rbp+7h]
  __int64 v14; // [rsp+48h] [rbp+Fh]
  DWORD v15; // [rsp+50h] [rbp+17h]
  int v16; // [rsp+54h] [rbp+1Bh]
  int v17; // [rsp+58h] [rbp+1Fh]
  _QWORD v18[4]; // [rsp+60h] [rbp+27h] BYREF

  result = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
             a1,
             &v9,
             a2);
  v3 = v9;
  if ( v9 != g_credMgr )
  {
    std::wstring::wstring(v18, v9 + 64);
    std::_Tree<std::_Tmap_traits<std::wstring,CredentialManager::EntryInformation,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,CredentialManager::EntryInformation>>,0>>::erase(
      &g_credMgr,
      &v9,
      v3);
    std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(
      &xmmword_18002F7D0,
      &v9,
      v18);
    v4 = v9;
    if ( v9 != (_QWORD)xmmword_18002F7D0 )
    {
      v5 = *(_DWORD *)(v9 + 96);
      if ( v5 <= 1 )
      {
        *(_DWORD *)(v9 + 96) = 0;
        v6 = (const WCHAR *)(v4 + 32);
        if ( *(_QWORD *)(v4 + 56) >= 8u )
          v6 = *(const WCHAR **)v6;
        if ( !CredDeleteW(v6, 1u, 0) )
        {
          LastError = GetLastError();
          v8 = LastError;
          if ( LastError )
          {
            if ( LastError != 1168 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_D(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  26,
                  &WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids,
                  LastError);
              }
              v11 = 0;
              v12 = "admin\\wmi\\events\\forwarding\\collector\\store\\credentialmanager.cpp";
              v13 = 0;
              v14 = 0;
              v15 = v8;
              v16 = -1;
              v17 = 387;
              pExceptionObject = &wmi::GenericException::`vftable';
              throw (wmi::GenericException *)&pExceptionObject;
            }
          }
        }
        std::_Tree<std::_Tmap_traits<std::wstring,CredentialManager::EntryInformation,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,CredentialManager::EntryInformation>>,0>>::erase(
          &xmmword_18002F7D0,
          &v9,
          v4);
      }
      else
      {
        *(_DWORD *)(v9 + 96) = v5 - 1;
      }
    }
    return std::wstring::_Tidy(v18, 1, 0);
  }
  return result;
}

```

## disassembly

```asm
0x18001b3b4  mov     [rsp-8+arg_0], rbx
0x18001b3b9  mov     [rsp-8+arg_10], rdi
0x18001b3be  push    rbp
0x18001b3bf  lea     rbp, [rsp-57h]
0x18001b3c4  sub     rsp, 90h
0x18001b3cb  mov     rax, cs:__security_cookie
0x18001b3d2  xor     rax, rsp
0x18001b3d5  mov     [rbp+57h+var_10], rax
0x18001b3d9  mov     r8, rdx
0x18001b3dc  lea     rdx, [rbp+57h+var_70]
0x18001b3e0  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@Uwstring_iless@CredentialManager@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x18001b3e5  mov     rbx, [rbp+57h+var_70]
0x18001b3e9  cmp     rbx, cs:?g_credMgr@@3VCredentialManager@@A; CredentialManager g_credMgr
0x18001b3f0  jz      loc_18001B538
0x18001b3f6  lea     rdx, [rbx+40h]
0x18001b3fa  lea     rcx, [rbp+57h+var_30]
0x18001b3fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b403  nop
0x18001b404  mov     r8, rbx
0x18001b407  lea     rdx, [rbp+57h+var_70]
0x18001b40b  lea     rcx, ?g_credMgr@@3VCredentialManager@@A; CredentialManager g_credMgr
0x18001b412  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@Uwstring_iless@4@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CredentialManager::EntryInformation,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,CredentialManager::EntryInformation>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CredentialManager::EntryInformation>>>>)
0x18001b417  lea     r8, [rbp+57h+var_30]
0x18001b41b  lea     rdx, [rbp+57h+var_70]
0x18001b41f  lea     rcx, xmmword_18002F7D0
0x18001b426  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@VCaseInsensitiveLess@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$AutoRef@VSubscription@@@wmi@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,wmi::AutoRef<Subscription>,CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,wmi::AutoRef<Subscription>>>,0>>::find(std::wstring const &)
0x18001b42b  mov     rbx, [rbp+57h+var_70]
0x18001b42f  cmp     rbx, qword ptr cs:xmmword_18002F7D0
0x18001b436  jz      loc_18001B52A
0x18001b43c  mov     eax, [rbx+60h]
0x18001b43f  cmp     eax, 1
0x18001b442  jbe     short loc_18001B44E
0x18001b444  dec     eax
0x18001b446  mov     [rbx+60h], eax
0x18001b449  jmp     loc_18001B52A
0x18001b44e  mov     dword ptr [rbx+60h], 0
0x18001b455  lea     rcx, [rbx+20h]
0x18001b459  cmp     qword ptr [rcx+18h], 8
0x18001b45e  jb      short loc_18001B463
0x18001b460  mov     rcx, [rcx]; TargetName
0x18001b463  xor     r8d, r8d; Flags
0x18001b466  lea     edx, [r8+1]; Type
0x18001b46a  call    cs:__imp_CredDeleteW
0x18001b470  test    eax, eax
0x18001b472  jnz     loc_18001B516
0x18001b478  call    cs:__imp_GetLastError
0x18001b47e  mov     edi, eax
0x18001b480  test    eax, eax
0x18001b482  jz      loc_18001B516
0x18001b488  cmp     eax, 490h
0x18001b48d  jz      loc_18001B516
0x18001b493  lea     rax, WPP_GLOBAL_Control
0x18001b49a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b4a1  cmp     rcx, rax
0x18001b4a4  jz      short loc_18001B4CA
0x18001b4a6  test    byte ptr [rcx+1Ch], 40h
0x18001b4aa  jz      short loc_18001B4CA
0x18001b4ac  cmp     byte ptr [rcx+19h], 2
0x18001b4b0  jb      short loc_18001B4CA
0x18001b4b2  mov     edx, 1Ah
0x18001b4b7  mov     r9d, edi
0x18001b4ba  lea     r8, WPP_3b54ed34bb4835de3895f7d36279b99a_Traceguids
0x18001b4c1  mov     rcx, [rcx+10h]
0x18001b4c5  call    WPP_SF_D
0x18001b4ca  mov     [rbp+57h+var_60], 0
0x18001b4ce  lea     rax, aAdminWmiEvents_9; "admin\\wmi\\events\\forwarding\\collect"...
0x18001b4d5  mov     [rbp+57h+var_58], rax
0x18001b4d9  mov     [rbp+57h+var_50], 0
0x18001b4e1  mov     [rbp+57h+var_48], 0
0x18001b4e9  mov     [rbp+57h+var_40], edi
0x18001b4ec  mov     [rbp+57h+var_3C], 0FFFFFFFFh
0x18001b4f3  mov     [rbp+57h+var_38], 183h
0x18001b4fa  lea     rax, ??_7GenericException@wmi@@6B@; const wmi::GenericException::`vftable'
0x18001b501  mov     [rbp+57h+pExceptionObject], rax
0x18001b505  lea     rdx, _TI3?AVGenericException@wmi@@; pThrowInfo
0x18001b50c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001b510  call    _CxxThrowException_0
0x18001b516  mov     r8, rbx
0x18001b519  lea     rdx, [rbp+57h+var_70]
0x18001b51d  lea     rcx, xmmword_18002F7D0
0x18001b524  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@Uwstring_iless@4@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UEntryInformation@CredentialManager@@@std@@@std@@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,CredentialManager::EntryInformation,CredentialManager::wstring_iless,std::allocator<std::pair<std::wstring const,CredentialManager::EntryInformation>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CredentialManager::EntryInformation>>>>)
0x18001b529  nop
0x18001b52a  xor     r8d, r8d
0x18001b52d  mov     dl, 1
0x18001b52f  lea     rcx, [rbp+57h+var_30]
0x18001b533  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001b538  mov     rcx, [rbp+57h+var_10]
0x18001b53c  xor     rcx, rsp; StackCookie
0x18001b53f  call    __security_check_cookie
0x18001b544  lea     r11, [rsp+90h+var_s0]
0x18001b54c  mov     rbx, [r11+10h]
0x18001b550  mov     rdi, [r11+20h]
0x18001b554  mov     rsp, r11
0x18001b557  pop     rbp
0x18001b558  retn
```
