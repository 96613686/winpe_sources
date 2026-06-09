# ToastHelper::LoadSmartAppControlToastBodyResourceToXml(uint,Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *)

- ea: `0x180030688`
- end: `0x180030a24`
- name: `?LoadSmartAppControlToastBodyResourceToXml@ToastHelper@@CAJIPEAUIXmlDocument@Dom@Xml@Data@Windows@@PEBG1@Z`
- size: `924`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::Data::Xml::Dom::IXmlDocument *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ff7c`

## callees

- `0x1800049d0`
- `0x180006814`
- `0x180006d00`
- `0x1800159a0`
- `0x18001f038`
- `0x18002084c`
- `0x180020a6c`
- `0x180021ec0`
- `0x18002f8f8`
- `0x18002f964`
- `0x18002fabc`
- `0x18002fb7c`
- `0x180030688`
- `0x180030a2c`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030842`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180030842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030894`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030894`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003088a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003088a`

## string_xrefs

- `0x18003072e`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x18003076d`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x1800307e1`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x180030813`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x1800308b7`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x180030931`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`
- `0x1800309ac`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ToastHelper::LoadSmartAppControlToastBodyResourceToXml(
        UINT a1,
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  va_list v6; // r8
  va_list v7; // r9
  __int64 (__fastcall ***v8)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *); // rdx
  int v9; // eax
  signed int v10; // ebx
  int v11; // eax
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // r14
  __int64 v14; // rax
  int v15; // eax
  int StringResource; // eax
  LPCVOID *v17; // rdx
  signed int LastError; // eax
  __int64 (__fastcall *v19)(struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD, __int64 *); // rbx
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, _QWORD, __int64 *); // rdi
  __int64 v25; // rcx
  _QWORD *v26; // rax
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  int lpBuffera; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL v34; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  va_list Arguments[2]; // [rsp+70h] [rbp-90h] BYREF
  LPCVOID lpSource[4]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  WCHAR sourceString[128]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  std::wstring::wstring(lpSource, a2, a3, a4);
  v33 = 0;
  v32 = 0;
  v31 = 0;
  v35 = 0;
  hMem = 0;
  Arguments[0] = v6;
  Arguments[1] = v7;
  v9 = (**v8)(a2, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v33);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = StringCchPrintfW(sourceString, 0x80u, L"/toast/visual/binding/text[number(@id) = '%d']", a1);
    v10 = v11;
    if ( v11 >= 0 )
    {
      v12 = v33;
      v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 48LL);
      v32 = 0;
      v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
      v15 = v13(v12, *(_QWORD *)(v14 + 24), &v32);
      v10 = v15;
      v39 = 0;
      if ( v15 >= 0 )
      {
        StringResource = ToastHelper::LoadStringResource(a1, (LPWSTR)lpSource);
        v10 = StringResource;
        if ( StringResource >= 0 )
        {
          hMem = 0;
          v17 = lpSource;
          if ( lpSource[3] > (LPCVOID)7 )
            v17 = (LPCVOID *)lpSource[0];
          if ( FormatMessageW(0x2500u, v17, 0, 0, (LPWSTR)&hMem, 0, Arguments) )
          {
            v19 = *(__int64 (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD, __int64 *))(*(_QWORD *)a2 + 88LL);
            v20 = v31;
            v31 = 0;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v34 = hMem;
            v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v34);
            v22 = v19(a2, *(_QWORD *)(v21 + 24), &v31);
            v10 = v22;
            v39 = 0;
            if ( v22 >= 0 )
            {
              v23 = v32;
              v24 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 176LL);
              v25 = v35;
              v35 = 0;
              if ( v25 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
              v26 = (_QWORD *)wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlAttribute,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNode>(
                                &v31,
                                &v34);
              v10 = v24(v23, *v26, &v35);
              wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v34);
              if ( v10 >= 0 )
                v10 = 0;
              else
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xBD,
                  (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
                  (const char *)(unsigned int)v10,
                  lpBuffera);
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xBB,
                (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
                (const char *)(unsigned int)v22,
                lpBuffera);
            }
          }
          else
          {
            LastError = GetLastError();
            v10 = LastError;
            if ( LastError > 0 )
              v10 = (unsigned __int16)LastError | 0x80070000;
            if ( v10 < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xB9,
                (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
                (const char *)(unsigned int)v10,
                lpBuffera);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB0,
            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
            (const char *)(unsigned int)StringResource,
            lpBuffer);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xAE,
          (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
          (const char *)(unsigned int)v15,
          lpBuffer);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
        (const char *)(unsigned int)v11,
        lpBuffer);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
      (const char *)(unsigned int)v9,
      lpBuffer);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v35);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v31);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v32);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v33);
  std::wstring::~wstring(lpSource);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180030688  push    rbp
0x18003068a  push    rbx
0x18003068b  push    rsi
0x18003068c  push    rdi
0x18003068d  push    r14
0x18003068f  push    r15
0x180030691  lea     rbp, [rsp-0D8h]
0x180030699  sub     rsp, 1D8h
0x1800306a0  mov     rax, cs:__security_cookie
0x1800306a7  xor     rax, rsp
0x1800306aa  mov     [rbp+100h+var_40], rax
0x1800306b1  mov     rdi, rdx
0x1800306b4  mov     esi, ecx
0x1800306b6  lea     rcx, [rbp+100h+lpSource]
0x1800306ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800306bf  nop
0x1800306c0  xor     r15d, r15d
0x1800306c3  mov     [rsp+200h+var_1A8], r15
0x1800306c8  mov     [rsp+200h+var_1B0], r15
0x1800306cd  mov     [rsp+200h+var_1B8], r15
0x1800306d2  mov     [rsp+200h+var_198], r15
0x1800306d7  mov     [rsp+200h+hMem], r15
0x1800306dc  mov     [rsp+200h+var_190], r8
0x1800306e1  mov     [rsp+200h+var_188], r9
0x1800306e6  mov     rax, [rdx]
0x1800306e9  mov     rbx, [rax]
0x1800306ec  mov     rcx, [rsp+200h+var_1A8]
0x1800306f1  mov     [rsp+200h+var_1A8], r15
0x1800306f6  test    rcx, rcx
0x1800306f9  jz      short loc_180030707
0x1800306fb  mov     rax, [rcx]
0x1800306fe  mov     rax, [rax+10h]
0x180030702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030707  lea     r8, [rsp+200h+var_1A8]
0x18003070c  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x180030713  mov     rcx, rdi
0x180030716  mov     rax, rbx
0x180030719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003071e  mov     ebx, eax
0x180030720  test    eax, eax
0x180030722  jns     short loc_180030745
0x180030724  mov     rcx, [rbp+108h]; this
0x18003072b  mov     r9d, eax; char *
0x18003072e  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030735  mov     edx, 0AAh; void *
0x18003073a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003073f  nop
0x180030740  jmp     loc_1800309C3
0x180030745  mov     r9d, esi
0x180030748  lea     r8, aToastVisualBin; "/toast/visual/binding/text[number(@id) "...
0x18003074f  mov     edx, 80h; unsigned __int64
0x180030754  lea     rcx, [rbp+100h+sourceString]; unsigned __int16 *
0x180030758  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003075d  mov     ebx, eax
0x18003075f  test    eax, eax
0x180030761  jns     short loc_180030784
0x180030763  mov     rcx, [rbp+108h]; this
0x18003076a  mov     r9d, eax; char *
0x18003076d  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030774  mov     edx, 0ACh; void *
0x180030779  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003077e  nop
0x18003077f  jmp     loc_1800309C3
0x180030784  mov     rbx, [rsp+200h+var_1A8]
0x180030789  mov     rax, [rbx]
0x18003078c  mov     r14, [rax+30h]
0x180030790  mov     rcx, [rsp+200h+var_1B0]
0x180030795  mov     [rsp+200h+var_1B0], r15
0x18003079a  test    rcx, rcx
0x18003079d  jz      short loc_1800307AB
0x18003079f  mov     rax, [rcx]
0x1800307a2  mov     rax, [rax+10h]
0x1800307a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307ab  lea     rdx, [rbp+100h+sourceString]; sourceString
0x1800307af  lea     rcx, [rbp+100h+hstringHeader]; hstringHeader
0x1800307b3  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x1800307b8  nop
0x1800307b9  lea     r8, [rsp+200h+var_1B0]
0x1800307be  mov     rdx, [rax+18h]
0x1800307c2  mov     rcx, rbx
0x1800307c5  mov     rax, r14
0x1800307c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307cd  mov     ebx, eax
0x1800307cf  mov     [rbp+100h+var_148], r15
0x1800307d3  test    eax, eax
0x1800307d5  jns     short loc_1800307F8
0x1800307d7  mov     rcx, [rbp+108h]; this
0x1800307de  mov     r9d, eax; char *
0x1800307e1  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x1800307e8  mov     edx, 0AEh; void *
0x1800307ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800307f2  nop
0x1800307f3  jmp     loc_1800309C3
0x1800307f8  lea     rdx, [rbp+100h+lpSource]; lpBuffer
0x1800307fc  mov     ecx, esi; uID
0x1800307fe  call    ?LoadStringResource@ToastHelper@@CAJIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ToastHelper::LoadStringResource(uint,std::wstring &)
0x180030803  mov     ebx, eax
0x180030805  test    eax, eax
0x180030807  jns     short loc_18003082A
0x180030809  mov     rcx, [rbp+108h]; this
0x180030810  mov     r9d, eax; char *
0x180030813  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x18003081a  mov     edx, 0B0h; void *
0x18003081f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030824  nop
0x180030825  jmp     loc_1800309C3
0x18003082a  mov     rbx, [rsp+200h+hMem]
0x18003082f  test    rbx, rbx
0x180030832  jz      short loc_180030853
0x180030834  lea     rcx, [rsp+200h+var_1A0]; this
0x180030839  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003083e  nop
0x18003083f  mov     rcx, rbx; hMem
0x180030842  call    cs:__imp_LocalFree
0x180030848  nop
0x180030849  lea     rcx, [rsp+200h+var_1A0]; this
0x18003084e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030853  mov     [rsp+200h+hMem], r15
0x180030858  lea     rdx, [rbp+100h+lpSource]
0x18003085c  cmp     [rbp+100h+var_168], 7
0x180030861  cmova   rdx, [rbp+100h+lpSource]; lpSource
0x180030866  lea     rax, [rsp+200h+var_190]
0x18003086b  mov     [rsp+200h+Arguments], rax; Arguments
0x180030870  mov     [rsp+200h+nSize], r15d; nSize
0x180030875  lea     rax, [rsp+200h+hMem]
0x18003087a  mov     [rsp+200h+lpBuffer], rax; int
0x18003087f  xor     r9d, r9d; dwLanguageId
0x180030882  xor     r8d, r8d; dwMessageId
0x180030885  mov     ecx, 2500h; dwFlags
0x18003088a  call    cs:__imp_FormatMessageW
0x180030890  test    eax, eax
0x180030892  jnz     short loc_1800308CE
0x180030894  call    cs:__imp_GetLastError
0x18003089a  mov     ebx, eax
0x18003089c  test    eax, eax
0x18003089e  jle     short loc_1800308A9
0x1800308a0  movzx   ebx, ax
0x1800308a3  or      ebx, 80070000h
0x1800308a9  test    ebx, ebx
0x1800308ab  jns     short loc_1800308C9
0x1800308ad  mov     rcx, [rbp+108h]; this
0x1800308b4  mov     r9d, ebx; char *
0x1800308b7  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x1800308be  mov     edx, 0B9h; void *
0x1800308c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800308c8  nop
0x1800308c9  jmp     loc_1800309C3
0x1800308ce  mov     rax, [rdi]
0x1800308d1  mov     rbx, [rax+58h]
0x1800308d5  mov     rcx, [rsp+200h+var_1B8]
0x1800308da  mov     [rsp+200h+var_1B8], r15
0x1800308df  test    rcx, rcx
0x1800308e2  jz      short loc_1800308F0
0x1800308e4  mov     rax, [rcx]
0x1800308e7  mov     rax, [rax+10h]
0x1800308eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800308f0  mov     rdx, [rsp+200h+hMem]
0x1800308f5  mov     [rsp+200h+var_1A0], rdx
0x1800308fa  lea     rdx, [rsp+200h+var_1A0]
0x1800308ff  lea     rcx, [rbp+100h+hstringHeader]
0x180030903  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030908  nop
0x180030909  lea     r8, [rsp+200h+var_1B8]
0x18003090e  mov     rdx, [rax+18h]
0x180030912  mov     rcx, rdi
0x180030915  mov     rax, rbx
0x180030918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003091d  mov     ebx, eax
0x18003091f  mov     [rbp+100h+var_148], r15
0x180030923  test    eax, eax
0x180030925  jns     short loc_180030945
0x180030927  mov     rcx, [rbp+108h]; this
0x18003092e  mov     r9d, eax; char *
0x180030931  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x180030938  mov     edx, 0BBh; void *
0x18003093d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030942  nop
0x180030943  jmp     short loc_1800309C3
0x180030945  mov     rbx, [rsp+200h+var_1B0]
0x18003094a  mov     rax, [rbx]
0x18003094d  mov     rdi, [rax+0B0h]
0x180030954  mov     rcx, [rsp+200h+var_198]
0x180030959  mov     [rsp+200h+var_198], r15
0x18003095e  test    rcx, rcx
0x180030961  jz      short loc_18003096F
0x180030963  mov     rax, [rcx]
0x180030966  mov     rax, [rax+10h]
0x18003096a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003096f  lea     rdx, [rsp+200h+var_1A0]
0x180030974  lea     rcx, [rsp+200h+var_1B8]
0x180030979  call    ??$query@UIXmlNode@Dom@Xml@Data@Windows@@@?$com_ptr_t@UIXmlAttribute@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIXmlNode@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlAttribute,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNode>(void)
0x18003097e  nop
0x18003097f  lea     r8, [rsp+200h+var_198]
0x180030984  mov     rdx, [rax]
0x180030987  mov     rcx, rbx
0x18003098a  mov     rax, rdi
0x18003098d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030992  mov     ebx, eax
0x180030994  lea     rcx, [rsp+200h+var_1A0]
0x180030999  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18003099e  test    ebx, ebx
0x1800309a0  jns     short loc_1800309C0
0x1800309a2  mov     rcx, [rbp+108h]; this
0x1800309a9  mov     r9d, ebx; char *
0x1800309ac  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x1800309b3  mov     edx, 0BDh; void *
0x1800309b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800309bd  nop
0x1800309be  jmp     short loc_1800309C3
0x1800309c0  mov     ebx, r15d
0x1800309c3  lea     rcx, [rsp+200h+hMem]
0x1800309c8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800309cd  nop
0x1800309ce  lea     rcx, [rsp+200h+var_198]
0x1800309d3  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800309d8  nop
0x1800309d9  lea     rcx, [rsp+200h+var_1B8]
0x1800309de  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800309e3  nop
0x1800309e4  lea     rcx, [rsp+200h+var_1B0]
0x1800309e9  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800309ee  nop
0x1800309ef  lea     rcx, [rsp+200h+var_1A8]
0x1800309f4  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x1800309f9  nop
0x1800309fa  lea     rcx, [rbp+100h+lpSource]
0x1800309fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030a03  mov     eax, ebx
0x180030a05  mov     rcx, [rbp+100h+var_40]
0x180030a0c  xor     rcx, rsp; StackCookie
0x180030a0f  call    __security_check_cookie
0x180030a14  add     rsp, 1D8h
0x180030a1b  pop     r15
0x180030a1d  pop     r14
0x180030a1f  pop     rdi
0x180030a20  pop     rsi
0x180030a21  pop     rbx
0x180030a22  pop     rbp
0x180030a23  retn
```
