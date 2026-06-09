# SetChannelCommand::SetPropertyString(wchar_t const *,void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,IXMLDOMElement *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x14001117c`
- end: `0x1400112fb`
- name: `?SetPropertyString@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027f70`

## callees

- `0x140010450`
- `0x140010704`
- `0x14001117c`
- `0x14001159c`
- `0x140011a00`
- `0x140011bbc`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001125c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001125c`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x14001124e`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x14001124e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SetChannelCommand::SetPropertyString(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        __int128 *a4,
        __int128 *a5,
        __int64 a6,
        __int128 *a7,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId)
{
  _WORD *OptionString; // rcx
  __int64 NodeText; // rax
  DWORD LastError; // ebx
  char *v14; // [rsp+20h] [rbp-59h]
  struct _EVT_VARIANT PropertyValue; // [rsp+40h] [rbp-39h] BYREF
  __int128 v16; // [rsp+50h] [rbp-29h] BYREF
  __int128 v17; // [rsp+60h] [rbp-19h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+70h] [rbp-9h] BYREF
  char v19; // [rsp+C0h] [rbp+47h] BYREF
  INT64 v20; // [rsp+D8h] [rbp+5Fh] BYREF

  v20 = 0;
  PropertyValue = 0;
  v19 = 0;
  v16 = *a5;
  v17 = *a4;
  OptionString = (_WORD *)CommandArguments::GetOptionString(
                            *(_QWORD *)(a1 + 8),
                            (unsigned int)&v17,
                            (unsigned int)&v16,
                            (unsigned int)&ValueName,
                            (__int64)&v19);
  PropertyValue.Int64Val = (INT64)OptionString;
  if ( !v19 )
  {
    if ( !a6 )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v20);
    v17 = *a7;
    NodeText = XmlGetNodeText(&a5, a6, &v17);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &v20,
      NodeText);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&a5);
    OptionString = (_WORD *)v20;
    if ( !v20 )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v20);
    PropertyValue.Int64Val = v20;
  }
  PropertyValue.Type = *OptionString != 0;
  if ( !EvtSetChannelConfigProperty(a3, PropertyId, 0, &PropertyValue) )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v14, 412, 5u, a2);
    throw (EvtException *)pExceptionObject;
  }
  return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v20);
}

```

## disassembly

```asm
0x14001117c  mov     [rsp-8+arg_8], rbx
0x140011181  push    rbp
0x140011182  push    rsi
0x140011183  push    rdi
0x140011184  lea     rbp, [rsp-27h]
0x140011189  sub     rsp, 0A0h
0x140011190  mov     rbx, r8
0x140011193  mov     rdi, rdx
0x140011196  xor     esi, esi
0x140011198  mov     [rbp+37h+arg_18], rsi
0x14001119c  xorps   xmm0, xmm0
0x14001119f  movups  xmmword ptr [rbp+37h+PropertyValue], xmm0
0x1400111a3  mov     [rbp+37h+arg_0], sil
0x1400111a7  mov     rax, [rbp+37h+arg_20]
0x1400111ab  movaps  xmm0, xmmword ptr [rax]
0x1400111ae  movdqa  [rbp+37h+var_60], xmm0
0x1400111b3  movaps  xmm1, xmmword ptr [r9]
0x1400111b7  movdqa  [rbp+37h+var_50], xmm1
0x1400111bc  lea     rax, [rbp+37h+arg_0]
0x1400111c0  mov     [rsp+0B0h+var_90], rax; char *
0x1400111c5  lea     r9, ValueName
0x1400111cc  lea     r8, [rbp+37h+var_60]
0x1400111d0  lea     rdx, [rbp+37h+var_50]
0x1400111d4  mov     rcx, [rcx+8]
0x1400111d8  call    ?GetOptionString@CommandArguments@@QEBAPEB_WV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0PEB_WAEA_N@Z; CommandArguments::GetOptionString(std::wstring_view,std::wstring_view,wchar_t const *,bool &)
0x1400111dd  mov     rcx, rax
0x1400111e0  mov     qword ptr [rbp+37h+PropertyValue], rax
0x1400111e4  cmp     [rbp+37h+arg_0], sil
0x1400111e8  jnz     short loc_140011236
0x1400111ea  mov     rdx, [rbp+37h+arg_28]
0x1400111ee  test    rdx, rdx
0x1400111f1  jz      loc_1400112DF
0x1400111f7  mov     rax, [rbp+37h+arg_30]
0x1400111fb  movaps  xmm0, xmmword ptr [rax]
0x1400111fe  movdqa  [rbp+37h+var_50], xmm0
0x140011203  lea     r8, [rbp+37h+var_50]
0x140011207  lea     rcx, [rbp+37h+arg_20]
0x14001120b  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x140011210  mov     rdx, rax
0x140011213  lea     rcx, [rbp+37h+arg_18]
0x140011217  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x14001121c  lea     rcx, [rbp+37h+arg_20]
0x140011220  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140011225  mov     rcx, [rbp+37h+arg_18]
0x140011229  test    rcx, rcx
0x14001122c  jz      loc_1400112DF
0x140011232  mov     qword ptr [rbp+37h+PropertyValue], rcx
0x140011236  mov     eax, esi
0x140011238  cmp     [rcx], si
0x14001123b  setnz   al
0x14001123e  mov     [rbp+37h+PropertyValue.Type], eax
0x140011241  lea     r9, [rbp+37h+PropertyValue]; PropertyValue
0x140011245  xor     r8d, r8d; Flags
0x140011248  mov     edx, [rbp+37h+PropertyId]; PropertyId
0x14001124b  mov     rcx, rbx; ChannelConfig
0x14001124e  call    cs:__imp_EvtSetChannelConfigProperty
0x140011254  test    eax, eax
0x140011256  jnz     loc_1400112DF
0x14001125c  call    cs:__imp_GetLastError
0x140011262  mov     ebx, eax
0x140011264  mov     eax, 507h
0x140011269  test    ebx, ebx
0x14001126b  cmovz   ebx, eax
0x14001126e  lea     rax, WPP_GLOBAL_Control
0x140011275  mov     rcx, cs:WPP_GLOBAL_Control
0x14001127c  cmp     rcx, rax
0x14001127f  jz      short loc_1400112A8
0x140011281  test    dword ptr [rcx+1Ch], 400000h
0x140011288  jz      short loc_1400112A8
0x14001128a  cmp     byte ptr [rcx+19h], 2
0x14001128e  jb      short loc_1400112A8
0x140011290  mov     edx, 1Eh
0x140011295  mov     r9d, ebx
0x140011298  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14001129f  mov     rcx, [rcx+10h]
0x1400112a3  call    WPP_SF_d
0x1400112a8  mov     [rsp+0B0h+Src], rdi; Src
0x1400112ad  mov     [rsp+0B0h+var_80], 5; unsigned int
0x1400112b5  mov     [rsp+0B0h+var_88], 19Ch; int
0x1400112bd  xor     r9d, r9d; unsigned int
0x1400112c0  xor     r8d, r8d; unsigned int
0x1400112c3  mov     edx, ebx; unsigned int
0x1400112c5  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1400112c9  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400112ce  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400112d5  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1400112d9  call    _CxxThrowException_0
0x1400112df  lea     rcx, [rbp+37h+arg_18]
0x1400112e3  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x1400112e8  mov     rbx, [rsp+0B0h+arg_8]
0x1400112f0  add     rsp, 0A0h
0x1400112f7  pop     rdi
0x1400112f8  pop     rsi
0x1400112f9  pop     rbp
0x1400112fa  retn
```
