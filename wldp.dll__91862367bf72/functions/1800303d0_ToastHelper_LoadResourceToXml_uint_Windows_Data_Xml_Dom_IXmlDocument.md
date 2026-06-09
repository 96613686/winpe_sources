# ToastHelper::LoadResourceToXml(uint,Windows::Data::Xml::Dom::IXmlDocument *)

- ea: `0x1800303d0`
- end: `0x18003067f`
- name: `?LoadResourceToXml@ToastHelper@@CAJIPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z`
- size: `687`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::Data::Xml::Dom::IXmlDocument *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002ff7c`
- `0x1800300d0`

## callees

- `0x1800049d0`
- `0x1800159a0`
- `0x18001f038`
- `0x180020a6c`
- `0x180021ec0`
- `0x18002f8f8`
- `0x18002f964`
- `0x18002fabc`
- `0x18002fb7c`
- `0x1800303d0`
- `0x180030a2c`
- `0x180042010`

## string_xrefs

- `0x1800304a1`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ToastHelper::LoadResourceToXml(
        UINT a1,
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (__fastcall ***v6)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *); // rdx
  __int64 (__fastcall *v7)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *); // rbx
  int StringResource; // eax
  int v9; // ebx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // r14
  __int64 v14; // rax
  __int64 (__fastcall *v15)(struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD, int *); // rbx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64 *); // rdi
  __int64 v20; // rcx
  _QWORD *v21; // rax
  int v23[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v24; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR *v27; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[12]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v29; // [rsp+60h] [rbp-A0h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+80h] [rbp-80h]
  WCHAR sourceString[128]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  std::wstring::wstring(Buffer, a2, a3, a4);
  v25 = 0;
  v24 = 0;
  *(_QWORD *)v23 = 0;
  v26 = 0;
  v7 = **v6;
  v25 = 0;
  StringResource = v7(a2, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v25);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 95;
LABEL_5:
    v11 = (unsigned int)StringResource;
    goto LABEL_6;
  }
  StringResource = StringCchPrintfW(sourceString, 0x80u, L"/toast/visual/binding/text[number(@id) = '%d']", a1);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 97;
    goto LABEL_5;
  }
  v12 = v25;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
  v24 = 0;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
  StringResource = v13(v12, *(_QWORD *)(v14 + 24), &v24);
  v9 = StringResource;
  v31 = 0;
  if ( StringResource < 0 )
  {
    v10 = 99;
    goto LABEL_5;
  }
  StringResource = ToastHelper::LoadStringResource(a1, Buffer);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 101;
    goto LABEL_5;
  }
  v15 = *(__int64 (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD, int *))(*(_QWORD *)a2 + 88LL);
  *(_QWORD *)v23 = 0;
  v16 = Buffer;
  if ( v29 > 7 )
    v16 = *(WCHAR **)Buffer;
  v27 = v16;
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v27);
  StringResource = v15(a2, *(_QWORD *)(v17 + 24), v23);
  v9 = StringResource;
  v31 = 0;
  if ( StringResource < 0 )
  {
    v10 = 103;
    goto LABEL_5;
  }
  v18 = v24;
  v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 176LL);
  v20 = v26;
  v26 = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v21 = (_QWORD *)wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlAttribute,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNode>(
                    v23,
                    &v27);
  v9 = v19(v18, *v21, &v26);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v27);
  if ( v9 >= 0 )
  {
    v9 = 0;
    goto LABEL_20;
  }
  v11 = (unsigned int)v9;
  v10 = 105;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)v11,
    v23[0]);
LABEL_20:
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v26);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v23);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v24);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v25);
  std::wstring::~wstring(Buffer);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800303d0  mov     [rsp-8+arg_10], rbx
0x1800303d5  mov     [rsp-8+arg_18], rsi
0x1800303da  push    rbp
0x1800303db  push    rdi
0x1800303dc  push    r14
0x1800303de  lea     rbp, [rsp-0A0h]
0x1800303e6  sub     rsp, 1A0h
0x1800303ed  mov     rax, cs:__security_cookie
0x1800303f4  xor     rax, rsp
0x1800303f7  mov     [rbp+0B0h+var_20], rax
0x1800303fe  mov     rdi, rdx
0x180030401  mov     esi, ecx
0x180030403  lea     rcx, [rsp+1B0h+Buffer]
0x180030408  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003040d  nop
0x18003040e  mov     [rsp+1B0h+var_180], 0
0x180030417  mov     [rsp+1B0h+var_188], 0
0x180030420  mov     qword ptr [rsp+1B0h+var_190], 0; int
0x180030429  mov     [rsp+1B0h+var_178], 0
0x180030432  mov     rax, [rdx]
0x180030435  mov     rbx, [rax]
0x180030438  mov     rcx, [rsp+1B0h+var_180]
0x18003043d  mov     [rsp+1B0h+var_180], 0
0x180030446  test    rcx, rcx
0x180030449  jz      short loc_180030457
0x18003044b  mov     rax, [rcx]
0x18003044e  mov     rax, [rax+10h]
0x180030452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030457  lea     r8, [rsp+1B0h+var_180]
0x18003045c  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x180030463  mov     rcx, rdi
0x180030466  mov     rax, rbx
0x180030469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003046e  mov     ebx, eax
0x180030470  test    eax, eax
0x180030472  jns     short loc_18003047B
0x180030474  mov     edx, 5Fh ; '_'
0x180030479  jmp     short loc_18003049E
0x18003047b  mov     r9d, esi
0x18003047e  lea     r8, aToastVisualBin; "/toast/visual/binding/text[number(@id) "...
0x180030485  mov     edx, 80h; unsigned __int64
0x18003048a  lea     rcx, [rbp+0B0h+sourceString]; unsigned __int16 *
0x18003048e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030493  mov     ebx, eax
0x180030495  test    eax, eax
0x180030497  jns     short loc_1800304B9
0x180030499  mov     edx, 61h ; 'a'; void *
0x18003049e  mov     r9d, eax; char *
0x1800304a1  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x1800304a8  mov     rcx, [rbp+0B8h]; this
0x1800304af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800304b4  jmp     loc_180030620
0x1800304b9  mov     rbx, [rsp+1B0h+var_180]
0x1800304be  mov     rax, [rbx]
0x1800304c1  mov     r14, [rax+30h]
0x1800304c5  mov     rcx, [rsp+1B0h+var_188]
0x1800304ca  mov     [rsp+1B0h+var_188], 0
0x1800304d3  test    rcx, rcx
0x1800304d6  jz      short loc_1800304E4
0x1800304d8  mov     rax, [rcx]
0x1800304db  mov     rax, [rax+10h]
0x1800304df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800304e4  lea     rdx, [rbp+0B0h+sourceString]; sourceString
0x1800304e8  lea     rcx, [rsp+1B0h+hstringHeader]; hstringHeader
0x1800304ed  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x1800304f2  nop
0x1800304f3  lea     r8, [rsp+1B0h+var_188]
0x1800304f8  mov     rdx, [rax+18h]
0x1800304fc  mov     rcx, rbx
0x1800304ff  mov     rax, r14
0x180030502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030507  mov     ebx, eax
0x180030509  mov     [rbp+0B0h+var_130], 0
0x180030511  test    eax, eax
0x180030513  jns     short loc_18003051C
0x180030515  mov     edx, 63h ; 'c'
0x18003051a  jmp     short loc_18003049E
0x18003051c  lea     rdx, [rsp+1B0h+Buffer]; lpBuffer
0x180030521  mov     ecx, esi; uID
0x180030523  call    ?LoadStringResource@ToastHelper@@CAJIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ToastHelper::LoadStringResource(uint,std::wstring &)
0x180030528  mov     ebx, eax
0x18003052a  test    eax, eax
0x18003052c  jns     short loc_180030538
0x18003052e  mov     edx, 65h ; 'e'
0x180030533  jmp     loc_18003049E
0x180030538  mov     rax, [rdi]
0x18003053b  mov     rbx, [rax+58h]
0x18003053f  mov     rcx, qword ptr [rsp+1B0h+var_190]
0x180030544  mov     qword ptr [rsp+1B0h+var_190], 0
0x18003054d  test    rcx, rcx
0x180030550  jz      short loc_18003055E
0x180030552  mov     rax, [rcx]
0x180030555  mov     rax, [rax+10h]
0x180030559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003055e  lea     rdx, [rsp+1B0h+Buffer]
0x180030563  cmp     [rsp+1B0h+var_150], 7
0x180030569  cmova   rdx, qword ptr [rsp+1B0h+Buffer]
0x18003056f  mov     [rsp+1B0h+var_170], rdx
0x180030574  lea     rdx, [rsp+1B0h+var_170]
0x180030579  lea     rcx, [rsp+1B0h+hstringHeader]
0x18003057e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180030583  nop
0x180030584  lea     r8, [rsp+1B0h+var_190]
0x180030589  mov     rdx, [rax+18h]
0x18003058d  mov     rcx, rdi
0x180030590  mov     rax, rbx
0x180030593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030598  mov     ebx, eax
0x18003059a  mov     [rbp+0B0h+var_130], 0
0x1800305a2  test    eax, eax
0x1800305a4  jns     short loc_1800305B0
0x1800305a6  mov     edx, 67h ; 'g'
0x1800305ab  jmp     loc_18003049E
0x1800305b0  mov     rbx, [rsp+1B0h+var_188]
0x1800305b5  mov     rax, [rbx]
0x1800305b8  mov     rdi, [rax+0B0h]
0x1800305bf  mov     rcx, [rsp+1B0h+var_178]
0x1800305c4  mov     [rsp+1B0h+var_178], 0
0x1800305cd  test    rcx, rcx
0x1800305d0  jz      short loc_1800305DE
0x1800305d2  mov     rax, [rcx]
0x1800305d5  mov     rax, [rax+10h]
0x1800305d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800305de  lea     rdx, [rsp+1B0h+var_170]
0x1800305e3  lea     rcx, [rsp+1B0h+var_190]
0x1800305e8  call    ??$query@UIXmlNode@Dom@Xml@Data@Windows@@@?$com_ptr_t@UIXmlAttribute@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIXmlNode@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlAttribute,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNode>(void)
0x1800305ed  nop
0x1800305ee  lea     r8, [rsp+1B0h+var_178]
0x1800305f3  mov     rdx, [rax]
0x1800305f6  mov     rcx, rbx
0x1800305f9  mov     rax, rdi
0x1800305fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030601  mov     ebx, eax
0x180030603  lea     rcx, [rsp+1B0h+var_170]
0x180030608  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18003060d  test    ebx, ebx
0x18003060f  jns     short loc_18003061E
0x180030611  mov     r9d, ebx
0x180030614  mov     edx, 69h ; 'i'
0x180030619  jmp     loc_1800304A1
0x18003061e  xor     ebx, ebx
0x180030620  lea     rcx, [rsp+1B0h+var_178]
0x180030625  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18003062a  nop
0x18003062b  lea     rcx, [rsp+1B0h+var_190]
0x180030630  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030635  nop
0x180030636  lea     rcx, [rsp+1B0h+var_188]
0x18003063b  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x180030640  nop
0x180030641  lea     rcx, [rsp+1B0h+var_180]
0x180030646  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18003064b  nop
0x18003064c  lea     rcx, [rsp+1B0h+Buffer]
0x180030651  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030656  mov     eax, ebx
0x180030658  mov     rcx, [rbp+0B0h+var_20]
0x18003065f  xor     rcx, rsp; StackCookie
0x180030662  call    __security_check_cookie
0x180030667  lea     r11, [rsp+1B0h+var_10]
0x18003066f  mov     rbx, [r11+30h]
0x180030673  mov     rsi, [r11+38h]
0x180030677  mov     rsp, r11
0x18003067a  pop     r14
0x18003067c  pop     rdi
0x18003067d  pop     rbp
0x18003067e  retn
```
