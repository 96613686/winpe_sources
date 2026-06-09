# MsxmlDomElement::GetSingleSubElement(wchar_t const *)

- ea: `0x140010910`
- end: `0x140010c87`
- name: `?GetSingleSubElement@MsxmlDomElement@@UEAA?AV?$AutoRef@VAbstractDomElement@@@wmi@@PEB_W@Z`
- size: `887`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140002bd0`
- `0x140010910`
- `0x140011570`
- `0x14001159c`
- `0x1400117d8`
- `0x1400128e8`
- `0x14001950c`
- `0x140021b00`
- `0x140022cec`
- `0x14002f6c8`
- `0x140031810`
- `0x140034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *__fastcall MsxmlDomElement::GetSingleSubElement(__int64 a1, __int64 *a2, const char *a3)
{
  int v5; // ebx
  int v6; // eax
  int v7; // ebx
  void *v8; // rdi
  __int64 (__fastcall *v9)(void *, __int64); // rbx
  __int64 v10; // rax
  int v11; // ebx
  const char *v12; // rax
  int v13; // r8d
  int v14; // edx
  void *v15; // rcx
  void *v16; // rax
  __int64 v17; // rax
  void *v19; // [rsp+20h] [rbp-39h] BYREF
  __int64 v20; // [rsp+28h] [rbp-31h] BYREF
  __int64 v21; // [rsp+30h] [rbp-29h] BYREF
  void *v22; // [rsp+38h] [rbp-21h] BYREF
  __int64 *v23; // [rsp+40h] [rbp-19h] BYREF
  __int16 *pExceptionObject; // [rsp+48h] [rbp-11h] BYREF
  __int64 v25; // [rsp+50h] [rbp-9h]
  __int64 v26; // [rsp+58h] [rbp-1h]
  int v27; // [rsp+60h] [rbp+7h]
  __int64 v28; // [rsp+64h] [rbp+Bh]
  char v29; // [rsp+6Ch] [rbp+13h]
  GUID v30; // [rsp+78h] [rbp+1Fh] BYREF

  v23 = a2;
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_fda289614a233b29151e0c0c410d9667_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)&pExceptionObject, 0x57u, a3, 53);
    throw (EvtException *)&pExceptionObject;
  }
  v21 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(a1 + 32) + 96LL))(*(_QWORD *)(a1 + 32), &v21);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
        (unsigned int)v5);
    }
    pExceptionObject = word_14003838A;
    v25 = 0;
    v26 = 0;
    v27 = v5;
    v28 = -1;
    v29 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  while ( 1 )
  {
    v20 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 72LL))(v21, &v20);
    v7 = v6;
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
          (unsigned int)v6);
      }
      pExceptionObject = word_14003838A;
      v25 = 0;
      v26 = 0;
      v27 = v7;
      v28 = -1;
      v29 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v6 )
    {
      *a2 = 0;
      goto LABEL_38;
    }
    v19 = 0;
    v30 = IID_IXMLDOMElement;
    if ( *(_DWORD *)winrt::com_ptr<IXMLDOMNode>::as(&v20, &v22, &v30, &v19) != -2147467262 )
      break;
LABEL_16:
    if ( v19 )
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v19);
    if ( v20 )
      winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v20);
  }
  v23 = 0;
  v8 = v19;
  v9 = *(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)v19 + 328LL);
  v10 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(&v23);
  v11 = v9(v8, v10);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_fda289614a233b29151e0c0c410d9667_Traceguids,
        (unsigned int)v11);
    }
    pExceptionObject = word_14003838A;
    v25 = 0;
    v26 = 0;
    v27 = v11;
    v28 = -1;
    v29 = 0;
    throw (EvtException *)&pExceptionObject;
  }
  v12 = a3;
  do
  {
    v13 = *(unsigned __int16 *)&v12[(char *)v23 - a3];
    v14 = *(unsigned __int16 *)v12 - v13;
    if ( v14 )
      break;
    v12 += 2;
  }
  while ( v13 );
  if ( v14 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v23);
    goto LABEL_16;
  }
  v15 = operator new(0x28u);
  v22 = v15;
  if ( v15 )
  {
    v16 = v19;
    v19 = 0;
    v22 = v16;
    v17 = MsxmlDomElement::MsxmlDomElement(v15, &v22);
    *a2 = v17;
    if ( v17 )
      _InterlockedIncrement((volatile signed __int32 *)(v17 + 8));
  }
  else
  {
    *a2 = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&void SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&v23);
  if ( v19 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v19);
LABEL_38:
  if ( v20 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v20);
  if ( v21 )
    winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(&v21);
  return a2;
}

```

## disassembly

```asm
0x140010910  mov     [rsp-8+arg_10], rbx
0x140010915  push    rbp
0x140010916  push    rsi
0x140010917  push    rdi
0x140010918  push    r14
0x14001091a  push    r15
0x14001091c  lea     rbp, [rsp-37h]
0x140010921  sub     rsp, 90h
0x140010928  mov     rax, cs:__security_cookie
0x14001092f  xor     rax, rsp
0x140010932  mov     [rbp+57h+var_28], rax
0x140010936  mov     r14, r8
0x140010939  mov     rsi, rdx
0x14001093c  mov     [rbp+57h+var_70], rdx
0x140010940  xor     r15d, r15d
0x140010943  test    r8, r8
0x140010946  jnz     short loc_1400109A6
0x140010948  lea     rax, WPP_GLOBAL_Control
0x14001094f  lea     ebx, [r8+57h]
0x140010953  mov     rcx, cs:WPP_GLOBAL_Control
0x14001095a  cmp     rcx, rax
0x14001095d  jz      short loc_140010984
0x14001095f  test    dword ptr [rcx+1Ch], 400000h
0x140010966  jz      short loc_140010984
0x140010968  cmp     byte ptr [rcx+19h], 2
0x14001096c  jb      short loc_140010984
0x14001096e  lea     edx, [rbx-4Ah]
0x140010971  mov     r9d, ebx
0x140010974  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x14001097b  mov     rcx, [rcx+10h]
0x14001097f  call    WPP_SF_d
0x140010984  mov     r9d, 35h ; '5'; int
0x14001098a  mov     edx, ebx; unsigned int
0x14001098c  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140010990  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140010995  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14001099c  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400109a0  call    _CxxThrowException_0
0x1400109a6  mov     [rbp+57h+var_80], r15
0x1400109aa  mov     rcx, [rcx+20h]
0x1400109ae  mov     rax, [rcx]
0x1400109b1  lea     rdx, [rbp+57h+var_80]
0x1400109b5  mov     rax, [rax+60h]
0x1400109b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109be  mov     ebx, eax
0x1400109c0  test    eax, eax
0x1400109c2  jns     short loc_140010A31
0x1400109c4  lea     rax, WPP_GLOBAL_Control
0x1400109cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400109d2  cmp     rcx, rax
0x1400109d5  jz      short loc_1400109FE
0x1400109d7  test    dword ptr [rcx+1Ch], 400000h
0x1400109de  jz      short loc_1400109FE
0x1400109e0  cmp     byte ptr [rcx+19h], 2
0x1400109e4  jb      short loc_1400109FE
0x1400109e6  mov     edx, 0Eh
0x1400109eb  mov     r9d, ebx
0x1400109ee  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x1400109f5  mov     rcx, [rcx+10h]
0x1400109f9  call    WPP_SF_d
0x1400109fe  lea     rax, word_14003838A
0x140010a05  mov     [rbp+57h+pExceptionObject], rax
0x140010a09  mov     [rbp+57h+var_60], r15
0x140010a0d  mov     [rbp+57h+var_58], r15
0x140010a11  mov     [rbp+57h+var_50], ebx
0x140010a14  mov     [rbp+57h+var_4C], 0FFFFFFFFFFFFFFFFh
0x140010a1c  mov     [rbp+57h+var_44], r15b
0x140010a20  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010a27  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140010a2b  call    _CxxThrowException_0
0x140010a31  mov     [rbp+57h+var_88], r15
0x140010a35  mov     rcx, [rbp+57h+var_80]
0x140010a39  mov     rax, [rcx]
0x140010a3c  lea     rdx, [rbp+57h+var_88]
0x140010a40  mov     rax, [rax+48h]
0x140010a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a49  mov     ebx, eax
0x140010a4b  test    eax, eax
0x140010a4d  js      loc_140010C1A
0x140010a53  test    eax, eax
0x140010a55  jnz     loc_140010BD2
0x140010a5b  mov     [rbp+57h+var_90], r15
0x140010a5f  movups  xmm0, xmmword ptr cs:IID_IXMLDOMElement.Data1
0x140010a66  movdqu  [rbp+57h+var_38], xmm0
0x140010a6b  lea     r9, [rbp+57h+var_90]
0x140010a6f  lea     r8, [rbp+57h+var_38]
0x140010a73  lea     rdx, [rbp+57h+var_78]
0x140010a77  lea     rcx, [rbp+57h+var_88]
0x140010a7b  call    ?as@?$com_ptr@UIXMLDOMNode@@@winrt@@QEBA?AUhresult@2@AEBUguid@2@PEAPEAX@Z; winrt::com_ptr<IXMLDOMNode>::as(winrt::guid const &,void * *)
0x140010a80  cmp     dword ptr [rax], 80004002h
0x140010a86  jnz     short loc_140010AA9
0x140010a88  cmp     [rbp+57h+var_90], r15
0x140010a8c  jz      short loc_140010A98
0x140010a8e  lea     rcx, [rbp+57h+var_90]
0x140010a92  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140010a97  nop
0x140010a98  cmp     [rbp+57h+var_88], r15
0x140010a9c  jz      short loc_140010A31
0x140010a9e  lea     rcx, [rbp+57h+var_88]
0x140010aa2  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140010aa7  jmp     short loc_140010A31
0x140010aa9  mov     [rbp+57h+var_70], r15
0x140010aad  mov     rdi, [rbp+57h+var_90]
0x140010ab1  mov     rax, [rdi]
0x140010ab4  mov     rbx, [rax+148h]
0x140010abb  lea     rcx, [rbp+57h+var_70]
0x140010abf  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEA_WXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::put(void)
0x140010ac4  mov     rdx, rax
0x140010ac7  mov     rcx, rdi
0x140010aca  mov     rax, rbx
0x140010acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010ad2  mov     ebx, eax
0x140010ad4  test    eax, eax
0x140010ad6  js      loc_140010B65
0x140010adc  mov     rax, r14
0x140010adf  mov     rcx, [rbp+57h+var_70]
0x140010ae3  sub     rcx, r14
0x140010ae6  movzx   edx, word ptr [rax]
0x140010ae9  movzx   r8d, word ptr [rax+rcx]
0x140010aee  sub     edx, r8d
0x140010af1  jnz     short loc_140010AFC
0x140010af3  add     rax, 2
0x140010af7  test    r8d, r8d
0x140010afa  jnz     short loc_140010AE6
0x140010afc  test    edx, edx
0x140010afe  jz      short loc_140010B0E
0x140010b00  lea     rcx, [rbp+57h+var_70]
0x140010b04  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010b09  jmp     loc_140010A88
0x140010b0e  mov     ecx, 28h ; '('; dwBytes
0x140010b13  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010b18  mov     rcx, rax
0x140010b1b  mov     [rbp+57h+var_78], rax
0x140010b1f  test    rax, rax
0x140010b22  jz      short loc_140010B47
0x140010b24  mov     rax, [rbp+57h+var_90]
0x140010b28  mov     [rbp+57h+var_90], r15
0x140010b2c  mov     [rbp+57h+var_78], rax
0x140010b30  lea     rdx, [rbp+57h+var_78]
0x140010b34  call    ??0MsxmlDomElement@@QEAA@U?$com_ptr@UIXMLDOMElement@@@winrt@@@Z; MsxmlDomElement::MsxmlDomElement(winrt::com_ptr<IXMLDOMElement>)
0x140010b39  mov     [rsi], rax
0x140010b3c  test    rax, rax
0x140010b3f  jz      short loc_140010B4A
0x140010b41  lock inc dword ptr [rax+8]
0x140010b45  jmp     short loc_140010B4A
0x140010b47  mov     [rsi], r15
0x140010b4a  lea     rcx, [rbp+57h+var_70]
0x140010b4e  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6AXPEA_W@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void (*)(wchar_t *),&SysFreeString(wchar_t *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x140010b53  nop
0x140010b54  cmp     [rbp+57h+var_90], r15
0x140010b58  jz      short loc_140010BD5
0x140010b5a  lea     rcx, [rbp+57h+var_90]
0x140010b5e  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140010b63  jmp     short loc_140010BD5
0x140010b65  lea     rax, WPP_GLOBAL_Control
0x140010b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b73  cmp     rcx, rax
0x140010b76  jz      short loc_140010B9F
0x140010b78  test    dword ptr [rcx+1Ch], 400000h
0x140010b7f  jz      short loc_140010B9F
0x140010b81  cmp     byte ptr [rcx+19h], 2
0x140010b85  jb      short loc_140010B9F
0x140010b87  mov     edx, 10h
0x140010b8c  mov     r9d, ebx
0x140010b8f  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x140010b96  mov     rcx, [rcx+10h]
0x140010b9a  call    WPP_SF_d
0x140010b9f  lea     rax, word_14003838A
0x140010ba6  mov     [rbp+57h+pExceptionObject], rax
0x140010baa  mov     [rbp+57h+var_60], r15
0x140010bae  mov     [rbp+57h+var_58], r15
0x140010bb2  mov     [rbp+57h+var_50], ebx
0x140010bb5  mov     [rbp+57h+var_4C], 0FFFFFFFFFFFFFFFFh
0x140010bbd  mov     [rbp+57h+var_44], r15b
0x140010bc1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010bc8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140010bcc  call    _CxxThrowException_0
0x140010bd2  mov     [rsi], r15
0x140010bd5  cmp     [rbp+57h+var_88], r15
0x140010bd9  jz      short loc_140010BE5
0x140010bdb  lea     rcx, [rbp+57h+var_88]
0x140010bdf  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140010be4  nop
0x140010be5  cmp     [rbp+57h+var_80], r15
0x140010be9  jz      short loc_140010BF4
0x140010beb  lea     rcx, [rbp+57h+var_80]
0x140010bef  call    ?unconditional_release_ref@?$com_ptr@UIXMLDOMParseError@@@winrt@@AEAAXXZ; winrt::com_ptr<IXMLDOMParseError>::unconditional_release_ref(void)
0x140010bf4  mov     rax, rsi
0x140010bf7  mov     rcx, [rbp+57h+var_28]
0x140010bfb  xor     rcx, rsp; StackCookie
0x140010bfe  call    __security_check_cookie
0x140010c03  mov     rbx, [rsp+0B0h+arg_10]
0x140010c0b  add     rsp, 90h
0x140010c12  pop     r15
0x140010c14  pop     r14
0x140010c16  pop     rdi
0x140010c17  pop     rsi
0x140010c18  pop     rbp
0x140010c19  retn
0x140010c1a  lea     rax, WPP_GLOBAL_Control
0x140010c21  mov     rcx, cs:WPP_GLOBAL_Control
0x140010c28  cmp     rcx, rax
0x140010c2b  jz      short loc_140010C54
0x140010c2d  test    dword ptr [rcx+1Ch], 400000h
0x140010c34  jz      short loc_140010C54
0x140010c36  cmp     byte ptr [rcx+19h], 2
0x140010c3a  jb      short loc_140010C54
0x140010c3c  mov     edx, 0Fh
0x140010c41  mov     r9d, ebx
0x140010c44  lea     r8, WPP_fda289614a233b29151e0c0c410d9667_Traceguids
0x140010c4b  mov     rcx, [rcx+10h]
0x140010c4f  call    WPP_SF_d
0x140010c54  lea     rax, word_14003838A
0x140010c5b  mov     [rbp+57h+pExceptionObject], rax
0x140010c5f  mov     [rbp+57h+var_60], r15
0x140010c63  mov     [rbp+57h+var_58], r15
0x140010c67  mov     [rbp+57h+var_50], ebx
0x140010c6a  mov     [rbp+57h+var_4C], 0FFFFFFFFFFFFFFFFh
0x140010c72  mov     [rbp+57h+var_44], r15b
0x140010c76  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140010c7d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140010c81  call    _CxxThrowException_0
```
