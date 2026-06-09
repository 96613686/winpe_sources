# IsTetheringProfile(ushort * const)

- ea: `0x180023974`
- end: `0x180023d28`
- name: `?IsTetheringProfile@@YAHQEAG@Z`
- size: `948`
- prototype: `__int64 __fastcall(unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800229b8`

## callees

- `0x180002590`
- `0x1800029c0`
- `0x18000bf74`
- `0x18000c2a8`
- `0x18000fe0c`
- `0x180022394`
- `0x180023974`
- `0x180023fc8`
- `0x180028678`
- `0x180028998`
- `0x180028b14`
- `0x180028c8c`
- `0x180028e00`
- `0x180028e74`
- `0x180028ffc`
- `0x180029048`
- `0x180029360`
- `0x1800293e8`
- `0x180029600`
- `0x180029680`
- `0x180029740`
- `0x18003127c`
- `0x180031290`
- `0x180031448`
- `0x180033010`

## string_xrefs

- `0x180023ac2`: `http://www.microsoft.com/networking/WWAN/profile/v3`

## pseudocode

```c
__int64 __fastcall IsTetheringProfile(unsigned __int16 *const a1)
{
  unsigned int v1; // edi
  struct IUnknown *v2; // rbx
  const unsigned __int16 *v3; // rdx
  char *v4; // rax
  _bstr_t *v5; // rsi
  __int64 v6; // rdx
  int v7; // eax
  __int16 v8; // bx
  char *v9; // rbx
  WcmCommon::Xml::Document *v10; // rax
  struct IUnknown ***v11; // rbx
  __int64 **v12; // rax
  __int64 v13; // rdx
  volatile signed __int32 *v14; // rbx
  const wchar_t *v15; // rcx
  wchar_t *v16; // rax
  wchar_t **v17; // rcx
  __int64 v18; // r9
  volatile signed __int32 *v19; // rbx
  struct IUnknown *v21; // rax
  __int64 v22; // [rsp+20h] [rbp-79h] BYREF
  int v23; // [rsp+28h] [rbp-71h]
  __int128 v24; // [rsp+30h] [rbp-69h] BYREF
  __int16 v25; // [rsp+40h] [rbp-59h] BYREF
  char v26; // [rsp+42h] [rbp-57h]
  struct IUnknown *v27; // [rsp+48h] [rbp-51h] BYREF
  wchar_t *S1[2]; // [rsp+50h] [rbp-49h] BYREF
  size_t N; // [rsp+60h] [rbp-39h]
  unsigned __int64 v30; // [rsp+68h] [rbp-31h]
  char *v31; // [rsp+70h] [rbp-29h] BYREF
  volatile signed __int32 *v32; // [rsp+78h] [rbp-21h]
  unsigned __int16 *v33[4]; // [rsp+90h] [rbp-9h] BYREF
  char *v34[4]; // [rsp+B0h] [rbp+17h] BYREF

  v23 = 0;
  std::wstring::wstring(v33, a1);
  v1 = 1;
  v25 = 1;
  v26 = 0;
  v27 = 0;
  CreateDocumentObject((LPVOID *)&v27, &v25);
  v2 = v27;
  if ( !v27 )
    _com_issue_error(-2147467261);
  v3 = (const unsigned __int16 *)v33;
  if ( v33[3] > (unsigned __int16 *)7 )
    v3 = v33[0];
  v4 = (char *)_bstr_t::_bstr_t((_bstr_t *)&v22, v3);
  v5 = (_bstr_t *)v4;
  v31 = v4;
  v25 = 0;
  if ( *(_QWORD *)v4 )
    v6 = **(_QWORD **)v4;
  else
    v6 = 0;
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int16 *))v2->lpVtbl[21].Release)(v2, v6, &v25);
  if ( v7 < 0 )
    _com_issue_errorex(v7, v2, &GUID_2933bf81_7b36_11d2_b20e_00c04f983e60);
  v8 = v25;
  _bstr_t::~_bstr_t(v5);
  if ( !v8 )
  {
    v21 = (struct IUnknown *)_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument3,&__s_GUID const _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60>>::operator->((__int64 *)&v27);
    MSXML2::IXMLDOMDocument::GetparseError(v21, &v22);
    WcmCommon::Xml::Details::Node::~Node((WcmCommon::Xml::Details::Node *)&v22);
    _com_raise_error(-2147023431, 0);
  }
  v24 = 0;
  v9 = (char *)operator new(0x10u);
  v31 = v9;
  *(_OWORD *)v9 = 0;
  WcmCommon::Xml::Details::Document::Document((struct IUnknown **)S1, &v27);
  v23 = 2;
  v10 = WcmCommon::Xml::Document::Document((WcmCommon::Xml::Document *)v9, (const struct Document *)S1);
  std::shared_ptr<WcmCommon::Xml::Document>::shared_ptr<WcmCommon::Xml::Document>(&v24, (__int64)v10);
  v23 = 4;
  WcmCommon::Xml::Details::Document::~Document((WcmCommon::Xml::Details::Document *)S1);
  if ( v27 )
    ((void (__fastcall *)(struct IUnknown *))v27->lpVtbl->Release)(v27);
  std::wstring::~wstring((char **)v33);
  v11 = (struct IUnknown ***)v24;
  std::wstring::wstring(&v31, L"http://www.microsoft.com/networking/WWAN/profile/v3");
  std::wstring::wstring(S1, L"wwanv3");
  WcmCommon::Xml::Document::AddSelectionNamespace(v11, S1, &v31);
  std::wstring::~wstring((char **)S1);
  std::wstring::~wstring(&v31);
  std::wstring::wstring(v34, L"./wwanv3:IsTetheringProfile");
  WcmCommon::Xml::Node::SelectSingle(*(_QWORD *)(*(_QWORD *)v24 + 8LL), &v31, v34);
  if ( v31 )
  {
    if ( !**(_QWORD **)v31 )
      _com_issue_error(-2147467261);
    v12 = (__int64 **)MSXML2::IXMLDOMNode::Gettext(**(struct IUnknown ***)v31, &v22);
    if ( *v12 )
      v13 = **v12;
    else
      v13 = 0;
    BSTR_to_wstring(S1, v13);
    _bstr_t::~_bstr_t((_bstr_t *)&v22);
  }
  else
  {
    *(_OWORD *)S1 = 0;
    N = 0;
    v30 = 7;
    LOWORD(S1[0]) = 0;
  }
  v14 = v32;
  if ( v32 )
  {
    if ( _InterlockedExchangeAdd(v32 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  std::wstring::~wstring(v34);
  v15 = (const wchar_t *)S1;
  v16 = S1[0];
  if ( v30 > 7 )
    v15 = S1[0];
  if ( N == 4 )
  {
    if ( !wmemcmp(v15, L"true", 4u) )
      goto LABEL_31;
    v16 = S1[0];
  }
  v17 = S1;
  if ( v30 > 7 )
    v17 = (wchar_t **)v16;
  if ( N != 1 || wmemcmp((const wchar_t *)v17, L"1", 1u) )
  {
    v1 = 0;
    v18 = 0;
    goto LABEL_33;
  }
LABEL_31:
  v18 = 1;
LABEL_33:
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids, v18);
  }
  std::wstring::~wstring((char **)S1);
  v19 = (volatile signed __int32 *)*((_QWORD *)&v24 + 1);
  if ( *((_QWORD *)&v24 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v24 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x180023974  mov     [rsp-8+arg_8], rbx
0x180023979  mov     [rsp-8+arg_10], rsi
0x18002397e  push    rbp
0x18002397f  push    rdi
0x180023980  push    r14
0x180023982  lea     rbp, [rsp-47h]
0x180023987  sub     rsp, 0E0h
0x18002398e  mov     rax, cs:__security_cookie
0x180023995  xor     rax, rsp
0x180023998  mov     [rbp+57h+var_20], rax
0x18002399c  xor     r14d, r14d
0x18002399f  mov     [rbp+57h+var_C8], r14d
0x1800239a3  mov     rdx, rcx
0x1800239a6  lea     rcx, [rbp+57h+var_60]
0x1800239aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800239af  nop
0x1800239b0  lea     edi, [r14+1]
0x1800239b4  mov     [rbp+57h+var_B0], di
0x1800239b8  mov     [rbp+57h+var_AE], r14b
0x1800239bc  mov     [rbp+57h+var_A8], r14
0x1800239c0  lea     rdx, [rbp+57h+var_B0]
0x1800239c4  lea     rcx, [rbp+57h+var_A8]; ppv
0x1800239c8  call    ?CreateDocumentObject@@YA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument3@MSXML2@@$1?_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@AEBUParseOptions@Xml@WcmCommon@@@Z; CreateDocumentObject(WcmCommon::Xml::ParseOptions const &)
0x1800239cd  nop
0x1800239ce  mov     rbx, [rbp+57h+var_A8]
0x1800239d2  test    rbx, rbx
0x1800239d5  jz      loc_180023CE0
0x1800239db  lea     rdx, [rbp+57h+var_60]
0x1800239df  cmp     [rbp+57h+var_48], 7
0x1800239e4  cmova   rdx, [rbp+57h+var_60]; unsigned __int16 *
0x1800239e9  lea     rcx, [rbp+57h+var_D0]; this
0x1800239ed  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800239f2  mov     rsi, rax
0x1800239f5  mov     [rbp+57h+var_80], rax
0x1800239f9  mov     [rbp+57h+var_B0], r14w
0x1800239fe  mov     rax, [rbx]
0x180023a01  mov     rdx, [rsi]
0x180023a04  test    rdx, rdx
0x180023a07  jz      short loc_180023A0E
0x180023a09  mov     rdx, [rdx]
0x180023a0c  jmp     short loc_180023A11
0x180023a0e  mov     rdx, r14
0x180023a11  lea     r8, [rbp+57h+var_B0]
0x180023a15  mov     rcx, rbx
0x180023a18  mov     rax, [rax+208h]
0x180023a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a24  test    eax, eax
0x180023a26  js      loc_180023CEB
0x180023a2c  movzx   ebx, [rbp+57h+var_B0]
0x180023a30  mov     rcx, rsi; this
0x180023a33  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180023a38  test    bx, bx
0x180023a3b  jz      loc_180023CFD
0x180023a41  xorps   xmm0, xmm0
0x180023a44  movups  [rbp+57h+var_C0], xmm0
0x180023a48  mov     ecx, 10h; Size
0x180023a4d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180023a52  mov     rbx, rax
0x180023a55  mov     [rbp+57h+var_80], rax
0x180023a59  xorps   xmm0, xmm0
0x180023a5c  movups  xmmword ptr [rax], xmm0
0x180023a5f  lea     rdx, [rbp+57h+var_A8]
0x180023a63  lea     rcx, [rbp+57h+S1]
0x180023a67  call    ??0Document@Details@Xml@WcmCommon@@QEAA@AEBV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument3@MSXML2@@$1?_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@@Z; WcmCommon::Xml::Details::Document::Document(_com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument3,&__s_GUID const _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60>> const &)
0x180023a6c  nop
0x180023a6d  mov     [rbp+57h+var_C8], 2
0x180023a74  lea     rdx, [rbp+57h+S1]; struct Document *
0x180023a78  mov     rcx, rbx; this
0x180023a7b  call    ??0Document@Xml@WcmCommon@@AEAA@AEBU0Details@12@@Z; WcmCommon::Xml::Document::Document(WcmCommon::Xml::Details::Document const &)
0x180023a80  nop
0x180023a81  mov     rdx, rax
0x180023a84  lea     rcx, [rbp+57h+var_C0]
0x180023a88  call    ??$?0VDocument@Xml@WcmCommon@@$0A@@?$shared_ptr@VDocument@Xml@WcmCommon@@@std@@QEAA@PEAVDocument@Xml@WcmCommon@@@Z; std::shared_ptr<WcmCommon::Xml::Document>::shared_ptr<WcmCommon::Xml::Document>(WcmCommon::Xml::Document *)
0x180023a8d  nop
0x180023a8e  mov     [rbp+57h+var_C8], 4
0x180023a95  lea     rcx, [rbp+57h+S1]; this
0x180023a99  call    ??1Document@Details@Xml@WcmCommon@@QEAA@XZ; WcmCommon::Xml::Details::Document::~Document(void)
0x180023a9e  nop
0x180023a9f  mov     rcx, [rbp+57h+var_A8]
0x180023aa3  test    rcx, rcx
0x180023aa6  jz      short loc_180023AB5
0x180023aa8  mov     rax, [rcx]
0x180023aab  mov     rax, [rax+10h]
0x180023aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ab4  nop
0x180023ab5  lea     rcx, [rbp+57h+var_60]
0x180023ab9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023abe  mov     rbx, qword ptr [rbp+57h+var_C0]
0x180023ac2  lea     rdx, aHttpWwwMicroso; "http://www.microsoft.com/networking/WWA"...
0x180023ac9  lea     rcx, [rbp+57h+var_80]
0x180023acd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023ad2  nop
0x180023ad3  lea     rdx, aWwanv3; "wwanv3"
0x180023ada  lea     rcx, [rbp+57h+S1]
0x180023ade  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023ae3  nop
0x180023ae4  lea     r8, [rbp+57h+var_80]
0x180023ae8  lea     rdx, [rbp+57h+S1]
0x180023aec  mov     rcx, rbx
0x180023aef  call    ?AddSelectionNamespace@Document@Xml@WcmCommon@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; WcmCommon::Xml::Document::AddSelectionNamespace(std::wstring const &,std::wstring const &)
0x180023af4  nop
0x180023af5  lea     rcx, [rbp+57h+S1]
0x180023af9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023afe  nop
0x180023aff  lea     rcx, [rbp+57h+var_80]
0x180023b03  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023b08  lea     rdx, aWwanv3Istether; "./wwanv3:IsTetheringProfile"
0x180023b0f  lea     rcx, [rbp+57h+var_40]
0x180023b13  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180023b18  nop
0x180023b19  mov     rax, qword ptr [rbp+57h+var_C0]
0x180023b1d  mov     rcx, [rax]
0x180023b20  lea     r8, [rbp+57h+var_40]
0x180023b24  lea     rdx, [rbp+57h+var_80]
0x180023b28  mov     rcx, [rcx+8]
0x180023b2c  call    ?SelectSingle@Node@Xml@WcmCommon@@QEBA?AV?$shared_ptr@VNode@Xml@WcmCommon@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z; WcmCommon::Xml::Node::SelectSingle(std::wstring const &)
0x180023b31  nop
0x180023b32  or      esi, 0FFFFFFFFh
0x180023b35  mov     rax, [rbp+57h+var_80]
0x180023b39  test    rax, rax
0x180023b3c  jnz     short loc_180023B58
0x180023b3e  xorps   xmm0, xmm0
0x180023b41  movups  xmmword ptr [rbp+57h+S1], xmm0
0x180023b45  mov     [rbp+57h+N], r14
0x180023b49  mov     [rbp+57h+var_88], 7
0x180023b51  mov     word ptr [rbp+57h+S1], r14w
0x180023b56  jmp     short loc_180023B95
0x180023b58  mov     rax, [rax]
0x180023b5b  mov     rcx, [rax]
0x180023b5e  test    rcx, rcx
0x180023b61  jz      loc_180023CD5
0x180023b67  lea     rdx, [rbp+57h+var_D0]
0x180023b6b  call    ?Gettext@IXMLDOMNode@MSXML2@@QEAA?AV_bstr_t@@XZ; MSXML2::IXMLDOMNode::Gettext(void)
0x180023b70  nop
0x180023b71  mov     rdx, [rax]
0x180023b74  test    rdx, rdx
0x180023b77  jz      short loc_180023B7E
0x180023b79  mov     rdx, [rdx]
0x180023b7c  jmp     short loc_180023B81
0x180023b7e  mov     rdx, r14
0x180023b81  lea     rcx, [rbp+57h+S1]
0x180023b85  call    BSTR_to_wstring
0x180023b8a  nop
0x180023b8b  lea     rcx, [rbp+57h+var_D0]; this
0x180023b8f  call    ??1_bstr_t@@QEAA@XZ; _bstr_t::~_bstr_t(void)
0x180023b94  nop
0x180023b95  mov     rbx, [rbp+57h+var_78]
0x180023b99  test    rbx, rbx
0x180023b9c  jz      short loc_180023BD2
0x180023b9e  mov     eax, esi
0x180023ba0  lock xadd [rbx+8], eax
0x180023ba5  add     eax, esi
0x180023ba7  jnz     short loc_180023BD2
0x180023ba9  mov     rax, [rbx]
0x180023bac  mov     rcx, rbx
0x180023baf  mov     rax, [rax]
0x180023bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bb7  mov     eax, esi
0x180023bb9  lock xadd [rbx+0Ch], eax
0x180023bbe  add     eax, esi
0x180023bc0  jnz     short loc_180023BD2
0x180023bc2  mov     rax, [rbx]
0x180023bc5  mov     rcx, rbx
0x180023bc8  mov     rax, [rax+8]
0x180023bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bd1  nop
0x180023bd2  lea     rcx, [rbp+57h+var_40]
0x180023bd6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023bdb  mov     r8, [rbp+57h+N]; N
0x180023bdf  lea     rcx, [rbp+57h+S1]
0x180023be3  mov     rax, [rbp+57h+S1]
0x180023be7  cmp     [rbp+57h+var_88], 7
0x180023bec  cmova   rcx, rax; S1
0x180023bf0  cmp     r8, 4
0x180023bf4  jnz     short loc_180023C0A
0x180023bf6  lea     rdx, aTrue; "true"
0x180023bfd  call    wmemcmp
0x180023c02  test    eax, eax
0x180023c04  jz      short loc_180023C30
0x180023c06  mov     rax, [rbp+57h+S1]
0x180023c0a  mov     r8, [rbp+57h+N]; N
0x180023c0e  lea     rcx, [rbp+57h+S1]
0x180023c12  cmp     [rbp+57h+var_88], 7
0x180023c17  cmova   rcx, rax; S1
0x180023c1b  cmp     r8, rdi
0x180023c1e  jnz     short loc_180023C35
0x180023c20  lea     rdx, a1; "1"
0x180023c27  call    wmemcmp
0x180023c2c  test    eax, eax
0x180023c2e  jnz     short loc_180023C35
0x180023c30  mov     r9d, edi
0x180023c33  jmp     short loc_180023C3B
0x180023c35  mov     edi, r14d
0x180023c38  mov     r9d, r14d
0x180023c3b  lea     rax, WPP_GLOBAL_Control
0x180023c42  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c49  cmp     rcx, rax
0x180023c4c  jz      short loc_180023C69
0x180023c4e  test    byte ptr [rcx+1Ch], 4
0x180023c52  jz      short loc_180023C69
0x180023c54  mov     edx, 23h ; '#'
0x180023c59  lea     r8, WPP_b84c187f0cdc3883f5c1fe70f958441c_Traceguids
0x180023c60  mov     rcx, [rcx+10h]
0x180023c64  call    WPP_SF_d
0x180023c69  lea     rcx, [rbp+57h+S1]
0x180023c6d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023c72  nop
0x180023c73  mov     rbx, qword ptr [rbp+57h+var_C0+8]
0x180023c77  test    rbx, rbx
0x180023c7a  jz      short loc_180023CAF
0x180023c7c  mov     eax, esi
0x180023c7e  lock xadd [rbx+8], eax
0x180023c83  add     eax, esi
0x180023c85  jnz     short loc_180023CAF
0x180023c87  mov     rax, [rbx]
0x180023c8a  mov     rcx, rbx
0x180023c8d  mov     rax, [rax]
0x180023c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c95  mov     edx, esi
0x180023c97  lock xadd [rbx+0Ch], edx
0x180023c9c  add     edx, esi
0x180023c9e  jnz     short loc_180023CAF
0x180023ca0  mov     rdx, [rbx]
0x180023ca3  mov     rcx, rbx
0x180023ca6  mov     rax, [rdx+8]
0x180023caa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023caf  mov     eax, edi
0x180023cb1  mov     rcx, [rbp+57h+var_20]
0x180023cb5  xor     rcx, rsp; StackCookie
0x180023cb8  call    __security_check_cookie
0x180023cbd  lea     r11, [rsp+0F0h+var_10]
0x180023cc5  mov     rbx, [r11+28h]
0x180023cc9  mov     rsi, [r11+30h]
0x180023ccd  mov     rsp, r11
0x180023cd0  pop     r14
0x180023cd2  pop     rdi
0x180023cd3  pop     rbp
0x180023cd4  retn
0x180023cd5  mov     ecx, 80004003h; int
0x180023cda  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180023ce0  mov     ecx, 80004003h; int
0x180023ce5  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180023ceb  lea     r8, _GUID_2933bf81_7b36_11d2_b20e_00c04f983e60; struct _GUID *
0x180023cf2  mov     rdx, rbx; struct IUnknown *
0x180023cf5  mov     ecx, eax; int
0x180023cf7  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x180023cfd  lea     rcx, [rbp+57h+var_A8]
0x180023d01  call    ??C?$_com_ptr_t@V?$_com_IIID@UIXMLDOMDocument3@MSXML2@@$1?_GUID_2933bf96_7b36_11d2_b20e_00c04f983e60@@3U__s_GUID@@B@@@@QEBAPEAUIXMLDOMDocument3@MSXML2@@XZ; _com_ptr_t<_com_IIID<MSXML2::IXMLDOMDocument3,&__s_GUID const _GUID_2933bf96_7b36_11d2_b20e_00c04f983e60>>::operator->(void)
0x180023d06  lea     rdx, [rbp+57h+var_D0]
0x180023d0a  mov     rcx, rax; struct IUnknown *
0x180023d0d  call    ?GetparseError@IXMLDOMDocument@MSXML2@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UIXMLDOMParseError@MSXML2@@$1?_GUID_3efaa426_272f_11d2_836f_0000f87a7782@@3U__s_GUID@@B@@@@XZ; MSXML2::IXMLDOMDocument::GetparseError(void)
0x180023d12  lea     rcx, [rbp+57h+var_D0]; this
0x180023d16  call    ??1Node@Details@Xml@WcmCommon@@QEAA@XZ; WcmCommon::Xml::Details::Node::~Node(void)
0x180023d1b  xor     edx, edx; struct IErrorInfo *
0x180023d1d  mov     ecx, 800705B9h; int
0x180023d22  call    ?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z; _com_raise_error(long,IErrorInfo *)
```
