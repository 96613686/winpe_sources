# SetChannelCommand::Execute(void)

- ea: `0x14000fc50`
- end: `0x1400100d5`
- name: `?Execute@SetChannelCommand@@UEAAXXZ`
- size: `1157`
- prototype: `void __fastcall(SetChannelCommand *__hidden this)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000d144`
- `0x14000d868`
- `0x14000d900`
- `0x14000fc50`
- `0x140010450`
- `0x140010704`
- `0x140011570`
- `0x14001159c`
- `0x1400163cc`
- `0x140019c4c`
- `0x140021b00`
- `0x140022cec`
- `0x140023c6c`
- `0x140024b00`
- `0x140027930`
- `0x140027f70`
- `0x140028fc0`
- `0x140031810`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14000ffaa`
- `api-ms-win-core-processenvironment-l1-1-0!GetStdHandle` at `0x14000ffaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fe72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ff23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001000c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fe72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ff23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001000c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400100ab`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400100ab`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000fc7f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14000fc7f`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x14000fe5c`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x14000fe5c`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x14000ff15`
- `ext-ms-win-wevtapi-eventlog-l1-1-2!EvtSaveChannelConfig` at `0x14000ff15`

## string_xrefs

- `0x14000fd1d`: `Config`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall SetChannelCommand::Execute(SetChannelCommand *this)
{
  HRESULT v2; // eax
  unsigned int v3; // edi
  struct IXMLDOMElement *v4; // rbx
  __int64 v5; // rcx
  struct IXMLDOMElement **v6; // rax
  const WCHAR *v7; // rdi
  const WCHAR *v8; // rdx
  EVT_HANDLE v9; // rax
  void *v10; // r14
  DWORD LastError; // edi
  char *Src; // rsi
  HANDLE StdHandle; // rsi
  unsigned __int64 v14; // rdx
  __int128 *p_pExceptionObject; // rcx
  DWORD v16; // esi
  const char *v17; // [rsp+20h] [rbp-79h]
  __int128 v18; // [rsp+40h] [rbp-59h] BYREF
  char v19; // [rsp+51h] [rbp-48h]
  struct IXMLDOMElement *v20; // [rsp+58h] [rbp-41h] BYREF
  _QWORD v21[2]; // [rsp+60h] [rbp-39h] BYREF
  char v22[16]; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v23[40]; // [rsp+80h] [rbp-19h] BYREF
  __int128 pExceptionObject; // [rsp+A8h] [rbp+Fh] BYREF
  unsigned __int64 v25; // [rsp+B8h] [rbp+1Fh]
  unsigned __int64 v26; // [rsp+C0h] [rbp+27h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        WPP_2969cf25331937701283eddb1dcf16ae_Traceguids,
        (unsigned int)v2);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, v3, 0, 0, v17, 520, 3u, 0);
    throw (EvtException *)&pExceptionObject;
  }
  v19 = 1;
  v4 = 0;
  v20 = 0;
  v21[0] = L"C";
  v21[1] = 1;
  *(_QWORD *)&v18 = L"Config";
  *((_QWORD *)&v18 + 1) = 6;
  if ( (unsigned __int8)CommandArguments::HasOption(*((_QWORD *)this + 1), &v18, v21) )
  {
    v6 = (struct IXMLDOMElement **)SetChannelCommand::OpenConfig(v5, &v18);
    if ( &v20 != v6 )
    {
      v4 = *v6;
      *v6 = 0;
      v20 = v4;
    }
    if ( (_QWORD)v18 )
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v18);
    *(_QWORD *)&v18 = L"@name";
    *((_QWORD *)&v18 + 1) = 5;
    XmlGetNodeText(v21, v4, &v18);
    if ( !v21[0] )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, 2147942487LL);
      }
      EvtException::EvtException((EvtException *)&pExceptionObject, 0x80070057, 0, 0, v17, 536, 0x21u, L"@name");
      throw (EvtException *)&pExceptionObject;
    }
    v7 = (const WCHAR *)((char *)this + 40);
    std::wstring::assign((char *)this + 40);
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(v21);
  }
  else
  {
    v7 = (const WCHAR *)((char *)this + 40);
  }
  if ( *((_QWORD *)v7 + 3) <= 7u )
    v8 = v7;
  else
    v8 = *(const WCHAR **)v7;
  v9 = EvtOpenChannelConfig(*((EVT_HANDLE *)this + 3), v8, 0);
  v10 = v9;
  v21[0] = v9;
  if ( !v9 )
  {
    LastError = GetLastError();
    if ( !LastError )
      LastError = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, LastError);
    }
    Src = (char *)this + 40;
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(char **)Src;
    EvtException::EvtException(
      (EvtException *)&pExceptionObject,
      LastError,
      0,
      0,
      v17,
      545,
      0x1Du,
      (const wchar_t *)Src);
    throw (EvtException *)&pExceptionObject;
  }
  SetChannelCommand::SetProperties(this, v9, v4);
  if ( !EvtSaveChannelConfig(v10, 0) )
  {
    GetLastError();
    pExceptionObject = 0;
    v25 = 0;
    v26 = 7;
    LOWORD(pExceptionObject) = 0;
    if ( !(unsigned int)GetExtendedStatus(&pExceptionObject) && v25 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids);
      }
      StdHandle = GetStdHandle(0xFFFFFFF4);
      v14 = v25;
      if ( v25 >= v26 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__QEAAX_W_Z__W___basic_string__WU__char_traits__W_std__V__allocator__W_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAX_W_Z__W_Z(&pExceptionObject);
      }
      else
      {
        ++v25;
        p_pExceptionObject = &pExceptionObject;
        if ( v26 > 7 )
          p_pExceptionObject = (__int128 *)pExceptionObject;
        *(_DWORD *)((char *)p_pExceptionObject + 2 * v14) = 10;
      }
      v18 = *(_OWORD *)std::wstring::operator std::wstring_view(&pExceptionObject, v22);
      FilePuts(StdHandle, &v18);
    }
    v16 = GetLastError();
    if ( !v16 )
      v16 = 1287;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids, v16);
    }
    if ( *((_QWORD *)v7 + 3) > 7u )
      v7 = *(const WCHAR **)v7;
    EvtException::EvtException((EvtException *)v23, v16, 0, 0, v17, 563, 0x1Eu, v7);
    throw (EvtException *)v23;
  }
  tlx::unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&int EvtClose(void *),0>>(v21);
  if ( v4 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v20);
  CoUninitialize();
}

```

## disassembly

```asm
0x14000fc50  mov     [rsp-8+arg_8], rbx
0x14000fc55  mov     [rsp-8+arg_10], rsi
0x14000fc5a  push    rbp
0x14000fc5b  push    rdi
0x14000fc5c  push    r14
0x14000fc5e  lea     rbp, [rsp-47h]
0x14000fc63  sub     rsp, 0E0h
0x14000fc6a  mov     rax, cs:__security_cookie
0x14000fc71  xor     rax, rsp
0x14000fc74  mov     [rbp+57h+var_20], rax
0x14000fc78  mov     rsi, rcx
0x14000fc7b  xor     edx, edx; dwCoInit
0x14000fc7d  xor     ecx, ecx; pvReserved
0x14000fc7f  call    cs:__imp_CoInitializeEx
0x14000fc85  mov     edi, eax
0x14000fc87  test    eax, eax
0x14000fc89  jns     short loc_14000FD00
0x14000fc8b  lea     rbx, WPP_GLOBAL_Control
0x14000fc92  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc99  cmp     rcx, rbx
0x14000fc9c  jz      short loc_14000FCC5
0x14000fc9e  test    dword ptr [rcx+1Ch], 400000h
0x14000fca5  jz      short loc_14000FCC5
0x14000fca7  cmp     byte ptr [rcx+19h], 2
0x14000fcab  jb      short loc_14000FCC5
0x14000fcad  mov     edx, 21h ; '!'
0x14000fcb2  mov     r9d, eax
0x14000fcb5  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14000fcbc  mov     rcx, [rcx+10h]
0x14000fcc0  call    WPP_SF_d
0x14000fcc5  mov     [rsp+0F0h+Src], 0; Src
0x14000fcce  mov     [rsp+0F0h+var_C0], 3; unsigned int
0x14000fcd6  mov     [rsp+0F0h+var_C8], 208h; int
0x14000fcde  xor     r9d, r9d; unsigned int
0x14000fce1  xor     r8d, r8d; unsigned int
0x14000fce4  mov     edx, edi; unsigned int
0x14000fce6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000fcea  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000fcef  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000fcf6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000fcfa  call    _CxxThrowException_0
0x14000fd00  mov     [rbp+57h+var_9F], 1
0x14000fd04  xor     ebx, ebx
0x14000fd06  mov     [rbp+57h+var_98], rbx
0x14000fd0a  lea     rax, aC_0; "C"
0x14000fd11  mov     [rbp+57h+var_90], rax
0x14000fd15  mov     [rbp+57h+var_88], 1
0x14000fd1d  lea     rax, aConfig; "Config"
0x14000fd24  mov     qword ptr [rbp+57h+var_B0], rax
0x14000fd28  mov     qword ptr [rbp+57h+var_B0+8], 6
0x14000fd30  lea     r8, [rbp+57h+var_90]
0x14000fd34  lea     rdx, [rbp+57h+var_B0]
0x14000fd38  mov     rcx, [rsi+8]
0x14000fd3c  call    ?HasOption@CommandArguments@@QEBA_NV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0@Z; CommandArguments::HasOption(std::wstring_view,std::wstring_view)
0x14000fd41  test    al, al
0x14000fd43  jz      loc_14000FE42
0x14000fd49  lea     r8, [rsi+48h]
0x14000fd4d  cmp     qword ptr [r8+18h], 7
0x14000fd52  jbe     short loc_14000FD57
0x14000fd54  mov     r8, [r8]
0x14000fd57  lea     rdx, [rbp+57h+var_B0]
0x14000fd5b  call    ?OpenConfig@SetChannelCommand@@AEAA?AU?$com_ptr@UIXMLDOMElement@@@winrt@@PEB_W@Z; SetChannelCommand::OpenConfig(wchar_t const *)
0x14000fd60  lea     rcx, [rbp+57h+var_98]
0x14000fd64  cmp     rcx, rax
0x14000fd67  jz      short loc_14000FD77
0x14000fd69  mov     rbx, [rax]
0x14000fd6c  mov     qword ptr [rax], 0
0x14000fd73  mov     [rbp+57h+var_98], rbx
0x14000fd77  cmp     qword ptr [rbp+57h+var_B0], 0
0x14000fd7c  jz      short loc_14000FD87
0x14000fd7e  lea     rcx, [rbp+57h+var_B0]
0x14000fd82  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x14000fd87  lea     r14, aName; "@name"
0x14000fd8e  mov     qword ptr [rbp+57h+var_B0], r14
0x14000fd92  mov     qword ptr [rbp+57h+var_B0+8], 5
0x14000fd9a  lea     r8, [rbp+57h+var_B0]
0x14000fd9e  mov     rdx, rbx
0x14000fda1  lea     rcx, [rbp+57h+var_90]
0x14000fda5  call    ?XmlGetNodeText@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIXMLDOMNode@@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; XmlGetNodeText(IXMLDOMNode *,std::wstring_view)
0x14000fdaa  nop
0x14000fdab  mov     rdx, [rbp+57h+var_90]
0x14000fdaf  test    rdx, rdx
0x14000fdb2  jnz     short loc_14000FE2A
0x14000fdb4  lea     rbx, WPP_GLOBAL_Control
0x14000fdbb  mov     edi, 80070057h
0x14000fdc0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fdc7  cmp     rcx, rbx
0x14000fdca  jz      short loc_14000FDF3
0x14000fdcc  test    dword ptr [rcx+1Ch], 400000h
0x14000fdd3  jz      short loc_14000FDF3
0x14000fdd5  cmp     byte ptr [rcx+19h], 2
0x14000fdd9  jb      short loc_14000FDF3
0x14000fddb  mov     edx, 22h ; '"'
0x14000fde0  mov     r9d, edi
0x14000fde3  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14000fdea  mov     rcx, [rcx+10h]
0x14000fdee  call    WPP_SF_d
0x14000fdf3  mov     [rsp+0F0h+Src], r14; Src
0x14000fdf8  mov     [rsp+0F0h+var_C0], 21h ; '!'; unsigned int
0x14000fe00  mov     [rsp+0F0h+var_C8], 218h; int
0x14000fe08  xor     r9d, r9d; unsigned int
0x14000fe0b  xor     r8d, r8d; unsigned int
0x14000fe0e  mov     edx, edi; unsigned int
0x14000fe10  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000fe14  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000fe19  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000fe20  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000fe24  call    _CxxThrowException_0
0x14000fe2a  lea     rdi, [rsi+28h]
0x14000fe2e  mov     rcx, rdi
0x14000fe31  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x14000fe36  nop
0x14000fe37  lea     rcx, [rbp+57h+var_90]
0x14000fe3b  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x14000fe40  jmp     short loc_14000FE46
0x14000fe42  lea     rdi, [rsi+28h]
0x14000fe46  cmp     qword ptr [rdi+18h], 7
0x14000fe4b  jbe     short loc_14000FE52
0x14000fe4d  mov     rdx, [rdi]
0x14000fe50  jmp     short loc_14000FE55
0x14000fe52  mov     rdx, rdi; ChannelPath
0x14000fe55  xor     r8d, r8d; Flags
0x14000fe58  mov     rcx, [rsi+18h]; Session
0x14000fe5c  call    cs:__imp_EvtOpenChannelConfig
0x14000fe62  mov     r14, rax
0x14000fe65  mov     [rbp+57h+var_90], rax
0x14000fe69  test    rax, rax
0x14000fe6c  jnz     loc_14000FF02
0x14000fe72  call    cs:__imp_GetLastError
0x14000fe78  mov     edi, eax
0x14000fe7a  mov     eax, 507h
0x14000fe7f  test    edi, edi
0x14000fe81  cmovz   edi, eax
0x14000fe84  lea     rbx, WPP_GLOBAL_Control
0x14000fe8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe92  cmp     rcx, rbx
0x14000fe95  jz      short loc_14000FEBD
0x14000fe97  test    dword ptr [rcx+1Ch], 400000h
0x14000fe9e  jz      short loc_14000FEBD
0x14000fea0  cmp     byte ptr [rcx+19h], 2
0x14000fea4  jb      short loc_14000FEBD
0x14000fea6  lea     edx, [r14+23h]
0x14000feaa  mov     r9d, edi
0x14000fead  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14000feb4  mov     rcx, [rcx+10h]
0x14000feb8  call    WPP_SF_d
0x14000febd  add     rsi, 28h ; '('
0x14000fec1  cmp     qword ptr [rsi+18h], 7
0x14000fec6  jbe     short loc_14000FECB
0x14000fec8  mov     rsi, [rsi]
0x14000fecb  mov     [rsp+0F0h+Src], rsi; Src
0x14000fed0  mov     [rsp+0F0h+var_C0], 1Dh; unsigned int
0x14000fed8  mov     [rsp+0F0h+var_C8], 221h; int
0x14000fee0  xor     r9d, r9d; unsigned int
0x14000fee3  xor     r8d, r8d; unsigned int
0x14000fee6  mov     edx, edi; unsigned int
0x14000fee8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000feec  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x14000fef1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000fef8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000fefc  call    _CxxThrowException_0
0x14000ff02  mov     r8, rbx; struct IXMLDOMElement *
0x14000ff05  mov     rdx, r14; void *
0x14000ff08  mov     rcx, rsi; this
0x14000ff0b  call    ?SetProperties@SetChannelCommand@@AEAAXPEAXPEAUIXMLDOMElement@@@Z; SetChannelCommand::SetProperties(void *,IXMLDOMElement *)
0x14000ff10  xor     edx, edx; Flags
0x14000ff12  mov     rcx, r14; ChannelConfig
0x14000ff15  call    cs:__imp_EvtSaveChannelConfig
0x14000ff1b  test    eax, eax
0x14000ff1d  jnz     loc_140010092
0x14000ff23  call    cs:__imp_GetLastError
0x14000ff29  xorps   xmm0, xmm0
0x14000ff2c  movups  [rbp+57h+pExceptionObject], xmm0
0x14000ff30  mov     [rbp+57h+var_38], 0
0x14000ff38  mov     [rbp+57h+var_30], 7
0x14000ff40  xor     eax, eax
0x14000ff42  mov     word ptr [rbp+57h+pExceptionObject], ax
0x14000ff46  lea     rcx, [rbp+57h+pExceptionObject]
0x14000ff4a  call    ?GetExtendedStatus@@YAKAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; GetExtendedStatus(std::wstring &)
0x14000ff4f  lea     rbx, WPP_GLOBAL_Control
0x14000ff56  test    eax, eax
0x14000ff58  jnz     loc_14001000C
0x14000ff5e  cmp     [rbp+57h+var_38], 0
0x14000ff63  jbe     loc_14001000C
0x14000ff69  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ff70  cmp     rcx, rbx
0x14000ff73  jz      short loc_14000FFA5
0x14000ff75  test    dword ptr [rcx+1Ch], 400000h
0x14000ff7c  jz      short loc_14000FFA5
0x14000ff7e  cmp     byte ptr [rcx+19h], 2
0x14000ff82  jb      short loc_14000FFA5
0x14000ff84  lea     r9, [rbp+57h+pExceptionObject]
0x14000ff88  cmp     [rbp+57h+var_30], 7
0x14000ff8d  cmova   r9, qword ptr [rbp+57h+pExceptionObject]
0x14000ff92  lea     edx, [rax+24h]
0x14000ff95  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x14000ff9c  mov     rcx, [rcx+10h]
0x14000ffa0  call    WPP_SF_S
0x14000ffa5  mov     ecx, 0FFFFFFF4h; nStdHandle
0x14000ffaa  call    cs:__imp_GetStdHandle
0x14000ffb0  mov     rsi, rax
0x14000ffb3  mov     rdx, [rbp+57h+var_38]
0x14000ffb7  cmp     rdx, [rbp+57h+var_30]
0x14000ffbb  jnb     short loc_14000FFDC
0x14000ffbd  lea     rcx, [rdx+1]
0x14000ffc1  mov     [rbp+57h+var_38], rcx
0x14000ffc5  lea     rcx, [rbp+57h+pExceptionObject]
0x14000ffc9  cmp     [rbp+57h+var_30], 7
0x14000ffce  cmova   rcx, qword ptr [rbp+57h+pExceptionObject]
0x14000ffd3  mov     dword ptr [rcx+rdx*2], 0Ah
0x14000ffda  jmp     short loc_14000FFEB
0x14000ffdc  mov     r9d, 0Ah
0x14000ffe2  lea     rcx, [rbp+57h+pExceptionObject]; Src
0x14000ffe6  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAX_W@Z@_W@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t>(unsigned __int64,`std::wstring::push_back(wchar_t)'::`2'::_lambda_1_,wchar_t)
0x14000ffeb  lea     rdx, [rbp+57h+var_80]
0x14000ffef  lea     rcx, [rbp+57h+pExceptionObject]
0x14000fff3  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x14000fff8  movups  xmm0, xmmword ptr [rax]
0x14000fffb  movdqu  [rbp+57h+var_B0], xmm0
0x140010000  lea     rdx, [rbp+57h+var_B0]
0x140010004  mov     rcx, rsi; hFile
0x140010007  call    ?FilePuts@@YAJPEAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; FilePuts(void *,std::wstring_view)
0x14001000c  call    cs:__imp_GetLastError
0x140010012  mov     esi, eax
0x140010014  mov     eax, 507h
0x140010019  test    esi, esi
0x14001001b  cmovz   esi, eax
0x14001001e  mov     rcx, cs:WPP_GLOBAL_Control
0x140010025  cmp     rcx, rbx
0x140010028  jz      short loc_140010051
0x14001002a  test    dword ptr [rcx+1Ch], 400000h
0x140010031  jz      short loc_140010051
0x140010033  cmp     byte ptr [rcx+19h], 2
0x140010037  jb      short loc_140010051
0x140010039  mov     edx, 25h ; '%'
0x14001003e  mov     r9d, esi
0x140010041  lea     r8, WPP_2969cf25331937701283eddb1dcf16ae_Traceguids
0x140010048  mov     rcx, [rcx+10h]
0x14001004c  call    WPP_SF_d
0x140010051  cmp     qword ptr [rdi+18h], 7
0x140010056  jbe     short loc_14001005B
0x140010058  mov     rdi, [rdi]
0x14001005b  mov     [rsp+0F0h+Src], rdi; Src
0x140010060  mov     [rsp+0F0h+var_C0], 1Eh; unsigned int
0x140010068  mov     [rsp+0F0h+var_C8], 233h; int
0x140010070  xor     r9d, r9d; unsigned int
0x140010073  xor     r8d, r8d; unsigned int
0x140010076  mov     edx, esi; unsigned int
0x140010078  lea     rcx, [rbp+57h+var_70]; this
0x14001007c  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140010081  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010088  lea     rcx, [rbp+57h+var_70]; pExceptionObject
0x14001008c  call    _CxxThrowException_0
0x140010092  lea     rcx, [rbp+57h+var_90]
0x140010096  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6AHPEAX@Z$1?EvtClose@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>::~unique_any<tlx::handle_traits<void *,int (void *),&EvtClose(void *),0>>(void)
0x14001009b  nop
0x14001009c  test    rbx, rbx
0x14001009f  jz      short loc_1400100AB
0x1400100a1  lea     rcx, [rbp+57h+var_98]
0x1400100a5  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x1400100aa  nop
0x1400100ab  call    cs:__imp_CoUninitialize
0x1400100b1  mov     rcx, [rbp+57h+var_20]
0x1400100b5  xor     rcx, rsp; StackCookie
0x1400100b8  call    __security_check_cookie
0x1400100bd  lea     r11, [rsp+0F0h+var_10]
0x1400100c5  mov     rbx, [r11+28h]
0x1400100c9  mov     rsi, [r11+30h]
0x1400100cd  mov     rsp, r11
0x1400100d0  pop     r14
0x1400100d2  pop     rdi
0x1400100d3  pop     rbp
0x1400100d4  retn
```
