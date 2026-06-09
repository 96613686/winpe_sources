# SetChannelCommand::SetPropertyEnum(wchar_t const *,void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,IXMLDOMElement *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x140010c90`
- end: `0x140010f02`
- name: `?SetPropertyEnum@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027f70`

## callees

- `0x140010450`
- `0x140010704`
- `0x140010c90`
- `0x14001159c`
- `0x140011a00`
- `0x140011bbc`
- `0x14001b4e4`
- `0x14001b580`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140010dd6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140010dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010e04`
- `OLEAUT32!__imp_SysStringLen` at `0x140010d47`
- `OLEAUT32!__imp_SysStringLen` at `0x140010d47`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x140010df6`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x140010df6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetChannelCommand::SetPropertyEnum(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int128 *a4,
        __int128 *a5,
        __int64 a6,
        __int128 *a7,
        char a8)
{
  __int64 OptionString; // rax
  const wchar_t *Src; // rdi
  __int64 v11; // rbx
  __int64 NodeText; // rax
  __int64 v13; // rsi
  DWORD LastError; // ebx
  const char *bIgnoreCase; // [rsp+20h] [rbp-79h]
  struct _EVT_VARIANT PropertyValue; // [rsp+40h] [rbp-59h] BYREF
  __int128 v18; // [rsp+50h] [rbp-49h] BYREF
  __int128 v19; // [rsp+60h] [rbp-39h] BYREF
  _BYTE pExceptionObject[96]; // [rsp+70h] [rbp-29h] BYREF
  BSTR pbstr; // [rsp+E8h] [rbp+4Fh] BYREF

  pbstr = 0;
  a8 = 0;
  v18 = *a5;
  v19 = *a4;
  OptionString = CommandArguments::GetOptionString(
                   *(_QWORD *)(a1 + 8),
                   (unsigned int)&v19,
                   (unsigned int)&v18,
                   (unsigned int)&ValueName,
                   (__int64)&a8);
  Src = (const wchar_t *)OptionString;
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(OptionString + 2 * v11) );
  if ( a8 )
  {
    LODWORD(v13) = v11;
  }
  else
  {
    if ( !a6 )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
    v19 = *a7;
    NodeText = XmlGetNodeText(&a5, a6, &v19);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &pbstr,
      NodeText);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&a5);
    Src = pbstr;
    if ( !pbstr )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
    v13 = SysStringLen(pbstr);
    v11 = v13;
  }
  PropertyValue = 0;
  PropertyValue.Type = 8;
  *(_QWORD *)&v18 = Src;
  *((_QWORD *)&v18 + 1) = v11;
  if ( (unsigned __int8)IsApplicationChannel(&v18) )
  {
    PropertyValue.BooleanVal = 0;
  }
  else
  {
    *(_QWORD *)&v18 = Src;
    *((_QWORD *)&v18 + 1) = v11;
    if ( (unsigned __int8)IsSystemChannel(&v18) )
    {
      PropertyValue.BooleanVal = 1;
    }
    else
    {
      if ( v11 != 6 || CompareStringOrdinal(Src, v13, L"Custom", 6, 1) != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 87);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, bIgnoreCase, 465, 0x27u, Src);
        throw (EvtException *)pExceptionObject;
      }
      PropertyValue.BooleanVal = 2;
    }
  }
  if ( !EvtSetChannelConfigProperty(a3, EvtChannelConfigIsolation, 0, &PropertyValue) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, bIgnoreCase, 474, 5u, L"Isolation");
    throw (EvtException *)pExceptionObject;
  }
  return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
}

```

## disassembly

```asm
0x140010c90  mov     [rsp-8+pbstr], rdx
0x140010c95  push    rbp
0x140010c96  push    rbx
0x140010c97  push    rsi
0x140010c98  push    rdi
0x140010c99  push    r14
0x140010c9b  push    r15
0x140010c9d  lea     rbp, [rsp-0Fh]
0x140010ca2  sub     rsp, 0A8h
0x140010ca9  mov     r14, r8
0x140010cac  xor     r15d, r15d
0x140010caf  mov     [rbp+37h+pbstr], r15
0x140010cb3  mov     [rbp+37h+arg_38], r15b
0x140010cb7  mov     rax, [rbp+37h+arg_20]
0x140010cbb  movaps  xmm0, xmmword ptr [rax]
0x140010cbe  movdqa  [rbp+37h+var_80], xmm0
0x140010cc3  movaps  xmm1, xmmword ptr [r9]
0x140010cc7  movdqa  [rbp+37h+var_70], xmm1
0x140010ccc  lea     rax, [rbp+37h+arg_38]
0x140010cd0  mov     qword ptr [rsp+0D0h+bIgnoreCase], rax; char *
0x140010cd5  lea     r9, ValueName
0x140010cdc  lea     r8, [rbp+37h+var_80]
0x140010ce0  lea     rdx, [rbp+37h+var_70]
0x140010ce4  mov     rcx, [rcx+8]
0x140010ce8  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x140010ced  mov     rdi, rax
0x140010cf0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140010cf4  inc     rbx
0x140010cf7  cmp     [rax+rbx*2], r15w
0x140010cfc  jnz     short loc_140010CF4
0x140010cfe  cmp     [rbp+37h+arg_38], r15b
0x140010d02  jnz     short loc_140010D6C
0x140010d04  mov     rdx, [rbp+37h+arg_28]
0x140010d08  test    rdx, rdx
0x140010d0b  jz      short loc_140010D53
0x140010d0d  mov     rax, [rbp+37h+arg_30]
0x140010d11  movaps  xmm0, xmmword ptr [rax]
0x140010d14  movdqa  [rbp+37h+var_70], xmm0
0x140010d19  lea     r8, [rbp+37h+var_70]
0x140010d1d  lea     rcx, [rbp+37h+arg_20]
0x140010d21  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x140010d26  mov     rdx, rax
0x140010d29  lea     rcx, [rbp+37h+pbstr]
0x140010d2d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x140010d32  lea     rcx, [rbp+37h+arg_20]
0x140010d36  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010d3b  mov     rdi, [rbp+37h+pbstr]
0x140010d3f  test    rdi, rdi
0x140010d42  jz      short loc_140010D53
0x140010d44  mov     rcx, rdi; pbstr
0x140010d47  call    cs:__imp_SysStringLen
0x140010d4d  mov     esi, eax
0x140010d4f  mov     ebx, eax
0x140010d51  jmp     short loc_140010D6E
0x140010d53  lea     rcx, [rbp+37h+pbstr]
0x140010d57  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010d5c  add     rsp, 0A8h
0x140010d63  pop     r15
0x140010d65  pop     r14
0x140010d67  pop     rdi
0x140010d68  pop     rsi
0x140010d69  pop     rbx
0x140010d6a  pop     rbp
0x140010d6b  retn
0x140010d6c  mov     esi, ebx
0x140010d6e  xorps   xmm0, xmm0
0x140010d71  movups  xmmword ptr [rbp+37h+PropertyValue], xmm0
0x140010d75  mov     [rbp+37h+PropertyValue.Type], 8
0x140010d7c  mov     qword ptr [rbp+37h+var_80], rdi
0x140010d80  mov     qword ptr [rbp+37h+var_80+8], rbx
0x140010d84  lea     rcx, [rbp+37h+var_80]
0x140010d88  call    ?IsApplicationChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsApplicationChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140010d8d  test    al, al
0x140010d8f  jz      short loc_140010D97
0x140010d91  mov     dword ptr [rbp+37h+PropertyValue], r15d
0x140010d95  jmp     short loc_140010DE8
0x140010d97  mov     qword ptr [rbp+37h+var_80], rdi
0x140010d9b  mov     qword ptr [rbp+37h+var_80+8], rbx
0x140010d9f  lea     rcx, [rbp+37h+var_80]
0x140010da3  call    ?IsSystemChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSystemChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140010da8  test    al, al
0x140010daa  jz      short loc_140010DB5
0x140010dac  mov     dword ptr [rbp+37h+PropertyValue], 1
0x140010db3  jmp     short loc_140010DE8
0x140010db5  cmp     rbx, 6
0x140010db9  jnz     loc_140010E8E
0x140010dbf  mov     [rsp+0D0h+bIgnoreCase], 1; char *
0x140010dc7  mov     r9d, ebx; cchCount2
0x140010dca  lea     r8, String2; "Custom"
0x140010dd1  mov     edx, esi; cchCount1
0x140010dd3  mov     rcx, rdi; lpString1
0x140010dd6  call    cs:__imp_CompareStringOrdinal
0x140010ddc  cmp     eax, 2
0x140010ddf  jnz     loc_140010E8E
0x140010de5  mov     dword ptr [rbp+37h+PropertyValue], eax
0x140010de8  lea     r9, [rbp+37h+PropertyValue]; PropertyValue
0x140010dec  xor     r8d, r8d; Flags
0x140010def  lea     edx, [r8+1]; PropertyId
0x140010df3  mov     rcx, r14; ChannelConfig
0x140010df6  call    cs:__imp_EvtSetChannelConfigProperty
0x140010dfc  test    eax, eax
0x140010dfe  jnz     loc_140010D53
0x140010e04  call    cs:__imp_GetLastError
0x140010e0a  mov     ebx, eax
0x140010e0c  mov     eax, 507h
0x140010e11  test    ebx, ebx
0x140010e13  cmovz   ebx, eax
0x140010e16  lea     rax, WPP_GLOBAL_Control
0x140010e1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140010e24  cmp     rcx, rax
0x140010e27  jz      short loc_140010E50
0x140010e29  test    dword ptr [rcx+1Ch], 400000h
0x140010e30  jz      short loc_140010E50
0x140010e32  cmp     byte ptr [rcx+19h], 2
0x140010e36  jb      short loc_140010E50
0x140010e38  mov     edx, 20h ; ' '
0x140010e3d  mov     r9d, ebx
0x140010e40  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140010e47  mov     rcx, [rcx+10h]
0x140010e4b  call    WPP_SF_d
0x140010e50  lea     rax, aIsolation; "Isolation"
0x140010e57  mov     [rsp+0D0h+Src], rax; Src
0x140010e5c  mov     [rsp+0D0h+var_A0], 5; unsigned int
0x140010e64  mov     [rsp+0D0h+var_A8], 1DAh; int
0x140010e6c  xor     r9d, r9d; unsigned int
0x140010e6f  xor     r8d, r8d; unsigned int
0x140010e72  mov     edx, ebx; unsigned int
0x140010e74  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140010e78  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140010e7d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010e84  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140010e88  call    _CxxThrowException_0
0x140010e8e  lea     rax, WPP_GLOBAL_Control
0x140010e95  mov     ebx, 57h ; 'W'
0x140010e9a  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ea1  cmp     rcx, rax
0x140010ea4  jz      short loc_140010ECB
0x140010ea6  test    dword ptr [rcx+1Ch], 400000h
0x140010ead  jz      short loc_140010ECB
0x140010eaf  cmp     byte ptr [rcx+19h], 2
0x140010eb3  jb      short loc_140010ECB
0x140010eb5  lea     edx, [rbx-38h]
0x140010eb8  mov     r9d, ebx
0x140010ebb  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140010ec2  mov     rcx, [rcx+10h]
0x140010ec6  call    WPP_SF_d
0x140010ecb  mov     [rsp+0D0h+Src], rdi; Src
0x140010ed0  mov     [rsp+0D0h+var_A0], 27h ; '''; unsigned int
0x140010ed8  mov     [rsp+0D0h+var_A8], 1D1h; int
0x140010ee0  xor     r9d, r9d; unsigned int
0x140010ee3  xor     r8d, r8d; unsigned int
0x140010ee6  mov     edx, ebx; unsigned int
0x140010ee8  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140010eec  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140010ef1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010ef8  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140010efc  call    _CxxThrowException_0
```
