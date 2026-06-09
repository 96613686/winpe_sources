# WcmConnectionSelectionByDeviceType::WriteToRegistry(ATL::CRegKey &)

- ea: `0x18001b770`
- end: `0x18001b94d`
- name: `?WriteToRegistry@WcmConnectionSelectionByDeviceType@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `477`
- prototype: `int(WcmConnectionSelectionByDeviceType *__hidden this, struct ATL::CRegKey *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180007a70`
- `0x180008a90`
- `0x18001728c`
- `0x1800189d8`
- `0x180018ac0`
- `0x180018d84`
- `0x180018f18`
- `0x18001a9b0`
- `0x18001b770`

## string_xrefs

- `0x18001b7bc`: `WcmConnectionSelectionByDeviceType::WriteToRegistry`
- `0x18001b905`: `WcmConnectionSelectionByDeviceType::WriteToRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmConnectionSelectionByDeviceType::WriteToRegistry(
        WcmConnectionSelectionByDeviceType *this,
        HKEY *a2)
{
  int v4; // ebx
  WcmPolicyManager *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  const BYTE *v9; // rax
  LSTATUS v10; // edi
  _BYTE v12[32]; // [rsp+38h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids,
      "WcmConnectionSelectionByDeviceType::WriteToRegistry");
  }
  std::wstring::wstring(v12);
  v4 = ATL::CRegKey::SetDWORDValue(a2, L"SelectionType", *((_DWORD *)this + 2));
  if ( v4 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"SelectionType");
      v5 = WPP_GLOBAL_Control;
    }
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    try
    {
      v4 = GuidToString((char *)this + 16, v12);
      if ( v4 >= 0
        && (v9 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12, v6, v7, v8),
            (v10 = ATL::CRegKey::SetStringValue(a2, L"ConnectionDeviceType", v9)) != 0) )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25)
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionDeviceType");
          v5 = WPP_GLOBAL_Control;
        }
        if ( v10 > 0 )
          v4 = (unsigned __int16)v10 | 0x80070000;
        else
          v4 = v10;
      }
      else
      {
        v5 = WPP_GLOBAL_Control;
      }
    }
    catch ( std::bad_alloc )
    {
      v4 = -2147024882;
      v5 = WPP_GLOBAL_Control;
    }
  }
  if ( v5 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 5u && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v5 + 2),
      13,
      (unsigned int)WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids,
      (unsigned int)"WcmConnectionSelectionByDeviceType::WriteToRegistry",
      v4);
  std::wstring::_Tidy_deallocate(v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001b770  mov     [rsp+arg_10], rbx
0x18001b775  mov     [rsp+arg_18], rsi
0x18001b77a  push    rdi
0x18001b77b  push    r14
0x18001b77d  push    r15
0x18001b77f  sub     rsp, 60h
0x18001b783  mov     rax, cs:__security_cookie
0x18001b78a  xor     rax, rsp
0x18001b78d  mov     [rsp+78h+var_20], rax
0x18001b792  mov     r14, rdx
0x18001b795  mov     rdi, rcx
0x18001b798  lea     rsi, WPP_GLOBAL_Control
0x18001b79f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7a6  cmp     rcx, rsi
0x18001b7a9  jz      short loc_18001B7D3
0x18001b7ab  cmp     byte ptr [rcx+19h], 5
0x18001b7af  jb      short loc_18001B7D3
0x18001b7b1  test    byte ptr [rcx+1Ch], 1
0x18001b7b5  jz      short loc_18001B7D3
0x18001b7b7  mov     edx, 0Ah
0x18001b7bc  lea     r9, aWcmconnections_0; "WcmConnectionSelectionByDeviceType::Wri"...
0x18001b7c3  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b7ca  mov     rcx, [rcx+10h]
0x18001b7ce  call    WPP_SF_s
0x18001b7d3  lea     rcx, [rsp+78h+var_40]
0x18001b7d8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b7dd  nop
0x18001b7de  mov     r8d, [rdi+8]; unsigned int
0x18001b7e2  lea     r15, ?c_szConnectionSelection_SelectionTypeRegKey@@3QBGB; "SelectionType"
0x18001b7e9  mov     rdx, r15; unsigned __int16 *
0x18001b7ec  mov     rcx, r14; this
0x18001b7ef  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001b7f4  mov     ebx, eax
0x18001b7f6  test    eax, eax
0x18001b7f8  jz      short loc_18001B848
0x18001b7fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b801  cmp     rcx, rsi
0x18001b804  jz      short loc_18001B836
0x18001b806  cmp     byte ptr [rcx+19h], 1
0x18001b80a  jb      short loc_18001B836
0x18001b80c  test    byte ptr [rcx+1Ch], 1
0x18001b810  jz      short loc_18001B836
0x18001b812  mov     edx, 0Bh
0x18001b817  mov     [rsp+78h+var_58], r15; __int64
0x18001b81c  mov     r9d, eax
0x18001b81f  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b826  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b82a  call    WPP_SF_DS
0x18001b82f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b836  test    ebx, ebx
0x18001b838  jle     short loc_18001B843
0x18001b83a  movzx   ebx, bx
0x18001b83d  or      ebx, 80070000h
0x18001b843  jmp     loc_18001B8EB
0x18001b848  lea     rcx, [rdi+10h]
0x18001b84c  lea     rdx, [rsp+78h+var_40]
0x18001b851  call    ?GuidToString@@YAJAEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GuidToString(_GUID &,std::wstring &)
0x18001b856  mov     ebx, eax
0x18001b858  test    eax, eax
0x18001b85a  js      short loc_18001B8D0
0x18001b85c  lea     rcx, [rsp+78h+var_40]
0x18001b861  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001b866  mov     r8, rax; unsigned __int16 *
0x18001b869  lea     r15, ?c_szConnectionSelection_ConnectionDeviceTypeRegKey@@3QBGB; "ConnectionDeviceType"
0x18001b870  mov     rdx, r15; unsigned __int16 *
0x18001b873  mov     rcx, r14; this
0x18001b876  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001b87b  mov     edi, eax
0x18001b87d  test    eax, eax
0x18001b87f  jz      short loc_18001B8D0
0x18001b881  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b888  cmp     rcx, rsi
0x18001b88b  jz      short loc_18001B8BD
0x18001b88d  cmp     byte ptr [rcx+19h], 1
0x18001b891  jb      short loc_18001B8BD
0x18001b893  test    byte ptr [rcx+1Ch], 1
0x18001b897  jz      short loc_18001B8BD
0x18001b899  mov     edx, 0Ch
0x18001b89e  mov     [rsp+78h+var_58], r15; __int64
0x18001b8a3  mov     r9d, eax
0x18001b8a6  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b8ad  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b8b1  call    WPP_SF_DS
0x18001b8b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8bd  test    edi, edi
0x18001b8bf  jg      short loc_18001B8C5
0x18001b8c1  mov     ebx, edi
0x18001b8c3  jmp     short loc_18001B8D7
0x18001b8c5  movzx   ebx, di
0x18001b8c8  or      ebx, 80070000h
0x18001b8ce  jmp     short loc_18001B8D7
0x18001b8d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8d7  jmp     short loc_18001B8EB
0x18001b8d9  lea     rsi, WPP_GLOBAL_Control
0x18001b8e0  mov     ebx, [rsp+78h+var_48]
0x18001b8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8eb  cmp     rcx, rsi
0x18001b8ee  jz      short loc_18001B91D
0x18001b8f0  cmp     byte ptr [rcx+19h], 5
0x18001b8f4  jb      short loc_18001B91D
0x18001b8f6  test    byte ptr [rcx+1Ch], 1
0x18001b8fa  jz      short loc_18001B91D
0x18001b8fc  mov     edx, 0Dh
0x18001b901  mov     dword ptr [rsp+78h+var_58], ebx
0x18001b905  lea     r9, aWcmconnections_0; "WcmConnectionSelectionByDeviceType::Wri"...
0x18001b90c  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b913  mov     rcx, [rcx+10h]
0x18001b917  call    WPP_SF_sL
0x18001b91c  nop
0x18001b91d  lea     rcx, [rsp+78h+var_40]
0x18001b922  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b927  mov     eax, ebx
0x18001b929  mov     rcx, [rsp+78h+var_20]
0x18001b92e  xor     rcx, rsp; StackCookie
0x18001b931  call    __security_check_cookie
0x18001b936  lea     r11, [rsp+78h+var_18]
0x18001b93b  mov     rbx, [r11+30h]
0x18001b93f  mov     rsi, [r11+38h]
0x18001b943  mov     rsp, r11
0x18001b946  pop     r15
0x18001b948  pop     r14
0x18001b94a  pop     rdi
0x18001b94b  retn
```
