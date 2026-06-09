# SetChannelCommand::SetPropertyBoolean(wchar_t const *,void *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,IXMLDOMElement *,std::basic_string_view<wchar_t,std::char_traits<wchar_t>>,_EVT_CHANNEL_CONFIG_PROPERTY_ID)

- ea: `0x140011f60`
- end: `0x1400124f4`
- name: `?SetPropertyBoolean@SetChannelCommand@@AEAAXPEB_WPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@2PEAUIXMLDOMElement@@2W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027f70`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x14000a574`
- `0x14000d144`
- `0x14000d570`
- `0x140010450`
- `0x140010704`
- `0x14001159c`
- `0x140011a38`
- `0x140011f60`
- `0x140021b00`
- `0x1400223ae`
- `0x140022cec`
- `0x140028ce8`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400123a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400123b9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400123a0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400123b9`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14001233d`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14001234d`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14001233d`
- `api-ms-win-crt-private-l1-1-0!_o_fflush` at `0x14001234d`
- `api-ms-win-crt-private-l1-1-0!_o_getwc` at `0x14001236a`
- `api-ms-win-crt-private-l1-1-0!_o_getwc` at `0x14001236a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140012052`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001208c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x140012052`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x14001208c`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140012313`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x140012313`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012257`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012257`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140012471`
- `OLEAUT32!__imp_SysStringLen` at `0x14001201e`
- `OLEAUT32!__imp_SysStringLen` at `0x14001201e`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x140012463`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSetChannelConfigProperty` at `0x140012463`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
int __fastcall SetChannelCommand::SetPropertyBoolean(
        __int64 a1,
        const wchar_t *a2,
        void *a3,
        _OWORD *a4,
        __int128 *a5,
        __int64 a6,
        __int128 *a7,
        EVT_CHANNEL_CONFIG_PROPERTY_ID PropertyId)
{
  int result; // eax
  int v12; // r9d
  UINT v13; // eax
  unsigned int ChannelProperty; // ebx
  HMODULE ModuleHandleW; // rax
  int v16; // ebx
  __int64 v17; // rbx
  __int64 v18; // rdi
  HANDLE StdHandle; // rax
  FILE *v20; // rax
  FILE *v21; // rax
  __int64 v22; // rdi
  BSTR *v23; // rbx
  FILE *v24; // rax
  __int16 v25; // ax
  bool v26; // cf
  DWORD LastError; // ebx
  const char *bIgnoreCase; // [rsp+20h] [rbp-C9h]
  char v29[16]; // [rsp+40h] [rbp-A9h] BYREF
  __int128 v30; // [rsp+50h] [rbp-99h] BYREF
  struct _EVT_VARIANT PropertyValue; // [rsp+60h] [rbp-89h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+70h] [rbp-79h] BYREF
  int v33; // [rsp+88h] [rbp-61h]
  __int64 v34; // [rsp+8Ch] [rbp-5Dh]
  char v35; // [rsp+94h] [rbp-55h]
  __int128 v36; // [rsp+98h] [rbp-51h]
  __int64 v37; // [rsp+A8h] [rbp-41h]
  _QWORD v38[4]; // [rsp+B0h] [rbp-39h] BYREF
  BSTR pbstr[2]; // [rsp+D0h] [rbp-19h] BYREF

  v29[0] = 0;
  PropertyValue = 0;
  PropertyValue.Type = 13;
  v30 = *a5;
  *(_OWORD *)pbstr = *a4;
  result = (unsigned __int8)CommandArguments::GetOptionBool(
                              *(_QWORD *)(a1 + 8),
                              (unsigned int)pbstr,
                              (unsigned int)&v30,
                              (_DWORD)a4,
                              (__int64)v29);
  PropertyValue.BooleanVal = (unsigned __int8)result;
  if ( v29[0] )
    goto LABEL_21;
  if ( !a6 )
    return result;
  v30 = *a7;
  XmlGetNodeText(pbstr, a6, &v30);
  if ( !pbstr[0] )
    return wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(pbstr);
  v13 = SysStringLen(pbstr[0]);
  if ( v13 != 1 )
  {
    if ( v13 != 4 )
      goto LABEL_7;
    if ( CompareStringOrdinal(pbstr[0], 4, L"true", 4, 1) != 2 )
      goto LABEL_14;
LABEL_13:
    PropertyValue.BooleanVal = 1;
    goto LABEL_10;
  }
  if ( *pbstr[0] == 49 )
    goto LABEL_13;
  if ( *pbstr[0] != 48 )
  {
LABEL_7:
    if ( v13 == 5 && CompareStringOrdinal(pbstr[0], 5, L"false", 5, 1) == 2 )
      goto LABEL_9;
LABEL_14:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, 0, 0, bIgnoreCase, 173, 0x23u, a2);
    throw (EvtException *)pExceptionObject;
  }
LABEL_9:
  PropertyValue.BooleanVal = 0;
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(pbstr);
  result = PropertyValue.BooleanVal;
LABEL_21:
  if ( PropertyId == EvtChannelConfigEnabled && result == 1 )
  {
    pbstr[0] = L"Q";
    pbstr[1] = (BSTR)1;
    *(_QWORD *)&v30 = L"Quiet";
    *((_QWORD *)&v30 + 1) = 5;
    if ( !(unsigned __int8)CommandArguments::GetOptionBool(
                             *(_QWORD *)(a1 + 8),
                             (unsigned int)&v30,
                             (unsigned int)pbstr,
                             v12,
                             (__int64)v29) )
    {
      v36 = 0;
      v37 = 0;
      pbstr[0] = 0;
      ChannelProperty = GetChannelProperty(a3, EvtChannelConfigType);
      if ( ChannelProperty )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
            ChannelProperty);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, ChannelProperty, 0, 0, bIgnoreCase, 190, 4u, a2);
        throw (EvtException *)pExceptionObject;
      }
      if ( (unsigned int)(*(_DWORD *)pbstr[0] - 2) <= 1 )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
        ModuleHandleW = GetModuleHandleW(0);
        LODWORD(bIgnoreCase) = 0;
        v16 = tlx::_AppendFormatMessageImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                v38,
                2560,
                ModuleHandleW,
                68);
        if ( v16 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              21,
              WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
              (unsigned int)v16);
          }
          pExceptionObject[0] = word_14003838A;
          pExceptionObject[1] = 0;
          pExceptionObject[2] = 0;
          v33 = v16;
          v34 = -1;
          v35 = 0;
          throw (EvtException *)pExceptionObject;
        }
        v17 = v38[0];
        v18 = (__int64)(v38[1] - v38[0]) >> 1;
        StdHandle = GetStdHandle(0xFFFFFFF5);
        *(_QWORD *)&v30 = v17;
        *((_QWORD *)&v30 + 1) = v18;
        FilePuts(StdHandle);
        v20 = o___acrt_iob_func_0(1u);
        fflush(v20);
        v21 = o___acrt_iob_func_0(0);
        fflush(v21);
        v22 = 5;
        v23 = pbstr;
        do
        {
          v24 = o___acrt_iob_func_0(0);
          v25 = _o_getwc(v24);
          if ( v25 == -1 )
            break;
          if ( v25 == 10 )
            break;
          *(_WORD *)v23 = v25;
          v23 = (BSTR *)((char *)v23 + 2);
          v26 = v22-- == 1;
        }
        while ( !v26 && v22 != 1 );
        *(_WORD *)v23 = 0;
        if ( (unsigned int)_o__wcsicmp(pbstr, L"yes") && (unsigned int)_o__wcsicmp(pbstr, L"y") )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 235);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 0xEBu, 0, 0, bIgnoreCase, 208, 5u, a2);
          throw (EvtException *)pExceptionObject;
        }
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
      }
      if ( (_QWORD)v36 )
        std::_Deallocate<16>(v36, v37 - v36);
    }
  }
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, LastError, 0, 0, bIgnoreCase, 215, 5u, a2);
    throw (EvtException *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x140011f60  push    rbp
0x140011f62  push    rbx
0x140011f63  push    rdi
0x140011f64  push    r12
0x140011f66  push    r14
0x140011f68  push    r15
0x140011f6a  lea     rbp, [rsp-0Fh]
0x140011f6f  sub     rsp, 0F8h
0x140011f76  mov     rax, cs:__security_cookie
0x140011f7d  xor     rax, rsp
0x140011f80  mov     [rbp+37h+var_40], rax
0x140011f84  mov     r12, r8
0x140011f87  mov     r14, rdx
0x140011f8a  mov     r15, rcx
0x140011f8d  mov     rax, [rbp+37h+arg_20]
0x140011f91  mov     rbx, [rbp+37h+arg_28]
0x140011f95  mov     rdi, [rbp+37h+arg_30]
0x140011f99  mov     [rsp+120h+var_E0], 0
0x140011f9e  xorps   xmm0, xmm0
0x140011fa1  movups  xmmword ptr [rsp+120h+PropertyValue], xmm0
0x140011fa6  mov     [rbp+37h+PropertyValue.Type], 0Dh
0x140011fad  movaps  xmm0, xmmword ptr [rax]
0x140011fb0  movdqa  [rsp+120h+var_D0], xmm0
0x140011fb6  movaps  xmm1, xmmword ptr [r9]
0x140011fba  movdqa  xmmword ptr [rbp+37h+pbstr], xmm1
0x140011fbf  lea     rax, [rsp+120h+var_E0]
0x140011fc4  mov     qword ptr [rsp+120h+bIgnoreCase], rax; char *
0x140011fc9  lea     r8, [rsp+120h+var_D0]
0x140011fce  lea     rdx, [rbp+37h+pbstr]
0x140011fd2  mov     rcx, [rcx+8]
0x140011fd6  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x140011fdb  movzx   eax, al
0x140011fde  mov     dword ptr [rsp+120h+PropertyValue], eax
0x140011fe2  cmp     [rsp+120h+var_E0], 0
0x140011fe7  jnz     loc_140012137
0x140011fed  test    rbx, rbx
0x140011ff0  jz      loc_14001211A
0x140011ff6  movaps  xmm0, xmmword ptr [rdi]
0x140011ff9  movdqa  [rsp+120h+var_D0], xmm0
0x140011fff  lea     r8, [rsp+120h+var_D0]
0x140012004  mov     rdx, rbx
0x140012007  lea     rcx, [rbp+37h+pbstr]
0x14001200b  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x140012010  nop
0x140012011  mov     rcx, [rbp+37h+pbstr]; pbstr
0x140012015  test    rcx, rcx
0x140012018  jz      loc_140012111
0x14001201e  call    cs:__imp_SysStringLen
0x140012024  mov     rcx, [rbp+37h+pbstr]; lpString1
0x140012028  mov     edi, 1
0x14001202d  cmp     eax, edi
0x14001202f  jnz     short loc_140012077
0x140012031  cmp     word ptr [rcx], 31h ; '1'
0x140012035  jz      short loc_140012097
0x140012037  cmp     word ptr [rcx], 30h ; '0'
0x14001203b  jz      short loc_14001205D
0x14001203d  cmp     eax, 5
0x140012040  jnz     short loc_14001209D
0x140012042  mov     [rsp+120h+bIgnoreCase], edi; bIgnoreCase
0x140012046  mov     r9d, eax; cchCount2
0x140012049  lea     r8, aFalse; "false"
0x140012050  mov     edx, eax; cchCount1
0x140012052  call    cs:__imp_CompareStringOrdinal
0x140012058  cmp     eax, 2
0x14001205b  jnz     short loc_14001209D
0x14001205d  mov     dword ptr [rsp+120h+PropertyValue], 0
0x140012065  lea     rcx, [rbp+37h+pbstr]
0x140012069  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x14001206e  mov     eax, dword ptr [rsp+120h+PropertyValue]
0x140012072  jmp     loc_14001213C
0x140012077  cmp     eax, 4
0x14001207a  jnz     short loc_14001203D
0x14001207c  mov     [rsp+120h+bIgnoreCase], edi; bIgnoreCase
0x140012080  mov     r9d, eax; cchCount2
0x140012083  lea     r8, aTrue; "true"
0x14001208a  mov     edx, eax; cchCount1
0x14001208c  call    cs:__imp_CompareStringOrdinal
0x140012092  cmp     eax, 2
0x140012095  jnz     short loc_14001209D
0x140012097  mov     dword ptr [rsp+120h+PropertyValue], edi
0x14001209b  jmp     short loc_140012065
0x14001209d  lea     rax, WPP_GLOBAL_Control
0x1400120a4  mov     ebx, 57h ; 'W'
0x1400120a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120b0  cmp     rcx, rax
0x1400120b3  jz      short loc_1400120DA
0x1400120b5  test    dword ptr [rcx+1Ch], 400000h
0x1400120bc  jz      short loc_1400120DA
0x1400120be  cmp     byte ptr [rcx+19h], 2
0x1400120c2  jb      short loc_1400120DA
0x1400120c4  lea     edx, [rbx-44h]
0x1400120c7  mov     r9d, ebx
0x1400120ca  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x1400120d1  mov     rcx, [rcx+10h]
0x1400120d5  call    WPP_SF_d
0x1400120da  mov     [rsp+120h+Src], r14; Src
0x1400120df  mov     [rsp+120h+var_F0], 23h ; '#'; unsigned int
0x1400120e7  mov     [rsp+120h+var_F8], 0ADh; int
0x1400120ef  xor     r9d, r9d; unsigned int
0x1400120f2  xor     r8d, r8d; unsigned int
0x1400120f5  mov     edx, ebx; unsigned int
0x1400120f7  lea     rcx, [rbp+37h+pExceptionObject]; this
0x1400120fb  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140012100  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012107  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x14001210b  call    _CxxThrowException_0
0x140012111  lea     rcx, [rbp+37h+pbstr]
0x140012115  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x14001211a  mov     rcx, [rbp+37h+var_40]
0x14001211e  xor     rcx, rsp; StackCookie
0x140012121  call    __security_check_cookie
0x140012126  add     rsp, 0F8h
0x14001212d  pop     r15
0x14001212f  pop     r14
0x140012131  pop     r12
0x140012133  pop     rdi
0x140012134  pop     rbx
0x140012135  pop     rbp
0x140012136  retn
0x140012137  mov     edi, 1
0x14001213c  cmp     [rbp+37h+PropertyId], 0
0x140012140  jnz     loc_140012455
0x140012146  cmp     eax, edi
0x140012148  jnz     loc_140012455
0x14001214e  lea     rax, aQ_0; "Q"
0x140012155  mov     [rbp+37h+pbstr], rax
0x140012159  mov     [rbp+37h+pbstr+8], rdi
0x14001215d  lea     rax, aQuiet; "Quiet"
0x140012164  mov     qword ptr [rsp+120h+var_D0], rax
0x140012169  mov     qword ptr [rsp+120h+var_D0+8], 5
0x140012172  lea     rax, [rsp+120h+var_E0]
0x140012177  mov     qword ptr [rsp+120h+bIgnoreCase], rax; char *
0x14001217c  lea     r8, [rbp+37h+pbstr]
0x140012180  lea     rdx, [rsp+120h+var_D0]
0x140012185  mov     rcx, [r15+8]
0x140012189  call    ?GetOptionBool@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0_NAEA_N@Z; CommandArguments::GetOptionBool(std::wstring_view,std::wstring_view,bool,bool &)
0x14001218e  test    al, al
0x140012190  jnz     loc_140012455
0x140012196  xorps   xmm0, xmm0
0x140012199  movdqu  [rbp+37h+var_88], xmm0
0x14001219e  mov     [rbp+37h+var_78], 0
0x1400121a6  mov     [rbp+37h+pbstr], 0
0x1400121ae  lea     r9, [rbp+37h+pbstr]
0x1400121b2  lea     r8, [rbp+37h+var_88]
0x1400121b6  mov     edx, 2; PropertyId
0x1400121bb  mov     rcx, r12; ChannelConfig
0x1400121be  call    ?GetChannelProperty@@YAKPEAXW4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@AEAV?$vector@EV?$allocator@E@std@@@std@@AEAPEAU_EVT_VARIANT@@@Z; GetChannelProperty(void *,_EVT_CHANNEL_CONFIG_PROPERTY_ID,std::vector<uchar> &,_EVT_VARIANT * &)
0x1400121c3  mov     ebx, eax
0x1400121c5  test    eax, eax
0x1400121c7  jz      short loc_14001223A
0x1400121c9  lea     rax, WPP_GLOBAL_Control
0x1400121d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400121d7  cmp     rcx, rax
0x1400121da  jz      short loc_140012203
0x1400121dc  test    dword ptr [rcx+1Ch], 400000h
0x1400121e3  jz      short loc_140012203
0x1400121e5  cmp     byte ptr [rcx+19h], 2
0x1400121e9  jb      short loc_140012203
0x1400121eb  mov     edx, 14h
0x1400121f0  mov     r9d, ebx
0x1400121f3  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x1400121fa  mov     rcx, [rcx+10h]
0x1400121fe  call    WPP_SF_d
0x140012203  mov     [rsp+120h+Src], r14; Src
0x140012208  mov     [rsp+120h+var_F0], 4; unsigned int
0x140012210  mov     [rsp+120h+var_F8], 0BEh; int
0x140012218  xor     r9d, r9d; unsigned int
0x14001221b  xor     r8d, r8d; unsigned int
0x14001221e  mov     edx, ebx; unsigned int
0x140012220  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140012224  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140012229  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140012230  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140012234  call    _CxxThrowException_0
0x14001223a  mov     rax, [rbp+37h+pbstr]
0x14001223e  mov     ecx, [rax]
0x140012240  sub     ecx, 2
0x140012243  cmp     ecx, edi
0x140012245  ja      loc_140012440
0x14001224b  lea     rcx, [rbp+37h+var_70]
0x14001224f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140012254  nop
0x140012255  xor     ecx, ecx; lpModuleName
0x140012257  call    cs:__imp_GetModuleHandleW
0x14001225d  mov     qword ptr [rsp+120h+var_F8], 0
0x140012266  mov     [rsp+120h+bIgnoreCase], 0; char *
0x14001226e  mov     r9d, 44h ; 'D'
0x140012274  mov     r8, rax
0x140012277  mov     edx, 0A00h
0x14001227c  lea     rcx, [rbp+37h+var_70]
0x140012280  call    ??$_AppendFormatMessageImpl@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@IPEBXIIPEAPEAD@Z; tlx::_AppendFormatMessageImpl<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,uint,void const *,uint,uint,char * *)
0x140012285  mov     ebx, eax
0x140012287  test    eax, eax
0x140012289  jns     short loc_140012300
0x14001228b  lea     rax, WPP_GLOBAL_Control
0x140012292  mov     rcx, cs:WPP_GLOBAL_Control
0x140012299  cmp     rcx, rax
0x14001229c  jz      short loc_1400122C5
0x14001229e  test    dword ptr [rcx+1Ch], 400000h
0x1400122a5  jz      short loc_1400122C5
0x1400122a7  cmp     byte ptr [rcx+19h], 2
0x1400122ab  jb      short loc_1400122C5
0x1400122ad  mov     edx, 15h
0x1400122b2  mov     r9d, ebx
0x1400122b5  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x1400122bc  mov     rcx, [rcx+10h]
0x1400122c0  call    WPP_SF_d
0x1400122c5  lea     rax, word_14003838A
0x1400122cc  mov     [rbp+37h+pExceptionObject], rax
0x1400122d0  mov     [rbp+37h+var_A8], 0
0x1400122d8  mov     [rbp+37h+var_A0], 0
0x1400122e0  mov     [rbp+37h+var_98], ebx
0x1400122e3  mov     [rbp+37h+var_94], 0FFFFFFFFFFFFFFFFh
0x1400122eb  mov     [rbp+37h+var_8C], 0
0x1400122ef  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400122f6  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x1400122fa  call    _CxxThrowException_0
0x140012300  mov     rdi, [rbp+37h+var_68]
0x140012304  mov     rbx, [rbp+37h+var_70]
0x140012308  sub     rdi, rbx
0x14001230b  sar     rdi, 1
0x14001230e  mov     ecx, 0FFFFFFF5h; nStdHandle
0x140012313  call    cs:__imp_GetStdHandle
0x140012319  mov     qword ptr [rsp+120h+var_D0], rbx
0x14001231e  mov     qword ptr [rsp+120h+var_D0+8], rdi
0x140012323  lea     rdx, [rsp+120h+var_D0]
0x140012328  mov     rcx, rax; hFile
0x14001232b  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x140012330  mov     ecx, 1; Ix
0x140012335  call    _o___acrt_iob_func_0
0x14001233a  mov     rcx, rax; Stream
0x14001233d  call    cs:__imp_fflush
0x140012343  xor     ecx, ecx; Ix
0x140012345  call    _o___acrt_iob_func_0
0x14001234a  mov     rcx, rax; Stream
0x14001234d  call    cs:__imp_fflush
0x140012353  mov     r15d, 5
0x140012359  mov     edi, r15d
0x14001235c  lea     rbx, [rbp+37h+pbstr]
0x140012360  xor     ecx, ecx; Ix
0x140012362  call    _o___acrt_iob_func_0
0x140012367  mov     rcx, rax
0x14001236a  call    cs:__imp__o_getwc
0x140012370  mov     ecx, 0FFFFh
0x140012375  cmp     ax, cx
0x140012378  jz      short loc_140012390
0x14001237a  cmp     ax, 0Ah
0x14001237e  jz      short loc_140012390
0x140012380  mov     [rbx], ax
0x140012383  add     rbx, 2
0x140012387  dec     rdi
0x14001238a  cmp     rdi, 1
0x14001238e  ja      short loc_140012360
0x140012390  xor     eax, eax
0x140012392  mov     [rbx], ax
0x140012395  lea     rdx, aYes; "yes"
0x14001239c  lea     rcx, [rbp+37h+pbstr]
0x1400123a0  call    cs:__imp__o__wcsicmp
0x1400123a6  test    eax, eax
0x1400123a8  jz      loc_140012436
0x1400123ae  lea     rdx, aY; "y"
0x1400123b5  lea     rcx, [rbp+37h+pbstr]
0x1400123b9  call    cs:__imp__o__wcsicmp
0x1400123bf  test    eax, eax
0x1400123c1  jz      short loc_140012436
0x1400123c3  lea     rax, WPP_GLOBAL_Control
0x1400123ca  mov     ebx, 0EBh
0x1400123cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400123d6  cmp     rcx, rax
0x1400123d9  jz      short loc_140012402
0x1400123db  test    dword ptr [rcx+1Ch], 400000h
0x1400123e2  jz      short loc_140012402
0x1400123e4  cmp     byte ptr [rcx+19h], 2
0x1400123e8  jb      short loc_140012402
0x1400123ea  mov     edx, 16h
0x1400123ef  mov     r9d, ebx
0x1400123f2  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x1400123f9  mov     rcx, [rcx+10h]
0x1400123fd  call    WPP_SF_d
0x140012402  mov     [rsp+120h+Src], r14; Src
0x140012407  mov     [rsp+120h+var_F0], r15d; unsigned int
0x14001240c  mov     [rsp+120h+var_F8], 0D0h; int
0x140012414  xor     r9d, r9d; unsigned int
0x140012417  xor     r8d, r8d; unsigned int
0x14001241a  mov     edx, ebx; unsigned int
0x14001241c  lea     rcx, [rbp+37h+pExceptionObject]; this
0x140012420  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140012425  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001242c  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x140012430  call    _CxxThrowException_0
0x140012436  lea     rcx, [rbp+37h+var_70]
0x14001243a  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14001243f  nop
0x140012440  mov     rcx, qword ptr [rbp+37h+var_88]
0x140012444  test    rcx, rcx
0x140012447  jz      short loc_140012455
0x140012449  mov     rdx, [rbp+37h+var_78]
0x14001244d  sub     rdx, rcx
0x140012450  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140012455  lea     r9, [rsp+120h+PropertyValue]; PropertyValue
  ... truncated ...
```
