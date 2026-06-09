# WcmConnectionSelectionByConnectionType::ReadFromRegistry(ATL::CRegKey &)

- ea: `0x18001bcc0`
- end: `0x18001be24`
- name: `?ReadFromRegistry@WcmConnectionSelectionByConnectionType@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `356`
- prototype: `int(WcmConnectionSelectionByConnectionType *__hidden this, struct ATL::CRegKey *)`
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
- `0x18001bcc0`

## string_xrefs

- `0x18001bd09`: `WcmConnectionSelectionByConnectionType::ReadFromRegistry`
- `0x18001bdde`: `WcmConnectionSelectionByConnectionType::ReadFromRegistry`

## pseudocode

```c
__int64 __fastcall WcmConnectionSelectionByConnectionType::ReadFromRegistry(
        WcmConnectionSelectionByConnectionType *this,
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
      WPP_888260725c323bca86ac07eff46ed3c7_Traceguids,
      "WcmConnectionSelectionByConnectionType::ReadFromRegistry");
  }
  std::wstring::wstring(v9);
  StringValue = QueryStringValue(a2, L"ConnectionType");
  if ( StringValue )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionType");
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
      (unsigned int)WPP_888260725c323bca86ac07eff46ed3c7_Traceguids,
      (unsigned int)"WcmConnectionSelectionByConnectionType::ReadFromRegistry",
      StringValue);
  std::wstring::_Tidy_deallocate(v9);
  return (unsigned int)StringValue;
}

```

## disassembly

```asm
0x18001bcc0  mov     [rsp+arg_10], rbx
0x18001bcc5  push    rsi
0x18001bcc6  push    rdi
0x18001bcc7  push    r14
0x18001bcc9  sub     rsp, 80h
0x18001bcd0  mov     rax, cs:__security_cookie
0x18001bcd7  xor     rax, rsp
0x18001bcda  mov     [rsp+98h+var_20], rax
0x18001bcdf  mov     rbx, rdx
0x18001bce2  mov     rsi, rcx
0x18001bce5  lea     rdi, WPP_GLOBAL_Control
0x18001bcec  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bcf3  cmp     rcx, rdi
0x18001bcf6  jz      short loc_18001BD20
0x18001bcf8  cmp     byte ptr [rcx+19h], 5
0x18001bcfc  jb      short loc_18001BD20
0x18001bcfe  test    byte ptr [rcx+1Ch], 1
0x18001bd02  jz      short loc_18001BD20
0x18001bd04  mov     edx, 0Eh
0x18001bd09  lea     r9, aWcmconnections_5; "WcmConnectionSelectionByConnectionType:"...
0x18001bd10  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001bd17  mov     rcx, [rcx+10h]
0x18001bd1b  call    WPP_SF_s
0x18001bd20  lea     rcx, [rsp+98h+var_40]
0x18001bd25  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001bd2a  nop
0x18001bd2b  lea     r8, [rsp+98h+var_40]
0x18001bd30  lea     r14, ?c_szConnectionSelection_ConnectionTypeRegKey@@3QBGB; "ConnectionType"
0x18001bd37  mov     rdx, r14; unsigned __int16 *
0x18001bd3a  mov     rcx, rbx; this
0x18001bd3d  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x18001bd42  mov     ebx, eax
0x18001bd44  test    eax, eax
0x18001bd46  jz      short loc_18001BD93
0x18001bd48  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd4f  cmp     rcx, rdi
0x18001bd52  jz      short loc_18001BD84
0x18001bd54  cmp     byte ptr [rcx+19h], 1
0x18001bd58  jb      short loc_18001BD84
0x18001bd5a  test    byte ptr [rcx+1Ch], 1
0x18001bd5e  jz      short loc_18001BD84
0x18001bd60  mov     edx, 0Fh
0x18001bd65  mov     [rsp+98h+var_78], r14; __int64
0x18001bd6a  mov     r9d, eax
0x18001bd6d  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001bd74  mov     rcx, [rcx+10h]; LoggerHandle
0x18001bd78  call    WPP_SF_DS
0x18001bd7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bd84  test    ebx, ebx
0x18001bd86  jle     short loc_18001BD91
0x18001bd88  movzx   ebx, bx
0x18001bd8b  or      ebx, 80070000h
0x18001bd91  jmp     short loc_18001BDC4
0x18001bd93  lea     rdx, [rsp+98h+var_40]
0x18001bd98  lea     rcx, [rsp+98h+var_60]
0x18001bd9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001bda2  lea     rdx, [rsi+10h]
0x18001bda6  mov     rcx, rax
0x18001bda9  call    ?StringToGuid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; StringToGuid(std::wstring,_GUID &)
0x18001bdae  mov     ebx, eax
0x18001bdb0  jmp     short loc_18001BDBD
0x18001bdb2  lea     rdi, WPP_GLOBAL_Control
0x18001bdb9  mov     ebx, [rsp+98h+var_68]
0x18001bdbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bdc4  cmp     rcx, rdi
0x18001bdc7  jz      short loc_18001BDF6
0x18001bdc9  cmp     byte ptr [rcx+19h], 5
0x18001bdcd  jb      short loc_18001BDF6
0x18001bdcf  test    byte ptr [rcx+1Ch], 1
0x18001bdd3  jz      short loc_18001BDF6
0x18001bdd5  mov     edx, 10h
0x18001bdda  mov     dword ptr [rsp+98h+var_78], ebx
0x18001bdde  lea     r9, aWcmconnections_5; "WcmConnectionSelectionByConnectionType:"...
0x18001bde5  lea     r8, WPP_888260725c323bca86ac07eff46ed3c7_Traceguids
0x18001bdec  mov     rcx, [rcx+10h]
0x18001bdf0  call    WPP_SF_sL
0x18001bdf5  nop
0x18001bdf6  lea     rcx, [rsp+98h+var_40]
0x18001bdfb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001be00  mov     eax, ebx
0x18001be02  mov     rcx, [rsp+98h+var_20]
0x18001be07  xor     rcx, rsp; StackCookie
0x18001be0a  call    __security_check_cookie
0x18001be0f  mov     rbx, [rsp+98h+arg_10]
0x18001be17  add     rsp, 80h
0x18001be1e  pop     r14
0x18001be20  pop     rdi
0x18001be21  pop     rsi
0x18001be22  retn
```
