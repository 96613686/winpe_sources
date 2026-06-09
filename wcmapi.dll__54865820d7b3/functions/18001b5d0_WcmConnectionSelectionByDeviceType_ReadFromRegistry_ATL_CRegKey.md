# WcmConnectionSelectionByDeviceType::ReadFromRegistry(ATL::CRegKey &)

- ea: `0x18001b5d0`
- end: `0x18001b734`
- name: `?ReadFromRegistry@WcmConnectionSelectionByDeviceType@@UEAAJAEAVCRegKey@ATL@@@Z`
- size: `356`
- prototype: `int(WcmConnectionSelectionByDeviceType *__hidden this, struct ATL::CRegKey *)`
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
- `0x18001b5d0`

## string_xrefs

- `0x18001b619`: `WcmConnectionSelectionByDeviceType::ReadFromRegistry`
- `0x18001b6ee`: `WcmConnectionSelectionByDeviceType::ReadFromRegistry`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WcmConnectionSelectionByDeviceType::ReadFromRegistry(
        WcmConnectionSelectionByDeviceType *this,
        struct ATL::CRegKey *a2)
{
  signed int StringValue; // eax
  signed int v5; // ebx
  WcmPolicyManager *v6; // rcx
  __int64 v7; // rax
  _BYTE v9[32]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v10[32]; // [rsp+58h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids,
      "WcmConnectionSelectionByDeviceType::ReadFromRegistry");
  }
  std::wstring::wstring(v10);
  try
  {
    StringValue = QueryStringValue(a2, L"ConnectionDeviceType");
  }
  catch ( std::bad_alloc )
  {
    v5 = -2147024882;
    goto LABEL_15;
  }
  v5 = StringValue;
  if ( StringValue )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25)
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)L"ConnectionDeviceType");
      v6 = WPP_GLOBAL_Control;
    }
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
  }
  else
  {
    v7 = std::wstring::wstring(v9, v10);
    v5 = StringToGuid(v7, (char *)this + 16);
LABEL_15:
    v6 = WPP_GLOBAL_Control;
  }
  if ( v6 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 5u && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v6 + 2),
      16,
      (unsigned int)WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids,
      (unsigned int)"WcmConnectionSelectionByDeviceType::ReadFromRegistry",
      v5);
  std::wstring::_Tidy_deallocate(v10);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001b5d0  mov     [rsp+arg_10], rbx
0x18001b5d5  push    rsi
0x18001b5d6  push    rdi
0x18001b5d7  push    r14
0x18001b5d9  sub     rsp, 80h
0x18001b5e0  mov     rax, cs:__security_cookie
0x18001b5e7  xor     rax, rsp
0x18001b5ea  mov     [rsp+98h+var_20], rax
0x18001b5ef  mov     rbx, rdx
0x18001b5f2  mov     rsi, rcx
0x18001b5f5  lea     rdi, WPP_GLOBAL_Control
0x18001b5fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b603  cmp     rcx, rdi
0x18001b606  jz      short loc_18001B630
0x18001b608  cmp     byte ptr [rcx+19h], 5
0x18001b60c  jb      short loc_18001B630
0x18001b60e  test    byte ptr [rcx+1Ch], 1
0x18001b612  jz      short loc_18001B630
0x18001b614  mov     edx, 0Eh
0x18001b619  lea     r9, aWcmconnections; "WcmConnectionSelectionByDeviceType::Rea"...
0x18001b620  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b627  mov     rcx, [rcx+10h]
0x18001b62b  call    WPP_SF_s
0x18001b630  lea     rcx, [rsp+98h+var_40]
0x18001b635  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001b63a  nop
0x18001b63b  lea     r8, [rsp+98h+var_40]
0x18001b640  lea     r14, ?c_szConnectionSelection_ConnectionDeviceTypeRegKey@@3QBGB; "ConnectionDeviceType"
0x18001b647  mov     rdx, r14; unsigned __int16 *
0x18001b64a  mov     rcx, rbx; this
0x18001b64d  call    ?QueryStringValue@@YAKAEAVCRegKey@ATL@@PEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; QueryStringValue(ATL::CRegKey &,ushort const *,std::wstring &)
0x18001b652  mov     ebx, eax
0x18001b654  test    eax, eax
0x18001b656  jz      short loc_18001B6A3
0x18001b658  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b65f  cmp     rcx, rdi
0x18001b662  jz      short loc_18001B694
0x18001b664  cmp     byte ptr [rcx+19h], 1
0x18001b668  jb      short loc_18001B694
0x18001b66a  test    byte ptr [rcx+1Ch], 1
0x18001b66e  jz      short loc_18001B694
0x18001b670  mov     edx, 0Fh
0x18001b675  mov     [rsp+98h+var_78], r14; __int64
0x18001b67a  mov     r9d, eax
0x18001b67d  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b684  mov     rcx, [rcx+10h]; LoggerHandle
0x18001b688  call    WPP_SF_DS
0x18001b68d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b694  test    ebx, ebx
0x18001b696  jle     short loc_18001B6A1
0x18001b698  movzx   ebx, bx
0x18001b69b  or      ebx, 80070000h
0x18001b6a1  jmp     short loc_18001B6D4
0x18001b6a3  lea     rdx, [rsp+98h+var_40]
0x18001b6a8  lea     rcx, [rsp+98h+var_60]
0x18001b6ad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001b6b2  lea     rdx, [rsi+10h]
0x18001b6b6  mov     rcx, rax
0x18001b6b9  call    ?StringToGuid@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAU_GUID@@@Z; StringToGuid(std::wstring,_GUID &)
0x18001b6be  mov     ebx, eax
0x18001b6c0  jmp     short loc_18001B6CD
0x18001b6c2  lea     rdi, WPP_GLOBAL_Control
0x18001b6c9  mov     ebx, [rsp+98h+var_68]
0x18001b6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6d4  cmp     rcx, rdi
0x18001b6d7  jz      short loc_18001B706
0x18001b6d9  cmp     byte ptr [rcx+19h], 5
0x18001b6dd  jb      short loc_18001B706
0x18001b6df  test    byte ptr [rcx+1Ch], 1
0x18001b6e3  jz      short loc_18001B706
0x18001b6e5  mov     edx, 10h
0x18001b6ea  mov     dword ptr [rsp+98h+var_78], ebx
0x18001b6ee  lea     r9, aWcmconnections; "WcmConnectionSelectionByDeviceType::Rea"...
0x18001b6f5  lea     r8, WPP_151ddd895e933c0f2519f87f597ae9c4_Traceguids
0x18001b6fc  mov     rcx, [rcx+10h]
0x18001b700  call    WPP_SF_sL
0x18001b705  nop
0x18001b706  lea     rcx, [rsp+98h+var_40]
0x18001b70b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001b710  mov     eax, ebx
0x18001b712  mov     rcx, [rsp+98h+var_20]
0x18001b717  xor     rcx, rsp; StackCookie
0x18001b71a  call    __security_check_cookie
0x18001b71f  mov     rbx, [rsp+98h+arg_10]
0x18001b727  add     rsp, 80h
0x18001b72e  pop     r14
0x18001b730  pop     rdi
0x18001b731  pop     rsi
0x18001b732  retn
```
