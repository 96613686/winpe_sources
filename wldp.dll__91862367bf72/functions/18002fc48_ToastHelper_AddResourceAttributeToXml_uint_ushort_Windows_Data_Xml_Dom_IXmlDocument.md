# ToastHelper::AddResourceAttributeToXml(uint,ushort *,Windows::Data::Xml::Dom::IXmlDocument *)

- ea: `0x18002fc48`
- end: `0x18002ff75`
- name: `?AddResourceAttributeToXml@ToastHelper@@CAJIPEAGPEAUIXmlDocument@Dom@Xml@Data@Windows@@@Z`
- size: `813`
- prototype: `__int64 __fastcall(unsigned int, unsigned __int16 *, struct Windows::Data::Xml::Dom::IXmlDocument *)`
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
- `0x18002fc48`
- `0x180030a2c`
- `0x180042010`

## string_xrefs

- `0x18002fd17`: `onecore\base\ngscb\wldp\dll\toasthelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ToastHelper::AddResourceAttributeToXml(
        UINT a1,
        unsigned __int16 *a2,
        struct Windows::Data::Xml::Dom::IXmlDocument *a3,
        __int64 a4)
{
  __int64 (__fastcall ***v6)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *); // r8
  __int64 (__fastcall *v7)(struct Windows::Data::Xml::Dom::IXmlDocument *, GUID *, __int64 *); // rbx
  int StringResource; // eax
  int v9; // ebx
  __int64 v10; // rdx
  unsigned __int64 v11; // r9
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // r14
  __int64 v14; // rax
  __int64 (__fastcall *v15)(__int64, __int64 *); // r14
  __int64 (__fastcall *v16)(struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD, int *); // rbx
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, _QWORD); // rbx
  WCHAR *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, _QWORD, _QWORD *); // rdi
  __int64 v24; // rcx
  _QWORD *v25; // rax
  int v27[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v28; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  const wchar_t *v31; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v32[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[12]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+70h] [rbp-90h]
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-88h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h]
  WCHAR sourceString[128]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v31 = L"content";
  std::wstring::wstring(Buffer, a2, a3, a4);
  v30 = 0;
  v29 = 0;
  *(_QWORD *)v27 = 0;
  v28 = 0;
  v32[0] = 0;
  v7 = **v6;
  v30 = 0;
  StringResource = v7(a3, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v30);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 129;
LABEL_5:
    v11 = (unsigned int)StringResource;
    goto LABEL_6;
  }
  StringResource = StringCchPrintfW(sourceString, 0x80u, L"/toast/actions/action[number(@id) = '%d']", a1);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 131;
    goto LABEL_5;
  }
  v12 = v30;
  v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 48LL);
  v29 = 0;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString);
  StringResource = v13(v12, *(_QWORD *)(v14 + 24), &v29);
  v9 = StringResource;
  v36 = 0;
  if ( StringResource < 0 )
  {
    v10 = 133;
    goto LABEL_5;
  }
  v15 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v29 + 128LL);
  v28 = 0;
  StringResource = v15(v29, &v28);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 135;
    goto LABEL_5;
  }
  StringResource = ToastHelper::LoadStringResource(a1, Buffer);
  v9 = StringResource;
  if ( StringResource < 0 )
  {
    v10 = 137;
    goto LABEL_5;
  }
  v16 = *(__int64 (__fastcall **)(struct Windows::Data::Xml::Dom::IXmlDocument *, _QWORD, int *))(*(_QWORD *)a3 + 112LL);
  *(_QWORD *)v27 = 0;
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
  StringResource = v16(a3, *(_QWORD *)(v17 + 24), v27);
  v9 = StringResource;
  v36 = 0;
  if ( StringResource < 0 )
  {
    v10 = 139;
    goto LABEL_5;
  }
  v18 = *(_QWORD *)v27;
  v19 = *(__int64 (__fastcall **)(__int64, _QWORD))(**(_QWORD **)v27 + 72LL);
  v20 = Buffer;
  if ( v34 > 7 )
    v20 = *(WCHAR **)Buffer;
  v31 = v20;
  v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v31);
  StringResource = v19(v18, *(_QWORD *)(v21 + 24));
  v9 = StringResource;
  v36 = 0;
  if ( StringResource < 0 )
  {
    v10 = 141;
    goto LABEL_5;
  }
  v22 = v28;
  v23 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v28 + 72LL);
  v24 = v32[0];
  v32[0] = 0;
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v25 = (_QWORD *)wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlAttribute,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNode>(
                    v27,
                    &v31);
  v9 = v23(v22, *v25, v32);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v31);
  if ( v9 >= 0 )
  {
    v9 = 0;
    goto LABEL_24;
  }
  v11 = (unsigned int)v9;
  v10 = 143;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\toasthelper.cpp",
    (const char *)v11,
    v27[0]);
LABEL_24:
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v32);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v28);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(v27);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v29);
  wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(&v30);
  std::wstring::~wstring(Buffer);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002fc48  mov     [rsp-8+arg_8], rbx
0x18002fc4d  push    rbp
0x18002fc4e  push    rsi
0x18002fc4f  push    rdi
0x18002fc50  push    r14
0x18002fc52  push    r15
0x18002fc54  lea     rbp, [rsp-0B0h]
0x18002fc5c  sub     rsp, 1B0h
0x18002fc63  mov     rax, cs:__security_cookie
0x18002fc6a  xor     rax, rsp
0x18002fc6d  mov     [rbp+0D0h+var_30], rax
0x18002fc74  mov     rdi, r8
0x18002fc77  mov     esi, ecx
0x18002fc79  xor     r15d, r15d
0x18002fc7c  lea     rax, aContent; "content"
0x18002fc83  mov     [rsp+1D0h+var_190], rax
0x18002fc88  lea     rcx, [rsp+1D0h+Buffer]
0x18002fc8d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002fc92  nop
0x18002fc93  mov     [rsp+1D0h+var_198], r15
0x18002fc98  mov     [rsp+1D0h+var_1A0], r15
0x18002fc9d  mov     qword ptr [rsp+1D0h+var_1B0], r15; int
0x18002fca2  mov     [rsp+1D0h+var_1A8], r15
0x18002fca7  mov     [rsp+1D0h+var_188], r15
0x18002fcac  mov     rax, [r8]
0x18002fcaf  mov     rbx, [rax]
0x18002fcb2  mov     rcx, [rsp+1D0h+var_198]
0x18002fcb7  mov     [rsp+1D0h+var_198], r15
0x18002fcbc  test    rcx, rcx
0x18002fcbf  jz      short loc_18002FCCD
0x18002fcc1  mov     rax, [rcx]
0x18002fcc4  mov     rax, [rax+10h]
0x18002fcc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fccd  lea     r8, [rsp+1D0h+var_198]
0x18002fcd2  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x18002fcd9  mov     rcx, rdi
0x18002fcdc  mov     rax, rbx
0x18002fcdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fce4  mov     ebx, eax
0x18002fce6  test    eax, eax
0x18002fce8  jns     short loc_18002FCF1
0x18002fcea  mov     edx, 81h
0x18002fcef  jmp     short loc_18002FD14
0x18002fcf1  mov     r9d, esi
0x18002fcf4  lea     r8, aToastActionsAc; "/toast/actions/action[number(@id) = '%d"...
0x18002fcfb  mov     edx, 80h; unsigned __int64
0x18002fd00  lea     rcx, [rbp+0D0h+sourceString]; unsigned __int16 *
0x18002fd04  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002fd09  mov     ebx, eax
0x18002fd0b  test    eax, eax
0x18002fd0d  jns     short loc_18002FD2F
0x18002fd0f  mov     edx, 83h; void *
0x18002fd14  mov     r9d, eax; char *
0x18002fd17  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\wldp\\dll\\toasth"...
0x18002fd1e  mov     rcx, [rbp+0D8h]; this
0x18002fd25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fd2a  jmp     loc_18002FF0C
0x18002fd2f  mov     rbx, [rsp+1D0h+var_198]
0x18002fd34  mov     rax, [rbx]
0x18002fd37  mov     r14, [rax+30h]
0x18002fd3b  mov     rcx, [rsp+1D0h+var_1A0]
0x18002fd40  mov     [rsp+1D0h+var_1A0], r15
0x18002fd45  test    rcx, rcx
0x18002fd48  jz      short loc_18002FD56
0x18002fd4a  mov     rax, [rcx]
0x18002fd4d  mov     rax, [rax+10h]
0x18002fd51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd56  lea     rdx, [rbp+0D0h+sourceString]; sourceString
0x18002fd5a  lea     rcx, [rsp+1D0h+hstringHeader]; hstringHeader
0x18002fd5f  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x18002fd64  nop
0x18002fd65  lea     r8, [rsp+1D0h+var_1A0]
0x18002fd6a  mov     rdx, [rax+18h]
0x18002fd6e  mov     rcx, rbx
0x18002fd71  mov     rax, r14
0x18002fd74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fd79  mov     ebx, eax
0x18002fd7b  mov     [rbp+0D0h+var_140], r15
0x18002fd7f  test    eax, eax
0x18002fd81  jns     short loc_18002FD8A
0x18002fd83  mov     edx, 85h
0x18002fd88  jmp     short loc_18002FD14
0x18002fd8a  mov     rbx, [rsp+1D0h+var_1A0]
0x18002fd8f  mov     rax, [rbx]
0x18002fd92  mov     r14, [rax+80h]
0x18002fd99  mov     rdx, [rsp+1D0h+var_1A8]
0x18002fd9e  mov     [rsp+1D0h+var_1A8], r15
0x18002fda3  test    rdx, rdx
0x18002fda6  jz      short loc_18002FDB7
0x18002fda8  mov     rcx, [rdx]
0x18002fdab  mov     rax, [rcx+10h]
0x18002fdaf  mov     rcx, rdx
0x18002fdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdb7  lea     rdx, [rsp+1D0h+var_1A8]
0x18002fdbc  mov     rcx, rbx
0x18002fdbf  mov     rax, r14
0x18002fdc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fdc7  mov     ebx, eax
0x18002fdc9  test    eax, eax
0x18002fdcb  jns     short loc_18002FDD7
0x18002fdcd  mov     edx, 87h
0x18002fdd2  jmp     loc_18002FD14
0x18002fdd7  lea     rdx, [rsp+1D0h+Buffer]; lpBuffer
0x18002fddc  mov     ecx, esi; uID
0x18002fdde  call    ?LoadStringResource@ToastHelper@@CAJIAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ToastHelper::LoadStringResource(uint,std::wstring &)
0x18002fde3  mov     ebx, eax
0x18002fde5  test    eax, eax
0x18002fde7  jns     short loc_18002FDF3
0x18002fde9  mov     edx, 89h
0x18002fdee  jmp     loc_18002FD14
0x18002fdf3  mov     rax, [rdi]
0x18002fdf6  mov     rbx, [rax+70h]
0x18002fdfa  mov     rcx, qword ptr [rsp+1D0h+var_1B0]
0x18002fdff  mov     qword ptr [rsp+1D0h+var_1B0], r15
0x18002fe04  test    rcx, rcx
0x18002fe07  jz      short loc_18002FE15
0x18002fe09  mov     rax, [rcx]
0x18002fe0c  mov     rax, [rax+10h]
0x18002fe10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe15  lea     rdx, [rsp+1D0h+var_190]
0x18002fe1a  lea     rcx, [rsp+1D0h+hstringHeader]
0x18002fe1f  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002fe24  nop
0x18002fe25  lea     r8, [rsp+1D0h+var_1B0]
0x18002fe2a  mov     rdx, [rax+18h]
0x18002fe2e  mov     rcx, rdi
0x18002fe31  mov     rax, rbx
0x18002fe34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe39  mov     ebx, eax
0x18002fe3b  mov     [rbp+0D0h+var_140], r15
0x18002fe3f  test    eax, eax
0x18002fe41  jns     short loc_18002FE4D
0x18002fe43  mov     edx, 8Bh
0x18002fe48  jmp     loc_18002FD14
0x18002fe4d  mov     rdi, qword ptr [rsp+1D0h+var_1B0]
0x18002fe52  mov     rax, [rdi]
0x18002fe55  mov     rbx, [rax+48h]
0x18002fe59  lea     rdx, [rsp+1D0h+Buffer]
0x18002fe5e  cmp     [rsp+1D0h+var_160], 7
0x18002fe64  cmova   rdx, qword ptr [rsp+1D0h+Buffer]
0x18002fe6a  mov     [rsp+1D0h+var_190], rdx
0x18002fe6f  lea     rdx, [rsp+1D0h+var_190]
0x18002fe74  lea     rcx, [rsp+1D0h+hstringHeader]
0x18002fe79  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18002fe7e  nop
0x18002fe7f  mov     rdx, [rax+18h]
0x18002fe83  mov     rcx, rdi
0x18002fe86  mov     rax, rbx
0x18002fe89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fe8e  mov     ebx, eax
0x18002fe90  mov     [rbp+0D0h+var_140], r15
0x18002fe94  test    eax, eax
0x18002fe96  jns     short loc_18002FEA2
0x18002fe98  mov     edx, 8Dh
0x18002fe9d  jmp     loc_18002FD14
0x18002fea2  mov     rbx, [rsp+1D0h+var_1A8]
0x18002fea7  mov     rax, [rbx]
0x18002feaa  mov     rdi, [rax+48h]
0x18002feae  mov     rcx, [rsp+1D0h+var_188]
0x18002feb3  mov     [rsp+1D0h+var_188], r15
0x18002feb8  test    rcx, rcx
0x18002febb  jz      short loc_18002FEC9
0x18002febd  mov     rax, [rcx]
0x18002fec0  mov     rax, [rax+10h]
0x18002fec4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fec9  lea     rdx, [rsp+1D0h+var_190]
0x18002fece  lea     rcx, [rsp+1D0h+var_1B0]
0x18002fed3  call    ??$query@UIXmlNode@Dom@Xml@Data@Windows@@@?$com_ptr_t@UIXmlAttribute@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIXmlNode@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlAttribute,wil::err_exception_policy>::query<Windows::Data::Xml::Dom::IXmlNode>(void)
0x18002fed8  nop
0x18002fed9  lea     r8, [rsp+1D0h+var_188]
0x18002fede  mov     rdx, [rax]
0x18002fee1  mov     rcx, rbx
0x18002fee4  mov     rax, rdi
0x18002fee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002feec  mov     ebx, eax
0x18002feee  lea     rcx, [rsp+1D0h+var_190]
0x18002fef3  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18002fef8  test    ebx, ebx
0x18002fefa  jns     short loc_18002FF09
0x18002fefc  mov     r9d, ebx
0x18002feff  mov     edx, 8Fh
0x18002ff04  jmp     loc_18002FD17
0x18002ff09  mov     ebx, r15d
0x18002ff0c  lea     rcx, [rsp+1D0h+var_188]
0x18002ff11  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18002ff16  nop
0x18002ff17  lea     rcx, [rsp+1D0h+var_1A8]
0x18002ff1c  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18002ff21  nop
0x18002ff22  lea     rcx, [rsp+1D0h+var_1B0]
0x18002ff27  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18002ff2c  nop
0x18002ff2d  lea     rcx, [rsp+1D0h+var_1A0]
0x18002ff32  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18002ff37  nop
0x18002ff38  lea     rcx, [rsp+1D0h+var_198]
0x18002ff3d  call    ??1?$com_ptr_t@UIXmlDocumentIO@Dom@Xml@Data@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>::~com_ptr_t<Windows::Data::Xml::Dom::IXmlDocumentIO,wil::err_exception_policy>(void)
0x18002ff42  nop
0x18002ff43  lea     rcx, [rsp+1D0h+Buffer]
0x18002ff48  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ff4d  mov     eax, ebx
0x18002ff4f  mov     rcx, [rbp+0D0h+var_30]
0x18002ff56  xor     rcx, rsp; StackCookie
0x18002ff59  call    __security_check_cookie
0x18002ff5e  mov     rbx, [rsp+1D0h+arg_8]
0x18002ff66  add     rsp, 1B0h
0x18002ff6d  pop     r15
0x18002ff6f  pop     r14
0x18002ff71  pop     rdi
0x18002ff72  pop     rsi
0x18002ff73  pop     rbp
0x18002ff74  retn
```
