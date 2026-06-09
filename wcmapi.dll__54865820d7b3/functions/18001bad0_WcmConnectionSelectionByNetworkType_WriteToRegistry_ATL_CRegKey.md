# WcmConnectionSelectionByNetworkType::WriteToRegistry(ATL::CRegKey &)

- ea: `0x18001bad0`
- end: `0x18001bcad`
- name: `?WriteToRegistry@WcmConnectionSelectionByNetworkType@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `477`
- prototype: `int(WcmConnectionSelectionByNetworkType *__hidden this, struct ATL::CRegKey *)`
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
- `0x18001bad0`

## string_xrefs

- `0x18001bb1c`: `WcmConnectionSelectionByNetworkType::WriteToRegistry`
- `0x18001bc65`: `WcmConnectionSelectionByNetworkType::WriteToRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByNetworkType::WriteToRegistry(
        WcmConnectionSelectionByNetworkType *this,
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
      WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids,
      "WcmConnectionSelectionByNetworkType::WriteToRegistry");
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
    v4 = GuidToString((char *)this + 16, v12);
    if ( v4 >= 0
      && (v9 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12, v6, v7, v8),
          (v10 = ATL::CRegKey::SetStringValue(a2, L"ConnectionNetworkType", v9)) != 0) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionNetworkType");
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
  if ( v5 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 5u && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v5 + 2),
      13,
      (unsigned int)WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids,
      (unsigned int)"WcmConnectionSelectionByNetworkType::WriteToRegistry",
      v4);
  std::wstring::_Tidy_deallocate(v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001bad0  mov     [rsp+arg_10], rbx
0x18001bad5  mov     [rsp+arg_18], rsi
0x18001bada  push    rdi
0x18001badb  push    r14
0x18001badd  push    r15
0x18001badf  sub     rsp, 60h
0x18001bae3  mov     rax, cs:__security_cookie
0x18001baea  xor     rax, rsp
0x18001baed  mov     [rsp+78h+var_20], rax
0x18001baf2  mov     r14, rdx
0x18001baf5  mov     rdi, rcx
0x18001baf8  lea     rsi, WPP_GLOBAL_Control
0x18001baff  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb06  cmp     rcx, rsi
0x18001bb09  jz      short loc_18001BB33
0x18001bb0b  cmp     byte ptr [rcx+19h], 5
0x18001bb0f  jb      short loc_18001BB33
0x18001bb11  test    byte ptr [rcx+1Ch], 1
0x18001bb15  jz      short loc_18001BB33
0x18001bb17  mov     edx, 0Ah
0x18001bb1c  lea     r9, aWcmconnections_6; "WcmConnectionSelectionByNetworkType::Wr"...
0x18001bb23  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001bb2a  mov     rcx, [rcx+10h]
0x18001bb2e  call    WPP_SF_s
0x18001bb33  lea     rcx, [rsp+78h+var_40]
0x18001bb38  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001bb3d  nop
0x18001bb3e  mov     r8d, [rdi+8]; unsigned int
0x18001bb42  lea     r15, ?c_szConnectionSelection_SelectionTypeRegKey@@3QBGB; "SelectionType"
0x18001bb49  mov     rdx, r15; unsigned __int16 *
0x18001bb4c  mov     rcx, r14; this
0x18001bb4f  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001bb54  mov     ebx, eax
0x18001bb56  test    eax, eax
0x18001bb58  jz      short loc_18001BBA8
0x18001bb5a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb61  cmp     rcx, rsi
0x18001bb64  jz      short loc_18001BB96
0x18001bb66  cmp     byte ptr [rcx+19h], 1
0x18001bb6a  jb      short loc_18001BB96
0x18001bb6c  test    byte ptr [rcx+1Ch], 1
0x18001bb70  jz      short loc_18001BB96
0x18001bb72  mov     edx, 0Bh
0x18001bb77  mov     [rsp+78h+var_58], r15; __int64
0x18001bb7c  mov     r9d, eax
0x18001bb7f  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001bb86  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bb8a  call    WPP_SF_DS
0x18001bb8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb96  test    ebx, ebx
0x18001bb98  jle     short loc_18001BBA3
0x18001bb9a  movzx   ebx, bx
0x18001bb9d  or      ebx, 80070000h
0x18001bba3  jmp     loc_18001BC4B
0x18001bba8  lea     rcx, [rdi+10h]
0x18001bbac  lea     rdx, [rsp+78h+var_40]
0x18001bbb1  call    ?GuidToString@@YAJAEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GuidToString(_GUID &,std::wstring &)
0x18001bbb6  mov     ebx, eax
0x18001bbb8  test    eax, eax
0x18001bbba  js      short loc_18001BC30
0x18001bbbc  lea     rcx, [rsp+78h+var_40]
0x18001bbc1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bbc6  mov     r8, rax; unsigned __int16 *
0x18001bbc9  lea     r15, ?c_szConnectionSelection_ConnectionNetworkTypeRegKey@@3QBGB; "ConnectionNetworkType"
0x18001bbd0  mov     rdx, r15; unsigned __int16 *
0x18001bbd3  mov     rcx, r14; this
0x18001bbd6  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001bbdb  mov     edi, eax
0x18001bbdd  test    eax, eax
0x18001bbdf  jz      short loc_18001BC30
0x18001bbe1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbe8  cmp     rcx, rsi
0x18001bbeb  jz      short loc_18001BC1D
0x18001bbed  cmp     byte ptr [rcx+19h], 1
0x18001bbf1  jb      short loc_18001BC1D
0x18001bbf3  test    byte ptr [rcx+1Ch], 1
0x18001bbf7  jz      short loc_18001BC1D
0x18001bbf9  mov     edx, 0Ch
0x18001bbfe  mov     [rsp+78h+var_58], r15; __int64
0x18001bc03  mov     r9d, eax
0x18001bc06  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001bc0d  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bc11  call    WPP_SF_DS
0x18001bc16  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc1d  test    edi, edi
0x18001bc1f  jg      short loc_18001BC25
0x18001bc21  mov     ebx, edi
0x18001bc23  jmp     short loc_18001BC37
0x18001bc25  movzx   ebx, di
0x18001bc28  or      ebx, 80070000h
0x18001bc2e  jmp     short loc_18001BC37
0x18001bc30  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc37  jmp     short loc_18001BC4B
0x18001bc39  lea     rsi, WPP_GLOBAL_Control
0x18001bc40  mov     ebx, [rsp+78h+var_48]
0x18001bc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc4b  cmp     rcx, rsi
0x18001bc4e  jz      short loc_18001BC7D
0x18001bc50  cmp     byte ptr [rcx+19h], 5
0x18001bc54  jb      short loc_18001BC7D
0x18001bc56  test    byte ptr [rcx+1Ch], 1
0x18001bc5a  jz      short loc_18001BC7D
0x18001bc5c  mov     edx, 0Dh
0x18001bc61  mov     dword ptr [rsp+78h+var_58], ebx
0x18001bc65  lea     r9, aWcmconnections_6; "WcmConnectionSelectionByNetworkType::Wr"...
0x18001bc6c  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001bc73  mov     rcx, [rcx+10h]
0x18001bc77  call    WPP_SF_sL
0x18001bc7c  nop
0x18001bc7d  lea     rcx, [rsp+78h+var_40]
0x18001bc82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bc87  mov     eax, ebx
0x18001bc89  mov     rcx, [rsp+78h+var_20]
0x18001bc8e  xor     rcx, rsp; StackCookie
0x18001bc91  call    __security_check_cookie
0x18001bc96  lea     r11, [rsp+78h+var_18]
0x18001bc9b  mov     rbx, [r11+30h]
0x18001bc9f  mov     rsi, [r11+38h]
0x18001bca3  mov     rsp, r11
0x18001bca6  pop     r15
0x18001bca8  pop     r14
0x18001bcaa  pop     rdi
0x18001bcab  retn
```
