# SetChannelCommand::SetPropertyUInt32(wchar_t const *,void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,IXMLDOMElement *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x1400104f8`
- end: `0x1400106fc`
- name: `?SetPropertyUInt32@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027f70`

## callees

- `0x14000fa70`
- `0x140010450`
- `0x1400104f8`
- `0x140010704`
- `0x14001159c`
- `0x1400225cc`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140010679`
- `OLEAUT32!__imp_SysStringLen` at `0x1400105a6`
- `OLEAUT32!__imp_SysStringLen` at `0x1400105a6`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x14001066b`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x14001066b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall SetChannelCommand::SetPropertyUInt32(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        __int128 *a4,
        BSTR pbstr,
        __int64 a6,
        __int128 *a7,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId)
{
  int result; // eax
  DWORD LastError; // ebx
  char *v12; // [rsp+20h] [rbp-49h]
  _EVT_VARIANT PropertyValue; // [rsp+40h] [rbp-29h] BYREF
  __int128 v14; // [rsp+50h] [rbp-19h] BYREF
  __int128 v15; // [rsp+60h] [rbp-9h] BYREF
  _BYTE pExceptionObject[48]; // [rsp+70h] [rbp+7h] BYREF
  char v17; // [rsp+B0h] [rbp+47h] BYREF

  PropertyValue = 0;
  v17 = 0;
  v14 = *(_OWORD *)pbstr;
  v15 = *a4;
  result = CommandArguments::GetOptionInteger(
             *(_QWORD *)(a1 + 8),
             (unsigned int)&v15,
             (unsigned int)&v14,
             0,
             (__int64)&v17);
  if ( v17 )
  {
    PropertyValue.BooleanVal = result;
  }
  else
  {
    if ( !a6 )
      return result;
    v15 = *a7;
    XmlGetNodeText(&pbstr, a6, &v15);
    if ( !pbstr )
      return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
    if ( SysStringLen(pbstr) )
    {
      if ( swscanf(pbstr, L"%i", &PropertyValue) != 1 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 87);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, v12, 252, 0x23u, a2);
        throw (EvtException *)pExceptionObject;
      }
    }
    else
    {
      PropertyValue.BooleanVal = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&pbstr);
  }
  PropertyValue.Type = 8;
  result = EvtSetChannelConfigProperty(a3, PropertyId, 0, &PropertyValue);
  if ( !result )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, v12, 268, 5u, a2);
    throw (EvtException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1400104f8  mov     [rsp-8+arg_8], rbx
0x1400104fd  mov     [rsp-8+arg_10], rdi
0x140010502  push    rbp
0x140010503  lea     rbp, [rsp-37h]
0x140010508  sub     rsp, 0A0h
0x14001050f  mov     rbx, r8
0x140010512  mov     rdi, rdx
0x140010515  xorps   xmm0, xmm0
0x140010518  movups  xmmword ptr [rbp+37h+PropertyValue], xmm0
0x14001051c  mov     [rbp+37h+arg_0], 0
0x140010520  mov     rax, [rbp+37h+pbstr]
0x140010524  movaps  xmm0, xmmword ptr [rax]
0x140010527  movdqa  [rbp+37h+var_50], xmm0
0x14001052c  movaps  xmm1, xmmword ptr [r9]
0x140010530  movdqa  [rbp+37h+var_40], xmm1
0x140010535  lea     rax, [rbp+37h+arg_0]
0x140010539  mov     [rsp+0A0h+var_80], rax; char *
0x14001053e  xor     r9d, r9d
0x140010541  lea     r8, [rbp+37h+var_50]
0x140010545  lea     rdx, [rbp+37h+var_40]
0x140010549  mov     rcx, [rcx+8]
0x14001054d  call    ?GetOptionInteger@CommandArguments@@QEBAHV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0HAEA_N@Z; CommandArguments::GetOptionInteger(std::wstring_view,std::wstring_view,int,bool &)
0x140010552  cmp     [rbp+37h+arg_0], 0
0x140010556  jnz     loc_140010654
0x14001055c  mov     rdx, [rbp+37h+arg_28]
0x140010560  test    rdx, rdx
0x140010563  jz      short loc_140010591
0x140010565  mov     rax, [rbp+37h+arg_30]
0x140010569  movaps  xmm0, xmmword ptr [rax]
0x14001056c  movdqa  [rbp+37h+var_40], xmm0
0x140010571  lea     r8, [rbp+37h+var_40]
0x140010575  lea     rcx, [rbp+37h+pbstr]
0x140010579  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x14001057e  nop
0x14001057f  mov     rcx, [rbp+37h+pbstr]; pbstr
0x140010583  test    rcx, rcx
0x140010586  jnz     short loc_1400105A6
0x140010588  lea     rcx, [rbp+37h+pbstr]
0x14001058c  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010591  lea     r11, [rsp+0A0h+var_s0]
0x140010599  mov     rbx, [r11+18h]
0x14001059d  mov     rdi, [r11+20h]
0x1400105a1  mov     rsp, r11
0x1400105a4  pop     rbp
0x1400105a5  retn
0x1400105a6  call    cs:__imp_SysStringLen
0x1400105ac  nop
0x1400105ad  test    eax, eax
0x1400105af  jz      loc_140010642
0x1400105b5  lea     r8, [rbp+37h+PropertyValue]
0x1400105b9  lea     rdx, aI_1; "%i"
0x1400105c0  mov     rcx, [rbp+37h+pbstr]; Buffer
0x1400105c4  call    swscanf
0x1400105c9  cmp     eax, 1
0x1400105cc  jz      short loc_140010649
0x1400105ce  lea     rax, WPP_GLOBAL_Control
0x1400105d5  mov     ebx, 57h ; 'W'
0x1400105da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400105e1  cmp     rcx, rax
0x1400105e4  jz      short loc_14001060B
0x1400105e6  test    dword ptr [rcx+1Ch], 400000h
0x1400105ed  jz      short loc_14001060B
0x1400105ef  cmp     byte ptr [rcx+19h], 2
0x1400105f3  jb      short loc_14001060B
0x1400105f5  lea     edx, [rbx-3Fh]
0x1400105f8  mov     r9d, ebx
0x1400105fb  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140010602  mov     rcx, [rcx+10h]
0x140010606  call    WPP_SF_d
0x14001060b  mov     [rsp+0A0h+Src], rdi; Src
0x140010610  mov     [rsp+0A0h+var_70], 23h ; '#'; unsigned int
0x140010618  mov     [rsp+0A0h+var_78], 0FCh; int
0x140010620  xor     r9d, r9d; unsigned int
0x140010623  xor     r8d, r8d; unsigned int
0x140010626  mov     edx, ebx; unsigned int
0x140010628  lea     rcx, [rbp+37h+pExceptionObject]; this
0x14001062c  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140010631  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010638  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x14001063c  call    _CxxThrowException_0
0x140010642  mov     dword ptr [rbp+37h+PropertyValue], 0
0x140010649  lea     rcx, [rbp+37h+pbstr]
0x14001064d  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010652  jmp     short loc_140010657
0x140010654  mov     dword ptr [rbp+37h+PropertyValue], eax
0x140010657  mov     [rbp+37h+PropertyValue.Type], 8
0x14001065e  lea     r9, [rbp+37h+PropertyValue]; PropertyValue
0x140010662  xor     r8d, r8d; Flags
0x140010665  mov     edx, [rbp+37h+PropertyId]; PropertyId
0x140010668  mov     rcx, rbx; ChannelConfig
0x14001066b  call    cs:__imp_EvtSetChannelConfigProperty
0x140010671  test    eax, eax
0x140010673  jnz     loc_140010591
0x140010679  call    cs:__imp_GetLastError
0x14001067f  mov     ebx, eax
0x140010681  mov     eax, 507h
0x140010686  test    ebx, ebx
0x140010688  cmovz   ebx, eax
0x14001068b  lea     rax, WPP_GLOBAL_Control
0x140010692  mov     rcx, cs:WPP_GLOBAL_Control
0x140010699  cmp     rcx, rax
0x14001069c  jz      short loc_1400106C5
0x14001069e  test    dword ptr [rcx+1Ch], 400000h
0x1400106a5  jz      short loc_1400106C5
0x1400106a7  cmp     byte ptr [rcx+19h], 2
0x1400106ab  jb      short loc_1400106C5
0x1400106ad  mov     edx, 19h
0x1400106b2  mov     r9d, ebx
0x1400106b5  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x1400106bc  mov     rcx, [rcx+10h]
0x1400106c0  call    WPP_SF_d
0x1400106c5  mov     [rsp+0A0h+Src], rdi; Src
0x1400106ca  mov     [rsp+0A0h+var_70], 5; unsigned int
0x1400106d2  mov     [rsp+0A0h+var_78], 10Ch; int
0x1400106da  xor     r9d, r9d; unsigned int
0x1400106dd  xor     r8d, r8d; unsigned int
0x1400106e0  mov     edx, ebx; unsigned int
0x1400106e2  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1400106e6  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x1400106eb  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400106f2  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1400106f6  call    _CxxThrowException_0
```
