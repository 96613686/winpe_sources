# CFilterImpContentHandler::startElement(wchar_t const *,int,wchar_t const *,int,wchar_t const *,int,ISAXAttributes *)

- ea: `0x18000f7e0`
- end: `0x18000faf8`
- name: `?startElement@CFilterImpContentHandler@@UEAAJPEB_WH0H0HPEAUISAXAttributes@@@Z`
- size: `792`
- prototype: `__int64 __fastcall(HANDLE *this, const wchar_t *, unsigned int, const wchar_t *, int, const wchar_t *, int, struct ISAXAttributes *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800020e0`
- `0x18000596c`
- `0x180005f70`
- `0x18000b724`
- `0x18000c188`
- `0x18000e77c`
- `0x18000e98c`
- `0x18000ed94`
- `0x18000f41c`
- `0x18000f7e0`
- `0x180013c9c`
- `0x180017010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f94d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f976`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f94d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000f976`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fa9b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000fa9b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000faab`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000faab`

## string_xrefs

- `0x18000fabd`: `onecoreuap\base\appmodel\search\filters\xml\FilterImpContentHandler.h`
- `0x18000f87f`: `xml:lang`
- `0x18000f922`: `[XmlFilter SAX Content Handler] CSaxContentHandler::DetectLanguageFromAttributes():Located a Rfc1766 language string %s -> lcid %#x`
- `0x18000f92e`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\saxcontenthandler.cpp"`
- `0x18000f84a`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000fa03`: `"onecoreuap\\base\\appmodel\\search\\filters\\xml\\filterimpcontenthandler.cpp"`
- `0x18000f83e`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::startElement():NamespaceUri:%.*s LocalName:%.*s pwchQName:%.*s`
- `0x18000f9f7`: `[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::startElement():Could not retrieve the attribute count`

## pseudocode

```c
__int64 __fastcall CFilterImpContentHandler::startElement(
        HANDLE *this,
        const wchar_t *a2,
        unsigned int a3,
        const wchar_t *a4,
        int a5,
        const wchar_t *a6,
        int a7,
        struct ISAXAttributes *a8)
{
  CLanguageDetector *LanguageDetector; // rax
  unsigned int v10; // edi
  int v11; // esi
  int v12; // r12d
  unsigned int v13; // r14d
  int v14; // edi
  const wchar_t *v15; // r9
  unsigned int v16; // eax
  unsigned int v17; // esi
  const char *v18; // r9
  __int64 v20; // [rsp+20h] [rbp-C8h]
  int v21; // [rsp+50h] [rbp-98h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-94h] BYREF
  wchar_t *v23; // [rsp+58h] [rbp-90h] BYREF
  _QWORD v24[2]; // [rsp+60h] [rbp-88h] BYREF
  _WORD v25[20]; // [rsp+70h] [rbp-78h] BYREF
  void *Block; // [rsp+98h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
    (const wchar_t *)0x166,
    (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::startElement():NamespaceU"
                   "ri:%.*s LocalName:%.*s pwchQName:%.*s",
    (const wchar_t *)a3,
    a2,
    a5,
    a4,
    a7,
    a6);
  v23 = 0;
  v21 = 0;
  if ( ((int (__fastcall *)(struct ISAXAttributes *, const wchar_t *, __int64, wchar_t **, int *))a8->lpVtbl->getValueFromQName)(
         a8,
         L"xml:lang",
         8,
         &v23,
         &v21) < 0 )
  {
LABEL_11:
    v11 = 0;
    goto LABEL_12;
  }
  if ( v21 > 4096 )
    v21 = 4096;
  v24[0] = 16;
  v24[1] = 0;
  Block = v25;
  v25[0] = 0;
  TVarString<16>::SetMinimalSize(v24, 0);
  TVarString<16>::Cpy(v24, v21, v23);
  v23 = (wchar_t *)Block;
  LanguageDetector = CSaxContentHandler::GetLanguageDetector((CSaxContentHandler *)this);
  if ( !LanguageDetector )
  {
    if ( Block != v25 )
      free(Block);
    goto LABEL_11;
  }
  v10 = CLanguageDetector::MapRfc1766LanguageIdStringToLocale(LanguageDetector, v23);
  LODWORD(v20) = v10;
  SearchIndexerTrace::Verbose(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\saxcontenthandler.cpp\"",
    (const wchar_t *)0x67,
    (unsigned int)L"[XmlFilter SAX Content Handler] CSaxContentHandler::DetectLanguageFromAttributes():Located a Rfc1766 l"
                   "anguage string %s -> lcid %#x",
    v23,
    v20);
  if ( Block != v25 )
    free(Block);
  v11 = 0;
  if ( v10 != *((_DWORD *)this + 9) )
  {
    *((_DWORD *)this + 9) = v10;
    v11 = 1;
  }
LABEL_12:
  v12 = *((_DWORD *)this + 9);
  CVarVector<CElement,64>::SetSize(this + 15, (unsigned int)++*((_DWORD *)this + 100));
  v13 = *((_DWORD *)this + 100);
  if ( *((_DWORD *)this + 98) < v13 )
    CVarVector<CElement,64>::SetSize(this + 15, v13);
  *((_DWORD *)this[15] + v13 - 1) = v12;
  CFilterImpContentHandler::AddContentToBuffer((CFilterImpContentHandler *)this, L" ", 1);
  v22 = 0;
  v14 = ((__int64 (__fastcall *)(struct ISAXAttributes *, unsigned int *))a8->lpVtbl->getLength)(a8, &v22);
  if ( v14 >= 0 )
  {
    v16 = v22;
    if ( v22 )
    {
      v17 = 0;
      while ( v14 >= 0 )
      {
        if ( v17 >= v16 )
          goto LABEL_25;
        v21 = 0;
        v23 = 0;
        v14 = ((__int64 (__fastcall *)(struct ISAXAttributes *, _QWORD, wchar_t **, int *))a8->lpVtbl->getValue)(
                a8,
                v17,
                &v23,
                &v21);
        if ( v14 >= 0 && v21 > 0 )
        {
          CFilterImpContentHandler::AddContentToBuffer((CFilterImpContentHandler *)this, v23, v21);
          CFilterImpContentHandler::AddContentToBuffer((CFilterImpContentHandler *)this, L" ", 1);
        }
        ++v17;
        v16 = v22;
      }
    }
    else if ( v11 )
    {
LABEL_25:
      SetEvent(this[51]);
      if ( WaitForSingleObject(this[52], 0xFFFFFFFF) )
        wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x54,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\filters\\xml\\FilterImpContentHandler.h",
          v18);
    }
  }
  else
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\filters\\\\xml\\\\filterimpcontenthandler.cpp\"",
      (const wchar_t *)0x184,
      (unsigned int)L"[XmlFilter IFilter implementation Content Handler] CFilterImpContentHandler::startElement():Could no"
                     "t retrieve the attribute count",
      v15);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18000f7e0  push    rbx
0x18000f7e2  push    rsi
0x18000f7e3  push    rdi
0x18000f7e4  push    r12
0x18000f7e6  push    r14
0x18000f7e8  push    r15
0x18000f7ea  sub     rsp, 0B8h
0x18000f7f1  mov     rax, cs:__security_cookie
0x18000f7f8  xor     rax, rsp
0x18000f7fb  mov     [rsp+0E8h+var_48], rax
0x18000f803  mov     rbx, rcx
0x18000f806  mov     rax, [rsp+0E8h+arg_28]
0x18000f80e  mov     r15, [rsp+0E8h+arg_38]
0x18000f816  mov     [rsp+0E8h+var_A8], rax
0x18000f81b  mov     eax, [rsp+0E8h+arg_30]
0x18000f822  mov     [rsp+0E8h+var_B0], eax
0x18000f826  mov     [rsp+0E8h+var_B8], r9
0x18000f82b  mov     eax, [rsp+0E8h+arg_20]
0x18000f832  mov     [rsp+0E8h+var_C0], eax
0x18000f836  mov     [rsp+0E8h+var_C8], rdx
0x18000f83b  mov     r9d, r8d; wchar_t *
0x18000f83e  lea     r8, aXmlfilterIfilt_4; "[XmlFilter IFilter implementation Conte"...
0x18000f845  mov     edx, 166h; wchar_t *
0x18000f84a  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f851  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000f856  mov     [rsp+0E8h+var_90], 0
0x18000f85f  mov     [rsp+0E8h+var_98], 0
0x18000f867  mov     rax, [r15]
0x18000f86a  lea     rcx, [rsp+0E8h+var_98]
0x18000f86f  mov     [rsp+0E8h+var_C8], rcx
0x18000f874  lea     r9, [rsp+0E8h+var_90]
0x18000f879  mov     r8d, 8
0x18000f87f  lea     rdx, aXmlLang; "xml:lang"
0x18000f886  mov     rcx, r15
0x18000f889  mov     rax, [rax+78h]
0x18000f88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f892  test    eax, eax
0x18000f894  js      loc_18000F97C
0x18000f89a  mov     eax, 1000h
0x18000f89f  cmp     [rsp+0E8h+var_98], eax
0x18000f8a3  jle     short loc_18000F8A9
0x18000f8a5  mov     [rsp+0E8h+var_98], eax
0x18000f8a9  mov     [rsp+0E8h+var_88], 10h
0x18000f8b2  mov     [rsp+0E8h+var_80], 0
0x18000f8bb  lea     rax, [rsp+0E8h+var_78]
0x18000f8c0  mov     [rsp+0E8h+Block], rax
0x18000f8c8  xor     eax, eax
0x18000f8ca  mov     [rsp+0E8h+var_78], ax
0x18000f8cf  xor     edx, edx
0x18000f8d1  lea     rcx, [rsp+0E8h+var_88]
0x18000f8d6  call    ?SetMinimalSize@?$TVarString@$0BA@@@QEAAX_K@Z; TVarString<16>::SetMinimalSize(unsigned __int64)
0x18000f8db  nop
0x18000f8dc  movsxd  rdx, [rsp+0E8h+var_98]
0x18000f8e1  mov     r8, [rsp+0E8h+var_90]
0x18000f8e6  lea     rcx, [rsp+0E8h+var_88]
0x18000f8eb  call    ?Cpy@?$TVarString@$0BA@@@QEAAAEAV1@_KPEB_W@Z; TVarString<16>::Cpy(unsigned __int64,wchar_t const *)
0x18000f8f0  mov     rax, [rsp+0E8h+Block]
0x18000f8f8  mov     [rsp+0E8h+var_90], rax
0x18000f8fd  mov     rcx, rbx; this
0x18000f900  call    ?GetLanguageDetector@CSaxContentHandler@@AEAAPEAVCLanguageDetector@@XZ; CSaxContentHandler::GetLanguageDetector(void)
0x18000f905  test    rax, rax
0x18000f908  jz      short loc_18000F964
0x18000f90a  mov     rdx, [rsp+0E8h+var_90]; wchar_t *
0x18000f90f  mov     rcx, rax; this
0x18000f912  call    ?MapRfc1766LanguageIdStringToLocale@CLanguageDetector@@QEAAKPEB_W@Z; CLanguageDetector::MapRfc1766LanguageIdStringToLocale(wchar_t const *)
0x18000f917  mov     edi, eax
0x18000f919  mov     dword ptr [rsp+0E8h+var_C8], eax
0x18000f91d  mov     r9, [rsp+0E8h+var_90]; wchar_t *
0x18000f922  lea     r8, aXmlfilterSaxCo_8; "[XmlFilter SAX Content Handler] CSaxCon"...
0x18000f929  mov     edx, 67h ; 'g'; wchar_t *
0x18000f92e  lea     rcx, aOnecoreuapBase_5; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000f935  call    ?Verbose@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x18000f93a  nop
0x18000f93b  lea     rax, [rsp+0E8h+var_78]
0x18000f940  mov     rcx, [rsp+0E8h+Block]; Block
0x18000f948  cmp     rcx, rax
0x18000f94b  jz      short loc_18000F953
0x18000f94d  call    cs:__imp_free
0x18000f953  xor     esi, esi
0x18000f955  cmp     edi, [rbx+24h]
0x18000f958  jz      short loc_18000F97E
0x18000f95a  mov     [rbx+24h], edi
0x18000f95d  mov     esi, 1
0x18000f962  jmp     short loc_18000F97E
0x18000f964  lea     rax, [rsp+0E8h+var_78]
0x18000f969  mov     rcx, [rsp+0E8h+Block]; Block
0x18000f971  cmp     rcx, rax
0x18000f974  jz      short loc_18000F97C
0x18000f976  call    cs:__imp_free
0x18000f97c  xor     esi, esi
0x18000f97e  mov     r12d, [rbx+24h]
0x18000f982  lea     rdi, [rbx+78h]
0x18000f986  inc     dword ptr [rdi+118h]
0x18000f98c  mov     edx, [rdi+118h]
0x18000f992  mov     rcx, rdi
0x18000f995  call    ?SetSize@?$CVarVector@VCElement@@$0EA@@@QEAAXK@Z; CVarVector<CElement,64>::SetSize(ulong)
0x18000f99a  mov     r14d, [rdi+118h]
0x18000f9a1  cmp     [rdi+110h], r14d
0x18000f9a8  jnb     short loc_18000F9B5
0x18000f9aa  mov     edx, r14d
0x18000f9ad  mov     rcx, rdi
0x18000f9b0  call    ?SetSize@?$CVarVector@VCElement@@$0EA@@@QEAAXK@Z; CVarVector<CElement,64>::SetSize(ulong)
0x18000f9b5  lea     ecx, [r14-1]
0x18000f9b9  mov     rax, [rdi]
0x18000f9bc  mov     [rax+rcx*4], r12d
0x18000f9c0  mov     r8d, 1; int
0x18000f9c6  lea     rdx, asc_18001B6D4; " "
0x18000f9cd  mov     rcx, rbx; this
0x18000f9d0  call    ?AddContentToBuffer@CFilterImpContentHandler@@IEAAXPEB_WH@Z; CFilterImpContentHandler::AddContentToBuffer(wchar_t const *,int)
0x18000f9d5  mov     [rsp+0E8h+var_94], 0
0x18000f9dd  mov     rax, [r15]
0x18000f9e0  lea     rdx, [rsp+0E8h+var_94]
0x18000f9e5  mov     rcx, r15
0x18000f9e8  mov     rax, [rax+18h]
0x18000f9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f9f1  mov     edi, eax
0x18000f9f3  test    eax, eax
0x18000f9f5  jns     short loc_18000FA14
0x18000f9f7  lea     r8, aXmlfilterIfilt_3; "[XmlFilter IFilter implementation Conte"...
0x18000f9fe  mov     edx, 184h; wchar_t *
0x18000fa03  lea     rcx, aOnecoreuapBase_1; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x18000fa0a  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000fa0f  jmp     loc_18000FACE
0x18000fa14  mov     eax, [rsp+0E8h+var_94]
0x18000fa18  test    eax, eax
0x18000fa1a  jz      short loc_18000FA90
0x18000fa1c  xor     esi, esi
0x18000fa1e  test    edi, edi
0x18000fa20  js      loc_18000FACE
0x18000fa26  cmp     esi, eax
0x18000fa28  jnb     short loc_18000FA94
0x18000fa2a  mov     [rsp+0E8h+var_98], 0
0x18000fa32  mov     [rsp+0E8h+var_90], 0
0x18000fa3b  mov     rax, [r15]
0x18000fa3e  lea     r9, [rsp+0E8h+var_98]
0x18000fa43  lea     r8, [rsp+0E8h+var_90]
0x18000fa48  mov     edx, esi
0x18000fa4a  mov     rcx, r15
0x18000fa4d  mov     rax, [rax+68h]
0x18000fa51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa56  mov     edi, eax
0x18000fa58  test    eax, eax
0x18000fa5a  js      short loc_18000FA88
0x18000fa5c  mov     r8d, [rsp+0E8h+var_98]; int
0x18000fa61  test    r8d, r8d
0x18000fa64  jle     short loc_18000FA88
0x18000fa66  mov     rdx, [rsp+0E8h+var_90]; wchar_t *
0x18000fa6b  mov     rcx, rbx; this
0x18000fa6e  call    ?AddContentToBuffer@CFilterImpContentHandler@@IEAAXPEB_WH@Z; CFilterImpContentHandler::AddContentToBuffer(wchar_t const *,int)
0x18000fa73  mov     r8d, 1; int
0x18000fa79  lea     rdx, asc_18001B6D4; " "
0x18000fa80  mov     rcx, rbx; this
0x18000fa83  call    ?AddContentToBuffer@CFilterImpContentHandler@@IEAAXPEB_WH@Z; CFilterImpContentHandler::AddContentToBuffer(wchar_t const *,int)
0x18000fa88  inc     esi
0x18000fa8a  mov     eax, [rsp+0E8h+var_94]
0x18000fa8e  jmp     short loc_18000FA1E
0x18000fa90  test    esi, esi
0x18000fa92  jz      short loc_18000FACE
0x18000fa94  mov     rcx, [rbx+198h]; hEvent
0x18000fa9b  call    cs:__imp_SetEvent
0x18000faa1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000faa4  mov     rcx, [rbx+1A0h]; hHandle
0x18000faab  call    cs:__imp_WaitForSingleObject
0x18000fab1  test    eax, eax
0x18000fab3  jz      short loc_18000FACE
0x18000fab5  mov     rcx, [rsp+0E8h]; this
0x18000fabd  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000fac4  mov     edx, 54h ; 'T'; void *
0x18000fac9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000face  mov     eax, edi
0x18000fad0  jmp     short loc_18000FAD6
0x18000fad2  mov     eax, [rsp+0E8h+var_94]
0x18000fad6  mov     rcx, [rsp+0E8h+var_48]
0x18000fade  xor     rcx, rsp; StackCookie
0x18000fae1  call    __security_check_cookie
0x18000fae6  add     rsp, 0B8h
0x18000faed  pop     r15
0x18000faef  pop     r14
0x18000faf1  pop     r12
0x18000faf3  pop     rdi
0x18000faf4  pop     rsi
0x18000faf5  pop     rbx
0x18000faf6  retn
```
