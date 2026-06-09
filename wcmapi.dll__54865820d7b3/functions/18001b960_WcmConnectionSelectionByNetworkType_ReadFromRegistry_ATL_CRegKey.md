# WcmConnectionSelectionByNetworkType::ReadFromRegistry(ATL::CRegKey &)

- ea: `0x18001b960`
- end: `0x18001bac4`
- name: `?ReadFromRegistry@WcmConnectionSelectionByNetworkType@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `356`
- prototype: `int(WcmConnectionSelectionByNetworkType *__hidden this, struct ATL::CRegKey *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180004450`
- `0x1800044b0`
- `0x180007a70`
- `0x180008a90`
- `0x18001728c`
- `0x180018500`
- `0x180018f18`
- `0x18001ae30`
- `0x18001afcc`
- `0x18001b960`

## string_xrefs

- `0x18001b9a9`: `WcmConnectionSelectionByNetworkType::ReadFromRegistry`
- `0x18001ba7e`: `WcmConnectionSelectionByNetworkType::ReadFromRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByNetworkType::ReadFromRegistry(
        WcmConnectionSelectionByNetworkType *this,
        struct ATL::CRegKey *a2)
{
  signed int StringValue; // ebx
  WcmPolicyManager *v5; // rcx
  __int64 v6; // rax
  _BYTE v8[32]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v9[32]; // [rsp+58h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids,
      "WcmConnectionSelectionByNetworkType::ReadFromRegistry");
  }
  std::wstring::wstring(v9);
  StringValue = QueryStringValue(a2, L"ConnectionNetworkType");
  if ( StringValue )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionNetworkType");
      v5 = WPP_GLOBAL_Control;
    }
    if ( StringValue > 0 )
      StringValue = (unsigned __int16)StringValue | 0x80070000;
  }
  else
  {
    v6 = std::wstring::wstring(v8, v9);
    StringValue = StringToGuid(v6, (char *)this + 16);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v5 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v5 + 25) >= 5u && (*((_BYTE *)v5 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v5 + 2),
      16,
      (unsigned int)WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids,
      (unsigned int)"WcmConnectionSelectionByNetworkType::ReadFromRegistry",
      StringValue);
  std::wstring::_Tidy_deallocate(v9);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18001b960  mov     [rsp+arg_10], rbx
0x18001b965  push    rsi
0x18001b966  push    rdi
0x18001b967  push    r14
0x18001b969  sub     rsp, 80h
0x18001b970  mov     rax, cs:__security_cookie
0x18001b977  xor     rax, rsp
0x18001b97a  mov     [rsp+98h+var_20], rax
0x18001b97f  mov     rbx, rdx
0x18001b982  mov     rsi, rcx
0x18001b985  lea     rdi, WPP_GLOBAL_Control
0x18001b98c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b993  cmp     rcx, rdi
0x18001b996  jz      short loc_18001B9C0
0x18001b998  cmp     byte ptr [rcx+19h], 5
0x18001b99c  jb      short loc_18001B9C0
0x18001b99e  test    byte ptr [rcx+1Ch], 1
0x18001b9a2  jz      short loc_18001B9C0
0x18001b9a4  mov     edx, 0Eh
0x18001b9a9  lea     r9, aWcmconnections_3; "WcmConnectionSelectionByNetworkType::Re"...
0x18001b9b0  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001b9b7  mov     rcx, [rcx+10h]
0x18001b9bb  call    WPP_SF_s
0x18001b9c0  lea     rcx, [rsp+98h+var_40]
0x18001b9c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b9ca  nop
0x18001b9cb  lea     r8, [rsp+98h+var_40]
0x18001b9d0  lea     r14, ?c_szConnectionSelection_ConnectionNetworkTypeRegKey@@3QBGB; "ConnectionNetworkType"
0x18001b9d7  mov     rdx, r14; unsigned __int16 *
0x18001b9da  mov     rcx, rbx; this
0x18001b9dd  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x18001b9e2  mov     ebx, eax
0x18001b9e4  test    eax, eax
0x18001b9e6  jz      short loc_18001BA33
0x18001b9e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b9ef  cmp     rcx, rdi
0x18001b9f2  jz      short loc_18001BA24
0x18001b9f4  cmp     byte ptr [rcx+19h], 1
0x18001b9f8  jb      short loc_18001BA24
0x18001b9fa  test    byte ptr [rcx+1Ch], 1
0x18001b9fe  jz      short loc_18001BA24
0x18001ba00  mov     edx, 0Fh
0x18001ba05  mov     [rsp+98h+var_78], r14; __int64
0x18001ba0a  mov     r9d, eax
0x18001ba0d  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001ba14  mov     rcx, [rcx+10h]; LoggerHandle
0x18001ba18  call    WPP_SF_DS
0x18001ba1d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba24  test    ebx, ebx
0x18001ba26  jle     short loc_18001BA31
0x18001ba28  movzx   ebx, bx
0x18001ba2b  or      ebx, 80070000h
0x18001ba31  jmp     short loc_18001BA64
0x18001ba33  lea     rdx, [rsp+98h+var_40]
0x18001ba38  lea     rcx, [rsp+98h+var_60]
0x18001ba3d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ba42  lea     rdx, [rsi+10h]
0x18001ba46  mov     rcx, rax
0x18001ba49  call    ?StringToGuid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; StringToGuid(std::wstring,_GUID &)
0x18001ba4e  mov     ebx, eax
0x18001ba50  jmp     short loc_18001BA5D
0x18001ba52  lea     rdi, WPP_GLOBAL_Control
0x18001ba59  mov     ebx, [rsp+98h+var_68]
0x18001ba5d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba64  cmp     rcx, rdi
0x18001ba67  jz      short loc_18001BA96
0x18001ba69  cmp     byte ptr [rcx+19h], 5
0x18001ba6d  jb      short loc_18001BA96
0x18001ba6f  test    byte ptr [rcx+1Ch], 1
0x18001ba73  jz      short loc_18001BA96
0x18001ba75  mov     edx, 10h
0x18001ba7a  mov     dword ptr [rsp+98h+var_78], ebx
0x18001ba7e  lea     r9, aWcmconnections_3; "WcmConnectionSelectionByNetworkType::Re"...
0x18001ba85  lea     r8, WPP_2cc8bc73a7213448dc14543bf708c44c_Traceguids
0x18001ba8c  mov     rcx, [rcx+10h]
0x18001ba90  call    WPP_SF_sL
0x18001ba95  nop
0x18001ba96  lea     rcx, [rsp+98h+var_40]
0x18001ba9b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001baa0  mov     eax, ebx
0x18001baa2  mov     rcx, [rsp+98h+var_20]
0x18001baa7  xor     rcx, rsp; StackCookie
0x18001baaa  call    __security_check_cookie
0x18001baaf  mov     rbx, [rsp+98h+arg_10]
0x18001bab7  add     rsp, 80h
0x18001babe  pop     r14
0x18001bac0  pop     rdi
0x18001bac1  pop     rsi
0x18001bac2  retn
```
