# SetChannelCommand::SetPropertyUInt64(wchar_t const *,void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,IXMLDOMElement *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x1400124fc`
- end: `0x1400126ff`
- name: `?SetPropertyUInt64@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027f70`

## callees

- `0x14000eeb4`
- `0x140010450`
- `0x140010704`
- `0x14001159c`
- `0x1400124fc`
- `0x1400225cc`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001267c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001267c`
- `OLEAUT32!__imp_SysStringLen` at `0x1400125a7`
- `OLEAUT32!__imp_SysStringLen` at `0x1400125a7`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x14001266e`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x14001266e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SetChannelCommand::SetPropertyUInt64(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        __int128 *a4,
        BSTR pbstr,
        __int64 a6,
        __int128 *a7,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId)
{
  INT64 OptionInteger64; // rax
  DWORD LastError; // ebx
  char *v13; // [rsp+20h] [rbp-49h]
  struct _EVT_VARIANT PropertyValue; // [rsp+40h] [rbp-29h] BYREF
  __int128 v15; // [rsp+50h] [rbp-19h] BYREF
  __int128 v16; // [rsp+60h] [rbp-9h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp+7h] BYREF
  char v18; // [rsp+B0h] [rbp+47h] BYREF

  PropertyValue = 0;
  v18 = 0;
  v15 = *(_OWORD *)pbstr;
  v16 = *a4;
  OptionInteger64 = CommandArguments::GetOptionInteger64(
                      *(_QWORD *)(a1 + 8),
                      (unsigned int)&v16,
                      (unsigned int)&v15,
                      (_DWORD)a4,
                      (__int64)&v18);
  if ( v18 )
  {
    PropertyValue.Int64Val = OptionInteger64;
  }
  else
  {
    if ( !a6 )
      return OptionInteger64;
    v16 = *a7;
    XmlGetNodeText(&pbstr, a6, &v16);
    if ( !pbstr )
    {
      LODWORD(OptionInteger64) = wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
      return OptionInteger64;
    }
    if ( SysStringLen(pbstr) )
    {
      if ( swscanf(pbstr, L"%I64i", &PropertyValue) != 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 87);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v13, 303, 0x23u, a2);
        throw (EvtException *)pExceptionObject;
      }
    }
    else
    {
      PropertyValue.Int64Val = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
  }
  PropertyValue.Type = 10;
  LODWORD(OptionInteger64) = EvtSetChannelConfigProperty(a3, PropertyId, 0, &PropertyValue);
  if ( !(_DWORD)OptionInteger64 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v13, 319, 5u, a2);
    throw (EvtException *)pExceptionObject;
  }
  return OptionInteger64;
}

```

## disassembly

```asm
0x1400124fc  mov     [rsp-8+arg_8], rbx
0x140012501  mov     [rsp-8+arg_10], rdi
0x140012506  push    rbp
0x140012507  lea     rbp, [rsp-37h]
0x14001250c  sub     rsp, 0A0h
0x140012513  mov     rbx, r8
0x140012516  mov     rdi, rdx
0x140012519  xorps   xmm0, xmm0
0x14001251c  movups  xmmword ptr [rbp+37h+PropertyValue], xmm0
0x140012520  mov     [rbp+37h+arg_0], 0
0x140012524  mov     rax, [rbp+37h+pbstr]
0x140012528  movaps  xmm0, xmmword ptr [rax]
0x14001252b  movdqa  [rbp+37h+var_50], xmm0
0x140012530  movaps  xmm1, xmmword ptr [r9]
0x140012534  movdqa  [rbp+37h+var_40], xmm1
0x140012539  lea     rax, [rbp+37h+arg_0]
0x14001253d  mov     [rsp+0A0h+var_80], rax; char *
0x140012542  lea     r8, [rbp+37h+var_50]
0x140012546  lea     rdx, [rbp+37h+var_40]
0x14001254a  mov     rcx, [rcx+8]
0x14001254e  call    ?GetOptionInteger64@CommandArguments@@QEBA_JV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_JAEA_N@Z; CommandArguments::GetOptionInteger64(std::wstring_view,std::wstring_view,__int64,bool &)
0x140012553  cmp     [rbp+37h+arg_0], 0
0x140012557  jnz     loc_140012656
0x14001255d  mov     rdx, [rbp+37h+arg_28]
0x140012561  test    rdx, rdx
0x140012564  jz      short loc_140012592
0x140012566  mov     rax, [rbp+37h+arg_30]
0x14001256a  movaps  xmm0, xmmword ptr [rax]
0x14001256d  movdqa  [rbp+37h+var_40], xmm0
0x140012572  lea     r8, [rbp+37h+var_40]
0x140012576  lea     rcx, [rbp+37h+pbstr]
0x14001257a  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x14001257f  nop
0x140012580  mov     rcx, [rbp+37h+pbstr]; pbstr
0x140012584  test    rcx, rcx
0x140012587  jnz     short loc_1400125A7
0x140012589  lea     rcx, [rbp+37h+pbstr]
0x14001258d  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140012592  lea     r11, [rsp+0A0h+var_s0]
0x14001259a  mov     rbx, [r11+18h]
0x14001259e  mov     rdi, [r11+20h]
0x1400125a2  mov     rsp, r11
0x1400125a5  pop     rbp
0x1400125a6  retn
0x1400125a7  call    cs:__imp_SysStringLen
0x1400125ad  nop
0x1400125ae  test    eax, eax
0x1400125b0  jz      loc_140012643
0x1400125b6  lea     r8, [rbp+37h+PropertyValue]
0x1400125ba  lea     rdx, aI64i; "%I64i"
0x1400125c1  mov     rcx, [rbp+37h+pbstr]; Buffer
0x1400125c5  call    swscanf
0x1400125ca  cmp     eax, 1
0x1400125cd  jz      short loc_14001264B
0x1400125cf  lea     rax, WPP_GLOBAL_Control
0x1400125d6  mov     ebx, 57h ; 'W'
0x1400125db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400125e2  cmp     rcx, rax
0x1400125e5  jz      short loc_14001260C
0x1400125e7  test    dword ptr [rcx+1Ch], 400000h
0x1400125ee  jz      short loc_14001260C
0x1400125f0  cmp     byte ptr [rcx+19h], 2
0x1400125f4  jb      short loc_14001260C
0x1400125f6  lea     edx, [rbx-3Dh]
0x1400125f9  mov     r9d, ebx
0x1400125fc  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140012603  mov     rcx, [rcx+10h]
0x140012607  call    WPP_SF_d
0x14001260c  mov     [rsp+0A0h+Src], rdi; Src
0x140012611  mov     [rsp+0A0h+var_70], 23h ; '#'; unsigned int
0x140012619  mov     [rsp+0A0h+var_78], 12Fh; int
0x140012621  xor     r9d, r9d; unsigned int
0x140012624  xor     r8d, r8d; unsigned int
0x140012627  mov     edx, ebx; unsigned int
0x140012629  lea     rcx, [rbp+37h+pExceptionObject]; this
0x14001262d  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140012632  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012639  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x14001263d  call    _CxxThrowException_0
0x140012643  mov     qword ptr [rbp+37h+PropertyValue], 0
0x14001264b  lea     rcx, [rbp+37h+pbstr]
0x14001264f  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140012654  jmp     short loc_14001265A
0x140012656  mov     qword ptr [rbp+37h+PropertyValue], rax
0x14001265a  mov     [rbp+37h+PropertyValue.Type], 0Ah
0x140012661  lea     r9, [rbp+37h+PropertyValue]; PropertyValue
0x140012665  xor     r8d, r8d; Flags
0x140012668  mov     edx, [rbp+37h+PropertyId]; PropertyId
0x14001266b  mov     rcx, rbx; ChannelConfig
0x14001266e  call    cs:__imp_EvtSetChannelConfigProperty
0x140012674  test    eax, eax
0x140012676  jnz     loc_140012592
0x14001267c  call    cs:__imp_GetLastError
0x140012682  mov     ebx, eax
0x140012684  mov     eax, 507h
0x140012689  test    ebx, ebx
0x14001268b  cmovz   ebx, eax
0x14001268e  lea     rax, WPP_GLOBAL_Control
0x140012695  mov     rcx, cs:WPP_GLOBAL_Control
0x14001269c  cmp     rcx, rax
0x14001269f  jz      short loc_1400126C8
0x1400126a1  test    dword ptr [rcx+1Ch], 400000h
0x1400126a8  jz      short loc_1400126C8
0x1400126aa  cmp     byte ptr [rcx+19h], 2
0x1400126ae  jb      short loc_1400126C8
0x1400126b0  mov     edx, 1Bh
0x1400126b5  mov     r9d, ebx
0x1400126b8  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x1400126bf  mov     rcx, [rcx+10h]
0x1400126c3  call    WPP_SF_d
0x1400126c8  mov     [rsp+0A0h+Src], rdi; Src
0x1400126cd  mov     [rsp+0A0h+var_70], 5; unsigned int
0x1400126d5  mov     [rsp+0A0h+var_78], 13Fh; int
0x1400126dd  xor     r9d, r9d; unsigned int
0x1400126e0  xor     r8d, r8d; unsigned int
0x1400126e3  mov     edx, ebx; unsigned int
0x1400126e5  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1400126e9  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400126ee  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400126f5  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1400126f9  call    _CxxThrowException_0
```
