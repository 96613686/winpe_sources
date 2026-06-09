# WcmConnectionSelectionByConnectionType::WriteToRegistry(ATL::CRegKey &)

- ea: `0x18001be50`
- end: `0x18001c02d`
- name: `?WriteToRegistry@WcmConnectionSelectionByConnectionType@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `477`
- prototype: `int(WcmConnectionSelectionByConnectionType *__hidden this, struct ATL::CRegKey *)`
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
- `0x18001be50`

## string_xrefs

- `0x18001be9c`: `WcmConnectionSelectionByConnectionType::WriteToRegistry`
- `0x18001bfe5`: `WcmConnectionSelectionByConnectionType::WriteToRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByConnectionType::WriteToRegistry(
        WcmConnectionSelectionByConnectionType *this,
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
      WPP_888260725c323bca86ac07eff46ed3c7_Traceguids,
      "WcmConnectionSelectionByConnectionType::WriteToRegistry");
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
          (v10 = ATL::CRegKey::SetStringValue(a2, L"ConnectionType", v9)) != 0) )
    {
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25)
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionType");
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
      (unsigned int)WPP_888260725c323bca86ac07eff46ed3c7_Traceguids,
      (unsigned int)"WcmConnectionSelectionByConnectionType::WriteToRegistry",
      v4);
  std::wstring::_Tidy_deallocate(v12);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001be50  mov     [rsp+arg_10], rbx
0x18001be55  mov     [rsp+arg_18], rsi
0x18001be5a  push    rdi
0x18001be5b  push    r14
0x18001be5d  push    r15
0x18001be5f  sub     rsp, 60h
0x18001be63  mov     rax, cs:__security_cookie
0x18001be6a  xor     rax, rsp
0x18001be6d  mov     [rsp+78h+var_20], rax
0x18001be72  mov     r14, rdx
0x18001be75  mov     rdi, rcx
0x18001be78  lea     rsi, WPP_GLOBAL_Control
0x18001be7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be86  cmp     rcx, rsi
0x18001be89  jz      short loc_18001BEB3
0x18001be8b  cmp     byte ptr [rcx+19h], 5
0x18001be8f  jb      short loc_18001BEB3
0x18001be91  test    byte ptr [rcx+1Ch], 1
0x18001be95  jz      short loc_18001BEB3
0x18001be97  mov     edx, 0Ah
0x18001be9c  lea     r9, aWcmconnections_1; "WcmConnectionSelectionByConnectionType:"...
0x18001bea3  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001beaa  mov     rcx, [rcx+10h]
0x18001beae  call    WPP_SF_s
0x18001beb3  lea     rcx, [rsp+78h+var_40]
0x18001beb8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001bebd  nop
0x18001bebe  mov     r8d, [rdi+8]; unsigned int
0x18001bec2  lea     r15, ?c_szConnectionSelection_SelectionTypeRegKey@@3QBGB; "SelectionType"
0x18001bec9  mov     rdx, r15; unsigned __int16 *
0x18001becc  mov     rcx, r14; this
0x18001becf  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x18001bed4  mov     ebx, eax
0x18001bed6  test    eax, eax
0x18001bed8  jz      short loc_18001BF28
0x18001beda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bee1  cmp     rcx, rsi
0x18001bee4  jz      short loc_18001BF16
0x18001bee6  cmp     byte ptr [rcx+19h], 1
0x18001beea  jb      short loc_18001BF16
0x18001beec  test    byte ptr [rcx+1Ch], 1
0x18001bef0  jz      short loc_18001BF16
0x18001bef2  mov     edx, 0Bh
0x18001bef7  mov     [rsp+78h+var_58], r15; __int64
0x18001befc  mov     r9d, eax
0x18001beff  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001bf06  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bf0a  call    WPP_SF_DS
0x18001bf0f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf16  test    ebx, ebx
0x18001bf18  jle     short loc_18001BF23
0x18001bf1a  movzx   ebx, bx
0x18001bf1d  or      ebx, 80070000h
0x18001bf23  jmp     loc_18001BFCB
0x18001bf28  lea     rcx, [rdi+10h]
0x18001bf2c  lea     rdx, [rsp+78h+var_40]
0x18001bf31  call    ?GuidToString@@YAJAEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GuidToString(_GUID &,std::wstring &)
0x18001bf36  mov     ebx, eax
0x18001bf38  test    eax, eax
0x18001bf3a  js      short loc_18001BFB0
0x18001bf3c  lea     rcx, [rsp+78h+var_40]
0x18001bf41  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bf46  mov     r8, rax; unsigned __int16 *
0x18001bf49  lea     r15, ?c_szConnectionSelection_ConnectionTypeRegKey@@3QBGB; "ConnectionType"
0x18001bf50  mov     rdx, r15; unsigned __int16 *
0x18001bf53  mov     rcx, r14; this
0x18001bf56  call    ?SetStringValue@CRegKey@ATL@@QEAAJPEBG0K@Z; ATL::CRegKey::SetStringValue(ushort const *,ushort const *,ulong)
0x18001bf5b  mov     edi, eax
0x18001bf5d  test    eax, eax
0x18001bf5f  jz      short loc_18001BFB0
0x18001bf61  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf68  cmp     rcx, rsi
0x18001bf6b  jz      short loc_18001BF9D
0x18001bf6d  cmp     byte ptr [rcx+19h], 1
0x18001bf71  jb      short loc_18001BF9D
0x18001bf73  test    byte ptr [rcx+1Ch], 1
0x18001bf77  jz      short loc_18001BF9D
0x18001bf79  mov     edx, 0Ch
0x18001bf7e  mov     [rsp+78h+var_58], r15; __int64
0x18001bf83  mov     r9d, eax
0x18001bf86  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001bf8d  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bf91  call    WPP_SF_DS
0x18001bf96  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bf9d  test    edi, edi
0x18001bf9f  jg      short loc_18001BFA5
0x18001bfa1  mov     ebx, edi
0x18001bfa3  jmp     short loc_18001BFB7
0x18001bfa5  movzx   ebx, di
0x18001bfa8  or      ebx, 80070000h
0x18001bfae  jmp     short loc_18001BFB7
0x18001bfb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfb7  jmp     short loc_18001BFCB
0x18001bfb9  lea     rsi, WPP_GLOBAL_Control
0x18001bfc0  mov     ebx, [rsp+78h+var_48]
0x18001bfc4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bfcb  cmp     rcx, rsi
0x18001bfce  jz      short loc_18001BFFD
0x18001bfd0  cmp     byte ptr [rcx+19h], 5
0x18001bfd4  jb      short loc_18001BFFD
0x18001bfd6  test    byte ptr [rcx+1Ch], 1
0x18001bfda  jz      short loc_18001BFFD
0x18001bfdc  mov     edx, 0Dh
0x18001bfe1  mov     dword ptr [rsp+78h+var_58], ebx
0x18001bfe5  lea     r9, aWcmconnections_1; "WcmConnectionSelectionByConnectionType:"...
0x18001bfec  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001bff3  mov     rcx, [rcx+10h]
0x18001bff7  call    WPP_SF_sL
0x18001bffc  nop
0x18001bffd  lea     rcx, [rsp+78h+var_40]
0x18001c002  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c007  mov     eax, ebx
0x18001c009  mov     rcx, [rsp+78h+var_20]
0x18001c00e  xor     rcx, rsp; StackCookie
0x18001c011  call    __security_check_cookie
0x18001c016  lea     r11, [rsp+78h+var_18]
0x18001c01b  mov     rbx, [r11+30h]
0x18001c01f  mov     rsi, [r11+38h]
0x18001c023  mov     rsp, r11
0x18001c026  pop     r15
0x18001c028  pop     r14
0x18001c02a  pop     rdi
0x18001c02b  retn
```
