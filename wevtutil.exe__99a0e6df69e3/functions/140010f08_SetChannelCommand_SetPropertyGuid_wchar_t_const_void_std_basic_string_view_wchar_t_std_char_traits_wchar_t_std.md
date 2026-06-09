# SetChannelCommand::SetPropertyGuid(wchar_t const *,void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,IXMLDOMElement *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x140010f08`
- end: `0x140011175`
- name: `?SetPropertyGuid@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027f70`

## callees

- `0x1400081c0`
- `0x140010450`
- `0x140010704`
- `0x140010f08`
- `0x14001159c`
- `0x140011a00`
- `0x140011bbc`
- `0x140021b00`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400110bf`
- `OLEAUT32!__imp_SysStringLen` at `0x140010fe0`
- `OLEAUT32!__imp_SysStringLen` at `0x140010fe0`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x1400110b1`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x1400110b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetChannelCommand::SetPropertyGuid(
        __int64 a1,
        __int64 a2,
        void *a3,
        __int128 *a4,
        __int128 *a5,
        __int64 a6,
        __int128 *a7)
{
  BSTR OptionString; // rbx
  __int64 v9; // rax
  __int64 NodeText; // rax
  UINT v11; // eax
  DWORD LastError; // ebx
  char *v14; // [rsp+20h] [rbp-99h]
  char v15[8]; // [rsp+40h] [rbp-79h] BYREF
  BSTR pbstr; // [rsp+48h] [rbp-71h] BYREF
  __int128 v17; // [rsp+50h] [rbp-69h] BYREF
  __int128 v18; // [rsp+60h] [rbp-59h] BYREF
  struct _EVT_VARIANT PropertyValue; // [rsp+70h] [rbp-49h] BYREF
  __int128 v20; // [rsp+80h] [rbp-39h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+90h] [rbp-29h] BYREF
  __int128 v22; // [rsp+B8h] [rbp-1h] BYREF

  pbstr = 0;
  v15[0] = 0;
  v17 = *a5;
  v18 = *a4;
  OptionString = (BSTR)CommandArguments::GetOptionString(
                         *(_QWORD *)(a1 + 8),
                         (unsigned int)&v18,
                         (unsigned int)&v17,
                         (unsigned int)&ValueName,
                         (__int64)v15);
  *(_QWORD *)&v17 = OptionString;
  v9 = -1;
  do
    ++v9;
  while ( OptionString[v9] );
  *((_QWORD *)&v17 + 1) = v9;
  if ( !v15[0] )
  {
    if ( !a6 )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
    v20 = *a7;
    NodeText = XmlGetNodeText(&v18, a6, &v20);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &pbstr,
      NodeText);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v18);
    OptionString = pbstr;
    if ( !pbstr )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
    v11 = SysStringLen(pbstr);
    *(_QWORD *)&v17 = OptionString;
    *((_QWORD *)&v17 + 1) = v11;
  }
  if ( *OptionString )
  {
    v22 = 0;
    if ( !tlx::string_to_guid<std::wstring_view>(&v22, &v17) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 1705);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0x6A9u, 0, 0, v14, 359, 5u, L"ControlGuid");
      throw (EvtException *)pExceptionObject;
    }
    PropertyValue.Count = 0;
    PropertyValue.Int64Val = (INT64)&v22;
    PropertyValue.Type = 15;
    if ( !EvtSetChannelConfigProperty(a3, EvtChannelPublishingConfigControlGuid, 0, &PropertyValue) )
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1287;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v14, 368, 5u, L"ControlGuid");
      throw (EvtException *)pExceptionObject;
    }
  }
  return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
}

```

## disassembly

```asm
0x140010f08  mov     [rsp-8+arg_8], rbx
0x140010f0d  push    rbp
0x140010f0e  push    rsi
0x140010f0f  push    rdi
0x140010f10  push    r14
0x140010f12  push    r15
0x140010f14  lea     rbp, [rsp-17h]
0x140010f19  sub     rsp, 0D0h
0x140010f20  mov     rax, cs:__security_cookie
0x140010f27  xor     rax, rsp
0x140010f2a  mov     [rbp+37h+var_28], rax
0x140010f2e  mov     rsi, r8
0x140010f31  mov     rax, [rbp+37h+arg_20]
0x140010f35  mov     rdi, [rbp+37h+arg_28]
0x140010f39  mov     r14, [rbp+37h+arg_30]
0x140010f3d  xor     r15d, r15d
0x140010f40  mov     [rbp+37h+pbstr], r15
0x140010f44  mov     [rbp+37h+var_B0], r15b
0x140010f48  movaps  xmm0, xmmword ptr [rax]
0x140010f4b  movdqa  [rbp+37h+var_A0], xmm0
0x140010f50  movaps  xmm1, xmmword ptr [r9]
0x140010f54  movdqa  [rbp+37h+var_90], xmm1
0x140010f59  lea     rax, [rbp+37h+var_B0]
0x140010f5d  mov     [rsp+0F0h+var_D0], rax; char *
0x140010f62  lea     r9, ValueName
0x140010f69  lea     r8, [rbp+37h+var_A0]
0x140010f6d  lea     rdx, [rbp+37h+var_90]
0x140010f71  mov     rcx, [rcx+8]
0x140010f75  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x140010f7a  mov     rbx, rax
0x140010f7d  mov     qword ptr [rbp+37h+var_A0], rax
0x140010f81  or      rax, 0FFFFFFFFFFFFFFFFh
0x140010f85  inc     rax
0x140010f88  cmp     [rbx+rax*2], r15w
0x140010f8d  jnz     short loc_140010F85
0x140010f8f  mov     qword ptr [rbp+37h+var_A0+8], rax
0x140010f93  cmp     [rbp+37h+var_B0], r15b
0x140010f97  jnz     short loc_140010FF0
0x140010f99  test    rdi, rdi
0x140010f9c  jz      loc_140011149
0x140010fa2  movaps  xmm0, xmmword ptr [r14]
0x140010fa6  movdqa  [rbp+37h+var_70], xmm0
0x140010fab  lea     r8, [rbp+37h+var_70]
0x140010faf  mov     rdx, rdi
0x140010fb2  lea     rcx, [rbp+37h+var_90]
0x140010fb6  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x140010fbb  mov     rdx, rax
0x140010fbe  lea     rcx, [rbp+37h+pbstr]
0x140010fc2  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x140010fc7  lea     rcx, [rbp+37h+var_90]
0x140010fcb  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010fd0  mov     rbx, [rbp+37h+pbstr]
0x140010fd4  test    rbx, rbx
0x140010fd7  jz      loc_140011149
0x140010fdd  mov     rcx, rbx; pbstr
0x140010fe0  call    cs:__imp_SysStringLen
0x140010fe6  mov     eax, eax
0x140010fe8  mov     qword ptr [rbp+37h+var_A0], rbx
0x140010fec  mov     qword ptr [rbp+37h+var_A0+8], rax
0x140010ff0  cmp     [rbx], r15w
0x140010ff4  jz      loc_140011149
0x140010ffa  xorps   xmm0, xmm0
0x140010ffd  movups  [rbp+37h+var_38], xmm0
0x140011001  lea     rdx, [rbp+37h+var_A0]
0x140011005  lea     rcx, [rbp+37h+var_38]
0x140011009  call    ??$string_to_guid@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@tlx@@YAPEB_WPEAU_GUID@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; tlx::string_to_guid<std::wstring_view>(_GUID *,std::wstring_view const &)
0x14001100e  test    rax, rax
0x140011011  jnz     short loc_140011090
0x140011013  lea     rax, WPP_GLOBAL_Control
0x14001101a  mov     ebx, 6A9h
0x14001101f  mov     rcx, cs:WPP_GLOBAL_Control
0x140011026  cmp     rcx, rax
0x140011029  jz      short loc_140011052
0x14001102b  test    dword ptr [rcx+1Ch], 400000h
0x140011032  jz      short loc_140011052
0x140011034  cmp     byte ptr [rcx+19h], 2
0x140011038  jb      short loc_140011052
0x14001103a  mov     edx, 1Ch
0x14001103f  mov     r9d, ebx
0x140011042  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140011049  mov     rcx, [rcx+10h]
0x14001104d  call    WPP_SF_d
0x140011052  lea     rax, aControlguid; "ControlGuid"
0x140011059  mov     [rsp+0F0h+Src], rax; Src
0x14001105e  mov     [rsp+0F0h+var_C0], 5; unsigned int
0x140011066  mov     [rsp+0F0h+var_C8], 167h; int
0x14001106e  xor     r9d, r9d; unsigned int
0x140011071  xor     r8d, r8d; unsigned int
0x140011074  mov     edx, ebx; unsigned int
0x140011076  lea     rcx, [rbp+37h+pExceptionObject]; this
0x14001107a  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14001107f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140011086  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x14001108a  call    _CxxThrowException_0
0x140011090  mov     [rbp+37h+PropertyValue.Count], r15d
0x140011094  lea     rax, [rbp+37h+var_38]
0x140011098  mov     qword ptr [rbp+37h+PropertyValue], rax
0x14001109c  mov     [rbp+37h+PropertyValue.Type], 0Fh
0x1400110a3  lea     r9, [rbp+37h+PropertyValue]; PropertyValue
0x1400110a7  xor     r8d, r8d; Flags
0x1400110aa  lea     edx, [r8+0Ch]; PropertyId
0x1400110ae  mov     rcx, rsi; ChannelConfig
0x1400110b1  call    cs:__imp_EvtSetChannelConfigProperty
0x1400110b7  test    eax, eax
0x1400110b9  jnz     loc_140011149
0x1400110bf  call    cs:__imp_GetLastError
0x1400110c5  mov     ebx, eax
0x1400110c7  mov     eax, 507h
0x1400110cc  test    ebx, ebx
0x1400110ce  cmovz   ebx, eax
0x1400110d1  lea     rax, WPP_GLOBAL_Control
0x1400110d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400110df  cmp     rcx, rax
0x1400110e2  jz      short loc_14001110B
0x1400110e4  test    dword ptr [rcx+1Ch], 400000h
0x1400110eb  jz      short loc_14001110B
0x1400110ed  cmp     byte ptr [rcx+19h], 2
0x1400110f1  jb      short loc_14001110B
0x1400110f3  mov     edx, 1Dh
0x1400110f8  mov     r9d, ebx
0x1400110fb  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140011102  mov     rcx, [rcx+10h]
0x140011106  call    WPP_SF_d
0x14001110b  lea     rax, aControlguid; "ControlGuid"
0x140011112  mov     [rsp+0F0h+Src], rax; Src
0x140011117  mov     [rsp+0F0h+var_C0], 5; unsigned int
0x14001111f  mov     [rsp+0F0h+var_C8], 170h; int
0x140011127  xor     r9d, r9d; unsigned int
0x14001112a  xor     r8d, r8d; unsigned int
0x14001112d  mov     edx, ebx; unsigned int
0x14001112f  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140011133  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140011138  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001113f  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140011143  call    _CxxThrowException_0
0x140011149  lea     rcx, [rbp+37h+pbstr]
0x14001114d  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140011152  mov     rcx, [rbp+37h+var_28]
0x140011156  xor     rcx, rsp; StackCookie
0x140011159  call    __security_check_cookie
0x14001115e  mov     rbx, [rsp+0F0h+arg_8]
0x140011166  add     rsp, 0D0h
0x14001116d  pop     r15
0x14001116f  pop     r14
0x140011171  pop     rdi
0x140011172  pop     rsi
0x140011173  pop     rbp
0x140011174  retn
```
